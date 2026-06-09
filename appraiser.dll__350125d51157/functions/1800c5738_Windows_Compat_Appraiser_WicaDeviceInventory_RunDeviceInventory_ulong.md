# Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory(ulong)

- ea: `0x1800c5738`
- end: `0x1800c5c68`
- name: `?RunDeviceInventory@WicaDeviceInventory@Appraiser@Compat@Windows@@AEAAJK@Z`
- size: `1328`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::WicaDeviceInventory *this, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c3930`

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
- `0x1800c37c0`
- `0x1800c5738`
- `0x18021f010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800c5834`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c5834`
- `ntdll!RtlEnterCriticalSection` at `0x1800c5817`
- `ntdll!RtlEnterCriticalSection` at `0x1800c5817`
- `KERNEL32!GetSystemTime` at `0x1800c5b07`
- `KERNEL32!GetSystemTime` at `0x1800c5b07`
- `KERNEL32!LoadLibraryW` at `0x1800c585d`
- `KERNEL32!LoadLibraryW` at `0x1800c585d`
- `KERNEL32!GetProcAddress` at `0x1800c592b`
- `KERNEL32!GetProcAddress` at `0x1800c592b`
- `KERNEL32!GetLastError` at `0x1800c58ae`
- `KERNEL32!GetLastError` at `0x1800c5939`
- `KERNEL32!GetLastError` at `0x1800c5c36`
- `KERNEL32!GetLastError` at `0x1800c5c4d`
- `KERNEL32!GetLastError` at `0x1800c58ae`
- `KERNEL32!GetLastError` at `0x1800c5939`
- `KERNEL32!GetLastError` at `0x1800c5c36`
- `KERNEL32!GetLastError` at `0x1800c5c4d`

## string_xrefs

- `0x1800c58df`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c590e`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c5985`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c59ee`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c5a2b`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c5ade`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c5b8d`: `onecore\base\appcompat\appraiser\inventory\deviceinventory.cpp`
- `0x1800c5856`: `devinv.dll`
- `0x1800c5897`: `Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory`
- `0x1800c5955`: `Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory`
- `0x1800c597e`: `Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory`
- `0x1800c59b7`: `Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory`
- `0x1800c5ad3`: `Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory`
- `0x1800c58c3`: `LoadLibrary(devinv) failed: [0x%x].`
- `0x1800c5904`: `LoadLibrary(devinv) failed: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory(
        Windows::Compat::Appraiser::WicaDeviceInventory *this,
        int a2)
{
  char *v3; // r15
  char *v4; // rbx
  HMODULE LibraryW; // rbx
  HMODULE v6; // rcx
  signed int LastError; // eax
  signed int v8; // ebx
  const char *v9; // r9
  char v10; // dl
  FARPROC ProcAddress; // r14
  signed int v12; // eax
  int v13; // eax
  unsigned int v14; // r15d
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
  char *v29; // [rsp+28h] [rbp-E0h]
  char *v30; // [rsp+38h] [rbp-D0h]
  void **v31; // [rsp+68h] [rbp-A0h] BYREF
  HMODULE hModule; // [rsp+70h] [rbp-98h]
  _QWORD DestinationString[3]; // [rsp+78h] [rbp-90h] BYREF
  char *v34; // [rsp+90h] [rbp-78h] BYREF
  const char *v35; // [rsp+98h] [rbp-70h] BYREF
  const char *v36; // [rsp+A0h] [rbp-68h] BYREF
  const size_t *v37; // [rsp+A8h] [rbp-60h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v39; // [rsp+C8h] [rbp-40h]
  __int64 v40; // [rsp+D0h] [rbp-38h] BYREF
  BOOL v41; // [rsp+D8h] [rbp-30h]
  BOOL v42; // [rsp+DCh] [rbp-2Ch]
  int v43; // [rsp+E0h] [rbp-28h]
  BOOL v44; // [rsp+E4h] [rbp-24h]
  unsigned __int64 v45; // [rsp+E8h] [rbp-20h]
  struct _SYSTEMTIME v46; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v47[144]; // [rsp+108h] [rbp+0h] BYREF
  char v48[144]; // [rsp+198h] [rbp+90h] BYREF
  char v49[144]; // [rsp+228h] [rbp+120h] BYREF

  v39 = -2;
  v3 = 0;
  v40 = 32;
  v42 = *((_BYTE *)this + 1160) != 0;
  v41 = *((_BYTE *)this + 1161) != 0;
  v44 = *((_BYTE *)this + 1162) != 0;
  v43 = a2;
  v45 = ((unsigned __int64)this + 608) & -(__int64)(*((_WORD *)this + 304) != 0);
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
  {
    if ( !TraceLoggingCorrelationVector::Increment(Windows::Compat::Appraiser::WicaFactory::CorrelationVector, v48) )
      strcpy(v48, "UNK");
    *(_OWORD *)&DestinationString[1] = 0;
    v4 = (char *)P;
    if ( P && (int)AslAnsiStringCreate((PANSI_STRING)&DestinationString[1]) >= 0 )
    {
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v4 + 88));
      AslAnsiStringFree(v4 + 72);
      *(_OWORD *)(v4 + 72) = *(_OWORD *)&DestinationString[1];
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v4 + 88));
    }
    v3 = v48;
  }
  v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = 0;
  LibraryW = LoadLibraryW(L"devinv.dll");
  v6 = 0;
  if ( LibraryW )
  {
    v6 = LibraryW;
    hModule = LibraryW;
  }
  if ( !v6 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = "LoadLibrary(devinv) failed: [0x%x].";
      v10 = 89;
LABEL_15:
      LODWORD(v30) = v8;
      LODWORD(v29) = v8;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v10,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
        "Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory",
        v29,
        (int)v9,
        v30);
      goto LABEL_31;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x159u,
        "onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
        "Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory",
        "LoadLibrary(devinv) failed: [0x%x].",
        v8);
    v6 = hModule;
  }
  ProcAddress = GetProcAddress(v6, "GetDevInventory");
  if ( !ProcAddress )
  {
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = "GetProcAddress(GetDevInventory) failed: [0x%x].";
      v10 = 96;
      goto LABEL_15;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x160u,
        "onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
        "Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory",
        "GetProcAddress(GetDevInventory) failed: [0x%x].",
        v8);
  }
  v8 = ((__int64 (__fastcall *)(unsigned __int64, __int64 *, char *))ProcAddress)(
         ((unsigned __int64)this + 16) & -(__int64)(this != 0),
         &v40,
         v3);
  if ( v8 < 0 )
  {
    v9 = "Failed to get device inventory from devinv: [0x%x].";
    v10 = 101;
    goto LABEL_15;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x165u,
      "onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
      "Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory",
      "Failed to get device inventory from devinv: [0x%x].",
      v8);
  v8 = 0;
LABEL_31:
  v13 = Windows::Compat::Appraiser::WicaDeviceInventory::EndCurrentAsset(this);
  v14 = v13;
  if ( v13 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x170u,
        "onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
        "Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory",
        "Failed to end asset, swallowing: [0x%x].",
        v8);
  }
  else
  {
    LODWORD(v30) = v8;
    LODWORD(v29) = v13;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      112,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp",
      "Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory",
      v29,
      (int)"Failed to end asset, swallowing: [0x%x].",
      v30);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v47);
    v15 = (volatile signed __int64 *)v47;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v15 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v15,
      _InterlockedExchangeAdd64(v15 + 17, 0),
      v49);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v16);
    v17 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v34 = v49;
      DestinationString[0] = v14 | 0x17000000000LL;
      v35 = "Windows::Compat::Appraiser::WicaDeviceInventory::RunDeviceInventory";
      v36 = "onecore\\base\\appcompat\\appraiser\\inventory\\deviceinventory.cpp";
      v37 = &szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v46 = SystemTime;
      DestinationString[1] = &v46;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v17,
        (unsigned int)&byte_1802A32AF,
        v18,
        v19,
        (__int64)&DestinationString[1],
        (__int64)&v37,
        (__int64)DestinationString + 4,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)DestinationString,
        (__int64)&v34);
    }
  }
  v20 = *((_QWORD *)this + 142);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 16LL))(v20, 1);
    *((_QWORD *)this + 142) = 0;
  }
  v21 = *((_QWORD *)this + 144);
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21);
    *((_QWORD *)this + 144) = 0;
  }
  v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v31) )
  {
    v23 = GetLastError();
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
    v26 = GetLastError();
    if ( v26 > 0 )
      v26 = (unsigned __int16)v26 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
    JUMPOUT(0x1800C5C67LL);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c5738  mov     rax, rsp
0x1800c573b  push    rbp
0x1800c573c  push    rdi
0x1800c573d  push    r13
0x1800c573f  push    r14
0x1800c5741  push    r15
0x1800c5743  lea     rbp, [rax-1E8h]
0x1800c574a  sub     rsp, 2C0h
0x1800c5751  mov     [rbp+1E0h+var_220], 0FFFFFFFFFFFFFFFEh
0x1800c5759  mov     [rax+18h], rbx
0x1800c575d  mov     [rax+20h], rsi
0x1800c5761  mov     rax, cs:__security_cookie
0x1800c5768  xor     rax, rsp
0x1800c576b  mov     [rbp+1E0h+var_30], rax
0x1800c5772  mov     rsi, rcx
0x1800c5775  xor     r15d, r15d
0x1800c5778  mov     [rbp+1E0h+var_218], 20h ; ' '
0x1800c5780  xor     eax, eax
0x1800c5782  cmp     [rcx+488h], al
0x1800c5788  setnz   al
0x1800c578b  mov     [rbp+1E0h+var_20C], eax
0x1800c578e  xor     eax, eax
0x1800c5790  cmp     [rcx+489h], al
0x1800c5796  setnz   al
0x1800c5799  mov     [rbp+1E0h+var_210], eax
0x1800c579c  xor     eax, eax
0x1800c579e  cmp     [rcx+48Ah], al
0x1800c57a4  setnz   al
0x1800c57a7  mov     [rbp+1E0h+var_204], eax
0x1800c57aa  mov     [rbp+1E0h+var_208], edx
0x1800c57ad  lea     rdx, [rcx+260h]
0x1800c57b4  movzx   eax, word ptr [rdx]
0x1800c57b7  neg     ax
0x1800c57ba  sbb     rcx, rcx
0x1800c57bd  and     rcx, rdx
0x1800c57c0  mov     [rbp+1E0h+var_200], rcx
0x1800c57c4  mov     rcx, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; this
0x1800c57cb  test    rcx, rcx
0x1800c57ce  jz      short loc_1800C5841
0x1800c57d0  lea     rdx, [rbp+1E0h+var_150]; char *
0x1800c57d7  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800c57dc  test    al, al
0x1800c57de  jnz     short loc_1800C57EA
0x1800c57e0  mov     dword ptr [rbp+1E0h+var_150], 4B4E55h
0x1800c57ea  xorps   xmm0, xmm0
0x1800c57ed  movups  xmmword ptr [rsp+2E0h+DestinationString+8], xmm0
0x1800c57f2  mov     rbx, cs:P
0x1800c57f9  test    rbx, rbx
0x1800c57fc  jz      short loc_1800C583A
0x1800c57fe  lea     rdx, [rbp+1E0h+var_150]
0x1800c5805  lea     rcx, [rsp+2E0h+DestinationString+8]; DestinationString
0x1800c580a  call    AslAnsiStringCreate
0x1800c580f  test    eax, eax
0x1800c5811  js      short loc_1800C583A
0x1800c5813  lea     rcx, [rbx+58h]; CriticalSection
0x1800c5817  call    cs:__imp_RtlEnterCriticalSection
0x1800c581d  lea     rcx, [rbx+48h]
0x1800c5821  call    AslAnsiStringFree
0x1800c5826  movups  xmm0, xmmword ptr [rsp+2E0h+DestinationString+8]
0x1800c582b  movdqu  xmmword ptr [rbx+48h], xmm0
0x1800c5830  lea     rcx, [rbx+58h]; CriticalSection
0x1800c5834  call    cs:__imp_RtlLeaveCriticalSection
0x1800c583a  lea     r15, [rbp+1E0h+var_150]
0x1800c5841  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800c5848  mov     [rsp+2E0h+var_280], rax
0x1800c584d  mov     [rsp+2E0h+hModule], 0
0x1800c5856  lea     rcx, aDevinvDll; "devinv.dll"
0x1800c585d  call    cs:__imp_LoadLibraryW
0x1800c5863  mov     rbx, rax
0x1800c5866  mov     rcx, [rsp+2E0h+hModule]
0x1800c586b  cmp     rax, rcx
0x1800c586e  jz      short loc_1800C5897
0x1800c5870  test    rcx, rcx
0x1800c5873  jz      short loc_1800C588F
0x1800c5875  mov     rcx, [rsp+2E0h+var_280]
0x1800c587a  mov     rax, [rcx]
0x1800c587d  lea     rcx, [rsp+2E0h+var_280]
0x1800c5882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5887  test    al, al
0x1800c5889  jz      loc_1800C5C4D
0x1800c588f  mov     rcx, rbx
0x1800c5892  mov     [rsp+2E0h+hModule], rbx
0x1800c5897  lea     r14, aWindowsCompatA_598; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c589e  mov     edi, 80070000h
0x1800c58a3  mov     r13d, 1
0x1800c58a9  test    rcx, rcx
0x1800c58ac  jnz     short loc_1800C5924
0x1800c58ae  call    cs:__imp_GetLastError
0x1800c58b4  mov     ebx, eax
0x1800c58b6  test    eax, eax
0x1800c58b8  jle     short loc_1800C58BF
0x1800c58ba  movzx   ebx, ax
0x1800c58bd  or      ebx, edi
0x1800c58bf  test    ebx, ebx
0x1800c58c1  jns     short loc_1800C58F3
0x1800c58c3  lea     r9, aLoadlibraryDev; "LoadLibrary(devinv) failed: [0x%x]."
0x1800c58ca  mov     edx, 159h; bool
0x1800c58cf  mov     dword ptr [rsp+2E0h+var_2B0], ebx; char *
0x1800c58d3  mov     qword ptr [rsp+2E0h+var_2B8], r9; int
0x1800c58d8  mov     dword ptr [rsp+2E0h+var_2C0], ebx; char *
0x1800c58dc  mov     r9, r14; char *
0x1800c58df  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c58e6  mov     ecx, r13d; this
0x1800c58e9  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c58ee  jmp     loc_1800C5A01
0x1800c58f3  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c58f9  and     eax, r13d
0x1800c58fc  test    al, al
0x1800c58fe  jz      short loc_1800C591F
0x1800c5900  mov     dword ptr [rsp+2E0h+var_2C0], ebx
0x1800c5904  lea     r9, aLoadlibraryDev; "LoadLibrary(devinv) failed: [0x%x]."
0x1800c590b  mov     r8, r14; char *
0x1800c590e  lea     rdx, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c5915  mov     ecx, 159h; unsigned int
0x1800c591a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c591f  mov     rcx, [rsp+2E0h+hModule]; hModule
0x1800c5924  lea     rdx, aGetdevinventor; "GetDevInventory"
0x1800c592b  call    cs:__imp_GetProcAddress
0x1800c5931  mov     r14, rax
0x1800c5934  test    rax, rax
0x1800c5937  jnz     short loc_1800C5996
0x1800c5939  call    cs:__imp_GetLastError
0x1800c593f  mov     ebx, eax
0x1800c5941  test    eax, eax
0x1800c5943  jle     short loc_1800C594A
0x1800c5945  movzx   ebx, ax
0x1800c5948  or      ebx, edi
0x1800c594a  test    ebx, ebx
0x1800c594c  jns     short loc_1800C5966
0x1800c594e  lea     r9, aGetprocaddress_3; "GetProcAddress(GetDevInventory) failed:"...
0x1800c5955  lea     r14, aWindowsCompatA_598; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c595c  mov     edx, 160h
0x1800c5961  jmp     loc_1800C58CF
0x1800c5966  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c596c  and     eax, r13d
0x1800c596f  test    al, al
0x1800c5971  jz      short loc_1800C5996
0x1800c5973  mov     dword ptr [rsp+2E0h+var_2C0], ebx
0x1800c5977  lea     r9, aGetprocaddress_3; "GetProcAddress(GetDevInventory) failed:"...
0x1800c597e  lea     r8, aWindowsCompatA_598; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c5985  lea     rdx, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c598c  mov     ecx, 160h; unsigned int
0x1800c5991  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c5996  mov     rax, rsi
0x1800c5999  lea     rdx, [rsi+10h]
0x1800c599d  neg     rax
0x1800c59a0  sbb     rcx, rcx
0x1800c59a3  and     rcx, rdx
0x1800c59a6  mov     r8, r15
0x1800c59a9  lea     rdx, [rbp+1E0h+var_218]
0x1800c59ad  mov     rax, r14
0x1800c59b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c59b5  mov     ebx, eax
0x1800c59b7  lea     r14, aWindowsCompatA_598; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c59be  test    eax, eax
0x1800c59c0  jns     short loc_1800C59D3
0x1800c59c2  lea     r9, aFailedToGetDev; "Failed to get device inventory from dev"...
0x1800c59c9  mov     edx, 165h
0x1800c59ce  jmp     loc_1800C58CF
0x1800c59d3  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c59d9  and     eax, r13d
0x1800c59dc  test    al, al
0x1800c59de  jz      short loc_1800C59FF
0x1800c59e0  mov     dword ptr [rsp+2E0h+var_2C0], ebx
0x1800c59e4  lea     r9, aFailedToGetDev; "Failed to get device inventory from dev"...
0x1800c59eb  mov     r8, r14; char *
0x1800c59ee  lea     rdx, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c59f5  mov     ecx, 165h; unsigned int
0x1800c59fa  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c59ff  xor     ebx, ebx
0x1800c5a01  mov     rcx, rsi; this
0x1800c5a04  call    ?EndCurrentAsset@WicaDeviceInventory@Appraiser@Compat@Windows@@AEAAJXZ; Windows::Compat::Appraiser::WicaDeviceInventory::EndCurrentAsset(void)
0x1800c5a09  mov     r15d, eax
0x1800c5a0c  test    eax, eax
0x1800c5a0e  jns     loc_1800C5B72
0x1800c5a14  mov     dword ptr [rsp+2E0h+var_2B0], ebx; char *
0x1800c5a18  lea     r9, aFailedToEndAss_0; "Failed to end asset, swallowing: [0x%x]"...
0x1800c5a1f  mov     qword ptr [rsp+2E0h+var_2B8], r9; int
0x1800c5a24  mov     dword ptr [rsp+2E0h+var_2C0], eax; char *
0x1800c5a28  mov     r9, r14; char *
0x1800c5a2b  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c5a32  mov     edx, 170h; bool
0x1800c5a37  mov     ecx, r13d; this
0x1800c5a3a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c5a3f  lea     rcx, [rbp+1E0h+var_1E0]; this
0x1800c5a43  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800c5a48  lea     rcx, [rbp+1E0h+var_1E0]
0x1800c5a4c  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800c5a53  test    rax, rax
0x1800c5a56  cmovnz  rcx, rax; this
0x1800c5a5a  xor     edx, edx
0x1800c5a5c  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800c5a65  lea     r8, [rbp+1E0h+var_C0]; char *
0x1800c5a6c  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800c5a71  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800c5a78  jz      short loc_1800C5A86
0x1800c5a7a  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800c5a81  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800c5a86  mov     r14, cs:qword_1802C9628
0x1800c5a8d  mov     eax, [r14]
0x1800c5a90  cmp     eax, 5
0x1800c5a93  jbe     loc_1800C5B9E
0x1800c5a99  mov     rcx, [r14+18h]
0x1800c5a9d  mov     rax, [r14+10h]
0x1800c5aa1  mov     rdx, 200000000000h
0x1800c5aab  test    rdx, rax
0x1800c5aae  jz      loc_1800C5B9E
0x1800c5ab4  mov     rax, rcx
0x1800c5ab7  and     rax, rdx
0x1800c5aba  cmp     rax, rcx
0x1800c5abd  jnz     loc_1800C5B9E
0x1800c5ac3  lea     rax, [rbp+1E0h+var_C0]
0x1800c5aca  mov     [rbp+1E0h+var_258], rax
0x1800c5ace  mov     dword ptr [rsp+2E0h+DestinationString], r15d
0x1800c5ad3  lea     rax, aWindowsCompatA_598; "Windows::Compat::Appraiser::WicaDeviceI"...
0x1800c5ada  mov     [rbp+1E0h+var_250], rax
0x1800c5ade  lea     rax, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c5ae5  mov     [rbp+1E0h+var_248], rax
0x1800c5ae9  mov     dword ptr [rsp+2E0h+DestinationString+4], 170h
0x1800c5af1  lea     rax, szValueBuf
0x1800c5af8  mov     [rbp+1E0h+var_240], rax
0x1800c5afc  xorps   xmm0, xmm0
0x1800c5aff  movups  xmmword ptr [rbp+1E0h+SystemTime.wYear], xmm0
0x1800c5b03  lea     rcx, [rbp+1E0h+SystemTime]; lpSystemTime
0x1800c5b07  call    cs:__imp_GetSystemTime
0x1800c5b0d  movaps  xmm0, xmmword ptr [rbp+1E0h+SystemTime.wYear]
0x1800c5b11  movdqa  [rbp+1E0h+var_1F0], xmm0
0x1800c5b16  lea     rax, [rbp+1E0h+var_1F0]
0x1800c5b1a  mov     qword ptr [rsp+2E0h+DestinationString+8], rax
0x1800c5b1f  lea     rax, [rbp+1E0h+var_258]
0x1800c5b23  mov     [rsp+2E0h+var_290], rax
0x1800c5b28  lea     rax, [rsp+2E0h+DestinationString]
0x1800c5b2d  mov     [rsp+2E0h+var_298], rax
0x1800c5b32  lea     rax, [rbp+1E0h+var_250]
0x1800c5b36  mov     [rsp+2E0h+var_2A0], rax
0x1800c5b3b  lea     rax, [rbp+1E0h+var_248]
0x1800c5b3f  mov     [rsp+2E0h+var_2A8], rax
0x1800c5b44  lea     rax, [rsp+2E0h+DestinationString+4]
0x1800c5b49  mov     [rsp+2E0h+var_2B0], rax
0x1800c5b4e  lea     rax, [rbp+1E0h+var_240]
0x1800c5b52  mov     qword ptr [rsp+2E0h+var_2B8], rax
0x1800c5b57  lea     rax, [rsp+2E0h+DestinationString+8]
0x1800c5b5c  mov     [rsp+2E0h+var_2C0], rax
0x1800c5b61  lea     rdx, byte_1802A32AF
0x1800c5b68  mov     rcx, r14
0x1800c5b6b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c5b70  jmp     short loc_1800C5B9E
0x1800c5b72  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c5b78  and     eax, r13d
0x1800c5b7b  test    al, al
0x1800c5b7d  jz      short loc_1800C5B9E
0x1800c5b7f  mov     dword ptr [rsp+2E0h+var_2C0], ebx
0x1800c5b83  lea     r9, aFailedToEndAss_0; "Failed to end asset, swallowing: [0x%x]"...
0x1800c5b8a  mov     r8, r14; char *
0x1800c5b8d  lea     rdx, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c5b94  mov     ecx, 170h; unsigned int
0x1800c5b99  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c5b9e  mov     rcx, [rsi+470h]
0x1800c5ba5  test    rcx, rcx
0x1800c5ba8  jz      short loc_1800C5BC4
0x1800c5baa  mov     rax, [rcx]
0x1800c5bad  mov     edx, r13d
0x1800c5bb0  mov     rax, [rax+10h]
0x1800c5bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5bb9  mov     qword ptr [rsi+470h], 0
0x1800c5bc4  mov     rcx, [rsi+480h]
0x1800c5bcb  test    rcx, rcx
0x1800c5bce  jz      short loc_1800C5BE7
0x1800c5bd0  mov     rax, [rcx]
0x1800c5bd3  mov     rax, [rax+20h]
0x1800c5bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5bdc  mov     qword ptr [rsi+480h], 0
0x1800c5be7  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800c5bee  mov     [rsp+2E0h+var_280], rax
0x1800c5bf3  cmp     [rsp+2E0h+hModule], 0
0x1800c5bf9  jz      short loc_1800C5C09
0x1800c5bfb  lea     rcx, [rsp+2E0h+var_280]
0x1800c5c00  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800c5c05  test    al, al
0x1800c5c07  jz      short loc_1800C5C36
0x1800c5c09  mov     eax, ebx
0x1800c5c0b  mov     rcx, [rbp+1E0h+var_30]
0x1800c5c12  xor     rcx, rsp; StackCookie
0x1800c5c15  call    __security_check_cookie
0x1800c5c1a  lea     r11, [rsp+2E0h+var_20]
0x1800c5c22  mov     rbx, [r11+40h]
0x1800c5c26  mov     rsi, [r11+48h]
0x1800c5c2a  mov     rsp, r11
0x1800c5c2d  pop     r15
0x1800c5c2f  pop     r14
0x1800c5c31  pop     r13
0x1800c5c33  pop     rdi
0x1800c5c34  pop     rbp
0x1800c5c35  retn
0x1800c5c36  call    cs:__imp_GetLastError
0x1800c5c3c  test    eax, eax
0x1800c5c3e  jle     short loc_1800C5C45
0x1800c5c40  movzx   eax, ax
0x1800c5c43  or      eax, edi
0x1800c5c45  mov     ecx, eax; this
  ... truncated ...
```
