# _lambda_dc07a99bfe985c50c3a0ba401f40e5e2_::operator()

- ea: `0x180022ec4`
- end: `0x180022fc4`
- name: `_lambda_dc07a99bfe985c50c3a0ba401f40e5e2_::operator()`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800253c0`

## callees

- `0x180008320`
- `0x180008344`
- `0x180012408`
- `0x1800224b8`
- `0x180022ec4`
- `0x180024824`
- `0x18002695c`
- `0x180035a5c`
- `0x180035f20`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180022f37`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180022f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022f7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022f8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022f7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022f8e`

## string_xrefs

- `0x180022f14`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180022f48`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_dc07a99bfe985c50c3a0ba401f40e5e2_::operator()(__int64 a1, __int64 a2)
{
  int v4; // ebx
  int v5; // eax
  SQSAHelpers *v6; // rcx
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v8; // rax
  unsigned __int16 **v10; // [rsp+20h] [rbp-20h] BYREF
  __int64 v11; // [rsp+28h] [rbp-18h] BYREF
  char v12; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int v14; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *v15; // [rsp+78h] [rbp+38h] BYREF

  v15 = 0;
  v10 = &v15;
  v11 = 0;
  v12 = 1;
  v4 = SHGetUserName(a1, &v11);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v10);
  if ( v4 >= 0 )
  {
    v14 = 0;
    v5 = LsaLookupUserAccountType(0, &v14);
    if ( v5 >= 0 )
    {
      if ( v14 == 1 && !SHIsAccountPasswordBlank(v15) && !SQSAHelpers::IsSecurityQuestionResetBlocked(v6) )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 24), 0);
        v8 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 8), 0);
        *(_BYTE *)(a2 + 16) = (int)CloudExperienceHostBroker::Account::LocalAccountManager::s_CollectValidCredentials(
                                     *(HWND *)a1,
                                     v8,
                                     StringRawBuffer) >= 0;
      }
      v4 = 0;
    }
    else
    {
      v4 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x11E,
             (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
             (const char *)(unsigned int)v5,
             (int)v10);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11A,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
      (const char *)(unsigned int)v4,
      (int)v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180022ec4  mov     [rsp-18h+arg_0], rbx
0x180022ec9  push    rbp
0x180022eca  push    rsi
0x180022ecb  push    rdi
0x180022ecc  mov     rbp, rsp
0x180022ecf  sub     rsp, 40h
0x180022ed3  mov     rsi, rdx
0x180022ed6  mov     rdi, rcx
0x180022ed9  mov     [rbp+arg_18], 0
0x180022ee1  lea     rax, [rbp+arg_18]
0x180022ee5  mov     [rbp+var_20], rax
0x180022ee9  mov     [rbp+var_18], 0
0x180022ef1  mov     [rbp+var_10], 1
0x180022ef5  lea     rdx, [rbp+var_18]
0x180022ef9  call    SHGetUserName
0x180022efe  mov     ebx, eax
0x180022f00  lea     rcx, [rbp+var_20]
0x180022f04  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180022f09  test    ebx, ebx
0x180022f0b  jns     short loc_180022F2A
0x180022f0d  mov     rcx, [rbp+18h]; this
0x180022f11  mov     r9d, ebx; char *
0x180022f14  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180022f1b  mov     edx, 11Ah; void *
0x180022f20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f25  jmp     loc_180022FAC
0x180022f2a  mov     [rbp+arg_10], 0
0x180022f31  lea     rdx, [rbp+arg_10]
0x180022f35  xor     ecx, ecx
0x180022f37  call    cs:__imp_LsaLookupUserAccountType
0x180022f3d  test    eax, eax
0x180022f3f  jns     short loc_180022F5D
0x180022f41  mov     rcx, [rbp+18h]; this
0x180022f45  mov     r9d, eax; char *
0x180022f48  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180022f4f  mov     edx, 11Eh; void *
0x180022f54  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180022f59  mov     ebx, eax
0x180022f5b  jmp     short loc_180022FAC
0x180022f5d  cmp     [rbp+arg_10], 1
0x180022f61  jnz     short loc_180022FAA
0x180022f63  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x180022f67  call    ?SHIsAccountPasswordBlank@@YA_NPEBG@Z; SHIsAccountPasswordBlank(ushort const *)
0x180022f6c  test    al, al
0x180022f6e  jnz     short loc_180022FAA
0x180022f70  call    ?IsSecurityQuestionResetBlocked@SQSAHelpers@@YA_NXZ; SQSAHelpers::IsSecurityQuestionResetBlocked(void)
0x180022f75  test    al, al
0x180022f77  jnz     short loc_180022FAA
0x180022f79  xor     edx, edx; length
0x180022f7b  mov     rcx, [rdi+18h]; string
0x180022f7f  call    cs:__imp_WindowsGetStringRawBuffer
0x180022f85  mov     rbx, rax
0x180022f88  xor     edx, edx; length
0x180022f8a  mov     rcx, [rdi+8]; string
0x180022f8e  call    cs:__imp_WindowsGetStringRawBuffer
0x180022f94  mov     r8, rbx; unsigned __int16 *
0x180022f97  mov     rdx, rax; unsigned __int16 *
0x180022f9a  mov     rcx, [rdi]; HWND
0x180022f9d  call    ?s_CollectValidCredentials@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEAUHWND__@@PEBG1@Z; CloudExperienceHostBroker::Account::LocalAccountManager::s_CollectValidCredentials(HWND__ *,ushort const *,ushort const *)
0x180022fa2  shr     eax, 1Fh
0x180022fa5  xor     al, 1
0x180022fa7  mov     [rsi+10h], al
0x180022faa  xor     ebx, ebx
0x180022fac  lea     rcx, [rbp+arg_18]
0x180022fb0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022fb5  mov     eax, ebx
0x180022fb7  mov     rbx, [rsp+40h+arg_0]
0x180022fbc  add     rsp, 40h
0x180022fc0  pop     rdi
0x180022fc1  pop     rsi
0x180022fc2  pop     rbp
0x180022fc3  retn
```
