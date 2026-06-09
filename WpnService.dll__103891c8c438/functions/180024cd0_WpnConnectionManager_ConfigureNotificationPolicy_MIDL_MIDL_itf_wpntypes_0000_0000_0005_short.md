# WpnConnectionManager::ConfigureNotificationPolicy(__MIDL___MIDL_itf_wpntypes_0000_0000_0005,short)

- ea: `0x180024cd0`
- end: `0x180024df5`
- name: `?ConfigureNotificationPolicy@WpnConnectionManager@@UEAAJW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@F@Z`
- size: `293`
- prototype: `__int64 __fastcall(WpnConnectionManager *, unsigned int, unsigned __int16)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180007e20`
- `0x18000a2a0`
- `0x18000abc0`
- `0x1800202bc`
- `0x180021048`
- `0x180024cd0`
- `0x180024dfc`
- `0x180024e28`
- `0x180026200`
- `0x18002e8c0`

## string_xrefs

- `0x180024cf6`: `WnsCMConfigureNotificationPolicy`

## pseudocode

```c
__int64 __fastcall WpnConnectionManager::ConfigureNotificationPolicy(
        WpnConnectionManager *a1,
        unsigned int a2,
        unsigned __int16 a3)
{
  __int64 v6; // rdx
  int v8; // eax
  const char *v9; // r9
  int v10; // [rsp+20h] [rbp-188h]
  unsigned int v11; // [rsp+20h] [rbp-188h]
  _QWORD v12[42]; // [rsp+30h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v12,
    "WnsCMConfigureNotificationPolicy");
  v12[0] = &WnsCPLog::WnsCMConfigureNotificationPolicy::`vftable';
  WnsCPLog::WnsCMConfigureNotificationPolicy::StartActivity(
    (WnsCPLog::WnsCMConfigureNotificationPolicy *)v12,
    *((_QWORD *)a1 + 4),
    a2,
    a3);
  if ( a2 - 1 > 4 )
  {
    v6 = 221;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\wpnconnectionmanager.cpp",
      (const char *)0x80070057LL,
      v10);
    WnsCPLog::WnsCMConfigureNotificationPolicy::~WnsCMConfigureNotificationPolicy((WnsCPLog::WnsCMConfigureNotificationPolicy *)v12);
    return 2147942487LL;
  }
  if ( (unsigned __int16)(a3 + 1) > 1u )
  {
    v6 = 222;
    goto LABEL_3;
  }
  try
  {
    v8 = WpnConnectionManager::VerifyCallerUserId(a1);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\wpnconnectionmanager.cpp",
        (const char *)(unsigned int)v8,
        v10);
    Wns::ConnectionStateMachine::ConfigureNotificationPolicy(*((_QWORD *)a1 + 3) + 40LL, *((_QWORD *)a1 + 6), a2, a3);
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12, 0);
  }
  catch ( ... )
  {
    v11 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0xE8,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\wpnconnectionmanager.cpp",
            v9);
    WnsCPLog::WnsCMConfigureNotificationPolicy::~WnsCMConfigureNotificationPolicy((WnsCPLog::WnsCMConfigureNotificationPolicy *)v12);
    return v11;
  }
  WnsCPLog::WnsCMConfigureNotificationPolicy::~WnsCMConfigureNotificationPolicy((WnsCPLog::WnsCMConfigureNotificationPolicy *)v12);
  return 0;
}

```

## disassembly

```asm
0x180024cd0  push    rbx
0x180024cd2  push    rsi
0x180024cd3  push    rdi
0x180024cd4  sub     rsp, 190h
0x180024cdb  mov     rax, cs:__security_cookie
0x180024ce2  xor     rax, rsp
0x180024ce5  mov     [rsp+1A8h+var_28], rax
0x180024ced  movzx   edi, r8w
0x180024cf1  mov     esi, edx
0x180024cf3  mov     rbx, rcx
0x180024cf6  lea     rdx, aWnscmconfigure_1; "WnsCMConfigureNotificationPolicy"
0x180024cfd  lea     rcx, [rsp+1A8h+var_178]
0x180024d02  call    ??0?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180024d07  lea     rcx, ??_7WnsCMConfigureNotificationPolicy@WnsCPLog@@6B@; const WnsCPLog::WnsCMConfigureNotificationPolicy::`vftable'
0x180024d0e  mov     [rsp+1A8h+var_178], rcx
0x180024d13  movzx   r9d, di; __int16
0x180024d17  mov     r8d, esi; unsigned int
0x180024d1a  mov     rdx, [rbx+20h]; unsigned __int64
0x180024d1e  lea     rcx, [rsp+1A8h+var_178]; this
0x180024d23  call    ?StartActivity@WnsCMConfigureNotificationPolicy@WnsCPLog@@QEAAX_KIF@Z; WnsCPLog::WnsCMConfigureNotificationPolicy::StartActivity(unsigned __int64,uint,short)
0x180024d28  nop
0x180024d29  lea     eax, [rsi-1]
0x180024d2c  cmp     eax, 4
0x180024d2f  jbe     short loc_180024D61
0x180024d31  mov     edx, 0DDh; void *
0x180024d36  mov     ebx, 80070057h
0x180024d3b  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180024d42  mov     r9d, ebx; char *
0x180024d45  mov     rcx, [rsp+1A8h]; this
0x180024d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024d52  nop
0x180024d53  lea     rcx, [rsp+1A8h+var_178]; this
0x180024d58  call    ??1WnsCMConfigureNotificationPolicy@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsCMConfigureNotificationPolicy::~WnsCMConfigureNotificationPolicy(void)
0x180024d5d  mov     eax, ebx
0x180024d5f  jmp     short loc_180024DDA
0x180024d61  lea     eax, [rdi+1]
0x180024d64  cmp     ax, 1
0x180024d68  jbe     short loc_180024D71
0x180024d6a  mov     edx, 0DEh
0x180024d6f  jmp     short loc_180024D36
0x180024d71  mov     rcx, rbx; this
0x180024d74  call    ?VerifyCallerUserId@WpnConnectionManager@@AEAAJXZ; WpnConnectionManager::VerifyCallerUserId(void)
0x180024d79  mov     rcx, [rsp+1A8h]; this
0x180024d81  test    eax, eax
0x180024d83  jns     short loc_180024D99
0x180024d85  mov     r9d, eax; char *
0x180024d88  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180024d8f  mov     edx, 0E2h; void *
0x180024d94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024d99  mov     rcx, [rbx+18h]
0x180024d9d  add     rcx, 28h ; '('
0x180024da1  movzx   r9d, di
0x180024da5  mov     r8d, esi
0x180024da8  mov     rdx, [rbx+30h]
0x180024dac  call    ?ConfigureNotificationPolicy@ConnectionStateMachine@Wns@@QEAAX_KW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@F@Z; Wns::ConnectionStateMachine::ConfigureNotificationPolicy(unsigned __int64,__MIDL___MIDL_itf_wpntypes_0000_0000_0005,short)
0x180024db1  xor     edx, edx
0x180024db3  lea     rcx, [rsp+1A8h+var_178]
0x180024db8  call    ?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180024dbd  nop
0x180024dbe  lea     rcx, [rsp+1A8h+var_178]; this
0x180024dc3  call    ??1WnsCMConfigureNotificationPolicy@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsCMConfigureNotificationPolicy::~WnsCMConfigureNotificationPolicy(void)
0x180024dc8  xor     eax, eax
0x180024dca  jmp     short loc_180024DDA
0x180024dcc  lea     rcx, [rsp+1A8h+var_178]; this
0x180024dd1  call    ??1WnsCMConfigureNotificationPolicy@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsCMConfigureNotificationPolicy::~WnsCMConfigureNotificationPolicy(void)
0x180024dd6  mov     eax, [rsp+1A8h+var_188]
0x180024dda  mov     rcx, [rsp+1A8h+var_28]
0x180024de2  xor     rcx, rsp; StackCookie
0x180024de5  call    __security_check_cookie
0x180024dea  add     rsp, 190h
0x180024df1  pop     rdi
0x180024df2  pop     rsi
0x180024df3  pop     rbx
0x180024df4  retn
```
