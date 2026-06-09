# CUserModeHangReport::_OnWerDumpGenEnd(long,void (*)(void *,ulong,wchar_t const *,char *),void *)

- ea: `0x140026c80`
- end: `0x140026d79`
- name: `?_OnWerDumpGenEnd@CUserModeHangReport@@EEAAHJP6AXPEAXKPEB_WPEAD@Z0@Z`
- size: `249`
- prototype: `int(CUserModeHangReport *__hidden this, int, void (*)(void *, unsigned int, const wchar_t *, char *), void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400166ec`
- `0x1400241d0`
- `0x140026c80`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x140026cef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x140026cef`
- `wer!WerpResetTransientImageCacheStatistics` at `0x140026d5e`
- `wer!WerpResetTransientImageCacheStatistics` at `0x140026d5e`
- `wer!WerpTraceImageCacheStatistics` at `0x140026d23`
- `wer!WerpTraceImageCacheStatistics` at `0x140026d23`

## string_xrefs

- `0x140026cc4`: `VM read statistics:\n -  Pre-read calls: %9u.\n - Post-read calls: %9u.\n\n`

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
0x140026c80  push    rbx
0x140026c82  push    rbp
0x140026c83  push    rsi
0x140026c84  push    rdi
0x140026c85  sub     rsp, 38h
0x140026c89  cmp     dword ptr [rcx+0A4CCh], 0
0x140026c90  mov     rbp, r9
0x140026c93  mov     rdi, r8
0x140026c96  mov     qword ptr [rsp+58h+Frequency], 0
0x140026c9f  mov     rbx, rcx
0x140026ca2  jnz     short loc_140026CAB
0x140026ca4  xor     eax, eax
0x140026ca6  jmp     loc_140026D6F
0x140026cab  mov     dword ptr [rcx+0A4CCh], 0
0x140026cb5  test    rdi, rdi
0x140026cb8  jz      loc_140026D49
0x140026cbe  mov     eax, [rcx+9114h]
0x140026cc4  lea     r9, aVmReadStatisti; "VM read statistics:\r\n -  Pre-read cal"...
0x140026ccb  mov     [rsp+58h+var_30], eax
0x140026ccf  mov     r8d, 0C0000002h; unsigned int
0x140026cd5  mov     eax, [rcx+9110h]
0x140026cdb  mov     rdx, rbp; void *
0x140026cde  mov     rcx, rdi; void (*)(void *, unsigned int, const wchar_t *, char *)
0x140026ce1  mov     [rsp+58h+var_38], eax
0x140026ce5  call    ?CallWerpLogger@CUserModeHangReport@@CAXP6AXPEAXKPEB_WPEAD@Z0K1ZZ; CUserModeHangReport::CallWerpLogger(void (*)(void *,ulong,wchar_t const *,char *),void *,ulong,wchar_t const *,...)
0x140026cea  lea     rcx, [rsp+58h+Frequency]; lpFrequency
0x140026cef  call    cs:__imp_QueryPerformanceFrequency
0x140026cf6  nop     dword ptr [rax+rax+00h]
0x140026cfb  cmp     dword ptr [rsp+58h+Frequency], 0
0x140026d00  jnz     short loc_140026D0E
0x140026d02  cmp     dword ptr [rsp+58h+Frequency+4], 0
0x140026d07  jnz     short loc_140026D0E
0x140026d09  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140026d0e  lea     rsi, [rbx+0A198h]
0x140026d15  mov     rdx, rbp
0x140026d18  mov     r8, rsi
0x140026d1b  lea     r9, [rsp+58h+Frequency]
0x140026d20  mov     rcx, rdi
0x140026d23  call    cs:__imp_WerpTraceImageCacheStatistics
0x140026d2a  nop     dword ptr [rax+rax+00h]
0x140026d2f  lea     r9, asc_140069188; "\r\n\r\n"
0x140026d36  mov     r8d, 0C0000002h; unsigned int
0x140026d3c  mov     rdx, rbp; void *
0x140026d3f  mov     rcx, rdi; void (*)(void *, unsigned int, const wchar_t *, char *)
0x140026d42  call    ?CallWerpLogger@CUserModeHangReport@@CAXP6AXPEAXKPEB_WPEAD@Z0K1ZZ; CUserModeHangReport::CallWerpLogger(void (*)(void *,ulong,wchar_t const *,char *),void *,ulong,wchar_t const *,...)
0x140026d47  jmp     short loc_140026D50
0x140026d49  lea     rsi, [rcx+0A198h]
0x140026d50  mov     rcx, rsi
0x140026d53  mov     qword ptr [rbx+9110h], 0
0x140026d5e  call    cs:__imp_?WerpResetTransientImageCacheStatistics@@YAXPEAUWERP_IMAGE_CACHE@@@Z; WerpResetTransientImageCacheStatistics(WERP_IMAGE_CACHE *)
0x140026d65  nop     dword ptr [rax+rax+00h]
0x140026d6a  mov     eax, 1
0x140026d6f  add     rsp, 38h
0x140026d73  pop     rdi
0x140026d74  pop     rsi
0x140026d75  pop     rbp
0x140026d76  pop     rbx
0x140026d77  retn
```
