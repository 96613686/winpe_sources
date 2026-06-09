# CEventThrottle::ReportDroppedIfNeeded(void)

- ea: `0x14002a324`
- end: `0x14002a531`
- name: `?ReportDroppedIfNeeded@CEventThrottle@@QEAAXXZ`
- size: `525`
- prototype: `void __fastcall(CEventThrottle *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002a70c`

## callees

- `0x1400030a0`
- `0x14000a684`
- `0x14002a230`
- `0x14002a30c`
- `0x14002a324`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x14002a44a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x14002a44a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002a430`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14002a430`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x14002a478`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x14002a478`
- `ext-ms-win-advapi32-eventlog-l1-1-0!DeregisterEventSource` at `0x14002a50f`
- `ext-ms-win-advapi32-eventlog-l1-1-0!DeregisterEventSource` at `0x14002a50f`
- `ext-ms-win-advapi32-eventlog-l1-1-0!RegisterEventSourceW` at `0x14002a4bd`
- `ext-ms-win-advapi32-eventlog-l1-1-0!RegisterEventSourceW` at `0x14002a4bd`
- `ext-ms-win-advapi32-eventlog-l1-1-0!ReportEventW` at `0x14002a506`
- `ext-ms-win-advapi32-eventlog-l1-1-0!ReportEventW` at `0x14002a506`

## string_xrefs

- `0x14002a49e`: `Windows Search Service`

## pseudocode

```c
void __fastcall CEventThrottle::ReportDroppedIfNeeded(CEventThrottle *this)
{
  __int64 v2; // rcx
  int v3; // eax
  bool v4; // di
  __int64 v5; // rax
  int TimeFormatW; // eax
  bool v7; // dl
  HANDLE v8; // rbx
  FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE LocalTime[20]; // [rsp+58h] [rbp-A8h] BYREF
  int v11; // [rsp+6Ch] [rbp-94h]
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR Strings[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v14[16]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v15[16]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR TimeStr[128]; // [rsp+E0h] [rbp-20h] BYREF

  if ( CEventThrottle::NeedsReported(this) )
  {
    v3 = *(_DWORD *)(v2 + 20);
    memset(LocalTime, 0, sizeof(LocalTime));
    v11 = v3;
    if ( !CEventThrottle::Load(
            (CEventThrottle *)LocalTime,
            L"Software\\Microsoft\\Windows Search\\Tracing\\EventThrottleLastReported")
      || *(_DWORD *)LocalTime != *(_DWORD *)this
      || *(_QWORD *)&LocalTime[4] != *(_QWORD *)((char *)this + 4)
      || *(_DWORD *)&LocalTime[16] != *((_DWORD *)this + 4) )
    {
      v4 = StringCchPrintfW(v14, 0x10u, L"%u", *((unsigned int *)this + 5)) >= 0
        && StringCchPrintfW(v15, 0x10u, L"%d", *((unsigned int *)this + 4)) >= 0;
      SystemTime = 0;
      *(_OWORD *)LocalTime = 0;
      if ( v4 )
      {
        v5 = 10000LL * *(_QWORD *)((char *)this + 4);
        FileTime.dwLowDateTime = 10000 * *((_DWORD *)this + 1);
        FileTime.dwHighDateTime = HIDWORD(v5);
        if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
        {
          if ( SystemTimeToTzSpecificLocalTime(0, &SystemTime, (LPSYSTEMTIME)LocalTime) )
          {
            TimeFormatW = GetTimeFormatW(0x800u, 0, (const SYSTEMTIME *)LocalTime, 0, TimeStr, 128);
            v7 = 0;
            if ( TimeFormatW > 0 )
              v7 = v4;
            if ( v7 )
            {
              Strings[0] = &dword_140053AD4;
              Strings[1] = v14;
              Strings[2] = v15;
              Strings[3] = TimeStr;
              v8 = RegisterEventSourceW(0, L"Windows Search Service");
              if ( v8 )
              {
                ReportEventW(v8, 2u, 1u, 0x800003F7, 0, 4u, 0, Strings, 0);
                DeregisterEventSource(v8);
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14002a324  push    rbp
0x14002a326  push    rbx
0x14002a327  push    rdi
0x14002a328  push    r14
0x14002a32a  lea     rbp, [rsp-0F8h]
0x14002a332  sub     rsp, 1F8h
0x14002a339  mov     rax, cs:__security_cookie
0x14002a340  xor     rax, rsp
0x14002a343  mov     [rbp+110h+var_30], rax
0x14002a34a  mov     rbx, rcx
0x14002a34d  call    ?NeedsReported@CEventThrottle@@QEBA_NXZ; CEventThrottle::NeedsReported(void)
0x14002a352  test    al, al
0x14002a354  jz      loc_14002A515
0x14002a35a  mov     eax, [rcx+14h]
0x14002a35d  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows Search\\Tr"...
0x14002a364  lea     rcx, [rsp+210h+LocalTime]; this
0x14002a369  mov     dword ptr [rsp+210h+LocalTime], 0
0x14002a371  mov     qword ptr [rsp+210h+LocalTime+4], 0
0x14002a37a  mov     qword ptr [rsp+210h+LocalTime+0Ch], 0
0x14002a383  mov     [rsp+210h+var_1A4], eax
0x14002a387  call    ?Load@CEventThrottle@@QEAA_NPEB_W@Z; CEventThrottle::Load(wchar_t const *)
0x14002a38c  test    al, al
0x14002a38e  jz      short loc_14002A3B0
0x14002a390  mov     eax, [rbx]
0x14002a392  cmp     dword ptr [rsp+210h+LocalTime], eax
0x14002a396  jnz     short loc_14002A3B0
0x14002a398  mov     rax, [rbx+4]
0x14002a39c  cmp     qword ptr [rsp+210h+LocalTime+4], rax
0x14002a3a1  jnz     short loc_14002A3B0
0x14002a3a3  mov     eax, [rbx+10h]
0x14002a3a6  cmp     dword ptr [rsp+210h+LocalTime+10h], eax
0x14002a3aa  jz      loc_14002A515
0x14002a3b0  mov     r9d, [rbx+14h]
0x14002a3b4  lea     r8, aU; "%u"
0x14002a3bb  mov     edi, 10h
0x14002a3c0  lea     rcx, [rbp+110h+var_170]; unsigned __int16 *
0x14002a3c4  mov     edx, edi; unsigned __int64
0x14002a3c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002a3cb  lea     r14d, [rdi-0Fh]
0x14002a3cf  test    eax, eax
0x14002a3d1  jns     short loc_14002A3D8
0x14002a3d3  xor     dil, dil
0x14002a3d6  jmp     short loc_14002A3F9
0x14002a3d8  mov     r9d, [rbx+10h]
0x14002a3dc  lea     r8, aD; "%d"
0x14002a3e3  mov     rdx, rdi; unsigned __int64
0x14002a3e6  lea     rcx, [rbp+110h+var_150]; unsigned __int16 *
0x14002a3ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002a3ef  xor     ecx, ecx
0x14002a3f1  mov     edi, r14d
0x14002a3f4  test    eax, eax
0x14002a3f6  cmovs   edi, ecx
0x14002a3f9  xorps   xmm0, xmm0
0x14002a3fc  xorps   xmm1, xmm1
0x14002a3ff  movups  xmmword ptr [rsp+210h+SystemTime.wYear], xmm0
0x14002a404  movups  xmmword ptr [rsp+210h+LocalTime], xmm1
0x14002a409  test    dil, dil
0x14002a40c  jz      loc_14002A515
0x14002a412  imul    rax, [rbx+4], 2710h
0x14002a41a  lea     rdx, [rsp+210h+SystemTime]; lpSystemTime
0x14002a41f  mov     [rsp+210h+FileTime.dwLowDateTime], eax
0x14002a423  lea     rcx, [rsp+210h+FileTime]; lpFileTime
0x14002a428  shr     rax, 20h
0x14002a42c  mov     [rsp+210h+FileTime.dwHighDateTime], eax
0x14002a430  call    cs:__imp_FileTimeToSystemTime
0x14002a436  test    eax, eax
0x14002a438  jz      loc_14002A515
0x14002a43e  lea     r8, [rsp+210h+LocalTime]; lpLocalTime
0x14002a443  xor     ecx, ecx; lpTimeZoneInformation
0x14002a445  lea     rdx, [rsp+210h+SystemTime]; lpUniversalTime
0x14002a44a  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x14002a450  test    eax, eax
0x14002a452  jz      loc_14002A515
0x14002a458  lea     rax, [rbp+110h+TimeStr]
0x14002a45c  mov     [rsp+210h+cchTime], 80h; cchTime
0x14002a464  xor     r9d, r9d; lpFormat
0x14002a467  mov     [rsp+210h+lpTimeStr], rax; lpTimeStr
0x14002a46c  lea     r8, [rsp+210h+LocalTime]; lpTime
0x14002a471  xor     edx, edx; dwFlags
0x14002a473  mov     ecx, 800h; Locale
0x14002a478  call    cs:__imp_GetTimeFormatW
0x14002a47e  xor     edx, edx
0x14002a480  movzx   ecx, dil
0x14002a484  test    eax, eax
0x14002a486  cmovg   edx, ecx
0x14002a489  test    dl, dl
0x14002a48b  jz      loc_14002A515
0x14002a491  lea     rax, dword_140053AD4
0x14002a498  xor     ecx, ecx; lpUNCServerName
0x14002a49a  mov     [rbp+110h+Strings], rax
0x14002a49e  lea     rdx, SourceName; "Windows Search Service"
0x14002a4a5  lea     rax, [rbp+110h+var_170]
0x14002a4a9  mov     [rbp+110h+var_188], rax
0x14002a4ad  lea     rax, [rbp+110h+var_150]
0x14002a4b1  mov     [rbp+110h+var_180], rax
0x14002a4b5  lea     rax, [rbp+110h+TimeStr]
0x14002a4b9  mov     [rbp+110h+var_178], rax
0x14002a4bd  call    cs:__imp_RegisterEventSourceW
0x14002a4c3  mov     rbx, rax
0x14002a4c6  test    rax, rax
0x14002a4c9  jz      short loc_14002A515
0x14002a4cb  mov     [rsp+210h+lpRawData], 0; lpRawData
0x14002a4d4  lea     rax, [rbp+110h+Strings]
0x14002a4d8  mov     [rsp+210h+lpStrings], rax; lpStrings
0x14002a4dd  mov     r8d, r14d; wCategory
0x14002a4e0  mov     [rsp+210h+dwDataSize], 0; dwDataSize
0x14002a4e8  mov     edx, 2; wType
0x14002a4ed  mov     word ptr [rsp+210h+cchTime], 4; wNumStrings
0x14002a4f4  mov     r9d, 800003F7h; dwEventID
0x14002a4fa  mov     rcx, rbx; hEventLog
0x14002a4fd  mov     [rsp+210h+lpTimeStr], 0; lpUserSid
0x14002a506  call    cs:__imp_ReportEventW
0x14002a50c  mov     rcx, rbx; hEventLog
0x14002a50f  call    cs:__imp_DeregisterEventSource
0x14002a515  mov     rcx, [rbp+110h+var_30]
0x14002a51c  xor     rcx, rsp; StackCookie
0x14002a51f  call    __security_check_cookie
0x14002a524  add     rsp, 1F8h
0x14002a52b  pop     r14
0x14002a52d  pop     rdi
0x14002a52e  pop     rbx
0x14002a52f  pop     rbp
0x14002a530  retn
```
