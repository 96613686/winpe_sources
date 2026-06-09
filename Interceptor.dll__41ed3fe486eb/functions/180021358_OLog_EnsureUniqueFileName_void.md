# OLog::EnsureUniqueFileName(void)

- ea: `0x180021358`
- end: `0x18002160b`
- name: `?EnsureUniqueFileName@OLog@@AEAAXXZ`
- size: `691`
- prototype: `void __fastcall(OLog *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180021278`
- `0x180021610`

## callees

- `0x180002820`
- `0x180003e90`
- `0x18000410c`
- `0x1800045ec`
- `0x180021358`
- `0x180022290`
- `0x1800266e0`
- `0x18002b400`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180021498`
- `KERNEL32!GetCurrentProcessId` at `0x180021498`
- `KERNEL32!GetSystemTime` at `0x18002147e`
- `KERNEL32!GetSystemTime` at `0x18002147e`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180021492`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180021492`
- `KERNEL32!GetTimeZoneInformation` at `0x180021473`
- `KERNEL32!GetTimeZoneInformation` at `0x180021473`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002141a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002158a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800215d6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002141a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002158a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800215d6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180021424`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180021591`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800215dd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180021424`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180021591`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800215dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall OLog::EnsureUniqueFileName(OLog *this)
{
  char *v1; // rdi
  __int64 v2; // rbx
  void *v3; // rdx
  int v4; // edx
  __int64 v5; // rax
  void *v6; // rcx
  void *v7; // rcx
  DWORD LocalTime; // [rsp+58h] [rbp-B0h] BYREF
  struct _SYSTEMTIME LocalTime_8; // [rsp+60h] [rbp-A8h] BYREF
  struct _SYSTEMTIME Block_8; // [rsp+70h] [rbp-98h] BYREF
  __int128 v11; // [rsp+80h] [rbp-88h]
  void *v12[2]; // [rsp+90h] [rbp-78h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-68h]
  void *v14[2]; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v15; // [rsp+C0h] [rbp-48h]
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+D8h] [rbp-30h] BYREF

  v1 = (char *)this + 8;
  Block_8 = 0;
  v11 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&Block_8, L"*", 1);
  v2 = std::wstring::find(v1, &Block_8, 0);
  if ( *((_QWORD *)&v11 + 1) > 7u )
  {
    v3 = *(void **)&Block_8.wYear;
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v11 + 1) + 2) >= 0x1000 )
    {
      v3 = *(void **)(*(_QWORD *)&Block_8.wYear - 8LL);
      if ( (unsigned __int64)(*(_QWORD *)&Block_8.wYear - (_QWORD)v3 - 8LL) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v3);
  }
  if ( v2 != -1 )
  {
    LocalTime_8 = 0;
    Block_8 = 0;
    memset(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
    *(_OWORD *)v12 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v12[0]) = 0;
    GetTimeZoneInformation(&TimeZoneInformation);
    GetSystemTime(&Block_8);
    SystemTimeToTzSpecificLocalTime(&TimeZoneInformation, &Block_8, &LocalTime_8);
    LocalTime = GetCurrentProcessId();
    v5 = OString::Format<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned long>(
           (unsigned int)v14,
           v4,
           (unsigned int)&LocalTime_8,
           (unsigned int)&LocalTime_8.wMonth,
           (__int64)&LocalTime_8.wDay,
           (__int64)&LocalTime_8.wHour,
           (__int64)&LocalTime_8.wMinute,
           (__int64)&LocalTime_8.wSecond,
           (__int64)&LocalTime);
    if ( v12 != (void **)v5 )
    {
      *(_OWORD *)v12 = *(_OWORD *)v5;
      si128 = *(__m128i *)(v5 + 16);
      *(_QWORD *)(v5 + 16) = 0;
      *(_QWORD *)(v5 + 24) = 7;
      *(_WORD *)v5 = 0;
    }
    std::wstring::_Tidy_deallocate(v14);
    *(_OWORD *)v14 = 0;
    v15 = 0;
    std::wstring::_Construct<1,wchar_t const *>(v14, L"*", 1);
    OString::Replace(v1, v14, v12);
    if ( *((_QWORD *)&v15 + 1) > 7u )
    {
      v6 = v14[0];
      if ( (unsigned __int64)(2LL * *((_QWORD *)&v15 + 1) + 2) >= 0x1000 )
      {
        v6 = (void *)*((_QWORD *)v14[0] - 1);
        if ( (unsigned __int64)((char *)v14[0] - (char *)v6 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v6);
    }
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v7 = v12[0];
      if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
      {
        v7 = (void *)*((_QWORD *)v12[0] - 1);
        if ( (unsigned __int64)((char *)v12[0] - (char *)v7 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v7);
    }
  }
}

```

## disassembly

```asm
0x180021358  mov     rax, rsp
0x18002135b  mov     [rax+10h], rbx
0x18002135f  mov     [rax+18h], rdi
0x180021363  mov     [rax+20h], r14
0x180021367  push    rbp
0x180021368  lea     rbp, [rax-98h]
0x18002136f  sub     rsp, 190h
0x180021376  mov     rax, cs:__security_cookie
0x18002137d  xor     rax, rsp
0x180021380  mov     [rbp+90h+var_10], rax
0x180021387  lea     rdi, [rcx+8]
0x18002138b  xorps   xmm0, xmm0
0x18002138e  movups  xmmword ptr [rsp+190h+Block+8], xmm0
0x180021393  xorps   xmm1, xmm1
0x180021396  movdqu  [rsp+190h+var_120+8], xmm1
0x18002139c  mov     r8d, 1
0x1800213a2  lea     rdx, asc_180057F48; "*"
0x1800213a9  lea     rcx, [rsp+190h+Block+8]
0x1800213ae  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800213b3  xor     r8d, r8d
0x1800213b6  lea     rdx, [rsp+190h+Block+8]
0x1800213bb  mov     rcx, rdi
0x1800213be  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1800213c3  nop     dword ptr [rax+00h]
0x1800213c7  nop     word ptr [rax+rax+00000000h]
0x1800213d0  mov     rbx, rax
0x1800213d3  mov     r14d, 1000h
0x1800213d9  mov     rcx, [rbp+90h+var_110]
0x1800213dd  cmp     rcx, 7
0x1800213e1  jbe     short loc_18002142A
0x1800213e3  mov     rdx, [rsp+190h+Block+8]
0x1800213e8  mov     rax, rdx
0x1800213eb  lea     rcx, ds:2[rcx*2]
0x1800213f3  cmp     rcx, r14
0x1800213f6  jb      short loc_180021421
0x1800213f8  mov     rdx, [rdx-8]
0x1800213fc  sub     rax, rdx
0x1800213ff  add     rax, 0FFFFFFFFFFFFFFF8h
0x180021403  cmp     rax, 1Fh
0x180021407  jbe     short loc_180021421
0x180021409  xor     ebx, ebx
0x18002140b  mov     [rsp+190h+Reserved], rbx; Reserved
0x180021410  xor     r9d, r9d; LineNo
0x180021413  xor     r8d, r8d; FileName
0x180021416  xor     edx, edx; FunctionName
0x180021418  xor     ecx, ecx; Expression
0x18002141a  call    cs:__imp__invoke_watson
0x180021421  mov     rcx, rdx; Block
0x180021424  call    cs:__imp_free
0x18002142a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002142e  jz      loc_1800215E3
0x180021434  xorps   xmm0, xmm0
0x180021437  movups  xmmword ptr [rsp+190h+LocalTime.wHour], xmm0
0x18002143c  xorps   xmm1, xmm1
0x18002143f  movups  xmmword ptr [rsp+190h+Block+8], xmm1
0x180021444  xor     edx, edx; Val
0x180021446  mov     r8d, 0ACh; Size
0x18002144c  lea     rcx, [rbp+90h+TimeZoneInformation]; void *
0x180021450  call    memset
0x180021455  xorps   xmm0, xmm0
0x180021458  movups  xmmword ptr [rbp+90h+var_108], xmm0
0x18002145c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180021464  movdqu  [rbp+90h+var_F8], xmm1
0x180021469  xor     ebx, ebx
0x18002146b  mov     word ptr [rbp+90h+var_108], bx
0x18002146f  lea     rcx, [rbp+90h+TimeZoneInformation]; lpTimeZoneInformation
0x180021473  call    cs:__imp_GetTimeZoneInformation
0x180021479  lea     rcx, [rsp+190h+Block+8]; lpSystemTime
0x18002147e  call    cs:__imp_GetSystemTime
0x180021484  lea     r8, [rsp+190h+LocalTime.wHour]; lpLocalTime
0x180021489  lea     rdx, [rsp+190h+Block+8]; lpUniversalTime
0x18002148e  lea     rcx, [rbp+90h+TimeZoneInformation]; lpTimeZoneInformation
0x180021492  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180021498  call    cs:__imp_GetCurrentProcessId
0x18002149e  mov     dword ptr [rsp+190h+LocalTime.wYear], eax
0x1800214a2  lea     rax, [rsp+190h+LocalTime]
0x1800214a7  mov     [rsp+190h+var_150], rax
0x1800214ac  lea     rax, [rsp+190h+Block+4]
0x1800214b1  mov     [rsp+190h+var_158], rax
0x1800214b6  lea     rax, [rsp+190h+Block+2]
0x1800214bb  mov     [rsp+190h+var_160], rax
0x1800214c0  lea     rax, [rsp+190h+Block]
0x1800214c5  mov     [rsp+190h+var_168], rax
0x1800214ca  lea     rax, [rsp+190h+LocalTime.wMilliseconds]
0x1800214cf  mov     [rsp+190h+Reserved], rax
0x1800214d4  lea     r9, [rsp+190h+LocalTime.wMinute]
0x1800214d9  lea     r8, [rsp+190h+LocalTime.wHour]
0x1800214de  lea     rcx, [rbp+90h+var_E8]
0x1800214e2  call    ??$Format@GGGGGGK@OString@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEBG11111AEBK@Z; OString::Format<ushort,ushort,ushort,ushort,ushort,ushort,ulong>(wchar_t const *,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ulong const &)
0x1800214e7  lea     rcx, [rbp+90h+var_108]
0x1800214eb  cmp     rcx, rax
0x1800214ee  jz      short loc_18002150E
0x1800214f0  movups  xmm0, xmmword ptr [rax]
0x1800214f3  movups  xmmword ptr [rbp+90h+var_108], xmm0
0x1800214f7  movups  xmm1, xmmword ptr [rax+10h]
0x1800214fb  movups  [rbp+90h+var_F8], xmm1
0x1800214ff  mov     [rax+10h], rbx
0x180021503  mov     qword ptr [rax+18h], 7
0x18002150b  mov     [rax], bx
0x18002150e  lea     rcx, [rbp+90h+var_E8]
0x180021512  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021517  xorps   xmm0, xmm0
0x18002151a  movups  xmmword ptr [rbp+90h+var_E8], xmm0
0x18002151e  xorps   xmm1, xmm1
0x180021521  movdqu  [rbp+90h+var_D8], xmm1
0x180021526  mov     r8d, 1
0x18002152c  lea     rdx, asc_180057F48; "*"
0x180021533  lea     rcx, [rbp+90h+var_E8]
0x180021537  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002153c  lea     r8, [rbp+90h+var_108]
0x180021540  lea     rdx, [rbp+90h+var_E8]
0x180021544  mov     rcx, rdi
0x180021547  call    ?Replace@OString@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@1_K@Z; OString::Replace(std::wstring &,std::wstring const &,std::wstring const &,unsigned __int64)
0x18002154c  mov     rax, qword ptr [rbp+90h+var_D8+8]
0x180021550  cmp     rax, 7
0x180021554  jbe     short loc_180021598
0x180021556  mov     rcx, [rbp+90h+var_E8]; Block
0x18002155a  mov     rdx, rcx
0x18002155d  lea     rax, ds:2[rax*2]
0x180021565  cmp     rax, r14
0x180021568  jb      short loc_180021591
0x18002156a  mov     rcx, [rcx-8]
0x18002156e  sub     rdx, rcx
0x180021571  lea     rax, [rdx-8]
0x180021575  cmp     rax, 1Fh
0x180021579  jbe     short loc_180021591
0x18002157b  mov     [rsp+190h+Reserved], rbx; Reserved
0x180021580  xor     r9d, r9d; LineNo
0x180021583  xor     r8d, r8d; FileName
0x180021586  xor     edx, edx; FunctionName
0x180021588  xor     ecx, ecx; Expression
0x18002158a  call    cs:__imp__invoke_watson
0x180021591  call    cs:__imp_free
0x180021597  nop
0x180021598  mov     rax, qword ptr [rbp+90h+var_F8+8]
0x18002159c  cmp     rax, 7
0x1800215a0  jbe     short loc_1800215E3
0x1800215a2  mov     rcx, [rbp+90h+var_108]; Block
0x1800215a6  mov     rdx, rcx
0x1800215a9  lea     rax, ds:2[rax*2]
0x1800215b1  cmp     rax, r14
0x1800215b4  jb      short loc_1800215DD
0x1800215b6  mov     rcx, [rcx-8]
0x1800215ba  sub     rdx, rcx
0x1800215bd  lea     rax, [rdx-8]
0x1800215c1  cmp     rax, 1Fh
0x1800215c5  jbe     short loc_1800215DD
0x1800215c7  mov     [rsp+190h+Reserved], rbx; Reserved
0x1800215cc  xor     r9d, r9d; LineNo
0x1800215cf  xor     r8d, r8d; FileName
0x1800215d2  xor     edx, edx; FunctionName
0x1800215d4  xor     ecx, ecx; Expression
0x1800215d6  call    cs:__imp__invoke_watson
0x1800215dd  call    cs:__imp_free
0x1800215e3  mov     rcx, [rbp+90h+var_10]
0x1800215ea  xor     rcx, rsp; StackCookie
0x1800215ed  call    __security_check_cookie
0x1800215f2  lea     r11, [rsp+190h+var_s0]
0x1800215fa  mov     rbx, [r11+18h]
0x1800215fe  mov     rdi, [r11+20h]
0x180021602  mov     r14, [r11+28h]
0x180021606  mov     rsp, r11
0x180021609  pop     rbp
0x18002160a  retn
```
