# Windows::Internal::Management::Provision::SessionManager::GetCallerAuthenticatedUserSid(HSTRING__ * *)

- ea: `0x18003cf50`
- end: `0x18003d04e`
- name: `?GetCallerAuthenticatedUserSid@SessionManager@Provision@Management@Internal@Windows@@AEAAJPEAPEAUHSTRING__@@@Z`
- size: `254`
- prototype: `int(Windows::Internal::Management::Provision::SessionManager *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003d960`
- `0x18003da00`

## callees

- `0x18000a2a4`
- `0x180014af0`
- `0x180017204`
- `0x180019fb8`
- `0x18003cf50`
- `0x18003d174`
- `0x18003e234`

## import_xrefs

- `DMCmnUtils!DmGetUserSidFromToken` at `0x18003cfb2`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18003cfb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d017`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Management::Provision::SessionManager::GetCallerAuthenticatedUserSid(
        Windows::Internal::Management::Provision::SessionManager *this,
        HSTRING *a2)
{
  unsigned int v3; // ebx
  int UserSidFromToken; // eax
  Windows::Internal::Management::Provision::SessionManager *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  bool v11; // [rsp+48h] [rbp+28h] BYREF
  PCNZWCH sourceString; // [rsp+50h] [rbp+30h] BYREF
  void *v13; // [rsp+58h] [rbp+38h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    wil::GetImpersonationTokenForClientOfObject(&v13, this);
    sourceString = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &sourceString,
      0);
    UserSidFromToken = DmGetUserSidFromToken(v13, (unsigned __int16 **)&sourceString);
    v3 = UserSidFromToken;
    if ( UserSidFromToken >= 0 )
    {
      v11 = 0;
      UserSidFromToken = Windows::Internal::Management::Provision::SessionManager::IsWellKnownSid(
                           v5,
                           sourceString,
                           &v11);
      v3 = UserSidFromToken;
      if ( UserSidFromToken >= 0 )
      {
        if ( v11 )
        {
          v3 = 1;
          goto LABEL_15;
        }
        v7 = -1;
        do
          ++v7;
        while ( sourceString[v7] );
        UserSidFromToken = WindowsCreateString(sourceString, v7, a2);
        v3 = UserSidFromToken;
        if ( UserSidFromToken >= 0 )
        {
          v3 = 0;
          goto LABEL_15;
        }
        v6 = 158;
      }
      else
      {
        v6 = 150;
      }
    }
    else
    {
      v6 = 147;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
      (const char *)(unsigned int)UserSidFromToken,
      savedregs);
LABEL_15:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
    return v3;
  }
  v3 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8D,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
    (const char *)0x80070057LL,
    savedregs);
  return v3;
}

```

## disassembly

```asm
0x18003cf50  mov     [rsp-18h+arg_0], rbx
0x18003cf55  push    rbp
0x18003cf56  push    rsi
0x18003cf57  push    rdi; int
0x18003cf58  mov     rbp, rsp
0x18003cf5b  sub     rsp, 20h
0x18003cf5f  mov     rdi, rdx
0x18003cf62  xor     esi, esi
0x18003cf64  test    rdx, rdx
0x18003cf67  jnz     short loc_18003CF8B
0x18003cf69  mov     rcx, [rbp+18h]; this
0x18003cf6d  mov     ebx, 80070057h
0x18003cf72  mov     r9d, ebx; char *
0x18003cf75  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003cf7c  mov     edx, 8Dh; void *
0x18003cf81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cf86  jmp     loc_18003D03F
0x18003cf8b  mov     [rdx], rsi
0x18003cf8e  mov     rdx, rcx
0x18003cf91  lea     rcx, [rbp+arg_18]
0x18003cf95  call    ?GetImpersonationTokenForClientOfObject@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEAUIUnknown@@K@Z; wil::GetImpersonationTokenForClientOfObject(IUnknown *,ulong)
0x18003cf9a  nop
0x18003cf9b  mov     [rbp+sourceString], rsi
0x18003cf9f  xor     edx, edx
0x18003cfa1  lea     rcx, [rbp+sourceString]
0x18003cfa5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003cfaa  lea     rdx, [rbp+sourceString]
0x18003cfae  mov     rcx, [rbp+arg_18]
0x18003cfb2  call    cs:__imp_?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z; DmGetUserSidFromToken(void *,ushort * *)
0x18003cfb8  mov     ebx, eax
0x18003cfba  test    eax, eax
0x18003cfbc  jns     short loc_18003CFC5
0x18003cfbe  mov     edx, 93h
0x18003cfc3  jmp     short loc_18003CFE1
0x18003cfc5  mov     [rbp+arg_8], sil
0x18003cfc9  lea     r8, [rbp+arg_8]; bool *
0x18003cfcd  mov     rdx, [rbp+sourceString]; unsigned __int16 *
0x18003cfd1  call    ?IsWellKnownSid@SessionManager@Provision@Management@Internal@Windows@@AEAAJPEBGPEA_N@Z; Windows::Internal::Management::Provision::SessionManager::IsWellKnownSid(ushort const *,bool *)
0x18003cfd6  mov     ebx, eax
0x18003cfd8  test    eax, eax
0x18003cfda  jns     short loc_18003CFF6
0x18003cfdc  mov     edx, 96h; void *
0x18003cfe1  mov     rcx, [rbp+18h]; this
0x18003cfe5  mov     r9d, eax; char *
0x18003cfe8  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003cfef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cff4  jmp     short loc_18003D02C
0x18003cff6  cmp     [rbp+arg_8], sil
0x18003cffa  jz      short loc_18003D003
0x18003cffc  mov     ebx, 1
0x18003d001  jmp     short loc_18003D02C
0x18003d003  mov     rcx, [rbp+sourceString]; sourceString
0x18003d007  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003d00b  inc     rdx; length
0x18003d00e  cmp     [rcx+rdx*2], si
0x18003d012  jnz     short loc_18003D00B
0x18003d014  mov     r8, rdi; string
0x18003d017  call    cs:__imp_WindowsCreateString
0x18003d01d  mov     ebx, eax
0x18003d01f  test    eax, eax
0x18003d021  jns     short loc_18003D02A
0x18003d023  mov     edx, 9Eh
0x18003d028  jmp     short loc_18003CFE1
0x18003d02a  mov     ebx, esi
0x18003d02c  lea     rcx, [rbp+sourceString]
0x18003d030  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d035  nop
0x18003d036  lea     rcx, [rbp+arg_18]
0x18003d03a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003d03f  mov     eax, ebx
0x18003d041  mov     rbx, [rsp+20h+arg_0]
0x18003d046  add     rsp, 20h
0x18003d04a  pop     rdi
0x18003d04b  pop     rsi
0x18003d04c  pop     rbp
0x18003d04d  retn
```
