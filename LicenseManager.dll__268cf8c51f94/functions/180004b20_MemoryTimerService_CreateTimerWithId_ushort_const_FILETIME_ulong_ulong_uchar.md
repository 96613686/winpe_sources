# MemoryTimerService::CreateTimerWithId(ushort const *,_FILETIME,ulong,ulong,uchar *)

- ea: `0x180004b20`
- end: `0x180005026`
- name: `?CreateTimerWithId@MemoryTimerService@@UEAAJPEBGU_FILETIME@@KKPEAE@Z`
- size: `1286`
- prototype: `int(MemoryTimerService *__hidden this, const unsigned __int16 *, struct _FILETIME, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004b20`
- `0x18000502c`
- `0x180005794`
- `0x18000a98c`
- `0x180013b50`
- `0x1800171b0`
- `0x180017200`
- `0x1800174bc`
- `0x180075e60`
- `0x18008251f`
- `0x18008a400`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004ba5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004ba5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004edf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004fa9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004edf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004fa9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004eef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004eef`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180004bdf`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180004bdf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004f6e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004f6e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x180005001`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x180005001`

## string_xrefs

- `0x180004e6d`: `MemoryTimerService::CreateTimerWithId`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MemoryTimerService::CreateTimerWithId(
        MemoryTimerService *this,
        const unsigned __int16 *a2,
        struct _FILETIME a3,
        int a4,
        unsigned int a5,
        unsigned __int8 *a6)
{
  __int64 result; // rax
  __int64 v9; // rbx
  size_t v10; // rdi
  size_t v11; // rdi
  __int64 v12; // r13
  wchar_t *v13; // r15
  size_t v14; // rdi
  __int64 **v15; // r15
  __int64 *v16; // rsi
  __int64 *v17; // rdi
  const wchar_t *v18; // rcx
  size_t v19; // r13
  const wchar_t *v20; // rdx
  size_t v21; // r12
  size_t v22; // r8
  int v23; // eax
  const wchar_t *v24; // rdx
  size_t v25; // rdi
  size_t v26; // r12
  const wchar_t *v27; // rcx
  size_t v28; // r8
  int v29; // eax
  char *v30; // rax
  __int64 v31; // rcx
  _QWORD *v32; // rdi
  __int64 v33; // rax
  __int64 v34; // rsi
  __int64 v35; // rcx
  __int64 v36; // rdi
  double v37; // xmm0_8
  double v38; // xmm1_8
  void *v39; // rdx
  const char *v40; // r9
  const char *v41; // r9
  const char *v42; // r9
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v45; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v46; // [rsp+58h] [rbp-D0h]
  struct _FILETIME v47; // [rsp+60h] [rbp-C8h]
  unsigned __int8 *v48; // [rsp+68h] [rbp-C0h] BYREF
  char *v49; // [rsp+70h] [rbp-B8h]
  _QWORD v50[2]; // [rsp+78h] [rbp-B0h] BYREF
  char v51; // [rsp+88h] [rbp-A0h] BYREF
  int v52; // [rsp+9Ch] [rbp-8Ch]
  wchar_t *S2[2]; // [rsp+A8h] [rbp-80h] BYREF
  size_t N; // [rsp+B8h] [rbp-70h]
  unsigned __int64 v55; // [rsp+C0h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v50[0] = a2;
  v48 = a6;
  if ( !a6 && a5 )
    return 2147942487LL;
  v47 = a3;
  v9 = 0;
  v46 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v49 = (char *)this + 24;
  *(_OWORD *)S2 = 0;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  try
  {
    if ( v10 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v10 > 7 )
    {
      v12 = std::wstring::_Calculate_growth(v10, 7);
      v13 = (wchar_t *)std::allocator<unsigned short>::allocate(S2, v12 + 1);
      S2[0] = v13;
      N = v10;
      v55 = v12;
      v14 = v10;
      memcpy_0(v13, a2, v14 * 2);
      v13[v14] = 0;
    }
    else
    {
      N = v10;
      v55 = 7;
      v11 = 2 * v10;
      memcpy_0(S2, a2, v11);
      *(_WORD *)((char *)S2 + v11) = 0;
    }
    v15 = (__int64 **)((char *)this + 64);
    v16 = (__int64 *)*((_QWORD *)this + 8);
    v17 = (__int64 *)v16[1];
    v52 = 0;
    while ( 1 )
    {
      if ( *((_BYTE *)v17 + 25) )
      {
        if ( !*((_BYTE *)v16 + 25) )
        {
          v24 = (const wchar_t *)(v16 + 4);
          v25 = v16[6];
          if ( (unsigned __int64)v16[7] > 7 )
            v24 = *(const wchar_t **)v24;
          v26 = N;
          v27 = (const wchar_t *)S2;
          if ( v55 > 7 )
            v27 = S2[0];
          v28 = N;
          if ( v25 < N )
            v28 = v16[6];
          v29 = wmemcmp(v27, v24, v28);
          if ( v29 )
          {
            if ( v29 >= 0 )
            {
LABEL_39:
              std::wstring::_Tidy_deallocate(S2);
              if ( v16 == *v15 )
              {
                SystemTimeAsFileTime = (_FILETIME)this;
                if ( this )
                  (*(void (__fastcall **)(MemoryTimerService *))(*(_QWORD *)this + 8LL))(this);
                v30 = (char *)MakeCom<MemoryTimerService::TimerHandler,unsigned short const * &,Microsoft::WRL::ComPtr<MemoryTimerService>,Microsoft::WRL::ComPtr<ILicenseTimerServiceCallback> &,unsigned long &,unsigned char * &>(
                                (unsigned int)&v45,
                                (unsigned int)v50,
                                (unsigned int)&SystemTimeAsFileTime,
                                (int)this + 16,
                                (__int64)&a5,
                                (__int64)&v48);
                v9 = 0;
                if ( &v51 != v30 )
                {
                  v9 = *(_QWORD *)v30;
                  *(_QWORD *)v30 = 0;
                }
                v46 = v9;
                v31 = v45;
                if ( v45 )
                {
                  v45 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                }
                if ( SystemTimeAsFileTime )
                  (*(void (__fastcall **)(_FILETIME))(**(_QWORD **)&SystemTimeAsFileTime + 16LL))(SystemTimeAsFileTime);
                v32 = (_QWORD *)(v9 + 56);
                v33 = std::map<std::wstring,Microsoft::WRL::ComPtr<MemoryTimerService::TimerHandler>>::_Try_emplace<std::wstring const &,>(
                        (char *)this + 64,
                        v50,
                        v9 + 56);
                v34 = *(_QWORD *)v33;
                if ( *(_QWORD *)(*(_QWORD *)v33 + 64LL) != v9 )
                {
                  if ( v9 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
                  v35 = *(_QWORD *)(v34 + 64);
                  *(_QWORD *)(v34 + 64) = v9;
                  if ( v35 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                }
                if ( *(_QWORD *)(v9 + 80) > 7u )
                  v32 = (_QWORD *)*v32;
                LogMessage(
                  3u,
                  "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\memorytimer.cpp",
                  0x39u,
                  "MemoryTimerService::CreateTimerWithId",
                  (wchar_t *)L"Added timer for %s",
                  v32);
              }
              else
              {
                v36 = v16[8];
                if ( v36 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v16[8]);
                  v9 = v36;
                  v46 = v36;
                }
              }
              if ( this != (MemoryTimerService *)-24LL )
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
              SystemTimeAsFileTime = 0;
              GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
              v37 = (double)(v47.dwLowDateTime - SystemTimeAsFileTime.dwLowDateTime) / 10.0 / 1000.0;
              v38 = (double)(int)((double)a4 * 1000.0 * 10.0) / 10.0 / 1000.0;
              *(_BYTE *)(v9 + 16) = (int)v38 == 0;
              EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 104));
              v49 = (char *)(v9 + 104);
              v39 = *(void **)(v9 + 96);
              if ( v39 )
              {
                if ( !ChangeTimerQueueTimer(0, v39, (int)v37, (int)v38) )
                  wil::details::in1diag3::_Throw_GetLastError(
                    retaddr,
                    (void *)0xB3,
                    (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\memorytimer.cpp",
                    v42);
              }
              else
              {
                if ( !CreateTimerQueueTimer(
                        (PHANDLE)(v9 + 96),
                        0,
                        MemoryTimerService::TimerHandler::TimerCallback,
                        (PVOID)v9,
                        (int)v37,
                        (int)v38,
                        0x20u) )
                  wil::details::in1diag3::_Throw_GetLastError(
                    retaddr,
                    (void *)0xAA,
                    (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\memorytimer.cpp",
                    v40);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
              }
              if ( v9 != -104 )
                LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 104));
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
              return 0;
            }
          }
          else if ( v26 >= v25 )
          {
            goto LABEL_39;
          }
        }
        v16 = *v15;
        goto LABEL_39;
      }
      v18 = (const wchar_t *)(v17 + 4);
      v19 = N;
      v20 = (const wchar_t *)S2;
      if ( v55 > 7 )
        v20 = S2[0];
      v21 = v17[6];
      if ( (unsigned __int64)v17[7] > 7 )
        v18 = *(const wchar_t **)v18;
      v22 = v17[6];
      if ( N < v21 )
        v22 = N;
      v23 = wmemcmp(v18, v20, v22);
      if ( v23 )
      {
        if ( v23 < 0 )
          goto LABEL_23;
      }
      else if ( v21 < v19 )
      {
LABEL_23:
        v17 += 2;
        goto LABEL_25;
      }
      v16 = v17;
LABEL_25:
      v17 = (__int64 *)*v17;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x44,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\memorytimer.cpp",
                           v41);
  }
  return result;
}

```

## disassembly

```asm
0x180004b20  mov     r11, rsp
0x180004b23  push    rbx
0x180004b24  push    rsi
0x180004b25  push    rdi
0x180004b26  push    r12
0x180004b28  push    r13
0x180004b2a  push    r14
0x180004b2c  push    r15
0x180004b2e  sub     rsp, 0F0h
0x180004b35  movaps  xmmword ptr [r11-48h], xmm6
0x180004b3a  movaps  xmmword ptr [r11-58h], xmm7
0x180004b3f  mov     rax, cs:__security_cookie
0x180004b46  xor     rax, rsp
0x180004b49  mov     [rsp+128h+var_60], rax
0x180004b51  mov     [rsp+128h+var_E8], r9d
0x180004b56  mov     rsi, rdx
0x180004b59  mov     r14, rcx
0x180004b5c  mov     rcx, [rsp+128h+arg_28]
0x180004b64  mov     [rsp+128h+var_B0], rdx
0x180004b69  mov     rax, r8
0x180004b6c  shr     rax, 20h
0x180004b70  mov     [rsp+128h+var_C0], rcx
0x180004b75  xor     r12d, r12d
0x180004b78  test    rcx, rcx
0x180004b7b  jnz     short loc_180004B8D
0x180004b7d  cmp     [r11+28h], r12d
0x180004b81  jz      short loc_180004B8D
0x180004b83  mov     eax, 80070057h
0x180004b88  jmp     loc_180004FC8
0x180004b8d  mov     dword ptr [rsp+128h+var_C8], r8d
0x180004b92  mov     dword ptr [rsp+128h+var_C8+4], eax
0x180004b96  mov     rbx, r12
0x180004b99  mov     [rsp+128h+var_D0], rbx
0x180004b9e  lea     rdi, [r14+18h]
0x180004ba2  mov     rcx, rdi; lpCriticalSection
0x180004ba5  call    cs:__imp_EnterCriticalSection
0x180004bab  mov     [rsp+128h+var_B8], rdi
0x180004bb0  xorps   xmm0, xmm0
0x180004bb3  movups  xmmword ptr [rsp+128h+S2], xmm0
0x180004bbb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004bbf  inc     rdi
0x180004bc2  cmp     [rsi+rdi*2], r12w
0x180004bc7  jnz     short loc_180004BBF
0x180004bc9  mov     r8, 7FFFFFFFFFFFFFFEh
0x180004bd3  cmp     rdi, r8
0x180004bd6  jbe     short loc_180004BE5
0x180004bd8  lea     rcx, aStringTooLong; "string too long"
0x180004bdf  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180004be5  mov     eax, 7
0x180004bea  cmp     rdi, rax
0x180004bed  ja      short loc_180004C20
0x180004bef  mov     [rsp+128h+N], rdi
0x180004bf7  mov     [rsp+128h+var_68], rax
0x180004bff  add     rdi, rdi
0x180004c02  mov     r8, rdi; Size
0x180004c05  mov     rdx, rsi; Src
0x180004c08  lea     rcx, [rsp+128h+S2]; void *
0x180004c10  call    memcpy_0
0x180004c15  mov     word ptr [rsp+rdi+128h+S2], r12w
0x180004c1e  jmp     short loc_180004C70
0x180004c20  mov     rdx, rax
0x180004c23  mov     rcx, rdi
0x180004c26  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180004c2b  mov     r13, rax
0x180004c2e  lea     rdx, [rax+1]
0x180004c32  lea     rcx, [rsp+128h+S2]
0x180004c3a  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180004c3f  mov     r15, rax
0x180004c42  mov     [rsp+128h+S2], rax
0x180004c4a  mov     [rsp+128h+N], rdi
0x180004c52  mov     [rsp+128h+var_68], r13
0x180004c5a  add     rdi, rdi
0x180004c5d  mov     r8, rdi; Size
0x180004c60  mov     rdx, rsi; Src
0x180004c63  mov     rcx, rax; void *
0x180004c66  call    memcpy_0
0x180004c6b  mov     [rdi+r15], r12w
0x180004c70  lea     r15, [r14+40h]
0x180004c74  mov     rsi, [r15]
0x180004c77  mov     rdi, [rsi+8]
0x180004c7b  xor     eax, eax
0x180004c7d  mov     [rsp+128h+var_8C], eax
0x180004c84  jmp     short loc_180004CED
0x180004c86  lea     rcx, [rdi+20h]
0x180004c8a  mov     r13, [rsp+128h+N]
0x180004c92  lea     rdx, [rsp+128h+S2]
0x180004c9a  cmp     [rsp+128h+var_68], 7
0x180004ca3  cmova   rdx, [rsp+128h+S2]; S2
0x180004cac  mov     r12, [rdi+30h]
0x180004cb0  cmp     qword ptr [rcx+18h], 7
0x180004cb5  jbe     short loc_180004CBA
0x180004cb7  mov     rcx, [rcx]; S1
0x180004cba  mov     r8, r12
0x180004cbd  cmp     r13, r12
0x180004cc0  cmovb   r8, r13; N
0x180004cc4  call    wmemcmp
0x180004cc9  test    eax, eax
0x180004ccb  jz      short loc_180004CD6
0x180004ccd  xor     r12d, r12d
0x180004cd0  test    eax, eax
0x180004cd2  jns     short loc_180004CE7
0x180004cd4  jmp     short loc_180004CDE
0x180004cd6  cmp     r12, r13
0x180004cd9  jnb     short loc_180004CE4
0x180004cdb  xor     r12d, r12d
0x180004cde  add     rdi, 10h
0x180004ce2  jmp     short loc_180004CEA
0x180004ce4  xor     r12d, r12d
0x180004ce7  mov     rsi, rdi
0x180004cea  mov     rdi, [rdi]
0x180004ced  cmp     [rdi+19h], r12b
0x180004cf1  jz      short loc_180004C86
0x180004cf3  cmp     [rsi+19h], r12b
0x180004cf7  jnz     short loc_180004D56
0x180004cf9  lea     rdx, [rsi+20h]
0x180004cfd  mov     rdi, [rdx+10h]
0x180004d01  cmp     qword ptr [rdx+18h], 7
0x180004d06  jbe     short loc_180004D0B
0x180004d08  mov     rdx, [rdx]; S2
0x180004d0b  mov     r12, [rsp+128h+N]
0x180004d13  lea     rcx, [rsp+128h+S2]
0x180004d1b  cmp     [rsp+128h+var_68], 7
0x180004d24  cmova   rcx, [rsp+128h+S2]; S1
0x180004d2d  mov     r8, r12
0x180004d30  cmp     rdi, r12
0x180004d33  cmovb   r8, rdi; N
0x180004d37  call    wmemcmp
0x180004d3c  test    eax, eax
0x180004d3e  jz      short loc_180004D49
0x180004d40  xor     r12d, r12d
0x180004d43  test    eax, eax
0x180004d45  js      short loc_180004D56
0x180004d47  jmp     short loc_180004D59
0x180004d49  cmp     r12, rdi
0x180004d4c  jb      short loc_180004D53
0x180004d4e  xor     r12d, r12d
0x180004d51  jmp     short loc_180004D59
0x180004d53  xor     r12d, r12d
0x180004d56  mov     rsi, [r15]
0x180004d59  lea     rcx, [rsp+128h+S2]
0x180004d61  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180004d66  cmp     rsi, [r15]
0x180004d69  jnz     loc_180004E8C
0x180004d6f  mov     qword ptr [rsp+128h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180004d74  test    r14, r14
0x180004d77  jz      short loc_180004D89
0x180004d79  mov     rax, [r14]
0x180004d7c  mov     rcx, r14
0x180004d7f  mov     rax, [rax+8]
0x180004d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d88  nop
0x180004d89  lea     r9, [r14+10h]
0x180004d8d  lea     rax, [rsp+128h+var_C0]
0x180004d92  mov     qword ptr [rsp+128h+Period], rax
0x180004d97  lea     rax, [rsp+128h+arg_20]
0x180004d9f  mov     qword ptr [rsp+128h+DueTime], rax
0x180004da4  lea     r8, [rsp+128h+SystemTimeAsFileTime]
0x180004da9  lea     rdx, [rsp+128h+var_B0]
0x180004dae  lea     rcx, [rsp+128h+var_D8]
0x180004db3  call    ??$MakeCom@VTimerHandler@MemoryTimerService@@AEAPEBGV?$ComPtr@VMemoryTimerService@@@WRL@Microsoft@@AEAV?$ComPtr@UILicenseTimerServiceCallback@@@45@AEAKAEAPEAE@@YA?AV?$ComPtr@VTimerHandler@MemoryTimerService@@@WRL@Microsoft@@AEAPEBG$$QEAV?$ComPtr@VMemoryTimerService@@@12@AEAV?$ComPtr@UILicenseTimerServiceCallback@@@12@AEAKAEAPEAE@Z; MakeCom<MemoryTimerService::TimerHandler,ushort const * &,Microsoft::WRL::ComPtr<MemoryTimerService>,Microsoft::WRL::ComPtr<ILicenseTimerServiceCallback> &,ulong &,uchar * &>(ushort const * &,Microsoft::WRL::ComPtr<MemoryTimerService> &&,Microsoft::WRL::ComPtr<ILicenseTimerServiceCallback> &,ulong &,uchar * &)
0x180004db8  mov     rbx, r12
0x180004dbb  lea     rcx, [rsp+128h+var_A0]
0x180004dc3  cmp     rcx, rax
0x180004dc6  jz      short loc_180004DCE
0x180004dc8  mov     rbx, [rax]
0x180004dcb  mov     [rax], r12
0x180004dce  mov     [rsp+128h+var_D0], rbx
0x180004dd3  mov     rcx, [rsp+128h+var_D8]
0x180004dd8  test    rcx, rcx
0x180004ddb  jz      short loc_180004DEF
0x180004ddd  mov     [rsp+128h+var_D8], r12
0x180004de2  mov     rax, [rcx]
0x180004de5  mov     rax, [rax+10h]
0x180004de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dee  nop
0x180004def  mov     rcx, qword ptr [rsp+128h+SystemTimeAsFileTime.dwLowDateTime]
0x180004df4  test    rcx, rcx
0x180004df7  jz      short loc_180004E06
0x180004df9  mov     rax, [rcx]
0x180004dfc  mov     rax, [rax+10h]
0x180004e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e05  nop
0x180004e06  lea     rdi, [rbx+38h]
0x180004e0a  mov     r8, rdi
0x180004e0d  lea     rdx, [rsp+128h+var_B0]
0x180004e12  mov     rcx, r15
0x180004e15  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VTimerHandler@MemoryTimerService@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VTimerHandler@MemoryTimerService@@@WRL@Microsoft@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VTimerHandler@MemoryTimerService@@@WRL@Microsoft@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Microsoft::WRL::ComPtr<MemoryTimerService::TimerHandler>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180004e1a  mov     rsi, [rax]
0x180004e1d  cmp     [rsi+40h], rbx
0x180004e21  jz      short loc_180004E52
0x180004e23  test    rbx, rbx
0x180004e26  jz      short loc_180004E38
0x180004e28  mov     rax, [rbx]
0x180004e2b  mov     rcx, rbx
0x180004e2e  mov     rax, [rax+8]
0x180004e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e37  nop
0x180004e38  mov     rcx, [rsi+40h]
0x180004e3c  mov     [rsi+40h], rbx
0x180004e40  test    rcx, rcx
0x180004e43  jz      short loc_180004E52
0x180004e45  mov     rax, [rcx]
0x180004e48  mov     rax, [rax+10h]
0x180004e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e51  nop
0x180004e52  cmp     qword ptr [rdi+18h], 7
0x180004e57  jbe     short loc_180004E5C
0x180004e59  mov     rdi, [rdi]
0x180004e5c  mov     qword ptr [rsp+128h+Period], rdi
0x180004e61  lea     rax, aAddedTimerForS; "Added timer for %s"
0x180004e68  mov     qword ptr [rsp+128h+DueTime], rax; Format
0x180004e6d  lea     r9, aMemorytimerser_2; "MemoryTimerService::CreateTimerWithId"
0x180004e74  mov     r8d, 39h ; '9'; unsigned int
0x180004e7a  lea     rdx, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\licensem"...
0x180004e81  lea     ecx, [r8-36h]; unsigned int
0x180004e85  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180004e8a  jmp     short loc_180004EAD
0x180004e8c  mov     rdi, [rsi+40h]
0x180004e90  test    rdi, rdi
0x180004e93  jz      short loc_180004EAD
0x180004e95  mov     rax, [rdi]
0x180004e98  mov     rcx, rdi
0x180004e9b  mov     rax, [rax+8]
0x180004e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ea4  nop
0x180004ea5  mov     rbx, rdi
0x180004ea8  mov     [rsp+128h+var_D0], rbx
0x180004ead  mov     eax, [rsp+128h+var_E8]
0x180004eb1  xorps   xmm0, xmm0
0x180004eb4  cvtsi2sd xmm0, rax
0x180004eb9  movsd   xmm6, cs:__real@408f400000000000
0x180004ec1  mulsd   xmm0, xmm6
0x180004ec5  movsd   xmm7, cs:__real@4024000000000000
0x180004ecd  mulsd   xmm0, xmm7
0x180004ed1  cvttsd2si rdi, xmm0
0x180004ed6  lea     rcx, [r14+18h]; lpCriticalSection
0x180004eda  test    rcx, rcx
0x180004edd  jz      short loc_180004EE5
0x180004edf  call    cs:__imp_LeaveCriticalSection
0x180004ee5  mov     qword ptr [rsp+128h+SystemTimeAsFileTime.dwLowDateTime], r12
0x180004eea  lea     rcx, [rsp+128h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004eef  call    cs:__imp_GetSystemTimeAsFileTime
0x180004ef5  mov     rax, [rsp+128h+var_C8]
0x180004efa  sub     rax, qword ptr [rsp+128h+SystemTimeAsFileTime.dwLowDateTime]
0x180004eff  xorps   xmm0, xmm0
0x180004f02  cvtsi2sd xmm0, rax
0x180004f07  divsd   xmm0, xmm7
0x180004f0b  divsd   xmm0, xmm6
0x180004f0f  cvttsd2si r14, xmm0
0x180004f14  xorps   xmm1, xmm1
0x180004f17  cvtsi2sd xmm1, rdi
0x180004f1c  divsd   xmm1, xmm7
0x180004f20  divsd   xmm1, xmm6
0x180004f24  cvttsd2si rsi, xmm1
0x180004f29  test    esi, esi
0x180004f2b  setz    al
0x180004f2e  mov     [rbx+10h], al
0x180004f31  lea     rdi, [rbx+68h]
0x180004f35  mov     rcx, rdi; lpCriticalSection
0x180004f38  call    cs:__imp_EnterCriticalSection
0x180004f3e  mov     [rsp+128h+var_B8], rdi
0x180004f43  lea     rcx, [rbx+60h]; phNewTimer
0x180004f47  mov     rdx, [rcx]; Timer
0x180004f4a  test    rdx, rdx
0x180004f4d  jnz     loc_180004FF9
0x180004f53  mov     [rsp+128h+Flags], 20h ; ' '; Flags
0x180004f5b  mov     [rsp+128h+Period], esi; Period
0x180004f5f  mov     [rsp+128h+DueTime], r14d; DueTime
0x180004f64  mov     r9, rbx; Parameter
0x180004f67  lea     r8, ?TimerCallback@TimerHandler@MemoryTimerService@@CAXPEAXE@Z; Callback
0x180004f6e  call    cs:__imp_CreateTimerQueueTimer
0x180004f74  mov     rcx, [rsp+128h]; this
0x180004f7c  test    eax, eax
0x180004f7e  jnz     short loc_180004F91
0x180004f80  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\licensem"...
0x180004f87  mov     edx, 0AAh; void *
0x180004f8c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180004f91  mov     rax, [rbx]
0x180004f94  mov     rcx, rbx
0x180004f97  mov     rax, [rax+8]
0x180004f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa0  nop
0x180004fa1  test    rdi, rdi
0x180004fa4  jz      short loc_180004FB0
0x180004fa6  mov     rcx, rdi; lpCriticalSection
0x180004fa9  call    cs:__imp_LeaveCriticalSection
0x180004faf  nop
0x180004fb0  mov     rax, [rbx]
0x180004fb3  mov     rcx, rbx
0x180004fb6  mov     rax, [rax+10h]
0x180004fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fbf  nop
0x180004fc0  xor     eax, eax
0x180004fc2  jmp     short loc_180004FC8
0x180004fc4  mov     eax, [rsp+128h+var_E8]
0x180004fc8  mov     rcx, [rsp+128h+var_60]
0x180004fd0  xor     rcx, rsp; StackCookie
0x180004fd3  call    __security_check_cookie
0x180004fd8  lea     r11, [rsp+128h+var_38]
0x180004fe0  movaps  xmm6, xmmword ptr [r11-10h]
  ... truncated ...
```
