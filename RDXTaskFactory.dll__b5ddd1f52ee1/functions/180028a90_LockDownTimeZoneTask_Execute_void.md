# LockDownTimeZoneTask::Execute(void)

- ea: `0x180028a90`
- end: `0x180028acb`
- name: `?Execute@LockDownTimeZoneTask@@MEAAXXZ`
- size: `59`
- prototype: `void __fastcall(LockDownTimeZoneTask *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18001094c`
- `0x180028a90`
- `0x180028c40`

## import_xrefs

- `tzautoupdate!EnableTimeZoneAutoUpdate` at `0x180028aa2`
- `tzautoupdate!EnableTimeZoneAutoUpdate` at `0x180028aa2`

## string_xrefs

- `0x180028ab1`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdowntimezonetask.cpp`

## pseudocode

```c
void __fastcall LockDownTimeZoneTask::Execute(LockDownTimeZoneTask *this, __int64 a2)
{
  int v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_TimedShutdown>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RDX_TimedShutdown>::GetImpl'::`2'::impl,
    a2);
  v2 = EnableTimeZoneAutoUpdate();
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdowntimezonetask.cpp",
      (const char *)(unsigned int)v2,
      v3);
}

```

## disassembly

```asm
0x180028a90  sub     rsp, 28h
0x180028a94  mov     dl, 1
0x180028a96  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_TimedShutdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_TimedShutdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_TimedShutdown> `wil::Feature<__WilFeatureTraits_Feature_RDX_TimedShutdown>::GetImpl(void)'::`2'::impl
0x180028a9d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_TimedShutdown@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_TimedShutdown>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180028aa2  call    cs:__imp_EnableTimeZoneAutoUpdate
0x180028aa8  test    eax, eax
0x180028aaa  jns     short loc_180028AC6
0x180028aac  mov     rcx, [rsp+28h]; this
0x180028ab1  lea     r8, aPcshellShellRe_0; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180028ab8  mov     r9d, eax; char *
0x180028abb  mov     edx, 23h ; '#'; void *
0x180028ac0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028ac6  add     rsp, 28h
0x180028aca  retn
```
