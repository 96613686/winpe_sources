# BfspIsHashInSecurityDatabase

- ea: `0x14000fa8c`
- end: `0x14000fc9a`
- name: `BfspIsHashInSecurityDatabase`
- size: `526`
- prototype: `__int64 __fastcall(int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fca0`

## callees

- `0x14000fa8c`
- `0x140010fe4`
- `0x1400265d6`
- `0x140026650`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x14000fbf1`
- `bcrypt!BCryptFinishHash` at `0x14000fbf1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14000fb9c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x14000fb9c`
- `bcrypt!BCryptHashData` at `0x14000fbd6`
- `bcrypt!BCryptHashData` at `0x14000fbd6`
- `bcrypt!BCryptCreateHash` at `0x14000fbbd`
- `bcrypt!BCryptCreateHash` at `0x14000fbbd`
- `bcrypt!BCryptDestroyHash` at `0x14000fc02`
- `bcrypt!BCryptDestroyHash` at `0x14000fc02`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14000fc13`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14000fc13`
- `KERNEL32!HeapFree` at `0x14000fc69`
- `KERNEL32!HeapFree` at `0x14000fc69`
- `KERNEL32!GetProcessHeap` at `0x14000fc5b`
- `KERNEL32!GetProcessHeap` at `0x14000fc5b`
- `ntdll!RtlNtStatusToDosError` at `0x14000fb59`
- `ntdll!RtlNtStatusToDosError` at `0x14000fc1b`
- `ntdll!RtlNtStatusToDosError` at `0x14000fb59`
- `ntdll!RtlNtStatusToDosError` at `0x14000fc1b`

## pseudocode

```c
__int64 __fastcall BfspIsHashInSecurityDatabase(int a1, __int64 a2, _DWORD *a3)
{
  ULONG v3; // ebx
  int v6; // ecx
  NTSTATUS v7; // eax
  const WCHAR *v8; // rcx
  unsigned int i; // edi
  ULONG v10; // r12d
  UCHAR *v11; // r13
  int v12; // ebx
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  char *dwFlags; // [rsp+30h] [rbp-29h]
  BCRYPT_HASH_HANDLE *p_phHash; // [rsp+38h] [rbp-21h]
  __int64 v18; // [rsp+40h] [rbp-19h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-11h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-9h] BYREF
  __int64 v21; // [rsp+58h] [rbp-1h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp+7h]
  char v23; // [rsp+68h] [rbp+Fh] BYREF
  UCHAR pbOutput[24]; // [rsp+70h] [rbp+17h] BYREF

  v3 = 0;
  v21 = 0;
  LODWORD(v18) = 0;
  lpMem = 0;
  LODWORD(phAlgorithm) = 0;
  *a3 = 0;
  if ( a1 )
  {
    v6 = a1 - 1;
    if ( !v6 )
    {
      v7 = SbpParseSignatureDatabase(L"dbDefault", (LPGUID)EfiGlobalVariable, (__int64)&v21, (__int64)&v18, 0, 0);
      goto LABEL_9;
    }
    if ( v6 != 1 )
    {
      v7 = -1073741811;
LABEL_10:
      v3 = RtlNtStatusToDosError(v7);
      goto LABEL_24;
    }
    p_phHash = &phHash;
    v8 = L"dbx";
    dwFlags = &v23;
  }
  else
  {
    p_phHash = 0;
    v8 = L"db";
    dwFlags = 0;
  }
  v7 = SbpParseSignatureDatabase(
         v8,
         (LPGUID)&EfiImageSecurityDatabaseVariable,
         (__int64)&v21,
         (__int64)&v18,
         (__int64)dwFlags,
         (__int64)p_phHash);
LABEL_9:
  if ( v7 < 0 )
    goto LABEL_10;
  for ( i = 0; i < (unsigned int)v18; ++i )
  {
    phHash = 0;
    phAlgorithm = 0;
    v10 = *(_DWORD *)(v21 + 16LL * i);
    v11 = *(UCHAR **)(v21 + 16LL * i + 8);
    BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 0);
    v12 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    if ( v12 >= 0 )
    {
      v12 = BCryptHashData(phHash, v11, v10, 0);
      if ( v12 >= 0 )
        v12 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
    }
    if ( phHash )
      BCryptDestroyHash(phHash);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v3 = RtlNtStatusToDosError(v12);
    if ( v3 )
      break;
    v3 = 0;
    if ( !memcmp_0(pbOutput, *(const void **)(a2 + 8), *(unsigned int *)(a2 + 4)) )
    {
      *a3 = 1;
      break;
    }
  }
LABEL_24:
  v13 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
  }
  return v3;
}

```

## disassembly

```asm
0x14000fa8c  mov     [rsp-8+arg_0], rbx
0x14000fa91  mov     [rsp-8+arg_8], rdi
0x14000fa96  push    rbp
0x14000fa97  push    r12
0x14000fa99  push    r13
0x14000fa9b  push    r14
0x14000fa9d  push    r15
0x14000fa9f  lea     rbp, [rsp-37h]
0x14000faa4  sub     rsp, 90h
0x14000faab  mov     rax, cs:__security_cookie
0x14000fab2  xor     rax, rsp
0x14000fab5  mov     [rbp+57h+var_28], rax
0x14000fab9  xor     ebx, ebx
0x14000fabb  mov     r14, r8
0x14000fabe  mov     [rbp+57h+var_58], rbx
0x14000fac2  mov     r15, rdx
0x14000fac5  mov     dword ptr [rbp+57h+var_70], ebx
0x14000fac8  mov     [rbp+57h+lpMem], rbx
0x14000facc  mov     dword ptr [rbp+57h+phAlgorithm], ebx
0x14000facf  mov     [r8], ebx
0x14000fad2  test    ecx, ecx
0x14000fad4  jz      short loc_14000FB1C
0x14000fad6  sub     ecx, 1
0x14000fad9  jz      short loc_14000FB02
0x14000fadb  cmp     ecx, 1
0x14000fade  jz      short loc_14000FAE7
0x14000fae0  mov     eax, 0C000000Dh
0x14000fae5  jmp     short loc_14000FB57
0x14000fae7  lea     rax, [rbp+57h+phHash]
0x14000faeb  mov     [rsp+0B0h+var_78], rax
0x14000faf0  lea     rcx, aDbx; "dbx"
0x14000faf7  lea     rax, [rbp+57h+var_48]
0x14000fafb  mov     qword ptr [rsp+0B0h+dwFlags], rax
0x14000fb00  jmp     short loc_14000FB2D
0x14000fb02  mov     [rsp+0B0h+var_78], rbx
0x14000fb07  lea     rdx, EfiGlobalVariable
0x14000fb0e  mov     qword ptr [rsp+0B0h+dwFlags], rbx
0x14000fb13  lea     rcx, aDbdefault; "dbDefault"
0x14000fb1a  jmp     short loc_14000FB34
0x14000fb1c  mov     [rsp+0B0h+var_78], rbx; __int64
0x14000fb21  lea     rcx, aDb; "db"
0x14000fb28  mov     qword ptr [rsp+0B0h+dwFlags], rbx; __int64
0x14000fb2d  lea     rdx, EfiImageSecurityDatabaseVariable; VendorGuid
0x14000fb34  lea     rax, [rbp+57h+var_70]
0x14000fb38  mov     qword ptr [rsp+0B0h+cbSecret], rax; __int64
0x14000fb3d  lea     r9, [rbp+57h+phAlgorithm]
0x14000fb41  lea     rax, [rbp+57h+var_58]
0x14000fb45  lea     r8, [rbp+57h+lpMem]
0x14000fb49  mov     [rsp+0B0h+pbSecret], rax; __int64
0x14000fb4e  call    SbpParseSignatureDatabase
0x14000fb53  test    eax, eax
0x14000fb55  jns     short loc_14000FB66
0x14000fb57  mov     ecx, eax; Status
0x14000fb59  call    cs:__imp_RtlNtStatusToDosError
0x14000fb5f  mov     ebx, eax
0x14000fb61  jmp     loc_14000FC52
0x14000fb66  mov     edi, ebx
0x14000fb68  cmp     dword ptr [rbp+57h+var_70], ebx
0x14000fb6b  jbe     loc_14000FC52
0x14000fb71  mov     rcx, [rbp+57h+var_58]
0x14000fb75  lea     rdx, pszAlgId; "SHA1"
0x14000fb7c  mov     eax, edi
0x14000fb7e  xor     r9d, r9d; dwFlags
0x14000fb81  add     rax, rax
0x14000fb84  mov     [rbp+57h+phHash], rbx
0x14000fb88  xor     r8d, r8d; pszImplementation
0x14000fb8b  mov     [rbp+57h+phAlgorithm], rbx
0x14000fb8f  mov     r12d, [rcx+rax*8]
0x14000fb93  mov     r13, [rcx+rax*8+8]
0x14000fb98  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x14000fb9c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000fba2  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x14000fba6  lea     rdx, [rbp+57h+phHash]; phHash
0x14000fbaa  mov     [rsp+0B0h+dwFlags], ebx; dwFlags
0x14000fbae  xor     r9d, r9d; cbHashObject
0x14000fbb1  mov     [rsp+0B0h+cbSecret], ebx; cbSecret
0x14000fbb5  xor     r8d, r8d; pbHashObject
0x14000fbb8  mov     [rsp+0B0h+pbSecret], rbx; pbSecret
0x14000fbbd  call    cs:__imp_BCryptCreateHash
0x14000fbc3  mov     ebx, eax
0x14000fbc5  test    eax, eax
0x14000fbc7  js      short loc_14000FBF9
0x14000fbc9  mov     rcx, [rbp+57h+phHash]; hHash
0x14000fbcd  xor     r9d, r9d; dwFlags
0x14000fbd0  mov     r8d, r12d; cbInput
0x14000fbd3  mov     rdx, r13; pbInput
0x14000fbd6  call    cs:__imp_BCryptHashData
0x14000fbdc  mov     ebx, eax
0x14000fbde  test    eax, eax
0x14000fbe0  js      short loc_14000FBF9
0x14000fbe2  mov     rcx, [rbp+57h+phHash]; hHash
0x14000fbe6  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x14000fbea  xor     r9d, r9d; dwFlags
0x14000fbed  lea     r8d, [r9+14h]; cbOutput
0x14000fbf1  call    cs:__imp_BCryptFinishHash
0x14000fbf7  mov     ebx, eax
0x14000fbf9  mov     rcx, [rbp+57h+phHash]; hHash
0x14000fbfd  test    rcx, rcx
0x14000fc00  jz      short loc_14000FC08
0x14000fc02  call    cs:__imp_BCryptDestroyHash
0x14000fc08  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x14000fc0c  test    rcx, rcx
0x14000fc0f  jz      short loc_14000FC19
0x14000fc11  xor     edx, edx; dwFlags
0x14000fc13  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000fc19  mov     ecx, ebx; Status
0x14000fc1b  call    cs:__imp_RtlNtStatusToDosError
0x14000fc21  mov     ebx, eax
0x14000fc23  test    eax, eax
0x14000fc25  jnz     short loc_14000FC52
0x14000fc27  mov     r8d, [r15+4]; Size
0x14000fc2b  lea     rcx, [rbp+57h+pbOutput]; Buf1
0x14000fc2f  mov     rdx, [r15+8]; Buf2
0x14000fc33  call    memcmp_0
0x14000fc38  xor     ebx, ebx
0x14000fc3a  test    eax, eax
0x14000fc3c  jz      short loc_14000FC4B
0x14000fc3e  inc     edi
0x14000fc40  cmp     edi, dword ptr [rbp+57h+var_70]
0x14000fc43  jb      loc_14000FB71
0x14000fc49  jmp     short loc_14000FC52
0x14000fc4b  mov     dword ptr [r14], 1
0x14000fc52  mov     rdi, [rbp+57h+lpMem]
0x14000fc56  test    rdi, rdi
0x14000fc59  jz      short loc_14000FC6F
0x14000fc5b  call    cs:__imp_GetProcessHeap
0x14000fc61  mov     r8, rdi; lpMem
0x14000fc64  xor     edx, edx; dwFlags
0x14000fc66  mov     rcx, rax; hHeap
0x14000fc69  call    cs:__imp_HeapFree
0x14000fc6f  mov     eax, ebx
0x14000fc71  mov     rcx, [rbp+57h+var_28]
0x14000fc75  xor     rcx, rsp; StackCookie
0x14000fc78  call    __security_check_cookie
0x14000fc7d  lea     r11, [rsp+0B0h+var_20]
0x14000fc85  mov     rbx, [r11+30h]
0x14000fc89  mov     rdi, [r11+38h]
0x14000fc8d  mov     rsp, r11
0x14000fc90  pop     r15
0x14000fc92  pop     r14
0x14000fc94  pop     r13
0x14000fc96  pop     r12
0x14000fc98  pop     rbp
0x14000fc99  retn
```
