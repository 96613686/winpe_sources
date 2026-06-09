# AipGetDeviceDosName

- ea: `0x18000533c`
- end: `0x18000558c`
- name: `AipGetDeviceDosName`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180004980`

## callees

- `0x180003fd4`
- `0x18000533c`
- `0x180009562`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000538c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000538c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000537a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000537a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005493`
- `ntdll!NtDeviceIoControlFile` at `0x180005414`
- `ntdll!NtDeviceIoControlFile` at `0x180005414`
- `ntdll!RtlFreeHeap` at `0x18000543f`
- `ntdll!RtlFreeHeap` at `0x18000546c`
- `ntdll!RtlFreeHeap` at `0x180005484`
- `ntdll!RtlFreeHeap` at `0x18000543f`
- `ntdll!RtlFreeHeap` at `0x18000546c`
- `ntdll!RtlFreeHeap` at `0x180005484`
- `ntdll!RtlInitUnicodeString` at `0x1800054b3`
- `ntdll!RtlInitUnicodeString` at `0x1800054b3`

## string_xrefs

- `0x180005365`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall AipGetDeviceDosName(const void **a1, struct _UNICODE_STRING *a2)
{
  WCHAR *OutputBuffer; // r14
  HANDLE FileW; // rbp
  _WORD *InputBuffer; // r15
  DWORD LastError; // eax
  unsigned int v8; // ebx
  ULONG InputBufferLength; // esi
  WCHAR *v10; // r8
  __int64 OutputBufferLength; // rbx
  NTSTATUS v12; // eax
  __int64 Length; // rcx
  PWSTR Buffer; // rax
  WCHAR *v16; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF

  OutputBuffer = 0;
  IoStatusBlock = 0;
  FileW = CreateFileW(L"\\\\.\\MountPointManager", 0, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    InputBuffer = 0;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    InputBufferLength = *(unsigned __int16 *)a1 + 4;
    InputBuffer = (_WORD *)AiAlloc(InputBufferLength);
    if ( InputBuffer )
    {
      *InputBuffer = *(_WORD *)a1;
      memcpy_0(InputBuffer + 1, a1[1], *(unsigned __int16 *)a1);
      v10 = 0;
      for ( OutputBufferLength = 528; ; OutputBufferLength = (unsigned int)(*(_DWORD *)OutputBuffer + 8) )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
        OutputBuffer = (WCHAR *)AiAlloc(OutputBufferLength);
        if ( !OutputBuffer )
          break;
        v12 = NtDeviceIoControlFile(
                FileW,
                0,
                0,
                0,
                &IoStatusBlock,
                0x6D0030u,
                InputBuffer,
                InputBufferLength,
                OutputBuffer,
                OutputBufferLength);
        v8 = v12;
        if ( v12 != -2147483643 )
        {
          if ( v12 < 0 )
            goto LABEL_10;
          RtlInitUnicodeString(a2, OutputBuffer + 2);
          Length = a2->Length;
          if ( (_DWORD)Length == 96 || (_DWORD)Length == 98 && a2->Buffer[48] == 92 )
          {
            Buffer = a2->Buffer;
            if ( *Buffer == 92
              && (Buffer[1] == 63 || Buffer[1] == 92)
              && Buffer[2] == 63
              && Buffer[3] == 92
              && Buffer[4] == 86
              && Buffer[5] == 111
              && Buffer[6] == 108
              && Buffer[7] == 117
              && Buffer[8] == 109
              && Buffer[9] == 101
              && Buffer[10] == 123
              && Buffer[19] == 45
              && Buffer[24] == 45
              && Buffer[29] == 45
              && Buffer[34] == 45
              && Buffer[47] == 125 )
            {
              a2->Length = 0;
              a2->Buffer = 0;
              goto LABEL_10;
            }
          }
          a2->MaximumLength = Length;
          v16 = (WCHAR *)AiAlloc(Length);
          a2->Buffer = v16;
          if ( v16 )
          {
            memcpy_0(v16, OutputBuffer + 2, a2->Length);
            goto LABEL_10;
          }
          break;
        }
        v10 = OutputBuffer;
      }
    }
    v8 = -1073741801;
  }
LABEL_10:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBuffer);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, InputBuffer);
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return v8;
}

```

## disassembly

```asm
0x18000533c  mov     rax, rsp
0x18000533f  push    rbx
0x180005340  push    rbp
0x180005341  push    rsi
0x180005342  push    rdi
0x180005343  push    r14
0x180005345  push    r15
0x180005347  sub     rsp, 68h
0x18000534b  xor     r14d, r14d
0x18000534e  mov     rdi, rdx
0x180005351  mov     [rax-68h], r14
0x180005355  mov     rbx, rcx
0x180005358  xorps   xmm0, xmm0
0x18000535b  mov     dword ptr [rax-70h], 80h
0x180005362  xor     r9d, r9d; lpSecurityAttributes
0x180005365  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x18000536c  lea     r8d, [r14+3]; dwShareMode
0x180005370  xor     edx, edx; dwDesiredAccess
0x180005372  mov     [rax-78h], r8d
0x180005376  movups  xmmword ptr [rax-48h], xmm0
0x18000537a  call    cs:__imp_CreateFileW
0x180005380  mov     rbp, rax
0x180005383  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005387  jnz     short loc_1800053AA
0x180005389  xor     r15d, r15d
0x18000538c  call    cs:__imp_GetLastError
0x180005392  mov     ebx, eax
0x180005394  test    eax, eax
0x180005396  jz      loc_18000545A
0x18000539c  movzx   ebx, ax
0x18000539f  or      ebx, 80070000h
0x1800053a5  jmp     loc_18000545A
0x1800053aa  movzx   esi, word ptr [rbx]
0x1800053ad  add     esi, 4
0x1800053b0  mov     ecx, esi
0x1800053b2  call    AiAlloc
0x1800053b7  mov     r15, rax
0x1800053ba  test    rax, rax
0x1800053bd  jz      loc_180005455
0x1800053c3  movzx   eax, word ptr [rbx]
0x1800053c6  lea     rcx, [r15+2]; void *
0x1800053ca  mov     [r15], ax
0x1800053ce  movzx   r8d, word ptr [rbx]; Size
0x1800053d2  mov     rdx, [rbx+8]; Src
0x1800053d6  call    memcpy_0
0x1800053db  xor     r8d, r8d
0x1800053de  mov     ebx, 210h
0x1800053e3  jmp     short loc_180005430
0x1800053e5  mov     [rsp+98h+OutputBufferLength], ebx; OutputBufferLength
0x1800053e9  lea     rax, [rsp+98h+var_48]
0x1800053ee  mov     [rsp+98h+OutputBuffer], r14; OutputBuffer
0x1800053f3  xor     r9d, r9d; ApcContext
0x1800053f6  mov     [rsp+98h+InputBufferLength], esi; InputBufferLength
0x1800053fa  xor     r8d, r8d; ApcRoutine
0x1800053fd  mov     [rsp+98h+InputBuffer], r15; InputBuffer
0x180005402  xor     edx, edx; Event
0x180005404  mov     [rsp+98h+IoControlCode], 6D0030h; IoControlCode
0x18000540c  mov     rcx, rbp; FileHandle
0x18000540f  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180005414  call    cs:__imp_NtDeviceIoControlFile
0x18000541a  mov     ebx, eax
0x18000541c  cmp     eax, 80000005h
0x180005421  jnz     loc_1800054A8
0x180005427  mov     ebx, [r14]
0x18000542a  mov     r8, r14; P
0x18000542d  add     ebx, 8
0x180005430  mov     rcx, gs:60h
0x180005439  xor     edx, edx; Flags
0x18000543b  mov     rcx, [rcx+30h]; HeapHandle
0x18000543f  call    cs:__imp_RtlFreeHeap
0x180005445  mov     rcx, rbx
0x180005448  call    AiAlloc
0x18000544d  mov     r14, rax
0x180005450  test    rax, rax
0x180005453  jnz     short loc_1800053E5
0x180005455  mov     ebx, 0C0000017h
0x18000545a  mov     rcx, gs:60h
0x180005463  mov     r8, r14; P
0x180005466  xor     edx, edx; Flags
0x180005468  mov     rcx, [rcx+30h]; HeapHandle
0x18000546c  call    cs:__imp_RtlFreeHeap
0x180005472  mov     rcx, gs:60h
0x18000547b  mov     r8, r15; P
0x18000547e  xor     edx, edx; Flags
0x180005480  mov     rcx, [rcx+30h]; HeapHandle
0x180005484  call    cs:__imp_RtlFreeHeap
0x18000548a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18000548e  jz      short loc_180005499
0x180005490  mov     rcx, rbp; hObject
0x180005493  call    cs:__imp_CloseHandle
0x180005499  mov     eax, ebx
0x18000549b  add     rsp, 68h
0x18000549f  pop     r15
0x1800054a1  pop     r14
0x1800054a3  pop     rdi
0x1800054a4  pop     rsi
0x1800054a5  pop     rbp
0x1800054a6  pop     rbx
0x1800054a7  retn
0x1800054a8  test    eax, eax
0x1800054aa  js      short loc_18000545A
0x1800054ac  lea     rdx, [r14+4]; SourceString
0x1800054b0  mov     rcx, rdi; DestinationString
0x1800054b3  call    cs:__imp_RtlInitUnicodeString
0x1800054b9  movzx   ecx, word ptr [rdi]
0x1800054bc  mov     dx, 5Ch ; '\'
0x1800054c0  cmp     ecx, 60h ; '`'
0x1800054c3  jz      short loc_1800054DC
0x1800054c5  cmp     ecx, 62h ; 'b'
0x1800054c8  jnz     loc_180005561
0x1800054ce  mov     rax, [rdi+8]
0x1800054d2  cmp     [rax+60h], dx
0x1800054d6  jnz     loc_180005561
0x1800054dc  mov     rax, [rdi+8]
0x1800054e0  cmp     [rax], dx
0x1800054e3  jnz     short loc_180005561
0x1800054e5  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800054ea  jz      short loc_1800054F2
0x1800054ec  cmp     [rax+2], dx
0x1800054f0  jnz     short loc_180005561
0x1800054f2  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800054f7  jnz     short loc_180005561
0x1800054f9  cmp     [rax+6], dx
0x1800054fd  jnz     short loc_180005561
0x1800054ff  cmp     word ptr [rax+8], 56h ; 'V'
0x180005504  jnz     short loc_180005561
0x180005506  cmp     word ptr [rax+0Ah], 6Fh ; 'o'
0x18000550b  jnz     short loc_180005561
0x18000550d  cmp     word ptr [rax+0Ch], 6Ch ; 'l'
0x180005512  jnz     short loc_180005561
0x180005514  cmp     word ptr [rax+0Eh], 75h ; 'u'
0x180005519  jnz     short loc_180005561
0x18000551b  cmp     word ptr [rax+10h], 6Dh ; 'm'
0x180005520  jnz     short loc_180005561
0x180005522  cmp     word ptr [rax+12h], 65h ; 'e'
0x180005527  jnz     short loc_180005561
0x180005529  cmp     word ptr [rax+14h], 7Bh ; '{'
0x18000552e  jnz     short loc_180005561
0x180005530  mov     dx, 2Dh ; '-'
0x180005534  cmp     [rax+26h], dx
0x180005538  jnz     short loc_180005561
0x18000553a  cmp     [rax+30h], dx
0x18000553e  jnz     short loc_180005561
0x180005540  cmp     [rax+3Ah], dx
0x180005544  jnz     short loc_180005561
0x180005546  cmp     [rax+44h], dx
0x18000554a  jnz     short loc_180005561
0x18000554c  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x180005551  jnz     short loc_180005561
0x180005553  xor     eax, eax
0x180005555  mov     [rdi], ax
0x180005558  mov     [rdi+8], rax
0x18000555c  jmp     loc_18000545A
0x180005561  mov     [rdi+2], cx
0x180005565  call    AiAlloc
0x18000556a  mov     [rdi+8], rax
0x18000556e  test    rax, rax
0x180005571  jz      loc_180005455
0x180005577  movzx   r8d, word ptr [rdi]; Size
0x18000557b  lea     rdx, [r14+4]; Src
0x18000557f  mov     rcx, rax; void *
0x180005582  call    memcpy_0
0x180005587  jmp     loc_18000545A
```
