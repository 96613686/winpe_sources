# WifiSignal::UpdateState(void)

- ea: `0x18003cea4`
- end: `0x18003cf5d`
- name: `?UpdateState@WifiSignal@@AEAAXXZ`
- size: `185`
- prototype: `void __fastcall(WifiSignal *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18003b798`
- `0x18003cf70`

## callees

- `0x18000a7f8`
- `0x18000b5b0`
- `0x18002d62c`
- `0x18003c128`
- `0x18003cea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cec4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003cec4`
- `wlanapi!WlanFreeMemory` at `0x18003cf41`
- `wlanapi!WlanFreeMemory` at `0x18003cf41`
- `wlanapi!WlanEnumInterfaces` at `0x18003cedd`
- `wlanapi!WlanEnumInterfaces` at `0x18003cedd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WifiSignal::UpdateState(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  DWORD v3; // eax
  int matched; // eax
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v6; // [rsp+38h] [rbp+10h] BYREF

  ppInterfaceList = 0;
  v2 = this + 24;
  AcquireSRWLockExclusive(this + 24);
  v6 = v2;
  v3 = WlanEnumInterfaces(this[22].Ptr, 0, &ppInterfaceList);
  LODWORD(this[23].Ptr) = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_144dc3462c353fa21006ff9a189489cc_Traceguids, v3);
  }
  else
  {
    matched = WifiSignal::MatchProperties(this, ppInterfaceList);
    GenericPlugin::DefaultSignal::SetState((__int64)this, matched);
    if ( ppInterfaceList )
      WlanFreeMemory(ppInterfaceList);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
}

```

## disassembly

```asm
0x18003cea4  mov     [rsp+arg_10], rbx
0x18003cea9  push    rdi
0x18003ceaa  sub     rsp, 20h
0x18003ceae  mov     rdi, rcx
0x18003ceb1  mov     [rsp+28h+ppInterfaceList], 0
0x18003ceba  lea     rbx, [rcx+0C0h]
0x18003cec1  mov     rcx, rbx; SRWLock
0x18003cec4  call    cs:__imp_AcquireSRWLockExclusive
0x18003ceca  mov     [rsp+28h+arg_8], rbx
0x18003cecf  lea     r8, [rsp+28h+ppInterfaceList]; ppInterfaceList
0x18003ced4  xor     edx, edx; pReserved
0x18003ced6  mov     rcx, [rdi+0B0h]; hClientHandle
0x18003cedd  call    cs:__imp_WlanEnumInterfaces
0x18003cee3  mov     [rdi+0B8h], eax
0x18003cee9  test    eax, eax
0x18003ceeb  jz      short loc_18003CF20
0x18003ceed  lea     rdx, WPP_GLOBAL_Control
0x18003cef4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cefb  cmp     rcx, rdx
0x18003cefe  jz      short loc_18003CF48
0x18003cf00  test    byte ptr [rcx+1Ch], 1
0x18003cf04  jz      short loc_18003CF48
0x18003cf06  mov     edx, 0Fh
0x18003cf0b  mov     r9d, eax
0x18003cf0e  lea     r8, WPP_144dc3462c353fa21006ff9a189489cc_Traceguids
0x18003cf15  mov     rcx, [rcx+10h]
0x18003cf19  call    WPP_SF_d
0x18003cf1e  jmp     short loc_18003CF48
0x18003cf20  mov     rdx, [rsp+28h+ppInterfaceList]
0x18003cf25  mov     rcx, rdi
0x18003cf28  call    ?MatchProperties@WifiSignal@@AEAA?AW4NA_RULE_STATE@@QEAU_WLAN_INTERFACE_INFO_LIST@@@Z; WifiSignal::MatchProperties(_WLAN_INTERFACE_INFO_LIST * const)
0x18003cf2d  mov     edx, eax
0x18003cf2f  mov     rcx, rdi
0x18003cf32  call    ?SetState@DefaultSignal@GenericPlugin@@QEAAXW4NA_RULE_STATE@@@Z; GenericPlugin::DefaultSignal::SetState(NA_RULE_STATE)
0x18003cf37  mov     rcx, [rsp+28h+ppInterfaceList]; pMemory
0x18003cf3c  test    rcx, rcx
0x18003cf3f  jz      short loc_18003CF48
0x18003cf41  call    cs:__imp_WlanFreeMemory
0x18003cf47  nop
0x18003cf48  lea     rcx, [rsp+28h+arg_8]
0x18003cf4d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003cf52  mov     rbx, [rsp+28h+arg_10]
0x18003cf57  add     rsp, 20h
0x18003cf5b  pop     rdi
0x18003cf5c  retn
```
