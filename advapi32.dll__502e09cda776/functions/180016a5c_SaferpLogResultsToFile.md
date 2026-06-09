# SaferpLogResultsToFile

- ea: `0x180016a5c`
- end: `0x180016e20`
- name: `SaferpLogResultsToFile`
- size: `964`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800160c0`

## callees

- `0x180016a5c`
- `0x1800720b0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180016db3`
- `msvcrt!swprintf_s` at `0x180016db3`
- `ntdll!NtOpenKey` at `0x180016ad3`
- `ntdll!NtOpenKey` at `0x180016ad3`
- `ntdll!NtQueryValueKey` at `0x180016b0a`
- `ntdll!NtQueryValueKey` at `0x180016b0a`
- `ntdll!NtClose` at `0x180016b1c`
- `ntdll!NtClose` at `0x180016b1c`
- `ntdll!NtQueryInformationProcess` at `0x180016bf8`
- `ntdll!NtQueryInformationProcess` at `0x180016c78`
- `ntdll!NtQueryInformationProcess` at `0x180016bf8`
- `ntdll!NtQueryInformationProcess` at `0x180016c78`
- `ntdll!RtlFreeHeap` at `0x180016e00`
- `ntdll!RtlFreeHeap` at `0x180016e00`
- `ntdll!RtlAllocateHeap` at `0x180016caa`
- `ntdll!RtlAllocateHeap` at `0x180016caa`
- `KERNEL32!CloseHandle` at `0x180016e0f`
- `KERNEL32!CloseHandle` at `0x180016e0f`
- `KERNEL32!WriteFile` at `0x180016bbb`
- `KERNEL32!WriteFile` at `0x180016de2`
- `KERNEL32!WriteFile` at `0x180016bbb`
- `KERNEL32!WriteFile` at `0x180016de2`
- `KERNEL32!SetFilePointer` at `0x180016b9c`
- `KERNEL32!SetFilePointer` at `0x180016bd2`
- `KERNEL32!SetFilePointer` at `0x180016b9c`
- `KERNEL32!SetFilePointer` at `0x180016bd2`
- `KERNEL32!CreateFileW` at `0x180016b75`
- `KERNEL32!CreateFileW` at `0x180016b75`

## pseudocode

```c
int __fastcall SaferpLogResultsToFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // edi
  HANDLE FileW; // rax
  NTSTATUS ValueKey; // ebx
  __int64 v8; // r15
  HANDLE v9; // r14
  __int64 v10; // rax
  _BYTE *v11; // r13
  int v12; // eax
  __int64 v13; // rsi
  __int64 v14; // rbx
  PVOID ProcessHeap; // rcx
  wchar_t *Heap; // r12
  __int64 Buffer; // [rsp+C0h] [rbp-80h] BYREF
  __int64 NumberOfBytesWritten; // [rsp+C8h] [rbp-78h] BYREF
  __int64 v20; // [rsp+D0h] [rbp-70h] BYREF
  HANDLE KeyHandle; // [rsp+D8h] [rbp-68h] BYREF
  size_t BufferCount; // [rsp+E0h] [rbp-60h]
  __int64 v23; // [rsp+E8h] [rbp-58h]
  __int64 v24; // [rsp+F0h] [rbp-50h]
  __int64 v25; // [rsp+F8h] [rbp-48h]
  __int64 v26; // [rsp+100h] [rbp-40h]
  HANDLE hFile; // [rsp+108h] [rbp-38h]
  _OWORD ProcessInformation[2]; // [rsp+110h] [rbp-30h] BYREF
  __int128 v29; // [rsp+130h] [rbp-10h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+140h] [rbp+0h] BYREF
  int v31; // [rsp+144h] [rbp+4h]
  WCHAR FileName[266]; // [rsp+14Ch] [rbp+Ch] BYREF

  v25 = a3;
  v23 = a2;
  v26 = a1;
  v24 = a4;
  v5 = 1;
  KeyHandle = 0;
  HIDWORD(Buffer) = 0;
  LODWORD(v20) = 0;
  NumberOfBytesWritten = 0;
  LOWORD(Buffer) = -257;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  v29 = 0;
  LODWORD(FileW) = NtOpenKey(&KeyHandle, 1u, (POBJECT_ATTRIBUTES)&stru_180075100);
  if ( (int)FileW >= 0 )
  {
    ValueKey = NtQueryValueKey(
                 KeyHandle,
                 (PUNICODE_STRING)&stru_180075130,
                 KeyValuePartialInformation,
                 KeyValueInformation,
                 0x218u,
                 (PULONG)&NumberOfBytesWritten + 1);
    LODWORD(FileW) = NtClose(KeyHandle);
    if ( ValueKey >= 0 && v31 == 1 )
    {
      FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 4u, 0, 0);
      v8 = -1;
      hFile = FileW;
      v9 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        SetFilePointer(FileW, 0, 0, 0);
        WriteFile(v9, &Buffer, 2u, (LPDWORD)&NumberOfBytesWritten, 0);
        SetFilePointer(v9, 0, 0, 2u);
        if ( NtQueryInformationProcess(
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               ProcessImageFileName,
               KeyValueInformation,
               0x218u,
               (PULONG)&Buffer + 1) >= 0 )
        {
          v10 = HIDWORD(Buffer);
          HIDWORD(Buffer) = 1;
          v11 = &KeyValueInformation[v10 - 2];
          if ( &KeyValueInformation[v10 - 2] > KeyValueInformation )
          {
            v12 = 1;
            do
            {
              v5 = v12;
              if ( *((_WORD *)v11 - 1) == 92 )
                break;
              v5 = v12 + 1;
              v11 -= 2;
              HIDWORD(Buffer) = ++v12;
            }
            while ( v11 > KeyValueInformation );
          }
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)(a1 + 2 * v13) );
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)(v23 + 2 * v14) );
          if ( NtQueryInformationProcess(
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 ProcessBasicInformation,
                 ProcessInformation,
                 0x30u,
                 (PULONG)&v20) >= 0 )
          {
            ProcessHeap = NtCurrentPeb()->ProcessHeap;
            BufferCount = (unsigned int)(v5 + 2 * (v14 + v13 + 121));
            Heap = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, BufferCount);
            if ( Heap )
            {
              BufferCount >>= 1;
              swprintf_s(
                Heap,
                BufferCount,
                L"%s%s%Id%s%s%s%s%s%s%s{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\r\n",
                v11,
                L" (PID = ",
                (_QWORD)v29,
                L") identified ",
                v26,
                L" as ",
                v23,
                L" using ",
                v25,
                L" rule, Guid = ",
                *(_DWORD *)v24,
                *(unsigned __int16 *)(v24 + 4),
                *(unsigned __int16 *)(v24 + 6),
                *(unsigned __int8 *)(v24 + 8),
                *(unsigned __int8 *)(v24 + 9),
                *(unsigned __int8 *)(v24 + 10),
                *(unsigned __int8 *)(v24 + 11),
                *(unsigned __int8 *)(v24 + 12),
                *(unsigned __int8 *)(v24 + 13),
                *(unsigned __int8 *)(v24 + 14),
                *(unsigned __int8 *)(v24 + 15),
                Buffer,
                NumberOfBytesWritten,
                v20);
              do
                ++v8;
              while ( Heap[v8] );
              v9 = hFile;
              WriteFile(hFile, Heap, 2 * v8, (LPDWORD)&NumberOfBytesWritten, 0);
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            }
          }
        }
        LODWORD(FileW) = CloseHandle(v9);
      }
    }
  }
  return (int)FileW;
}

```

## disassembly

```asm
0x180016a5c  push    rbp
0x180016a5e  push    rbx
0x180016a5f  push    rsi
0x180016a60  push    rdi
0x180016a61  push    r12
0x180016a63  push    r13
0x180016a65  push    r14
0x180016a67  push    r15
0x180016a69  lea     rbp, [rsp-238h]
0x180016a71  sub     rsp, 378h
0x180016a78  mov     rax, cs:__security_cookie
0x180016a7f  xor     rax, rsp
0x180016a82  mov     [rbp+270h+var_50], rax
0x180016a89  xor     esi, esi
0x180016a8b  mov     [rbp+270h+var_2B8], r8
0x180016a8f  xorps   xmm0, xmm0
0x180016a92  mov     [rbp+270h+var_2C8], rdx
0x180016a96  mov     r12, rcx
0x180016a99  mov     [rbp+270h+var_2B0], rcx
0x180016a9d  lea     r8, stru_180075100; ObjectAttributes
0x180016aa4  mov     [rbp+270h+var_2C0], r9
0x180016aa8  lea     edi, [rsi+1]
0x180016aab  mov     [rbp+270h+KeyHandle], rsi
0x180016aaf  mov     edx, edi; DesiredAccess
0x180016ab1  mov     [rbp+270h+ReturnLength], esi
0x180016ab4  lea     rcx, [rbp+270h+KeyHandle]; KeyHandle
0x180016ab8  mov     dword ptr [rbp+270h+var_2E0], esi
0x180016abb  mov     [rbp+270h+NumberOfBytesWritten], esi
0x180016abe  mov     [rbp+270h+Buffer], 0FEFFh
0x180016ac4  movups  [rbp+270h+ProcessInformation], xmm0
0x180016ac8  mov     [rbp+270h+var_2E4], esi
0x180016acb  movups  [rbp+270h+var_290], xmm0
0x180016acf  movups  [rbp+270h+var_280], xmm0
0x180016ad3  call    cs:__imp_NtOpenKey
0x180016ada  nop     dword ptr [rax+rax+00h]
0x180016adf  test    eax, eax
0x180016ae1  js      short loc_180016B2C
0x180016ae3  mov     rcx, [rbp+270h+KeyHandle]; KeyHandle
0x180016ae7  lea     rax, [rbp+270h+var_2E4]
0x180016aeb  mov     [rsp+3B0h+ResultLength], rax; ResultLength
0x180016af0  lea     r13d, [rsi+2]
0x180016af4  mov     r8d, r13d; KeyValueInformationClass
0x180016af7  mov     [rsp+3B0h+Length], 218h; Length
0x180016aff  lea     r9, [rbp+270h+KeyValueInformation]; KeyValueInformation
0x180016b03  lea     rdx, stru_180075130; ValueName
0x180016b0a  call    cs:__imp_NtQueryValueKey
0x180016b11  nop     dword ptr [rax+rax+00h]
0x180016b16  mov     rcx, [rbp+270h+KeyHandle]; Handle
0x180016b1a  mov     ebx, eax
0x180016b1c  call    cs:__imp_NtClose
0x180016b23  nop     dword ptr [rax+rax+00h]
0x180016b28  test    ebx, ebx
0x180016b2a  jns     short loc_180016B50
0x180016b2c  mov     rcx, [rbp+270h+var_50]
0x180016b33  xor     rcx, rsp; StackCookie
0x180016b36  call    __security_check_cookie
0x180016b3b  add     rsp, 378h
0x180016b42  pop     r15
0x180016b44  pop     r14
0x180016b46  pop     r13
0x180016b48  pop     r12
0x180016b4a  pop     rdi
0x180016b4b  pop     rsi
0x180016b4c  pop     rbx
0x180016b4d  pop     rbp
0x180016b4e  retn
0x180016b50  cmp     [rbp+270h+var_26C], edi
0x180016b53  jnz     short loc_180016B2C
0x180016b55  mov     [rsp+3B0h+hTemplateFile], rsi; hTemplateFile
0x180016b5a  lea     rcx, [rbp+270h+FileName]; lpFileName
0x180016b5e  mov     dword ptr [rsp+3B0h+ResultLength], esi; dwFlagsAndAttributes
0x180016b62  xor     r9d, r9d; lpSecurityAttributes
0x180016b65  xor     r8d, r8d; dwShareMode
0x180016b68  mov     [rsp+3B0h+Length], 4; dwCreationDisposition
0x180016b70  mov     edx, 40000000h; dwDesiredAccess
0x180016b75  call    cs:__imp_CreateFileW
0x180016b7c  nop     dword ptr [rax+rax+00h]
0x180016b81  or      r15, 0FFFFFFFFFFFFFFFFh
0x180016b85  mov     [rbp+270h+hFile], rax
0x180016b89  mov     r14, rax
0x180016b8c  cmp     rax, r15
0x180016b8f  jz      short loc_180016B2C
0x180016b91  xor     r9d, r9d; dwMoveMethod
0x180016b94  xor     r8d, r8d; lpDistanceToMoveHigh
0x180016b97  xor     edx, edx; lDistanceToMove
0x180016b99  mov     rcx, rax; hFile
0x180016b9c  call    cs:__imp_SetFilePointer
0x180016ba3  nop     dword ptr [rax+rax+00h]
0x180016ba8  lea     r9, [rbp+270h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016bac  mov     qword ptr [rsp+3B0h+Length], rsi; lpOverlapped
0x180016bb1  mov     r8d, r13d; nNumberOfBytesToWrite
0x180016bb4  lea     rdx, [rbp+270h+Buffer]; lpBuffer
0x180016bb8  mov     rcx, r14; hFile
0x180016bbb  call    cs:__imp_WriteFile
0x180016bc2  nop     dword ptr [rax+rax+00h]
0x180016bc7  mov     r9d, r13d; dwMoveMethod
0x180016bca  xor     r8d, r8d; lpDistanceToMoveHigh
0x180016bcd  xor     edx, edx; lDistanceToMove
0x180016bcf  mov     rcx, r14; hFile
0x180016bd2  call    cs:__imp_SetFilePointer
0x180016bd9  nop     dword ptr [rax+rax+00h]
0x180016bde  lea     rax, [rbp+270h+ReturnLength]
0x180016be2  mov     r9d, 218h; ProcessInformationLength
0x180016be8  lea     r8, [rbp+270h+KeyValueInformation]; ProcessInformation
0x180016bec  mov     qword ptr [rsp+3B0h+Length], rax; ReturnLength
0x180016bf1  lea     edx, [r15+1Ch]; ProcessInformationClass
0x180016bf5  mov     rcx, r15; ProcessHandle
0x180016bf8  call    cs:__imp_NtQueryInformationProcess
0x180016bff  nop     dword ptr [rax+rax+00h]
0x180016c04  test    eax, eax
0x180016c06  js      loc_180016E0C
0x180016c0c  mov     eax, [rbp+270h+ReturnLength]
0x180016c0f  mov     [rbp+270h+ReturnLength], edi
0x180016c12  lea     r13, [rbp+rax+270h+var_280+0Eh]
0x180016c17  lea     rax, [rbp+270h+KeyValueInformation]
0x180016c1b  cmp     r13, rax
0x180016c1e  jbe     short loc_180016C41
0x180016c20  mov     eax, edi
0x180016c22  cmp     word ptr [r13-2], 5Ch ; '\'
0x180016c28  mov     edi, eax
0x180016c2a  jz      short loc_180016C41
0x180016c2c  lea     edi, [rax+1]
0x180016c2f  add     r13, 0FFFFFFFFFFFFFFFEh
0x180016c33  lea     rcx, [rbp+270h+KeyValueInformation]
0x180016c37  mov     [rbp+270h+ReturnLength], edi
0x180016c3a  mov     eax, edi
0x180016c3c  cmp     r13, rcx
0x180016c3f  ja      short loc_180016C22
0x180016c41  mov     rsi, r15
0x180016c44  xor     ecx, ecx
0x180016c46  inc     rsi
0x180016c49  cmp     [r12+rsi*2], cx
0x180016c4e  jnz     short loc_180016C46
0x180016c50  mov     rax, [rbp+270h+var_2C8]
0x180016c54  mov     rbx, r15
0x180016c57  inc     rbx
0x180016c5a  cmp     [rax+rbx*2], cx
0x180016c5e  jnz     short loc_180016C57
0x180016c60  lea     rax, [rbp+270h+var_2E0]
0x180016c64  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180016c6a  lea     r8, [rbp+270h+ProcessInformation]; ProcessInformation
0x180016c6e  mov     qword ptr [rsp+3B0h+Length], rax; ReturnLength
0x180016c73  xor     edx, edx; ProcessInformationClass
0x180016c75  mov     rcx, r15; ProcessHandle
0x180016c78  call    cs:__imp_NtQueryInformationProcess
0x180016c7f  nop     dword ptr [rax+rax+00h]
0x180016c84  test    eax, eax
0x180016c86  js      loc_180016E0C
0x180016c8c  mov     rcx, gs:60h
0x180016c95  lea     eax, [rsi+79h]
0x180016c98  add     eax, ebx
0x180016c9a  xor     edx, edx; Flags
0x180016c9c  mov     rcx, [rcx+30h]; HeapHandle
0x180016ca0  lea     eax, [rdi+rax*2]
0x180016ca3  mov     r8d, eax; Size
0x180016ca6  mov     [rbp+270h+BufferCount], rax
0x180016caa  call    cs:__imp_RtlAllocateHeap
0x180016cb1  nop     dword ptr [rax+rax+00h]
0x180016cb6  mov     r12, rax
0x180016cb9  test    rax, rax
0x180016cbc  jz      loc_180016E0C
0x180016cc2  mov     rax, [rbp+270h+var_2C0]
0x180016cc6  shr     [rbp+270h+BufferCount], 1
0x180016cca  movzx   ecx, byte ptr [rax+0Fh]
0x180016cce  movzx   edx, byte ptr [rax+0Eh]
0x180016cd2  movzx   r8d, byte ptr [rax+0Dh]
0x180016cd7  movzx   r9d, byte ptr [rax+0Ch]
0x180016cdc  movzx   r10d, byte ptr [rax+0Bh]
0x180016ce1  movzx   r11d, byte ptr [rax+0Ah]
0x180016ce6  movzx   ebx, byte ptr [rax+9]
0x180016cea  movzx   edi, byte ptr [rax+8]
0x180016cee  movzx   esi, word ptr [rax+6]
0x180016cf2  movzx   r14d, word ptr [rax+4]
0x180016cf7  mov     eax, [rax]
0x180016cf9  mov     [rsp+3B0h+var_2F8], ecx
0x180016d00  mov     rcx, r12; Buffer
0x180016d03  mov     [rsp+3B0h+var_300], edx
0x180016d0a  mov     rdx, [rbp+270h+BufferCount]; BufferCount
0x180016d0e  mov     [rsp+3B0h+var_308], r8d
0x180016d16  lea     r8, aSSIdSSSSSSS08l; "%s%s%Id%s%s%s%s%s%s%s{%08lx-%04x-%04x-%"...
0x180016d1d  mov     [rsp+3B0h+var_310], r9d
0x180016d25  mov     r9, r13
0x180016d28  mov     [rsp+3B0h+var_318], r10d
0x180016d30  mov     [rsp+3B0h+var_320], r11d
0x180016d38  mov     [rsp+3B0h+var_328], ebx
0x180016d3f  mov     [rsp+3B0h+var_330], edi
0x180016d46  mov     [rsp+3B0h+var_338], esi
0x180016d4a  mov     [rsp+3B0h+var_340], r14d
0x180016d4f  mov     [rsp+3B0h+var_348], eax
0x180016d53  lea     rax, aRuleGuid; " rule, Guid = "
0x180016d5a  mov     [rsp+3B0h+var_350], rax
0x180016d5f  mov     rax, [rbp+270h+var_2B8]
0x180016d63  mov     [rsp+3B0h+var_358], rax
0x180016d68  lea     rax, aUsing; " using "
0x180016d6f  mov     [rsp+3B0h+var_360], rax
0x180016d74  mov     rax, [rbp+270h+var_2C8]
0x180016d78  mov     [rsp+3B0h+var_368], rax
0x180016d7d  lea     rax, aAs; " as "
0x180016d84  mov     [rsp+3B0h+var_370], rax
0x180016d89  mov     rax, [rbp+270h+var_2B0]
0x180016d8d  mov     [rsp+3B0h+var_378], rax
0x180016d92  lea     rax, aIdentified; ") identified "
0x180016d99  mov     [rsp+3B0h+hTemplateFile], rax
0x180016d9e  mov     rax, qword ptr [rbp+270h+var_280]
0x180016da2  mov     [rsp+3B0h+ResultLength], rax
0x180016da7  lea     rax, aPid; " (PID = "
0x180016dae  mov     qword ptr [rsp+3B0h+Length], rax
0x180016db3  call    cs:__imp_swprintf_s
0x180016dba  nop     dword ptr [rax+rax+00h]
0x180016dbf  xor     eax, eax
0x180016dc1  inc     r15
0x180016dc4  cmp     [r12+r15*2], ax
0x180016dc9  jnz     short loc_180016DC1
0x180016dcb  mov     r14, [rbp+270h+hFile]
0x180016dcf  lea     r8d, [r15+r15]; nNumberOfBytesToWrite
0x180016dd3  mov     rcx, r14; hFile
0x180016dd6  mov     qword ptr [rsp+3B0h+Length], rax; lpOverlapped
0x180016ddb  lea     r9, [rbp+270h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016ddf  mov     rdx, r12; lpBuffer
0x180016de2  call    cs:__imp_WriteFile
0x180016de9  nop     dword ptr [rax+rax+00h]
0x180016dee  mov     rcx, gs:60h
0x180016df7  mov     r8, r12; P
0x180016dfa  xor     edx, edx; Flags
0x180016dfc  mov     rcx, [rcx+30h]; HeapHandle
0x180016e00  call    cs:__imp_RtlFreeHeap
0x180016e07  nop     dword ptr [rax+rax+00h]
0x180016e0c  mov     rcx, r14; hObject
0x180016e0f  call    cs:__imp_CloseHandle
0x180016e16  nop     dword ptr [rax+rax+00h]
0x180016e1b  jmp     loc_180016B2C
```
