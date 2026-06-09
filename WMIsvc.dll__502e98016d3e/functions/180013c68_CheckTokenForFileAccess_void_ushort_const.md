# CheckTokenForFileAccess(void *,ushort const *)

- ea: `0x180013c68`
- end: `0x180013dd6`
- name: `?CheckTokenForFileAccess@@YAKPEAXPEBG@Z`
- size: `366`
- prototype: `unsigned int __fastcall(HANDLE ClientToken, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800136e4`

## callees

- `0x180013c68`
- `0x18001d377`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d8e`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180013cb5`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180013d04`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180013cb5`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180013d04`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180013d84`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180013d84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013cd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013cd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013dac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013dac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall CheckTokenForFileAccess(HANDLE ClientToken, LPCWSTR lpFileName)
{
  DWORD result; // eax
  HLOCAL v5; // rdi
  DWORD LastError; // ebx
  DWORD nLengthNeeded; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-BCh] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-B8h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp-B4h] BYREF
  HLOCAL v11; // [rsp+50h] [rbp-B0h]
  _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp-A8h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp-90h] BYREF

  nLengthNeeded = 0;
  if ( GetFileSecurityW(lpFileName, 0xFu, 0, 0, &nLengthNeeded) || (result = GetLastError(), result == 122) )
  {
    v5 = LocalAlloc(0, nLengthNeeded);
    if ( v5 )
    {
      if ( GetFileSecurityW(lpFileName, 0xFu, v5, nLengthNeeded, &nLengthNeeded)
        && (v11 = v5,
            AccessStatus = 0,
            GrantedAccess = 0,
            GenericMapping = 0,
            memset_0(&PrivilegeSet, 0, 0x1C4u),
            PrivilegeSetLength = 452,
            AccessCheck(
              v5,
              ClientToken,
              0x120116u,
              &GenericMapping,
              &PrivilegeSet,
              &PrivilegeSetLength,
              &GrantedAccess,
              &AccessStatus)) )
      {
        if ( AccessStatus )
          LastError = 0;
        else
          LastError = 5;
      }
      else
      {
        LastError = GetLastError();
      }
      LocalFree(v5);
      return LastError;
    }
    else
    {
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013c68  mov     [rsp-8+arg_10], rbx
0x180013c6d  push    rbp
0x180013c6e  push    rsi
0x180013c6f  push    rdi
0x180013c70  lea     rbp, [rsp-150h]
0x180013c78  sub     rsp, 250h
0x180013c7f  mov     rax, cs:__security_cookie
0x180013c86  xor     rax, rsp
0x180013c89  mov     [rbp+160h+var_20], rax
0x180013c90  mov     rbx, rdx
0x180013c93  mov     rsi, rcx
0x180013c96  mov     [rsp+260h+nLengthNeeded], 0
0x180013c9e  lea     rax, [rsp+260h+nLengthNeeded]
0x180013ca3  mov     [rsp+260h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180013ca8  xor     r9d, r9d; nLength
0x180013cab  xor     r8d, r8d; pSecurityDescriptor
0x180013cae  lea     edx, [r9+0Fh]; RequestedInformation
0x180013cb2  mov     rcx, rbx; lpFileName
0x180013cb5  call    cs:__imp_GetFileSecurityW
0x180013cbb  test    eax, eax
0x180013cbd  jnz     short loc_180013CCE
0x180013cbf  call    cs:__imp_GetLastError
0x180013cc5  cmp     eax, 7Ah ; 'z'
0x180013cc8  jnz     loc_180013DB4
0x180013cce  mov     edx, [rsp+260h+nLengthNeeded]; uBytes
0x180013cd2  xor     ecx, ecx; uFlags
0x180013cd4  call    cs:__imp_LocalAlloc
0x180013cda  mov     rdi, rax
0x180013cdd  test    rax, rax
0x180013ce0  jnz     short loc_180013CEA
0x180013ce2  lea     eax, [rdi+8]
0x180013ce5  jmp     loc_180013DB4
0x180013cea  lea     rax, [rsp+260h+nLengthNeeded]
0x180013cef  mov     [rsp+260h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180013cf4  mov     r9d, [rsp+260h+nLengthNeeded]; nLength
0x180013cf9  mov     r8, rdi; pSecurityDescriptor
0x180013cfc  mov     edx, 0Fh; RequestedInformation
0x180013d01  mov     rcx, rbx; lpFileName
0x180013d04  call    cs:__imp_GetFileSecurityW
0x180013d0a  test    eax, eax
0x180013d0c  jnz     short loc_180013D16
0x180013d0e  call    cs:__imp_GetLastError
0x180013d14  jmp     short loc_180013D95
0x180013d16  mov     [rsp+260h+var_210], rdi
0x180013d1b  mov     [rsp+260h+var_21C], 0
0x180013d23  mov     [rsp+260h+var_218], 0
0x180013d2b  xorps   xmm0, xmm0
0x180013d2e  movups  xmmword ptr [rsp+260h+GenericMapping.GenericRead], xmm0
0x180013d33  mov     ebx, 1C4h
0x180013d38  mov     r8d, ebx; Size
0x180013d3b  xor     edx, edx; Val
0x180013d3d  lea     rcx, [rsp+260h+PrivilegeSet]; void *
0x180013d42  call    memset_0
0x180013d47  mov     [rsp+260h+var_214], ebx
0x180013d4b  lea     rax, [rsp+260h+var_21C]
0x180013d50  mov     [rsp+260h+AccessStatus], rax; AccessStatus
0x180013d55  lea     rax, [rsp+260h+var_218]
0x180013d5a  mov     [rsp+260h+GrantedAccess], rax; GrantedAccess
0x180013d5f  lea     rax, [rsp+260h+var_214]
0x180013d64  mov     [rsp+260h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180013d69  lea     rax, [rsp+260h+PrivilegeSet]
0x180013d6e  mov     [rsp+260h+lpnLengthNeeded], rax; PrivilegeSet
0x180013d73  lea     r9, [rsp+260h+GenericMapping]; GenericMapping
0x180013d78  mov     r8d, 120116h; DesiredAccess
0x180013d7e  mov     rdx, rsi; ClientToken
0x180013d81  mov     rcx, rdi; pSecurityDescriptor
0x180013d84  call    cs:__imp_AccessCheck
0x180013d8a  test    eax, eax
0x180013d8c  jnz     short loc_180013D99
0x180013d8e  call    cs:__imp_GetLastError
0x180013d94  nop
0x180013d95  mov     ebx, eax
0x180013d97  jmp     short loc_180013DA9
0x180013d99  cmp     [rsp+260h+var_21C], 0
0x180013d9e  jnz     short loc_180013DA7
0x180013da0  mov     ebx, 5
0x180013da5  jmp     short loc_180013DA9
0x180013da7  xor     ebx, ebx
0x180013da9  mov     rcx, rdi; hMem
0x180013dac  call    cs:__imp_LocalFree
0x180013db2  mov     eax, ebx
0x180013db4  mov     rcx, [rbp+160h+var_20]
0x180013dbb  xor     rcx, rsp; StackCookie
0x180013dbe  call    __security_check_cookie
0x180013dc3  mov     rbx, [rsp+260h+arg_10]
0x180013dcb  add     rsp, 250h
0x180013dd2  pop     rdi
0x180013dd3  pop     rsi
0x180013dd4  pop     rbp
0x180013dd5  retn
```
