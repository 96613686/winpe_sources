# CDlpHelpersT<CEmptyType>::CreateFolderWithAcl(ushort *)

- ea: `0x140009aa8`
- end: `0x140009c4c`
- name: `?CreateFolderWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAG@Z`
- size: `420`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140013894`

## callees

- `0x140003ad0`
- `0x1400076c8`
- `0x140009aa8`
- `0x14000c20c`
- `0x1400135b8`
- `0x140026104`
- `0x140027a70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140009c31`
- `KERNEL32!HeapFree` at `0x140009c31`
- `KERNEL32!GetProcessHeap` at `0x140009c1d`
- `KERNEL32!GetProcessHeap` at `0x140009c1d`
- `KERNEL32!CreateDirectoryW` at `0x140009bcb`
- `KERNEL32!CreateDirectoryW` at `0x140009bcb`
- `KERNEL32!GetLastError` at `0x140009b11`
- `KERNEL32!GetLastError` at `0x140009bdb`
- `KERNEL32!GetLastError` at `0x140009b11`
- `KERNEL32!GetLastError` at `0x140009bdb`
- `KERNEL32!GetFileAttributesW` at `0x140009b7e`
- `KERNEL32!GetFileAttributesW` at `0x140009b7e`

## pseudocode

```c
__int64 __fastcall CDlpHelpersT<CEmptyType>::CreateFolderWithAcl(LPCWSTR lpFileName)
{
  void *v2; // rsi
  unsigned int v3; // ebx
  signed int v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  DWORD FileAttributesW; // edi
  int v8; // edi
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  _DWORD v12[4]; // [rsp+28h] [rbp-28h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+38h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+80h] [rbp+30h] BYREF
  __int64 v15; // [rsp+88h] [rbp+38h] BYREF
  __int64 v16; // [rsp+90h] [rbp+40h]

  v16 = -1;
  v2 = 0;
  lpMem = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v15 = 0;
  v12[0] = 17;
  v12[1] = 18;
  v12[2] = 8;
  if ( !lpFileName )
  {
    v3 = -2147024809;
    goto LABEL_21;
  }
  if ( (unsigned int)CreateWorkingDirectorySecurityDescriptor(&lpMem) )
  {
    SecurityAttributes.nLength = 24;
    v2 = lpMem;
    SecurityAttributes.lpSecurityDescriptor = lpMem;
    SecurityAttributes.bInheritHandle = 0;
    v5 = CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(&v15, v12, 3);
    v3 = v5;
    if ( v5 < 0 )
    {
      v6 = (unsigned int)v5;
LABEL_22:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
      goto LABEL_23;
    }
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1 )
      v8 = 0;
    else
      v8 = (FileAttributesW >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v3 = 0;
    if ( (!v8 || (unsigned int)DeletePathEx(lpFileName)) && CreateDirectoryW(lpFileName, &SecurityAttributes) )
      goto LABEL_23;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
LABEL_21:
    v6 = v3;
    goto LABEL_22;
  }
  v4 = GetLastError();
  v3 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v3 = -2147467259;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
  v2 = lpMem;
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  CAutoRevertApplyPrivilegesT<CEmptyType>::~CAutoRevertApplyPrivilegesT<CEmptyType>(&v15);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  return v3;
}

```

## disassembly

```asm
0x140009aa8  push    rbp
0x140009aaa  push    rbx
0x140009aab  push    rsi
0x140009aac  push    rdi
0x140009aad  push    r14
0x140009aaf  mov     rbp, rsp
0x140009ab2  sub     rsp, 50h
0x140009ab6  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x140009abe  mov     r14, rcx
0x140009ac1  mov     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x140009ac9  xor     esi, esi
0x140009acb  mov     [rbp+lpMem], rsi
0x140009acf  xorps   xmm0, xmm0
0x140009ad2  xor     eax, eax
0x140009ad4  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x140009ad8  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x140009adc  mov     [rbp+arg_8], rax
0x140009ae0  mov     [rbp+var_28], 11h
0x140009ae7  mov     [rbp+var_24], 12h
0x140009aee  mov     [rbp+var_20], 8
0x140009af5  test    rcx, rcx
0x140009af8  jnz     short loc_140009B04
0x140009afa  mov     ebx, 80070057h
0x140009aff  jmp     loc_140009BFF
0x140009b04  lea     rcx, [rbp+lpMem]
0x140009b08  call    CreateWorkingDirectorySecurityDescriptor
0x140009b0d  test    eax, eax
0x140009b0f  jnz     short loc_140009B45
0x140009b11  call    cs:__imp_GetLastError
0x140009b18  nop     dword ptr [rax+rax+00h]
0x140009b1d  mov     ebx, eax
0x140009b1f  test    eax, eax
0x140009b21  jnz     short loc_140009B2A
0x140009b23  mov     ebx, 80004005h
0x140009b28  jmp     short loc_140009B35
0x140009b2a  jle     short loc_140009B35
0x140009b2c  movzx   ebx, ax
0x140009b2f  or      ebx, 80070000h
0x140009b35  mov     ecx, ebx
0x140009b37  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140009b3c  mov     rsi, [rbp+lpMem]
0x140009b40  jmp     loc_140009C06
0x140009b45  mov     [rbp+SecurityAttributes.nLength], 18h
0x140009b4c  mov     rsi, [rbp+lpMem]
0x140009b50  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rsi
0x140009b54  mov     [rbp+SecurityAttributes.bInheritHandle], 0
0x140009b5b  mov     r8d, 3
0x140009b61  lea     rdx, [rbp+var_28]
0x140009b65  lea     rcx, [rbp+arg_8]
0x140009b69  call    ?Enable@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAAJPEBKK@Z; CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(ulong const *,ulong)
0x140009b6e  mov     ebx, eax
0x140009b70  test    eax, eax
0x140009b72  jns     short loc_140009B7B
0x140009b74  mov     ecx, eax
0x140009b76  jmp     loc_140009C01
0x140009b7b  mov     rcx, r14; lpFileName
0x140009b7e  call    cs:__imp_GetFileAttributesW
0x140009b85  nop     dword ptr [rax+rax+00h]
0x140009b8a  mov     edi, eax
0x140009b8c  cmp     eax, 0FFFFFFFFh
0x140009b8f  jz      short loc_140009B99
0x140009b91  shr     edi, 4
0x140009b94  and     edi, 1
0x140009b97  jmp     short loc_140009B9B
0x140009b99  xor     edi, edi
0x140009b9b  xor     ecx, ecx
0x140009b9d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140009ba2  xor     ecx, ecx
0x140009ba4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140009ba9  xor     ebx, ebx
0x140009bab  test    edi, edi
0x140009bad  jz      short loc_140009BC4
0x140009baf  xor     r9d, r9d
0x140009bb2  xor     r8d, r8d
0x140009bb5  lea     edx, [rbx+12h]
0x140009bb8  mov     rcx, r14; lpFileName
0x140009bbb  call    DeletePathEx
0x140009bc0  test    eax, eax
0x140009bc2  jz      short loc_140009BDB
0x140009bc4  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x140009bc8  mov     rcx, r14; lpPathName
0x140009bcb  call    cs:__imp_CreateDirectoryW
0x140009bd2  nop     dword ptr [rax+rax+00h]
0x140009bd7  test    eax, eax
0x140009bd9  jnz     short loc_140009C06
0x140009bdb  call    cs:__imp_GetLastError
0x140009be2  nop     dword ptr [rax+rax+00h]
0x140009be7  mov     ebx, eax
0x140009be9  test    eax, eax
0x140009beb  jnz     short loc_140009BF4
0x140009bed  mov     ebx, 80004005h
0x140009bf2  jmp     short loc_140009BFF
0x140009bf4  jle     short loc_140009BFF
0x140009bf6  movzx   ebx, ax
0x140009bf9  or      ebx, 80070000h
0x140009bff  mov     ecx, ebx
0x140009c01  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140009c06  mov     ecx, ebx
0x140009c08  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140009c0d  nop
0x140009c0e  lea     rcx, [rbp+arg_8]
0x140009c12  call    ??1?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; CAutoRevertApplyPrivilegesT<CEmptyType>::~CAutoRevertApplyPrivilegesT<CEmptyType>(void)
0x140009c17  nop
0x140009c18  test    rsi, rsi
0x140009c1b  jz      short loc_140009C3E
0x140009c1d  call    cs:__imp_GetProcessHeap
0x140009c24  nop     dword ptr [rax+rax+00h]
0x140009c29  mov     rcx, rax; hHeap
0x140009c2c  mov     r8, rsi; lpMem
0x140009c2f  xor     edx, edx; dwFlags
0x140009c31  call    cs:__imp_HeapFree
0x140009c38  nop     dword ptr [rax+rax+00h]
0x140009c3d  nop
0x140009c3e  mov     eax, ebx
0x140009c40  add     rsp, 50h
0x140009c44  pop     r14
0x140009c46  pop     rdi
0x140009c47  pop     rsi
0x140009c48  pop     rbx
0x140009c49  pop     rbp
0x140009c4a  retn
```
