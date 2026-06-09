# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::s_GetValueAsyncThread(void *)

- ea: `0x1800235b0`
- end: `0x180023655`
- name: `?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCLabeledStringSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z`
- size: `165`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000282c`
- `0x180012024`
- `0x180013f54`
- `0x1800235b0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235f0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800235dc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800235dc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002363d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002363d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::s_GetValueAsyncThread(
        _QWORD *Parameter)
{
  char v2; // bl
  void *v3; // rcx
  DWORD LastError; // esi

  v2 = 0;
  v3 = (void *)Parameter[3];
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( ImpersonateLoggedOnUser(v3) )
    {
      LastError = 0;
      v2 = 1;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 0;
  }
  if ( LastError )
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)Parameter[1] + 168LL))(Parameter[1], 0);
  else
    SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::DoAsyncWorkInternal(
      *Parameter,
      Parameter[1],
      Parameter[2]);
  SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::~ASYNC_PARAMS(Parameter);
  operator delete(Parameter);
  if ( v2 )
    RevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x1800235b0  mov     [rsp+arg_8], rbx
0x1800235b5  mov     [rsp+arg_10], rsi
0x1800235ba  push    rdi
0x1800235bb  sub     rsp, 20h
0x1800235bf  mov     rdi, rcx
0x1800235c2  xor     bl, bl
0x1800235c4  mov     [rsp+28h+arg_0], bl
0x1800235c8  mov     rcx, [rcx+18h]; hToken
0x1800235cc  lea     rax, [rcx+1]
0x1800235d0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800235d6  jnz     short loc_1800235DC
0x1800235d8  xor     esi, esi
0x1800235da  jmp     short loc_1800235F8
0x1800235dc  call    cs:__imp_ImpersonateLoggedOnUser
0x1800235e2  test    eax, eax
0x1800235e4  jz      short loc_1800235F0
0x1800235e6  xor     esi, esi
0x1800235e8  mov     bl, 1
0x1800235ea  mov     [rsp+28h+arg_0], bl
0x1800235ee  jmp     short loc_1800235F8
0x1800235f0  call    cs:__imp_GetLastError
0x1800235f6  mov     esi, eax
0x1800235f8  test    esi, esi
0x1800235fa  jnz     short loc_18002360E
0x1800235fc  mov     r8, [rdi+10h]
0x180023600  mov     rdx, [rdi+8]
0x180023604  mov     rcx, [rdi]
0x180023607  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCLabeledStringSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x18002360c  jmp     short loc_180023623
0x18002360e  mov     rcx, [rdi+8]
0x180023612  mov     rax, [rcx]
0x180023615  xor     edx, edx
0x180023617  mov     rax, [rax+0A8h]
0x18002361e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023623  mov     rcx, rdi
0x180023626  call    ??1ASYNC_PARAMS@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::~ASYNC_PARAMS(void)
0x18002362b  mov     edx, 30h ; '0'
0x180023630  mov     rcx, rdi; Block
0x180023633  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023638  nop
0x180023639  test    bl, bl
0x18002363b  jz      short loc_180023643
0x18002363d  call    cs:__imp_RevertToSelf
0x180023643  mov     eax, esi
0x180023645  mov     rbx, [rsp+28h+arg_8]
0x18002364a  mov     rsi, [rsp+28h+arg_10]
0x18002364f  add     rsp, 20h
0x180023653  pop     rdi
0x180023654  retn
```
