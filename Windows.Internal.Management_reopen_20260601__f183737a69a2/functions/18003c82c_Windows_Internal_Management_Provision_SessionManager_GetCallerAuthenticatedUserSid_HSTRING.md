# Windows::Internal::Management::Provision::SessionManager::GetCallerAuthenticatedUserSid(HSTRING__ * *)

- ea: `0x18003c82c`
- end: `0x18003c937`
- name: `?GetCallerAuthenticatedUserSid@SessionManager@Provision@Management@Internal@Windows@@AEAAJPEAPEAUHSTRING__@@@Z`
- size: `267`
- prototype: `int(Windows::Internal::Management::Provision::SessionManager *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003d2c0`
- `0x18003d360`

## callees

- `0x18000a5c4`
- `0x1800151e0`
- `0x1800179f8`
- `0x1800187d4`
- `0x18003c82c`
- `0x18003ca64`
- `0x18003dbe4`

## import_xrefs

- `DMCmnUtils!DmGetUserSidFromToken` at `0x18003c88e`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18003c88e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003c8f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003c8f9`

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
0x18003c82c  mov     [rsp-18h+arg_0], rbx
0x18003c831  push    rbp
0x18003c832  push    rsi
0x18003c833  push    rdi; int
0x18003c834  mov     rbp, rsp
0x18003c837  sub     rsp, 20h
0x18003c83b  mov     rdi, rdx
0x18003c83e  xor     esi, esi
0x18003c840  test    rdx, rdx
0x18003c843  jnz     short loc_18003C867
0x18003c845  mov     rcx, [rbp+18h]; this
0x18003c849  mov     ebx, 80070057h
0x18003c84e  mov     r9d, ebx; char *
0x18003c851  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003c858  mov     edx, 8Dh; void *
0x18003c85d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c862  jmp     loc_18003C927
0x18003c867  mov     [rdx], rsi
0x18003c86a  mov     rdx, rcx
0x18003c86d  lea     rcx, [rbp+arg_18]
0x18003c871  call    ?GetImpersonationTokenForClientOfObject@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEAUIUnknown@@K@Z; wil::GetImpersonationTokenForClientOfObject(IUnknown *,ulong)
0x18003c876  nop
0x18003c877  mov     [rbp+sourceString], rsi
0x18003c87b  xor     edx, edx
0x18003c87d  lea     rcx, [rbp+sourceString]
0x18003c881  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003c886  lea     rdx, [rbp+sourceString]
0x18003c88a  mov     rcx, [rbp+arg_18]
0x18003c88e  call    cs:__imp_?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z; DmGetUserSidFromToken(void *,ushort * *)
0x18003c895  nop     dword ptr [rax+rax+00h]
0x18003c89a  mov     ebx, eax
0x18003c89c  test    eax, eax
0x18003c89e  jns     short loc_18003C8A7
0x18003c8a0  mov     edx, 93h
0x18003c8a5  jmp     short loc_18003C8C3
0x18003c8a7  mov     [rbp+arg_8], sil
0x18003c8ab  lea     r8, [rbp+arg_8]; bool *
0x18003c8af  mov     rdx, [rbp+sourceString]; unsigned __int16 *
0x18003c8b3  call    ?IsWellKnownSid@SessionManager@Provision@Management@Internal@Windows@@AEAAJPEBGPEA_N@Z; Windows::Internal::Management::Provision::SessionManager::IsWellKnownSid(ushort const *,bool *)
0x18003c8b8  mov     ebx, eax
0x18003c8ba  test    eax, eax
0x18003c8bc  jns     short loc_18003C8D8
0x18003c8be  mov     edx, 96h; void *
0x18003c8c3  mov     rcx, [rbp+18h]; this
0x18003c8c7  mov     r9d, eax; char *
0x18003c8ca  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003c8d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c8d6  jmp     short loc_18003C914
0x18003c8d8  cmp     [rbp+arg_8], sil
0x18003c8dc  jz      short loc_18003C8E5
0x18003c8de  mov     ebx, 1
0x18003c8e3  jmp     short loc_18003C914
0x18003c8e5  mov     rcx, [rbp+sourceString]; sourceString
0x18003c8e9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003c8ed  inc     rdx; length
0x18003c8f0  cmp     [rcx+rdx*2], si
0x18003c8f4  jnz     short loc_18003C8ED
0x18003c8f6  mov     r8, rdi; string
0x18003c8f9  call    cs:__imp_WindowsCreateString
0x18003c900  nop     dword ptr [rax+rax+00h]
0x18003c905  mov     ebx, eax
0x18003c907  test    eax, eax
0x18003c909  jns     short loc_18003C912
0x18003c90b  mov     edx, 9Eh
0x18003c910  jmp     short loc_18003C8C3
0x18003c912  mov     ebx, esi
0x18003c914  lea     rcx, [rbp+sourceString]
0x18003c918  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003c91d  nop
0x18003c91e  lea     rcx, [rbp+arg_18]
0x18003c922  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003c927  mov     eax, ebx
0x18003c929  mov     rbx, [rsp+20h+arg_0]
0x18003c92e  add     rsp, 20h
0x18003c932  pop     rdi
0x18003c933  pop     rsi
0x18003c934  pop     rbp
0x18003c935  retn
```
