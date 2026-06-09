# CSchedule::SetNextTransitionTimer(TimeValue)

- ea: `0x180004b30`
- end: `0x180004d9e`
- name: `?SetNextTransitionTimer@CSchedule@@AEAAJVTimeValue@@@Z`
- size: `622`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800025b0`
- `0x180003fa0`

## callees

- `0x180004b30`
- `0x180005c30`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004b75`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004b75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004d58`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004d86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004d58`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b8c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004c05`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004c6f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004cb2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004d1c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004c05`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004c6f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004cb2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180004d1c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180004c4f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180004c4f`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180004bec`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180004c99`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180004bec`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180004c99`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x180004cfc`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x180004cfc`

## pseudocode

```c
signed int __fastcall CSchedule::SetNextTransitionTimer(__int64 a1, __int64 *a2)
{
  struct _TP_TIMER *v4; // rcx
  signed int result; // eax
  __int64 v6; // r14
  __int64 v7; // rbx
  DWORD v8; // eax
  DWORD v9; // eax
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-E0h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+28h] [rbp-D8h] BYREF
  SYSTEMTIME UniversalTime; // [rsp+38h] [rbp-C8h] BYREF
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v14; // [rsp+FCh] [rbp-4h]
  SYSTEMTIME v15; // [rsp+100h] [rbp+0h] BYREF
  struct _FILETIME v16; // [rsp+110h] [rbp+10h] BYREF
  struct _FILETIME v17; // [rsp+118h] [rbp+18h]
  __int64 v18; // [rsp+120h] [rbp+20h]
  int v19; // [rsp+128h] [rbp+28h]
  SYSTEMTIME SystemTime; // [rsp+130h] [rbp+30h] BYREF
  struct _FILETIME FileTime; // [rsp+140h] [rbp+40h] BYREF
  struct _FILETIME v22; // [rsp+148h] [rbp+48h]
  __int64 v23; // [rsp+150h] [rbp+50h]
  int v24; // [rsp+158h] [rbp+58h]

  v4 = *(struct _TP_TIMER **)(a1 + 296);
  if ( v4 )
    SetThreadpoolTimer(v4, 0, 0, 0);
  else
    *(_QWORD *)(a1 + 296) = CreateThreadpoolTimer(
                              CScheduleMgr::BaseTimeTransitionsCallback,
                              (PVOID)a1,
                              &ThreadpoolCallBackEnvironment);
  if ( *(_QWORD *)(a1 + 296) )
  {
    TimeInfo::TimeInfo(&TimeZoneInformation);
    v6 = *a2;
    v7 = a2[1];
    if ( (*(_BYTE *)(a1 + 44) & 8) != 0 )
    {
      v8 = GetTimeZoneInformation(&TimeZoneInformation);
      *(_QWORD *)&SystemTime.wYear = v6;
      v14 = v8;
      *(_QWORD *)&SystemTime.wHour = v7;
      if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
      {
        v22 = FileTime;
        v23 = 0;
        v24 = 1;
      }
      UniversalTime = SystemTime;
      LocalTime = 0;
      SystemTimeToTzSpecificLocalTime(&TimeZoneInformation, &UniversalTime, &LocalTime);
      v15 = LocalTime;
      if ( SystemTimeToFileTime(&v15, &v16) )
      {
        v17 = v16;
        v18 = 0;
        v19 = 1;
      }
    }
    else
    {
      v9 = GetTimeZoneInformation(&TimeZoneInformation);
      *(_QWORD *)&v15.wYear = v6;
      v14 = v9;
      *(_QWORD *)&v15.wHour = v7;
      if ( SystemTimeToFileTime(&v15, &v16) )
      {
        v17 = v16;
        v18 = 0;
        v19 = 1;
      }
      UniversalTime = v15;
      LocalTime = 0;
      TzSpecificLocalTimeToSystemTime(&TimeZoneInformation, &UniversalTime, &LocalTime);
      SystemTime = LocalTime;
      if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
      {
        v22 = FileTime;
        v23 = 0;
        v24 = 1;
      }
    }
    pftDueTime = FileTime;
    SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 296), &pftDueTime, 0, 0);
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180004b30  push    rbp
0x180004b32  push    rbx
0x180004b33  push    rdi
0x180004b34  lea     rbp, [rsp-70h]
0x180004b39  sub     rsp, 170h
0x180004b40  mov     rax, cs:__security_cookie
0x180004b47  xor     rax, rsp
0x180004b4a  mov     [rbp+80h+var_20], rax
0x180004b4e  mov     rdi, rcx
0x180004b51  mov     rbx, rdx
0x180004b54  mov     rcx, [rcx+128h]; pti
0x180004b5b  test    rcx, rcx
0x180004b5e  jnz     loc_180004D7E
0x180004b64  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180004b6b  mov     rdx, rdi; pv
0x180004b6e  lea     rcx, ?BaseTimeTransitionsCallback@CScheduleMgr@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004b75  call    cs:__imp_CreateThreadpoolTimer
0x180004b7b  mov     [rdi+128h], rax
0x180004b82  cmp     qword ptr [rdi+128h], 0
0x180004b8a  jnz     short loc_180004BB1
0x180004b8c  call    cs:__imp_GetLastError
0x180004b92  test    eax, eax
0x180004b94  jg      loc_180004D91
0x180004b9a  mov     rcx, [rbp+80h+var_20]
0x180004b9e  xor     rcx, rsp; StackCookie
0x180004ba1  call    __security_check_cookie
0x180004ba6  add     rsp, 170h
0x180004bad  pop     rdi
0x180004bae  pop     rbx
0x180004baf  pop     rbp
0x180004bb0  retn
0x180004bb1  mov     [rsp+180h+arg_8], rsi
0x180004bb9  lea     rcx, [rsp+180h+TimeZoneInformation]; lpTimeZoneInformation
0x180004bbe  mov     [rsp+180h+arg_10], r14
0x180004bc6  mov     [rsp+180h+arg_18], r15
0x180004bce  xor     r15d, r15d
0x180004bd1  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x180004bd6  test    byte ptr [rdi+2Ch], 8
0x180004bda  lea     rcx, [rsp+180h+TimeZoneInformation]; lpTimeZoneInformation
0x180004bdf  mov     r14, [rbx]
0x180004be2  mov     rbx, [rbx+8]
0x180004be6  jz      loc_180004C99
0x180004bec  call    cs:__imp_GetTimeZoneInformation
0x180004bf2  lea     rdx, [rbp+80h+FileTime]; lpFileTime
0x180004bf6  mov     qword ptr [rbp+80h+SystemTime.wYear], r14
0x180004bfa  lea     rcx, [rbp+80h+SystemTime]; lpSystemTime
0x180004bfe  mov     [rbp+80h+var_84], eax
0x180004c01  mov     qword ptr [rbp+80h+SystemTime.wHour], rbx
0x180004c05  call    cs:__imp_SystemTimeToFileTime
0x180004c0b  test    eax, eax
0x180004c0d  jz      short loc_180004C26
0x180004c0f  mov     eax, [rbp+80h+FileTime.dwHighDateTime]
0x180004c12  mov     dword ptr [rbp+80h+var_38+4], eax
0x180004c15  mov     eax, [rbp+80h+FileTime.dwLowDateTime]
0x180004c18  mov     dword ptr [rbp+80h+var_38], eax
0x180004c1b  mov     [rbp+80h+var_30], r15
0x180004c1f  mov     [rbp+80h+var_28], 1
0x180004c26  mov     rax, qword ptr [rbp+80h+SystemTime.wYear]
0x180004c2a  lea     r8, [rsp+180h+LocalTime]; lpLocalTime
0x180004c2f  mov     qword ptr [rsp+180h+UniversalTime.wYear], rax
0x180004c34  lea     rdx, [rsp+180h+UniversalTime]; lpUniversalTime
0x180004c39  mov     rax, qword ptr [rbp+80h+SystemTime.wHour]
0x180004c3d  lea     rcx, [rsp+180h+TimeZoneInformation]; lpTimeZoneInformation
0x180004c42  xorps   xmm0, xmm0
0x180004c45  mov     qword ptr [rsp+180h+UniversalTime.wHour], rax
0x180004c4a  movups  xmmword ptr [rsp+180h+LocalTime.wYear], xmm0
0x180004c4f  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180004c55  mov     rax, qword ptr [rsp+180h+LocalTime.wYear]
0x180004c5a  lea     rdx, [rbp+80h+var_70]; lpFileTime
0x180004c5e  mov     qword ptr [rbp+80h+var_80.wYear], rax
0x180004c62  lea     rcx, [rbp+80h+var_80]; lpSystemTime
0x180004c66  mov     rax, qword ptr [rsp+180h+LocalTime.wHour]
0x180004c6b  mov     qword ptr [rbp+80h+var_80.wHour], rax
0x180004c6f  call    cs:__imp_SystemTimeToFileTime
0x180004c75  test    eax, eax
0x180004c77  jz      loc_180004D3D
0x180004c7d  mov     eax, [rbp+80h+var_70.dwHighDateTime]
0x180004c80  mov     dword ptr [rbp+80h+var_68+4], eax
0x180004c83  mov     eax, [rbp+80h+var_70.dwLowDateTime]
0x180004c86  mov     dword ptr [rbp+80h+var_68], eax
0x180004c89  mov     [rbp+80h+var_60], r15
0x180004c8d  mov     [rbp+80h+var_58], 1
0x180004c94  jmp     loc_180004D3D
0x180004c99  call    cs:__imp_GetTimeZoneInformation
0x180004c9f  lea     rdx, [rbp+80h+var_70]; lpFileTime
0x180004ca3  mov     qword ptr [rbp+80h+var_80.wYear], r14
0x180004ca7  lea     rcx, [rbp+80h+var_80]; lpSystemTime
0x180004cab  mov     [rbp+80h+var_84], eax
0x180004cae  mov     qword ptr [rbp+80h+var_80.wHour], rbx
0x180004cb2  call    cs:__imp_SystemTimeToFileTime
0x180004cb8  test    eax, eax
0x180004cba  jz      short loc_180004CD3
0x180004cbc  mov     eax, [rbp+80h+var_70.dwHighDateTime]
0x180004cbf  mov     dword ptr [rbp+80h+var_68+4], eax
0x180004cc2  mov     eax, [rbp+80h+var_70.dwLowDateTime]
0x180004cc5  mov     dword ptr [rbp+80h+var_68], eax
0x180004cc8  mov     [rbp+80h+var_60], r15
0x180004ccc  mov     [rbp+80h+var_58], 1
0x180004cd3  mov     rax, qword ptr [rbp+80h+var_80.wYear]
0x180004cd7  lea     r8, [rsp+180h+LocalTime]; lpUniversalTime
0x180004cdc  mov     qword ptr [rsp+180h+UniversalTime.wYear], rax
0x180004ce1  lea     rdx, [rsp+180h+UniversalTime]; lpLocalTime
0x180004ce6  mov     rax, qword ptr [rbp+80h+var_80.wHour]
0x180004cea  lea     rcx, [rsp+180h+TimeZoneInformation]; lpTimeZoneInformation
0x180004cef  xorps   xmm0, xmm0
0x180004cf2  mov     qword ptr [rsp+180h+UniversalTime.wHour], rax
0x180004cf7  movups  xmmword ptr [rsp+180h+LocalTime.wYear], xmm0
0x180004cfc  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x180004d02  mov     rax, qword ptr [rsp+180h+LocalTime.wYear]
0x180004d07  lea     rdx, [rbp+80h+FileTime]; lpFileTime
0x180004d0b  mov     qword ptr [rbp+80h+SystemTime.wYear], rax
0x180004d0f  lea     rcx, [rbp+80h+SystemTime]; lpSystemTime
0x180004d13  mov     rax, qword ptr [rsp+180h+LocalTime.wHour]
0x180004d18  mov     qword ptr [rbp+80h+SystemTime.wHour], rax
0x180004d1c  call    cs:__imp_SystemTimeToFileTime
0x180004d22  test    eax, eax
0x180004d24  jz      short loc_180004D3D
0x180004d26  mov     eax, [rbp+80h+FileTime.dwHighDateTime]
0x180004d29  mov     ecx, [rbp+80h+FileTime.dwLowDateTime]
0x180004d2c  mov     dword ptr [rbp+80h+var_38+4], eax
0x180004d2f  mov     dword ptr [rbp+80h+var_38], ecx
0x180004d32  mov     [rbp+80h+var_30], r15
0x180004d36  mov     [rbp+80h+var_28], 1
0x180004d3d  mov     rcx, qword ptr [rbp+80h+FileTime.dwLowDateTime]
0x180004d41  lea     rdx, [rsp+180h+pftDueTime]; pftDueTime
0x180004d46  mov     qword ptr [rsp+180h+pftDueTime.dwLowDateTime], rcx
0x180004d4b  xor     r9d, r9d; msWindowLength
0x180004d4e  mov     rcx, [rdi+128h]; pti
0x180004d55  xor     r8d, r8d; msPeriod
0x180004d58  call    cs:__imp_SetThreadpoolTimer
0x180004d5e  mov     r14, [rsp+180h+arg_10]
0x180004d66  mov     eax, r15d
0x180004d69  mov     r15, [rsp+180h+arg_18]
0x180004d71  mov     rsi, [rsp+180h+arg_8]
0x180004d79  jmp     loc_180004B9A
0x180004d7e  xor     r9d, r9d; msWindowLength
0x180004d81  xor     r8d, r8d; msPeriod
0x180004d84  xor     edx, edx; pftDueTime
0x180004d86  call    cs:__imp_SetThreadpoolTimer
0x180004d8c  jmp     loc_180004B82
0x180004d91  movzx   eax, ax
0x180004d94  or      eax, 80070000h
0x180004d99  jmp     loc_180004B9A
```
