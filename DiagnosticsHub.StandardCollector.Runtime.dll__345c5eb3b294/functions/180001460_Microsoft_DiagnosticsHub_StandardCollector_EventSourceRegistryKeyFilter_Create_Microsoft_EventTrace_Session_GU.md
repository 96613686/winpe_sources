# Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::Create(Microsoft::EventTrace::Session *,_GUID const &,uchar const *,unsigned __int64,std::unique_ptr<Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter,std::default_delete<Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter>> &)

- ea: `0x180001460`
- end: `0x180001a97`
- name: `?Create@EventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@SAJPEAVSession@EventTrace@4@AEBU_GUID@@PEBE_KAEAV?$unique_ptr@VEventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@U?$default_delete@VEventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@Z`
- size: `1591`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180020ccc`

## callees

- `0x180001460`
- `0x180001a98`
- `0x180001b50`
- `0x180001cf8`
- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x18003d864`
- `0x180049b50`
- `0x18004a03c`
- `0x18004a078`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800015bc`
- `KERNEL32!GetLastError` at `0x18000162c`
- `KERNEL32!GetLastError` at `0x180001735`
- `KERNEL32!GetLastError` at `0x1800017f0`
- `KERNEL32!GetLastError` at `0x1800018c7`
- `KERNEL32!GetLastError` at `0x180001982`
- `KERNEL32!GetLastError` at `0x1800015bc`
- `KERNEL32!GetLastError` at `0x18000162c`
- `KERNEL32!GetLastError` at `0x180001735`
- `KERNEL32!GetLastError` at `0x1800017f0`
- `KERNEL32!GetLastError` at `0x1800018c7`
- `KERNEL32!GetLastError` at `0x180001982`
- `ole32!StringFromGUID2` at `0x18000153b`
- `ole32!StringFromGUID2` at `0x180001566`
- `ole32!StringFromGUID2` at `0x18000153b`
- `ole32!StringFromGUID2` at `0x180001566`
- `ADVAPI32!RegSetValueExW` at `0x18000172b`
- `ADVAPI32!RegSetValueExW` at `0x1800017e6`
- `ADVAPI32!RegSetValueExW` at `0x1800018bd`
- `ADVAPI32!RegSetValueExW` at `0x180001978`
- `ADVAPI32!RegSetValueExW` at `0x18000172b`
- `ADVAPI32!RegSetValueExW` at `0x1800017e6`
- `ADVAPI32!RegSetValueExW` at `0x1800018bd`
- `ADVAPI32!RegSetValueExW` at `0x180001978`
- `ADVAPI32!RegQueryValueExW` at `0x1800016d5`
- `ADVAPI32!RegQueryValueExW` at `0x18000186c`
- `ADVAPI32!RegQueryValueExW` at `0x1800016d5`
- `ADVAPI32!RegQueryValueExW` at `0x18000186c`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800017ba`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18000194c`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800017ba`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18000194c`

## string_xrefs

- `0x1800016fa`: `DiagnosticSourceEventSource filter already present in 64-bit hive: %s %s`
- `0x180001701`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\EventSourceRegistryKeyFilter.cpp`
- `0x180001898`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\EventSourceRegistryKeyFilter.cpp`
- `0x180001891`: `DiagnosticSourceEventSource filter already present in 32-bit hive: %s %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::Create(
        __int64 a1,
        const GUID *a2,
        const BYTE *a3,
        __int64 a4,
        Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter **a5)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  _QWORD *v9; // rdi
  struct ATL::IAtlStringMgr *v10; // rax
  HKEY *v11; // rsi
  unsigned __int16 *v12; // rbx
  HKEY v13; // rdx
  unsigned __int16 *v14; // r9
  HKEY v15; // rdx
  unsigned __int16 *v16; // r9
  signed int LastError; // eax
  unsigned int v18; // esi
  __int64 result; // rax
  HKEY *v20; // r14
  signed int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // rax
  __int64 v24; // r8
  DWORD v25; // r15d
  signed int v26; // eax
  unsigned int v27; // esi
  int v28; // eax
  signed int v29; // eax
  unsigned int v30; // esi
  signed int v31; // eax
  unsigned int v32; // esi
  int v33; // eax
  signed int v34; // eax
  unsigned int v35; // esi
  Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter *v36; // rsi
  unsigned int lpData; // [rsp+20h] [rbp-268h]
  unsigned int lpDataa; // [rsp+20h] [rbp-268h]
  struct _SECURITY_ATTRIBUTES *v39; // [rsp+30h] [rbp-258h]
  struct _SECURITY_ATTRIBUTES *v40; // [rsp+30h] [rbp-258h]
  unsigned int *v41; // [rsp+38h] [rbp-250h]
  unsigned int *v42; // [rsp+38h] [rbp-250h]
  int pExceptionObject; // [rsp+40h] [rbp-248h] BYREF
  int v44; // [rsp+44h] [rbp-244h] BYREF
  unsigned __int16 *v45; // [rsp+48h] [rbp-240h] BYREF
  unsigned int v46; // [rsp+50h] [rbp-238h] BYREF
  DWORD v47[2]; // [rsp+58h] [rbp-230h]
  _QWORD *v48; // [rsp+60h] [rbp-228h]
  OLECHAR v49[112]; // [rsp+70h] [rbp-218h] BYREF
  DWORD cbData; // [rsp+150h] [rbp-138h] BYREF
  DWORD Type; // [rsp+158h] [rbp-130h] BYREF
  OLECHAR sz[112]; // [rsp+160h] [rbp-128h] BYREF

  *(_QWORD *)v47 = a4;
  Instance = ATL::CAtlStringMgr::GetInstance();
  try
  {
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    v45 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                             + 24);
    v9 = operator new(0x38u);
    *(_OWORD *)v9 = 0;
    *((_OWORD *)v9 + 1) = 0;
    *((_OWORD *)v9 + 2) = 0;
    v9[6] = 0;
    v10 = ATL::CAtlStringMgr::GetInstance();
    if ( !v10 )
      ATL::AtlThrowImpl(-2147467259);
    *v9 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v10 + 24LL))(v10) + 24;
    v9[1] = 0;
    *((_DWORD *)v9 + 4) = 0;
    v9[3] = 0;
    v9[4] = 0;
    *((_DWORD *)v9 + 10) = 0;
    v9[6] = 0;
    v48 = v9;
    if ( !StringFromGUID2(a2, sz, 39) )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    sz[39] = 0;
    sz[78] = 0;
    if ( !StringFromGUID2(a2, v49, 39) )
    {
      v44 = -2147024882;
      throw (long *)&v44;
    }
    v49[39] = 0;
    v49[78] = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &v45,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Winevt\\Publishers\\%s",
      v49);
    v11 = (HKEY *)(v9 + 1);
    v12 = v45;
    if ( ATL::CRegKey::Create((ATL::CRegKey *)(v9 + 1), v13, v45, v14, lpData, 0x2001Fu, v39, v41) )
    {
      LastError = GetLastError();
      v18 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v18 = LastError;
      Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter((Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter *)v9);
      operator delete(v9);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
      }
      result = v18;
    }
    else
    {
      v20 = (HKEY *)(v9 + 4);
      if ( ATL::CRegKey::Create((ATL::CRegKey *)(v9 + 4), v15, v12, v16, lpDataa, 0x2021Fu, v40, v42) )
      {
        v21 = GetLastError();
        v22 = (unsigned __int16)v21 | 0x80070000;
        if ( v21 <= 0 )
          v22 = v21;
        Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter((Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter *)v9);
        operator delete(v9);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
        }
        result = v22;
      }
      else
      {
        v23 = *(_QWORD *)(a1 + 8);
        if ( v23 )
          v24 = *(_QWORD *)(v23 + 8);
        else
          v24 = -1;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          v9,
          L"ControllerData_Session_%llu",
          v24);
        cbData = 0;
        if ( RegQueryValueExW(*v11, (LPCWSTR)*v9, 0, &Type, 0, &cbData) != 2 )
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 112),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EventSourceRegistryKeyFilter.cpp",
            L"DiagnosticSourceEventSource filter already present in 64-bit hive: %s %s",
            v12,
            *v9);
        v25 = v47[0];
        if ( RegSetValueExW(*v11, (LPCWSTR)*v9, 0, 3u, a3, v47[0]) )
        {
          v26 = GetLastError();
          v27 = (unsigned __int16)v26 | 0x80070000;
          if ( v26 <= 0 )
            v27 = v26;
          Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter((Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter *)v9);
          operator delete(v9);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
          }
          result = v27;
        }
        else if ( ((unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)(v9 + 1), 0, 0, &cbData) == 2 || !cbData)
               && (v28 = wcslen(sz), RegSetValueExW(*v11, 0, 0, 1u, (const BYTE *)sz, 2 * v28 + 2)) )
        {
          v29 = GetLastError();
          v30 = (unsigned __int16)v29 | 0x80070000;
          if ( v29 <= 0 )
            v30 = v29;
          Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter((Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter *)v9);
          operator delete(v9);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
          }
          result = v30;
        }
        else
        {
          if ( RegQueryValueExW(*v20, (LPCWSTR)*v9, 0, &Type, 0, &cbData) != 2 )
            DiagHubCommon::LogStream::Write(
              (DiagHubCommon::LogStream *)((char *)_logger + 112),
              L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EventSourceRegistryKeyFilter.cpp",
              L"DiagnosticSourceEventSource filter already present in 32-bit hive: %s %s",
              v12,
              *v9);
          if ( RegSetValueExW(*v20, (LPCWSTR)*v9, 0, 3u, a3, v25) )
          {
            v31 = GetLastError();
            v32 = (unsigned __int16)v31 | 0x80070000;
            if ( v31 <= 0 )
              v32 = v31;
            Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter((Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter *)v9);
            operator delete(v9);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
            }
            result = v32;
          }
          else if ( ((unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)(v9 + 4), 0, 0, &cbData) == 2
                  || !cbData)
                 && (v33 = wcslen(sz), RegSetValueExW(*v20, 0, 0, 1u, (const BYTE *)sz, 2 * v33 + 2)) )
          {
            v34 = GetLastError();
            v35 = (unsigned __int16)v34 | 0x80070000;
            if ( v34 <= 0 )
              v35 = v34;
            Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter((Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter *)v9);
            operator delete(v9);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
            }
            result = v35;
          }
          else
          {
            v36 = *a5;
            *a5 = (Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter *)v9;
            if ( v36 )
            {
              Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter(v36);
              operator delete(v36);
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
            }
            result = 0;
          }
        }
      }
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ATL::CAtlException v46 )
  {
    return v46;
  }
  return result;
}

```

## disassembly

```asm
0x180001460  push    rbx
0x180001462  push    rsi
0x180001463  push    rdi
0x180001464  push    r12
0x180001466  push    r13
0x180001468  push    r14
0x18000146a  push    r15
0x18000146c  sub     rsp, 250h
0x180001473  mov     rax, cs:__security_cookie
0x18000147a  xor     rax, rsp
0x18000147d  mov     [rsp+288h+var_48], rax
0x180001485  mov     qword ptr [rsp+288h+var_230], r9
0x18000148a  mov     r13, r8
0x18000148d  mov     rbx, rdx
0x180001490  mov     r15, rcx
0x180001493  mov     r12, [rsp+288h+arg_20]
0x18000149b  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1800014a0  mov     rcx, rax
0x1800014a3  xor     r14d, r14d
0x1800014a6  test    rax, rax
0x1800014a9  jz      loc_180001A4D
0x1800014af  mov     rax, [rax]
0x1800014b2  mov     rax, [rax+18h]
0x1800014b6  call    cs:__guard_dispatch_icall_fptr
0x1800014bc  add     rax, 18h
0x1800014c0  mov     [rsp+288h+var_240], rax
0x1800014c5  mov     ecx, 38h ; '8'; Size
0x1800014ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800014cf  mov     rdi, rax
0x1800014d2  xorps   xmm0, xmm0
0x1800014d5  xor     eax, eax
0x1800014d7  movups  xmmword ptr [rdi], xmm0
0x1800014da  movups  xmmword ptr [rdi+10h], xmm0
0x1800014de  movups  xmmword ptr [rdi+20h], xmm0
0x1800014e2  mov     [rdi+30h], rax
0x1800014e6  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1800014eb  mov     rcx, rax
0x1800014ee  test    rax, rax
0x1800014f1  jz      loc_180001A58
0x1800014f7  mov     rax, [rax]
0x1800014fa  mov     rax, [rax+18h]
0x1800014fe  call    cs:__guard_dispatch_icall_fptr
0x180001504  add     rax, 18h
0x180001508  mov     [rdi], rax
0x18000150b  mov     [rdi+8], r14
0x18000150f  mov     [rdi+10h], r14d
0x180001513  mov     [rdi+18h], r14
0x180001517  mov     [rdi+20h], r14
0x18000151b  mov     [rdi+28h], r14d
0x18000151f  mov     [rdi+30h], r14
0x180001523  mov     [rsp+288h+var_228], rdi
0x180001528  mov     esi, 27h ; '''
0x18000152d  mov     r8d, esi; cchMax
0x180001530  lea     rdx, [rsp+288h+sz]; lpsz
0x180001538  mov     rcx, rbx; rguid
0x18000153b  call    cs:__imp_StringFromGUID2
0x180001541  test    eax, eax
0x180001543  jz      loc_180001A63
0x180001549  mov     [rsp+288h+var_DA], r14w
0x180001552  mov     [rsp+288h+var_8C], r14w
0x18000155b  mov     r8d, esi; cchMax
0x18000155e  lea     rdx, [rsp+288h+var_218]; lpsz
0x180001563  mov     rcx, rbx; rguid
0x180001566  call    cs:__imp_StringFromGUID2
0x18000156c  test    eax, eax
0x18000156e  jz      loc_180001A7C
0x180001574  mov     [rsp+288h+var_1CA], r14w
0x18000157d  mov     [rsp+288h+var_17C], r14w
0x180001586  lea     r8, [rsp+288h+var_218]
0x18000158b  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001592  lea     rcx, [rsp+288h+var_240]
0x180001597  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18000159c  lea     rsi, [rdi+8]
0x1800015a0  mov     dword ptr [rsp+288h+lpcbData], 2001Fh; unsigned int
0x1800015a8  mov     rbx, [rsp+288h+var_240]
0x1800015ad  mov     r8, rbx; unsigned __int16 *
0x1800015b0  mov     rcx, rsi; this
0x1800015b3  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800015b8  test    eax, eax
0x1800015ba  jz      short loc_180001611
0x1800015bc  call    cs:__imp_GetLastError
0x1800015c2  movzx   esi, ax
0x1800015c5  or      esi, 80070000h
0x1800015cb  test    eax, eax
0x1800015cd  cmovle  esi, eax
0x1800015d0  mov     rcx, rdi; this
0x1800015d3  call    ??1EventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter(void)
0x1800015d8  mov     edx, 38h ; '8'
0x1800015dd  mov     rcx, rdi; Block
0x1800015e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800015e5  nop
0x1800015e6  lea     rdx, [rbx-18h]
0x1800015ea  or      ecx, 0FFFFFFFFh
0x1800015ed  lock xadd [rdx+10h], ecx
0x1800015f2  sub     ecx, 1
0x1800015f5  jg      short loc_18000160A
0x1800015f7  lfence
0x1800015fa  mov     rcx, [rdx]
0x1800015fd  mov     r8, [rcx]
0x180001600  mov     rax, [r8+8]
0x180001604  call    cs:__guard_dispatch_icall_fptr
0x18000160a  mov     eax, esi
0x18000160c  jmp     loc_180001A2A
0x180001611  lea     r14, [rdi+20h]
0x180001615  mov     dword ptr [rsp+288h+lpcbData], 2021Fh; unsigned int
0x18000161d  mov     r8, rbx; unsigned __int16 *
0x180001620  mov     rcx, r14; this
0x180001623  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180001628  test    eax, eax
0x18000162a  jz      short loc_180001681
0x18000162c  call    cs:__imp_GetLastError
0x180001632  movzx   esi, ax
0x180001635  or      esi, 80070000h
0x18000163b  test    eax, eax
0x18000163d  cmovle  esi, eax
0x180001640  mov     rcx, rdi; this
0x180001643  call    ??1EventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter(void)
0x180001648  mov     edx, 38h ; '8'
0x18000164d  mov     rcx, rdi; Block
0x180001650  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001655  nop
0x180001656  lea     rdx, [rbx-18h]
0x18000165a  or      ecx, 0FFFFFFFFh
0x18000165d  lock xadd [rdx+10h], ecx
0x180001662  sub     ecx, 1
0x180001665  jg      short loc_18000167A
0x180001667  lfence
0x18000166a  mov     rcx, [rdx]
0x18000166d  mov     r8, [rcx]
0x180001670  mov     rax, [r8+8]
0x180001674  call    cs:__guard_dispatch_icall_fptr
0x18000167a  mov     eax, esi
0x18000167c  jmp     loc_180001A2A
0x180001681  mov     rax, [r15+8]
0x180001685  test    rax, rax
0x180001688  jnz     short loc_180001690
0x18000168a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000168e  jmp     short loc_180001694
0x180001690  mov     r8, [rax+8]
0x180001694  lea     rdx, aControllerdata; "ControllerData_Session_%llu"
0x18000169b  mov     rcx, rdi
0x18000169e  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800016a3  mov     [rsp+288h+cbData], 0
0x1800016ae  lea     rax, [rsp+288h+cbData]
0x1800016b6  mov     [rsp+288h+lpcbData], rax; lpcbData
0x1800016bb  mov     [rsp+288h+lpData], 0; lpData
0x1800016c4  lea     r9, [rsp+288h+Type]; lpType
0x1800016cc  xor     r8d, r8d; lpReserved
0x1800016cf  mov     rdx, [rdi]; lpValueName
0x1800016d2  mov     rcx, [rsi]; hKey
0x1800016d5  call    cs:__imp_RegQueryValueExW
0x1800016db  test    eax, eax
0x1800016dd  jz      short loc_1800016E4
0x1800016df  cmp     eax, 2
0x1800016e2  jz      short loc_18000170D
0x1800016e4  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800016eb  add     rcx, 70h ; 'p'; this
0x1800016ef  mov     rax, [rdi]
0x1800016f2  mov     [rsp+288h+lpData], rax
0x1800016f7  mov     r9, rbx
0x1800016fa  lea     r8, aDiagnosticsour; "DiagnosticSourceEventSource filter alre"...
0x180001701  lea     rdx, aDAWork1SSource_8; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180001708  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000170d  mov     r15, qword ptr [rsp+288h+var_230]
0x180001712  mov     dword ptr [rsp+288h+lpcbData], r15d; cbData
0x180001717  mov     [rsp+288h+lpData], r13; lpData
0x18000171c  mov     r9d, 3; dwType
0x180001722  xor     r8d, r8d; Reserved
0x180001725  mov     rdx, [rdi]; lpValueName
0x180001728  mov     rcx, [rsi]; hKey
0x18000172b  call    cs:__imp_RegSetValueExW
0x180001731  test    eax, eax
0x180001733  jz      short loc_18000178A
0x180001735  call    cs:__imp_GetLastError
0x18000173b  movzx   esi, ax
0x18000173e  or      esi, 80070000h
0x180001744  test    eax, eax
0x180001746  cmovle  esi, eax
0x180001749  mov     rcx, rdi; this
0x18000174c  call    ??1EventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter(void)
0x180001751  mov     edx, 38h ; '8'
0x180001756  mov     rcx, rdi; Block
0x180001759  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000175e  nop
0x18000175f  lea     rdx, [rbx-18h]
0x180001763  or      ecx, 0FFFFFFFFh
0x180001766  lock xadd [rdx+10h], ecx
0x18000176b  sub     ecx, 1
0x18000176e  jg      short loc_180001783
0x180001770  lfence
0x180001773  mov     rcx, [rdx]
0x180001776  mov     r8, [rcx]
0x180001779  mov     rax, [r8+8]
0x18000177d  call    cs:__guard_dispatch_icall_fptr
0x180001783  mov     eax, esi
0x180001785  jmp     loc_180001A2A
0x18000178a  lea     r9, [rsp+288h+cbData]; unsigned int *
0x180001792  xor     r8d, r8d; unsigned __int16 *
0x180001795  xor     edx, edx; unsigned __int16 *
0x180001797  mov     rcx, rsi; this
0x18000179a  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000179f  cmp     eax, 2
0x1800017a2  jz      short loc_1800017B2
0x1800017a4  cmp     [rsp+288h+cbData], 0
0x1800017ac  jnz     loc_180001845
0x1800017b2  lea     rcx, [rsp+288h+sz]; String
0x1800017ba  call    cs:__imp_wcslen
0x1800017c0  lea     eax, ds:2[rax*2]
0x1800017c7  mov     dword ptr [rsp+288h+lpcbData], eax; cbData
0x1800017cb  lea     rax, [rsp+288h+sz]
0x1800017d3  mov     [rsp+288h+lpData], rax; lpData
0x1800017d8  mov     r9d, 1; dwType
0x1800017de  xor     r8d, r8d; Reserved
0x1800017e1  xor     edx, edx; lpValueName
0x1800017e3  mov     rcx, [rsi]; hKey
0x1800017e6  call    cs:__imp_RegSetValueExW
0x1800017ec  test    eax, eax
0x1800017ee  jz      short loc_180001845
0x1800017f0  call    cs:__imp_GetLastError
0x1800017f6  movzx   esi, ax
0x1800017f9  or      esi, 80070000h
0x1800017ff  test    eax, eax
0x180001801  cmovle  esi, eax
0x180001804  mov     rcx, rdi; this
0x180001807  call    ??1EventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter(void)
0x18000180c  mov     edx, 38h ; '8'
0x180001811  mov     rcx, rdi; Block
0x180001814  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001819  nop
0x18000181a  lea     rdx, [rbx-18h]
0x18000181e  or      ecx, 0FFFFFFFFh
0x180001821  lock xadd [rdx+10h], ecx
0x180001826  sub     ecx, 1
0x180001829  jg      short loc_18000183E
0x18000182b  lfence
0x18000182e  mov     rcx, [rdx]
0x180001831  mov     r8, [rcx]
0x180001834  mov     rax, [r8+8]
0x180001838  call    cs:__guard_dispatch_icall_fptr
0x18000183e  mov     eax, esi
0x180001840  jmp     loc_180001A2A
0x180001845  lea     rax, [rsp+288h+cbData]
0x18000184d  mov     [rsp+288h+lpcbData], rax; lpcbData
0x180001852  mov     [rsp+288h+lpData], 0; lpData
0x18000185b  lea     r9, [rsp+288h+Type]; lpType
0x180001863  xor     r8d, r8d; lpReserved
0x180001866  mov     rdx, [rdi]; lpValueName
0x180001869  mov     rcx, [r14]; hKey
0x18000186c  call    cs:__imp_RegQueryValueExW
0x180001872  test    eax, eax
0x180001874  jz      short loc_18000187B
0x180001876  cmp     eax, 2
0x180001879  jz      short loc_1800018A4
0x18000187b  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180001882  add     rcx, 70h ; 'p'; this
0x180001886  mov     rax, [rdi]
0x180001889  mov     [rsp+288h+lpData], rax
0x18000188e  mov     r9, rbx
0x180001891  lea     r8, aDiagnosticsour_0; "DiagnosticSourceEventSource filter alre"...
0x180001898  lea     rdx, aDAWork1SSource_8; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000189f  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800018a4  mov     dword ptr [rsp+288h+lpcbData], r15d; cbData
0x1800018a9  mov     [rsp+288h+lpData], r13; lpData
0x1800018ae  mov     r9d, 3; dwType
0x1800018b4  xor     r8d, r8d; Reserved
0x1800018b7  mov     rdx, [rdi]; lpValueName
0x1800018ba  mov     rcx, [r14]; hKey
0x1800018bd  call    cs:__imp_RegSetValueExW
0x1800018c3  test    eax, eax
0x1800018c5  jz      short loc_18000191C
0x1800018c7  call    cs:__imp_GetLastError
0x1800018cd  movzx   esi, ax
0x1800018d0  or      esi, 80070000h
0x1800018d6  test    eax, eax
0x1800018d8  cmovle  esi, eax
0x1800018db  mov     rcx, rdi; this
0x1800018de  call    ??1EventSourceRegistryKeyFilter@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EventSourceRegistryKeyFilter::~EventSourceRegistryKeyFilter(void)
0x1800018e3  mov     edx, 38h ; '8'
0x1800018e8  mov     rcx, rdi; Block
0x1800018eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800018f0  nop
0x1800018f1  lea     rdx, [rbx-18h]
0x1800018f5  or      ecx, 0FFFFFFFFh
0x1800018f8  lock xadd [rdx+10h], ecx
0x1800018fd  sub     ecx, 1
0x180001900  jg      short loc_180001915
0x180001902  lfence
0x180001905  mov     rcx, [rdx]
0x180001908  mov     r8, [rcx]
0x18000190b  mov     rax, [r8+8]
0x18000190f  call    cs:__guard_dispatch_icall_fptr
0x180001915  mov     eax, esi
0x180001917  jmp     loc_180001A2A
0x18000191c  lea     r9, [rsp+288h+cbData]; unsigned int *
0x180001924  xor     r8d, r8d; unsigned __int16 *
0x180001927  xor     edx, edx; unsigned __int16 *
0x180001929  mov     rcx, r14; this
0x18000192c  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180001931  cmp     eax, 2
0x180001934  jz      short loc_180001944
  ... truncated ...
```
