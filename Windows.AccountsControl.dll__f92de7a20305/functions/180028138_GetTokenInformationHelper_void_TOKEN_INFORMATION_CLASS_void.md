# GetTokenInformationHelper(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x180028138`
- end: `0x18002826e`
- name: `?GetTokenInformationHelper@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS, void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022520`
- `0x180022744`
- `0x180022968`
- `0x180022b8c`

## callees

- `0x180006e8c`
- `0x180006eac`
- `0x1800242d8`
- `0x180028138`
- `0x18002b748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028179`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002816b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800281d9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002816b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800281d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002818e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002818e`

## string_xrefs

- `0x1800281a6`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800281e8`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180028228`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180028243`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

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
0x180028138  mov     rax, rsp
0x18002813b  mov     [rax+8], rbx
0x18002813f  mov     [rax+18h], rsi
0x180028143  mov     [rax+10h], edx
0x180028146  push    rdi
0x180028147  sub     rsp, 30h
0x18002814b  xor     r9d, r9d; TokenInformationLength
0x18002814e  mov     dword ptr [rax+10h], 0
0x180028155  mov     rdi, r8
0x180028158  lea     rax, [rax+10h]
0x18002815c  xor     r8d, r8d; TokenInformation
0x18002815f  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180028164  mov     rsi, rcx
0x180028167  lea     edx, [r9+1]; TokenInformationClass
0x18002816b  call    cs:__imp_GetTokenInformation
0x180028171  test    eax, eax
0x180028173  jnz     loc_18002823E
0x180028179  call    cs:__imp_GetLastError
0x18002817f  cmp     eax, 7Ah ; 'z'
0x180028182  jnz     loc_18002821F
0x180028188  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x18002818c  xor     ecx, ecx; uFlags
0x18002818e  call    cs:__imp_LocalAlloc
0x180028194  mov     [rsp+38h+arg_18], rax
0x180028199  mov     rbx, rax
0x18002819c  test    rax, rax
0x18002819f  jnz     short loc_1800281BF
0x1800281a1  mov     rcx, [rsp+38h]; this
0x1800281a6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800281ad  mov     ebx, 8007000Eh
0x1800281b2  lea     edx, [rax+11h]; void *
0x1800281b5  mov     r9d, ebx; char *
0x1800281b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800281bd  jmp     short loc_1800281F9
0x1800281bf  mov     r9d, dword ptr [rsp+38h+uBytes]; TokenInformationLength
0x1800281c4  lea     rax, [rsp+38h+uBytes]
0x1800281c9  mov     r8, rbx; TokenInformation
0x1800281cc  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800281d1  mov     edx, 1; TokenInformationClass
0x1800281d6  mov     rcx, rsi; TokenHandle
0x1800281d9  call    cs:__imp_GetTokenInformation
0x1800281df  test    eax, eax
0x1800281e1  jnz     short loc_180028205
0x1800281e3  mov     rcx, [rsp+38h]; this
0x1800281e8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800281ef  lea     edx, [rax+13h]; void *
0x1800281f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800281f7  mov     ebx, eax
0x1800281f9  lea     rcx, [rsp+38h+arg_18]
0x1800281fe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028203  jmp     short loc_18002825C
0x180028205  lea     rcx, [rsp+38h+arg_18]
0x18002820a  mov     [rsp+38h+arg_18], 0
0x180028213  mov     [rdi], rbx
0x180028216  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002821b  xor     eax, eax
0x18002821d  jmp     short loc_18002825E
0x18002821f  test    eax, eax
0x180028221  jz      short loc_18002821B
0x180028223  mov     rcx, [rsp+38h]; this
0x180028228  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18002822f  mov     r9d, eax; char *
0x180028232  mov     edx, 19h; void *
0x180028237  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002823c  jmp     short loc_18002825E
0x18002823e  mov     rcx, [rsp+38h]; this
0x180028243  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18002824a  mov     ebx, 8000FFFFh
0x18002824f  mov     edx, 1Eh; void *
0x180028254  mov     r9d, ebx; char *
0x180028257  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002825c  mov     eax, ebx
0x18002825e  mov     rbx, [rsp+38h+arg_0]
0x180028263  mov     rsi, [rsp+38h+arg_10]
0x180028268  add     rsp, 30h
0x18002826c  pop     rdi
0x18002826d  retn
```
