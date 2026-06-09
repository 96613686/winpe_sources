# Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::CreateAgentInstance(ushort const *,_GUID const &,IStandardCollectorAgent * *)

- ea: `0x180006544`
- end: `0x180006b51`
- name: `?CreateAgentInstance@CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJPEBGAEBU_GUID@@PEAPEAUIStandardCollectorAgent@@@Z`
- size: `1549`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *this, const unsigned __int16 *, const struct _GUID *, struct IStandardCollectorAgent **)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004c80`
- `0x180006190`

## callees

- `0x180006544`
- `0x180006c5c`
- `0x180008d3c`
- `0x18000a078`
- `0x18000b914`
- `0x18003d864`
- `0x180041834`
- `0x180041938`
- `0x180041968`
- `0x180041a18`
- `0x180041a48`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180006ae1`
- `KERNEL32!LocalFree` at `0x180006ae1`
- `KERNEL32!LoadLibraryExW` at `0x180006676`
- `KERNEL32!LoadLibraryExW` at `0x180006676`
- `KERNEL32!LeaveCriticalSection` at `0x1800067bb`
- `KERNEL32!LeaveCriticalSection` at `0x180006b16`
- `KERNEL32!LeaveCriticalSection` at `0x1800067bb`
- `KERNEL32!LeaveCriticalSection` at `0x180006b16`
- `KERNEL32!EnterCriticalSection` at `0x180006787`
- `KERNEL32!EnterCriticalSection` at `0x180006787`
- `KERNEL32!GetLastError` at `0x18000668d`
- `KERNEL32!GetLastError` at `0x1800067db`
- `KERNEL32!GetLastError` at `0x18000668d`
- `KERNEL32!GetLastError` at `0x1800067db`
- `KERNEL32!GetProcAddress` at `0x1800067d0`
- `KERNEL32!GetProcAddress` at `0x1800067d0`

## string_xrefs

- `0x1800065f4`: `Name of agent DLL is invalid. Agent %s will not be loaded`
- `0x180006643`: `Valid agent assembly path found at '%s'`
- `0x1800066e6`: `Agent binary does not match bitness of the current platform.`
- `0x18000675a`: `Failed to load agent DLL. Error: %#08x`
- `0x1800067c6`: `DllGetClassObject`
- `0x180006a2c`: `Failure consuming agent DLL (%s). HRESULT: %#08x`
- `0x180006860`: `CreateInstance of IStandardCollectorAgent failed with HRESULT: %#08x`
- `0x1800068b2`: `CreateInstance of IStandardCollectorAgent (v1) failed with HRESULT: %#08x`
- `0x18000698c`: `IStandardCollectorAgent (v1) was created`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::CreateAgentInstance(
        Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *this,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        struct IStandardCollectorAgent **a4)
{
  const unsigned __int16 *v8; // r8
  const struct _GUID *v9; // rdx
  int v10; // ebx
  struct _GUID **v11; // rcx
  __int128 *p_lpLibFileName; // r9
  const WCHAR *v13; // rcx
  struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent *Library; // rsi
  signed int LastError; // ebx
  unsigned __int16 v16; // r8
  const unsigned __int16 *v17; // r8
  const struct _GUID *v18; // rdx
  unsigned int v19; // edx
  const unsigned __int16 *v20; // r8
  const struct _GUID *v21; // rdx
  struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent **v22; // rdx
  FARPROC ProcAddress; // rax
  signed int v24; // eax
  signed int v25; // ebx
  int v26; // eax
  int v27; // eax
  struct IStandardCollectorAgent *v28; // rax
  __int128 *v30; // r9
  __int128 *v31; // rax
  const unsigned __int16 *v32; // r8
  const struct _GUID *v33; // rdx
  HLOCAL hMem[2]; // [rsp+30h] [rbp-C8h] BYREF
  struct _GUID *v35[2]; // [rsp+40h] [rbp-B8h] BYREF
  struct _GUID *v36[2]; // [rsp+50h] [rbp-A8h] BYREF
  struct _GUID *v37[2]; // [rsp+60h] [rbp-98h] BYREF
  struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent *v38; // [rsp+70h] [rbp-88h] BYREF
  __int64 v39; // [rsp+78h] [rbp-80h] BYREF
  struct IStandardCollectorAgent *v40; // [rsp+80h] [rbp-78h] BYREF
  __int128 lpLibFileName; // [rsp+88h] [rbp-70h] BYREF
  __m128i si128; // [rsp+98h] [rbp-60h]
  void *v43[2]; // [rsp+A8h] [rbp-50h] BYREF

  *a4 = 0;
  lpLibFileName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpLibFileName) = 0;
  if ( !Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::GetValidAgentPath(
          (__int64)this,
          a2,
          (void **)&lpLibFileName) )
  {
    *(_OWORD *)v35 = 0;
    DiagHubCommon::HResultFormatter::HResultFormatter(
      (DiagHubCommon::HResultFormatter *)v35,
      -518979578,
      a2,
      *((_WORD *)this + 42));
    v9 = (const struct _GUID *)L"<unknown error>";
    if ( v35[0] )
      v9 = v35[0];
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v9, v8);
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
      L"Name of agent DLL is invalid. Agent %s will not be loaded",
      a2);
    v10 = (int)v35[1];
    v11 = v35;
LABEL_16:
    DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)v11);
LABEL_67:
    std::wstring::~wstring(&lpLibFileName);
    return (unsigned int)v10;
  }
  if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
  {
    p_lpLibFileName = &lpLibFileName;
    if ( si128.m128i_i64[1] > 7uLL )
      p_lpLibFileName = (__int128 *)lpLibFileName;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
      L"Valid agent assembly path found at '%s'",
      p_lpLibFileName);
  }
  v13 = (const WCHAR *)&lpLibFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v13 = (const WCHAR *)lpLibFileName;
  Library = (struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent *)LoadLibraryExW(v13, 0, 8u);
  v38 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v16 = *((_WORD *)this + 42);
    if ( LastError == 193 )
    {
      *(_OWORD *)v36 = 0;
      DiagHubCommon::HResultFormatter::HResultFormatter((DiagHubCommon::HResultFormatter *)v36, -518979558, v16);
      v18 = (const struct _GUID *)L"<unknown error>";
      if ( v36[0] )
        v18 = v36[0];
      DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v18, v17);
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
        L"Agent binary does not match bitness of the current platform.");
      v10 = (int)v36[1];
      v11 = v36;
    }
    else
    {
      *(_OWORD *)v37 = 0;
      v19 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v19 = LastError;
      DiagHubCommon::HResultFormatter::HResultFormatter((DiagHubCommon::HResultFormatter *)v37, v19, v16);
      v21 = (const struct _GUID *)L"<unknown error>";
      if ( v37[0] )
        v21 = v37[0];
      DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v21, v20);
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
        L"Failed to load agent DLL. Error: %#08x",
        (unsigned int)LastError);
      v10 = (int)v37[1];
      v11 = v37;
    }
    goto LABEL_16;
  }
  hMem[0] = (char *)this + 168;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  v22 = (struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent **)*((_QWORD *)this + 19);
  if ( v22 == *((struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent ***)this + 20) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      std::vector<HINSTANCE__ *>::_Emplace_reallocate<HINSTANCE__ * const &>((_QWORD *)this + 18, v22, &v38);
      Library = v38;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180006B11);
        LeaveCriticalSection((LPCRITICAL_SECTION)hMem[0]);
        std::wstring::~wstring(&lpLibFileName);
        return 2147942414LL;
      }
    }
  }
  else
  {
    *v22 = Library;
    *((_QWORD *)this + 19) += 8LL;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  v39 = 0;
  ProcAddress = GetProcAddress((HMODULE)Library, "DllGetClassObject");
  if ( ProcAddress )
  {
    v25 = ((__int64 (__fastcall *)(const struct _GUID *, GUID *, __int64 *))ProcAddress)(
            a3,
            &GUID_00000001_0000_0000_c000_000000000046,
            &v39);
  }
  else
  {
    v24 = GetLastError();
    v25 = (unsigned __int16)v24 | 0x80070000;
    if ( v24 <= 0 )
      v25 = v24;
  }
  if ( v25 < 0 || !v39 )
  {
    if ( *((_QWORD *)_logger + 21) != *((_QWORD *)_logger + 22) )
    {
      v30 = &lpLibFileName;
      if ( si128.m128i_i64[1] > 7uLL )
        v30 = (__int128 *)lpLibFileName;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
        L"Failure consuming agent DLL (%s). HRESULT: %#08x",
        v30,
        v25);
    }
    v31 = &lpLibFileName;
    if ( si128.m128i_i64[1] > 7uLL )
      v31 = (__int128 *)lpLibFileName;
    v43[0] = v31;
    v43[1] = (void *)v25;
    hMem[0] = 0;
    hMem[1] = (HLOCAL)3775987733LL;
    DiagHubCommon::HResultFormatter::Init(
      (DiagHubCommon::HResultFormatter *)hMem,
      *((_WORD *)this + 42),
      -518979563,
      (const void **const)v43);
    v33 = (const struct _GUID *)L"<unknown error>";
    if ( hMem[0] )
      v33 = (const struct _GUID *)hMem[0];
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v33, v32);
    v10 = (int)hMem[1];
    if ( hMem[0] && hMem[0] != &word_180055D48 && hMem[0] != L"Out of memory" )
      LocalFree(hMem[0]);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    goto LABEL_67;
  }
  v40 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct IStandardCollectorAgent **))(*(_QWORD *)v39 + 24LL))(
          v39,
          0,
          &GUID_bb4a877f_85a4_4891_b7fe_6b28d1c1b059,
          &v40);
  if ( v26 < 0 )
  {
    _mm_lfence();
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
      L"CreateInstance of IStandardCollectorAgent failed with HRESULT: %#08x",
      (unsigned int)v26);
    v38 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent **))(*(_QWORD *)v39 + 24LL))(
            v39,
            0,
            &GUID_834d11ed_31e5_4030_b9e4_8bff1fe6f3eb,
            &v38);
    v10 = v27;
    if ( v27 < 0 )
    {
      _mm_lfence();
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
        L"CreateInstance of IStandardCollectorAgent (v1) failed with HRESULT: %#08x",
        (unsigned int)v27);
      if ( v38 )
        (*(void (__fastcall **)(struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent *))(*(_QWORD *)v38 + 16LL))(v38);
      if ( v40 )
        (*(void (__fastcall **)(struct IStandardCollectorAgent *))(*(_QWORD *)v40 + 16LL))(v40);
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      goto LABEL_67;
    }
    v10 = Microsoft::DiagnosticsHub::StandardCollector::AgentWrapper_v1::CreateAgentInstance(v38, &v40);
    if ( v10 < 0 )
    {
      _mm_lfence();
      if ( v38 )
        (*(void (__fastcall **)(struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent *))(*(_QWORD *)v38 + 16LL))(v38);
      if ( v40 )
        (*(void (__fastcall **)(struct IStandardCollectorAgent *))(*(_QWORD *)v40 + 16LL))(v40);
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      goto LABEL_67;
    }
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
      L"IStandardCollectorAgent (v1) was created");
    if ( v38 )
      (*(void (__fastcall **)(struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent *))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v28 = v40;
  v40 = 0;
  *a4 = v28;
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  std::wstring::~wstring(&lpLibFileName);
  return 0;
}

```

## disassembly

```asm
0x180006544  mov     r11, rsp
0x180006547  push    rbx
0x180006548  push    rsi
0x180006549  push    r12
0x18000654b  push    r13
0x18000654d  push    r14
0x18000654f  push    r15
0x180006551  sub     rsp, 0C8h
0x180006558  mov     rax, cs:__security_cookie
0x18000655f  xor     rax, rsp
0x180006562  mov     [rsp+0F8h+var_40], rax
0x18000656a  mov     r15, r9
0x18000656d  mov     r12, r8
0x180006570  mov     rbx, rdx
0x180006573  mov     r14, rcx
0x180006576  xor     r13d, r13d
0x180006579  mov     [r9], r13
0x18000657c  xorps   xmm0, xmm0
0x18000657f  movups  xmmword ptr [r11-70h], xmm0
0x180006584  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000658c  movdqu  xmmword ptr [r11-60h], xmm1
0x180006592  mov     [r11-70h], r13w
0x180006597  lea     r8, [r11-70h]
0x18000659b  call    ?GetValidAgentPath@CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@AEAA_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::GetValidAgentPath(ushort const *,std::wstring &)
0x1800065a0  test    al, al
0x1800065a2  jnz     short loc_180006615
0x1800065a4  xorps   xmm0, xmm0
0x1800065a7  movups  xmmword ptr [rsp+0F8h+var_B8], xmm0
0x1800065ac  movzx   r9d, word ptr [r14+54h]; unsigned __int16
0x1800065b1  mov     r8, rbx; unsigned __int16 *
0x1800065b4  mov     edx, 0E1110006h; int
0x1800065b9  lea     rcx, [rsp+0F8h+var_B8]; this
0x1800065be  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JPEBGG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort const *,ushort)
0x1800065c3  nop
0x1800065c4  lea     rdx, aUnknownError; "<unknown error>"
0x1800065cb  mov     rax, [rsp+0F8h+var_B8]
0x1800065d0  test    rax, rax
0x1800065d3  cmovnz  rdx, rax; struct _GUID *
0x1800065d7  lea     rcx, IID_ICollectionSession; this
0x1800065de  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x1800065e3  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800065ea  add     rcx, 0A8h; this
0x1800065f1  mov     r9, rbx
0x1800065f4  lea     r8, aNameOfAgentDll; "Name of agent DLL is invalid. Agent %s "...
0x1800065fb  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180006602  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180006607  mov     ebx, dword ptr [rsp+0F8h+var_B8+8]
0x18000660b  lea     rcx, [rsp+0F8h+var_B8]
0x180006610  jmp     loc_180006702
0x180006615  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000661c  add     rcx, 38h ; '8'; this
0x180006620  mov     rax, [rcx+8]
0x180006624  cmp     [rcx], rax
0x180006627  jz      short loc_180006656
0x180006629  lea     r9, [rsp+0F8h+lpLibFileName]
0x180006631  cmp     [rsp+0F8h+var_58], 7
0x18000663a  cmova   r9, qword ptr [rsp+0F8h+lpLibFileName]
0x180006643  lea     r8, aValidAgentAsse; "Valid agent assembly path found at '%s'"
0x18000664a  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180006651  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180006656  lea     rcx, [rsp+0F8h+lpLibFileName]
0x18000665e  cmp     [rsp+0F8h+var_58], 7
0x180006667  cmova   rcx, qword ptr [rsp+0F8h+lpLibFileName]; lpLibFileName
0x180006670  xor     edx, edx; hFile
0x180006672  lea     r8d, [rdx+8]; dwFlags
0x180006676  call    cs:__imp_LoadLibraryExW
0x18000667c  mov     rsi, rax
0x18000667f  mov     [rsp+0F8h+var_88], rax
0x180006684  test    rax, rax
0x180006687  jnz     loc_180006778
0x18000668d  call    cs:__imp_GetLastError
0x180006693  mov     ebx, eax
0x180006695  movzx   r8d, word ptr [r14+54h]; unsigned __int16
0x18000669a  xorps   xmm0, xmm0
0x18000669d  cmp     eax, 0C1h
0x1800066a2  jnz     short loc_18000670C
0x1800066a4  movups  xmmword ptr [rsp+0F8h+var_A8], xmm0
0x1800066a9  mov     edx, 0E111001Ah; int
0x1800066ae  lea     rcx, [rsp+0F8h+var_A8]; this
0x1800066b3  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort)
0x1800066b8  nop
0x1800066b9  lea     rdx, aUnknownError; "<unknown error>"
0x1800066c0  mov     rax, [rsp+0F8h+var_A8]
0x1800066c5  test    rax, rax
0x1800066c8  cmovnz  rdx, rax; struct _GUID *
0x1800066cc  lea     rcx, IID_ICollectionSession; this
0x1800066d3  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x1800066d8  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800066df  add     rcx, 0A8h; this
0x1800066e6  lea     r8, aAgentBinaryDoe; "Agent binary does not match bitness of "...
0x1800066ed  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800066f4  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800066f9  mov     ebx, dword ptr [rsp+0F8h+var_A8+8]
0x1800066fd  lea     rcx, [rsp+0F8h+var_A8]; this
0x180006702  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x180006707  jmp     loc_180006B00
0x18000670c  movups  xmmword ptr [rsp+0F8h+var_98], xmm0
0x180006711  movzx   edx, bx
0x180006714  or      edx, 80070000h
0x18000671a  test    ebx, ebx
0x18000671c  cmovle  edx, ebx; int
0x18000671f  lea     rcx, [rsp+0F8h+var_98]; this
0x180006724  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort)
0x180006729  nop
0x18000672a  lea     rdx, aUnknownError; "<unknown error>"
0x180006731  mov     rax, [rsp+0F8h+var_98]
0x180006736  test    rax, rax
0x180006739  cmovnz  rdx, rax; struct _GUID *
0x18000673d  lea     rcx, IID_ICollectionSession; this
0x180006744  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x180006749  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180006750  add     rcx, 0A8h; this
0x180006757  mov     r9d, ebx
0x18000675a  lea     r8, aFailedToLoadAg; "Failed to load agent DLL. Error: %#08x"
0x180006761  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180006768  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000676d  mov     ebx, dword ptr [rsp+0F8h+var_98+8]
0x180006771  lea     rcx, [rsp+0F8h+var_98]
0x180006776  jmp     short loc_180006702
0x180006778  lea     rbx, [r14+0A8h]
0x18000677f  mov     [rsp+0F8h+hMem], rbx
0x180006784  mov     rcx, rbx; lpCriticalSection
0x180006787  call    cs:__imp_EnterCriticalSection
0x18000678d  nop
0x18000678e  lea     rcx, [r14+90h]
0x180006795  mov     rdx, [rcx+8]
0x180006799  cmp     rdx, [rcx+10h]
0x18000679d  jz      short loc_1800067A9
0x18000679f  mov     [rdx], rsi
0x1800067a2  add     qword ptr [rcx+8], 8
0x1800067a7  jmp     short loc_1800067B8
0x1800067a9  lea     r8, [rsp+0F8h+var_88]
0x1800067ae  call    ??$_Emplace_reallocate@AEBQEAUHINSTANCE__@@@?$vector@PEAUHINSTANCE__@@V?$allocator@PEAUHINSTANCE__@@@std@@@std@@AEAAPEAPEAUHINSTANCE__@@QEAPEAU2@AEBQEAU2@@Z; std::vector<HINSTANCE__ *>::_Emplace_reallocate<HINSTANCE__ * const &>(HINSTANCE__ * * const,HINSTANCE__ * const &)
0x1800067b3  mov     rsi, [rsp+0F8h+var_88]
0x1800067b8  mov     rcx, rbx; lpCriticalSection
0x1800067bb  call    cs:__imp_LeaveCriticalSection
0x1800067c1  mov     [rsp+0F8h+var_80], r13
0x1800067c6  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x1800067cd  mov     rcx, rsi; hModule
0x1800067d0  call    cs:__imp_GetProcAddress
0x1800067d6  test    rax, rax
0x1800067d9  jnz     short loc_1800067F1
0x1800067db  call    cs:__imp_GetLastError
0x1800067e1  movzx   ebx, ax
0x1800067e4  or      ebx, 80070000h
0x1800067ea  test    eax, eax
0x1800067ec  cmovle  ebx, eax
0x1800067ef  jmp     short loc_180006808
0x1800067f1  lea     r8, [rsp+0F8h+var_80]
0x1800067f6  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x1800067fd  mov     rcx, r12
0x180006800  call    cs:__guard_dispatch_icall_fptr
0x180006806  mov     ebx, eax
0x180006808  test    ebx, ebx
0x18000680a  js      loc_1800069F7
0x180006810  mov     rcx, [rsp+0F8h+var_80]
0x180006815  test    rcx, rcx
0x180006818  jz      loc_1800069F7
0x18000681e  mov     [rsp+0F8h+var_78], r13
0x180006826  mov     rax, [rcx]
0x180006829  lea     r9, [rsp+0F8h+var_78]
0x180006831  lea     r8, _GUID_bb4a877f_85a4_4891_b7fe_6b28d1c1b059
0x180006838  xor     edx, edx
0x18000683a  mov     rax, [rax+18h]
0x18000683e  call    cs:__guard_dispatch_icall_fptr
0x180006844  test    eax, eax
0x180006846  jns     loc_1800069B8
0x18000684c  lfence
0x18000684f  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180006856  add     rcx, 0A8h; this
0x18000685d  mov     r9d, eax
0x180006860  lea     r8, aCreateinstance; "CreateInstance of IStandardCollectorAge"...
0x180006867  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000686e  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180006873  mov     [rsp+0F8h+var_88], r13
0x180006878  mov     rcx, [rsp+0F8h+var_80]
0x18000687d  mov     rax, [rcx]
0x180006880  lea     r9, [rsp+0F8h+var_88]
0x180006885  lea     r8, _GUID_834d11ed_31e5_4030_b9e4_8bff1fe6f3eb
0x18000688c  xor     edx, edx
0x18000688e  mov     rax, [rax+18h]
0x180006892  call    cs:__guard_dispatch_icall_fptr
0x180006898  mov     ebx, eax
0x18000689a  test    eax, eax
0x18000689c  jns     short loc_180006916
0x18000689e  lfence
0x1800068a1  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800068a8  add     rcx, 0A8h; this
0x1800068af  mov     r9d, eax
0x1800068b2  lea     r8, aCreateinstance_0; "CreateInstance of IStandardCollectorAge"...
0x1800068b9  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800068c0  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800068c5  nop
0x1800068c6  mov     rcx, [rsp+0F8h+var_88]
0x1800068cb  test    rcx, rcx
0x1800068ce  jz      short loc_1800068DE
0x1800068d0  mov     rax, [rcx]
0x1800068d3  mov     rax, [rax+10h]
0x1800068d7  call    cs:__guard_dispatch_icall_fptr
0x1800068dd  nop
0x1800068de  mov     rcx, [rsp+0F8h+var_78]
0x1800068e6  test    rcx, rcx
0x1800068e9  jz      short loc_1800068F9
0x1800068eb  mov     rax, [rcx]
0x1800068ee  mov     rax, [rax+10h]
0x1800068f2  call    cs:__guard_dispatch_icall_fptr
0x1800068f8  nop
0x1800068f9  mov     rcx, [rsp+0F8h+var_80]
0x1800068fe  test    rcx, rcx
0x180006901  jz      short loc_180006911
0x180006903  mov     rax, [rcx]
0x180006906  mov     rax, [rax+10h]
0x18000690a  call    cs:__guard_dispatch_icall_fptr
0x180006910  nop
0x180006911  jmp     loc_180006B00
0x180006916  lea     rdx, [rsp+0F8h+var_78]; struct IStandardCollectorAgent **
0x18000691e  mov     rcx, [rsp+0F8h+var_88]; struct v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent *
0x180006923  call    ?CreateAgentInstance@AgentWrapper_v1@StandardCollector@DiagnosticsHub@Microsoft@@SAJPEAUIStandardCollectorAgent@Collectors@34v1@@PEAPEAU5@@Z; Microsoft::DiagnosticsHub::StandardCollector::AgentWrapper_v1::CreateAgentInstance(v1::Microsoft::DiagnosticsHub::Collectors::IStandardCollectorAgent *,IStandardCollectorAgent * *)
0x180006928  mov     ebx, eax
0x18000692a  test    eax, eax
0x18000692c  jns     short loc_180006981
0x18000692e  lfence
0x180006931  mov     rcx, [rsp+0F8h+var_88]
0x180006936  test    rcx, rcx
0x180006939  jz      short loc_180006949
0x18000693b  mov     rax, [rcx]
0x18000693e  mov     rax, [rax+10h]
0x180006942  call    cs:__guard_dispatch_icall_fptr
0x180006948  nop
0x180006949  mov     rcx, [rsp+0F8h+var_78]
0x180006951  test    rcx, rcx
0x180006954  jz      short loc_180006964
0x180006956  mov     rax, [rcx]
0x180006959  mov     rax, [rax+10h]
0x18000695d  call    cs:__guard_dispatch_icall_fptr
0x180006963  nop
0x180006964  mov     rcx, [rsp+0F8h+var_80]
0x180006969  test    rcx, rcx
0x18000696c  jz      short loc_18000697C
0x18000696e  mov     rax, [rcx]
0x180006971  mov     rax, [rax+10h]
0x180006975  call    cs:__guard_dispatch_icall_fptr
0x18000697b  nop
0x18000697c  jmp     loc_180006B00
0x180006981  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180006988  add     rcx, 38h ; '8'; this
0x18000698c  lea     r8, aIstandardcolle; "IStandardCollectorAgent (v1) was create"...
0x180006993  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000699a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000699f  nop
0x1800069a0  mov     rcx, [rsp+0F8h+var_88]
0x1800069a5  test    rcx, rcx
0x1800069a8  jz      short loc_1800069B8
0x1800069aa  mov     rax, [rcx]
0x1800069ad  mov     rax, [rax+10h]
0x1800069b1  call    cs:__guard_dispatch_icall_fptr
0x1800069b7  nop
0x1800069b8  mov     rax, [rsp+0F8h+var_78]
0x1800069c0  mov     [rsp+0F8h+var_78], r13
0x1800069c8  mov     [r15], rax
0x1800069cb  mov     rcx, [rsp+0F8h+var_80]
0x1800069d0  test    rcx, rcx
0x1800069d3  jz      short loc_1800069E3
0x1800069d5  mov     rax, [rcx]
0x1800069d8  mov     rax, [rax+10h]
0x1800069dc  call    cs:__guard_dispatch_icall_fptr
0x1800069e2  nop
0x1800069e3  lea     rcx, [rsp+0F8h+lpLibFileName]
0x1800069eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800069f0  xor     eax, eax
0x1800069f2  jmp     loc_180006B2F
0x1800069f7  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800069fe  add     rcx, 0A8h; this
0x180006a05  mov     rax, [rcx+8]
0x180006a09  cmp     [rcx], rax
0x180006a0c  jz      short loc_180006A3F
0x180006a0e  lea     r9, [rsp+0F8h+lpLibFileName]
0x180006a16  cmp     [rsp+0F8h+var_58], 7
0x180006a1f  cmova   r9, qword ptr [rsp+0F8h+lpLibFileName]
0x180006a28  mov     [rsp+0F8h+var_D8], ebx
0x180006a2c  lea     r8, aFailureConsumi; "Failure consuming agent DLL (%s). HRESU"...
0x180006a33  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180006a3a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180006a3f  lea     rax, [rsp+0F8h+lpLibFileName]
0x180006a47  cmp     [rsp+0F8h+var_58], 7
0x180006a50  cmova   rax, qword ptr [rsp+0F8h+lpLibFileName]
0x180006a59  mov     [rsp+0F8h+var_50], rax
0x180006a61  movsxd  rax, ebx
0x180006a64  mov     [rsp+0F8h+var_48], rax
0x180006a6c  xorps   xmm0, xmm0
0x180006a6f  movups  xmmword ptr [rsp+0F8h+hMem], xmm0
0x180006a74  mov     [rsp+0F8h+hMem], r13
0x180006a79  mov     r8d, 0E1110015h; int
0x180006a7f  mov     dword ptr [rsp+0F8h+hMem+8], r8d
0x180006a84  lea     r9, [rsp+0F8h+var_50]; void **
0x180006a8c  movzx   edx, word ptr [r14+54h]; unsigned __int16
0x180006a91  lea     rcx, [rsp+0F8h+hMem]; this
0x180006a96  call    ?Init@HResultFormatter@DiagHubCommon@@AEAAXGJQEAPEBX@Z; DiagHubCommon::HResultFormatter::Init(ushort,long,void const * * const)
0x180006a9b  nop
0x180006a9c  lea     rdx, aUnknownError; "<unknown error>"
  ... truncated ...
```
