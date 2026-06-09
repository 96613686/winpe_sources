# gpm::TraceProvider::OnSamplingFrequency(PresentTraceConsumerCore::Counters const &)

- ea: `0x180012c84`
- end: `0x180013069`
- name: `?OnSamplingFrequency@TraceProvider@gpm@@SAXAEBUCounters@PresentTraceConsumerCore@@@Z`
- size: `997`
- prototype: `void __fastcall(const struct Counters *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180011fa0`

## callees

- `0x1800018ac`
- `0x180001a40`
- `0x180003ab0`
- `0x1800047f0`
- `0x180010f1c`
- `0x180012040`
- `0x1800121a0`
- `0x180012c84`
- `0x180013344`
- `0x18001338c`
- `0x180022f54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012cc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012cc8`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180012cd9`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180012cd9`

## string_xrefs

- `0x180012cea`: `onecoreuap\windows\directx\dxg\gpm\service\traceprovider.cpp`

## pseudocode

```c
void __fastcall gpm::TraceProvider::OnSamplingFrequency(const struct Counters *a1)
{
  HANDLE CurrentProcess; // rax
  __int64 v3; // rcx
  const char *v4; // r9
  int v5; // edx
  __int64 v6; // r8
  __int64 v7; // r9
  const char *v8; // rax
  unsigned int v9; // ebx
  __int64 v10; // [rsp+120h] [rbp-80h] BYREF
  int v11; // [rsp+128h] [rbp-78h] BYREF
  int v12; // [rsp+12Ch] [rbp-74h] BYREF
  int v13; // [rsp+130h] [rbp-70h] BYREF
  int v14; // [rsp+134h] [rbp-6Ch] BYREF
  int v15; // [rsp+138h] [rbp-68h] BYREF
  int v16; // [rsp+13Ch] [rbp-64h] BYREF
  int v17; // [rsp+140h] [rbp-60h] BYREF
  int v18; // [rsp+144h] [rbp-5Ch] BYREF
  int v19; // [rsp+148h] [rbp-58h] BYREF
  int v20; // [rsp+14Ch] [rbp-54h] BYREF
  int v21; // [rsp+150h] [rbp-50h] BYREF
  DWORD cb; // [rsp+154h] [rbp-4Ch] BYREF
  DWORD PageFaultCount; // [rsp+158h] [rbp-48h] BYREF
  int v24; // [rsp+15Ch] [rbp-44h] BYREF
  int v25; // [rsp+160h] [rbp-40h] BYREF
  __int64 v26; // [rsp+168h] [rbp-38h] BYREF
  const char *v27; // [rsp+170h] [rbp-30h] BYREF
  __int64 v28; // [rsp+178h] [rbp-28h] BYREF
  __int64 v29; // [rsp+180h] [rbp-20h] BYREF
  __int64 v30; // [rsp+188h] [rbp-18h] BYREF
  __int64 v31; // [rsp+190h] [rbp-10h] BYREF
  SIZE_T QuotaNonPagedPoolUsage; // [rsp+198h] [rbp-8h] BYREF
  SIZE_T QuotaPeakNonPagedPoolUsage; // [rsp+1A0h] [rbp+0h] BYREF
  SIZE_T QuotaPagedPoolUsage; // [rsp+1A8h] [rbp+8h] BYREF
  SIZE_T QuotaPeakPagedPoolUsage; // [rsp+1B0h] [rbp+10h] BYREF
  SIZE_T WorkingSetSize; // [rsp+1B8h] [rbp+18h] BYREF
  SIZE_T PeakWorkingSetSize; // [rsp+1C0h] [rbp+20h] BYREF
  SIZE_T PeakPagefileUsage; // [rsp+1C8h] [rbp+28h] BYREF
  __int64 v39; // [rsp+1D0h] [rbp+30h] BYREF
  __int64 v40; // [rsp+1D8h] [rbp+38h] BYREF
  int v41; // [rsp+1E0h] [rbp+40h]
  const struct Counters *v42; // [rsp+1E8h] [rbp+48h] BYREF
  int v43; // [rsp+1F0h] [rbp+50h]
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+200h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+C8h]

  memset_0(&ppsmemCounters, 0, 0x50u);
  ppsmemCounters.cb = 80;
  CurrentProcess = GetCurrentProcess();
  if ( !K32GetProcessMemoryInfo(CurrentProcess, &ppsmemCounters, ppsmemCounters.cb) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\traceprovider.cpp",
      v4);
  if ( (unsigned int)dword_180042048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180042048, 1) )
  {
    v11 = *((_DWORD *)a1 + 48);
    v39 = (__int64)a1 + 176;
    v26 = *((_QWORD *)a1 + 17);
    v8 = (char *)a1 + 144;
    if ( *((_QWORD *)a1 + 21) > 0xFu )
      v8 = *(const char **)v8;
    v27 = v8;
    v28 = *((_QWORD *)a1 + 14);
    v29 = *((_QWORD *)a1 + 13);
    v30 = *((_QWORD *)a1 + 16);
    v31 = *((_QWORD *)a1 + 15);
    v12 = *((_DWORD *)a1 + 22);
    v13 = *((_DWORD *)a1 + 21);
    v14 = *((_DWORD *)a1 + 20);
    v15 = *((_DWORD *)a1 + 18);
    v16 = *((_DWORD *)a1 + 17);
    v17 = *((_DWORD *)a1 + 23);
    v18 = *((_DWORD *)a1 + 16);
    v19 = *((_DWORD *)a1 + 14);
    v20 = *((_DWORD *)a1 + 12);
    v21 = *((_DWORD *)a1 + 10);
    v40 = (__int64)a1 + 20;
    v41 = 20;
    v43 = 20;
    cb = ppsmemCounters.cb;
    QuotaNonPagedPoolUsage = ppsmemCounters.QuotaNonPagedPoolUsage;
    QuotaPeakNonPagedPoolUsage = ppsmemCounters.QuotaPeakNonPagedPoolUsage;
    QuotaPagedPoolUsage = ppsmemCounters.QuotaPagedPoolUsage;
    QuotaPeakPagedPoolUsage = ppsmemCounters.QuotaPeakPagedPoolUsage;
    WorkingSetSize = ppsmemCounters.WorkingSetSize;
    PeakWorkingSetSize = ppsmemCounters.PeakWorkingSetSize;
    PeakPagefileUsage = ppsmemCounters.PeakPagefileUsage;
    PageFaultCount = ppsmemCounters.PageFaultCount;
    v42 = a1;
    v24 = 5;
    v25 = v5;
    v10 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v3,
      (__int64)&word_18003A05E,
      v6,
      v7,
      (__int64)&v10,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&PageFaultCount,
      (__int64)&PeakPagefileUsage,
      (__int64)&PeakWorkingSetSize,
      (__int64)&WorkingSetSize,
      (__int64)&QuotaPeakPagedPoolUsage,
      (__int64)&QuotaPagedPoolUsage,
      (__int64)&QuotaPeakNonPagedPoolUsage,
      (__int64)&QuotaNonPagedPoolUsage,
      (__int64)&cb,
      (__int64 *)&v42,
      &v40,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      &v27,
      (__int64)&v26,
      &v39,
      (__int64)&v11);
  }
  if ( *((_DWORD *)a1 + 17) > 0xE10u )
  {
    v9 = (int)((double)*((int *)a1 + 18) / (double)*((int *)a1 + 17) * 100.0);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::GetCachedVariantState(v3, &v10);
    if ( v9 >= HIDWORD(v10)
      && ((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::GetImpl'::`2'::impl) == 2
       || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::GetImpl'::`2'::impl) == 3
       && !IsContainer()) )
    {
      __fastfail(7u);
    }
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::GetCachedVariantState(v3, &v10);
  if ( *((_QWORD *)a1 + 13) >= (unsigned __int64)HIDWORD(v10)
    && ((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::GetImpl'::`2'::impl) == 2
     || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::GetImpl'::`2'::impl) == 3
     && !IsContainer()) )
  {
    __fastfail(7u);
  }
}

```

## disassembly

```asm
0x180012c84  mov     [rsp-8+arg_0], rbx
0x180012c89  mov     [rsp-8+arg_8], rdi
0x180012c8e  push    rbp
0x180012c8f  lea     rbp, [rsp-0C0h]
0x180012c97  sub     rsp, 260h
0x180012c9e  mov     rax, cs:__security_cookie
0x180012ca5  xor     rax, rsp
0x180012ca8  mov     [rbp+0C0h+var_10], rax
0x180012caf  mov     rdi, rcx
0x180012cb2  mov     ebx, 50h ; 'P'
0x180012cb7  mov     r8d, ebx; Size
0x180012cba  lea     rcx, [rbp+0C0h+ppsmemCounters]; void *
0x180012cbe  xor     edx, edx; Val
0x180012cc0  call    memset_0
0x180012cc5  mov     [rbp+0C0h+ppsmemCounters.cb], ebx
0x180012cc8  call    cs:__imp_GetCurrentProcess
0x180012cce  mov     r8d, [rbp+0C0h+ppsmemCounters.cb]; cb
0x180012cd2  lea     rdx, [rbp+0C0h+ppsmemCounters]; ppsmemCounters
0x180012cd6  mov     rcx, rax; Process
0x180012cd9  call    cs:__imp_K32GetProcessMemoryInfo
0x180012cdf  test    eax, eax
0x180012ce1  jnz     short loc_180012CF9
0x180012ce3  mov     rcx, [rbp+0C8h]; this
0x180012cea  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x180012cf1  lea     edx, [rbx+33h]; void *
0x180012cf4  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180012cf9  mov     eax, cs:dword_180042048
0x180012cff  cmp     eax, 5
0x180012d02  jbe     loc_180012F95
0x180012d08  mov     edx, 1
0x180012d0d  lea     rcx, dword_180042048
0x180012d14  call    _tlgKeywordOn
0x180012d19  test    al, al
0x180012d1b  jz      loc_180012F95
0x180012d21  mov     eax, [rdi+0C0h]
0x180012d27  mov     [rbp+0C0h+var_138], eax
0x180012d2a  lea     rax, [rdi+0B0h]
0x180012d31  mov     [rbp+0C0h+var_90], rax
0x180012d35  mov     rax, [rdi+88h]
0x180012d3c  mov     [rbp+0C0h+var_F8], rax
0x180012d40  lea     rax, [rdi+90h]
0x180012d47  cmp     qword ptr [rax+18h], 0Fh
0x180012d4c  jbe     short loc_180012D51
0x180012d4e  mov     rax, [rax]
0x180012d51  mov     [rbp+0C0h+var_F0], rax
0x180012d55  mov     rax, [rdi+70h]
0x180012d59  mov     [rbp+0C0h+var_E8], rax
0x180012d5d  mov     rax, [rdi+68h]
0x180012d61  mov     [rbp+0C0h+var_E0], rax
0x180012d65  mov     rax, [rdi+80h]
0x180012d6c  mov     [rbp+0C0h+var_D8], rax
0x180012d70  mov     rax, [rdi+78h]
0x180012d74  mov     [rbp+0C0h+var_D0], rax
0x180012d78  mov     eax, [rdi+58h]
0x180012d7b  mov     [rbp+0C0h+var_134], eax
0x180012d7e  mov     eax, [rdi+54h]
0x180012d81  mov     [rbp+0C0h+var_130], eax
0x180012d84  mov     eax, [rdi+50h]
0x180012d87  mov     [rbp+0C0h+var_12C], eax
0x180012d8a  mov     eax, [rdi+48h]
0x180012d8d  mov     [rbp+0C0h+var_128], eax
0x180012d90  mov     eax, [rdi+44h]
0x180012d93  mov     [rbp+0C0h+var_124], eax
0x180012d96  mov     eax, [rdi+5Ch]
0x180012d99  mov     [rbp+0C0h+var_120], eax
0x180012d9c  mov     eax, [rdi+40h]
0x180012d9f  mov     [rbp+0C0h+var_11C], eax
0x180012da2  mov     eax, [rdi+38h]
0x180012da5  mov     [rbp+0C0h+var_118], eax
0x180012da8  mov     eax, [rdi+30h]
0x180012dab  mov     [rbp+0C0h+var_114], eax
0x180012dae  mov     eax, [rdi+28h]
0x180012db1  mov     [rbp+0C0h+var_110], eax
0x180012db4  lea     rax, [rdi+14h]
0x180012db8  mov     [rbp+0C0h+var_88], rax
0x180012dbc  mov     eax, 14h
0x180012dc1  mov     [rbp+0C0h+var_80], eax
0x180012dc4  mov     [rbp+0C0h+var_70], eax
0x180012dc7  mov     eax, [rbp+0C0h+ppsmemCounters.cb]
0x180012dca  mov     [rbp+0C0h+var_10C], eax
0x180012dcd  mov     rax, [rbp+0C0h+ppsmemCounters.QuotaNonPagedPoolUsage]
0x180012dd4  mov     [rbp+0C0h+var_C8], rax
0x180012dd8  mov     rax, [rbp+0C0h+ppsmemCounters.QuotaPeakNonPagedPoolUsage]
0x180012ddf  mov     [rbp+0C0h+var_C0], rax
0x180012de3  mov     rax, [rbp+0C0h+ppsmemCounters.QuotaPagedPoolUsage]
0x180012dea  mov     [rbp+0C0h+var_B8], rax
0x180012dee  mov     rax, [rbp+0C0h+ppsmemCounters.QuotaPeakPagedPoolUsage]
0x180012df2  mov     [rbp+0C0h+var_B0], rax
0x180012df6  mov     rax, [rbp+0C0h+ppsmemCounters.WorkingSetSize]
0x180012dfa  mov     [rbp+0C0h+var_A8], rax
0x180012dfe  mov     rax, [rbp+0C0h+ppsmemCounters.PeakWorkingSetSize]
0x180012e02  mov     [rbp+0C0h+var_A0], rax
0x180012e06  mov     rax, [rbp+0C0h+ppsmemCounters.PeakPagefileUsage]
0x180012e0d  mov     [rbp+0C0h+var_98], rax
0x180012e11  mov     eax, [rbp+0C0h+ppsmemCounters.PageFaultCount]
0x180012e14  mov     [rbp+0C0h+var_108], eax
0x180012e17  lea     rax, [rbp+0C0h+var_138]
0x180012e1b  mov     [rsp+260h+var_148], rax
0x180012e23  lea     rax, [rbp+0C0h+var_90]
0x180012e27  mov     [rsp+260h+var_150], rax
0x180012e2f  lea     rax, [rbp+0C0h+var_F8]
0x180012e33  mov     [rsp+260h+var_158], rax
0x180012e3b  lea     rax, [rbp+0C0h+var_F0]
0x180012e3f  mov     [rsp+260h+var_160], rax
0x180012e47  lea     rax, [rbp+0C0h+var_E8]
0x180012e4b  mov     [rsp+260h+var_168], rax
0x180012e53  lea     rax, [rbp+0C0h+var_E0]
0x180012e57  mov     [rsp+260h+var_170], rax
0x180012e5f  lea     rax, [rbp+0C0h+var_D8]
0x180012e63  mov     [rsp+260h+var_178], rax
0x180012e6b  lea     rax, [rbp+0C0h+var_D0]
0x180012e6f  mov     [rsp+260h+var_180], rax
0x180012e77  lea     rax, [rbp+0C0h+var_134]
0x180012e7b  mov     [rsp+260h+var_188], rax
0x180012e83  lea     rax, [rbp+0C0h+var_130]
0x180012e87  mov     [rsp+260h+var_190], rax
0x180012e8f  lea     rax, [rbp+0C0h+var_12C]
0x180012e93  mov     [rsp+260h+var_198], rax
0x180012e9b  lea     rax, [rbp+0C0h+var_128]
0x180012e9f  mov     [rsp+260h+var_1A0], rax
0x180012ea7  lea     rax, [rbp+0C0h+var_124]
0x180012eab  mov     [rbp+0C0h+var_78], rdi
0x180012eaf  mov     [rbp+0C0h+var_104], 5
0x180012eb6  mov     [rbp+0C0h+var_100], edx
0x180012eb9  mov     [rbp+0C0h+var_140], 1000000h
0x180012ec1  mov     [rsp+260h+var_1A8], rax
0x180012ec9  lea     rdx, word_18003A05E
0x180012ed0  lea     rax, [rbp+0C0h+var_120]
0x180012ed4  mov     [rsp+260h+var_1B0], rax
0x180012edc  lea     rax, [rbp+0C0h+var_11C]
0x180012ee0  mov     [rsp+260h+var_1B8], rax
0x180012ee8  lea     rax, [rbp+0C0h+var_118]
0x180012eec  mov     [rsp+260h+var_1C0], rax
0x180012ef4  lea     rax, [rbp+0C0h+var_114]
0x180012ef8  mov     [rsp+260h+var_1C8], rax
0x180012f00  lea     rax, [rbp+0C0h+var_110]
0x180012f04  mov     [rsp+260h+var_1D0], rax
0x180012f0c  lea     rax, [rbp+0C0h+var_88]
0x180012f10  mov     [rsp+260h+var_1D8], rax
0x180012f18  lea     rax, [rbp+0C0h+var_78]
0x180012f1c  mov     [rsp+260h+var_1E0], rax
0x180012f24  lea     rax, [rbp+0C0h+var_10C]
0x180012f28  mov     [rsp+260h+var_1E8], rax
0x180012f2d  lea     rax, [rbp+0C0h+var_C8]
0x180012f31  mov     [rsp+260h+var_1F0], rax
0x180012f36  lea     rax, [rbp+0C0h+var_C0]
0x180012f3a  mov     [rsp+260h+var_1F8], rax
0x180012f3f  lea     rax, [rbp+0C0h+var_B8]
0x180012f43  mov     [rsp+260h+var_200], rax
0x180012f48  lea     rax, [rbp+0C0h+var_B0]
0x180012f4c  mov     [rsp+260h+var_208], rax
0x180012f51  lea     rax, [rbp+0C0h+var_A8]
0x180012f55  mov     [rsp+260h+var_210], rax
0x180012f5a  lea     rax, [rbp+0C0h+var_A0]
0x180012f5e  mov     [rsp+260h+var_218], rax
0x180012f63  lea     rax, [rbp+0C0h+var_98]
0x180012f67  mov     [rsp+260h+var_220], rax
0x180012f6c  lea     rax, [rbp+0C0h+var_108]
0x180012f70  mov     [rsp+260h+var_228], rax
0x180012f75  lea     rax, [rbp+0C0h+var_104]
0x180012f79  mov     [rsp+260h+var_230], rax
0x180012f7e  lea     rax, [rbp+0C0h+var_100]
0x180012f82  mov     [rsp+260h+var_238], rax
0x180012f87  lea     rax, [rbp+0C0h+var_140]
0x180012f8b  mov     [rsp+260h+var_240], rax
0x180012f90  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U1@U1@U1@U1@U1@U1@U1@U2@U_tlgWrapperPtrSize@@U3@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U1@U1@U1@U1@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4433333334AEBU_tlgWrapperPtrSize@@544444444443333AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180012f95  cmp     dword ptr [rdi+44h], 0E10h
0x180012f9c  jbe     short loc_180013003
0x180012f9e  mov     eax, [rdi+48h]
0x180012fa1  lea     rdx, [rbp+0C0h+var_140]
0x180012fa5  xorps   xmm1, xmm1
0x180012fa8  xorps   xmm0, xmm0
0x180012fab  cvtsi2sd xmm1, rax
0x180012fb0  mov     eax, [rdi+44h]
0x180012fb3  cvtsi2sd xmm0, rax
0x180012fb8  divsd   xmm1, xmm0
0x180012fbc  mulsd   xmm1, cs:__real@4059000000000000
0x180012fc4  cvttsd2si rbx, xmm1
0x180012fc9  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_LostPresentsFastFail@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::GetCachedVariantState(void)
0x180012fce  cmp     ebx, dword ptr [rbp+0C0h+var_140+4]
0x180012fd1  jb      short loc_180013003
0x180012fd3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_LostPresentsFastFail@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_LostPresentsFastFail@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail> `wil::Feature<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::GetImpl(void)'::`2'::impl
0x180012fda  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_LostPresentsFastFail@@@details@wil@@QEAA?AW4Variant_GPM_LostPresentsFastFail@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180012fdf  cmp     al, 2
0x180012fe1  jz      short loc_180012FFC
0x180012fe3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_LostPresentsFastFail@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_LostPresentsFastFail@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail> `wil::Feature<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::GetImpl(void)'::`2'::impl
0x180012fea  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_LostPresentsFastFail@@@details@wil@@QEAA?AW4Variant_GPM_LostPresentsFastFail@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180012fef  cmp     al, 3
0x180012ff1  jnz     short loc_180013003
0x180012ff3  call    ?IsContainer@@YAEXZ; IsContainer(void)
0x180012ff8  test    al, al
0x180012ffa  jnz     short loc_180013003
0x180012ffc  mov     ecx, 7
0x180013001  int     29h; Win8: RtlFailFast(ecx)
0x180013003  lea     rdx, [rbp+0C0h+var_140]
0x180013007  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MemUsageFastFail@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::GetCachedVariantState(void)
0x18001300c  mov     eax, dword ptr [rbp+0C0h+var_140+4]
0x18001300f  cmp     [rdi+68h], rax
0x180013013  jb      short loc_180013045
0x180013015  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_MemUsageFastFail@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MemUsageFastFail@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MemUsageFastFail> `wil::Feature<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::GetImpl(void)'::`2'::impl
0x18001301c  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MemUsageFastFail@@@details@wil@@QEAA?AW4Variant_GPM_MemUsageFastFail@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180013021  cmp     al, 2
0x180013023  jz      short loc_18001303E
0x180013025  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_MemUsageFastFail@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MemUsageFastFail@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MemUsageFastFail> `wil::Feature<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::GetImpl(void)'::`2'::impl
0x18001302c  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MemUsageFastFail@@@details@wil@@QEAA?AW4Variant_GPM_MemUsageFastFail@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180013031  cmp     al, 3
0x180013033  jnz     short loc_180013045
0x180013035  call    ?IsContainer@@YAEXZ; IsContainer(void)
0x18001303a  test    al, al
0x18001303c  jnz     short loc_180013045
0x18001303e  mov     ecx, 7
0x180013043  int     29h; Win8: RtlFailFast(ecx)
0x180013045  mov     rcx, [rbp+0C0h+var_10]
0x18001304c  xor     rcx, rsp; StackCookie
0x18001304f  call    __security_check_cookie
0x180013054  lea     r11, [rsp+260h+var_s0]
0x18001305c  mov     rbx, [r11+10h]
0x180013060  mov     rdi, [r11+18h]
0x180013064  mov     rsp, r11
0x180013067  pop     rbp
0x180013068  retn
```
