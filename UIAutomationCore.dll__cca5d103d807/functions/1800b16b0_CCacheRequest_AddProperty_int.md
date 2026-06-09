# CCacheRequest::AddProperty(int)

- ea: `0x1800b16b0`
- end: `0x1800b1cb2`
- name: `?AddProperty@CCacheRequest@@UEAAJH@Z`
- size: `1538`
- prototype: `__int64 __fastcall(CCacheRequest *__hidden this, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002f580`
- `0x180061630`
- `0x180098180`
- `0x180098590`
- `0x18009ab54`
- `0x1800ad424`
- `0x1800ad62c`
- `0x1800b0198`
- `0x1800b09d0`
- `0x1800b1120`
- `0x1800b16b0`
- `0x1800b3338`
- `0x1800b4988`
- `0x180133550`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1801e9240`
- `0x180234818`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800b1b04`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800b1b04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b1864`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b1885`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b19a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b1864`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b1885`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b19a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1837`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1837`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b18a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b18a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b19df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1bf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b19df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1bf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b1a29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b1a29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b184a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b1871`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b1994`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b184a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b1871`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b1994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1783`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1783`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b1791`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b1791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1c06`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b1b19`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b1b19`

## string_xrefs

- `0x1800b1a43`: `onecore\windows\accessibletech\uiautomationcore\SafeApis.h`
- `0x1800b1a5e`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800b1a8d`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800b1aaa`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800b1c86`: `onecore\windows\accessibletech\common\ArrayBuilder.h`
- `0x1800b1700`: `CCacheRequest::AddProperty`
- `0x1800b1acf`: `CCacheRequest::AddProperty`
- `0x1800b1bbb`: `onecore\windows\accessibletech\uiautomationcore\ccacherequest.cpp`
- `0x1800b1bdb`: `onecore\windows\accessibletech\uiautomationcore\ccacherequest.cpp`
- `0x1800b1b8a`: `IUIAutomationCacheRequest::AddProperty`
- `0x1800b1c66`: `IUIAutomationCacheRequest::AddProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCacheRequest::AddProperty(RTL_SRWLOCK *this, int a2)
{
  _OWORD *v4; // rbx
  char v5; // di
  HANDLE ProcessHeap; // rax
  unsigned int i; // edi
  __int64 v8; // rbx
  _DWORD *Ptr; // r13
  RTL_SRWLOCK *v10; // rbx
  _BYTE *v11; // r13
  __int64 Ptr_low; // rcx
  unsigned int v13; // edi
  unsigned __int64 v14; // rax
  char *v15; // rbx
  unsigned __int64 v16; // r13
  PVOID v17; // rcx
  unsigned int v18; // edi
  PVOID v19; // rbx
  void *v21; // rcx
  __int64 v22; // rdx
  int v23; // edx
  const unsigned __int16 *v24; // rbx
  signed int LastError; // eax
  const unsigned __int16 *v26; // r15
  const unsigned __int16 *v27; // r14
  const OLECHAR *v28; // rsi
  int v29; // ecx
  const OLECHAR *v30; // rax
  unsigned int v31; // eax
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  _BYTE *v35; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v37; // [rsp+60h] [rbp-A0h]
  _QWORD v38[3]; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+88h] [rbp-78h]
  __int128 *v40; // [rsp+90h] [rbp-70h]
  char v41; // [rsp+98h] [rbp-68h]
  _OWORD v42[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-30h]
  int v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E0h] [rbp-20h]
  char v46; // [rsp+E8h] [rbp-18h]
  _BYTE v47[80]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v48[272]; // [rsp+140h] [rbp+40h] BYREF
  _DWORD *v49; // [rsp+250h] [rbp+150h]
  WCHAR Buffer[512]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6D8h] [rbp+5D8h]

  LODWORD(v35) = 0;
  ClientApiCallTrace::ClientApiCallTrace(
    (ClientApiCallTrace *)v48,
    "CCacheRequest::AddProperty",
    this,
    a2,
    (HINSTANCE)retaddr);
  if ( retaddr < (wil::details::in1diag3 *)g_hInstance
    || retaddr > (wil::details::in1diag3 *)((char *)g_hInstance + g_ModuleSize) )
  {
    v4 = (_OWORD *)UiaImportantTraceLoggingProvider::WatchCurrentThread(
                     (__int64)v47,
                     (__int64)"CCacheRequest::AddProperty",
                     "object=%p, parameter=%d",
                     this,
                     a2);
    v5 = 1;
  }
  else
  {
    memset(v42, 0, sizeof(v42));
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v4 = v42;
    v5 = 2;
  }
  v36 = 0;
  v37 = 0;
  LODWORD(v36) = *(_DWORD *)v4;
  *((_QWORD *)&v36 + 1) = *((_QWORD *)v4 + 1);
  if ( (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, 0);
    BYTE8(v37) = 0;
  }
  *(_QWORD *)&v37 = 0;
  *(_QWORD *)&v37 = *((_QWORD *)v4 + 2);
  *((_QWORD *)v4 + 2) = 0;
  BYTE8(v37) = *((_BYTE *)v4 + 24);
  *((_BYTE *)v4 + 24) = 0;
  v38[0] = 0;
  v38[1] = *((_QWORD *)v4 + 5);
  v38[2] = 0;
  v39 = 0;
  v40 = (__int128 *)*((_QWORD *)v4 + 8);
  v41 = 0;
  if ( *((_DWORD *)v4 + 14) )
  {
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v4 + 2));
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v38);
  }
  v40 = &v36;
  if ( (v5 & 2) != 0 )
  {
    v5 &= ~2u;
    ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)v42);
  }
  if ( (v5 & 1) != 0 )
    ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)v47);
  if ( !Schema::GetPropertyInfo(a2) )
  {
    if ( LoadStringW(g_hInstance, 0x1F6u, Buffer, 512) )
    {
      v24 = SysAllocString(Buffer);
      v35 = v24;
      LastError = v24 == 0 ? 0x8007000E : 0;
      v26 = v24;
      v27 = v24;
    }
    else
    {
      v24 = 0;
      v35 = 0;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v26 = 0;
      v27 = 0;
    }
    if ( LastError >= 0 )
      Error::SetError(v24, 0);
    v28 = &word_180313900;
    v18 = -2147024809;
    v29 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v30 = &word_180313900;
      if ( v24 )
        v30 = v26;
      WPP_SF_SdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, (__int64)L"propertyId", (__int64)v30);
    }
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 1) != 0 )
    {
      if ( v24 )
        v28 = v27;
      McTemplateU0zzz_EventWriteTransfer(
        v29,
        v23,
        (unsigned int)L"IUIAutomationCacheRequest::AddProperty",
        (unsigned int)L"propertyId",
        (__int64)v28);
    }
    AutoCleanupInfo<unsigned short *>::SafeRelease(&v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\ccacherequest.cpp",
      (const char *)0x80070057LL,
      v32);
    goto LABEL_40;
  }
  EnterCriticalSection(&CCacheRequest::_classLock);
  for ( i = 0; ; ++i )
  {
    AcquireSRWLockShared(this + 16);
    v8 = ((char *)this[15].Ptr - (char *)this[13].Ptr) >> 2;
    if ( this != (RTL_SRWLOCK *)-128LL )
      ReleaseSRWLockShared(this + 16);
    if ( i >= (unsigned int)v8 )
      break;
    AcquireSRWLockShared(this + 16);
    Ptr = this[13].Ptr;
    if ( this != (RTL_SRWLOCK *)-128LL )
      ReleaseSRWLockShared(this + 16);
    if ( Ptr[i] == a2 )
      goto LABEL_37;
  }
  v10 = this + 16;
  AcquireSRWLockExclusive(this + 16);
  v35 = this[13].Ptr;
  v11 = this[15].Ptr;
  Ptr_low = LODWORD(this[14].Ptr);
  if ( (unsigned int)((__int64)&v35[4 * Ptr_low - (_QWORD)v11] >> 2) )
    goto LABEL_30;
  if ( (_DWORD)Ptr_low )
  {
    v31 = 2 * Ptr_low;
    if ( (unsigned __int64)(2 * Ptr_low) <= 0xFFFFFFFF )
    {
      v13 = v31 + 1;
      if ( v31 + 1 >= v31 )
        goto LABEL_24;
      v22 = 107;
    }
    else
    {
      v22 = 105;
    }
    v18 = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
      (const char *)0x80070216LL,
      v32);
    goto LABEL_45;
  }
  v13 = 33;
LABEL_24:
  v14 = 4LL * v13;
  if ( !is_mul_ok(v13, 4u) )
    v14 = -1;
  v15 = (char *)operator new[](v14, (const struct std::nothrow_t *)std::nothrow);
  if ( v15 )
  {
    v16 = 4LL * (unsigned int)((v11 - v35) >> 2);
    if ( v16 <= 0xFFFFFFFF )
    {
      memcpy_0(v15, this[13].Ptr, (unsigned int)v16);
      v17 = this[13].Ptr;
      if ( v17 && v17 != this[11].Ptr )
        operator delete(v17);
      this[13].Ptr = v15;
      LODWORD(this[14].Ptr) = v13;
      this[15].Ptr = &v15[v16];
      operator delete(0);
      v10 = this + 16;
LABEL_30:
      *(_DWORD *)this[15].Ptr = a2;
      this[15].Ptr = (char *)this[15].Ptr + 4;
      v18 = 0;
      goto LABEL_31;
    }
    v18 = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SafeApis.h",
      (const char *)0x80070216LL,
      v32);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
      (const char *)0x80070216LL,
      v33);
    v21 = v15;
  }
  else
  {
    v18 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
      (const char *)0x8007000ELL,
      v32);
    v21 = 0;
  }
  operator delete(v21);
  v10 = this + 16;
LABEL_45:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x51,
    (unsigned int)"onecore\\windows\\accessibletech\\common\\ArrayBuilder.h",
    (const char *)v18,
    v34);
LABEL_31:
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  if ( (v18 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\ccacherequest.cpp",
      (const char *)v18,
      v32);
    LeaveCriticalSection(&CCacheRequest::_classLock);
    goto LABEL_40;
  }
  AcquireSRWLockShared(this + 16);
  v19 = this[13].Ptr;
  if ( this != (RTL_SRWLOCK *)-128LL )
    ReleaseSRWLockShared(this + 16);
  this[27].Ptr = v19;
  LODWORD(this[28].Ptr) = BasicArrayBuilder<int>::Count(&this[11]);
LABEL_37:
  if ( *v49 == 1 )
    wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v48);
  LeaveCriticalSection(&CCacheRequest::_classLock);
  v18 = 0;
LABEL_40:
  ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)&v36);
  UiaProvider::ClientApiCallActivity::~ClientApiCallActivity((UiaProvider::ClientApiCallActivity *)v48);
  return v18;
}

```

## disassembly

```asm
0x1800b16b0  mov     [rsp-8+arg_10], rbx
0x1800b16b5  push    rbp
0x1800b16b6  push    rsi
0x1800b16b7  push    rdi
0x1800b16b8  push    r12
0x1800b16ba  push    r13
0x1800b16bc  push    r14
0x1800b16be  push    r15
0x1800b16c0  lea     rbp, [rsp-5A0h]
0x1800b16c8  sub     rsp, 6A0h
0x1800b16cf  mov     rax, cs:__security_cookie
0x1800b16d6  xor     rax, rsp
0x1800b16d9  mov     [rbp+5D0h+var_40], rax
0x1800b16e0  mov     r12d, edx
0x1800b16e3  mov     r15, rcx
0x1800b16e6  xor     r13d, r13d
0x1800b16e9  mov     dword ptr [rsp+6D0h+var_690], r13d
0x1800b16ee  mov     rbx, [rbp+5D8h]
0x1800b16f5  mov     [rsp+6D0h+var_6B0], rbx; int
0x1800b16fa  mov     r9d, edx; int
0x1800b16fd  mov     r8, rcx; void *
0x1800b1700  lea     rdx, aCcacherequestA; "CCacheRequest::AddProperty"
0x1800b1707  lea     rcx, [rbp+5D0h+var_590]; this
0x1800b170b  call    ??0ClientApiCallTrace@@QEAA@PEBDPEBXH1@Z; ClientApiCallTrace::ClientApiCallTrace(char const *,void const *,int,void const *)
0x1800b1710  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800b1717  cmp     rbx, rcx
0x1800b171a  jb      loc_1800B1AC0
0x1800b1720  mov     eax, cs:?g_ModuleSize@@3KA; ulong g_ModuleSize
0x1800b1726  add     rax, rcx
0x1800b1729  cmp     rbx, rax
0x1800b172c  ja      loc_1800B1AC0
0x1800b1732  xorps   xmm0, xmm0
0x1800b1735  movups  [rbp+5D0h+var_630], xmm0
0x1800b1739  movups  [rbp+5D0h+var_620], xmm0
0x1800b173d  movdqu  [rbp+5D0h+var_610], xmm0
0x1800b1742  mov     [rbp+5D0h+var_600], r13
0x1800b1746  mov     [rbp+5D0h+var_5F8], r13d
0x1800b174a  mov     [rbp+5D0h+var_5F0], r13
0x1800b174e  mov     [rbp+5D0h+var_5E8], r13b
0x1800b1752  lea     rbx, [rbp+5D0h+var_630]
0x1800b1756  lea     edi, [r13+2]
0x1800b175a  xorps   xmm0, xmm0
0x1800b175d  movups  [rsp+6D0h+var_680], xmm0
0x1800b1762  movaps  [rsp+6D0h+var_670], xmm0
0x1800b1767  mov     ecx, [rbx]
0x1800b1769  mov     dword ptr [rsp+6D0h+var_680], ecx
0x1800b176d  mov     rcx, [rbx+8]
0x1800b1771  mov     qword ptr [rsp+6D0h+var_680+8], rcx
0x1800b1776  psrldq  xmm0, 8
0x1800b177b  movd    ecx, xmm0
0x1800b177f  test    cl, cl
0x1800b1781  jz      short loc_1800B179C
0x1800b1783  call    cs:__imp_GetProcessHeap
0x1800b1789  xor     r8d, r8d; lpMem
0x1800b178c  xor     edx, edx; dwFlags
0x1800b178e  mov     rcx, rax; hHeap
0x1800b1791  call    cs:__imp_HeapFree
0x1800b1797  mov     byte ptr [rsp+6D0h+var_670+8], r13b
0x1800b179c  mov     qword ptr [rsp+6D0h+var_670], r13
0x1800b17a1  mov     rax, [rbx+10h]
0x1800b17a5  mov     qword ptr [rsp+6D0h+var_670], rax
0x1800b17aa  mov     [rbx+10h], r13
0x1800b17ae  mov     al, [rbx+18h]
0x1800b17b1  mov     byte ptr [rsp+6D0h+var_670+8], al
0x1800b17b5  mov     [rbx+18h], r13b
0x1800b17b9  lea     rcx, [rbx+20h]; this
0x1800b17bd  mov     [rsp+6D0h+var_660], r13
0x1800b17c2  mov     rax, [rcx+8]
0x1800b17c6  mov     [rsp+6D0h+var_658], rax
0x1800b17cb  mov     [rbp+5D0h+var_650], r13
0x1800b17cf  mov     [rbp+5D0h+var_648], r13d
0x1800b17d3  mov     rax, [rcx+20h]
0x1800b17d7  mov     [rbp+5D0h+var_640], rax
0x1800b17db  mov     [rbp+5D0h+var_638], r13b
0x1800b17df  cmp     [rcx+18h], r13d
0x1800b17e3  jz      short loc_1800B17F5
0x1800b17e5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800b17ea  lea     rcx, [rsp+6D0h+var_660]; this
0x1800b17ef  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800b17f4  nop
0x1800b17f5  lea     rax, [rsp+6D0h+var_680]
0x1800b17fa  mov     [rbp+5D0h+var_640], rax
0x1800b17fe  test    dil, 2
0x1800b1802  jz      short loc_1800B1810
0x1800b1804  and     edi, 0FFFFFFFDh
0x1800b1807  lea     rcx, [rbp+5D0h+var_630]; this
0x1800b180b  call    ??1ClientApiErrorTrace@@QEAA@XZ; ClientApiErrorTrace::~ClientApiErrorTrace(void)
0x1800b1810  test    dil, 1
0x1800b1814  jz      short loc_1800B181F
0x1800b1816  lea     rcx, [rbp+5D0h+var_5E0]; this
0x1800b181a  call    ??1ClientApiErrorTrace@@QEAA@XZ; ClientApiErrorTrace::~ClientApiErrorTrace(void)
0x1800b181f  mov     ecx, r12d; int
0x1800b1822  call    ?GetPropertyInfo@Schema@@SAPEBUPropertyInfo@@H@Z; Schema::GetPropertyInfo(int)
0x1800b1827  test    rax, rax
0x1800b182a  jz      loc_1800B1AEC
0x1800b1830  lea     rcx, ?_classLock@CCacheRequest@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b1837  call    cs:__imp_EnterCriticalSection
0x1800b183d  mov     edi, r13d
0x1800b1840  lea     r14, [r15+80h]
0x1800b1847  mov     rcx, r14; SRWLock
0x1800b184a  call    cs:__imp_AcquireSRWLockShared
0x1800b1850  mov     rbx, [r15+78h]
0x1800b1854  sub     rbx, [r15+68h]
0x1800b1858  sar     rbx, 2
0x1800b185c  test    r14, r14
0x1800b185f  jz      short loc_1800B186A
0x1800b1861  mov     rcx, r14; SRWLock
0x1800b1864  call    cs:__imp_ReleaseSRWLockShared
0x1800b186a  cmp     edi, ebx
0x1800b186c  jnb     short loc_1800B189A
0x1800b186e  mov     rcx, r14; SRWLock
0x1800b1871  call    cs:__imp_AcquireSRWLockShared
0x1800b1877  mov     ebx, edi
0x1800b1879  mov     r13, [r15+68h]
0x1800b187d  test    r14, r14
0x1800b1880  jz      short loc_1800B188B
0x1800b1882  mov     rcx, r14; SRWLock
0x1800b1885  call    cs:__imp_ReleaseSRWLockShared
0x1800b188b  cmp     [r13+rbx*4+0], r12d
0x1800b1890  jz      loc_1800B19C3
0x1800b1896  inc     edi
0x1800b1898  jmp     short loc_1800B1847
0x1800b189a  lea     rbx, [r15+80h]
0x1800b18a1  mov     rcx, rbx; SRWLock
0x1800b18a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800b18aa  mov     rdx, [r15+68h]
0x1800b18ae  mov     [rsp+6D0h+var_690], rdx
0x1800b18b3  mov     r13, [r15+78h]
0x1800b18b7  mov     ecx, [r15+70h]
0x1800b18bb  lea     rax, ds:0[rcx*4]
0x1800b18c3  sub     rax, r13
0x1800b18c6  add     rax, rdx
0x1800b18c9  sar     rax, 2
0x1800b18cd  cmp     eax, 1
0x1800b18d0  jnb     loc_1800B1972
0x1800b18d6  mov     edx, 0FFFFFFFFh
0x1800b18db  test    ecx, ecx
0x1800b18dd  jnz     loc_1800B1C25
0x1800b18e3  lea     edi, [rcx+21h]
0x1800b18e6  mov     ecx, edi
0x1800b18e8  mov     eax, 4
0x1800b18ed  mul     rcx
0x1800b18f0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b18f7  cmovb   rax, rcx
0x1800b18fb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b1902  mov     rcx, rax; unsigned __int64
0x1800b1905  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b190a  mov     rbx, rax
0x1800b190d  test    rax, rax
0x1800b1910  jz      loc_1800B1C77
0x1800b1916  sub     r13, [rsp+6D0h+var_690]
0x1800b191b  sar     r13, 2
0x1800b191f  mov     eax, r13d
0x1800b1922  lea     r13, ds:0[rax*4]
0x1800b192a  mov     eax, 0FFFFFFFFh
0x1800b192f  cmp     r13, rax
0x1800b1932  ja      loc_1800B1A34
0x1800b1938  mov     r8d, r13d; Size
0x1800b193b  mov     rdx, [r15+68h]; Src
0x1800b193f  mov     rcx, rbx; void *
0x1800b1942  call    memcpy_0
0x1800b1947  mov     rcx, [r15+68h]; Block
0x1800b194b  test    rcx, rcx
0x1800b194e  jnz     loc_1800B1C9E
0x1800b1954  mov     [r15+68h], rbx
0x1800b1958  mov     [r15+70h], edi
0x1800b195c  lea     rax, [rbx+r13]
0x1800b1960  mov     [r15+78h], rax
0x1800b1964  xor     ecx, ecx; Block
0x1800b1966  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b196b  lea     rbx, [r15+80h]
0x1800b1972  mov     rax, [r15+78h]
0x1800b1976  mov     [rax], r12d
0x1800b1979  add     qword ptr [r15+78h], 4
0x1800b197e  xor     edi, edi
0x1800b1980  test    rbx, rbx
0x1800b1983  jnz     loc_1800B1A26
0x1800b1989  test    edi, edi
0x1800b198b  js      loc_1800B1BD1
0x1800b1991  mov     rcx, r14; SRWLock
0x1800b1994  call    cs:__imp_AcquireSRWLockShared
0x1800b199a  mov     rbx, [r15+68h]
0x1800b199e  test    r14, r14
0x1800b19a1  jz      short loc_1800B19AC
0x1800b19a3  mov     rcx, r14; SRWLock
0x1800b19a6  call    cs:__imp_ReleaseSRWLockShared
0x1800b19ac  mov     [r15+0D8h], rbx
0x1800b19b3  lea     rcx, [r15+58h]
0x1800b19b7  call    ?Count@?$BasicArrayBuilder@H@@QEAAHXZ; BasicArrayBuilder<int>::Count(void)
0x1800b19bc  mov     [r15+0E0h], eax
0x1800b19c3  mov     rax, [rbp+5D0h+var_480]
0x1800b19ca  cmp     dword ptr [rax], 1
0x1800b19cd  jnz     short loc_1800B19D8
0x1800b19cf  lea     rcx, [rbp+5D0h+var_590]
0x1800b19d3  call    ?Stop@?$ActivityBase@VUiaProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800b19d8  lea     rcx, ?_classLock@CCacheRequest@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800b19df  call    cs:__imp_LeaveCriticalSection
0x1800b19e5  xor     edi, edi
0x1800b19e7  lea     rcx, [rsp+6D0h+var_680]; this
0x1800b19ec  call    ??1ClientApiErrorTrace@@QEAA@XZ; ClientApiErrorTrace::~ClientApiErrorTrace(void)
0x1800b19f1  lea     rcx, [rbp+5D0h+var_590]; this
0x1800b19f5  call    ??1ClientApiCallActivity@UiaProvider@@QEAA@XZ; UiaProvider::ClientApiCallActivity::~ClientApiCallActivity(void)
0x1800b19fa  mov     eax, edi
0x1800b19fc  mov     rcx, [rbp+5D0h+var_40]
0x1800b1a03  xor     rcx, rsp; StackCookie
0x1800b1a06  call    __security_check_cookie
0x1800b1a0b  mov     rbx, [rsp+6D0h+arg_10]
0x1800b1a13  add     rsp, 6A0h
0x1800b1a1a  pop     r15
0x1800b1a1c  pop     r14
0x1800b1a1e  pop     r13
0x1800b1a20  pop     r12
0x1800b1a22  pop     rdi
0x1800b1a23  pop     rsi
0x1800b1a24  pop     rbp
0x1800b1a25  retn
0x1800b1a26  mov     rcx, rbx; SRWLock
0x1800b1a29  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b1a2f  jmp     loc_1800B1989
0x1800b1a34  mov     rcx, [rbp+5D8h]; this
0x1800b1a3b  mov     edi, 80070216h
0x1800b1a40  mov     r9d, edi; char *
0x1800b1a43  lea     r8, aOnecoreWindows_51; "onecore\\windows\\accessibletech\\uiaut"...
0x1800b1a4a  mov     edx, 46h ; 'F'; void *
0x1800b1a4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1a54  mov     rcx, [rbp+5D8h]; this
0x1800b1a5b  mov     r9d, edi; char *
0x1800b1a5e  lea     r8, aOnecoreWindows_138; "onecore\\windows\\accessibletech\\commo"...
0x1800b1a65  mov     edx, 70h ; 'p'; void *
0x1800b1a6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1a6f  mov     rcx, rbx; Block
0x1800b1a72  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b1a77  lea     rbx, [r15+80h]
0x1800b1a7e  jmp     short loc_1800B1AA0
0x1800b1a80  mov     edx, 6Bh ; 'k'; void *
0x1800b1a85  mov     edi, 80070216h
0x1800b1a8a  mov     r9d, edi; char *
0x1800b1a8d  lea     r8, aOnecoreWindows_138; "onecore\\windows\\accessibletech\\commo"...
0x1800b1a94  mov     rcx, [rbp+5D8h]; this
0x1800b1a9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1aa0  mov     rcx, [rbp+5D8h]; this
0x1800b1aa7  mov     r9d, edi; char *
0x1800b1aaa  lea     r8, aOnecoreWindows_138; "onecore\\windows\\accessibletech\\commo"...
0x1800b1ab1  mov     edx, 51h ; 'Q'; void *
0x1800b1ab6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1abb  jmp     loc_1800B1980
0x1800b1ac0  mov     dword ptr [rsp+6D0h+var_6B0], r12d
0x1800b1ac5  mov     r9, r15
0x1800b1ac8  lea     r8, aObjectPParamet; "object=%p, parameter=%d"
0x1800b1acf  lea     rdx, aCcacherequestA; "CCacheRequest::AddProperty"
0x1800b1ad6  lea     rcx, [rbp+5D0h+var_5E0]
0x1800b1ada  call    ?WatchCurrentThread@UiaImportantTraceLoggingProvider@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; UiaImportantTraceLoggingProvider::WatchCurrentThread(char const *,char const *,...)
0x1800b1adf  mov     rbx, rax
0x1800b1ae2  mov     edi, 1
0x1800b1ae7  jmp     loc_1800B175A
0x1800b1aec  mov     r9d, 200h; cchBufferMax
0x1800b1af2  lea     r8, [rbp+5D0h+Buffer]; lpBuffer
0x1800b1af9  lea     edx, [r9-0Ah]; uID
0x1800b1afd  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800b1b04  call    cs:__imp_LoadStringW
0x1800b1b0a  test    eax, eax
0x1800b1b0c  jz      loc_1800B1BFE
0x1800b1b12  lea     rcx, [rbp+5D0h+Buffer]; psz
0x1800b1b19  call    cs:__imp_SysAllocString
0x1800b1b1f  mov     rbx, rax
0x1800b1b22  mov     [rsp+6D0h+var_690], rax
0x1800b1b27  neg     rax
0x1800b1b2a  sbb     eax, eax
0x1800b1b2c  not     eax
0x1800b1b2e  and     eax, 8007000Eh
0x1800b1b33  mov     r15, rbx
0x1800b1b36  mov     r14, rbx
0x1800b1b39  test    eax, eax
0x1800b1b3b  jns     loc_1800B1C48
0x1800b1b41  lea     rax, WPP_GLOBAL_Control
0x1800b1b48  lea     rsi, word_180313900
0x1800b1b4f  lea     r12, aPropertyid; "propertyId"
0x1800b1b56  mov     edi, 80070057h
0x1800b1b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1b62  cmp     rcx, rax
0x1800b1b65  jz      short loc_1800B1B9A
0x1800b1b67  test    byte ptr [rcx+1Ch], 2
0x1800b1b6b  jz      short loc_1800B1B9A
0x1800b1b6d  mov     rax, rsi
0x1800b1b70  test    rbx, rbx
0x1800b1b73  cmovnz  rax, r15
0x1800b1b77  mov     edx, 12h
0x1800b1b7c  mov     [rsp+6D0h+var_6A0], rax; __int64
0x1800b1b81  mov     [rsp+6D0h+var_6A8], r12; __int64
0x1800b1b86  mov     dword ptr [rsp+6D0h+var_6B0], edi; int
0x1800b1b8a  lea     r9, aIuiautomationc_4; "IUIAutomationCacheRequest::AddProperty"
0x1800b1b91  mov     rcx, [rcx+10h]; LoggerHandle
0x1800b1b95  call    WPP_SF_SdSS
0x1800b1b9a  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 1
0x1800b1ba1  jnz     loc_1800B1C57
0x1800b1ba7  lea     rcx, [rsp+6D0h+var_690]
0x1800b1bac  call    ?SafeRelease@?$AutoCleanupInfo@PEAG@@SAXAEAPEAG@Z; AutoCleanupInfo<ushort *>::SafeRelease(ushort * &)
0x1800b1bb1  mov     rcx, [rbp+5D8h]; this
0x1800b1bb8  mov     r9d, edi; char *
0x1800b1bbb  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\uiaut"...
  ... truncated ...
```
