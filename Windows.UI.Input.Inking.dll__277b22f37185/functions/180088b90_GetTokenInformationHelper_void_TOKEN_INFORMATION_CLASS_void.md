# GetTokenInformationHelper(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x180088b90`
- end: `0x180088cc6`
- name: `?GetTokenInformationHelper@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180086f20`

## callees

- `0x18001330c`
- `0x18001332c`
- `0x180033b04`
- `0x180087ab4`
- `0x180088b90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088bd1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180088bc3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180088c31`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180088bc3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180088c31`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180088be6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180088be6`

## string_xrefs

- `0x180088bfe`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180088c40`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180088c80`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180088c9b`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
int __fastcall GetTokenInformationHelper(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS a2, void **a3)
{
  DWORD LastError; // eax
  void *v6; // rbx
  int v7; // ebx
  const char *v8; // r9
  unsigned int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SIZE_T uBytes; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v13; // [rsp+58h] [rbp+20h] BYREF

  LODWORD(uBytes) = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&uBytes) )
  {
    v7 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
      (const char *)0x8000FFFFLL,
      ReturnLength);
    return v7;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x19,
               (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
               (const char *)LastError,
               ReturnLength);
    return 0;
  }
  v13 = LocalAlloc(0, (unsigned int)uBytes);
  v6 = v13;
  if ( v13 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, v13, uBytes, (PDWORD)&uBytes) )
    {
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x13,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             v8);
      goto LABEL_7;
    }
    v13 = 0;
    *a3 = v6;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
    return 0;
  }
  v7 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11,
    (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
    (const char *)0x8007000ELL,
    ReturnLength);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
  return v7;
}

```

## disassembly

```asm
0x180088b90  mov     rax, rsp
0x180088b93  mov     [rax+8], rbx
0x180088b97  mov     [rax+18h], rsi
0x180088b9b  mov     [rax+10h], edx
0x180088b9e  push    rdi
0x180088b9f  sub     rsp, 30h
0x180088ba3  xor     r9d, r9d; TokenInformationLength
0x180088ba6  mov     dword ptr [rax+10h], 0
0x180088bad  mov     rdi, r8
0x180088bb0  lea     rax, [rax+10h]
0x180088bb4  xor     r8d, r8d; TokenInformation
0x180088bb7  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180088bbc  mov     rsi, rcx
0x180088bbf  lea     edx, [r9+1]; TokenInformationClass
0x180088bc3  call    cs:__imp_GetTokenInformation
0x180088bc9  test    eax, eax
0x180088bcb  jnz     loc_180088C96
0x180088bd1  call    cs:__imp_GetLastError
0x180088bd7  cmp     eax, 7Ah ; 'z'
0x180088bda  jnz     loc_180088C77
0x180088be0  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x180088be4  xor     ecx, ecx; uFlags
0x180088be6  call    cs:__imp_LocalAlloc
0x180088bec  mov     [rsp+38h+arg_18], rax
0x180088bf1  mov     rbx, rax
0x180088bf4  test    rax, rax
0x180088bf7  jnz     short loc_180088C17
0x180088bf9  mov     rcx, [rsp+38h]; this
0x180088bfe  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180088c05  mov     ebx, 8007000Eh
0x180088c0a  lea     edx, [rax+11h]; void *
0x180088c0d  mov     r9d, ebx; char *
0x180088c10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088c15  jmp     short loc_180088C51
0x180088c17  mov     r9d, dword ptr [rsp+38h+uBytes]; TokenInformationLength
0x180088c1c  lea     rax, [rsp+38h+uBytes]
0x180088c21  mov     r8, rbx; TokenInformation
0x180088c24  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180088c29  mov     edx, 1; TokenInformationClass
0x180088c2e  mov     rcx, rsi; TokenHandle
0x180088c31  call    cs:__imp_GetTokenInformation
0x180088c37  test    eax, eax
0x180088c39  jnz     short loc_180088C5D
0x180088c3b  mov     rcx, [rsp+38h]; this
0x180088c40  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180088c47  lea     edx, [rax+13h]; void *
0x180088c4a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180088c4f  mov     ebx, eax
0x180088c51  lea     rcx, [rsp+38h+arg_18]
0x180088c56  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180088c5b  jmp     short loc_180088CB4
0x180088c5d  lea     rcx, [rsp+38h+arg_18]
0x180088c62  mov     [rsp+38h+arg_18], 0
0x180088c6b  mov     [rdi], rbx
0x180088c6e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180088c73  xor     eax, eax
0x180088c75  jmp     short loc_180088CB6
0x180088c77  test    eax, eax
0x180088c79  jz      short loc_180088C73
0x180088c7b  mov     rcx, [rsp+38h]; this
0x180088c80  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180088c87  mov     r9d, eax; char *
0x180088c8a  mov     edx, 19h; void *
0x180088c8f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180088c94  jmp     short loc_180088CB6
0x180088c96  mov     rcx, [rsp+38h]; this
0x180088c9b  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180088ca2  mov     ebx, 8000FFFFh
0x180088ca7  mov     edx, 1Eh; void *
0x180088cac  mov     r9d, ebx; char *
0x180088caf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088cb4  mov     eax, ebx
0x180088cb6  mov     rbx, [rsp+38h+arg_0]
0x180088cbb  mov     rsi, [rsp+38h+arg_10]
0x180088cc0  add     rsp, 30h
0x180088cc4  pop     rdi
0x180088cc5  retn
```
