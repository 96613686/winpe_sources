# AiAppXSync(void *)

- ea: `0x180040304`
- end: `0x18004040e`
- name: `?AiAppXSync@@YAJPEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(HANDLE hToken)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180040b00`

## callees

- `0x180018400`
- `0x18001dfd8`
- `0x180040270`
- `0x1800402ac`
- `0x180040304`
- `0x180040bf0`
- `0x180040d50`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180040355`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180040355`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800403d4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800403d4`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x1800403a1`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x1800403a1`

## string_xrefs

- `0x18004036f`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

## pseudocode

```c
__int64 __fastcall AiAppXSync(HANDLE hToken)
{
  int v2; // edi
  BOOL v3; // eax
  const char *v4; // r9
  unsigned int LastError; // ebx
  int v7[3]; // [rsp+34h] [rbp-174h] BYREF
  _QWORD v8[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v8);
  v8[0] = &LUATelemetry::AppXSyncActivity::`vftable';
  LUATelemetry::AppXSyncActivity::StartActivity((LUATelemetry::AppXSyncActivity *)v8);
  v2 = 1;
  v3 = ImpersonateLoggedOnUser(hToken);
  LastError = 0;
  if ( v3 )
  {
    v7[0] = RegisterAppXPackageIfNecessary2(0, L"Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe!App", 0, 0);
    if ( v7[0] < 0 )
    {
      LUATelemetry::SettingsSyncErrorContext<long &,unsigned short * const &>(v7, off_180048980);
      v2 = 0;
    }
    LUATelemetry::AppXSyncActivity::Stop((LUATelemetry::AppXSyncActivity *)v8, v2);
    RevertToSelf();
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xF2,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
                  v4);
  }
  LUATelemetry::AppXSyncActivity::~AppXSyncActivity((LUATelemetry::AppXSyncActivity *)v8);
  return LastError;
}

```

## disassembly

```asm
0x180040304  mov     [rsp+arg_8], rbx
0x180040309  push    rdi
0x18004030a  sub     rsp, 1A0h
0x180040311  mov     rax, cs:__security_cookie
0x180040318  xor     rax, rsp
0x18004031b  mov     [rsp+1A8h+var_18], rax
0x180040323  mov     rbx, rcx
0x180040326  lea     rdx, aAppxsyncactivi; "AppXSyncActivity"
0x18004032d  lea     rcx, [rsp+1A8h+var_168]; struct wil::details::IFailureCallback *
0x180040332  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180040337  lea     rax, ??_7AppXSyncActivity@LUATelemetry@@6B@; const LUATelemetry::AppXSyncActivity::`vftable'
0x18004033e  lea     rcx, [rsp+1A8h+var_168]; this
0x180040343  mov     [rsp+1A8h+var_168], rax
0x180040348  call    ?StartActivity@AppXSyncActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::AppXSyncActivity::StartActivity(void)
0x18004034d  mov     rcx, rbx; hToken
0x180040350  mov     edi, 1
0x180040355  call    cs:__imp_ImpersonateLoggedOnUser
0x18004035c  nop     dword ptr [rax+rax+00h]
0x180040361  xor     ebx, ebx
0x180040363  test    eax, eax
0x180040365  jnz     short loc_180040384
0x180040367  mov     rcx, [rsp+1A8h]; this
0x18004036f  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040376  mov     edx, 0F2h; void *
0x18004037b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040380  mov     ebx, eax
0x180040382  jmp     short loc_1800403E0
0x180040384  mov     rdx, cs:off_180048980; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x18004038b  lea     rax, [rsp+1A8h+var_178]
0x180040390  xor     r9d, r9d
0x180040393  mov     [rsp+1A8h+var_188], rax
0x180040398  xor     r8d, r8d
0x18004039b  mov     [rsp+1A8h+var_178], ebx
0x18004039f  xor     ecx, ecx
0x1800403a1  call    cs:__imp_RegisterAppXPackageIfNecessary2
0x1800403a8  nop     dword ptr [rax+rax+00h]
0x1800403ad  mov     [rsp+1A8h+var_174], eax
0x1800403b1  test    eax, eax
0x1800403b3  jns     short loc_1800403C8
0x1800403b5  lea     rdx, off_180048980; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x1800403bc  lea     rcx, [rsp+1A8h+var_174]
0x1800403c1  call    ??$SettingsSyncErrorContext@AEAJAEBQEAG@LUATelemetry@@SAXAEAJAEBQEAG@Z; LUATelemetry::SettingsSyncErrorContext<long &,ushort * const &>(long &,ushort * const &)
0x1800403c6  mov     edi, ebx
0x1800403c8  mov     edx, edi; int
0x1800403ca  lea     rcx, [rsp+1A8h+var_168]; this
0x1800403cf  call    ?Stop@AppXSyncActivity@LUATelemetry@@QEAAXH@Z; LUATelemetry::AppXSyncActivity::Stop(int)
0x1800403d4  call    cs:__imp_RevertToSelf
0x1800403db  nop     dword ptr [rax+rax+00h]
0x1800403e0  lea     rcx, [rsp+1A8h+var_168]; this
0x1800403e5  call    ??1AppXSyncActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::AppXSyncActivity::~AppXSyncActivity(void)
0x1800403ea  mov     eax, ebx
0x1800403ec  mov     rcx, [rsp+1A8h+var_18]
0x1800403f4  xor     rcx, rsp; StackCookie
0x1800403f7  call    __security_check_cookie
0x1800403fc  mov     rbx, [rsp+1A8h+arg_8]
0x180040404  add     rsp, 1A0h
0x18004040b  pop     rdi
0x18004040c  retn
```
