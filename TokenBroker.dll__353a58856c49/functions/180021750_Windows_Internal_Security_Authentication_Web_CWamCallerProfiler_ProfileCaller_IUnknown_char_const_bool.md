# Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)

- ea: `0x180021750`
- end: `0x1800228a1`
- name: `?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z`
- size: `4433`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `91`
- callee_count: `25`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001e7c0`
- `0x18001fc10`
- `0x180020840`
- `0x180020d90`
- `0x18002eb80`
- `0x18002f450`
- `0x18002fc10`
- `0x180033800`
- `0x180040480`
- `0x180054240`
- `0x1800564d0`
- `0x180056540`
- `0x180057160`
- `0x180057310`
- `0x180057580`
- `0x180058520`
- `0x1800586a8`
- `0x18005a1f0`
- `0x18005d080`
- `0x18005d870`
- `0x180060250`
- `0x180069a40`
- `0x18006abe0`
- `0x18006b0c0`
- `0x1800803f0`
- `0x180081890`
- `0x180082e10`
- `0x180083f90`
- `0x1800845d0`
- `0x180084d40`
- `0x180085c40`
- `0x180086a40`
- `0x180087800`
- `0x180088620`
- `0x180089730`
- `0x1800899a0`
- `0x18008b9a0`
- `0x18008be40`
- `0x18008c150`
- `0x18008c410`
- `0x18008d0b0`
- `0x18008dc10`
- `0x18009ed20`
- `0x18009f0c0`
- `0x1800a6a30`
- `0x1800a7600`
- `0x1800a9060`
- `0x1800a90b0`
- `0x1800a9100`
- `0x1800a9150`

## callees

- `0x18000730c`
- `0x180009e80`
- `0x18000bd70`
- `0x180020620`
- `0x180021750`
- `0x180030adc`
- `0x1800372d0`
- `0x18004343c`
- `0x18004fe68`
- `0x180061b84`
- `0x18007f9b0`
- `0x180080048`
- `0x180084c90`
- `0x18008e690`
- `0x18008e6b4`
- `0x18008e6cc`
- `0x18008e710`
- `0x18008f234`
- `0x180091969`
- `0x180091975`
- `0x1800a05ac`
- `0x1800a125c`
- `0x1800a12b8`
- `0x1800a13f8`
- `0x18011b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180021963`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180021963`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180021eb7`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180021eb7`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180021ba1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002190e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002190e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800218f5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800218f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002186c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021ecf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002186c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021ecf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021885`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800218cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021fdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022569`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021885`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800218cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180021fdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022569`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002188e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021fe8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002188e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021fe8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800218c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800222bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022362`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800218c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800222bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021953`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021999`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021953`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021999`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021948`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022304`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800224ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021948`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022304`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800224ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022712`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022815`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022815`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021860`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021860`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800218b3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800218b3`

## string_xrefs

- `0x180021959`: `tokenbroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
        __int64 a1,
        __int64 a2,
        struct IUnknown *a3,
        void *a4,
        char a5)
{
  PSRWLOCK v7; // r14
  _QWORD *v8; // rax
  int v9; // ecx
  ULONGLONG TickCount64; // rdi
  HSTRING *CallingAppNameForProfiling; // rax
  HSTRING v13; // rbx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v15; // rax
  size_t v16; // r14
  __int64 v17; // r8
  unsigned __int64 v18; // r15
  size_t v19; // r13
  unsigned __int16 **v20; // rdi
  unsigned __int64 i; // rcx
  unsigned __int64 v22; // rax
  __int64 v23; // rdi
  size_t v24; // rcx
  unsigned __int16 *v25; // r8
  unsigned __int16 *v26; // rcx
  void *v27; // rax
  unsigned __int64 v28; // rdx
  unsigned __int16 *v29; // rdi
  unsigned __int64 j; // rcx
  unsigned __int16 **v31; // r12
  void **v32; // rdx
  HSTRING v33; // rax
  void **v34; // r15
  PSRWLOCK v35; // r12
  const unsigned __int16 *v36; // rcx
  size_t v37; // r15
  unsigned __int64 v38; // rdi
  size_t v39; // rax
  size_t v40; // rcx
  _QWORD *v41; // r12
  void *v42; // rax
  size_t v43; // rdi
  size_t v44; // rcx
  void *v45; // r14
  void *v46; // rax
  void **v47; // r15
  void **v48; // rdi
  void **v49; // rdi
  void **v50; // r14
  __int64 Ptr; // r14
  _QWORD *v52; // rdi
  _QWORD *v53; // r13
  size_t v54; // r15
  _QWORD *v55; // rcx
  void **v56; // rdx
  size_t v57; // r14
  size_t v58; // r8
  int v59; // eax
  __int64 v60; // rax
  _QWORD *v61; // rdx
  size_t v62; // rdi
  void **v63; // rcx
  size_t v64; // r8
  int v65; // eax
  __int64 v66; // r14
  _QWORD *v67; // rdi
  char *v68; // r13
  size_t v69; // r15
  _QWORD *v70; // rcx
  void **v71; // rdx
  size_t v72; // r14
  size_t v73; // r8
  int v74; // eax
  __int64 v75; // rax
  _QWORD *v76; // rdx
  size_t v77; // rdi
  void **v78; // rcx
  size_t v79; // r8
  int v80; // eax
  _DWORD *v81; // r14
  _QWORD *v82; // rax
  __int64 inserted; // rdi
  _QWORD *v84; // rdx
  size_t v85; // r12
  size_t v86; // r13
  void **v87; // rcx
  size_t v88; // r8
  int v89; // eax
  __int64 v90; // rdi
  _OWORD *v91; // rax
  std::_Ref_count_base *v92; // rcx
  __int64 v93; // rdi
  const unsigned __int16 *v94; // rdx
  void *v95; // rcx
  void *v96; // rcx
  unsigned __int16 *v97; // rcx
  void *v98; // rcx
  const unsigned __int16 *v99; // rdx
  void *v100; // rcx
  void *v101; // rcx
  unsigned __int16 *v102; // rcx
  void *v103; // rcx
  int v104; // [rsp+30h] [rbp-168h] BYREF
  __int64 v105; // [rsp+38h] [rbp-160h] BYREF
  HSTRING string; // [rsp+40h] [rbp-158h] BYREF
  __int64 v107; // [rsp+48h] [rbp-150h]
  void *Src; // [rsp+50h] [rbp-148h]
  _DWORD *v109; // [rsp+58h] [rbp-140h]
  PSRWLOCK SRWLock; // [rsp+60h] [rbp-138h]
  __int64 v111; // [rsp+68h] [rbp-130h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-128h] BYREF
  __int64 v113; // [rsp+80h] [rbp-118h]
  struct _EVENT_DATA_DESCRIPTOR v114; // [rsp+90h] [rbp-108h] BYREF
  HSTRING v115; // [rsp+A0h] [rbp-F8h]
  void *Buf2[2]; // [rsp+A8h] [rbp-F0h] BYREF
  size_t v117[2]; // [rsp+B8h] [rbp-E0h]
  unsigned __int16 *v118[2]; // [rsp+C8h] [rbp-D0h] BYREF
  unsigned __int64 v119; // [rsp+D8h] [rbp-C0h]
  unsigned __int64 v120; // [rsp+E0h] [rbp-B8h]
  void *Block[2]; // [rsp+E8h] [rbp-B0h] BYREF
  size_t Size; // [rsp+F8h] [rbp-A0h]
  unsigned __int64 v123; // [rsp+100h] [rbp-98h]
  void *v124[2]; // [rsp+108h] [rbp-90h] BYREF
  unsigned __int64 v125; // [rsp+118h] [rbp-80h]
  unsigned __int64 v126; // [rsp+120h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+128h] [rbp-70h] BYREF
  char *v128; // [rsp+138h] [rbp-60h]
  int v129; // [rsp+140h] [rbp-58h]
  int v130; // [rsp+144h] [rbp-54h]
  int *v131; // [rsp+148h] [rbp-50h]
  __int64 v132; // [rsp+150h] [rbp-48h]

  Src = a4;
  v111 = a2;
  v113 = a2;
  v104 = 1;
  v7 = g_WAMCallerProfiler;
  SRWLock = g_WAMCallerProfiler;
  v8 = operator new(0x140u, (const struct std::nothrow_t *)std::nothrow);
  if ( v8 )
  {
    *(_WORD *)v8 = 0;
    v8[1] = 0;
    v8[2] = 0;
    *((_DWORD *)v8 + 6) = 0;
    v8[4] = 0;
    v8[5] = 0;
    v8[6] = 0;
    v8[7] = 0;
    v8[8] = 0;
    v8[9] = 0;
    v8[36] = 0;
    v8[37] = 0;
    v8[38] = 0;
    v8[39] = 0;
  }
  else
  {
    v8 = 0;
  }
  *(_BYTE *)a2 = 0;
  v105 = 0;
  *(_QWORD *)(a2 + 8) = v8;
  v104 = 1;
  if ( !LOBYTE(v7[9].Ptr) )
  {
LABEL_15:
    v104 = 0;
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v105,
      0);
    return a2;
  }
  if ( v8 )
  {
    v9 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(
           (Windows::Internal::Security::Authentication::Web::CallerContext *)v8,
           a3,
           0,
           a5);
    if ( v9 >= 0 )
    {
      TickCount64 = GetTickCount64();
      AcquireSRWLockShared(v7);
      if ( TickCount64 - (unsigned __int64)v7[8].Ptr <= qword_180175A08 )
      {
        ReleaseSRWLockShared(v7);
      }
      else
      {
        ReleaseSRWLockShared(v7);
        AcquireSRWLockExclusive(v7);
        if ( TickCount64 - (unsigned __int64)v7[8].Ptr > qword_180175A08
          && QueueUserWorkItem(
               Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::DumpProfilerData,
               0,
               0x10u) )
        {
          v7[8].Ptr = (PVOID)TickCount64;
        }
        ReleaseSRWLockExclusive(v7);
      }
      if ( dwTlsIndex == -1 || TlsGetValue(dwTlsIndex) == (LPVOID)1 || !TlsSetValue(dwTlsIndex, (LPVOID)1) )
        goto LABEL_15;
      *(_BYTE *)a2 = 1;
      CallingAppNameForProfiling = (HSTRING *)Windows::Internal::Security::Authentication::Web::CallerContext::GetCallingAppNameForProfiling(
                                                *(_QWORD *)(a2 + 8),
                                                &string);
      v13 = *CallingAppNameForProfiling;
      v115 = *CallingAppNameForProfiling;
      *CallingAppNameForProfiling = 0;
      if ( string )
        WindowsDeleteString(string);
      StringRawBuffer = WindowsGetStringRawBuffer(v13, 0);
      if ( !(unsigned int)_o__wcsicmp(StringRawBuffer, L"tokenbroker") )
      {
        v104 = 0;
        if ( v13 )
          WindowsDeleteString(v13);
        wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
          &v105,
          0);
        return a2;
      }
      v15 = WindowsGetStringRawBuffer(v13, 0);
      *(_OWORD *)v124 = 0;
      v125 = 0;
      v126 = 0;
      v16 = -1;
      v17 = -1;
      do
        ++v17;
      while ( v15[v17] );
      std::wstring::_Construct<1,unsigned short const *>(v124, v15);
      *(_OWORD *)v118 = 0;
      v119 = 0;
      v120 = 7;
      LOWORD(v118[0]) = 0;
      v18 = v125;
      if ( !v125 )
      {
        v119 = 0;
        LOWORD(v118[0]) = 0;
        v19 = 0x7FFFFFFFFFFFFFFFLL;
        goto LABEL_52;
      }
      if ( v125 <= 7 )
      {
        v119 = v125;
        v20 = v118;
        for ( i = (2 * v125) >> 1; i; --i )
        {
          *(_WORD *)v20 = 0;
          v20 = (unsigned __int16 **)((char *)v20 + 2);
        }
        *((_WORD *)v118 + v18) = 0;
        v19 = 0x7FFFFFFFFFFFFFFFLL;
        goto LABEL_52;
      }
      if ( v125 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      v22 = v125 | 7;
      v19 = 0x7FFFFFFFFFFFFFFFLL;
      if ( (v125 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        if ( v22 < 0xA )
          v22 = 10;
        v23 = v22 + 1;
        if ( v22 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
        v24 = 2 * v23;
        if ( !(2 * v23) )
        {
          v25 = 0;
          v26 = 0;
LABEL_47:
          v28 = v18;
          v119 = v18;
          v120 = v23 - 1;
          v29 = v26;
          for ( j = v18; j; --j )
            *v29++ = 0;
          do
            --v28;
          while ( v28 );
          v25[v18] = 0;
          v118[0] = v25;
LABEL_52:
          v31 = v118;
          if ( v120 > 7 )
            v31 = (unsigned __int16 **)v118[0];
          v32 = v124;
          if ( v126 > 7 )
            v32 = (void **)v124[0];
          v33 = (HSTRING)((char *)v32 + 2 * v125);
          string = v33;
          v34 = v124;
          if ( v126 > 7 )
            v34 = (void **)v124[0];
          while ( v34 != (void **)v33 )
          {
            *(_WORD *)v31 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*(unsigned __int16 *)v34);
            v34 = (void **)((char *)v34 + 2);
            v31 = (unsigned __int16 **)((char *)v31 + 2);
            v33 = string;
          }
          v35 = SRWLock;
          if ( (unsigned __int8)Windows::Internal::Security::Authentication::Web::CWamProfiler::ProfileCaller(
                                  &SRWLock[3],
                                  v118) )
          {
            v36 = (const unsigned __int16 *)v118;
            if ( v120 > 7 )
              v36 = v118[0];
            Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::AddAggNoisyTelemetryTrace(v36);
          }
          *(_OWORD *)Block = 0;
          Size = 0;
          v123 = 0;
          do
            ++v16;
          while ( *((_BYTE *)Src + v16) );
          if ( v16 > 0x7FFFFFFFFFFFFFFFLL )
            std::_Xlen_string();
          if ( v16 <= 0xF )
          {
            Size = v16;
            v123 = 15;
            memcpy_0(Block, Src, v16);
            *((_BYTE *)Block + v16) = 0;
            v37 = 0x8000000000000027uLL;
            goto LABEL_83;
          }
          v38 = v16 | 0xF;
          if ( (v16 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
          {
            v38 = 0x7FFFFFFFFFFFFFFFLL;
            v37 = 0x8000000000000027uLL;
            v39 = 0x8000000000000027uLL;
LABEL_78:
            v42 = operator new(v39);
            if ( !v42 )
              goto LABEL_236;
            v41 = (_QWORD *)(((unsigned __int64)v42 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v41 - 1) = v42;
            goto LABEL_82;
          }
          if ( v38 < 0x16 )
            v38 = 22;
          v40 = v38 + 1;
          if ( v38 == -1 )
          {
            v41 = 0;
          }
          else
          {
            if ( v40 >= 0x1000 )
            {
              v39 = v38 + 40;
              if ( v38 + 40 < v38 + 1 )
                std::_Throw_bad_array_new_length();
              v37 = 0x8000000000000027uLL;
              goto LABEL_78;
            }
            v41 = operator new(v40);
          }
          v37 = 0x8000000000000027uLL;
LABEL_82:
          Block[0] = v41;
          Size = v16;
          v123 = v38;
          memcpy_0(v41, Src, v16);
          *((_BYTE *)v41 + v16) = 0;
          v35 = SRWLock;
LABEL_83:
          *(_OWORD *)Buf2 = 0;
          v117[0] = 0;
          v117[1] = 15;
          LOBYTE(Buf2[0]) = 0;
          v43 = Size;
          if ( !Size )
          {
            v117[0] = 0;
            LOBYTE(Buf2[0]) = 0;
            goto LABEL_100;
          }
          if ( Size <= 0xF )
          {
            v117[0] = Size;
            memset_0(Buf2, 0, Size);
            *((_BYTE *)Buf2 + v43) = 0;
            goto LABEL_100;
          }
          if ( Size > 0x7FFFFFFFFFFFFFFFLL )
            std::_Xlen_string();
          if ( (Size | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
          {
            v19 = Size | 0xF;
            if ( (Size | 0xF) < 0x16 )
              v19 = 22;
            v44 = v19 + 1;
            if ( v19 == -1 )
            {
              v45 = 0;
LABEL_99:
              v117[0] = v43;
              v117[1] = v19;
              memset_0(v45, 0, v43);
              *((_BYTE *)v45 + v43) = 0;
              Buf2[0] = v45;
LABEL_100:
              v47 = Buf2;
              if ( v117[1] > 0xF )
                v47 = (void **)Buf2[0];
              v48 = Block;
              if ( v123 > 0xF )
                v48 = (void **)Block[0];
              v49 = (void **)((char *)v48 + Size);
              v50 = Block;
              if ( v123 > 0xF )
                v50 = (void **)Block[0];
              for ( ; v50 != v49; v50 = (void **)((char *)v50 + 1) )
              {
                *(_BYTE *)v47 = _o_tolower((unsigned int)*(char *)v50);
                v47 = (void **)((char *)v47 + 1);
              }
              AcquireSRWLockShared(v35);
              *(_QWORD *)&EventDescriptor.Id = v35;
              string = (HSTRING)&v35[1];
              Ptr = (__int64)v35[1].Ptr;
              v107 = Ptr;
              v52 = *(_QWORD **)(Ptr + 8);
              UserData.Reserved = 0;
              v53 = (_QWORD *)Ptr;
              v54 = v117[0];
              if ( !*((_BYTE *)v52 + 25) )
              {
                while ( 1 )
                {
                  v55 = v52 + 4;
                  v56 = Buf2;
                  if ( v117[1] > 0xF )
                    v56 = (void **)Buf2[0];
                  v57 = v52[6];
                  if ( v52[7] > 0xFu )
                    v55 = (_QWORD *)*v55;
                  v58 = v52[6];
                  if ( v54 < v57 )
                    v58 = v54;
                  v59 = memcmp_0(v55, v56, v58);
                  if ( v59 )
                  {
                    if ( v59 < 0 )
                      goto LABEL_121;
                  }
                  else if ( v57 < v54 )
                  {
LABEL_121:
                    v52 = (_QWORD *)v52[2];
                    goto LABEL_118;
                  }
                  v53 = v52;
                  v52 = (_QWORD *)*v52;
LABEL_118:
                  if ( *((_BYTE *)v52 + 25) )
                  {
                    v60 = (__int64)v35[1].Ptr;
                    Ptr = v107;
                    goto LABEL_123;
                  }
                }
              }
              v60 = Ptr;
LABEL_123:
              if ( !*((_BYTE *)v53 + 25) )
              {
                v61 = v53 + 4;
                v62 = v53[6];
                if ( v53[7] > 0xFu )
                  v61 = (_QWORD *)*v61;
                v63 = Buf2;
                if ( v117[1] > 0xF )
                  v63 = (void **)Buf2[0];
                v64 = v54;
                if ( v62 < v54 )
                  v64 = v53[6];
                v65 = memcmp_0(v63, v61, v64);
                if ( v65 )
                {
                  if ( v65 >= 0 )
                    goto LABEL_136;
                }
                else if ( v54 >= v62 )
                {
                  goto LABEL_136;
                }
                v60 = (__int64)v35[1].Ptr;
              }
              v53 = (_QWORD *)v60;
LABEL_136:
              if ( v53 != (_QWORD *)Ptr )
              {
                if ( (unsigned __int8)Windows::Internal::Security::Authentication::Web::CWamProfiler::ProfileCaller(
                                        v53[8],
                                        v118) )
                {
                  v99 = (const unsigned __int16 *)v118;
                  if ( v120 > 7 )
                    v99 = v118[0];
                  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::AddNoisyTelemetryTrace(
                    (const char *const)Src,
                    v99);
                }
                v104 = 0;
                if ( v35 )
                  ReleaseSRWLockShared(v35);
                if ( v117[1] > 0xF )
                {
                  if ( v117[1] + 1 < 0x1000 )
                  {
                    v100 = Buf2[0];
                  }
                  else
                  {
                    v100 = (void *)*((_QWORD *)Buf2[0] - 1);
                    if ( (unsigned __int64)((char *)Buf2[0] - (char *)v100 - 8) > 0x1F )
                      goto LABEL_230;
                  }
                  operator delete(v100);
                }
                v117[0] = 0;
                v117[1] = 15;
                LOBYTE(Buf2[0]) = 0;
                if ( v123 > 0xF )
                {
                  if ( v123 + 1 < 0x1000 )
                  {
                    v101 = Block[0];
                  }
                  else
                  {
                    v101 = (void *)*((_QWORD *)Block[0] - 1);
                    if ( (unsigned __int64)((char *)Block[0] - (char *)v101 - 8) > 0x1F )
                      goto LABEL_236;
                  }
                  operator delete(v101);
                }
                Size = 0;
                v123 = 15;
                LOBYTE(Block[0]) = 0;
                if ( v120 > 7 )
                {
                  if ( 2 * v120 + 2 < 0x1000 )
                  {
                    v102 = v118[0];
                  }
                  else
                  {
                    v102 = (unsigned __int16 *)*((_QWORD *)v118[0] - 1);
                    if ( (unsigned __int64)((char *)v118[0] - (char *)v102 - 8) > 0x1F )
                      goto LABEL_242;
                  }
                  operator delete(v102);
                }
                v119 = 0;
                v120 = 7;
                LOWORD(v118[0]) = 0;
                if ( v126 > 7 )
                {
                  if ( 2 * v126 + 2 < 0x1000 )
                  {
                    v103 = v124[0];
                  }
                  else
                  {
                    v103 = (void *)*((_QWORD *)v124[0] - 1);
                    if ( (unsigned __int64)((char *)v124[0] - (char *)v103 - 8) > 0x1F )
                      goto LABEL_248;
                  }
                  operator delete(v103);
                }
                v125 = 0;
                v126 = 7;
                LOWORD(v124[0]) = 0;
                if ( !v13 )
                  goto LABEL_220;
                goto LABEL_219;
              }
              if ( v35 )
                ReleaseSRWLockShared(v35);
              AcquireSRWLockExclusive(v35);
              *(_QWORD *)&EventDescriptor.Id = v35;
              v66 = (__int64)v35[1].Ptr;
              v107 = v66;
              v67 = *(_QWORD **)(v66 + 8);
              UserData.Reserved = 0;
              v68 = (char *)v66;
              v69 = v117[0];
              if ( !*((_BYTE *)v67 + 25) )
              {
                while ( 1 )
                {
                  v70 = v67 + 4;
                  v71 = Buf2;
                  if ( v117[1] > 0xF )
                    v71 = (void **)Buf2[0];
                  v72 = v67[6];
                  if ( v67[7] > 0xFu )
                    v70 = (_QWORD *)*v70;
                  v73 = v67[6];
                  if ( v69 < v72 )
                    v73 = v69;
                  v74 = memcmp_0(v70, v71, v73);
                  if ( v74 )
                  {
                    if ( v74 < 0 )
                      goto LABEL_152;
                  }
                  else if ( v72 < v69 )
                  {
LABEL_152:
                    v67 = (_QWORD *)v67[2];
                    goto LABEL_149;
                  }
                  v68 = (char *)v67;
                  v67 = (_QWORD *)*v67;
LABEL_149:
                  if ( *((_BYTE *)v67 + 25) )
                  {
                    v75 = (__int64)v35[1].Ptr;
                    v66 = v107;
                    goto LABEL_154;
                  }
                }
              }
              v75 = v66;
LABEL_154:
              if ( v68[25] )
                goto LABEL_166;
              v76 = v68 + 32;
              v77 = *((_QWORD *)v68 + 6);
              if ( *((_QWORD *)v68 + 7) > 0xFu )
                v76 = (_QWORD *)*v76;
              v78 = Buf2;
              if ( v117[1] > 0xF )
                v78 = (void **)Buf2[0];
              v79 = v69;
              if ( v77 < v69 )
                v79 = *((_QWORD *)v68 + 6);
              v80 = memcmp_0(v78, v76, v79);
              if ( v80 )
              {
                if ( v80 < 0 )
                  goto LABEL_165;
              }
              else if ( v69 < v77 )
              {
LABEL_165:
                v75 = (__int64)v35[1].Ptr;
LABEL_166:
                v68 = (char *)v75;
              }
              if ( v68 == (char *)v66 )
              {
                v81 = operator new(0x30u);
                v107 = (__int64)v81;
                v81[2] = 1;
                v81[3] = 1;
                *(_QWORD *)v81 = &std::_Ref_count_obj2<Windows::Internal::Security::Authentication::Web::CWamProfiler>::`vftable';
                v81[4] = 1;
                *((_QWORD *)v81 + 3) = 0;
                *((_QWORD *)v81 + 4) = 0;
                *((_QWORD *)v81 + 5) = 0;
                v82 = operator new(0x50u);
                *v82 = v82;
                v82[1] = v82;
                v82[2] = v82;
                *((_WORD *)v82 + 12) = 257;
                *((_QWORD *)v81 + 4) = v82;
                v107 = 3;
                v104 = 3;
                Src = v81 + 4;
                v109 = v81;
                Windows::Internal::Security::Authentication::Web::CWamProfiler::ProfileCaller(v81 + 4, v118);
                std::_Tree<std::_Tmap_traits<std::string,std::shared_ptr<Windows::Internal::Security::Authentication::Web::CWamProfiler>,std::less<std::string>,std::allocator<std::pair<std::string const,std::shared_ptr<Windows::Internal::Security::Authentication::Web::CWamProfiler>>>,0>>::_Find_lower_bound<std::string>(
                  (__int64)string,
                  &UserData,
                  (size_t *)Buf2);
                inserted = (__int64)v128;
                if ( !v128[25] )
                {
                  v84 = v128 + 32;
                  v85 = *((_QWORD *)v128 + 6);
                  if ( *((_QWORD *)v128 + 7) > 0xFu )
                    v84 = (_QWORD *)*v84;
                  v86 = v117[0];
                  v87 = Buf2;
                  if ( v117[1] > 0xF )
                    v87 = (void **)Buf2[0];
                  v88 = v117[0];
                  if ( v85 < v117[0] )
                    v88 = *((_QWORD *)v128 + 6);
                  v89 = memcmp_0(v87, v84, v88);
                  if ( v89 )
                  {
                    if ( v89 < 0 )
                      goto LABEL_179;
LABEL_181:
                    *(_QWORD *)(inserted + 64) = v81 + 4;
                    v92 = *(std::_Ref_count_base **)(inserted + 72);
                    *(_QWORD *)(inserted + 72) = v81;
                    if ( v92 )
                      std::_Ref_count_base::_Decref(v92);
                    if ( SRWLock )
                      ReleaseSRWLockExclusive(SRWLock);
                    std::string::~string(Buf2);
                    std::string::~string(Block);
                    std::wstring::_Tidy_deallocate(v118);
                    std::wstring::_Tidy_deallocate(v124);
                    if ( v13 )
                      WindowsDeleteString(v13);
                    v93 = v111;
                    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::~unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>(&v105);
                    return v93;
                  }
                  if ( v86 >= v85 )
                    goto LABEL_181;
                }
LABEL_179:
                if ( *((_QWORD *)string + 1) == 0x333333333333333LL )
                  std::_Throw_tree_length_error();
                v90 = *(_QWORD *)string;
                v114 = (struct _EVENT_DATA_DESCRIPTOR)(unsigned __int64)string;
                v91 = operator new(0x50u);
                v91[2] = *(_OWORD *)Buf2;
                v91[3] = *(_OWORD *)v117;
                v117[0] = 0;
                v117[1] = 15;
                LOBYTE(Buf2[0]) = 0;
                *((_QWORD *)v91 + 8) = 0;
                *((_QWORD *)v91 + 9) = 0;
                *(_QWORD *)v91 = v90;
                *((_QWORD *)v91 + 1) = v90;
                *((_QWORD *)v91 + 2) = v90;
                *((_WORD *)v91 + 12) = 0;
                v114 = UserData;
                inserted = std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Insert_node(string, &v114, v91);
                goto LABEL_181;
              }
              if ( (unsigned __int8)Windows::Internal::Security::Authentication::Web::CWamProfiler::ProfileCaller(
                                      *((_QWORD *)v68 + 8),
                                      v118) )
              {
                v94 = (const unsigned __int16 *)v118;
                if ( v120 > 7 )
                  v94 = v118[0];
                Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::AddNoisyTelemetryTrace(
                  (const char *const)Src,
                  v94);
              }
              v104 = 0;
              if ( v35 )
                ReleaseSRWLockExclusive(v35);
              if ( v117[1] <= 0xF )
                goto LABEL_200;
              if ( v117[1] + 1 < 0x1000 )
              {
                v95 = Buf2[0];
LABEL_199:
                operator delete(v95);
LABEL_200:
                v117[0] = 0;
                v117[1] = 15;
                LOBYTE(Buf2[0]) = 0;
                if ( v123 <= 0xF )
                {
LABEL_206:
                  Size = 0;
                  v123 = 15;
                  LOBYTE(Block[0]) = 0;
                  if ( v120 <= 7 )
                  {
LABEL_212:
                    v119 = 0;
                    v120 = 7;
                    LOWORD(v118[0]) = 0;
                    if ( v126 <= 7 )
                      goto LABEL_218;
                    if ( 2 * v126 + 2 < 0x1000 )
                    {
                      v98 = v124[0];
LABEL_217:
                      operator delete(v98);
LABEL_218:
                      v125 = 0;
                      v126 = 7;
                      LOWORD(v124[0]) = 0;
                      if ( !v13 )
                      {
LABEL_220:
                        wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                          &v105,
                          0);
                        return v111;
                      }
LABEL_219:
                      WindowsDeleteString(v13);
                      goto LABEL_220;
                    }
                    v98 = (void *)*((_QWORD *)v124[0] - 1);
                    if ( (unsigned __int64)((char *)v124[0] - (char *)v98 - 8) <= 0x1F )
                      goto LABEL_217;
LABEL_248:
                    __fastfail(5u);
                  }
                  if ( 2 * v120 + 2 < 0x1000 )
                  {
                    v97 = v118[0];
LABEL_211:
                    operator delete(v97);
                    goto LABEL_212;
                  }
                  v97 = (unsigned __int16 *)*((_QWORD *)v118[0] - 1);
                  if ( (unsigned __int64)((char *)v118[0] - (char *)v97 - 8) <= 0x1F )
                    goto LABEL_211;
LABEL_242:
                  __fastfail(5u);
                }
                if ( v123 + 1 < 0x1000 )
                {
                  v96 = Block[0];
LABEL_205:
                  operator delete(v96);
                  goto LABEL_206;
                }
                v96 = (void *)*((_QWORD *)Block[0] - 1);
                if ( (unsigned __int64)((char *)Block[0] - (char *)v96 - 8) <= 0x1F )
                  goto LABEL_205;
LABEL_236:
                __fastfail(5u);
              }
              v95 = (void *)*((_QWORD *)Buf2[0] - 1);
              if ( (unsigned __int64)((char *)Buf2[0] - (char *)v95 - 8) <= 0x1F )
                goto LABEL_199;
LABEL_230:
              __fastfail(5u);
            }
            if ( v44 < 0x1000 )
            {
              v45 = operator new(v44);
              goto LABEL_99;
            }
            v37 = v19 + 40;
            if ( v19 + 40 < v19 + 1 )
              std::_Throw_bad_array_new_length();
          }
          v46 = operator new(v37);
          if ( !v46 )
            __fastfail(5u);
          v45 = (void *)(((unsigned __int64)v46 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v45 - 1) = v46;
          goto LABEL_99;
        }
      }
      else
      {
        v23 = 0x7FFFFFFFFFFFFFFFLL;
        v24 = -2;
      }
      if ( v24 < 0x1000 )
      {
        v25 = (unsigned __int16 *)operator new(v24);
        v26 = v25;
      }
      else
      {
        if ( v24 + 39 < v24 )
          std::_Throw_bad_array_new_length();
        v27 = operator new(v24 + 39);
        if ( !v27 )
          goto LABEL_236;
        v25 = (unsigned __int16 *)(((unsigned __int64)v27 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v25 - 1) = v27;
        v26 = v25;
      }
      goto LABEL_47;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  if ( (unsigned int)dword_180175000 > 2 )
  {
    v104 = v9;
    v131 = &v104;
    v132 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180175008;
    UserData.Size = *(unsigned __int16 *)off_180175008;
    UserData.Reserved = 2;
    v128 = byte_180146A25;
    v129 = 52;
    v130 = 1;
    LODWORD(Src) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
    a2 + 8,
    0);
  v104 = 0;
  wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
    &v105,
    0);
  return a2;
}

```

## disassembly

```asm
0x180021750  push    rbx
0x180021752  push    rsi
0x180021753  push    rdi
0x180021754  push    r12
0x180021756  push    r13
0x180021758  push    r14
0x18002175a  push    r15
0x18002175c  sub     rsp, 160h
0x180021763  mov     rax, cs:__security_cookie
0x18002176a  xor     rax, rsp
0x18002176d  mov     [rsp+198h+var_40], rax
0x180021775  mov     [rsp+198h+Src], r9
0x18002177a  mov     rdi, r8
0x18002177d  mov     r12, rdx
0x180021780  mov     [rsp+198h+var_130], rdx
0x180021785  mov     [rsp+198h+var_118], rdx
0x18002178d  mov     r15d, 1
0x180021793  mov     [rsp+198h+var_168], r15d
0x180021798  mov     r14, cs:?g_WAMCallerProfiler@@3PEAVCWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@EA; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler * g_WAMCallerProfiler
0x18002179f  mov     [rsp+198h+SRWLock], r14
0x1800217a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800217ab  mov     ecx, 140h; unsigned __int64
0x1800217b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800217b5  xor     esi, esi
0x1800217b7  test    rax, rax
0x1800217ba  jz      short loc_180021800
0x1800217bc  mov     [rax], si
0x1800217bf  mov     [rax+8], rsi
0x1800217c3  mov     [rax+10h], rsi
0x1800217c7  mov     [rax+18h], esi
0x1800217ca  mov     [rax+20h], rsi
0x1800217ce  mov     [rax+28h], rsi
0x1800217d2  mov     [rax+30h], rsi
0x1800217d6  mov     [rax+38h], rsi
0x1800217da  mov     [rax+40h], rsi
0x1800217de  mov     [rax+48h], rsi
0x1800217e2  mov     [rax+120h], rsi
0x1800217e9  mov     [rax+128h], rsi
0x1800217f0  mov     [rax+130h], rsi
0x1800217f7  mov     [rax+138h], rsi
0x1800217fe  jmp     short loc_180021803
0x180021800  mov     rax, rsi
0x180021803  mov     byte ptr [r12], 0
0x180021808  mov     [rsp+198h+var_160], rsi
0x18002180d  mov     [r12+8], rax
0x180021812  mov     [rsp+198h+var_168], r15d
0x180021817  cmp     byte ptr [r14+48h], 0
0x18002181c  jnz     short loc_180021836
0x18002181e  mov     [rsp+198h+var_168], esi
0x180021822  xor     edx, edx
0x180021824  lea     rcx, [rsp+198h+var_160]
0x180021829  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002182e  mov     rax, r12
0x180021831  jmp     loc_180022851
0x180021836  test    rax, rax
0x180021839  jz      loc_180022747
0x18002183f  movzx   r9d, [rsp+198h+arg_20]; bool
0x180021848  xor     r8d, r8d; unsigned __int64
0x18002184b  mov     rdx, rdi; struct IUnknown *
0x18002184e  mov     rcx, rax; this
0x180021851  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x180021856  mov     ecx, eax
0x180021858  test    eax, eax
0x18002185a  js      loc_18002274C
0x180021860  call    cs:__imp_GetTickCount64
0x180021866  mov     rdi, rax
0x180021869  mov     rcx, r14; SRWLock
0x18002186c  call    cs:__imp_AcquireSRWLockShared
0x180021872  mov     rcx, rdi
0x180021875  sub     rcx, [r14+40h]
0x180021879  cmp     rcx, cs:qword_180175A08
0x180021880  mov     rcx, r14; SRWLock
0x180021883  jbe     short loc_1800218CC
0x180021885  call    cs:__imp_ReleaseSRWLockShared
0x18002188b  mov     rcx, r14; SRWLock
0x18002188e  call    cs:__imp_AcquireSRWLockExclusive
0x180021894  mov     rcx, rdi
0x180021897  sub     rcx, [r14+40h]
0x18002189b  cmp     rcx, cs:qword_180175A08
0x1800218a2  jbe     short loc_1800218C1
0x1800218a4  xor     edx, edx; Context
0x1800218a6  mov     r8d, 10h; Flags
0x1800218ac  lea     rcx, ?DumpProfilerData@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@SAKPEAX@Z; Function
0x1800218b3  call    cs:__imp_QueueUserWorkItem
0x1800218b9  test    eax, eax
0x1800218bb  jz      short loc_1800218C1
0x1800218bd  mov     [r14+40h], rdi
0x1800218c1  mov     rcx, r14; SRWLock
0x1800218c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800218ca  jmp     short loc_1800218D2
0x1800218cc  call    cs:__imp_ReleaseSRWLockShared
0x1800218d2  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800218d8  cmp     ecx, 0FFFFFFFFh
0x1800218db  jnz     short loc_1800218F5
0x1800218dd  mov     [rsp+198h+var_168], esi
0x1800218e1  xor     edx, edx
0x1800218e3  lea     rcx, [rsp+198h+var_160]
0x1800218e8  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800218ed  mov     rax, r12
0x1800218f0  jmp     loc_180022851
0x1800218f5  call    cs:__imp_TlsGetValue
0x1800218fb  cmp     rax, 1
0x1800218ff  jz      loc_18002272F
0x180021905  mov     rdx, r15; lpTlsValue
0x180021908  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002190e  call    cs:__imp_TlsSetValue
0x180021914  test    eax, eax
0x180021916  jz      loc_18002272F
0x18002191c  mov     byte ptr [r12], 1
0x180021921  lea     rdx, [rsp+198h+string]
0x180021926  mov     rcx, [r12+8]
0x18002192b  call    ?GetCallingAppNameForProfiling@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA?AVString@56@XZ; Windows::Internal::Security::Authentication::Web::CallerContext::GetCallingAppNameForProfiling(void)
0x180021930  mov     rbx, [rax]
0x180021933  mov     [rsp+198h+var_F8], rbx
0x18002193b  mov     [rax], rsi
0x18002193e  mov     rcx, [rsp+198h+string]; string
0x180021943  test    rcx, rcx
0x180021946  jz      short loc_18002194E
0x180021948  call    cs:__imp_WindowsDeleteString
0x18002194e  xor     edx, edx; length
0x180021950  mov     rcx, rbx; string
0x180021953  call    cs:__imp_WindowsGetStringRawBuffer
0x180021959  lea     rdx, aTokenbroker_0; "tokenbroker"
0x180021960  mov     rcx, rax
0x180021963  call    cs:__imp__o__wcsicmp
0x180021969  test    eax, eax
0x18002196b  jnz     short loc_180021994
0x18002196d  mov     [rsp+198h+var_168], esi
0x180021971  test    rbx, rbx
0x180021974  jz      short loc_180021980
0x180021976  mov     rcx, rbx; string
0x180021979  call    cs:__imp_WindowsDeleteString
0x18002197f  nop
0x180021980  xor     edx, edx
0x180021982  lea     rcx, [rsp+198h+var_160]
0x180021987  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002198c  mov     rax, r12
0x18002198f  jmp     loc_180022851
0x180021994  xor     edx, edx; length
0x180021996  mov     rcx, rbx; string
0x180021999  call    cs:__imp_WindowsGetStringRawBuffer
0x18002199f  xorps   xmm0, xmm0
0x1800219a2  movups  xmmword ptr [rsp+198h+var_90], xmm0
0x1800219aa  mov     [rsp+198h+var_80], rsi
0x1800219b2  mov     [rsp+198h+var_78], rsi
0x1800219ba  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800219c1  mov     r8, r14
0x1800219c4  inc     r8
0x1800219c7  cmp     word ptr [rax+r8*2], 0
0x1800219cd  jnz     short loc_1800219C4
0x1800219cf  mov     rdx, rax
0x1800219d2  lea     rcx, [rsp+198h+var_90]
0x1800219da  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800219df  nop
0x1800219e0  xorps   xmm0, xmm0
0x1800219e3  movups  xmmword ptr [rsp+198h+var_D0], xmm0
0x1800219eb  mov     [rsp+198h+var_C0], rsi
0x1800219f3  mov     [rsp+198h+var_B8], 7
0x1800219ff  mov     word ptr [rsp+198h+var_D0], si
0x180021a07  mov     r15, [rsp+198h+var_80]
0x180021a0f  test    r15, r15
0x180021a12  jnz     short loc_180021A34
0x180021a14  mov     [rsp+198h+var_C0], r15
0x180021a1c  mov     word ptr [rsp+r15*2+198h+var_D0], si
0x180021a25  mov     r13, 7FFFFFFFFFFFFFFFh
0x180021a2f  jmp     loc_180021B4B
0x180021a34  cmp     r15, 7
0x180021a38  ja      short loc_180021A71
0x180021a3a  mov     [rsp+198h+var_C0], r15
0x180021a42  lea     rdi, [rsp+198h+var_D0]
0x180021a4a  lea     rdx, [r15+r15]
0x180021a4e  mov     rcx, rdx
0x180021a51  shr     rcx, 1
0x180021a54  movzx   eax, si
0x180021a57  rep stosw
0x180021a5a  mov     word ptr [rsp+rdx+198h+var_D0], si
0x180021a62  mov     r13, 7FFFFFFFFFFFFFFFh
0x180021a6c  jmp     loc_180021B4B
0x180021a71  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180021a7b  cmp     r15, rcx
0x180021a7e  ja      loc_180022874
0x180021a84  mov     rax, r15
0x180021a87  or      rax, 7
0x180021a8b  mov     r13, 7FFFFFFFFFFFFFFFh
0x180021a95  cmp     rax, rcx
0x180021a98  jbe     short loc_180021ABC
0x180021a9a  mov     rdi, r13
0x180021a9d  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180021aa4  cmp     rcx, 1000h
0x180021aab  jb      short loc_180021B08
0x180021aad  lea     rax, [rcx+27h]
0x180021ab1  cmp     rax, rcx
0x180021ab4  jbe     loc_18002287A
0x180021aba  jmp     short loc_180021AE6
0x180021abc  mov     ecx, 0Ah
0x180021ac1  cmp     rax, rcx
0x180021ac4  cmovb   rax, rcx
0x180021ac8  lea     rdi, [rax+1]
0x180021acc  cmp     rdi, r13
0x180021acf  ja      loc_18002287F
0x180021ad5  lea     rcx, [rdi+rdi]
0x180021ad9  test    rcx, rcx
0x180021adc  jnz     short loc_180021AA4
0x180021ade  mov     r8, rsi
0x180021ae1  mov     rcx, rsi
0x180021ae4  jmp     short loc_180021B13
0x180021ae6  mov     rcx, rax; Size
0x180021ae9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021aee  test    rax, rax
0x180021af1  jz      loc_18002260D
0x180021af7  lea     r8, [rax+27h]
0x180021afb  and     r8, 0FFFFFFFFFFFFFFE0h
0x180021aff  mov     [r8-8], rax
0x180021b03  mov     rcx, r8
0x180021b06  jmp     short loc_180021B13
0x180021b08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021b0d  mov     r8, rax
0x180021b10  mov     rcx, rax
0x180021b13  mov     rdx, r15
0x180021b16  dec     rdi
0x180021b19  mov     rax, r15
0x180021b1c  mov     [rsp+198h+var_C0], rax
0x180021b24  mov     [rsp+198h+var_B8], rdi
0x180021b2c  movzx   eax, si
0x180021b2f  mov     rdi, rcx
0x180021b32  mov     rcx, r15
0x180021b35  rep stosw
0x180021b38  sub     rdx, 1
0x180021b3c  jnz     short loc_180021B38
0x180021b3e  mov     [r8+r15*2], si
0x180021b43  mov     [rsp+198h+var_D0], r8
0x180021b4b  lea     r12, [rsp+198h+var_D0]
0x180021b53  cmp     [rsp+198h+var_B8], 7
0x180021b5c  cmova   r12, [rsp+198h+var_D0]
0x180021b65  lea     rdx, [rsp+198h+var_90]
0x180021b6d  cmp     [rsp+198h+var_78], 7
0x180021b76  cmova   rdx, [rsp+198h+var_90]
0x180021b7f  mov     rax, [rsp+198h+var_80]
0x180021b87  lea     rax, [rdx+rax*2]
0x180021b8b  mov     [rsp+198h+string], rax
0x180021b90  lea     r15, [rsp+198h+var_90]
0x180021b98  cmova   r15, [rsp+198h+var_90]
0x180021ba1  mov     rdi, cs:__imp__o_towlower
0x180021ba8  cmp     r15, rax
0x180021bab  jz      short loc_180021BCD
0x180021bad  movzx   ecx, word ptr [r15]
0x180021bb1  mov     rax, rdi
0x180021bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bb9  mov     [r12], ax
0x180021bbe  add     r15, 2
0x180021bc2  add     r12, 2
0x180021bc6  mov     rax, [rsp+198h+string]
0x180021bcb  jmp     short loc_180021BA8
0x180021bcd  mov     r12, [rsp+198h+SRWLock]
0x180021bd2  lea     rcx, [r12+18h]
0x180021bd7  lea     rdx, [rsp+198h+var_D0]
0x180021bdf  call    ?ProfileCaller@CWamProfiler@Web@Authentication@Security@Internal@Windows@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::Security::Authentication::Web::CWamProfiler::ProfileCaller(std::wstring const &)
0x180021be4  test    al, al
0x180021be6  jz      short loc_180021C07
0x180021be8  lea     rcx, [rsp+198h+var_D0]
0x180021bf0  cmp     [rsp+198h+var_B8], 7
0x180021bf9  cmova   rcx, [rsp+198h+var_D0]; unsigned __int16 *
0x180021c02  call    ?AddAggNoisyTelemetryTrace@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@CAXQEBG@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::AddAggNoisyTelemetryTrace(ushort const * const)
0x180021c07  xorps   xmm0, xmm0
0x180021c0a  movups  xmmword ptr [rsp+198h+Block], xmm0
0x180021c12  mov     [rsp+198h+Size], rsi
0x180021c1a  mov     [rsp+198h+var_98], rsi
0x180021c22  mov     rcx, [rsp+198h+Src]
0x180021c27  nop     word ptr [rax+rax+00000000h]
0x180021c30  inc     r14
0x180021c33  cmp     byte ptr [rcx+r14], 0
0x180021c38  jnz     short loc_180021C30
0x180021c3a  cmp     r14, r13
0x180021c3d  ja      loc_180022884
0x180021c43  cmp     r14, 0Fh
0x180021c47  ja      short loc_180021C88
0x180021c49  mov     [rsp+198h+Size], r14
0x180021c51  mov     [rsp+198h+var_98], 0Fh
0x180021c5d  mov     r8, r14; Size
0x180021c60  mov     rdx, rcx; Src
0x180021c63  lea     rcx, [rsp+198h+Block]; void *
0x180021c6b  call    memcpy_0
0x180021c70  mov     byte ptr [rsp+r14+198h+Block], 0
0x180021c79  mov     r15, 8000000000000027h
0x180021c83  jmp     loc_180021D45
0x180021c88  mov     rdi, r14
0x180021c8b  or      rdi, 0Fh
0x180021c8f  cmp     rdi, r13
0x180021c92  jbe     short loc_180021CA6
0x180021c94  mov     rdi, r13
0x180021c97  mov     r15, 8000000000000027h
0x180021ca1  mov     rax, r15
0x180021ca4  jmp     short loc_180021CE1
0x180021ca6  mov     r12d, 16h
0x180021cac  cmp     rdi, r12
0x180021caf  cmovb   rdi, r12
0x180021cb3  lea     rcx, [rdi+1]; Size
0x180021cb7  test    rcx, rcx
0x180021cba  jnz     short loc_180021CC1
0x180021cbc  mov     r12, rsi
  ... truncated ...
```
