# GetWellKnownSidString(WELL_KNOWN_SID_TYPE)

- ea: `0x180034504`
- end: `0x180034638`
- name: `?GetWellKnownSidString@@YA?AVHString@Wrappers@WRL@Microsoft@@W4WELL_KNOWN_SID_TYPE@@@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180034498`

## callees

- `0x180003450`
- `0x180010150`
- `0x180014990`
- `0x180015624`
- `0x1800156a8`
- `0x180019624`
- `0x180034504`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800345b1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800345b1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180034557`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180034557`

## string_xrefs

- `0x180034565`: `onecoreuap\enduser\winstore\servicescommon\lib\tokenhelpers.cpp`
- `0x1800345bb`: `onecoreuap\enduser\winstore\servicescommon\lib\tokenhelpers.cpp`
- `0x1800345f8`: `onecoreuap\enduser\winstore\servicescommon\lib\tokenhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HSTRING *GetWellKnownSidString()
{
  const char *v0; // r9
  const char *v1; // r9
  int v2; // eax
  DWORD cbSid; // [rsp+20h] [rbp-49h] BYREF
  int v5; // [rsp+24h] [rbp-45h]
  void *v6; // [rsp+28h] [rbp-41h] BYREF
  _QWORD v7[2]; // [rsp+30h] [rbp-39h] BYREF
  void **v8; // [rsp+40h] [rbp-29h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-21h] BYREF
  char v10; // [rsp+50h] [rbp-19h]
  _BYTE pSid[80]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v5 = 0;
  v7[1] = &qword_1800840B8;
  cbSid = 68;
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\tokenhelpers.cpp",
      v0);
  qword_1800840B8 = 0;
  v5 = 1;
  v6 = 0;
  v8 = &v6;
  StringSid = 0;
  v10 = 1;
  if ( !ConvertSidToStringSidW(pSid, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\tokenhelpers.cpp",
      v1);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v8);
  v7[0] = v6;
  v2 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&qword_1800840B8, v7);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\tokenhelpers.cpp",
      (const char *)(unsigned int)v2,
      cbSid);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v6);
  return &qword_1800840B8;
}

```

## disassembly

```asm
0x180034504  mov     [rsp-8+arg_0], rbx
0x180034509  mov     [rsp-8+arg_8], rsi
0x18003450e  push    rbp
0x18003450f  lea     rbp, [rsp-57h]
0x180034514  sub     rsp, 0C0h
0x18003451b  mov     rax, cs:__security_cookie
0x180034522  xor     rax, rsp
0x180034525  mov     [rbp+57h+var_10], rax
0x180034529  mov     rax, [rbp+57h+var_90]
0x18003452d  mov     [rbp+57h+var_88], rax
0x180034531  mov     [rbp+57h+var_9C], 0
0x180034538  lea     rsi, qword_1800840B8
0x18003453f  mov     [rbp+57h+var_88], rsi
0x180034543  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18003454a  lea     r9, [rbp+57h+cbSid]; cbSid
0x18003454e  lea     r8, [rbp+57h+pSid]; pSid
0x180034552  xor     edx, edx; DomainSid
0x180034554  lea     ecx, [rdx+16h]; WellKnownSidType
0x180034557  call    cs:__imp_CreateWellKnownSid
0x18003455d  mov     rcx, [rbp+5Fh]; this
0x180034561  test    eax, eax
0x180034563  jnz     short loc_180034577
0x180034565  lea     r8, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\services"...
0x18003456c  mov     edx, 94h; void *
0x180034571  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180034577  mov     cs:qword_1800840B8, 0
0x180034582  mov     [rbp+57h+var_9C], 1
0x180034589  mov     [rbp+57h+var_98], 0
0x180034591  lea     rax, [rbp+57h+var_98]
0x180034595  mov     [rbp+57h+var_80], rax
0x180034599  mov     [rbp+57h+StringSid], 0
0x1800345a1  mov     [rbp+57h+var_70], 1
0x1800345a5  mov     rbx, [rbp+5Fh]
0x1800345a9  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800345ad  lea     rcx, [rbp+57h+pSid]; Sid
0x1800345b1  call    cs:__imp_ConvertSidToStringSidW
0x1800345b7  test    eax, eax
0x1800345b9  jnz     short loc_1800345D0
0x1800345bb  lea     r8, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\services"...
0x1800345c2  mov     edx, 98h; void *
0x1800345c7  mov     rcx, rbx; this
0x1800345ca  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800345d0  lea     rcx, [rbp+57h+var_80]
0x1800345d4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800345d9  mov     rax, [rbp+57h+var_98]
0x1800345dd  mov     [rbp+57h+var_90], rax
0x1800345e1  lea     rdx, [rbp+57h+var_90]
0x1800345e5  mov     rcx, rsi
0x1800345e8  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800345ed  mov     rcx, [rbp+5Fh]; this
0x1800345f1  test    eax, eax
0x1800345f3  jns     short loc_18003460A
0x1800345f5  mov     r9d, eax; char *
0x1800345f8  lea     r8, aOnecoreuapEndu_2; "onecoreuap\\enduser\\winstore\\services"...
0x1800345ff  mov     edx, 99h; void *
0x180034604  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003460a  lea     rcx, [rbp+57h+var_98]
0x18003460e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034613  mov     rax, rsi
0x180034616  mov     rcx, [rbp+57h+var_10]
0x18003461a  xor     rcx, rsp; StackCookie
0x18003461d  call    __security_check_cookie
0x180034622  lea     r11, [rsp+0C0h+var_s0]
0x18003462a  mov     rbx, [r11+10h]
0x18003462e  mov     rsi, [r11+18h]
0x180034632  mov     rsp, r11
0x180034635  pop     rbp
0x180034636  retn
```
