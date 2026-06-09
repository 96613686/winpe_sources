# _lambda_80cac1bf4a374e7912bfe63e9ade0b04_::operator()

- ea: `0x180022d30`
- end: `0x180022ebd`
- name: `_lambda_80cac1bf4a374e7912bfe63e9ade0b04_::operator()`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180025380`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x18000a7a0`
- `0x18000e6f4`
- `0x180020f9c`
- `0x18002245c`
- `0x18002251c`
- `0x180022d30`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022e6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022e6a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022e29`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022e29`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022db8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022db8`

## string_xrefs

- `0x180022d6a`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180022dd4`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180022e3a`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_80cac1bf4a374e7912bfe63e9ade0b04_::operator()(__int64 a1, void *a2)
{
  int token_information; // eax
  HRESULT LastError; // ebx
  void *v5; // rcx
  void *v7; // rsi
  bool v8; // bl
  const char *v9; // r9
  __int64 v10; // rdx
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, __int64, PCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  int ppv; // [rsp+20h] [rbp-30h]
  int ppva; // [rsp+20h] [rbp-30h]
  __int64 *v16; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-18h] BYREF
  char v18; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPVOID v20; // [rsp+88h] [rbp+38h] BYREF
  __int64 v21; // [rsp+90h] [rbp+40h] BYREF
  void *Block; // [rsp+98h] [rbp+48h] BYREF

  v20 = a2;
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, -4);
  LastError = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
      (const char *)(unsigned int)token_information,
      ppv);
    v5 = Block;
    if ( !Block )
      return (unsigned int)LastError;
LABEL_3:
    operator delete(v5);
    return (unsigned int)LastError;
  }
  v21 = 0;
  v16 = &v21;
  StringSid = 0;
  v18 = 1;
  v7 = Block;
  v8 = !ConvertSidToStringSidW(*(PSID *)Block, &StringSid);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v16);
  if ( v8 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xFB,
                  (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
                  v9);
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
    if ( !v7 )
      return (unsigned int)LastError;
    v5 = v7;
    goto LABEL_3;
  }
  v20 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  LastError = CoCreateInstance(
                &GUID_54337179_c8b2_4ed4_95e4_95601c850d8c,
                0,
                1u,
                &GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c,
                &v20);
  if ( LastError < 0 )
  {
    v10 = 254;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
      (const char *)(unsigned int)LastError,
      ppva);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    goto LABEL_7;
  }
  v11 = v20;
  v12 = *(__int64 (__fastcall **)(LPVOID, __int64, PCWSTR))(*(_QWORD *)v20 + 40LL);
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 8), 0);
  LastError = v12(v11, v21, StringRawBuffer);
  if ( LastError < 0 )
  {
    v10 = 256;
    goto LABEL_11;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
  if ( v7 )
    operator delete(v7);
  return 0;
}

```

## disassembly

```asm
0x180022d30  mov     [rsp-28h+arg_8], rdx
0x180022d35  push    rbp
0x180022d36  push    rbx
0x180022d37  push    rsi
0x180022d38  push    rdi
0x180022d39  push    r14
0x180022d3b  mov     rbp, rsp
0x180022d3e  sub     rsp, 50h
0x180022d42  mov     r14, rcx
0x180022d45  mov     [rbp+Block], 0
0x180022d4d  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x180022d54  lea     rcx, [rbp+Block]
0x180022d58  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180022d5d  mov     ebx, eax
0x180022d5f  test    eax, eax
0x180022d61  jns     short loc_180022D91
0x180022d63  mov     rcx, [rbp+28h]; this
0x180022d67  mov     r9d, eax; char *
0x180022d6a  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180022d71  mov     edx, 0F8h; void *
0x180022d76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022d7b  nop
0x180022d7c  mov     rcx, [rbp+Block]; Block
0x180022d80  test    rcx, rcx
0x180022d83  jz      short loc_180022D8A
0x180022d85  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022d8a  mov     eax, ebx
0x180022d8c  jmp     loc_180022EB2
0x180022d91  mov     [rbp+arg_10], 0
0x180022d99  lea     rax, [rbp+arg_10]
0x180022d9d  mov     [rbp+var_20], rax
0x180022da1  mov     [rbp+StringSid], 0
0x180022da9  mov     [rbp+var_10], 1
0x180022dad  lea     rdx, [rbp+StringSid]; StringSid
0x180022db1  mov     rsi, [rbp+Block]
0x180022db5  mov     rcx, [rsi]; Sid
0x180022db8  call    cs:__imp_ConvertSidToStringSidW
0x180022dbe  test    eax, eax
0x180022dc0  setz    bl
0x180022dc3  lea     rcx, [rbp+var_20]
0x180022dc7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180022dcc  test    bl, bl
0x180022dce  jz      short loc_180022DFB
0x180022dd0  mov     rcx, [rbp+28h]; this
0x180022dd4  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180022ddb  mov     edx, 0FBh; void *
0x180022de0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022de5  mov     ebx, eax
0x180022de7  lea     rcx, [rbp+arg_10]
0x180022deb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180022df0  nop
0x180022df1  test    rsi, rsi
0x180022df4  jz      short loc_180022D8A
0x180022df6  mov     rcx, rsi
0x180022df9  jmp     short loc_180022D85
0x180022dfb  mov     [rbp+arg_8], 0
0x180022e03  lea     rcx, [rbp+arg_8]
0x180022e07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022e0c  lea     rax, [rbp+arg_8]
0x180022e10  mov     qword ptr [rsp+50h+ppv], rax; int
0x180022e15  lea     r9, _GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c; riid
0x180022e1c  xor     edx, edx; pUnkOuter
0x180022e1e  lea     r8d, [rdx+1]; dwClsContext
0x180022e22  lea     rcx, _GUID_54337179_c8b2_4ed4_95e4_95601c850d8c; rclsid
0x180022e29  call    cs:__imp_CoCreateInstance
0x180022e2f  mov     ebx, eax
0x180022e31  test    eax, eax
0x180022e33  jns     short loc_180022E59
0x180022e35  mov     edx, 0FEh; void *
0x180022e3a  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180022e41  mov     r9d, ebx; char *
0x180022e44  mov     rcx, [rbp+28h]; this
0x180022e48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022e4d  nop
0x180022e4e  lea     rcx, [rbp+arg_8]
0x180022e52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022e57  jmp     short loc_180022DE7
0x180022e59  mov     rdi, [rbp+arg_8]
0x180022e5d  mov     rax, [rdi]
0x180022e60  mov     rbx, [rax+28h]
0x180022e64  xor     edx, edx; length
0x180022e66  mov     rcx, [r14+8]; string
0x180022e6a  call    cs:__imp_WindowsGetStringRawBuffer
0x180022e70  mov     r8, rax
0x180022e73  mov     rdx, [rbp+arg_10]
0x180022e77  mov     rcx, rdi
0x180022e7a  mov     rax, rbx
0x180022e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e82  mov     ebx, eax
0x180022e84  test    eax, eax
0x180022e86  jns     short loc_180022E8F
0x180022e88  mov     edx, 100h
0x180022e8d  jmp     short loc_180022E3A
0x180022e8f  lea     rcx, [rbp+arg_8]
0x180022e93  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022e98  nop
0x180022e99  lea     rcx, [rbp+arg_10]
0x180022e9d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180022ea2  nop
0x180022ea3  test    rsi, rsi
0x180022ea6  jz      short loc_180022EB0
0x180022ea8  mov     rcx, rsi; Block
0x180022eab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022eb0  xor     eax, eax
0x180022eb2  add     rsp, 50h
0x180022eb6  pop     r14
0x180022eb8  pop     rdi
0x180022eb9  pop     rsi
0x180022eba  pop     rbx
0x180022ebb  pop     rbp
0x180022ebc  retn
```
