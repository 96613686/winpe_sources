# SystemSettings::Prov::CProvisioningDeleteSetting::DoGenericAsyncWork(void)

- ea: `0x180013b50`
- end: `0x180013bfd`
- name: `?DoGenericAsyncWork@CProvisioningDeleteSetting@Prov@SystemSettings@@MEAAXXZ`
- size: `173`
- prototype: `void __fastcall(SystemSettings::Prov::CProvisioningDeleteSetting *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800087ec`
- `0x180010238`
- `0x180011248`
- `0x180013b50`
- `0x180022634`
- `0x180028860`
- `0x18002c010`

## string_xrefs

- `0x180013ba2`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SystemSettings::Prov::CProvisioningDeleteSetting::DoGenericAsyncWork(
        const struct ProvPackageInfo **this)
{
  int v1; // eax
  const char *v2; // r9
  int v3; // [rsp+20h] [rbp-88h] BYREF
  int *v4; // [rsp+28h] [rbp-80h] BYREF
  _BYTE v5[96]; // [rsp+30h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  try
  {
    ProvPackageInfo::ProvPackageInfo((ProvPackageInfo *)v5, this[34]);
    v1 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)qword_18003EF18 + 48LL))(qword_18003EF18, v5);
    if ( v1 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
        (const char *)(unsigned int)v1,
        v3);
    v3 = 1;
    v4 = &v3;
    SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::_Notify<_lambda_54ed50563004914756eca7ce6ffaf3b0_>(
      &g_CProvisioningSingleton,
      &v4);
    ProvPackageInfo::~ProvPackageInfo((ProvPackageInfo *)v5);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x2A9,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      v2);
  }
}

```

## disassembly

```asm
0x180013b50  sub     rsp, 0A8h
0x180013b57  mov     rax, cs:__security_cookie
0x180013b5e  xor     rax, rsp
0x180013b61  mov     [rsp+0A8h+var_18], rax
0x180013b69  mov     rdx, [rcx+110h]; struct ProvPackageInfo *
0x180013b70  lea     rcx, [rsp+0A8h+var_78]; this
0x180013b75  call    ??0ProvPackageInfo@@QEAA@AEBV0@@Z; ProvPackageInfo::ProvPackageInfo(ProvPackageInfo const &)
0x180013b7a  nop
0x180013b7b  mov     rcx, cs:qword_18003EF18
0x180013b82  mov     rax, [rcx]
0x180013b85  lea     rdx, [rsp+0A8h+var_78]
0x180013b8a  mov     rax, [rax+30h]
0x180013b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b93  test    eax, eax
0x180013b95  jns     short loc_180013BB3
0x180013b97  mov     rcx, [rsp+0A8h]; this
0x180013b9f  mov     r9d, eax; char *
0x180013ba2  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180013ba9  mov     edx, 145h; void *
0x180013bae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013bb3  mov     [rsp+0A8h+var_88], 1
0x180013bbb  lea     rax, [rsp+0A8h+var_88]
0x180013bc0  mov     [rsp+0A8h+var_80], rax
0x180013bc5  lea     rdx, [rsp+0A8h+var_80]
0x180013bca  lea     rcx, ?g_CProvisioningSingleton@@3VCProvisioningSingleton@@A; CProvisioningSingleton g_CProvisioningSingleton
0x180013bd1  call    ??$_Notify@V_lambda_54ed50563004914756eca7ce6ffaf3b0_@@@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_54ed50563004914756eca7ce6ffaf3b0_@@@Z; SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::_Notify<_lambda_54ed50563004914756eca7ce6ffaf3b0_>(_lambda_54ed50563004914756eca7ce6ffaf3b0_ const &)
0x180013bd6  nop
0x180013bd7  lea     rcx, [rsp+0A8h+var_78]; this
0x180013bdc  call    ??1ProvPackageInfo@@QEAA@XZ; ProvPackageInfo::~ProvPackageInfo(void)
0x180013be1  nop
0x180013be2  jmp     short $+2
0x180013be4  mov     rcx, [rsp+0A8h+var_18]
0x180013bec  xor     rcx, rsp; StackCookie
0x180013bef  call    __security_check_cookie
0x180013bf4  add     rsp, 0A8h
0x180013bfb  retn
```
