# SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting::IsLicenseUpgradePrepared(void)

- ea: `0x180026fe4`
- end: `0x180027078`
- name: `?IsLicenseUpgradePrepared@ConnectWorkSchoolAccountSetting@WorkAccess@SystemSettings@@AEAA_NXZ`
- size: `148`
- prototype: `bool __fastcall(SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023db4`

## callees

- `0x180005490`
- `0x180017a84`
- `0x180026fe4`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027016`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027016`

## string_xrefs

- `0x18002704d`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting::IsLicenseUpgradePrepared(
        SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting *this)
{
  HRESULT v1; // eax
  __int64 v2; // rdx
  bool v3; // bl
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v7; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+44h] [rbp+Ch]
  LPVOID v9; // [rsp+48h] [rbp+10h] BYREF

  v8 = HIDWORD(this);
  v7 = 0;
  v9 = 0;
  v1 = CoCreateInstance(
         &GUID_2c012f55_1318_44f4_a235_20c4df918fb3,
         0,
         1u,
         &GUID_3f633654_f773_480f_ad8b_bf48f536852d,
         &v9);
  if ( v1 < 0 )
  {
    v2 = 115;
LABEL_5:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
      (const char *)(unsigned int)v1,
      ppv);
    goto LABEL_6;
  }
  v1 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v9 + 40LL))(v9, &v7);
  if ( v1 < 0 )
  {
    v2 = 118;
    goto LABEL_5;
  }
LABEL_6:
  v3 = v7 != 0;
  wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v9);
  return v3;
}

```

## disassembly

```asm
0x180026fe4  mov     rax, rsp
0x180026fe7  mov     [rax+8], rcx
0x180026feb  push    rbx
0x180026fec  sub     rsp, 30h
0x180026ff0  xor     ebx, ebx
0x180026ff2  mov     [rax+8], ebx
0x180026ff5  mov     [rax+10h], rbx
0x180026ff9  lea     rax, [rax+10h]
0x180026ffd  mov     qword ptr [rsp+38h+ppv], rax; int
0x180027002  lea     r9, _GUID_3f633654_f773_480f_ad8b_bf48f536852d; riid
0x180027009  xor     edx, edx; pUnkOuter
0x18002700b  lea     r8d, [rbx+1]; dwClsContext
0x18002700f  lea     rcx, _GUID_2c012f55_1318_44f4_a235_20c4df918fb3; rclsid
0x180027016  call    cs:__imp_CoCreateInstance
0x18002701d  nop     dword ptr [rax+rax+00h]
0x180027022  test    eax, eax
0x180027024  jns     short loc_18002702B
0x180027026  lea     edx, [rbx+73h]
0x180027029  jmp     short loc_18002704A
0x18002702b  mov     rcx, [rsp+38h+arg_8]
0x180027030  mov     rax, [rcx]
0x180027033  lea     rdx, [rsp+38h+arg_0]
0x180027038  mov     rax, [rax+28h]
0x18002703c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027041  test    eax, eax
0x180027043  jns     short loc_18002705E
0x180027045  mov     edx, 76h ; 'v'; void *
0x18002704a  mov     r9d, eax; char *
0x18002704d  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180027054  mov     rcx, [rsp+38h]; this
0x180027059  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002705e  cmp     [rsp+38h+arg_0], ebx
0x180027062  setnz   bl
0x180027065  lea     rcx, [rsp+38h+arg_8]
0x18002706a  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x18002706f  mov     al, bl
0x180027071  add     rsp, 30h
0x180027075  pop     rbx
0x180027076  retn
```
