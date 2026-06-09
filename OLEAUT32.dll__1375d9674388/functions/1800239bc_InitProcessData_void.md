# InitProcessData(void)

- ea: `0x1800239bc`
- end: `0x180023e27`
- name: `?InitProcessData@@YAJXZ`
- size: `1131`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007a2bc`

## callees

- `0x1800239bc`
- `0x180023e30`
- `0x180023e90`
- `0x180023ee8`
- `0x180023f54`
- `0x18004d900`
- `0x18004e530`
- `0x18004e5f4`
- `0x180059d70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023a66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023a66`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180023b88`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180023b88`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180023dff`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180023dff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d97`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800239fc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180023a18`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800239fc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180023a18`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180023d10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180023d45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180023d7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180023d10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180023d45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180023d7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023d8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023d8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180023b28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180023b28`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180023a76`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180023a76`

## string_xrefs

- `0x180023a33`: `OANOCACHE`
- `0x180023ba3`: `OACACHEPARAMS`

## pseudocode

```c
signed int InitProcessData(void)
{
  signed int result; // eax
  HANDLE CurrentProcess; // rax
  const char *Env; // rax
  __m128 v3; // xmm0
  __m128 v4; // xmm2
  __m128 v5; // xmm1
  __m128i v6; // xmm3
  unsigned int v7; // edx
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // eax
  DWORD Type; // [rsp+40h] [rbp-30h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD cbData; // [rsp+48h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  __m128i v15; // [rsp+58h] [rbp-18h] BYREF

  hKey = 0;
  if ( g_itlsAppData == -1 )
  {
    g_itlsAppData = TlsAlloc();
    if ( g_itlsAppData == -1 )
      return -2147024882;
  }
  if ( InitializeCriticalSectionAndSpinCount(&g_OletmgrCriticalSection, 0) )
    goto LABEL_51;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  g_OletmgrCriticalSection.SpinCount = 0;
  *(_OWORD *)&g_OletmgrCriticalSection.DebugInfo = 0;
  *(_OWORD *)&g_OletmgrCriticalSection.OwningThread = 0;
  if ( result >= 0 )
  {
LABEL_51:
    if ( InitializeCriticalSectionAndSpinCount(&g_OldFormatCriticalSection, 0) )
      goto LABEL_4;
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    g_OldFormatCriticalSection.SpinCount = 0;
    *(_OWORD *)&g_OldFormatCriticalSection.DebugInfo = 0;
    *(_OWORD *)&g_OldFormatCriticalSection.OwningThread = 0;
    if ( result >= 0 )
    {
LABEL_4:
      result = InitRecordInfo();
      if ( result >= 0 )
      {
        if ( OaGetEnv("OANOCACHE") )
          g_fDebNoCache = 1;
        if ( OaGetEnv("OAPERUSERTLIBREG") )
          g_fOaPerUserTlibReg = 1;
        CurrentProcess = GetCurrentProcess();
        if ( IsWow64Process(CurrentProcess, &g_fIsWow64Process) )
        {
          if ( !g_fDebNoCache )
          {
            Env = OaGetEnv("OACACHEPARAMS");
            if ( Env )
            {
              v15 = 0u;
              sscanf_s(
                Env,
                "%d,%d,%d,%d:%hd",
                (char *)&v15.m128i_u64[1] + 4,
                &v15.m128i_u64[1],
                (char *)v15.m128i_i64 + 4,
                &v15,
                &word_1800C2914);
              if ( (unsigned __int16)(word_1800C2914 - 1) > 5u )
                word_1800C2914 = 6;
              v3 = (__m128)_mm_loadu_si128(&v15);
              v4 = (__m128)_mm_cmpeq_epi32((__m128i)0LL, (__m128i)v3);
              v5 = _mm_or_ps(_mm_andnot_ps(v4, v3), _mm_and_ps(v4, *(__m128 *)&dwBucketSize));
              v6 = (__m128i)_mm_or_ps(
                              _mm_andnot_ps(
                                v4,
                                _mm_and_ps(
                                  (__m128)_mm_add_epi32(_mm_load_si128((const __m128i *)&_xmm), (__m128i)v5),
                                  (__m128)_xmm_fffffff0fffffff0fffffff0fffffff0)),
                              _mm_and_ps(v5, v4));
              v7 = _mm_cvtsi128_si32(v6);
              v8 = _mm_cvtsi128_si32(_mm_srli_si128(v6, 4));
              if ( v7 < v8 )
              {
                v9 = _mm_cvtsi128_si32(_mm_srli_si128(v6, 8));
                if ( v8 < v9 )
                {
                  v10 = _mm_cvtsi128_si32(_mm_srli_si128(v6, 12));
                  if ( v9 < v10 && v7 >= 0x10 && v10 <= 0x20000 )
                    *(__m128i *)&dwBucketSize = v6;
                }
              }
            }
          }
          result = InitDateInfo(1);
          if ( result >= 0 )
          {
            result = OaInitializeCriticalSectionAndSpinCount(&NumInfo_csCacheLock, 1000);
            if ( result > -1 )
            {
              result = OaInitializeCriticalSectionAndSpinCount(&CVtableSizeCache::critsec, 1000);
              if ( result >= 0 )
              {
                memset_0(qword_1800C3840, 0, 0x8D4u);
                CVtableSizeCache::pCache = (struct CVtableSizeCache::VtableSize *)qword_1800C3840;
                CVtableSizeCache::cSize = 113;
                CVtableSizeCache::cPopulationLimit = 113;
                CVtableSizeCache::cPopulation = 0;
                if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\OLEAUT", 0, 1u, &hKey) )
                {
                  Type = 0;
                  *(_DWORD *)Data = 0;
                  cbData = 4;
                  if ( !RegQueryValueExA(hKey, "VarConversionLocaleSetting", 0, &Type, Data, &cbData) && Type == 4 )
                    SetVarConversionLocaleSetting(*(unsigned int *)Data);
                  cbData = 4;
                  if ( !RegQueryValueExA(hKey, "BreakOnLoad", 0, &Type, Data, &cbData)
                    && Type == 4
                    && *(_DWORD *)Data == 1 )
                  {
                    DebugBreak();
                  }
                  cbData = 4;
                  if ( !RegQueryValueExA(hKey, "ReleaseMarshalBuffers", 0, &Type, Data, &cbData)
                    && Type == 4
                    && *(_DWORD *)Data == 1 )
                  {
                    g_bReleaseMarshalBuffers = 1;
                  }
                  RegCloseKey(hKey);
                }
                return 0;
              }
            }
          }
        }
        else
        {
          result = GetLastError();
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800239bc  mov     [rsp-8+arg_0], rbx
0x1800239c1  mov     [rsp-8+arg_8], rsi
0x1800239c6  push    rbp
0x1800239c7  mov     rbp, rsp
0x1800239ca  sub     rsp, 70h
0x1800239ce  mov     rax, cs:__security_cookie
0x1800239d5  xor     rax, rsp
0x1800239d8  mov     [rbp+var_8], rax
0x1800239dc  or      ebx, 0FFFFFFFFh
0x1800239df  mov     [rbp+hKey], 0
0x1800239e7  cmp     cs:?g_itlsAppData@@3KA, ebx; ulong g_itlsAppData
0x1800239ed  jz      loc_180023B88
0x1800239f3  xor     edx, edx; dwSpinCount
0x1800239f5  lea     rcx, ?g_OletmgrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800239fc  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180023a02  mov     ebx, 80070000h
0x180023a07  test    eax, eax
0x180023a09  jz      loc_180023B3A
0x180023a0f  xor     edx, edx; dwSpinCount
0x180023a11  lea     rcx, ?g_OldFormatCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023a18  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180023a1e  test    eax, eax
0x180023a20  jz      loc_180023D97
0x180023a26  call    ?InitRecordInfo@@YAJXZ; InitRecordInfo(void)
0x180023a2b  test    eax, eax
0x180023a2d  js      loc_180023B6A
0x180023a33  lea     rcx, Name; "OANOCACHE"
0x180023a3a  call    ?OaGetEnv@@YAPEADPEBD@Z; OaGetEnv(char const *)
0x180023a3f  mov     esi, 1
0x180023a44  test    rax, rax
0x180023a47  jz      short loc_180023A4F
0x180023a49  mov     cs:?g_fDebNoCache@@3HA, esi; int g_fDebNoCache
0x180023a4f  lea     rcx, aOaperusertlibr; "OAPERUSERTLIBREG"
0x180023a56  call    ?OaGetEnv@@YAPEADPEBD@Z; OaGetEnv(char const *)
0x180023a5b  test    rax, rax
0x180023a5e  jz      short loc_180023A66
0x180023a60  mov     cs:?g_fOaPerUserTlibReg@@3HA, esi; int g_fOaPerUserTlibReg
0x180023a66  call    cs:__imp_GetCurrentProcess
0x180023a6c  mov     rcx, rax; hProcess
0x180023a6f  lea     rdx, ?g_fIsWow64Process@@3HA; Wow64Process
0x180023a76  call    cs:__imp_IsWow64Process
0x180023a7c  test    eax, eax
0x180023a7e  jz      loc_180023CBE
0x180023a84  cmp     cs:?g_fDebNoCache@@3HA, 0; int g_fDebNoCache
0x180023a8b  jz      loc_180023BA3
0x180023a91  mov     ecx, esi; int
0x180023a93  call    ?InitDateInfo@@YAJH@Z; InitDateInfo(int)
0x180023a98  test    eax, eax
0x180023a9a  js      loc_180023B6A
0x180023aa0  mov     ebx, 3E8h
0x180023aa5  lea     rcx, ?NumInfo_csCacheLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION NumInfo_csCacheLock
0x180023aac  mov     edx, ebx
0x180023aae  call    OaInitializeCriticalSectionAndSpinCount
0x180023ab3  cmp     eax, 0FFFFFFFFh
0x180023ab6  jle     loc_180023B6A
0x180023abc  mov     edx, ebx
0x180023abe  lea     rcx, ?critsec@CVtableSizeCache@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CVtableSizeCache::critsec
0x180023ac5  call    OaInitializeCriticalSectionAndSpinCount
0x180023aca  test    eax, eax
0x180023acc  js      loc_180023B6A
0x180023ad2  lea     rbx, qword_1800C3840
0x180023ad9  xor     edx, edx; Val
0x180023adb  mov     rcx, rbx; void *
0x180023ade  mov     r8d, 8D4h; Size
0x180023ae4  call    memset_0
0x180023ae9  mov     eax, 71h ; 'q'
0x180023aee  mov     cs:?pCache@CVtableSizeCache@@0PEAUVtableSize@1@EA, rbx; CVtableSizeCache::VtableSize * CVtableSizeCache::pCache
0x180023af5  mov     cs:?cSize@CVtableSizeCache@@0KA, eax; ulong CVtableSizeCache::cSize
0x180023afb  mov     cs:?cPopulationLimit@CVtableSizeCache@@0KA, eax; ulong CVtableSizeCache::cPopulationLimit
0x180023b01  mov     cs:?cPopulation@CVtableSizeCache@@0KA, 0; ulong CVtableSizeCache::cPopulation
0x180023b0b  lea     rax, [rbp+hKey]
0x180023b0f  mov     r9d, esi; samDesired
0x180023b12  xor     r8d, r8d; ulOptions
0x180023b15  mov     [rsp+70h+phkResult], rax; phkResult
0x180023b1a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\OLEAUT"
0x180023b21  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023b28  call    cs:__imp_RegOpenKeyExA
0x180023b2e  test    eax, eax
0x180023b30  jz      loc_180023CD6
0x180023b36  xor     eax, eax
0x180023b38  jmp     short loc_180023B6A
0x180023b3a  call    cs:__imp_GetLastError
0x180023b40  test    eax, eax
0x180023b42  jg      loc_180023DCD
0x180023b48  xor     ecx, ecx
0x180023b4a  xorps   xmm0, xmm0
0x180023b4d  mov     cs:?g_OletmgrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A.SpinCount, rcx; _RTL_CRITICAL_SECTION g_OletmgrCriticalSection ...
0x180023b54  movups  xmmword ptr cs:?g_OletmgrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A.DebugInfo, xmm0; _RTL_CRITICAL_SECTION g_OletmgrCriticalSection ...
0x180023b5b  movups  xmmword ptr cs:?g_OletmgrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, xmm0; _RTL_CRITICAL_SECTION g_OletmgrCriticalSection ...
0x180023b62  test    eax, eax
0x180023b64  jns     loc_180023A0F
0x180023b6a  mov     rcx, [rbp+var_8]
0x180023b6e  xor     rcx, rsp; StackCookie
0x180023b71  call    __security_check_cookie
0x180023b76  lea     r11, [rsp+70h+var_s0]
0x180023b7b  mov     rbx, [r11+10h]
0x180023b7f  mov     rsi, [r11+18h]
0x180023b83  mov     rsp, r11
0x180023b86  pop     rbp
0x180023b87  retn
0x180023b88  call    cs:__imp_TlsAlloc
0x180023b8e  mov     cs:?g_itlsAppData@@3KA, eax; ulong g_itlsAppData
0x180023b94  cmp     eax, ebx
0x180023b96  jnz     loc_1800239F3
0x180023b9c  mov     eax, 8007000Eh
0x180023ba1  jmp     short loc_180023B6A
0x180023ba3  lea     rcx, aOacacheparams; "OACACHEPARAMS"
0x180023baa  call    ?OaGetEnv@@YAPEADPEBD@Z; OaGetEnv(char const *)
0x180023baf  test    rax, rax
0x180023bb2  jz      loc_180023A91
0x180023bb8  lea     rcx, word_1800C2914
0x180023bbf  mov     qword ptr [rbp+var_18], 0
0x180023bc7  mov     [rsp+70h+var_40], rcx
0x180023bcc  lea     r9, [rbp+var_18+8]
0x180023bd0  lea     rcx, [rbp+var_18]
0x180023bd4  mov     qword ptr [rbp+var_18+8], 0
0x180023bdc  mov     [rsp+70h+lpcbData], rcx
0x180023be1  lea     r8, [rbp+var_18+0Ch]
0x180023be5  lea     rcx, [rbp+var_18+4]
0x180023be9  mov     [rsp+70h+phkResult], rcx
0x180023bee  lea     rdx, Format; "%d,%d,%d,%d:%hd"
0x180023bf5  mov     rcx, rax; Buffer
0x180023bf8  call    sscanf_s
0x180023bfd  movzx   eax, cs:word_1800C2914
0x180023c04  sub     ax, si
0x180023c07  cmp     ax, 5
0x180023c0b  jbe     short loc_180023C19
0x180023c0d  mov     eax, 6
0x180023c12  mov     cs:word_1800C2914, ax
0x180023c19  movdqu  xmm0, [rbp+var_18]
0x180023c1e  xorps   xmm2, xmm2
0x180023c21  pcmpeqd xmm2, xmm0
0x180023c25  movdqa  xmm1, xmm2
0x180023c29  movdqa  xmm3, xmm2
0x180023c2d  andnps  xmm1, xmm0
0x180023c30  movdqa  xmm0, xmm2
0x180023c34  andps   xmm0, cs:?dwBucketSize@@3PAKA; ulong near * dwBucketSize
0x180023c3b  orps    xmm1, xmm0
0x180023c3e  movdqa  xmm0, cs:__xmm@0000000f0000000f0000000f0000000f
0x180023c46  paddd   xmm0, xmm1
0x180023c4a  andps   xmm1, xmm2
0x180023c4d  andps   xmm0, cs:__xmm@fffffff0fffffff0fffffff0fffffff0
0x180023c54  andnps  xmm3, xmm0
0x180023c57  orps    xmm3, xmm1
0x180023c5a  movdqa  xmm0, xmm3
0x180023c5e  movd    edx, xmm3
0x180023c62  psrldq  xmm0, 4
0x180023c67  movd    eax, xmm0
0x180023c6b  cmp     edx, eax
0x180023c6d  jnb     loc_180023A91
0x180023c73  movdqa  xmm0, xmm3
0x180023c77  psrldq  xmm0, 8
0x180023c7c  movd    ecx, xmm0
0x180023c80  cmp     eax, ecx
0x180023c82  jnb     loc_180023A91
0x180023c88  movdqa  xmm0, xmm3
0x180023c8c  psrldq  xmm0, 0Ch
0x180023c91  movd    eax, xmm0
0x180023c95  cmp     ecx, eax
0x180023c97  jnb     loc_180023A91
0x180023c9d  cmp     edx, 10h
0x180023ca0  jb      loc_180023A91
0x180023ca6  cmp     eax, 20000h
0x180023cab  ja      loc_180023A91
0x180023cb1  movdqu  cs:?dwBucketSize@@3PAKA, xmm3; ulong near * dwBucketSize
0x180023cb9  jmp     loc_180023A91
0x180023cbe  call    cs:__imp_GetLastError
0x180023cc4  test    eax, eax
0x180023cc6  jle     loc_180023B6A
0x180023ccc  movzx   eax, ax
0x180023ccf  or      eax, ebx
0x180023cd1  jmp     loc_180023B6A
0x180023cd6  mov     rcx, [rbp+hKey]; hKey
0x180023cda  lea     rax, [rbp+cbData]
0x180023cde  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180023ce3  lea     r9, [rbp+Type]; lpType
0x180023ce7  lea     rax, [rbp+Data]
0x180023ceb  mov     [rbp+Type], 0
0x180023cf2  mov     ebx, 4
0x180023cf7  mov     [rsp+70h+phkResult], rax; lpData
0x180023cfc  xor     r8d, r8d; lpReserved
0x180023cff  mov     dword ptr [rbp+Data], 0
0x180023d06  lea     rdx, aVarconversionl; "VarConversionLocaleSetting"
0x180023d0d  mov     [rbp+cbData], ebx
0x180023d10  call    cs:__imp_RegQueryValueExA
0x180023d16  test    eax, eax
0x180023d18  jz      loc_180023DD7
0x180023d1e  mov     rcx, [rbp+hKey]; hKey
0x180023d22  lea     rax, [rbp+cbData]
0x180023d26  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180023d2b  lea     r9, [rbp+Type]; lpType
0x180023d2f  lea     rax, [rbp+Data]
0x180023d33  mov     [rbp+cbData], ebx
0x180023d36  xor     r8d, r8d; lpReserved
0x180023d39  mov     [rsp+70h+phkResult], rax; lpData
0x180023d3e  lea     rdx, aBreakonload; "BreakOnLoad"
0x180023d45  call    cs:__imp_RegQueryValueExA
0x180023d4b  test    eax, eax
0x180023d4d  jz      loc_180023DED
0x180023d53  mov     rcx, [rbp+hKey]; hKey
0x180023d57  lea     rax, [rbp+cbData]
0x180023d5b  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180023d60  lea     r9, [rbp+Type]; lpType
0x180023d64  lea     rax, [rbp+Data]
0x180023d68  mov     [rbp+cbData], ebx
0x180023d6b  xor     r8d, r8d; lpReserved
0x180023d6e  mov     [rsp+70h+phkResult], rax; lpData
0x180023d73  lea     rdx, aReleasemarshal; "ReleaseMarshalBuffers"
0x180023d7a  call    cs:__imp_RegQueryValueExA
0x180023d80  test    eax, eax
0x180023d82  jz      loc_180023E0A
0x180023d88  mov     rcx, [rbp+hKey]; hKey
0x180023d8c  call    cs:__imp_RegCloseKey
0x180023d92  jmp     loc_180023B36
0x180023d97  call    cs:__imp_GetLastError
0x180023d9d  test    eax, eax
0x180023d9f  jle     short loc_180023DA6
0x180023da1  movzx   eax, ax
0x180023da4  or      eax, ebx
0x180023da6  xor     ecx, ecx
0x180023da8  xorps   xmm0, xmm0
0x180023dab  mov     cs:?g_OldFormatCriticalSection@@3U_RTL_CRITICAL_SECTION@@A.SpinCount, rcx; _RTL_CRITICAL_SECTION g_OldFormatCriticalSection ...
0x180023db2  movups  xmmword ptr cs:?g_OldFormatCriticalSection@@3U_RTL_CRITICAL_SECTION@@A.DebugInfo, xmm0; _RTL_CRITICAL_SECTION g_OldFormatCriticalSection ...
0x180023db9  movups  xmmword ptr cs:?g_OldFormatCriticalSection@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, xmm0; _RTL_CRITICAL_SECTION g_OldFormatCriticalSection ...
0x180023dc0  test    eax, eax
0x180023dc2  js      loc_180023B6A
0x180023dc8  jmp     loc_180023A26
0x180023dcd  movzx   eax, ax
0x180023dd0  or      eax, ebx
0x180023dd2  jmp     loc_180023B48
0x180023dd7  cmp     [rbp+Type], ebx
0x180023dda  jnz     loc_180023D1E
0x180023de0  mov     ecx, dword ptr [rbp+Data]
0x180023de3  call    SetVarConversionLocaleSetting
0x180023de8  jmp     loc_180023D1E
0x180023ded  cmp     [rbp+Type], ebx
0x180023df0  jnz     loc_180023D53
0x180023df6  cmp     dword ptr [rbp+Data], esi
0x180023df9  jnz     loc_180023D53
0x180023dff  call    cs:__imp_DebugBreak
0x180023e05  jmp     loc_180023D53
0x180023e0a  cmp     [rbp+Type], ebx
0x180023e0d  jnz     loc_180023D88
0x180023e13  cmp     dword ptr [rbp+Data], esi
0x180023e16  jnz     loc_180023D88
0x180023e1c  mov     cs:?g_bReleaseMarshalBuffers@@3HA, esi; int g_bReleaseMarshalBuffers
0x180023e22  jmp     loc_180023D88
```
