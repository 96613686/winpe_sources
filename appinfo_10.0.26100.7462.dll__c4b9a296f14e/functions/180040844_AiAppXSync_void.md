# AiAppXSync(void *)

- ea: `0x180040844`
- end: `0x18004094e`
- name: `?AiAppXSync@@YAJPEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(HANDLE hToken)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180041040`

## callees

- `0x180018400`
- `0x18001dfd8`
- `0x1800407b0`
- `0x1800407ec`
- `0x180040844`
- `0x180041130`
- `0x180041290`
- `0x180044a20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180040895`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180040895`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040914`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040914`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x1800408e1`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x1800408e1`

## string_xrefs

- `0x1800408af`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

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
      LUATelemetry::SettingsSyncErrorContext<long &,unsigned short * const &>(v7, off_180049980);
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
0x180040844  mov     [rsp+arg_8], rbx
0x180040849  push    rdi
0x18004084a  sub     rsp, 1A0h
0x180040851  mov     rax, cs:__security_cookie
0x180040858  xor     rax, rsp
0x18004085b  mov     [rsp+1A8h+var_18], rax
0x180040863  mov     rbx, rcx
0x180040866  lea     rdx, aAppxsyncactivi; "AppXSyncActivity"
0x18004086d  lea     rcx, [rsp+1A8h+var_168]; struct wil::details::IFailureCallback *
0x180040872  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180040877  lea     rax, ??_7AppXSyncActivity@LUATelemetry@@6B@; const LUATelemetry::AppXSyncActivity::`vftable'
0x18004087e  lea     rcx, [rsp+1A8h+var_168]; this
0x180040883  mov     [rsp+1A8h+var_168], rax
0x180040888  call    ?StartActivity@AppXSyncActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::AppXSyncActivity::StartActivity(void)
0x18004088d  mov     rcx, rbx; hToken
0x180040890  mov     edi, 1
0x180040895  call    cs:__imp_ImpersonateLoggedOnUser
0x18004089c  nop     dword ptr [rax+rax+00h]
0x1800408a1  xor     ebx, ebx
0x1800408a3  test    eax, eax
0x1800408a5  jnz     short loc_1800408C4
0x1800408a7  mov     rcx, [rsp+1A8h]; this
0x1800408af  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x1800408b6  mov     edx, 0F2h; void *
0x1800408bb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800408c0  mov     ebx, eax
0x1800408c2  jmp     short loc_180040920
0x1800408c4  mov     rdx, cs:off_180049980; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x1800408cb  lea     rax, [rsp+1A8h+var_178]
0x1800408d0  xor     r9d, r9d
0x1800408d3  mov     [rsp+1A8h+var_188], rax
0x1800408d8  xor     r8d, r8d
0x1800408db  mov     [rsp+1A8h+var_178], ebx
0x1800408df  xor     ecx, ecx
0x1800408e1  call    cs:__imp_RegisterAppXPackageIfNecessary2
0x1800408e8  nop     dword ptr [rax+rax+00h]
0x1800408ed  mov     [rsp+1A8h+var_174], eax
0x1800408f1  test    eax, eax
0x1800408f3  jns     short loc_180040908
0x1800408f5  lea     rdx, off_180049980; "Microsoft.WindowsFeedbackHub_8wekyb3d8b"...
0x1800408fc  lea     rcx, [rsp+1A8h+var_174]
0x180040901  call    ??$SettingsSyncErrorContext@AEAJAEBQEAG@LUATelemetry@@SAXAEAJAEBQEAG@Z; LUATelemetry::SettingsSyncErrorContext<long &,ushort * const &>(long &,ushort * const &)
0x180040906  mov     edi, ebx
0x180040908  mov     edx, edi; int
0x18004090a  lea     rcx, [rsp+1A8h+var_168]; this
0x18004090f  call    ?Stop@AppXSyncActivity@LUATelemetry@@QEAAXH@Z; LUATelemetry::AppXSyncActivity::Stop(int)
0x180040914  call    cs:__imp_RevertToSelf
0x18004091b  nop     dword ptr [rax+rax+00h]
0x180040920  lea     rcx, [rsp+1A8h+var_168]; this
0x180040925  call    ??1AppXSyncActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::AppXSyncActivity::~AppXSyncActivity(void)
0x18004092a  mov     eax, ebx
0x18004092c  mov     rcx, [rsp+1A8h+var_18]
0x180040934  xor     rcx, rsp; StackCookie
0x180040937  call    __security_check_cookie
0x18004093c  mov     rbx, [rsp+1A8h+arg_8]
0x180040944  add     rsp, 1A0h
0x18004094b  pop     rdi
0x18004094c  retn
```
