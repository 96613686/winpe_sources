# CMapiManager::CMapiManager(ulong)

- ea: `0x18002ce64`
- end: `0x18002d00f`
- name: `??0CMapiManager@@AEAA@K@Z`
- size: `427`
- prototype: `CMapiManager *__fastcall(CMapiManager *this, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e57c`

## callees

- `0x1800113ec`
- `0x18002cd78`
- `0x18002eb44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cfa1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002cfa1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002cf4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002cfc2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002cf4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002cfc2`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18002cf8a`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18002cf8a`

## pseudocode

```c
CMapiManager *__fastcall CMapiManager::CMapiManager(CMapiManager *this, unsigned int a2, int a3, int a4)
{
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  int v9; // xmm5_4
  __int64 v10; // r8
  __int64 v11; // r8

  *(_QWORD *)this = &CMapiManager::`vftable';
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(
    (_DWORD)this + 16,
    a2,
    a3,
    a4,
    LODWORD(FLOAT_2_25));
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(
    (_DWORD)this + 280,
    v6,
    v7,
    v8,
    v9);
  CLogger::Info(L"CMapiManager::CMapiManager() Enter");
  *((_DWORD *)this + 41) = a2 & 1;
  *((_DWORD *)this + 39) = (a2 >> 1) & 1;
  *((_DWORD *)this + 40) = 0;
  *((_DWORD *)this + 38) = (a2 & 4) == 0;
  *((_DWORD *)this + 42) = (a2 >> 3) & 1;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  LOBYTE(v10) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 16,
    7,
    v10);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  *((_DWORD *)this + 54) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 17) = CreateSemaphoreW(0, 0, 1, 0);
  *((_QWORD *)this + 34) = CreateEventW(0, 0, 0, 0);
  LOBYTE(v11) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 280,
    7,
    v11);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  CLogger::Info(L"CMapiManager::CMapiManager() Exit");
  return this;
}

```

## disassembly

```asm
0x18002ce64  mov     [rsp+arg_8], rbx
0x18002ce69  mov     [rsp+arg_10], rsi
0x18002ce6e  mov     [rsp+arg_0], rcx
0x18002ce73  push    rdi
0x18002ce74  push    r14
0x18002ce76  push    r15
0x18002ce78  sub     rsp, 30h
0x18002ce7c  mov     ebx, edx
0x18002ce7e  mov     r14, rcx
0x18002ce81  lea     rax, ??_7CMapiManager@@6B@; const CMapiManager::`vftable'
0x18002ce88  mov     [rcx], rax
0x18002ce8b  movss   xmm5, cs:__real@40100000
0x18002ce93  movss   [rsp+48h+var_28], xmm5
0x18002ce99  movss   xmm3, cs:__real@3e800000
0x18002cea1  movss   xmm4, cs:__real@3f400000
0x18002cea9  movaps  xmm2, xmm4
0x18002ceac  add     rcx, 10h
0x18002ceb0  call    ??0?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiSession@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiSession@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(uint,float,float,float,uint)
0x18002ceb5  nop
0x18002ceb6  lea     rsi, [r14+118h]
0x18002cebd  movss   [rsp+48h+var_28], xmm5
0x18002cec3  movaps  xmm2, xmm4
0x18002cec6  mov     rcx, rsi
0x18002cec9  call    ??0?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiSession@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiSession@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(uint,float,float,float,uint)
0x18002cece  nop
0x18002cecf  lea     rcx, aCmapimanagerCm; "CMapiManager::CMapiManager() Enter"
0x18002ced6  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002cedb  mov     eax, ebx
0x18002cedd  and     eax, 1
0x18002cee0  mov     [r14+0A4h], eax
0x18002cee7  mov     eax, ebx
0x18002cee9  shr     eax, 1
0x18002ceeb  and     eax, 1
0x18002ceee  mov     [r14+9Ch], eax
0x18002cef5  xor     r15d, r15d
0x18002cef8  mov     [r14+0A0h], r15d
0x18002ceff  mov     eax, ebx
0x18002cf01  shr     eax, 2
0x18002cf04  not     eax
0x18002cf06  and     eax, 1
0x18002cf09  mov     [r14+98h], eax
0x18002cf10  shr     ebx, 3
0x18002cf13  and     ebx, 1
0x18002cf16  mov     [r14+0A8h], ebx
0x18002cf1d  mov     [r14+80h], r15
0x18002cf24  mov     [r14+88h], r15
0x18002cf2b  mov     [r14+108h], r15
0x18002cf32  mov     [r14+110h], r15
0x18002cf39  mov     r8b, 1
0x18002cf3c  lea     ebx, [r15+7]
0x18002cf40  mov     edx, ebx
0x18002cf42  lea     rcx, [r14+10h]
0x18002cf46  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x18002cf4b  lea     rcx, [r14+58h]; lpCriticalSection
0x18002cf4f  call    cs:__imp_InitializeCriticalSection
0x18002cf55  mov     [r14+0B0h], r15
0x18002cf5c  mov     [r14+0B8h], r15
0x18002cf63  mov     [r14+0C0h], r15d
0x18002cf6a  mov     [r14+0D8h], r15d
0x18002cf71  mov     [r14+0C8h], r15
0x18002cf78  mov     [r14+0D0h], r15
0x18002cf7f  xor     r9d, r9d; lpName
0x18002cf82  xor     edx, edx; lInitialCount
0x18002cf84  xor     ecx, ecx; lpSemaphoreAttributes
0x18002cf86  lea     r8d, [r15+1]; lMaximumCount
0x18002cf8a  call    cs:__imp_CreateSemaphoreW
0x18002cf90  mov     [r14+88h], rax
0x18002cf97  xor     r9d, r9d; lpName
0x18002cf9a  xor     r8d, r8d; bInitialState
0x18002cf9d  xor     edx, edx; bManualReset
0x18002cf9f  xor     ecx, ecx; lpEventAttributes
0x18002cfa1  call    cs:__imp_CreateEventW
0x18002cfa7  mov     [r14+110h], rax
0x18002cfae  mov     r8b, 1
0x18002cfb1  mov     edx, ebx
0x18002cfb3  mov     rcx, rsi
0x18002cfb6  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x18002cfbb  lea     rcx, [r14+160h]; lpCriticalSection
0x18002cfc2  call    cs:__imp_InitializeCriticalSection
0x18002cfc8  mov     [r14+0E0h], r15
0x18002cfcf  mov     [r14+0E8h], r15
0x18002cfd6  mov     [r14+0F0h], r15
0x18002cfdd  mov     [r14+0F8h], r15
0x18002cfe4  mov     [r14+100h], r15
0x18002cfeb  lea     rcx, aCmapimanagerCm_2; "CMapiManager::CMapiManager() Exit"
0x18002cff2  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002cff7  nop
0x18002cff8  mov     rax, r14
0x18002cffb  mov     rbx, [rsp+48h+arg_8]
0x18002d000  mov     rsi, [rsp+48h+arg_10]
0x18002d005  add     rsp, 30h
0x18002d009  pop     r15
0x18002d00b  pop     r14
0x18002d00d  pop     rdi
0x18002d00e  retn
```
