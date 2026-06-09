# CDlpManager::~CDlpManager(void)

- ea: `0x140029f5c`
- end: `0x14002a464`
- name: `??1CDlpManager@@EEAA@XZ`
- size: `1288`
- prototype: `void __fastcall(CDlpManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14002b3b0`

## callees

- `0x1400135b8`
- `0x14001dbe4`
- `0x140029f5c`
- `0x14004d240`
- `0x14004dbc4`
- `0x14004e1f8`
- `0x14004e398`
- `0x14004eda0`
- `0x140082010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14002a08c`
- `KERNEL32!CloseHandle` at `0x14002a0ab`
- `KERNEL32!CloseHandle` at `0x14002a0ca`
- `KERNEL32!CloseHandle` at `0x14002a08c`
- `KERNEL32!CloseHandle` at `0x14002a0ab`
- `KERNEL32!CloseHandle` at `0x14002a0ca`
- `KERNEL32!DeleteCriticalSection` at `0x14002a050`
- `KERNEL32!DeleteCriticalSection` at `0x14002a070`
- `KERNEL32!DeleteCriticalSection` at `0x14002a314`
- `KERNEL32!DeleteCriticalSection` at `0x14002a334`
- `KERNEL32!DeleteCriticalSection` at `0x14002a354`
- `KERNEL32!DeleteCriticalSection` at `0x14002a374`
- `KERNEL32!DeleteCriticalSection` at `0x14002a394`
- `KERNEL32!DeleteCriticalSection` at `0x14002a3b4`
- `KERNEL32!DeleteCriticalSection` at `0x14002a3d4`
- `KERNEL32!DeleteCriticalSection` at `0x14002a438`
- `KERNEL32!DeleteCriticalSection` at `0x14002a050`
- `KERNEL32!DeleteCriticalSection` at `0x14002a070`
- `KERNEL32!DeleteCriticalSection` at `0x14002a314`
- `KERNEL32!DeleteCriticalSection` at `0x14002a334`
- `KERNEL32!DeleteCriticalSection` at `0x14002a354`
- `KERNEL32!DeleteCriticalSection` at `0x14002a374`
- `KERNEL32!DeleteCriticalSection` at `0x14002a394`
- `KERNEL32!DeleteCriticalSection` at `0x14002a3b4`
- `KERNEL32!DeleteCriticalSection` at `0x14002a3d4`
- `KERNEL32!DeleteCriticalSection` at `0x14002a438`
- `KERNEL32!HeapFree` at `0x14002a187`
- `KERNEL32!HeapFree` at `0x14002a1c5`
- `KERNEL32!HeapFree` at `0x14002a203`
- `KERNEL32!HeapFree` at `0x14002a241`
- `KERNEL32!HeapFree` at `0x14002a27f`
- `KERNEL32!HeapFree` at `0x14002a2bd`
- `KERNEL32!HeapFree` at `0x14002a2f4`
- `KERNEL32!HeapFree` at `0x14002a402`
- `KERNEL32!HeapFree` at `0x14002a187`
- `KERNEL32!HeapFree` at `0x14002a1c5`
- `KERNEL32!HeapFree` at `0x14002a203`
- `KERNEL32!HeapFree` at `0x14002a241`
- `KERNEL32!HeapFree` at `0x14002a27f`
- `KERNEL32!HeapFree` at `0x14002a2bd`
- `KERNEL32!HeapFree` at `0x14002a2f4`
- `KERNEL32!HeapFree` at `0x14002a402`
- `KERNEL32!GetProcessHeap` at `0x14002a173`
- `KERNEL32!GetProcessHeap` at `0x14002a1b1`
- `KERNEL32!GetProcessHeap` at `0x14002a1ef`
- `KERNEL32!GetProcessHeap` at `0x14002a22d`
- `KERNEL32!GetProcessHeap` at `0x14002a26b`
- `KERNEL32!GetProcessHeap` at `0x14002a2a9`
- `KERNEL32!GetProcessHeap` at `0x14002a2e0`
- `KERNEL32!GetProcessHeap` at `0x14002a3ed`
- `KERNEL32!GetProcessHeap` at `0x14002a173`
- `KERNEL32!GetProcessHeap` at `0x14002a1b1`
- `KERNEL32!GetProcessHeap` at `0x14002a1ef`
- `KERNEL32!GetProcessHeap` at `0x14002a22d`
- `KERNEL32!GetProcessHeap` at `0x14002a26b`
- `KERNEL32!GetProcessHeap` at `0x14002a2a9`
- `KERNEL32!GetProcessHeap` at `0x14002a2e0`
- `KERNEL32!GetProcessHeap` at `0x14002a3ed`

## pseudocode

```c
void __fastcall CDlpManager::~CDlpManager(CDlpManager *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  void *v12; // rsi
  HANDLE ProcessHeap; // rax
  void *v14; // rsi
  HANDLE v15; // rax
  void *v16; // rsi
  HANDLE v17; // rax
  void *v18; // rsi
  HANDLE v19; // rax
  void *v20; // rsi
  HANDLE v21; // rax
  void *v22; // rsi
  HANDLE v23; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 v26; // rbx
  HANDLE v27; // rax

  *(_QWORD *)this = &CDlpManager::`vftable'{for `IDlpObject'};
  *((_QWORD *)this + 1) = &CDlpManager::`vftable'{for `IDlpProperties'};
  *((_QWORD *)this + 10) = &CDlpFile::`vftable';
  if ( *((_DWORD *)this + 212) )
  {
    CDlpManager::SetPriority(this);
    *((_DWORD *)this + 212) = 0;
  }
  if ( *((_DWORD *)this + 213) )
  {
    CDlpManager::SetThreadPriority(this);
    *((_DWORD *)this + 213) = 0;
  }
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 528, 0);
  v2 = *((_QWORD *)this + 81);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 81) = 0;
  }
  v3 = *((_QWORD *)this + 80);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 80) = 0;
  }
  v4 = *((_QWORD *)this + 82);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 82) = 0;
  }
  if ( *((_DWORD *)this + 204) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 776));
    *((_DWORD *)this + 204) = 0;
  }
  if ( *((_DWORD *)this + 188) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
    *((_DWORD *)this + 188) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 86);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 86) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 85);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 85) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 84);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 84) = 0;
  }
  v8 = *((_QWORD *)this + 83);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 83) = 0;
  }
  v9 = *((_QWORD *)this + 82);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 82) = 0;
  }
  v10 = *((_QWORD *)this + 81);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 81) = 0;
  }
  v11 = *((_QWORD *)this + 80);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)this + 80) = 0;
  }
  CArray<unsigned __int64,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 624, 0);
  v12 = (void *)*((_QWORD *)this + 79);
  if ( v12 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
    *((_QWORD *)this + 79) = 0;
  }
  CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 608, 0);
  v14 = (void *)*((_QWORD *)this + 77);
  if ( v14 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
    *((_QWORD *)this + 77) = 0;
  }
  CArray<unsigned long,unsigned long,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 592, 0);
  v16 = (void *)*((_QWORD *)this + 75);
  if ( v16 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
    *((_QWORD *)this + 75) = 0;
  }
  CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 576, 0);
  v18 = (void *)*((_QWORD *)this + 73);
  if ( v18 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v18);
    *((_QWORD *)this + 73) = 0;
  }
  CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 560, 0);
  v20 = (void *)*((_QWORD *)this + 71);
  if ( v20 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v20);
    *((_QWORD *)this + 71) = 0;
  }
  CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 544, 0);
  v22 = (void *)*((_QWORD *)this + 69);
  if ( v22 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
    *((_QWORD *)this + 69) = 0;
  }
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 528, 0);
  v24 = (void *)*((_QWORD *)this + 67);
  if ( v24 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
    *((_QWORD *)this + 67) = 0;
  }
  if ( *((_DWORD *)this + 130) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 12);
    *((_DWORD *)this + 130) = 0;
  }
  if ( *((_DWORD *)this + 116) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
    *((_DWORD *)this + 116) = 0;
  }
  if ( *((_DWORD *)this + 102) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
    *((_DWORD *)this + 102) = 0;
  }
  if ( *((_DWORD *)this + 88) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    *((_DWORD *)this + 88) = 0;
  }
  if ( *((_DWORD *)this + 74) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
    *((_DWORD *)this + 74) = 0;
  }
  if ( *((_DWORD *)this + 60) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
    *((_DWORD *)this + 60) = 0;
  }
  if ( *((_DWORD *)this + 46) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
    *((_DWORD *)this + 46) = 0;
  }
  v26 = *((_QWORD *)this + 15);
  if ( v26 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, (LPVOID)(v26 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 15) = 0;
  }
  *(_QWORD *)this = &CUnknownImpl<IDlpManagerInternal>::`vftable'{for `IDlpObject'};
  *((_QWORD *)this + 1) = &CUnknownImpl<IDlpManagerInternal>::`vftable'{for `IDlpProperties'};
  if ( *((_DWORD *)this + 18) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *((_DWORD *)this + 18) = 0;
  }
}

```

## disassembly

```asm
0x140029f5c  mov     rax, rsp
0x140029f5f  push    r14
0x140029f61  sub     rsp, 30h
0x140029f65  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x140029f6d  mov     [rax+8], rbx
0x140029f71  mov     [rax+10h], rbp
0x140029f75  mov     [rax+18h], rsi
0x140029f79  mov     [rax+20h], rdi
0x140029f7d  mov     rdi, rcx
0x140029f80  lea     rax, ??_7CDlpManager@@6BIDlpObject@@@; const CDlpManager::`vftable'{for `IDlpObject'}
0x140029f87  mov     [rcx], rax
0x140029f8a  lea     rax, ??_7CDlpManager@@6BIDlpProperties@@@; const CDlpManager::`vftable'{for `IDlpProperties'}
0x140029f91  mov     [rcx+8], rax
0x140029f95  lea     rax, ??_7CDlpFile@@6B@; const CDlpFile::`vftable'
0x140029f9c  mov     [rcx+50h], rax
0x140029fa0  mov     edx, [rcx+350h]
0x140029fa6  xor     r14d, r14d
0x140029fa9  test    edx, edx
0x140029fab  jz      short loc_140029FB9
0x140029fad  call    ?SetPriority@CDlpManager@@UEAAJW4WINDLP_PRIORITY@@@Z; CDlpManager::SetPriority(WINDLP_PRIORITY)
0x140029fb2  mov     [rdi+350h], r14d
0x140029fb9  mov     edx, [rdi+354h]
0x140029fbf  test    edx, edx
0x140029fc1  jz      short loc_140029FD2
0x140029fc3  mov     rcx, rdi
0x140029fc6  call    ?SetThreadPriority@CDlpManager@@UEAAJW4WINDLP_PRIORITY@@@Z; CDlpManager::SetThreadPriority(WINDLP_PRIORITY)
0x140029fcb  mov     [rdi+354h], r14d
0x140029fd2  lea     rbp, [rdi+210h]
0x140029fd9  xor     edx, edx
0x140029fdb  mov     rcx, rbp
0x140029fde  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x140029fe3  mov     rcx, [rdi+288h]
0x140029fea  test    rcx, rcx
0x140029fed  jz      short loc_14002A002
0x140029fef  mov     rax, [rcx]
0x140029ff2  mov     rax, [rax+10h]
0x140029ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029ffb  mov     [rdi+288h], r14
0x14002a002  mov     rcx, [rdi+280h]
0x14002a009  test    rcx, rcx
0x14002a00c  jz      short loc_14002A021
0x14002a00e  mov     rax, [rcx]
0x14002a011  mov     rax, [rax+10h]
0x14002a015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a01a  mov     [rdi+280h], r14
0x14002a021  mov     rcx, [rdi+290h]
0x14002a028  test    rcx, rcx
0x14002a02b  jz      short loc_14002A040
0x14002a02d  mov     rax, [rcx]
0x14002a030  mov     rax, [rax+10h]
0x14002a034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a039  mov     [rdi+290h], r14
0x14002a040  lea     rbx, [rdi+308h]
0x14002a047  cmp     [rbx+28h], r14d
0x14002a04b  jz      short loc_14002A060
0x14002a04d  mov     rcx, rbx; lpCriticalSection
0x14002a050  call    cs:__imp_DeleteCriticalSection
0x14002a057  nop     dword ptr [rax+rax+00h]
0x14002a05c  mov     [rbx+28h], r14d
0x14002a060  lea     rbx, [rdi+2C8h]
0x14002a067  cmp     [rbx+28h], r14d
0x14002a06b  jz      short loc_14002A080
0x14002a06d  mov     rcx, rbx; lpCriticalSection
0x14002a070  call    cs:__imp_DeleteCriticalSection
0x14002a077  nop     dword ptr [rax+rax+00h]
0x14002a07c  mov     [rbx+28h], r14d
0x14002a080  mov     rcx, [rdi+2B0h]; hObject
0x14002a087  test    rcx, rcx
0x14002a08a  jz      short loc_14002A09F
0x14002a08c  call    cs:__imp_CloseHandle
0x14002a093  nop     dword ptr [rax+rax+00h]
0x14002a098  mov     [rdi+2B0h], r14
0x14002a09f  mov     rcx, [rdi+2A8h]; hObject
0x14002a0a6  test    rcx, rcx
0x14002a0a9  jz      short loc_14002A0BE
0x14002a0ab  call    cs:__imp_CloseHandle
0x14002a0b2  nop     dword ptr [rax+rax+00h]
0x14002a0b7  mov     [rdi+2A8h], r14
0x14002a0be  mov     rcx, [rdi+2A0h]; hObject
0x14002a0c5  test    rcx, rcx
0x14002a0c8  jz      short loc_14002A0DD
0x14002a0ca  call    cs:__imp_CloseHandle
0x14002a0d1  nop     dword ptr [rax+rax+00h]
0x14002a0d6  mov     [rdi+2A0h], r14
0x14002a0dd  mov     rcx, [rdi+298h]
0x14002a0e4  test    rcx, rcx
0x14002a0e7  jz      short loc_14002A0FC
0x14002a0e9  mov     rax, [rcx]
0x14002a0ec  mov     rax, [rax+10h]
0x14002a0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a0f5  mov     [rdi+298h], r14
0x14002a0fc  mov     rcx, [rdi+290h]
0x14002a103  test    rcx, rcx
0x14002a106  jz      short loc_14002A11B
0x14002a108  mov     rax, [rcx]
0x14002a10b  mov     rax, [rax+10h]
0x14002a10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a114  mov     [rdi+290h], r14
0x14002a11b  mov     rcx, [rdi+288h]
0x14002a122  test    rcx, rcx
0x14002a125  jz      short loc_14002A13A
0x14002a127  mov     rax, [rcx]
0x14002a12a  mov     rax, [rax+10h]
0x14002a12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a133  mov     [rdi+288h], r14
0x14002a13a  mov     rcx, [rdi+280h]
0x14002a141  test    rcx, rcx
0x14002a144  jz      short loc_14002A159
0x14002a146  mov     rax, [rcx]
0x14002a149  mov     rax, [rax+10h]
0x14002a14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a152  mov     [rdi+280h], r14
0x14002a159  lea     rbx, [rdi+270h]
0x14002a160  xor     edx, edx
0x14002a162  mov     rcx, rbx
0x14002a165  call    ?SetSize@?$CArray@_K_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<unsigned __int64,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a16a  mov     rsi, [rbx+8]
0x14002a16e  test    rsi, rsi
0x14002a171  jz      short loc_14002A197
0x14002a173  call    cs:__imp_GetProcessHeap
0x14002a17a  nop     dword ptr [rax+rax+00h]
0x14002a17f  mov     rcx, rax; hHeap
0x14002a182  mov     r8, rsi; lpMem
0x14002a185  xor     edx, edx; dwFlags
0x14002a187  call    cs:__imp_HeapFree
0x14002a18e  nop     dword ptr [rax+rax+00h]
0x14002a193  mov     [rbx+8], r14
0x14002a197  lea     rbx, [rdi+260h]
0x14002a19e  xor     edx, edx
0x14002a1a0  mov     rcx, rbx
0x14002a1a3  call    ?SetSize@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a1a8  mov     rsi, [rbx+8]
0x14002a1ac  test    rsi, rsi
0x14002a1af  jz      short loc_14002A1D5
0x14002a1b1  call    cs:__imp_GetProcessHeap
0x14002a1b8  nop     dword ptr [rax+rax+00h]
0x14002a1bd  mov     rcx, rax; hHeap
0x14002a1c0  mov     r8, rsi; lpMem
0x14002a1c3  xor     edx, edx; dwFlags
0x14002a1c5  call    cs:__imp_HeapFree
0x14002a1cc  nop     dword ptr [rax+rax+00h]
0x14002a1d1  mov     [rbx+8], r14
0x14002a1d5  lea     rbx, [rdi+250h]
0x14002a1dc  xor     edx, edx
0x14002a1de  mov     rcx, rbx
0x14002a1e1  call    ?SetSize@?$CArray@KKVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<ulong,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a1e6  mov     rsi, [rbx+8]
0x14002a1ea  test    rsi, rsi
0x14002a1ed  jz      short loc_14002A213
0x14002a1ef  call    cs:__imp_GetProcessHeap
0x14002a1f6  nop     dword ptr [rax+rax+00h]
0x14002a1fb  mov     rcx, rax; hHeap
0x14002a1fe  mov     r8, rsi; lpMem
0x14002a201  xor     edx, edx; dwFlags
0x14002a203  call    cs:__imp_HeapFree
0x14002a20a  nop     dword ptr [rax+rax+00h]
0x14002a20f  mov     [rbx+8], r14
0x14002a213  lea     rbx, [rdi+240h]
0x14002a21a  xor     edx, edx
0x14002a21c  mov     rcx, rbx
0x14002a21f  call    ?SetSize@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a224  mov     rsi, [rbx+8]
0x14002a228  test    rsi, rsi
0x14002a22b  jz      short loc_14002A251
0x14002a22d  call    cs:__imp_GetProcessHeap
0x14002a234  nop     dword ptr [rax+rax+00h]
0x14002a239  mov     rcx, rax; hHeap
0x14002a23c  mov     r8, rsi; lpMem
0x14002a23f  xor     edx, edx; dwFlags
0x14002a241  call    cs:__imp_HeapFree
0x14002a248  nop     dword ptr [rax+rax+00h]
0x14002a24d  mov     [rbx+8], r14
0x14002a251  lea     rbx, [rdi+230h]
0x14002a258  xor     edx, edx
0x14002a25a  mov     rcx, rbx
0x14002a25d  call    ?SetSize@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a262  mov     rsi, [rbx+8]
0x14002a266  test    rsi, rsi
0x14002a269  jz      short loc_14002A28F
0x14002a26b  call    cs:__imp_GetProcessHeap
0x14002a272  nop     dword ptr [rax+rax+00h]
0x14002a277  mov     rcx, rax; hHeap
0x14002a27a  mov     r8, rsi; lpMem
0x14002a27d  xor     edx, edx; dwFlags
0x14002a27f  call    cs:__imp_HeapFree
0x14002a286  nop     dword ptr [rax+rax+00h]
0x14002a28b  mov     [rbx+8], r14
0x14002a28f  lea     rbx, [rdi+220h]
0x14002a296  xor     edx, edx
0x14002a298  mov     rcx, rbx
0x14002a29b  call    ?SetSize@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a2a0  mov     rsi, [rbx+8]
0x14002a2a4  test    rsi, rsi
0x14002a2a7  jz      short loc_14002A2CD
0x14002a2a9  call    cs:__imp_GetProcessHeap
0x14002a2b0  nop     dword ptr [rax+rax+00h]
0x14002a2b5  mov     rcx, rax; hHeap
0x14002a2b8  mov     r8, rsi; lpMem
0x14002a2bb  xor     edx, edx; dwFlags
0x14002a2bd  call    cs:__imp_HeapFree
0x14002a2c4  nop     dword ptr [rax+rax+00h]
0x14002a2c9  mov     [rbx+8], r14
0x14002a2cd  xor     edx, edx
0x14002a2cf  mov     rcx, rbp
0x14002a2d2  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14002a2d7  mov     rbx, [rbp+8]
0x14002a2db  test    rbx, rbx
0x14002a2de  jz      short loc_14002A304
0x14002a2e0  call    cs:__imp_GetProcessHeap
0x14002a2e7  nop     dword ptr [rax+rax+00h]
0x14002a2ec  mov     rcx, rax; hHeap
0x14002a2ef  mov     r8, rbx; lpMem
0x14002a2f2  xor     edx, edx; dwFlags
0x14002a2f4  call    cs:__imp_HeapFree
0x14002a2fb  nop     dword ptr [rax+rax+00h]
0x14002a300  mov     [rbp+8], r14
0x14002a304  lea     rbx, [rdi+1E0h]
0x14002a30b  cmp     [rbx+28h], r14d
0x14002a30f  jz      short loc_14002A324
0x14002a311  mov     rcx, rbx; lpCriticalSection
0x14002a314  call    cs:__imp_DeleteCriticalSection
0x14002a31b  nop     dword ptr [rax+rax+00h]
0x14002a320  mov     [rbx+28h], r14d
0x14002a324  lea     rbx, [rdi+1A8h]
0x14002a32b  cmp     [rbx+28h], r14d
0x14002a32f  jz      short loc_14002A344
0x14002a331  mov     rcx, rbx; lpCriticalSection
0x14002a334  call    cs:__imp_DeleteCriticalSection
0x14002a33b  nop     dword ptr [rax+rax+00h]
0x14002a340  mov     [rbx+28h], r14d
0x14002a344  lea     rbx, [rdi+170h]
0x14002a34b  cmp     [rbx+28h], r14d
0x14002a34f  jz      short loc_14002A364
0x14002a351  mov     rcx, rbx; lpCriticalSection
0x14002a354  call    cs:__imp_DeleteCriticalSection
0x14002a35b  nop     dword ptr [rax+rax+00h]
0x14002a360  mov     [rbx+28h], r14d
0x14002a364  lea     rbx, [rdi+138h]
0x14002a36b  cmp     [rbx+28h], r14d
0x14002a36f  jz      short loc_14002A384
0x14002a371  mov     rcx, rbx; lpCriticalSection
0x14002a374  call    cs:__imp_DeleteCriticalSection
0x14002a37b  nop     dword ptr [rax+rax+00h]
0x14002a380  mov     [rbx+28h], r14d
0x14002a384  lea     rbx, [rdi+100h]
0x14002a38b  cmp     [rbx+28h], r14d
0x14002a38f  jz      short loc_14002A3A4
0x14002a391  mov     rcx, rbx; lpCriticalSection
0x14002a394  call    cs:__imp_DeleteCriticalSection
0x14002a39b  nop     dword ptr [rax+rax+00h]
0x14002a3a0  mov     [rbx+28h], r14d
0x14002a3a4  lea     rbx, [rdi+0C8h]
0x14002a3ab  cmp     [rbx+28h], r14d
0x14002a3af  jz      short loc_14002A3C4
0x14002a3b1  mov     rcx, rbx; lpCriticalSection
0x14002a3b4  call    cs:__imp_DeleteCriticalSection
0x14002a3bb  nop     dword ptr [rax+rax+00h]
0x14002a3c0  mov     [rbx+28h], r14d
0x14002a3c4  lea     rbx, [rdi+90h]
0x14002a3cb  cmp     [rbx+28h], r14d
0x14002a3cf  jz      short loc_14002A3E4
0x14002a3d1  mov     rcx, rbx; lpCriticalSection
0x14002a3d4  call    cs:__imp_DeleteCriticalSection
0x14002a3db  nop     dword ptr [rax+rax+00h]
0x14002a3e0  mov     [rbx+28h], r14d
0x14002a3e4  mov     rbx, [rdi+78h]
0x14002a3e8  test    rbx, rbx
0x14002a3eb  jz      short loc_14002A419
0x14002a3ed  call    cs:__imp_GetProcessHeap
0x14002a3f4  nop     dword ptr [rax+rax+00h]
0x14002a3f9  mov     rcx, rax; hHeap
0x14002a3fc  lea     r8, [rbx-4]; lpMem
0x14002a400  xor     edx, edx; dwFlags
0x14002a402  call    cs:__imp_HeapFree
0x14002a409  nop     dword ptr [rax+rax+00h]
0x14002a40e  xor     ecx, ecx
0x14002a410  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14002a415  mov     [rdi+78h], r14
0x14002a419  lea     rax, ??_7?$CUnknownImpl@VIDlpManagerInternal@@@@6BIDlpObject@@@; const CUnknownImpl<IDlpManagerInternal>::`vftable'{for `IDlpObject'}
0x14002a420  mov     [rdi], rax
0x14002a423  lea     rax, ??_7?$CUnknownImpl@VIDlpManagerInternal@@@@6BIDlpProperties@@@; const CUnknownImpl<IDlpManagerInternal>::`vftable'{for `IDlpProperties'}
0x14002a42a  mov     [rdi+8], rax
0x14002a42e  cmp     [rdi+48h], r14d
0x14002a432  jz      short loc_14002A448
0x14002a434  lea     rcx, [rdi+20h]; lpCriticalSection
0x14002a438  call    cs:__imp_DeleteCriticalSection
0x14002a43f  nop     dword ptr [rax+rax+00h]
0x14002a444  mov     [rdi+48h], r14d
0x14002a448  mov     rbx, [rsp+38h+arg_0]
0x14002a44d  mov     rbp, [rsp+38h+arg_8]
0x14002a452  mov     rsi, [rsp+38h+arg_10]
0x14002a457  mov     rdi, [rsp+38h+arg_18]
0x14002a45c  add     rsp, 30h
0x14002a460  pop     r14
0x14002a462  retn
```
