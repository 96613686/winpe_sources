# StateRepository::Globals::GetAppRepositoryPath(Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)

- ea: `0x1800236c4`
- end: `0x1800237b3`
- name: `?GetAppRepositoryPath@Globals@StateRepository@@YAJAEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800232c8`

## callees

- `0x18000a3c0`
- `0x18000c584`
- `0x18000d9a4`
- `0x1800136ec`
- `0x1800236c4`
- `0x18002393c`
- `0x18002bca4`

## string_xrefs

- `0x180023748`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180023782`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180023769`: `Required configuration data not found: %ws`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::GetAppRepositoryPath(
        const struct Common::StateSeparationRedirectionMapping *a1,
        __int64 a2,
        void *a3,
        unsigned __int16 *a4)
{
  int RegKeyContainingValue; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int Setting; // eax
  bool v10; // [rsp+20h] [rbp-18h]
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY v13; // [rsp+48h] [rbp+10h] BYREF
  const unsigned __int16 *v14; // [rsp+50h] [rbp+18h] BYREF

  v13 = 0;
  v14 = 0;
  RegKeyContainingValue = Common::StateSeparation::GetRegKeyContainingValue(a1, &v14, a3, a4, v10, &v13);
  v7 = RegKeyContainingValue;
  if ( RegKeyContainingValue >= 0 )
  {
    Setting = StateRepository::Globals::GetSetting((Common::RegistryKey *)&v13, L"PackageRepositoryRoot", 0);
    v7 = Setting;
    if ( Setting >= 0 )
    {
      if ( *(_QWORD *)a1 )
      {
        v7 = 0;
      }
      else
      {
        v7 = -2147023286;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x5C4,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
          (const char *)0x8007064ALL,
          (int)"Required configuration data not found: %ws",
          (const char *)L"PackageRepositoryRoot");
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C3,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)Setting,
        v11);
    }
  }
  else if ( (Microsoft_Windows_StateRepositoryEnableBits & 1) != 0 )
  {
    McTemplateU0dz_EventWriteTransfer(
      v6,
      OpenSettingsError,
      (unsigned int)RegKeyContainingValue,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx");
  }
  Common::AutoHandleCloseHKEY<HKEY__ *>(v13);
  return v7;
}

```

## disassembly

```asm
0x1800236c4  mov     r11, rsp
0x1800236c7  mov     [r11+8], rbx
0x1800236cb  mov     [r11+20h], rbp
0x1800236cf  push    rdi
0x1800236d0  sub     rsp, 30h
0x1800236d4  lea     rax, [r11+10h]
0x1800236d8  mov     qword ptr [r11+10h], 0
0x1800236e0  lea     rdx, [r11+18h]; unsigned __int16 **
0x1800236e4  mov     [r11-10h], rax
0x1800236e8  mov     rdi, rcx
0x1800236eb  mov     qword ptr [r11+18h], 0
0x1800236f3  call    ?GetRegKeyContainingValue@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEBGKPEAVRegistryKey@2@@Z; Common::StateSeparation::GetRegKeyContainingValue(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort const *,ulong,Common::RegistryKey *)
0x1800236f8  mov     ebx, eax
0x1800236fa  test    eax, eax
0x1800236fc  jns     short loc_180023723
0x1800236fe  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 1
0x180023705  jz      loc_180023797
0x18002370b  lea     r9, ?appRepositoryRegistrySubkey@StateRepository@@3QBGB; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180023712  mov     r8d, eax
0x180023715  lea     rdx, OpenSettingsError
0x18002371c  call    McTemplateU0dz_EventWriteTransfer
0x180023721  jmp     short loc_180023797
0x180023723  lea     rbp, ?appRepositoryPath@StateRepository@@3QBGB; "PackageRepositoryRoot"
0x18002372a  mov     r9, rdi
0x18002372d  mov     rdx, rbp; unsigned __int16 *
0x180023730  lea     rcx, [rsp+38h+arg_8]; this
0x180023735  xor     r8d, r8d; unsigned __int16 *
0x180023738  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG1AEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@4@@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,ushort const *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x18002373d  mov     ebx, eax
0x18002373f  test    eax, eax
0x180023741  jns     short loc_18002375E
0x180023743  mov     rcx, [rsp+38h]; this
0x180023748  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x18002374f  mov     r9d, eax; char *
0x180023752  mov     edx, 5C3h; void *
0x180023757  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002375c  jmp     short loc_180023797
0x18002375e  cmp     qword ptr [rdi], 0
0x180023762  jnz     short loc_180023795
0x180023764  mov     rcx, [rsp+38h]; this
0x180023769  lea     rax, aRequiredConfig; "Required configuration data not found: "...
0x180023770  mov     ebx, 8007064Ah
0x180023775  mov     [rsp+38h+var_10], rbp; char *
0x18002377a  mov     r9d, ebx; char *
0x18002377d  mov     qword ptr [rsp+38h+var_18], rax; int
0x180023782  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180023789  mov     edx, 5C4h; void *
0x18002378e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023793  jmp     short loc_180023797
0x180023795  xor     ebx, ebx
0x180023797  mov     rcx, [rsp+38h+arg_8]
0x18002379c  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800237a1  mov     rbp, [rsp+38h+arg_18]
0x1800237a6  mov     eax, ebx
0x1800237a8  mov     rbx, [rsp+38h+arg_0]
0x1800237ad  add     rsp, 30h
0x1800237b1  pop     rdi
0x1800237b2  retn
```
