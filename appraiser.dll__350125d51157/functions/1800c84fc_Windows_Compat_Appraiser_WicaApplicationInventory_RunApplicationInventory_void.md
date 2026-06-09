# Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory(void)

- ea: `0x1800c84fc`
- end: `0x1800c8a8f`
- name: `?RunApplicationInventory@WicaApplicationInventory@Appraiser@Compat@Windows@@AEAAJXZ`
- size: `1427`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::WicaApplicationInventory *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c7520`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x18001b324`
- `0x18001b468`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18008e08c`
- `0x18008e3a0`
- `0x18008fadc`
- `0x1800c7424`
- `0x1800c84fc`
- `0x18021f010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800c85ea`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c85ea`
- `ntdll!RtlEnterCriticalSection` at `0x1800c85cd`
- `ntdll!RtlEnterCriticalSection` at `0x1800c85cd`
- `KERNEL32!GetSystemTime` at `0x1800c8928`
- `KERNEL32!GetSystemTime` at `0x1800c8928`
- `KERNEL32!LoadLibraryW` at `0x1800c8608`
- `KERNEL32!LoadLibraryW` at `0x1800c8693`
- `KERNEL32!LoadLibraryW` at `0x1800c8608`
- `KERNEL32!LoadLibraryW` at `0x1800c8693`
- `KERNEL32!GetProcAddress` at `0x1800c8755`
- `KERNEL32!GetProcAddress` at `0x1800c8755`
- `KERNEL32!GetLastError` at `0x1800c86d9`
- `KERNEL32!GetLastError` at `0x1800c8763`
- `KERNEL32!GetLastError` at `0x1800c8a46`
- `KERNEL32!GetLastError` at `0x1800c8a5d`
- `KERNEL32!GetLastError` at `0x1800c8a78`
- `KERNEL32!GetLastError` at `0x1800c86d9`
- `KERNEL32!GetLastError` at `0x1800c8763`
- `KERNEL32!GetLastError` at `0x1800c8a46`
- `KERNEL32!GetLastError` at `0x1800c8a5d`
- `KERNEL32!GetLastError` at `0x1800c8a78`

## string_xrefs

- `0x1800c8679`: `onecore\base\appcompat\appraiser\inventory\applicationinventory.cpp`
- `0x1800c86fa`: `onecore\base\appcompat\appraiser\inventory\applicationinventory.cpp`
- `0x1800c873c`: `onecore\base\appcompat\appraiser\inventory\applicationinventory.cpp`
- `0x1800c87a4`: `onecore\base\appcompat\appraiser\inventory\applicationinventory.cpp`
- `0x1800c87da`: `onecore\base\appcompat\appraiser\inventory\applicationinventory.cpp`
- `0x1800c88ff`: `onecore\base\appcompat\appraiser\inventory\applicationinventory.cpp`
- `0x1800c8647`: `Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory`
- `0x1800c8848`: `Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory`
- `0x1800c88f4`: `Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory`
- `0x1800c89ab`: `Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory`
- `0x1800c8665`: `LoadLibrary(aeinv) failed. Trying to use aepic for application inventory`
- `0x1800c8601`: `aeinv.dll`
- `0x1800c86ee`: `LoadLibrary(aepic) failed: [0x%x].`
- `0x1800c8732`: `LoadLibrary(aepic) failed: [0x%x].`
- `0x1800c868c`: `aepic.dll`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory(
        Windows::Compat::Appraiser::WicaApplicationInventory *this)
{
  char *v2; // rbx
  HMODULE LibraryW; // rbx
  HMODULE v4; // rcx
  const CHAR *v5; // r14
  HMODULE v6; // rbx
  signed int v7; // eax
  signed int v8; // ebx
  const char *v9; // r9
  char v10; // dl
  FARPROC ProcAddress; // r14
  signed int v12; // eax
  int v13; // eax
  int v14; // r15d
  volatile signed __int64 *v15; // rcx
  void **v16; // rdx
  int v17; // r14d
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rcx
  __int64 v21; // rcx
  signed int v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  signed int v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  signed int LastError; // eax
  int v30; // edx
  unsigned int v31; // r8d
  char *v32; // [rsp+20h] [rbp-E0h]
  char *v33; // [rsp+30h] [rbp-D0h]
  void **v34; // [rsp+60h] [rbp-A0h] BYREF
  HMODULE hModule; // [rsp+68h] [rbp-98h]
  int v36; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+74h] [rbp-8Ch] BYREF
  struct _STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  char *v39; // [rsp+88h] [rbp-78h] BYREF
  const char *v40; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v41; // [rsp+98h] [rbp-68h] BYREF
  const size_t *v42; // [rsp+A0h] [rbp-60h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v44; // [rsp+C0h] [rbp-40h]
  __int64 v45; // [rsp+C8h] [rbp-38h] BYREF
  BOOL v46; // [rsp+D0h] [rbp-30h]
  BOOL v47; // [rsp+D4h] [rbp-2Ch]
  int v48; // [rsp+D8h] [rbp-28h]
  BOOL v49; // [rsp+DCh] [rbp-24h]
  struct _SYSTEMTIME v50; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v51[144]; // [rsp+F0h] [rbp-10h] BYREF
  char v52[144]; // [rsp+180h] [rbp+80h] BYREF
  char v53[144]; // [rsp+210h] [rbp+110h] BYREF

  v44 = -2;
  v52[0] = 0;
  v45 = 24;
  v47 = *((_BYTE *)this + 608) != 0;
  v46 = *((_BYTE *)this + 609) != 0;
  v49 = *((_BYTE *)this + 614) != 0;
  v48 = 0;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
  {
    if ( !TraceLoggingCorrelationVector::Increment(Windows::Compat::Appraiser::WicaFactory::CorrelationVector, v52) )
      strcpy(v52, "UNK");
    DestinationString = 0;
    v2 = (char *)P;
    if ( P && (int)AslAnsiStringCreate(&DestinationString) >= 0 )
    {
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v2 + 88));
      AslAnsiStringFree(v2 + 72);
      *(struct _STRING *)(v2 + 72) = DestinationString;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v2 + 88));
    }
  }
  v34 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = 0;
  LibraryW = LoadLibraryW(L"aeinv.dll");
  v4 = 0;
  if ( LibraryW )
  {
    v4 = LibraryW;
    hModule = LibraryW;
  }
  if ( v4 )
  {
    v5 = "GetAppInventory";
  }
  else
  {
    Windows::Compat::Appraiser::WriteLog(
      0,
      235,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\applicationinventory.cpp",
      "Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory",
      0,
      (int)"LoadLibrary(aeinv) failed. Trying to use aepic for application inventory",
      v33);
    v6 = LoadLibraryW(L"aepic.dll");
    v4 = hModule;
    if ( v6 != hModule )
    {
      if ( hModule && !((unsigned __int8 (__fastcall *)(void ***))*v34)(&v34) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v30, v31);
        JUMPOUT(0x1800C8A8ELL);
      }
      v4 = v6;
      hModule = v6;
    }
    v5 = "GetAppInventoryCore";
    if ( !v4 )
    {
      v7 = GetLastError();
      v8 = v7;
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      if ( v8 < 0 )
      {
        v9 = "LoadLibrary(aepic) failed: [0x%x].";
        v10 = -13;
LABEL_20:
        LODWORD(v33) = v8;
        LODWORD(v32) = v8;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          v10,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\applicationinventory.cpp",
          "Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory",
          v32,
          (int)v9,
          v33);
        goto LABEL_36;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xF3u,
          "onecore\\base\\appcompat\\appraiser\\inventory\\applicationinventory.cpp",
          "Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory",
          "LoadLibrary(aepic) failed: [0x%x].",
          v8);
      v4 = hModule;
    }
  }
  ProcAddress = GetProcAddress(v4, v5);
  if ( !ProcAddress )
  {
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = "GetProcAddress(GetAppInventory) failed: [0x%x].";
      v10 = -5;
      goto LABEL_20;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xFBu,
        "onecore\\base\\appcompat\\appraiser\\inventory\\applicationinventory.cpp",
        "Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory",
        "GetProcAddress(GetAppInventory) failed: [0x%x].",
        v8);
  }
  v8 = ((__int64 (__fastcall *)(unsigned __int64, __int64 *, char *))ProcAddress)(
         ((unsigned __int64)this + 16) & -(__int64)(this != 0),
         &v45,
         v52);
  if ( v8 < 0 )
  {
    v9 = "Getting app inventory failed: [0x%x].";
    v10 = 0;
    goto LABEL_20;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x100u,
      "onecore\\base\\appcompat\\appraiser\\inventory\\applicationinventory.cpp",
      "Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory",
      "Getting app inventory failed: [0x%x].",
      v8);
  v8 = 0;
LABEL_36:
  v13 = Windows::Compat::Appraiser::WicaApplicationInventory::EndCurrentAsset(this);
  v14 = v13;
  if ( v13 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x10Bu,
        "onecore\\base\\appcompat\\appraiser\\inventory\\applicationinventory.cpp",
        "Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory",
        "Failed to end asset, swallowing: [0x%x].",
        v8);
  }
  else
  {
    LODWORD(v33) = v8;
    LODWORD(v32) = v13;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      11,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\applicationinventory.cpp",
      "Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory",
      v32,
      (int)"Failed to end asset, swallowing: [0x%x].",
      v33);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v51);
    v15 = (volatile signed __int64 *)v51;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v15 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v15,
      _InterlockedExchangeAdd64(v15 + 17, 0),
      v53);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v16);
    v17 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v39 = v53;
      v36 = v14;
      v40 = "Windows::Compat::Appraiser::WicaApplicationInventory::RunApplicationInventory";
      v41 = "onecore\\base\\appcompat\\appraiser\\inventory\\applicationinventory.cpp";
      v37 = 267;
      v42 = &szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v50 = SystemTime;
      *(_QWORD *)&DestinationString.Length = &v50;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v17,
        (unsigned int)byte_1802A3743,
        v18,
        v19,
        (__int64)&DestinationString,
        (__int64)&v42,
        (__int64)&v37,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v36,
        (__int64)&v39);
    }
  }
  v20 = *((_QWORD *)this + 86);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 16LL))(v20, 1);
    *((_QWORD *)this + 86) = 0;
  }
  v21 = *((_QWORD *)this + 85);
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21);
    *((_QWORD *)this + 85) = 0;
  }
  v34 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v34) )
  {
    v23 = GetLastError();
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
    v26 = GetLastError();
    if ( v26 > 0 )
      v26 = (unsigned __int16)v26 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
    __debugbreak();
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c84fc  push    rbp
0x1800c84fe  push    rbx
0x1800c84ff  push    rsi
0x1800c8500  push    rdi
0x1800c8501  push    r12
0x1800c8503  push    r13
0x1800c8505  push    r14
0x1800c8507  push    r15
0x1800c8509  lea     rbp, [rsp-1B8h]
0x1800c8511  sub     rsp, 2B8h
0x1800c8518  mov     [rbp+1F0h+var_230], 0FFFFFFFFFFFFFFFEh
0x1800c8520  mov     rax, cs:__security_cookie
0x1800c8527  xor     rax, rsp
0x1800c852a  mov     [rbp+1F0h+var_50], rax
0x1800c8531  mov     rsi, rcx
0x1800c8534  xor     r12d, r12d
0x1800c8537  mov     [rbp+1F0h+var_170], r12b
0x1800c853e  mov     [rbp+1F0h+var_228], 18h
0x1800c8546  mov     eax, r12d
0x1800c8549  cmp     [rcx+260h], r12b
0x1800c8550  setnz   al
0x1800c8553  mov     [rbp+1F0h+var_21C], eax
0x1800c8556  mov     eax, r12d
0x1800c8559  cmp     [rcx+261h], r12b
0x1800c8560  setnz   al
0x1800c8563  mov     [rbp+1F0h+var_220], eax
0x1800c8566  mov     eax, r12d
0x1800c8569  cmp     [rcx+266h], r12b
0x1800c8570  setnz   al
0x1800c8573  mov     [rbp+1F0h+var_214], eax
0x1800c8576  mov     [rbp+1F0h+var_218], r12d
0x1800c857a  mov     rcx, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; this
0x1800c8581  test    rcx, rcx
0x1800c8584  jz      short loc_1800C85F0
0x1800c8586  lea     rdx, [rbp+1F0h+var_170]; char *
0x1800c858d  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800c8592  test    al, al
0x1800c8594  jnz     short loc_1800C85A0
0x1800c8596  mov     dword ptr [rbp+1F0h+var_170], 4B4E55h
0x1800c85a0  xorps   xmm0, xmm0
0x1800c85a3  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x1800c85a8  mov     rbx, cs:P
0x1800c85af  test    rbx, rbx
0x1800c85b2  jz      short loc_1800C85F0
0x1800c85b4  lea     rdx, [rbp+1F0h+var_170]
0x1800c85bb  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x1800c85c0  call    AslAnsiStringCreate
0x1800c85c5  test    eax, eax
0x1800c85c7  js      short loc_1800C85F0
0x1800c85c9  lea     rcx, [rbx+58h]; CriticalSection
0x1800c85cd  call    cs:__imp_RtlEnterCriticalSection
0x1800c85d3  lea     rcx, [rbx+48h]
0x1800c85d7  call    AslAnsiStringFree
0x1800c85dc  movups  xmm0, xmmword ptr [rsp+2F0h+DestinationString.Length]
0x1800c85e1  movdqu  xmmword ptr [rbx+48h], xmm0
0x1800c85e6  lea     rcx, [rbx+58h]; CriticalSection
0x1800c85ea  call    cs:__imp_RtlLeaveCriticalSection
0x1800c85f0  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800c85f7  mov     [rsp+2F0h+var_290], rax
0x1800c85fc  mov     [rsp+2F0h+hModule], r12
0x1800c8601  lea     rcx, aAeinvDll; "aeinv.dll"
0x1800c8608  call    cs:__imp_LoadLibraryW
0x1800c860e  mov     rbx, rax
0x1800c8611  mov     rcx, [rsp+2F0h+hModule]
0x1800c8616  cmp     rax, rcx
0x1800c8619  jz      short loc_1800C8642
0x1800c861b  test    rcx, rcx
0x1800c861e  jz      short loc_1800C863A
0x1800c8620  mov     rcx, [rsp+2F0h+var_290]
0x1800c8625  mov     rax, [rcx]
0x1800c8628  lea     rcx, [rsp+2F0h+var_290]
0x1800c862d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8632  test    al, al
0x1800c8634  jz      loc_1800C8A5D
0x1800c863a  mov     rcx, rbx
0x1800c863d  mov     [rsp+2F0h+hModule], rbx
0x1800c8642  mov     edi, 80070000h
0x1800c8647  lea     r15, aWindowsCompatA_469; "Windows::Compat::Appraiser::WicaApplica"...
0x1800c864e  mov     r13d, 1
0x1800c8654  test    rcx, rcx
0x1800c8657  jz      short loc_1800C8665
0x1800c8659  lea     r14, aGetappinventor_0; "GetAppInventory"
0x1800c8660  jmp     loc_1800C8752
0x1800c8665  lea     rax, aLoadlibraryAei; "LoadLibrary(aeinv) failed. Trying to us"...
0x1800c866c  mov     qword ptr [rsp+2F0h+var_2C8], rax; int
0x1800c8671  mov     [rsp+2F0h+var_2D0], r12; char *
0x1800c8676  mov     r9, r15; char *
0x1800c8679  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c8680  mov     edx, 0EBh; bool
0x1800c8685  xor     ecx, ecx; this
0x1800c8687  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c868c  lea     rcx, aAepicDll_0; "aepic.dll"
0x1800c8693  call    cs:__imp_LoadLibraryW
0x1800c8699  mov     rbx, rax
0x1800c869c  mov     rcx, [rsp+2F0h+hModule]
0x1800c86a1  cmp     rax, rcx
0x1800c86a4  jz      short loc_1800C86CD
0x1800c86a6  test    rcx, rcx
0x1800c86a9  jz      short loc_1800C86C5
0x1800c86ab  mov     rcx, [rsp+2F0h+var_290]
0x1800c86b0  mov     rax, [rcx]
0x1800c86b3  lea     rcx, [rsp+2F0h+var_290]
0x1800c86b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c86bd  test    al, al
0x1800c86bf  jz      loc_1800C8A78
0x1800c86c5  mov     rcx, rbx
0x1800c86c8  mov     [rsp+2F0h+hModule], rbx
0x1800c86cd  lea     r14, aGetappinventor; "GetAppInventoryCore"
0x1800c86d4  test    rcx, rcx
0x1800c86d7  jnz     short loc_1800C8752
0x1800c86d9  call    cs:__imp_GetLastError
0x1800c86df  mov     ebx, eax
0x1800c86e1  test    eax, eax
0x1800c86e3  jle     short loc_1800C86EA
0x1800c86e5  movzx   ebx, ax
0x1800c86e8  or      ebx, edi
0x1800c86ea  test    ebx, ebx
0x1800c86ec  jns     short loc_1800C8721
0x1800c86ee  lea     r9, aLoadlibraryAep; "LoadLibrary(aepic) failed: [0x%x]."
0x1800c86f5  mov     edx, 0F3h; bool
0x1800c86fa  lea     r14, aOnecoreBaseApp_33; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c8701  mov     dword ptr [rsp+2F0h+var_2C0], ebx; char *
0x1800c8705  mov     qword ptr [rsp+2F0h+var_2C8], r9; int
0x1800c870a  mov     dword ptr [rsp+2F0h+var_2D0], ebx; char *
0x1800c870e  mov     r9, r15; char *
0x1800c8711  mov     r8, r14; unsigned int
0x1800c8714  mov     ecx, r13d; this
0x1800c8717  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c871c  jmp     loc_1800C8821
0x1800c8721  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c8727  and     eax, r13d
0x1800c872a  test    al, al
0x1800c872c  jz      short loc_1800C874D
0x1800c872e  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x1800c8732  lea     r9, aLoadlibraryAep; "LoadLibrary(aepic) failed: [0x%x]."
0x1800c8739  mov     r8, r15; char *
0x1800c873c  lea     rdx, aOnecoreBaseApp_33; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c8743  mov     ecx, 0F3h; unsigned int
0x1800c8748  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c874d  mov     rcx, [rsp+2F0h+hModule]; hModule
0x1800c8752  mov     rdx, r14; lpProcName
0x1800c8755  call    cs:__imp_GetProcAddress
0x1800c875b  mov     r14, rax
0x1800c875e  test    rax, rax
0x1800c8761  jnz     short loc_1800C87B5
0x1800c8763  call    cs:__imp_GetLastError
0x1800c8769  mov     ebx, eax
0x1800c876b  test    eax, eax
0x1800c876d  jle     short loc_1800C8774
0x1800c876f  movzx   ebx, ax
0x1800c8772  or      ebx, edi
0x1800c8774  test    ebx, ebx
0x1800c8776  jns     short loc_1800C8789
0x1800c8778  lea     r9, aGetprocaddress_1; "GetProcAddress(GetAppInventory) failed:"...
0x1800c877f  mov     edx, 0FBh
0x1800c8784  jmp     loc_1800C86FA
0x1800c8789  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c878f  and     eax, r13d
0x1800c8792  test    al, al
0x1800c8794  jz      short loc_1800C87B5
0x1800c8796  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x1800c879a  lea     r9, aGetprocaddress_1; "GetProcAddress(GetAppInventory) failed:"...
0x1800c87a1  mov     r8, r15; char *
0x1800c87a4  lea     rdx, aOnecoreBaseApp_33; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c87ab  mov     ecx, 0FBh; unsigned int
0x1800c87b0  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c87b5  mov     rax, rsi
0x1800c87b8  lea     rdx, [rsi+10h]
0x1800c87bc  neg     rax
0x1800c87bf  sbb     rcx, rcx
0x1800c87c2  and     rcx, rdx
0x1800c87c5  lea     r8, [rbp+1F0h+var_170]
0x1800c87cc  lea     rdx, [rbp+1F0h+var_228]
0x1800c87d0  mov     rax, r14
0x1800c87d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c87d8  mov     ebx, eax
0x1800c87da  lea     r14, aOnecoreBaseApp_33; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c87e1  test    eax, eax
0x1800c87e3  jns     short loc_1800C87F6
0x1800c87e5  lea     r9, aGettingAppInve; "Getting app inventory failed: [0x%x]."
0x1800c87ec  mov     edx, 100h
0x1800c87f1  jmp     loc_1800C8701
0x1800c87f6  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c87fc  and     eax, r13d
0x1800c87ff  test    al, al
0x1800c8801  jz      short loc_1800C881E
0x1800c8803  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x1800c8807  lea     r9, aGettingAppInve; "Getting app inventory failed: [0x%x]."
0x1800c880e  mov     r8, r15; char *
0x1800c8811  mov     rdx, r14; char *
0x1800c8814  mov     ecx, 100h; unsigned int
0x1800c8819  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c881e  mov     ebx, r12d
0x1800c8821  mov     rcx, rsi; this
0x1800c8824  call    ?EndCurrentAsset@WicaApplicationInventory@Appraiser@Compat@Windows@@AEAAJXZ; Windows::Compat::Appraiser::WicaApplicationInventory::EndCurrentAsset(void)
0x1800c8829  mov     r15d, eax
0x1800c882c  test    eax, eax
0x1800c882e  jns     loc_1800C8993
0x1800c8834  mov     dword ptr [rsp+2F0h+var_2C0], ebx; char *
0x1800c8838  lea     r9, aFailedToEndAss_0; "Failed to end asset, swallowing: [0x%x]"...
0x1800c883f  mov     qword ptr [rsp+2F0h+var_2C8], r9; int
0x1800c8844  mov     dword ptr [rsp+2F0h+var_2D0], eax; char *
0x1800c8848  lea     r9, aWindowsCompatA_469; "Windows::Compat::Appraiser::WicaApplica"...
0x1800c884f  mov     r8, r14; unsigned int
0x1800c8852  mov     edx, 10Bh; bool
0x1800c8857  mov     ecx, r13d; this
0x1800c885a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c885f  lea     rcx, [rbp+1F0h+var_200]; this
0x1800c8863  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800c8868  lea     rcx, [rbp+1F0h+var_200]
0x1800c886c  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800c8873  test    rax, rax
0x1800c8876  cmovnz  rcx, rax; this
0x1800c887a  mov     rdx, r12
0x1800c887d  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800c8886  lea     r8, [rbp+1F0h+var_E0]; char *
0x1800c888d  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800c8892  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r12b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800c8899  jz      short loc_1800C88A7
0x1800c889b  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800c88a2  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800c88a7  mov     r14, cs:qword_1802C9628
0x1800c88ae  mov     eax, [r14]
0x1800c88b1  cmp     eax, 5
0x1800c88b4  jbe     loc_1800C89BF
0x1800c88ba  mov     rcx, [r14+18h]
0x1800c88be  mov     rax, [r14+10h]
0x1800c88c2  mov     rdx, 200000000000h
0x1800c88cc  test    rdx, rax
0x1800c88cf  jz      loc_1800C89BF
0x1800c88d5  mov     rax, rcx
0x1800c88d8  and     rax, rdx
0x1800c88db  cmp     rax, rcx
0x1800c88de  jnz     loc_1800C89BF
0x1800c88e4  lea     rax, [rbp+1F0h+var_E0]
0x1800c88eb  mov     [rbp+1F0h+var_268], rax
0x1800c88ef  mov     [rsp+2F0h+var_280], r15d
0x1800c88f4  lea     rax, aWindowsCompatA_469; "Windows::Compat::Appraiser::WicaApplica"...
0x1800c88fb  mov     [rbp+1F0h+var_260], rax
0x1800c88ff  lea     rax, aOnecoreBaseApp_33; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c8906  mov     [rbp+1F0h+var_258], rax
0x1800c890a  mov     [rsp+2F0h+var_27C], 10Bh
0x1800c8912  lea     rax, szValueBuf
0x1800c8919  mov     [rbp+1F0h+var_250], rax
0x1800c891d  xorps   xmm0, xmm0
0x1800c8920  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x1800c8924  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x1800c8928  call    cs:__imp_GetSystemTime
0x1800c892e  movaps  xmm0, xmmword ptr [rbp+1F0h+SystemTime.wYear]
0x1800c8932  movdqa  [rbp+1F0h+var_210], xmm0
0x1800c8937  lea     rax, [rbp+1F0h+var_210]
0x1800c893b  mov     qword ptr [rsp+2F0h+DestinationString.Length], rax
0x1800c8940  lea     rax, [rbp+1F0h+var_268]
0x1800c8944  mov     [rsp+2F0h+var_2A0], rax
0x1800c8949  lea     rax, [rsp+2F0h+var_280]
0x1800c894e  mov     [rsp+2F0h+var_2A8], rax
0x1800c8953  lea     rax, [rbp+1F0h+var_260]
0x1800c8957  mov     [rsp+2F0h+var_2B0], rax
0x1800c895c  lea     rax, [rbp+1F0h+var_258]
0x1800c8960  mov     [rsp+2F0h+var_2B8], rax
0x1800c8965  lea     rax, [rsp+2F0h+var_27C]
0x1800c896a  mov     [rsp+2F0h+var_2C0], rax
0x1800c896f  lea     rax, [rbp+1F0h+var_250]
0x1800c8973  mov     qword ptr [rsp+2F0h+var_2C8], rax
0x1800c8978  lea     rax, [rsp+2F0h+DestinationString]
0x1800c897d  mov     [rsp+2F0h+var_2D0], rax
0x1800c8982  lea     rdx, byte_1802A3743
0x1800c8989  mov     rcx, r14
0x1800c898c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c8991  jmp     short loc_1800C89BF
0x1800c8993  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c8999  and     eax, r13d
0x1800c899c  test    al, al
0x1800c899e  jz      short loc_1800C89BF
0x1800c89a0  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x1800c89a4  lea     r9, aFailedToEndAss_0; "Failed to end asset, swallowing: [0x%x]"...
0x1800c89ab  lea     r8, aWindowsCompatA_469; "Windows::Compat::Appraiser::WicaApplica"...
0x1800c89b2  mov     rdx, r14; char *
0x1800c89b5  mov     ecx, 10Bh; unsigned int
0x1800c89ba  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c89bf  mov     rcx, [rsi+2B0h]
0x1800c89c6  test    rcx, rcx
0x1800c89c9  jz      short loc_1800C89E1
0x1800c89cb  mov     rax, [rcx]
0x1800c89ce  mov     edx, r13d
0x1800c89d1  mov     rax, [rax+10h]
0x1800c89d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c89da  mov     [rsi+2B0h], r12
0x1800c89e1  mov     rcx, [rsi+2A8h]
0x1800c89e8  test    rcx, rcx
0x1800c89eb  jz      short loc_1800C8A00
0x1800c89ed  mov     rax, [rcx]
0x1800c89f0  mov     rax, [rax+20h]
0x1800c89f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c89f9  mov     [rsi+2A8h], r12
0x1800c8a00  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800c8a07  mov     [rsp+2F0h+var_290], rax
0x1800c8a0c  cmp     [rsp+2F0h+hModule], r12
0x1800c8a11  jz      short loc_1800C8A21
0x1800c8a13  lea     rcx, [rsp+2F0h+var_290]
  ... truncated ...
```
