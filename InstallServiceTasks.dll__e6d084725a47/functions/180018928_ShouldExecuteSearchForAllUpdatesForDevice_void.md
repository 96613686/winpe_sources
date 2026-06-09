# ShouldExecuteSearchForAllUpdatesForDevice(void)

- ea: `0x180018928`
- end: `0x180018a09`
- name: `?ShouldExecuteSearchForAllUpdatesForDevice@@YA_NXZ`
- size: `225`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180016044`

## callees

- `0x180012118`
- `0x180017060`
- `0x1800176e0`
- `0x1800186d0`
- `0x180018928`
- `0x1800190e0`

## string_xrefs

- `0x18001896c`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x1800189b0`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x18001894b`: `OOBE completion time has lapsed 2 hours for AutoScanForUpdates to run.`
- `0x18001895f`: `ShouldExecuteSearchForAllUpdatesForDevice`
- `0x1800189a3`: `ShouldExecuteSearchForAllUpdatesForDevice`
- `0x18001898f`: `Checking if update scan required for Device`

## pseudocode

```c
char ShouldExecuteSearchForAllUpdatesForDevice(void)
{
  char result; // al
  __int128 *SearchIntervalDurationsForUsers; // rax
  unsigned __int16 *v2; // rcx
  __int128 v3; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v4[24]; // [rsp+50h] [rbp-18h] BYREF
  __int64 v5; // [rsp+70h] [rbp+8h] BYREF

  result = IsOobeTwoHoursTimeLapsed();
  if ( result )
  {
    LogSimpleMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
      0x1AEu,
      "ShouldExecuteSearchForAllUpdatesForDevice",
      -1,
      L"OOBE completion time has lapsed 2 hours for AutoScanForUpdates to run.",
      0,
      0);
    LogSimpleMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
      0x1B0u,
      "ShouldExecuteSearchForAllUpdatesForDevice",
      -1,
      L"Checking if update scan required for Device",
      0,
      0);
    v5 = 0;
    if ( (unsigned __int8)TryGetLastSuccesTime(&v5) )
    {
      SearchIntervalDurationsForUsers = (__int128 *)GetSearchIntervalDurationsForUsers(v4);
      v2 = (unsigned __int16 *)&v5;
    }
    else
    {
      SearchIntervalDurationsForUsers = (__int128 *)GetSearchIntervalDurationsForUsers(v4);
      v2 = 0;
    }
    v3 = *SearchIntervalDurationsForUsers;
    return ShouldExecuteSearchForAllUpdates(v2, (__int64 *)&v3);
  }
  return result;
}

```

## disassembly

```asm
0x180018928  sub     rsp, 68h
0x18001892c  call    ?IsOobeTwoHoursTimeLapsed@@YA_NXZ; IsOobeTwoHoursTimeLapsed(void)
0x180018931  test    al, al
0x180018933  jz      loc_180018A04
0x180018939  mov     [rsp+68h+var_30], 0; unsigned __int16 *
0x180018942  mov     [rsp+68h+var_38], 0; char *
0x18001894b  lea     rax, aOobeCompletion; "OOBE completion time has lapsed 2 hours"...
0x180018952  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180018957  mov     [rsp+68h+var_48], 0FFFFFFFFh; int
0x18001895f  lea     r9, aShouldexecutes; "ShouldExecuteSearchForAllUpdatesForDevi"...
0x180018966  mov     r8d, 1AEh; unsigned int
0x18001896c  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x180018973  mov     ecx, 3; unsigned int
0x180018978  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18001897d  mov     [rsp+68h+var_30], 0; unsigned __int16 *
0x180018986  mov     [rsp+68h+var_38], 0; char *
0x18001898f  lea     rax, aCheckingIfUpda_0; "Checking if update scan required for De"...
0x180018996  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18001899b  mov     [rsp+68h+var_48], 0FFFFFFFFh; int
0x1800189a3  lea     r9, aShouldexecutes; "ShouldExecuteSearchForAllUpdatesForDevi"...
0x1800189aa  mov     r8d, 1B0h; unsigned int
0x1800189b0  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x1800189b7  mov     ecx, 3; unsigned int
0x1800189bc  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800189c1  mov     [rsp+68h+arg_0], 0
0x1800189ca  lea     rcx, [rsp+68h+arg_0]
0x1800189cf  call    ?TryGetLastSuccesTime@@YA_NAEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; TryGetLastSuccesTime(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> &)
0x1800189d4  lea     rcx, [rsp+68h+var_18]
0x1800189d9  test    al, al
0x1800189db  jz      short loc_1800189E9
0x1800189dd  call    ?GetSearchIntervalDurationsForUsers@@YA?AUSearchIntervalDurationsInMs@@XZ; GetSearchIntervalDurationsForUsers(void)
0x1800189e2  lea     rcx, [rsp+68h+arg_0]
0x1800189e7  jmp     short loc_1800189F0
0x1800189e9  call    ?GetSearchIntervalDurationsForUsers@@YA?AUSearchIntervalDurationsInMs@@XZ; GetSearchIntervalDurationsForUsers(void)
0x1800189ee  xor     ecx, ecx; unsigned __int16 *
0x1800189f0  movups  xmm0, xmmword ptr [rax]
0x1800189f3  movdqu  [rsp+68h+var_28], xmm0
0x1800189f9  lea     rdx, [rsp+68h+var_28]
0x1800189fe  call    ?ShouldExecuteSearchForAllUpdates@@YA_NPEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@USearchIntervalDurationsInMs@@@Z; ShouldExecuteSearchForAllUpdates(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> *,SearchIntervalDurationsInMs)
0x180018a03  nop
0x180018a04  add     rsp, 68h
0x180018a08  retn
```
