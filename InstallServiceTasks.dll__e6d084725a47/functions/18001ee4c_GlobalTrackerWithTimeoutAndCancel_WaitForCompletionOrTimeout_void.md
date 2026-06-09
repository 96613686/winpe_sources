# GlobalTrackerWithTimeoutAndCancel::_WaitForCompletionOrTimeout(void)

- ea: `0x18001ee4c`
- end: `0x18001ef4b`
- name: `?_WaitForCompletionOrTimeout@GlobalTrackerWithTimeoutAndCancel@@QEAAXXZ`
- size: `255`
- prototype: `void __fastcall(GlobalTrackerWithTimeoutAndCancel *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001bdbc`

## callees

- `0x1800067d8`
- `0x18000c5ac`
- `0x18000fd08`
- `0x180012f10`
- `0x180019c50`
- `0x18001ee4c`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18001ee76`
- `msvcp_win!_Xtime_get_ticks` at `0x18001ee76`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001ee65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001ef31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001ee65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001ef31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001eeb0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001eeb0`

## string_xrefs

- `0x18001eed4`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001eec7`: `GlobalTrackerWithTimeoutAndCancel::_WaitForCompletionOrTimeout`

## pseudocode

```c
void __fastcall GlobalTrackerWithTimeoutAndCancel::_WaitForCompletionOrTimeout(GlobalTrackerWithTimeoutAndCancel *this)
{
  void *v2; // rdi
  DWORD v3; // eax
  unsigned int v4; // r8d
  const char *v5; // r9
  _QWORD *v6; // rax
  __int64 v7; // r9
  void *v8; // rdx
  int v9; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF
  char v12; // [rsp+68h] [rbp+10h] BYREF

  while ( 1 )
  {
    v2 = (void *)*((_QWORD *)this + 4);
    v3 = WaitForSingleObjectEx(v2, 0, 0);
    if ( v3 != 258 )
      break;
    v11 = _Xtime_get_ticks() - *((_QWORD *)this + 3);
    v6 = (_QWORD *)std::chrono::duration<__int64,std::ratio<1,10000000>>::duration<__int64,std::ratio<1,10000000>>(
                     &v12,
                     (char *)this + 16);
    if ( *v6 < v7 )
    {
      v9 = *(_DWORD *)std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(
                        &v12,
                        &v11);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
        0x8Bu,
        "GlobalTrackerWithTimeoutAndCancel::_WaitForCompletionOrTimeout",
        -1,
        L"No one pinged for %d seconds. Timing out due to inactivity",
        0,
        0,
        v9);
      wil::details::SetEvent(*((wil::details **)this + 4), v8);
      return;
    }
    WaitForSingleObject(*((HANDLE *)this + 4), *((_QWORD *)this + 2) / 2LL);
  }
  if ( v3 || WaitForSingleObjectEx(v2, 0, 0) )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB07, v4, v5);
}

```

## disassembly

```asm
0x18001ee4c  mov     [rsp+arg_10], rbx
0x18001ee51  push    rdi
0x18001ee52  sub     rsp, 50h
0x18001ee56  mov     rbx, rcx
0x18001ee59  mov     rdi, [rbx+20h]
0x18001ee5d  xor     r8d, r8d; bAlertable
0x18001ee60  mov     rcx, rdi; hHandle
0x18001ee63  xor     edx, edx; dwMilliseconds
0x18001ee65  call    cs:__imp_WaitForSingleObjectEx
0x18001ee6b  cmp     eax, 102h
0x18001ee70  jnz     loc_18001EF25
0x18001ee76  call    cs:__imp__Xtime_get_ticks
0x18001ee7c  mov     r9, rax
0x18001ee7f  lea     rdx, [rbx+10h]
0x18001ee83  sub     r9, [rbx+18h]
0x18001ee87  lea     rcx, [rsp+58h+arg_8]
0x18001ee8c  mov     [rsp+58h+arg_0], r9
0x18001ee91  call    ??$?0_JU?$ratio@$00$0DOI@@std@@$0A@@?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@QEAA@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@12@@Z; std::chrono::duration<__int64,std::ratio<1,10000000>>::duration<__int64,std::ratio<1,10000000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x18001ee96  cmp     [rax], r9
0x18001ee99  jl      short loc_18001EEB8
0x18001ee9b  mov     rax, [rbx+10h]
0x18001ee9f  mov     ecx, 2
0x18001eea4  cqo
0x18001eea6  idiv    rcx
0x18001eea9  mov     rcx, [rbx+20h]; hHandle
0x18001eead  mov     rdx, rax; dwMilliseconds
0x18001eeb0  call    cs:__imp_WaitForSingleObject
0x18001eeb6  jmp     short loc_18001EE59
0x18001eeb8  lea     rdx, [rsp+58h+arg_0]
0x18001eebd  lea     rcx, [rsp+58h+arg_8]
0x18001eec2  call    ??$duration_cast@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@_JU?$ratio@$00$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x18001eec7  lea     r9, aGlobaltrackerw; "GlobalTrackerWithTimeoutAndCancel::_Wai"...
0x18001eece  mov     r8d, 8Bh; unsigned int
0x18001eed4  lea     rdx, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001eedb  mov     ecx, [rax]
0x18001eedd  lea     rax, aNoOnePingedFor; "No one pinged for %d seconds. Timing ou"...
0x18001eee4  mov     [rsp+58h+var_18], ecx
0x18001eee8  mov     ecx, 3; unsigned int
0x18001eeed  mov     [rsp+58h+var_20], 0; unsigned __int16 *
0x18001eef6  mov     [rsp+58h+var_28], 0; char *
0x18001eeff  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x18001ef04  mov     [rsp+58h+var_38], 0FFFFFFFFh; int
0x18001ef0c  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18001ef11  mov     rcx, [rbx+20h]; this
0x18001ef15  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18001ef1a  mov     rbx, [rsp+58h+arg_10]
0x18001ef1f  add     rsp, 50h
0x18001ef23  pop     rdi
0x18001ef24  retn
0x18001ef25  test    eax, eax
0x18001ef27  jnz     short loc_18001EF3B
0x18001ef29  xor     r8d, r8d; bAlertable
0x18001ef2c  xor     edx, edx; dwMilliseconds
0x18001ef2e  mov     rcx, rdi; hHandle
0x18001ef31  call    cs:__imp_WaitForSingleObjectEx
0x18001ef37  test    eax, eax
0x18001ef39  jz      short loc_18001EF1A
0x18001ef3b  mov     rcx, [rsp+58h]; this
0x18001ef40  mov     edx, 0B07h; void *
0x18001ef45  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
