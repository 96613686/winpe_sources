# AiAppXSync(void *)

- ea: `0x18003e734`
- end: `0x18003e83e`
- name: `?AiAppXSync@@YAJPEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(HANDLE hToken)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003ef30`

## callees

- `0x180018150`
- `0x18001dbf8`
- `0x18003e6a0`
- `0x18003e6dc`
- `0x18003e734`
- `0x18003f020`
- `0x18003f180`
- `0x180042950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003e785`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003e785`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003e804`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003e804`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18003e7d1`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18003e7d1`

## string_xrefs

- `0x18003e79f`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

## pseudocode

```c
__int64 __fastcall AiAppXSync(HANDLE hToken)
{
  int v2; // edi
  BOOL v3; // eax
  const char *v4; // r9
  unsigned int LastError; // ebx
  int v7; // [rsp+30h] [rbp-178h] BYREF
  int v8[3]; // [rsp+34h] [rbp-174h] BYREF
  _QWORD v9[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v9);
  v9[0] = &LUATelemetry::AppXSyncActivity::`vftable';
  LUATelemetry::AppXSyncActivity::StartActivity((LUATelemetry::AppXSyncActivity *)v9);
  v2 = 1;
  v3 = ImpersonateLoggedOnUser(hToken);
  LastError = 0;
  if ( v3 )
  {
    v7 = 0;
    v8[0] = RegisterAppXPackageIfNecessary2(0, L"Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe!App", 0, 0, &v7);
    if ( v8[0] < 0 )
    {
      LUATelemetry::SettingsSyncErrorContext<long &,unsigned short * const &>(v8, off_180046950);
      v2 = 0;
    }
    LUATelemetry::AppXSyncActivity::Stop((LUATelemetry::AppXSyncActivity *)v9, v2);
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
  LUATelemetry::AppXSyncActivity::~AppXSyncActivity((LUATelemetry::AppXSyncActivity *)v9);
  return LastError;
}

```

## disassembly

```asm
0x18003e734  mov     [rsp+arg_8], rbx
0x18003e739  push    rdi
0x18003e73a  sub     rsp, 1A0h
0x18003e741  mov     rax, cs:__security_cookie
0x18003e748  xor     rax, rsp
0x18003e74b  mov     [rsp+1A8h+var_18], rax
0x18003e753  mov     rbx, rcx
0x18003e756  lea     rdx, aAppxsyncactivi; "AppXSyncActivity"
0x18003e75d  lea     rcx, [rsp+1A8h+var_168]; struct wil::details::IFailureCallback *
0x18003e762  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003e767  lea     rax, ??_7AppXSyncActivity@LUATelemetry@@6B@; const LUATelemetry::AppXSyncActivity::`vftable'
0x18003e76e  lea     rcx, [rsp+1A8h+var_168]; this
0x18003e773  mov     [rsp+1A8h+var_168], rax
0x18003e778  call    ?StartActivity@AppXSyncActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::AppXSyncActivity::StartActivity(void)
0x18003e77d  mov     rcx, rbx; hToken
0x18003e780  mov     edi, 1
0x18003e785  call    cs:__imp_ImpersonateLoggedOnUser
0x18003e78c  nop     dword ptr [rax+rax+00h]
0x18003e791  xor     ebx, ebx
0x18003e793  test    eax, eax
0x18003e795  jnz     short loc_18003E7B4
0x18003e797  mov     rcx, [rsp+1A8h]; this
0x18003e79f  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003e7a6  mov     edx, 0F2h; void *
0x18003e7ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e7b0  mov     ebx, eax
0x18003e7b2  jmp     short loc_18003E810
0x18003e7b4  mov     rdx, cs:off_180046950; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x18003e7bb  lea     rax, [rsp+1A8h+var_178]
0x18003e7c0  xor     r9d, r9d
0x18003e7c3  mov     [rsp+1A8h+var_188], rax
0x18003e7c8  xor     r8d, r8d
0x18003e7cb  mov     [rsp+1A8h+var_178], ebx
0x18003e7cf  xor     ecx, ecx
0x18003e7d1  call    cs:__imp_RegisterAppXPackageIfNecessary2
0x18003e7d8  nop     dword ptr [rax+rax+00h]
0x18003e7dd  mov     [rsp+1A8h+var_174], eax
0x18003e7e1  test    eax, eax
0x18003e7e3  jns     short loc_18003E7F8
0x18003e7e5  lea     rdx, off_180046950; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x18003e7ec  lea     rcx, [rsp+1A8h+var_174]
0x18003e7f1  call    ??$SettingsSyncErrorContext@AEAJAEBQEAG@LUATelemetry@@SAXAEAJAEBQEAG@Z; LUATelemetry::SettingsSyncErrorContext<long &,ushort * const &>(long &,ushort * const &)
0x18003e7f6  mov     edi, ebx
0x18003e7f8  mov     edx, edi; int
0x18003e7fa  lea     rcx, [rsp+1A8h+var_168]; this
0x18003e7ff  call    ?Stop@AppXSyncActivity@LUATelemetry@@QEAAXH@Z; LUATelemetry::AppXSyncActivity::Stop(int)
0x18003e804  call    cs:__imp_RevertToSelf
0x18003e80b  nop     dword ptr [rax+rax+00h]
0x18003e810  lea     rcx, [rsp+1A8h+var_168]; this
0x18003e815  call    ??1AppXSyncActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::AppXSyncActivity::~AppXSyncActivity(void)
0x18003e81a  mov     eax, ebx
0x18003e81c  mov     rcx, [rsp+1A8h+var_18]
0x18003e824  xor     rcx, rsp; StackCookie
0x18003e827  call    __security_check_cookie
0x18003e82c  mov     rbx, [rsp+1A8h+arg_8]
0x18003e834  add     rsp, 1A0h
0x18003e83b  pop     rdi
0x18003e83c  retn
```
