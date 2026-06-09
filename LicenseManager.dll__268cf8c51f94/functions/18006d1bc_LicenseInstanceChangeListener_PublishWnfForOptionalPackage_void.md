# LicenseInstanceChangeListener::PublishWnfForOptionalPackage(void)

- ea: `0x18006d1bc`
- end: `0x18006d3f0`
- name: `?PublishWnfForOptionalPackage@LicenseInstanceChangeListener@@QEAAXXZ`
- size: `564`
- prototype: `void __fastcall(LicenseInstanceChangeListener *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180058d60`
- `0x18008c420`

## callees

- `0x180013b50`
- `0x1800593bc`
- `0x18006d1bc`
- `0x18006d3f8`
- `0x180075e60`
- `0x1800769f4`
- `0x1800b8010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18006d2e8`
- `ntdll!RtlPublishWnfStateData` at `0x18006d2e8`

## string_xrefs

- `0x18006d22b`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18006d272`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18006d2b6`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18006d33f`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18006d3a5`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
void __fastcall LicenseInstanceChangeListener::PublishWnfForOptionalPackage(LicenseInstanceChangeListener *this)
{
  int v1; // eax
  int v3; // eax
  const unsigned __int16 **v4; // rbx
  const unsigned __int16 *v5; // r8
  int v6; // eax
  unsigned __int64 v7; // r11
  const unsigned __int16 **v8; // rdi
  const unsigned __int16 *v9; // r8
  int v10; // eax
  int v11; // edx
  int Format; // [rsp+20h] [rbp-258h]
  _DWORD v13[2]; // [rsp+50h] [rbp-228h] BYREF
  unsigned __int16 v14[128]; // [rsp+58h] [rbp-220h] BYREF
  unsigned __int16 v15[132]; // [rsp+158h] [rbp-120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v1 = *((_DWORD *)this + 45);
  v13[0] = 0;
  v13[1] = v1;
  memset_0(v14, 0, 0x200u);
  v3 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 23) + 80LL))(*((_QWORD *)this + 23), v13);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x272,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v3,
      Format);
  v4 = (const unsigned __int16 **)((char *)this + 48);
  if ( *((_QWORD *)this + 9) <= 7u )
    v5 = (const unsigned __int16 *)((char *)this + 48);
  else
    v5 = *v4;
  v6 = StringCchCopyW(v14, 0x80u, v5);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x273,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v6,
      Format);
  v8 = (const unsigned __int16 **)((char *)this + 80);
  if ( *((_QWORD *)this + 13) <= 7u )
    v9 = (const unsigned __int16 *)((char *)this + 80);
  else
    v9 = *v8;
  v10 = StringCchCopyW(v15, v7, v9);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x274,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v10,
      Format);
  v11 = RtlPublishWnfStateData(WNF_LM_OPTIONAL_PACKAGE_SUSPEND_REQUIRED, 0, v13, 520, 0);
  if ( (v11 & 0xC0000000) == 0xC0000000 )
  {
    if ( _UnitTestWnfCallback )
    {
      _UnitTestWnfCallback((struct _WNF_STATE_NAME)WNF_LM_OPTIONAL_PACKAGE_SUSPEND_REQUIRED, 0, 0, 0, v13, 0x208u);
    }
    else
    {
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        0x280u,
        "LicenseInstanceChangeListener::PublishWnfForOptionalPackage",
        (wchar_t *)L"Failed to send WNF_LM_OPTIONAL_PACKAGE_SUSPEND_REQUIRED - status = 0x%08x",
        v11);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 32LL))(*((_QWORD *)this + 23));
    }
  }
  else
  {
    if ( *((_QWORD *)this + 9) > 7u )
      v4 = (const unsigned __int16 **)*v4;
    if ( *((_QWORD *)this + 13) > 7u )
      v8 = (const unsigned __int16 **)*v8;
    LogMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x286u,
      "LicenseInstanceChangeListener::PublishWnfForOptionalPackage",
      (wchar_t *)L"Sent WNF_LM_OPTIONAL_PACKAGE_SUSPEND_REQUIRED 0x%08X for %s in app package %s - status = 0x%08x",
      v13[0],
      v8,
      v4,
      v11);
  }
}

```

## disassembly

```asm
0x18006d1bc  mov     [rsp+arg_8], rbx
0x18006d1c1  mov     [rsp+arg_10], rsi
0x18006d1c6  push    rdi
0x18006d1c7  sub     rsp, 270h
0x18006d1ce  mov     rax, cs:__security_cookie
0x18006d1d5  xor     rax, rsp
0x18006d1d8  mov     [rsp+278h+var_18], rax
0x18006d1e0  mov     eax, [rcx+0B4h]
0x18006d1e6  mov     rsi, rcx
0x18006d1e9  lea     rcx, [rsp+278h+var_220]; void *
0x18006d1ee  mov     [rsp+278h+var_228], 0
0x18006d1f6  xor     edx, edx; Val
0x18006d1f8  mov     [rsp+278h+var_224], eax
0x18006d1fc  mov     r8d, 200h; Size
0x18006d202  call    memset_0
0x18006d207  mov     rcx, [rsi+0B8h]
0x18006d20e  lea     rdx, [rsp+278h+var_228]
0x18006d213  mov     rax, [rcx]
0x18006d216  mov     rax, [rax+50h]
0x18006d21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d21f  test    eax, eax
0x18006d221  jns     short loc_18006D240
0x18006d223  mov     rcx, [rsp+278h]; this
0x18006d22b  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006d232  mov     r9d, eax; char *
0x18006d235  mov     edx, 272h; void *
0x18006d23a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d240  lea     rbx, [rsi+30h]
0x18006d244  cmp     qword ptr [rbx+18h], 7
0x18006d249  jbe     short loc_18006D250
0x18006d24b  mov     r8, [rbx]
0x18006d24e  jmp     short loc_18006D253
0x18006d250  mov     r8, rbx; unsigned __int16 *
0x18006d253  mov     r11d, 80h
0x18006d259  lea     rcx, [rsp+278h+var_220]; unsigned __int16 *
0x18006d25e  mov     edx, r11d; unsigned __int64
0x18006d261  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006d266  test    eax, eax
0x18006d268  jns     short loc_18006D287
0x18006d26a  mov     rcx, [rsp+278h]; this
0x18006d272  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006d279  mov     r9d, eax; char *
0x18006d27c  mov     edx, 273h; void *
0x18006d281  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d287  lea     rdi, [rsi+50h]
0x18006d28b  cmp     qword ptr [rdi+18h], 7
0x18006d290  jbe     short loc_18006D297
0x18006d292  mov     r8, [rdi]
0x18006d295  jmp     short loc_18006D29A
0x18006d297  mov     r8, rdi; unsigned __int16 *
0x18006d29a  mov     rdx, r11; unsigned __int64
0x18006d29d  lea     rcx, [rsp+278h+var_120]; unsigned __int16 *
0x18006d2a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006d2aa  test    eax, eax
0x18006d2ac  jns     short loc_18006D2CB
0x18006d2ae  mov     rcx, [rsp+278h]; this
0x18006d2b6  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006d2bd  mov     r9d, eax; char *
0x18006d2c0  mov     edx, 274h; void *
0x18006d2c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d2cb  mov     rcx, cs:WNF_LM_OPTIONAL_PACKAGE_SUSPEND_REQUIRED
0x18006d2d2  lea     r8, [rsp+278h+var_228]
0x18006d2d7  mov     r9d, 208h
0x18006d2dd  mov     [rsp+278h+Format], 0
0x18006d2e6  xor     edx, edx
0x18006d2e8  call    cs:__imp_RtlPublishWnfStateData
0x18006d2ee  mov     ecx, eax
0x18006d2f0  mov     edx, eax
0x18006d2f2  mov     eax, 0C0000000h
0x18006d2f7  and     ecx, eax
0x18006d2f9  cmp     ecx, eax
0x18006d2fb  jnz     short loc_18006D377
0x18006d2fd  mov     rax, cs:?_UnitTestWnfCallback@@3P6AJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@ZEA; long (*_UnitTestWnfCallback)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18006d304  test    rax, rax
0x18006d307  jz      short loc_18006D334
0x18006d309  lea     rcx, [rsp+278h+var_228]
0x18006d30e  mov     [rsp+278h+var_250], 208h
0x18006d316  mov     [rsp+278h+Format], rcx
0x18006d31b  xor     r9d, r9d
0x18006d31e  mov     rcx, cs:WNF_LM_OPTIONAL_PACKAGE_SUSPEND_REQUIRED
0x18006d325  xor     r8d, r8d
0x18006d328  xor     edx, edx
0x18006d32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d32f  jmp     loc_18006D3CB
0x18006d334  mov     [rsp+278h+var_250], edx
0x18006d338  lea     rax, aFailedToSendWn_0; "Failed to send WNF_LM_OPTIONAL_PACKAGE_"...
0x18006d33f  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006d346  mov     [rsp+278h+Format], rax; Format
0x18006d34b  lea     r9, aLicenseinstanc_1; "LicenseInstanceChangeListener::PublishW"...
0x18006d352  mov     r8d, 280h; unsigned int
0x18006d358  mov     ecx, 1; unsigned int
0x18006d35d  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18006d362  mov     rcx, [rsi+0B8h]
0x18006d369  mov     rax, [rcx]
0x18006d36c  mov     rax, [rax+20h]
0x18006d370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d375  jmp     short loc_18006D3CB
0x18006d377  cmp     qword ptr [rbx+18h], 7
0x18006d37c  jbe     short loc_18006D381
0x18006d37e  mov     rbx, [rbx]
0x18006d381  cmp     qword ptr [rdi+18h], 7
0x18006d386  jbe     short loc_18006D38B
0x18006d388  mov     rdi, [rdi]
0x18006d38b  mov     eax, [rsp+278h+var_228]
0x18006d38f  lea     r9, aLicenseinstanc_1; "LicenseInstanceChangeListener::PublishW"...
0x18006d396  mov     [rsp+278h+var_238], edx
0x18006d39a  mov     r8d, 286h; unsigned int
0x18006d3a0  mov     [rsp+278h+var_240], rbx
0x18006d3a5  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006d3ac  mov     [rsp+278h+var_248], rdi
0x18006d3b1  mov     ecx, 2; unsigned int
0x18006d3b6  mov     [rsp+278h+var_250], eax
0x18006d3ba  lea     rax, aSentWnfLmOptio; "Sent WNF_LM_OPTIONAL_PACKAGE_SUSPEND_RE"...
0x18006d3c1  mov     [rsp+278h+Format], rax; Format
0x18006d3c6  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18006d3cb  mov     rcx, [rsp+278h+var_18]
0x18006d3d3  xor     rcx, rsp; StackCookie
0x18006d3d6  call    __security_check_cookie
0x18006d3db  lea     r11, [rsp+278h+var_8]
0x18006d3e3  mov     rbx, [r11+18h]
0x18006d3e7  mov     rsi, [r11+20h]
0x18006d3eb  mov     rsp, r11
0x18006d3ee  pop     rdi
0x18006d3ef  retn
```
