# winreGetDiskSignature(PartitionNode *)

- ea: `0x18000eb1c`
- end: `0x18000ed6d`
- name: `?winreGetDiskSignature@@YAKPEAUPartitionNode@@@Z`
- size: `593`
- prototype: `unsigned int __fastcall(struct PartitionNode *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x18000d67c`

## callees

- `0x1800059fc`
- `0x18000c6f0`
- `0x18000eb1c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ec75`
- `KERNEL32!GetLastError` at `0x18000ec75`
- `KERNEL32!HeapFree` at `0x18000ec1c`
- `KERNEL32!HeapFree` at `0x18000ed21`
- `KERNEL32!HeapFree` at `0x18000ec1c`
- `KERNEL32!HeapFree` at `0x18000ed21`
- `KERNEL32!HeapAlloc` at `0x18000ec33`
- `KERNEL32!HeapAlloc` at `0x18000ec33`
- `KERNEL32!GetProcessHeap` at `0x18000ec0e`
- `KERNEL32!GetProcessHeap` at `0x18000ec22`
- `KERNEL32!GetProcessHeap` at `0x18000ed13`
- `KERNEL32!GetProcessHeap` at `0x18000ec0e`
- `KERNEL32!GetProcessHeap` at `0x18000ec22`
- `KERNEL32!GetProcessHeap` at `0x18000ed13`
- `KERNEL32!CreateFileW` at `0x18000ebe2`
- `KERNEL32!CreateFileW` at `0x18000ebe2`
- `KERNEL32!CloseHandle` at `0x18000ed08`
- `KERNEL32!CloseHandle` at `0x18000ed08`
- `KERNEL32!DeviceIoControl` at `0x18000ec6b`
- `KERNEL32!DeviceIoControl` at `0x18000ec6b`

## string_xrefs

- `0x18000eb87`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000eca7`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`

## pseudocode

```c
__int64 __fastcall winreGetDiskSignature(struct PartitionNode *a1)
{
  __int64 v2; // r9
  DWORD LastError; // ebx
  HANDLE FileW; // r14
  _DWORD *v5; // rdi
  DWORD v6; // ebp
  unsigned int i; // r15d
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-2A8h] BYREF
  WCHAR FileName[304]; // [rsp+50h] [rbp-298h] BYREF

  memset_0(FileName, 0, 0x25Cu);
  v2 = *((unsigned int *)a1 + 324);
  BytesReturned[0] = 0;
  LastError = StringCchPrintfW(FileName, 0x12Eu, L"\\\\.\\PhysicalDrive%lu", v2);
  if ( (LastError & 0x80000000) == 0 )
  {
    LastError = 0;
    FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
      return LastError;
    v5 = 0;
    v6 = 192;
    for ( i = 0; i < 0xA; ++i )
    {
      if ( v5 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v5);
      }
      v9 = GetProcessHeap();
      v5 = HeapAlloc(v9, 8u, v6);
      if ( !v5 )
      {
        LastError = 8;
        UnattendLogW(2, L"winreGetDiskSignature %s (0x%x) in file %S line %d", L"failed to allocate memory");
        goto LABEL_22;
      }
      if ( DeviceIoControl(FileW, 0x70050u, 0, 0, v5, v6, BytesReturned, 0) )
      {
        LastError = 0;
        goto LABEL_15;
      }
      LastError = GetLastError();
      if ( LastError != 122 )
        break;
      v6 += 2304;
      LastError = 2;
    }
    if ( LastError )
      goto LABEL_22;
LABEL_15:
    if ( *v5 != 2 )
    {
      if ( *((_DWORD *)a1 + 327) )
      {
        if ( !*v5 )
        {
          *((_DWORD *)a1 + 8) = v5[2];
          goto LABEL_22;
        }
      }
      else if ( *v5 == 1 )
      {
        *(_OWORD *)((char *)a1 + 36) = *(_OWORD *)(v5 + 2);
        goto LABEL_22;
      }
    }
    LastError = 3;
LABEL_22:
    if ( FileW )
      CloseHandle(FileW);
    if ( v5 )
    {
      v10 = GetProcessHeap();
      HeapFree(v10, 0, v5);
    }
    goto LABEL_26;
  }
  UnattendLogW(
    2,
    L"winreGetDiskSignature %s (0x%x) in file %S line %d",
    L"failed to get drive name",
    LastError,
    "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
    1790);
  LastError = (unsigned __int16)LastError;
LABEL_26:
  if ( LastError )
    UnattendLogW(1, L"winreGetDiskSignature failed: 0x%x", LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000eb1c  mov     [rsp+arg_8], rbx
0x18000eb21  mov     [rsp+arg_10], rbp
0x18000eb26  push    rsi
0x18000eb27  push    rdi
0x18000eb28  push    r13
0x18000eb2a  push    r14
0x18000eb2c  push    r15
0x18000eb2e  sub     rsp, 2C0h
0x18000eb35  mov     rax, cs:__security_cookie
0x18000eb3c  xor     rax, rsp
0x18000eb3f  mov     [rsp+2E8h+var_38], rax
0x18000eb47  mov     rsi, rcx
0x18000eb4a  xor     edx, edx; Val
0x18000eb4c  lea     rcx, [rsp+2E8h+FileName]; void *
0x18000eb51  mov     r8d, 25Ch; Size
0x18000eb57  call    memset_0
0x18000eb5c  mov     r9d, [rsi+510h]
0x18000eb63  lea     r8, aPhysicaldriveL; "\\\\.\\PhysicalDrive%lu"
0x18000eb6a  mov     edx, 12Eh; unsigned __int64
0x18000eb6f  mov     [rsp+2E8h+BytesReturned], 0
0x18000eb77  lea     rcx, [rsp+2E8h+FileName]; unsigned __int16 *
0x18000eb7c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000eb81  mov     ebx, eax
0x18000eb83  test    eax, eax
0x18000eb85  jns     short loc_18000EBBE
0x18000eb87  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000eb8e  mov     [rsp+2E8h+dwFlagsAndAttributes], 6FEh
0x18000eb96  mov     r9d, ebx
0x18000eb99  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax
0x18000eb9e  lea     r8, aFailedToGetDri; "failed to get drive name"
0x18000eba5  mov     ecx, 2
0x18000ebaa  lea     rdx, aWinregetdisksi_0; "winreGetDiskSignature %s (0x%x) in file"...
0x18000ebb1  call    UnattendLogW
0x18000ebb6  movzx   ebx, bx
0x18000ebb9  jmp     loc_18000ED27
0x18000ebbe  xor     ebx, ebx
0x18000ebc0  lea     rcx, [rsp+2E8h+FileName]; lpFileName
0x18000ebc5  mov     [rsp+2E8h+hTemplateFile], rbx; hTemplateFile
0x18000ebca  xor     r9d, r9d; lpSecurityAttributes
0x18000ebcd  mov     [rsp+2E8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18000ebd1  mov     edx, 80000000h; dwDesiredAccess
0x18000ebd6  lea     r13d, [rbx+3]
0x18000ebda  mov     r8d, r13d; dwShareMode
0x18000ebdd  mov     [rsp+2E8h+dwCreationDisposition], r13d; dwCreationDisposition
0x18000ebe2  call    cs:__imp_CreateFileW
0x18000ebe8  mov     r14, rax
0x18000ebeb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ebef  jz      loc_18000ED3F
0x18000ebf5  xor     edi, edi
0x18000ebf7  mov     ebp, 0C0h
0x18000ebfc  xor     r15d, r15d
0x18000ebff  cmp     r15d, 0Ah
0x18000ec03  jnb     loc_18000ECCE
0x18000ec09  test    rdi, rdi
0x18000ec0c  jz      short loc_18000EC22
0x18000ec0e  call    cs:__imp_GetProcessHeap
0x18000ec14  mov     r8, rdi; lpMem
0x18000ec17  xor     edx, edx; dwFlags
0x18000ec19  mov     rcx, rax; hHeap
0x18000ec1c  call    cs:__imp_HeapFree
0x18000ec22  call    cs:__imp_GetProcessHeap
0x18000ec28  mov     r8d, ebp; dwBytes
0x18000ec2b  mov     edx, 8; dwFlags
0x18000ec30  mov     rcx, rax; hHeap
0x18000ec33  call    cs:__imp_HeapAlloc
0x18000ec39  mov     rdi, rax
0x18000ec3c  test    rax, rax
0x18000ec3f  jz      short loc_18000EC97
0x18000ec41  mov     [rsp+2E8h+lpOverlapped], 0; lpOverlapped
0x18000ec4a  lea     rax, [rsp+2E8h+BytesReturned]
0x18000ec4f  mov     [rsp+2E8h+hTemplateFile], rax; lpBytesReturned
0x18000ec54  xor     r9d, r9d; nInBufferSize
0x18000ec57  mov     [rsp+2E8h+dwFlagsAndAttributes], ebp; nOutBufferSize
0x18000ec5b  xor     r8d, r8d; lpInBuffer
0x18000ec5e  mov     edx, 70050h; dwIoControlCode
0x18000ec63  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rdi; lpOutBuffer
0x18000ec68  mov     rcx, r14; hDevice
0x18000ec6b  call    cs:__imp_DeviceIoControl
0x18000ec71  test    eax, eax
0x18000ec73  jnz     short loc_18000EC93
0x18000ec75  call    cs:__imp_GetLastError
0x18000ec7b  mov     ebx, eax
0x18000ec7d  cmp     eax, 7Ah ; 'z'
0x18000ec80  jnz     short loc_18000ECCE
0x18000ec82  add     ebp, 900h
0x18000ec88  lea     ebx, [rax-78h]
0x18000ec8b  inc     r15d
0x18000ec8e  jmp     loc_18000EBFF
0x18000ec93  xor     ebx, ebx
0x18000ec95  jmp     short loc_18000ECD2
0x18000ec97  mov     ecx, 8
0x18000ec9c  mov     [rsp+2E8h+dwFlagsAndAttributes], 717h
0x18000eca4  mov     r9d, ecx
0x18000eca7  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000ecae  mov     ebx, ecx
0x18000ecb0  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax
0x18000ecb5  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x18000ecbc  lea     rdx, aWinregetdisksi_0; "winreGetDiskSignature %s (0x%x) in file"...
0x18000ecc3  lea     ecx, [r9-6]
0x18000ecc7  call    UnattendLogW
0x18000eccc  jmp     short loc_18000ED00
0x18000ecce  test    ebx, ebx
0x18000ecd0  jnz     short loc_18000ED00
0x18000ecd2  cmp     dword ptr [rdi], 2
0x18000ecd5  jnz     short loc_18000ECDC
0x18000ecd7  mov     ebx, r13d
0x18000ecda  jmp     short loc_18000ED00
0x18000ecdc  cmp     dword ptr [rsi+51Ch], 0
0x18000ece3  jz      short loc_18000ECF2
0x18000ece5  cmp     dword ptr [rdi], 0
0x18000ece8  jnz     short loc_18000ECD7
0x18000ecea  mov     eax, [rdi+8]
0x18000eced  mov     [rsi+20h], eax
0x18000ecf0  jmp     short loc_18000ED00
0x18000ecf2  cmp     dword ptr [rdi], 1
0x18000ecf5  jnz     short loc_18000ECD7
0x18000ecf7  movups  xmm0, xmmword ptr [rdi+8]
0x18000ecfb  movdqu  xmmword ptr [rsi+24h], xmm0
0x18000ed00  test    r14, r14
0x18000ed03  jz      short loc_18000ED0E
0x18000ed05  mov     rcx, r14; hObject
0x18000ed08  call    cs:__imp_CloseHandle
0x18000ed0e  test    rdi, rdi
0x18000ed11  jz      short loc_18000ED27
0x18000ed13  call    cs:__imp_GetProcessHeap
0x18000ed19  mov     r8, rdi; lpMem
0x18000ed1c  xor     edx, edx; dwFlags
0x18000ed1e  mov     rcx, rax; hHeap
0x18000ed21  call    cs:__imp_HeapFree
0x18000ed27  test    ebx, ebx
0x18000ed29  jz      short loc_18000ED3F
0x18000ed2b  mov     r8d, ebx
0x18000ed2e  lea     rdx, aWinregetdisksi; "winreGetDiskSignature failed: 0x%x"
0x18000ed35  mov     ecx, 1
0x18000ed3a  call    UnattendLogW
0x18000ed3f  mov     eax, ebx
0x18000ed41  mov     rcx, [rsp+2E8h+var_38]
0x18000ed49  xor     rcx, rsp; StackCookie
0x18000ed4c  call    __security_check_cookie
0x18000ed51  lea     r11, [rsp+2E8h+var_28]
0x18000ed59  mov     rbx, [r11+38h]
0x18000ed5d  mov     rbp, [r11+40h]
0x18000ed61  mov     rsp, r11
0x18000ed64  pop     r15
0x18000ed66  pop     r14
0x18000ed68  pop     r13
0x18000ed6a  pop     rdi
0x18000ed6b  pop     rsi
0x18000ed6c  retn
```
