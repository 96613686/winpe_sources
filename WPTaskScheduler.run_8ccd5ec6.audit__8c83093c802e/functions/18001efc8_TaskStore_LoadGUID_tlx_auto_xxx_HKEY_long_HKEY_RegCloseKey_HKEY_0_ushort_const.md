# TaskStore::LoadGUID(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &,ushort const *)

- ea: `0x18001efc8`
- end: `0x18001f2aa`
- name: `?LoadGUID@TaskStore@@AEAAJAEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@PEBG@Z`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x18001edf0`

## callees

- `0x180006410`
- `0x180019610`
- `0x18001e818`
- `0x18001e840`
- `0x18001e868`
- `0x18001e890`
- `0x18001e8b8`
- `0x18001ebd0`
- `0x18001efc8`
- `0x18001f9e0`
- `0x1800209f8`
- `0x180020a2c`
- `0x180020a48`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f019`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f019`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f12e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f1d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f12e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f1d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f153`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f16f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f258`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f28b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f153`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f16f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f258`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f28b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001f074`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001f074`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TaskStore::LoadGUID(CScheduleMgr **a1, HKEY *a2, const WCHAR *a3)
{
  HKEY *phkResult; // rax
  LSTATUS v7; // eax
  __int64 v8; // rdx
  signed int v9; // ebx
  __int64 v10; // rdx
  int v11; // ebx
  FILETIME *v12; // rsi
  __int64 v13; // rcx
  FILETIME *v14; // rbx
  LSTATUS v15; // eax
  signed int Schedule; // edi
  FILETIME v18; // rax
  __int64 v19; // rdx
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-38h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-34h] BYREF
  FILETIME *lpFileTime; // [rsp+40h] [rbp-30h] BYREF
  struct _GUID v24; // [rsp+48h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  v24 = 0;
  hKey = 0;
  phkResult = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v7 = RegOpenKeyExW(*a2, a3, 0, 1u, phkResult);
  v9 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v9 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_38;
  }
  lpFileTime = 0;
  dword_180030F30 = 0;
  v11 = anonymous_namespace_::GuardedDecodeKey__TASK_RUNTIME_DATA_(&hKey, v8, &lpFileTime);
  if ( v11 >= 0 )
  {
    SystemTime = 0;
    v12 = lpFileTime;
    FileTimeToSystemTime(lpFileTime, &SystemTime);
    if ( (byte_180030D09 & 0x20) != 0 )
      McTemplateU0jyq_EventWriteTransfer(v13, LoadingLastNextRunTime, &v24, &SystemTime, v11);
  }
  else
  {
    v12 = 0;
  }
  lpFileTime = 0;
  if ( !dword_180030F30 )
  {
    v9 = anonymous_namespace_::GuardedDecodeKey__TASK_SCHEDULE_(&hKey, v10, &lpFileTime);
    if ( v9 >= 0 )
    {
      v14 = lpFileTime;
      goto LABEL_13;
    }
LABEL_38:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v9;
  }
  v9 = anonymous_namespace_::GuardedDecodeKey_Encoderv1::_TASK_SCHEDULE_(&hKey, v10, &lpFileTime);
  if ( v9 < 0 )
    goto LABEL_38;
  v14 = lpFileTime;
  anonymous_namespace_::ConvertTaskScheduleFromV1(lpFileTime, lpFileTime);
  v12[2] = (FILETIME)qword_180030F28;
LABEL_13:
  qword_180030F28 = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v15 = RegQueryValueExW(hKey, L"Enabled", 0, 0, Data, &cbData);
  Schedule = v15;
  if ( v15 != 2 )
  {
    if ( v15 )
    {
      if ( v15 > 0 )
        Schedule = (unsigned __int16)v15 | 0x80070000;
LABEL_17:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)Schedule;
    }
    if ( cbData != 4 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      return 13;
    }
    v14[1].dwLowDateTime &= ~2u;
    v14[1].dwLowDateTime |= *(_DWORD *)Data == 0 ? 2 : 0;
  }
  v18 = v14[9];
  if ( v18 )
  {
    if ( *(_DWORD *)v18.dwLowDateTime == 4 )
    {
      if ( *(_QWORD *)(*(_QWORD *)&v18 + 8LL) )
      {
        lpFileTime = 0;
        cbData = 8;
        if ( !RegQueryValueExW(hKey, L"AdhocState", 0, 0, (LPBYTE)&lpFileTime, &cbData) && cbData == 8 )
          **(_QWORD **)(*(_QWORD *)&v14[9] + 8LL) = lpFileTime;
      }
    }
  }
  Schedule = CScheduleMgr::CreateSchedule(
               *a1,
               (const struct _TASK_SCHEDULE *)v14,
               (const struct _TASK_RUNTIME_DATA *)v12,
               0x80000000);
  v24 = *(struct _GUID *)*(_QWORD *)v14;
  TaskSchedulerFreeRunTime(v12);
  TaskSchedulerFreeSchedule(v14);
  if ( Schedule < 0 )
    goto LABEL_17;
  lpFileTime = 0;
  v9 = anonymous_namespace_::GuardedDecodeKey__TASK_STATISTICS_(&hKey, v19, &lpFileTime);
  if ( v9 != -2147024894 )
  {
    if ( v9 >= 0 )
    {
      v9 = CScheduleMgr::SetStatistics(*a1, &v24, (struct _TASK_STATISTICS *)lpFileTime);
      TaskSchedulerFreeScheduleStatistics(lpFileTime);
    }
    goto LABEL_38;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001efc8  push    rbp
0x18001efca  push    rbx
0x18001efcb  push    rsi
0x18001efcc  push    rdi
0x18001efcd  push    r14
0x18001efcf  mov     rbp, rsp
0x18001efd2  sub     rsp, 70h
0x18001efd6  mov     rax, cs:__security_cookie
0x18001efdd  xor     rax, rsp
0x18001efe0  mov     [rbp+var_8], rax
0x18001efe4  mov     rdi, r8
0x18001efe7  mov     rbx, rdx
0x18001efea  mov     r14, rcx
0x18001efed  xorps   xmm0, xmm0
0x18001eff0  movups  xmmword ptr [rbp+var_28.Data1], xmm0
0x18001eff4  mov     [rbp+hKey], 0
0x18001effc  lea     rcx, [rbp+hKey]
0x18001f000  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f005  mov     [rsp+70h+phkResult], rax; phkResult
0x18001f00a  mov     r9d, 1; samDesired
0x18001f010  xor     r8d, r8d; ulOptions
0x18001f013  mov     rdx, rdi; lpSubKey
0x18001f016  mov     rcx, [rbx]; hKey
0x18001f019  call    cs:__imp_RegOpenKeyExW
0x18001f01f  mov     ebx, eax
0x18001f021  test    eax, eax
0x18001f023  jz      short loc_18001F039
0x18001f025  jle     loc_18001F282
0x18001f02b  movzx   ebx, ax
0x18001f02e  or      ebx, 80070000h
0x18001f034  jmp     loc_18001F282
0x18001f039  mov     [rbp+lpFileTime], 0
0x18001f041  mov     cs:dword_180030F30, 0
0x18001f04b  lea     r8, [rbp+lpFileTime]
0x18001f04f  lea     rcx, [rbp+hKey]
0x18001f053  call    _anonymous_namespace___GuardedDecodeKey__TASK_RUNTIME_DATA_
0x18001f058  mov     ebx, eax
0x18001f05a  test    eax, eax
0x18001f05c  jns     short loc_18001F062
0x18001f05e  xor     esi, esi
0x18001f060  jmp     short loc_18001F09B
0x18001f062  xorps   xmm0, xmm0
0x18001f065  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18001f069  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001f06d  mov     rsi, [rbp+lpFileTime]
0x18001f071  mov     rcx, rsi; lpFileTime
0x18001f074  call    cs:__imp_FileTimeToSystemTime
0x18001f07a  test    cs:byte_180030D09, 20h
0x18001f081  jz      short loc_18001F09B
0x18001f083  mov     dword ptr [rsp+70h+phkResult], ebx
0x18001f087  lea     r9, [rbp+SystemTime]
0x18001f08b  lea     r8, [rbp+var_28]
0x18001f08f  lea     rdx, LoadingLastNextRunTime
0x18001f096  call    McTemplateU0jyq_EventWriteTransfer
0x18001f09b  mov     [rbp+lpFileTime], 0
0x18001f0a3  lea     r8, [rbp+lpFileTime]
0x18001f0a7  lea     rcx, [rbp+hKey]
0x18001f0ab  cmp     cs:dword_180030F30, 0
0x18001f0b2  jnz     short loc_18001F0C9
0x18001f0b4  call    _anonymous_namespace___GuardedDecodeKey__TASK_SCHEDULE_
0x18001f0b9  mov     ebx, eax
0x18001f0bb  test    eax, eax
0x18001f0bd  js      loc_18001F282
0x18001f0c3  mov     rbx, [rbp+lpFileTime]
0x18001f0c7  jmp     short loc_18001F0F2
0x18001f0c9  call    _anonymous_namespace___GuardedDecodeKey_Encoderv1___TASK_SCHEDULE_
0x18001f0ce  mov     ebx, eax
0x18001f0d0  test    eax, eax
0x18001f0d2  js      loc_18001F282
0x18001f0d8  mov     rbx, [rbp+lpFileTime]
0x18001f0dc  mov     rdx, rbx
0x18001f0df  mov     rcx, rbx
0x18001f0e2  call    _anonymous_namespace___ConvertTaskScheduleFromV1
0x18001f0e7  mov     rax, cs:qword_180030F28
0x18001f0ee  mov     [rsi+10h], rax
0x18001f0f2  mov     cs:qword_180030F28, 0
0x18001f0fd  mov     dword ptr [rbp+Data], 0
0x18001f104  mov     [rbp+cbData], 4
0x18001f10b  lea     rax, [rbp+cbData]
0x18001f10f  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001f114  lea     rax, [rbp+Data]
0x18001f118  mov     [rsp+70h+phkResult], rax; lpData
0x18001f11d  xor     r9d, r9d; lpType
0x18001f120  xor     r8d, r8d; lpReserved
0x18001f123  lea     rdx, aEnabled; "Enabled"
0x18001f12a  mov     rcx, [rbp+hKey]; hKey
0x18001f12e  call    cs:__imp_RegQueryValueExW
0x18001f134  mov     edi, eax
0x18001f136  cmp     eax, 2
0x18001f139  jz      short loc_18001F192
0x18001f13b  test    eax, eax
0x18001f13d  jz      short loc_18001F160
0x18001f13f  jle     short loc_18001F14A
0x18001f141  movzx   edi, ax
0x18001f144  or      edi, 80070000h
0x18001f14a  mov     rcx, [rbp+hKey]; hKey
0x18001f14e  test    rcx, rcx
0x18001f151  jz      short loc_18001F159
0x18001f153  call    cs:__imp_RegCloseKey
0x18001f159  mov     eax, edi
0x18001f15b  jmp     loc_18001F293
0x18001f160  cmp     [rbp+cbData], 4
0x18001f164  jz      short loc_18001F17F
0x18001f166  mov     rcx, [rbp+hKey]; hKey
0x18001f16a  test    rcx, rcx
0x18001f16d  jz      short loc_18001F175
0x18001f16f  call    cs:__imp_RegCloseKey
0x18001f175  mov     eax, 0Dh
0x18001f17a  jmp     loc_18001F293
0x18001f17f  and     dword ptr [rbx+8], 0FFFFFFFDh
0x18001f183  mov     eax, dword ptr [rbp+Data]
0x18001f186  neg     eax
0x18001f188  sbb     ecx, ecx
0x18001f18a  not     ecx
0x18001f18c  and     ecx, 2
0x18001f18f  or      [rbx+8], ecx
0x18001f192  mov     rax, [rbx+48h]
0x18001f196  test    rax, rax
0x18001f199  jz      short loc_18001F1F8
0x18001f19b  cmp     dword ptr [rax], 4
0x18001f19e  jnz     short loc_18001F1F8
0x18001f1a0  cmp     qword ptr [rax+8], 0
0x18001f1a5  jz      short loc_18001F1F8
0x18001f1a7  mov     [rbp+lpFileTime], 0
0x18001f1af  mov     [rbp+cbData], 8
0x18001f1b6  lea     rax, [rbp+cbData]
0x18001f1ba  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001f1bf  lea     rax, [rbp+lpFileTime]
0x18001f1c3  mov     [rsp+70h+phkResult], rax; lpData
0x18001f1c8  xor     r9d, r9d; lpType
0x18001f1cb  xor     r8d, r8d; lpReserved
0x18001f1ce  lea     rdx, aAdhocstate; "AdhocState"
0x18001f1d5  mov     rcx, [rbp+hKey]; hKey
0x18001f1d9  call    cs:__imp_RegQueryValueExW
0x18001f1df  test    eax, eax
0x18001f1e1  jnz     short loc_18001F1F8
0x18001f1e3  cmp     [rbp+cbData], 8
0x18001f1e7  jnz     short loc_18001F1F8
0x18001f1e9  mov     rax, [rbx+48h]
0x18001f1ed  mov     rdx, [rax+8]
0x18001f1f1  mov     rax, [rbp+lpFileTime]
0x18001f1f5  mov     [rdx], rax
0x18001f1f8  mov     r9d, 80000000h; unsigned int
0x18001f1fe  mov     r8, rsi; struct _TASK_RUNTIME_DATA *
0x18001f201  mov     rdx, rbx; struct _TASK_SCHEDULE *
0x18001f204  mov     rcx, [r14]; this
0x18001f207  call    ?CreateSchedule@CScheduleMgr@@QEAAJPEBU_TASK_SCHEDULE@@PEBU_TASK_RUNTIME_DATA@@K@Z; CScheduleMgr::CreateSchedule(_TASK_SCHEDULE const *,_TASK_RUNTIME_DATA const *,ulong)
0x18001f20c  mov     edi, eax
0x18001f20e  mov     rdx, [rbx]
0x18001f211  movups  xmm0, xmmword ptr [rdx]
0x18001f214  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x18001f219  mov     rcx, rsi; void *
0x18001f21c  call    TaskSchedulerFreeRunTime
0x18001f221  mov     rcx, rbx
0x18001f224  call    TaskSchedulerFreeSchedule
0x18001f229  test    edi, edi
0x18001f22b  js      loc_18001F14A
0x18001f231  mov     [rbp+lpFileTime], 0
0x18001f239  lea     r8, [rbp+lpFileTime]
0x18001f23d  lea     rcx, [rbp+hKey]
0x18001f241  call    _anonymous_namespace___GuardedDecodeKey__TASK_STATISTICS_
0x18001f246  mov     ebx, eax
0x18001f248  cmp     eax, 80070002h
0x18001f24d  jnz     short loc_18001F262
0x18001f24f  mov     rcx, [rbp+hKey]; hKey
0x18001f253  test    rcx, rcx
0x18001f256  jz      short loc_18001F25E
0x18001f258  call    cs:__imp_RegCloseKey
0x18001f25e  xor     eax, eax
0x18001f260  jmp     short loc_18001F293
0x18001f262  test    ebx, ebx
0x18001f264  js      short loc_18001F282
0x18001f266  mov     r8, [rbp+lpFileTime]; struct _TASK_STATISTICS *
0x18001f26a  lea     rdx, [rbp+var_28]; struct _GUID *
0x18001f26e  mov     rcx, [r14]; this
0x18001f271  call    ?SetStatistics@CScheduleMgr@@QEAAJPEBU_GUID@@PEAU_TASK_STATISTICS@@@Z; CScheduleMgr::SetStatistics(_GUID const *,_TASK_STATISTICS *)
0x18001f276  mov     ebx, eax
0x18001f278  mov     rcx, [rbp+lpFileTime]
0x18001f27c  call    TaskSchedulerFreeScheduleStatistics
0x18001f281  nop
0x18001f282  mov     rcx, [rbp+hKey]; hKey
0x18001f286  test    rcx, rcx
0x18001f289  jz      short loc_18001F291
0x18001f28b  call    cs:__imp_RegCloseKey
0x18001f291  mov     eax, ebx
0x18001f293  mov     rcx, [rbp+var_8]
0x18001f297  xor     rcx, rsp; StackCookie
0x18001f29a  call    __security_check_cookie
0x18001f29f  add     rsp, 70h
0x18001f2a3  pop     r14
0x18001f2a5  pop     rdi
0x18001f2a6  pop     rsi
0x18001f2a7  pop     rbx
0x18001f2a8  pop     rbp
0x18001f2a9  retn
```
