# ShouldPauseAppUpdates(void)

- ea: `0x180028c50`
- end: `0x180028d76`
- name: `?ShouldPauseAppUpdates@@YA_NXZ`
- size: `294`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180020a1c`

## callees

- `0x180012118`
- `0x180020fe4`
- `0x180028c50`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180028c6f`
- `msvcp_win!_Xtime_get_ticks` at `0x180028c6f`

## string_xrefs

- `0x180028c85`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180028d59`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180028c7e`: `ShouldPauseAppUpdates`
- `0x180028d4c`: `ShouldPauseAppUpdates`
- `0x180028cb5`: `Tampering detected: AutoUpdatePauseEndTime is more than 35 days in the future.`
- `0x180028cfe`: `AutoUpdatePauseEndTime is in the past`
- `0x180028cdb`: `AutoUpdatePauseEndTime is less than 35 days in the future.`
- `0x180028d38`: `Unable to get AutoUpdatePauseEndTime registry value`

## pseudocode

```c
bool ShouldPauseAppUpdates(void)
{
  __int64 ticks; // rax
  bool result; // al
  __int64 v2; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  try
  {
    if ( GetAutoUpdatePauseEndTime((struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *)&v2) )
    {
      ticks = _Xtime_get_ticks();
      if ( ticks >= v2 )
      {
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0xDD2u,
          "ShouldPauseAppUpdates",
          -1,
          L"AutoUpdatePauseEndTime is in the past",
          0,
          0);
        result = 0;
      }
      else if ( ticks + 30240000000000LL >= v2 )
      {
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0xDCCu,
          "ShouldPauseAppUpdates",
          -1,
          L"AutoUpdatePauseEndTime is less than 35 days in the future.",
          0,
          0);
        result = 1;
      }
      else
      {
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0xDC7u,
          "ShouldPauseAppUpdates",
          -1,
          L"Tampering detected: AutoUpdatePauseEndTime is more than 35 days in the future.",
          0,
          0);
        result = 0;
      }
    }
    else
    {
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        0xDD8u,
        "ShouldPauseAppUpdates",
        -1,
        L"Unable to get AutoUpdatePauseEndTime registry value",
        0,
        0);
      result = 0;
    }
  }
  catch ( ... )
  {
    LogSimpleMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0xDDEu,
      "ShouldPauseAppUpdates",
      -1,
      L"ShouldPauseAppUpdates failed with an unknown exception, defaulting to not allow pause",
      0,
      0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180028c50  sub     rsp, 48h
0x180028c54  mov     [rsp+48h+arg_0], 0
0x180028c5d  lea     rcx, [rsp+48h+arg_0]
0x180028c62  call    ?GetAutoUpdatePauseEndTime@@YA_NAEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; GetAutoUpdatePauseEndTime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> &)
0x180028c67  test    al, al
0x180028c69  jz      loc_180028D26
0x180028c6f  call    cs:__imp__Xtime_get_ticks
0x180028c75  mov     [rsp+48h+var_10], 0; unsigned __int16 *
0x180028c7e  lea     r9, aShouldpauseapp_0; "ShouldPauseAppUpdates"
0x180028c85  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180028c8c  mov     [rsp+48h+var_18], 0; char *
0x180028c95  cmp     rax, [rsp+48h+arg_0]
0x180028c9a  jge     short loc_180028CFE
0x180028c9c  mov     rcx, 1B80CC754000h
0x180028ca6  add     rax, rcx
0x180028ca9  mov     ecx, 3; unsigned int
0x180028cae  cmp     rax, [rsp+48h+arg_0]
0x180028cb3  jge     short loc_180028CDB
0x180028cb5  lea     rax, aTamperingDetec; "Tampering detected: AutoUpdatePauseEndT"...
0x180028cbc  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x180028cc1  mov     [rsp+48h+var_28], 0FFFFFFFFh; int
0x180028cc9  mov     r8d, 0DC7h; unsigned int
0x180028ccf  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180028cd4  xor     al, al
0x180028cd6  jmp     loc_180028D70
0x180028cdb  lea     rax, aAutoupdatepaus; "AutoUpdatePauseEndTime is less than 35 "...
0x180028ce2  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x180028ce7  mov     [rsp+48h+var_28], 0FFFFFFFFh; int
0x180028cef  mov     r8d, 0DCCh; unsigned int
0x180028cf5  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180028cfa  mov     al, 1
0x180028cfc  jmp     short loc_180028D70
0x180028cfe  lea     rax, aAutoupdatepaus_2; "AutoUpdatePauseEndTime is in the past"
0x180028d05  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x180028d0a  mov     [rsp+48h+var_28], 0FFFFFFFFh; int
0x180028d12  mov     r8d, 0DD2h; unsigned int
0x180028d18  mov     ecx, 3; unsigned int
0x180028d1d  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180028d22  xor     al, al
0x180028d24  jmp     short loc_180028D70
0x180028d26  mov     [rsp+48h+var_10], 0; unsigned __int16 *
0x180028d2f  mov     [rsp+48h+var_18], 0; char *
0x180028d38  lea     rax, aUnableToGetAut; "Unable to get AutoUpdatePauseEndTime re"...
0x180028d3f  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x180028d44  mov     [rsp+48h+var_28], 0FFFFFFFFh; int
0x180028d4c  lea     r9, aShouldpauseapp_0; "ShouldPauseAppUpdates"
0x180028d53  mov     r8d, 0DD8h; unsigned int
0x180028d59  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180028d60  mov     ecx, 3; unsigned int
0x180028d65  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180028d6a  xor     al, al
0x180028d6c  jmp     short loc_180028D70
0x180028d6e  xor     al, al
0x180028d70  add     rsp, 48h
0x180028d74  retn
```
