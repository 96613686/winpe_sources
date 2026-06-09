# TakeDiskOfflineByHandle_LockVolumes

- ea: `0x14001bfa0`
- end: `0x14001c1cf`
- name: `TakeDiskOfflineByHandle_LockVolumes`
- size: `559`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14001be40`

## callees

- `0x14001bfa0`
- `0x14001da08`
- `0x14001dae0`
- `0x14001dc84`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001c170`
- `KERNEL32!CloseHandle` at `0x14001c170`
- `KERNEL32!HeapReAlloc` at `0x14001c116`
- `KERNEL32!HeapReAlloc` at `0x14001c116`
- `KERNEL32!HeapAlloc` at `0x14001c061`
- `KERNEL32!HeapAlloc` at `0x14001c061`
- `KERNEL32!HeapFree` at `0x14001c187`
- `KERNEL32!HeapFree` at `0x14001c187`
- `KERNEL32!GetProcessHeap` at `0x14001bfe4`
- `KERNEL32!GetProcessHeap` at `0x14001bfe4`
- `KERNEL32!SetLastError` at `0x14001c074`
- `KERNEL32!SetLastError` at `0x14001c19c`
- `KERNEL32!SetLastError` at `0x14001c074`
- `KERNEL32!SetLastError` at `0x14001c19c`
- `KERNEL32!GetLastError` at `0x14001c042`
- `KERNEL32!GetLastError` at `0x14001c12d`
- `KERNEL32!GetLastError` at `0x14001c13e`
- `KERNEL32!GetLastError` at `0x14001c15b`
- `KERNEL32!GetLastError` at `0x14001c042`
- `KERNEL32!GetLastError` at `0x14001c12d`
- `KERNEL32!GetLastError` at `0x14001c13e`
- `KERNEL32!GetLastError` at `0x14001c15b`
- `KERNEL32!DeviceIoControl` at `0x14001c01b`
- `KERNEL32!DeviceIoControl` at `0x14001c0e2`
- `KERNEL32!DeviceIoControl` at `0x14001c01b`
- `KERNEL32!DeviceIoControl` at `0x14001c0e2`
- `KERNEL32!CreateFileW` at `0x14001c0a9`
- `KERNEL32!CreateFileW` at `0x14001c0a9`

## pseudocode

```c
__int64 __fastcall TakeDiskOfflineByHandle_LockVolumes(HANDLE hDevice, int a2, _DWORD *a3, _QWORD *a4)
{
  __int64 FirstVolumeIdentifier; // rbp
  _QWORD *v9; // rsi
  HANDLE ProcessHeap; // r15
  __int64 v11; // rdi
  unsigned int NextVolumeIdentifier; // ebx
  HANDLE FileW; // rax
  _QWORD *v14; // rax
  DWORD LastError; // r14d
  unsigned int VolumeIdentifierClose; // eax
  __int64 OutBuffer; // [rsp+40h] [rbp-C8h] BYREF
  int v19; // [rsp+48h] [rbp-C0h]
  WCHAR FileName[56]; // [rsp+50h] [rbp-B8h] BYREF

  OutBuffer = 0;
  v19 = 0;
  FirstVolumeIdentifier = -1;
  v9 = 0;
  ProcessHeap = GetProcessHeap();
  v11 = 0;
  NextVolumeIdentifier = DeviceIoControl(hDevice, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, 0, 0);
  if ( NextVolumeIdentifier )
  {
    FirstVolumeIdentifier = (__int64)FindFirstVolumeIdentifier(HIDWORD(OutBuffer), FileName);
    if ( FirstVolumeIdentifier == -1 )
    {
      if ( GetLastError() != 18 )
        NextVolumeIdentifier = 0;
    }
    else
    {
      v9 = HeapAlloc(ProcessHeap, 0, 8u);
      if ( v9 )
      {
        while ( 1 )
        {
          FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0, 0);
          v9[v11] = FileW;
          if ( FileW == (HANDLE)-1LL )
            break;
          v11 = (unsigned int)(v11 + 1);
          NextVolumeIdentifier = DeviceIoControl(FileW, 0x90018u, 0, 0, 0, 0, 0, 0);
          if ( !NextVolumeIdentifier && !a2 )
            break;
          NextVolumeIdentifier = FindNextVolumeIdentifier((void *)FirstVolumeIdentifier, FileName);
          if ( !NextVolumeIdentifier )
          {
            NextVolumeIdentifier = GetLastError() == 18;
            break;
          }
          v14 = HeapReAlloc(ProcessHeap, 0, v9, 8LL * (unsigned int)v11 + 8);
          if ( !v14 )
            goto LABEL_6;
          v9 = v14;
        }
      }
      else
      {
LABEL_6:
        NextVolumeIdentifier = 0;
        SetLastError(8u);
      }
    }
  }
  LastError = GetLastError();
  if ( FirstVolumeIdentifier == -1 )
  {
LABEL_17:
    if ( NextVolumeIdentifier )
      goto LABEL_24;
    goto LABEL_20;
  }
  VolumeIdentifierClose = FindVolumeIdentifierClose((void *)FirstVolumeIdentifier);
  if ( NextVolumeIdentifier )
  {
    NextVolumeIdentifier = VolumeIdentifierClose;
    LastError = GetLastError();
    goto LABEL_17;
  }
LABEL_20:
  while ( (_DWORD)v11 )
  {
    LODWORD(v11) = v11 - 1;
    CloseHandle((HANDLE)v9[(unsigned int)v11]);
  }
  if ( v9 )
    HeapFree(ProcessHeap, 0, v9);
  v9 = 0;
  LODWORD(v11) = 0;
LABEL_24:
  *a3 = v11;
  *a4 = v9;
  SetLastError(LastError);
  return NextVolumeIdentifier;
}

```

## disassembly

```asm
0x14001bfa0  mov     [rsp+arg_8], rbx
0x14001bfa5  push    rbp
0x14001bfa6  push    rsi
0x14001bfa7  push    rdi
0x14001bfa8  push    r12
0x14001bfaa  push    r13
0x14001bfac  push    r14
0x14001bfae  push    r15
0x14001bfb0  sub     rsp, 0D0h
0x14001bfb7  mov     rax, cs:__security_cookie
0x14001bfbe  xor     rax, rsp
0x14001bfc1  mov     [rsp+108h+var_48], rax
0x14001bfc9  xor     eax, eax
0x14001bfcb  mov     r12, r9
0x14001bfce  mov     [rsp+108h+OutBuffer], rax
0x14001bfd3  mov     r13, r8
0x14001bfd6  mov     [rsp+108h+var_C0], eax
0x14001bfda  mov     r14d, edx
0x14001bfdd  mov     rbx, rcx
0x14001bfe0  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14001bfe4  call    cs:__imp_GetProcessHeap
0x14001bfea  xor     esi, esi
0x14001bfec  xor     r9d, r9d; nInBufferSize
0x14001bfef  mov     [rsp+108h+lpOverlapped], rsi; lpOverlapped
0x14001bff4  mov     r15, rax
0x14001bff7  mov     [rsp+108h+lpBytesReturned], rsi; lpBytesReturned
0x14001bffc  lea     rax, [rsp+108h+OutBuffer]
0x14001c001  mov     [rsp+108h+nOutBufferSize], 0Ch; nOutBufferSize
0x14001c009  xor     r8d, r8d; lpInBuffer
0x14001c00c  mov     edx, 2D1080h; dwIoControlCode
0x14001c011  mov     [rsp+108h+lpOutBuffer], rax; lpOutBuffer
0x14001c016  mov     rcx, rbx; hDevice
0x14001c019  xor     edi, edi
0x14001c01b  call    cs:__imp_DeviceIoControl
0x14001c021  mov     ebx, eax
0x14001c023  test    eax, eax
0x14001c025  jz      loc_14001C13E
0x14001c02b  mov     ecx, dword ptr [rsp+108h+OutBuffer+4]; unsigned int
0x14001c02f  lea     rdx, [rsp+108h+FileName]; unsigned __int16 *
0x14001c034  call    ?FindFirstVolumeIdentifier@@YAPEAXKPEAG@Z; FindFirstVolumeIdentifier(ulong,ushort *)
0x14001c039  mov     rbp, rax
0x14001c03c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001c040  jnz     short loc_14001C058
0x14001c042  call    cs:__imp_GetLastError
0x14001c048  cmp     eax, 12h
0x14001c04b  jz      loc_14001C13E
0x14001c051  xor     ebx, ebx
0x14001c053  jmp     loc_14001C13E
0x14001c058  xor     edx, edx; dwFlags
0x14001c05a  mov     rcx, r15; hHeap
0x14001c05d  lea     r8d, [rdx+8]; dwBytes
0x14001c061  call    cs:__imp_HeapAlloc
0x14001c067  mov     rsi, rax
0x14001c06a  test    rax, rax
0x14001c06d  jnz     short loc_14001C07F
0x14001c06f  xor     ebx, ebx
0x14001c071  lea     ecx, [rbx+8]; dwErrCode
0x14001c074  call    cs:__imp_SetLastError
0x14001c07a  jmp     loc_14001C13E
0x14001c07f  xor     r9d, r9d; lpSecurityAttributes
0x14001c082  mov     [rsp+108h+lpBytesReturned], 0; hTemplateFile
0x14001c08b  mov     [rsp+108h+nOutBufferSize], 0; dwFlagsAndAttributes
0x14001c093  lea     rcx, [rsp+108h+FileName]; lpFileName
0x14001c098  mov     edx, 0C0000000h; dwDesiredAccess
0x14001c09d  mov     dword ptr [rsp+108h+lpOutBuffer], 3; dwCreationDisposition
0x14001c0a5  lea     r8d, [r9+3]; dwShareMode
0x14001c0a9  call    cs:__imp_CreateFileW
0x14001c0af  mov     [rsi+rdi*8], rax
0x14001c0b3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001c0b7  jz      loc_14001C13E
0x14001c0bd  xor     ecx, ecx
0x14001c0bf  xor     r9d, r9d; nInBufferSize
0x14001c0c2  mov     [rsp+108h+lpOverlapped], rcx; lpOverlapped
0x14001c0c7  xor     r8d, r8d; lpInBuffer
0x14001c0ca  mov     [rsp+108h+lpBytesReturned], rcx; lpBytesReturned
0x14001c0cf  mov     edx, 90018h; dwIoControlCode
0x14001c0d4  mov     [rsp+108h+nOutBufferSize], ecx; nOutBufferSize
0x14001c0d8  inc     edi
0x14001c0da  mov     [rsp+108h+lpOutBuffer], rcx; lpOutBuffer
0x14001c0df  mov     rcx, rax; hDevice
0x14001c0e2  call    cs:__imp_DeviceIoControl
0x14001c0e8  mov     ebx, eax
0x14001c0ea  test    eax, eax
0x14001c0ec  jnz     short loc_14001C0F3
0x14001c0ee  test    r14d, r14d
0x14001c0f1  jz      short loc_14001C13E
0x14001c0f3  lea     rdx, [rsp+108h+FileName]; unsigned __int16 *
0x14001c0f8  mov     rcx, rbp; void *
0x14001c0fb  call    ?FindNextVolumeIdentifier@@YAHPEAXPEAG@Z; FindNextVolumeIdentifier(void *,ushort *)
0x14001c100  mov     ebx, eax
0x14001c102  test    eax, eax
0x14001c104  jz      short loc_14001C12D
0x14001c106  lea     r9, ds:8[rdi*8]; dwBytes
0x14001c10e  mov     r8, rsi; lpMem
0x14001c111  xor     edx, edx; dwFlags
0x14001c113  mov     rcx, r15; hHeap
0x14001c116  call    cs:__imp_HeapReAlloc
0x14001c11c  test    rax, rax
0x14001c11f  jz      loc_14001C06F
0x14001c125  mov     rsi, rax
0x14001c128  jmp     loc_14001C07F
0x14001c12d  call    cs:__imp_GetLastError
0x14001c133  cmp     eax, 12h
0x14001c136  mov     eax, 1
0x14001c13b  cmovz   ebx, eax
0x14001c13e  call    cs:__imp_GetLastError
0x14001c144  mov     r14d, eax
0x14001c147  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14001c14b  jz      short loc_14001C164
0x14001c14d  mov     rcx, rbp; lpMem
0x14001c150  call    ?FindVolumeIdentifierClose@@YAHPEAX@Z; FindVolumeIdentifierClose(void *)
0x14001c155  test    ebx, ebx
0x14001c157  jz      short loc_14001C176
0x14001c159  mov     ebx, eax
0x14001c15b  call    cs:__imp_GetLastError
0x14001c161  mov     r14d, eax
0x14001c164  test    ebx, ebx
0x14001c166  jnz     short loc_14001C191
0x14001c168  jmp     short loc_14001C176
0x14001c16a  dec     edi
0x14001c16c  mov     rcx, [rsi+rdi*8]; hObject
0x14001c170  call    cs:__imp_CloseHandle
0x14001c176  test    edi, edi
0x14001c178  jnz     short loc_14001C16A
0x14001c17a  test    rsi, rsi
0x14001c17d  jz      short loc_14001C18D
0x14001c17f  mov     r8, rsi; lpMem
0x14001c182  xor     edx, edx; dwFlags
0x14001c184  mov     rcx, r15; hHeap
0x14001c187  call    cs:__imp_HeapFree
0x14001c18d  xor     esi, esi
0x14001c18f  xor     edi, edi
0x14001c191  mov     [r13+0], edi
0x14001c195  mov     ecx, r14d; dwErrCode
0x14001c198  mov     [r12], rsi
0x14001c19c  call    cs:__imp_SetLastError
0x14001c1a2  mov     eax, ebx
0x14001c1a4  mov     rcx, [rsp+108h+var_48]
0x14001c1ac  xor     rcx, rsp; StackCookie
0x14001c1af  call    __security_check_cookie
0x14001c1b4  mov     rbx, [rsp+108h+arg_8]
0x14001c1bc  add     rsp, 0D0h
0x14001c1c3  pop     r15
0x14001c1c5  pop     r14
0x14001c1c7  pop     r13
0x14001c1c9  pop     r12
0x14001c1cb  pop     rdi
0x14001c1cc  pop     rsi
0x14001c1cd  pop     rbp
0x14001c1ce  retn
```
