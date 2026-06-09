# TokenHelpers::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)

- ea: `0x18001719c`
- end: `0x1800172cd`
- name: `?GetTokenSid@TokenHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@345@@Z`
- size: `305`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800150ac`
- `0x180017b80`
- `0x180018a10`
- `0x180018c14`
- `0x180027178`

## callees

- `0x180003450`
- `0x180010150`
- `0x180014990`
- `0x180015624`
- `0x1800156a8`
- `0x18001719c`
- `0x180019624`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017248`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017248`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800171f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800171f5`

## string_xrefs

- `0x1800171ff`: `onecoreuap\enduser\WinStore\ServicesCommon\inc\TokenHelpers.h`
- `0x180017252`: `onecoreuap\enduser\WinStore\ServicesCommon\inc\TokenHelpers.h`
- `0x18001728d`: `onecoreuap\enduser\WinStore\ServicesCommon\inc\TokenHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall TokenHelpers::GetTokenSid(_QWORD *a1, __int64 a2)
{
  const char *v3; // r9
  const char *v4; // r9
  int v5; // eax
  int ReturnLength; // [rsp+20h] [rbp-69h]
  DWORD v8; // [rsp+30h] [rbp-59h] BYREF
  int v9; // [rsp+34h] [rbp-55h]
  void *v10; // [rsp+38h] [rbp-51h] BYREF
  void *v11; // [rsp+40h] [rbp-49h] BYREF
  void **v12; // [rsp+48h] [rbp-41h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-39h] BYREF
  char v14; // [rsp+58h] [rbp-31h]
  _QWORD *v15; // [rsp+60h] [rbp-29h]
  PSID TokenInformation[12]; // [rsp+70h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v15 = a1;
  v9 = 0;
  v8 = 84;
  if ( !GetTokenInformation(*(HANDLE *)(a2 + 8), TokenUser, TokenInformation, 0x54u, &v8) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecoreuap\\enduser\\WinStore\\ServicesCommon\\inc\\TokenHelpers.h",
      v3);
  *a1 = 0;
  v9 = 1;
  v10 = 0;
  v12 = &v10;
  StringSid = 0;
  v14 = 1;
  if ( !ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\enduser\\WinStore\\ServicesCommon\\inc\\TokenHelpers.h",
      v4);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v12);
  v11 = v10;
  v5 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(a1, &v11);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\enduser\\WinStore\\ServicesCommon\\inc\\TokenHelpers.h",
      (const char *)(unsigned int)v5,
      ReturnLength);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
  return a1;
}

```

## disassembly

```asm
0x18001719c  mov     [rsp-8+arg_10], rbx
0x1800171a1  mov     [rsp-8+arg_18], rdi
0x1800171a6  push    rbp
0x1800171a7  lea     rbp, [rsp-57h]
0x1800171ac  sub     rsp, 0E0h
0x1800171b3  mov     rax, cs:__security_cookie
0x1800171ba  xor     rax, rsp
0x1800171bd  mov     [rbp+57h+var_10], rax
0x1800171c1  mov     rax, rdx
0x1800171c4  mov     rbx, rcx
0x1800171c7  mov     [rbp+57h+var_80], rcx
0x1800171cb  mov     [rbp+57h+var_AC], 0
0x1800171d2  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800171d8  mov     [rbp+57h+var_B0], r9d
0x1800171dc  mov     rdi, [rbp+5Fh]
0x1800171e0  lea     rcx, [rbp+57h+var_B0]
0x1800171e4  mov     qword ptr [rsp+0E0h+ReturnLength], rcx; int
0x1800171e9  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800171ed  lea     edx, [r9-53h]; TokenInformationClass
0x1800171f1  mov     rcx, [rax+8]; TokenHandle
0x1800171f5  call    cs:__imp_GetTokenInformation
0x1800171fb  test    eax, eax
0x1800171fd  jnz     short loc_180017212
0x1800171ff  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\WinStore\\Services"...
0x180017206  lea     edx, [rax+58h]; void *
0x180017209  mov     rcx, rdi; this
0x18001720c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180017212  mov     qword ptr [rbx], 0
0x180017219  mov     [rbp+57h+var_AC], 1
0x180017220  mov     [rbp+57h+var_A8], 0
0x180017228  lea     rax, [rbp+57h+var_A8]
0x18001722c  mov     [rbp+57h+var_98], rax
0x180017230  mov     [rbp+57h+StringSid], 0
0x180017238  mov     [rbp+57h+var_88], 1
0x18001723c  mov     rdi, [rbp+5Fh]
0x180017240  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180017244  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x180017248  call    cs:__imp_ConvertSidToStringSidW
0x18001724e  test    eax, eax
0x180017250  jnz     short loc_180017265
0x180017252  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\WinStore\\Services"...
0x180017259  lea     edx, [rax+5Dh]; void *
0x18001725c  mov     rcx, rdi; this
0x18001725f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180017265  lea     rcx, [rbp+57h+var_98]
0x180017269  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18001726e  mov     rax, [rbp+57h+var_A8]
0x180017272  mov     [rbp+57h+var_A0], rax
0x180017276  lea     rdx, [rbp+57h+var_A0]
0x18001727a  mov     rcx, rbx
0x18001727d  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180017282  mov     rcx, [rbp+5Fh]; this
0x180017286  test    eax, eax
0x180017288  jns     short loc_18001729F
0x18001728a  mov     r9d, eax; char *
0x18001728d  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\WinStore\\Services"...
0x180017294  mov     edx, 5Eh ; '^'; void *
0x180017299  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001729f  lea     rcx, [rbp+57h+var_A8]
0x1800172a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800172a8  mov     rax, rbx
0x1800172ab  mov     rcx, [rbp+57h+var_10]
0x1800172af  xor     rcx, rsp; StackCookie
0x1800172b2  call    __security_check_cookie
0x1800172b7  lea     r11, [rsp+0E0h+var_s0]
0x1800172bf  mov     rbx, [r11+20h]
0x1800172c3  mov     rdi, [r11+28h]
0x1800172c7  mov     rsp, r11
0x1800172ca  pop     rbp
0x1800172cb  retn
```
