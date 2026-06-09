# CUserModeHangReport::_OnWerDumpGenEnd(long,void (*)(void *,ulong,wchar_t const *,char *),void *)

- ea: `0x1400253a0`
- end: `0x140025482`
- name: `?_OnWerDumpGenEnd@CUserModeHangReport@@EEAAHJP6AXPEAXKPEB_WPEAD@Z0@Z`
- size: `226`
- prototype: `int(CUserModeHangReport *__hidden this, int, void (*)(void *, unsigned int, const wchar_t *, char *), void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140015b40`
- `0x140022b04`
- `0x1400253a0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x14002540b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x14002540b`
- `wer!WerpResetTransientImageCacheStatistics` at `0x14002546e`
- `wer!WerpResetTransientImageCacheStatistics` at `0x14002546e`
- `wer!WerpTraceImageCacheStatistics` at `0x140025439`
- `wer!WerpTraceImageCacheStatistics` at `0x140025439`

## string_xrefs

- `0x1400253e0`: `VM read statistics:\n -  Pre-read calls: %9u.\n - Post-read calls: %9u.\n\n`

## pseudocode

```c
__int64 __fastcall CUserModeHangReport::_OnWerDumpGenEnd(
        CUserModeHangReport *this,
        __int64 a2,
        void (*a3)(void *, unsigned int, const wchar_t *, char *),
        void *a4)
{
  bool v4; // zf
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  struct WERP_IMAGE_CACHE *v13; // rsi
  LARGE_INTEGER Frequency; // [rsp+60h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 10547) == 0;
  Frequency.QuadPart = 0;
  if ( v4 )
    return 0;
  *((_DWORD *)this + 10547) = 0;
  if ( a3 )
  {
    CUserModeHangReport::CallWerpLogger(
      a3,
      a4,
      0xC0000002,
      L"VM read statistics:\r\n -  Pre-read calls: %9u.\r\n - Post-read calls: %9u.\r\n\r\n",
      *((_DWORD *)this + 9284),
      *((_DWORD *)this + 9285));
    QueryPerformanceFrequency(&Frequency);
    if ( !Frequency.QuadPart )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11, v12);
    v13 = (CUserModeHangReport *)((char *)this + 41368);
    WerpTraceImageCacheStatistics(a3, a4, (char *)this + 41368, &Frequency);
    CUserModeHangReport::CallWerpLogger(a3, a4, 0xC0000002, L"\r\n\r\n");
  }
  else
  {
    v13 = (CUserModeHangReport *)((char *)this + 41368);
  }
  *((_QWORD *)this + 4642) = 0;
  WerpResetTransientImageCacheStatistics(v13);
  return 1;
}

```

## disassembly

```asm
0x1400253a0  push    rbx
0x1400253a2  push    rbp
0x1400253a3  push    rsi
0x1400253a4  push    rdi
0x1400253a5  sub     rsp, 38h
0x1400253a9  cmp     dword ptr [rcx+0A4CCh], 0
0x1400253b0  mov     rbp, r9
0x1400253b3  mov     rdi, r8
0x1400253b6  mov     qword ptr [rsp+58h+Frequency], 0
0x1400253bf  mov     rbx, rcx
0x1400253c2  jnz     short loc_1400253CB
0x1400253c4  xor     eax, eax
0x1400253c6  jmp     loc_140025479
0x1400253cb  mov     dword ptr [rcx+0A4CCh], 0
0x1400253d5  test    rdi, rdi
0x1400253d8  jz      short loc_140025459
0x1400253da  mov     eax, [rcx+9114h]
0x1400253e0  lea     r9, aVmReadStatisti; "VM read statistics:\r\n -  Pre-read cal"...
0x1400253e7  mov     [rsp+58h+var_30], eax
0x1400253eb  mov     r8d, 0C0000002h; unsigned int
0x1400253f1  mov     eax, [rcx+9110h]
0x1400253f7  mov     rdx, rbp; void *
0x1400253fa  mov     rcx, rdi; void (*)(void *, unsigned int, const wchar_t *, char *)
0x1400253fd  mov     [rsp+58h+var_38], eax
0x140025401  call    ?CallWerpLogger@CUserModeHangReport@@CAXP6AXPEAXKPEB_WPEAD@Z0K1ZZ; CUserModeHangReport::CallWerpLogger(void (*)(void *,ulong,wchar_t const *,char *),void *,ulong,wchar_t const *,...)
0x140025406  lea     rcx, [rsp+58h+Frequency]; lpFrequency
0x14002540b  call    cs:__imp_QueryPerformanceFrequency
0x140025411  cmp     dword ptr [rsp+58h+Frequency], 0
0x140025416  jnz     short loc_140025424
0x140025418  cmp     dword ptr [rsp+58h+Frequency+4], 0
0x14002541d  jnz     short loc_140025424
0x14002541f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140025424  lea     rsi, [rbx+0A198h]
0x14002542b  mov     rdx, rbp
0x14002542e  mov     r8, rsi
0x140025431  lea     r9, [rsp+58h+Frequency]
0x140025436  mov     rcx, rdi
0x140025439  call    cs:__imp_WerpTraceImageCacheStatistics
0x14002543f  lea     r9, asc_140065188; "\r\n\r\n"
0x140025446  mov     r8d, 0C0000002h; unsigned int
0x14002544c  mov     rdx, rbp; void *
0x14002544f  mov     rcx, rdi; void (*)(void *, unsigned int, const wchar_t *, char *)
0x140025452  call    ?CallWerpLogger@CUserModeHangReport@@CAXP6AXPEAXKPEB_WPEAD@Z0K1ZZ; CUserModeHangReport::CallWerpLogger(void (*)(void *,ulong,wchar_t const *,char *),void *,ulong,wchar_t const *,...)
0x140025457  jmp     short loc_140025460
0x140025459  lea     rsi, [rcx+0A198h]
0x140025460  mov     rcx, rsi
0x140025463  mov     qword ptr [rbx+9110h], 0
0x14002546e  call    cs:__imp_?WerpResetTransientImageCacheStatistics@@YAXPEAUWERP_IMAGE_CACHE@@@Z; WerpResetTransientImageCacheStatistics(WERP_IMAGE_CACHE *)
0x140025474  mov     eax, 1
0x140025479  add     rsp, 38h
0x14002547d  pop     rdi
0x14002547e  pop     rsi
0x14002547f  pop     rbp
0x140025480  pop     rbx
0x140025481  retn
```
