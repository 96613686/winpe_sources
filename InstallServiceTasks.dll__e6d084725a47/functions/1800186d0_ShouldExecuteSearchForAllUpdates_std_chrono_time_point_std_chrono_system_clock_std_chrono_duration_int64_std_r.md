# ShouldExecuteSearchForAllUpdates(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> *,SearchIntervalDurationsInMs)

- ea: `0x1800186d0`
- end: `0x180018922`
- name: `?ShouldExecuteSearchForAllUpdates@@YA_NPEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@USearchIntervalDurationsInMs@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180018928`
- `0x180018c14`

## callees

- `0x180003450`
- `0x18000c5ac`
- `0x18000d370`
- `0x180012118`
- `0x180012f10`
- `0x180015dbc`
- `0x1800186d0`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180018740`
- `msvcp_win!_Xtime_get_ticks` at `0x180018740`

## string_xrefs

- `0x180018725`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x1800187bc`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x180018835`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x180018893`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x1800188ee`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x180018718`: `ShouldExecuteSearchForAllUpdates`
- `0x1800187af`: `ShouldExecuteSearchForAllUpdates`
- `0x180018828`: `ShouldExecuteSearchForAllUpdates`
- `0x180018886`: `ShouldExecuteSearchForAllUpdates`
- `0x1800188e1`: `ShouldExecuteSearchForAllUpdates`
- `0x1800188cd`: `Last Successful Update seems to be in the future : %s. Not Executing search`

## pseudocode

```c
char __fastcall ShouldExecuteSearchForAllUpdates(unsigned __int16 *a1, __int64 *a2)
{
  __int64 v4; // rcx
  __int64 ticks; // rax
  __int64 v7; // rax
  _DWORD *v8; // rax
  int v9; // r9d
  _DWORD *v10; // rax
  int v11; // r9d
  wchar_t *v12; // rax
  int v13; // [rsp+40h] [rbp-78h]
  __int64 v14; // [rsp+50h] [rbp-68h] BYREF
  char v15[8]; // [rsp+58h] [rbp-60h] BYREF
  char v16[8]; // [rsp+60h] [rbp-58h] BYREF
  wchar_t Buffer[28]; // [rsp+68h] [rbp-50h] BYREF

  if ( !a1 )
  {
    LogSimpleMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
      0x14Du,
      "ShouldExecuteSearchForAllUpdates",
      -1,
      L"Cannot figure out when was the last time we ran",
      0,
      0);
    goto LABEL_3;
  }
  ticks = _Xtime_get_ticks();
  if ( ticks < *(_QWORD *)a1 )
  {
    v12 = time_point_iso8601::time_point_iso8601(Buffer, (__int64)a1);
    LogMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
      0x155u,
      "ShouldExecuteSearchForAllUpdates",
      -1,
      L"Last Successful Update seems to be in the future : %s. Not Executing search",
      0,
      0,
      v12);
  }
  else
  {
    v7 = ticks - *(_QWORD *)a1;
    v14 = v7;
    if ( v7 >= *a2 )
    {
      if ( a2[1] < v7 )
      {
        std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(
          v15,
          a2 + 1);
        v10 = (_DWORD *)std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(
                          v16,
                          &v14);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
          0x169u,
          "ShouldExecuteSearchForAllUpdates",
          -1,
          L"Past Maximum Duration (%u > %u)",
          0,
          0,
          *v10,
          v11,
          v14);
        v4 = 1;
        return CheckNetworkCostForCostPolicyWithLogging(v4);
      }
      v13 = *(_DWORD *)std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(
                         v15,
                         &v14);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
        0x16Du,
        "ShouldExecuteSearchForAllUpdates",
        -1,
        L"Duration since last check %u",
        0,
        0,
        v13);
LABEL_3:
      v4 = 0;
      return CheckNetworkCostForCostPolicyWithLogging(v4);
    }
    std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(v16, a2);
    v8 = (_DWORD *)std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(
                     v15,
                     &v14);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
      0x160u,
      "ShouldExecuteSearchForAllUpdates",
      -1,
      L"Skipping Search. Duration since last check is too short (%u < %u)",
      0,
      0,
      *v8,
      v9,
      v14);
  }
  return 0;
}

```

## disassembly

```asm
0x1800186d0  mov     [rsp+arg_10], rbx
0x1800186d5  push    rdi
0x1800186d6  sub     rsp, 0B0h
0x1800186dd  mov     rax, cs:__security_cookie
0x1800186e4  xor     rax, rsp
0x1800186e7  mov     [rsp+0B8h+var_18], rax
0x1800186ef  mov     rdi, rdx
0x1800186f2  mov     rbx, rcx
0x1800186f5  test    rcx, rcx
0x1800186f8  jnz     short loc_180018740
0x1800186fa  mov     [rsp+0B8h+var_80], rcx; unsigned __int16 *
0x1800186ff  mov     [rsp+0B8h+var_88], rcx; char *
0x180018704  lea     rax, aCannotFigureOu; "Cannot figure out when was the last tim"...
0x18001870b  mov     [rsp+0B8h+var_90], rax; unsigned __int16 *
0x180018710  mov     [rsp+0B8h+var_98], 0FFFFFFFFh; int
0x180018718  lea     r9, aShouldexecutes_2; "ShouldExecuteSearchForAllUpdates"
0x18001871f  mov     r8d, 14Dh; unsigned int
0x180018725  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x18001872c  lea     ecx, [rbx+3]; unsigned int
0x18001872f  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x180018734  xor     ecx, ecx
0x180018736  call    ?CheckNetworkCostForCostPolicyWithLogging@@YA_NW4IANetworkCostPolicy@@@Z; CheckNetworkCostForCostPolicyWithLogging(IANetworkCostPolicy)
0x18001873b  jmp     loc_180018901
0x180018740  call    cs:__imp__Xtime_get_ticks
0x180018746  mov     rcx, [rbx]
0x180018749  cmp     rax, rcx
0x18001874c  jl      loc_1800188A9
0x180018752  sub     rax, rcx
0x180018755  mov     [rsp+0B8h+var_68], rax
0x18001875a  cmp     rax, [rdi]
0x18001875d  jge     short loc_1800187D2
0x18001875f  mov     rdx, rdi
0x180018762  lea     rcx, [rsp+0B8h+var_58]
0x180018767  call    ??$duration_cast@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@_JU?$ratio@$00$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x18001876c  mov     r9d, [rax]
0x18001876f  lea     rdx, [rsp+0B8h+var_68]
0x180018774  lea     rcx, [rsp+0B8h+var_60]
0x180018779  call    ??$duration_cast@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@_JU?$ratio@$00$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x18001877e  mov     [rsp+0B8h+var_70], r9d
0x180018783  mov     eax, [rax]
0x180018785  mov     dword ptr [rsp+0B8h+var_78], eax
0x180018789  mov     [rsp+0B8h+var_80], 0; unsigned __int16 *
0x180018792  mov     [rsp+0B8h+var_88], 0; char *
0x18001879b  lea     rax, aSkippingSearch; "Skipping Search. Duration since last ch"...
0x1800187a2  mov     [rsp+0B8h+var_90], rax; unsigned __int16 *
0x1800187a7  mov     [rsp+0B8h+var_98], 0FFFFFFFFh; int
0x1800187af  lea     r9, aShouldexecutes_2; "ShouldExecuteSearchForAllUpdates"
0x1800187b6  mov     r8d, 160h; unsigned int
0x1800187bc  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x1800187c3  mov     ecx, 3; unsigned int
0x1800187c8  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800187cd  jmp     loc_1800188FF
0x1800187d2  lea     rdx, [rdi+8]
0x1800187d6  lea     rcx, [rsp+0B8h+var_60]
0x1800187db  cmp     [rdx], rax
0x1800187de  jge     short loc_180018850
0x1800187e0  call    ??$duration_cast@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@_JU?$ratio@$00$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x1800187e5  mov     r9d, [rax]
0x1800187e8  lea     rdx, [rsp+0B8h+var_68]
0x1800187ed  lea     rcx, [rsp+0B8h+var_58]
0x1800187f2  call    ??$duration_cast@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@_JU?$ratio@$00$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x1800187f7  mov     [rsp+0B8h+var_70], r9d
0x1800187fc  mov     eax, [rax]
0x1800187fe  mov     dword ptr [rsp+0B8h+var_78], eax
0x180018802  mov     [rsp+0B8h+var_80], 0; unsigned __int16 *
0x18001880b  mov     [rsp+0B8h+var_88], 0; char *
0x180018814  lea     rax, aPastMaximumDur; "Past Maximum Duration (%u > %u)"
0x18001881b  mov     [rsp+0B8h+var_90], rax; unsigned __int16 *
0x180018820  mov     [rsp+0B8h+var_98], 0FFFFFFFFh; int
0x180018828  lea     r9, aShouldexecutes_2; "ShouldExecuteSearchForAllUpdates"
0x18001882f  mov     r8d, 169h; unsigned int
0x180018835  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x18001883c  mov     ecx, 3; unsigned int
0x180018841  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180018846  mov     ecx, 1
0x18001884b  jmp     loc_180018736
0x180018850  lea     rdx, [rsp+0B8h+var_68]
0x180018855  call    ??$duration_cast@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@_JU?$ratio@$00$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x18001885a  mov     ecx, [rax]
0x18001885c  mov     dword ptr [rsp+0B8h+var_78], ecx
0x180018860  mov     [rsp+0B8h+var_80], 0; unsigned __int16 *
0x180018869  mov     [rsp+0B8h+var_88], 0; char *
0x180018872  lea     rax, aDurationSinceL; "Duration since last check %u"
0x180018879  mov     [rsp+0B8h+var_90], rax; unsigned __int16 *
0x18001887e  mov     [rsp+0B8h+var_98], 0FFFFFFFFh; int
0x180018886  lea     r9, aShouldexecutes_2; "ShouldExecuteSearchForAllUpdates"
0x18001888d  mov     r8d, 16Dh; unsigned int
0x180018893  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x18001889a  mov     ecx, 3; unsigned int
0x18001889f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800188a4  jmp     loc_180018734
0x1800188a9  mov     rdx, rbx
0x1800188ac  lea     rcx, [rsp+0B8h+Buffer]; Buffer
0x1800188b1  call    ??0time_point_iso8601@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; time_point_iso8601::time_point_iso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800188b6  mov     [rsp+0B8h+var_78], rax
0x1800188bb  mov     [rsp+0B8h+var_80], 0; unsigned __int16 *
0x1800188c4  mov     [rsp+0B8h+var_88], 0; char *
0x1800188cd  lea     rax, aLastSuccessful; "Last Successful Update seems to be in t"...
0x1800188d4  mov     [rsp+0B8h+var_90], rax; unsigned __int16 *
0x1800188d9  mov     [rsp+0B8h+var_98], 0FFFFFFFFh; int
0x1800188e1  lea     r9, aShouldexecutes_2; "ShouldExecuteSearchForAllUpdates"
0x1800188e8  mov     r8d, 155h; unsigned int
0x1800188ee  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x1800188f5  mov     ecx, 2; unsigned int
0x1800188fa  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800188ff  xor     al, al
0x180018901  mov     rcx, [rsp+0B8h+var_18]
0x180018909  xor     rcx, rsp; StackCookie
0x18001890c  call    __security_check_cookie
0x180018911  mov     rbx, [rsp+0B8h+arg_10]
0x180018919  add     rsp, 0B0h
0x180018920  pop     rdi
0x180018921  retn
```
