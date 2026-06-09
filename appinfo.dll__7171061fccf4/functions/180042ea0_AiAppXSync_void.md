# AiAppXSync(void *)

- ea: `0x180042ea0`
- end: `0x180042faa`
- name: `?AiAppXSync@@YAJPEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(HANDLE hToken)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800436a8`

## callees

- `0x18001a0d4`
- `0x1800212cc`
- `0x180042e08`
- `0x180042e48`
- `0x180042ea0`
- `0x180043794`
- `0x1800438ec`
- `0x180046e50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180042eec`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180042eec`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042f75`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042f75`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x180042f3c`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x180042f3c`

## string_xrefs

- `0x180042efe`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

## pseudocode

```c
__int64 __fastcall AiAppXSync(HANDLE hToken)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  int v4; // edi
  __int64 *v5; // rbx
  int v7[3]; // [rsp+34h] [rbp-174h] BYREF
  _QWORD v8[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v8);
  v8[0] = &LUATelemetry::AppXSyncActivity::`vftable';
  LUATelemetry::AppXSyncActivity::StartActivity((LUATelemetry::AppXSyncActivity *)v8);
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    v4 = 1;
    v5 = (__int64 *)&off_18004BC10;
    do
    {
      v7[0] = RegisterAppXPackageIfNecessary2(0, *v5, 0, 0);
      if ( v7[0] < 0 )
      {
        LUATelemetry::SettingsSyncErrorContext<long &,unsigned short * const &>(v7, v5);
        v4 = 0;
      }
      ++v5;
    }
    while ( v5 != &qword_18004BC18 );
    LUATelemetry::AppXSyncActivity::Stop((LUATelemetry::AppXSyncActivity *)v8, v4);
    RevertToSelf();
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xF3,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
                  v2);
  }
  LUATelemetry::AppXSyncActivity::~AppXSyncActivity((LUATelemetry::AppXSyncActivity *)v8);
  return LastError;
}

```

## disassembly

```asm
0x180042ea0  mov     [rsp+arg_8], rbx
0x180042ea5  push    rdi
0x180042ea6  sub     rsp, 1A0h
0x180042ead  mov     rax, cs:__security_cookie
0x180042eb4  xor     rax, rsp
0x180042eb7  mov     [rsp+1A8h+var_18], rax
0x180042ebf  mov     rbx, rcx
0x180042ec2  lea     rdx, aAppxsyncactivi; "AppXSyncActivity"
0x180042ec9  lea     rcx, [rsp+1A8h+var_168]; struct wil::details::IFailureCallback *
0x180042ece  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180042ed3  lea     rax, ??_7AppXSyncActivity@LUATelemetry@@6B@; const LUATelemetry::AppXSyncActivity::`vftable'
0x180042eda  lea     rcx, [rsp+1A8h+var_168]; this
0x180042edf  mov     [rsp+1A8h+var_168], rax
0x180042ee4  call    ?StartActivity@AppXSyncActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::AppXSyncActivity::StartActivity(void)
0x180042ee9  mov     rcx, rbx; hToken
0x180042eec  call    cs:__imp_ImpersonateLoggedOnUser
0x180042ef2  test    eax, eax
0x180042ef4  jnz     short loc_180042F13
0x180042ef6  mov     rcx, [rsp+1A8h]; this
0x180042efe  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180042f05  mov     edx, 0F3h; void *
0x180042f0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042f0f  mov     ebx, eax
0x180042f11  jmp     short loc_180042F7D
0x180042f13  mov     edi, 1
0x180042f18  lea     rbx, off_18004BC10; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x180042f1f  mov     rdx, [rbx]
0x180042f22  lea     rax, [rsp+1A8h+var_178]
0x180042f27  xor     r9d, r9d
0x180042f2a  mov     [rsp+1A8h+var_188], rax
0x180042f2f  xor     r8d, r8d
0x180042f32  mov     [rsp+1A8h+var_178], 0
0x180042f3a  xor     ecx, ecx
0x180042f3c  call    cs:__imp_RegisterAppXPackageIfNecessary2
0x180042f42  mov     [rsp+1A8h+var_174], eax
0x180042f46  test    eax, eax
0x180042f48  jns     short loc_180042F59
0x180042f4a  mov     rdx, rbx
0x180042f4d  lea     rcx, [rsp+1A8h+var_174]
0x180042f52  call    ??$SettingsSyncErrorContext@AEAJAEBQEAG@LUATelemetry@@SAXAEAJAEBQEAG@Z; LUATelemetry::SettingsSyncErrorContext<long &,ushort * const &>(long &,ushort * const &)
0x180042f57  xor     edi, edi
0x180042f59  add     rbx, 8
0x180042f5d  lea     rax, qword_18004BC18
0x180042f64  cmp     rbx, rax
0x180042f67  jnz     short loc_180042F1F
0x180042f69  mov     edx, edi; int
0x180042f6b  lea     rcx, [rsp+1A8h+var_168]; this
0x180042f70  call    ?Stop@AppXSyncActivity@LUATelemetry@@QEAAXH@Z; LUATelemetry::AppXSyncActivity::Stop(int)
0x180042f75  call    cs:__imp_RevertToSelf
0x180042f7b  xor     ebx, ebx
0x180042f7d  lea     rcx, [rsp+1A8h+var_168]; this
0x180042f82  call    ??1AppXSyncActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::AppXSyncActivity::~AppXSyncActivity(void)
0x180042f87  mov     eax, ebx
0x180042f89  mov     rcx, [rsp+1A8h+var_18]
0x180042f91  xor     rcx, rsp; StackCookie
0x180042f94  call    __security_check_cookie
0x180042f99  mov     rbx, [rsp+1A8h+arg_8]
0x180042fa1  add     rsp, 1A0h
0x180042fa8  pop     rdi
0x180042fa9  retn
```
