# CSpellerGlobalState::~CSpellerGlobalState(void)

- ea: `0x18026f074`
- end: `0x18026f1f0`
- name: `??1CSpellerGlobalState@@AEAA@XZ`
- size: `380`
- prototype: `void __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180270910`

## callees

- `0x180048d5c`
- `0x1800d29d8`
- `0x1800d2a5c`
- `0x18013bf70`
- `0x18026f074`
- `0x180270970`
- `0x1802710a0`
- `0x18027270c`
- `0x1802738ec`
- `0x18027a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18026f0e3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18026f0fe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18026f119`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18026f1d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18026f0e3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18026f0fe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18026f119`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18026f1d7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18026f177`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18026f177`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026f191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026f191`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreeServices` at `0x18026f0c8`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreeServices` at `0x18026f0c8`

## pseudocode

```c
void __fastcall CSpellerGlobalState::~CSpellerGlobalState(CSpellerGlobalState *this)
{
  bool v1; // zf
  struct _MAPPING_SERVICE_INFO *v3; // rcx
  void **v4; // rdi
  void **v5; // rdi
  void **v6; // rdi
  __int64 v7; // rcx
  void *v8; // rdi
  HMODULE v9; // rcx
  void *v10; // rcx
  void **v11; // rdi

  v1 = *((_BYTE *)this + 66) == 0;
  *(_QWORD *)this = &CSpellerGlobalState::`vftable'{for `ISpellEngineTSF'};
  *((_QWORD *)this + 1) = &CSpellerGlobalState::`vftable'{for `ISpellEngineGlobalState'};
  *((_QWORD *)this + 2) = &CSpellerGlobalState::`vftable'{for `IMultilingualSpellEngine'};
  if ( !v1 )
  {
    _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 2, 1);
    CSpellerGlobalState::FinishInitialization(this);
  }
  v3 = (struct _MAPPING_SERVICE_INFO *)*((_QWORD *)this + 31);
  if ( v3 )
    MappingFreeServices(v3);
  CSpellerGlobalState::RemoveSpellCheckingResources(this);
  v4 = (void **)*((_QWORD *)this + 5);
  if ( v4 )
  {
    free(v4[2]);
    operator delete(v4);
  }
  v5 = (void **)*((_QWORD *)this + 3);
  if ( v5 )
  {
    free(v5[2]);
    operator delete(v5);
  }
  v6 = (void **)*((_QWORD *)this + 4);
  if ( v6 )
  {
    free(v6[2]);
    operator delete(v6);
  }
  v7 = *((_QWORD *)this + 16);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 16LL))(*((_QWORD *)this + 16));
  }
  v8 = (void *)*((_QWORD *)this + 7);
  if ( v8 )
  {
    CSpellContextHandler::~CSpellContextHandler(*((CSpellContextHandler **)this + 7));
    operator delete(v8);
  }
  v9 = (HMODULE)*((_QWORD *)this + 17);
  if ( v9 )
    FreeLibrary(v9);
  CSpellerGlobalState::FreeSpellCheckErrors(this);
  v10 = (void *)*((_QWORD *)this + 40);
  if ( v10 )
    CoTaskMemFree(v10);
  v11 = (void **)((char *)this + 80);
  if ( *((_QWORD *)this + 10) )
  {
    CSpellCheckerTelemetry::LogSpellerStatistics<CSpellCheckerTelemetryStatistics * &>((char *)this + 80);
    operator delete(*v11);
    *v11 = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 296);
  CMultilingualSpeller::~CMultilingualSpeller((CSpellerGlobalState *)((char *)this + 256));
  free(*((void **)this + 30));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 48);
}

```

## disassembly

```asm
0x18026f074  mov     [rsp+arg_0], rbx
0x18026f079  push    rdi
0x18026f07a  sub     rsp, 20h
0x18026f07e  cmp     byte ptr [rcx+42h], 0
0x18026f082  lea     rax, ??_7CSpellerGlobalState@@6BISpellEngineTSF@@@; const CSpellerGlobalState::`vftable'{for `ISpellEngineTSF'}
0x18026f089  mov     [rcx], rax
0x18026f08c  mov     rbx, rcx
0x18026f08f  lea     rax, ??_7CSpellerGlobalState@@6BISpellEngineGlobalState@@@; const CSpellerGlobalState::`vftable'{for `ISpellEngineGlobalState'}
0x18026f096  mov     [rcx+8], rax
0x18026f09a  lea     rax, ??_7CSpellerGlobalState@@6BIMultilingualSpellEngine@@@; const CSpellerGlobalState::`vftable'{for `IMultilingualSpellEngine'}
0x18026f0a1  mov     [rcx+10h], rax
0x18026f0a5  jz      short loc_18026F0BC
0x18026f0a7  mov     ecx, 2
0x18026f0ac  lea     eax, [rcx-1]
0x18026f0af  lock cmpxchg [rbx+68h], ecx
0x18026f0b4  mov     rcx, rbx; this
0x18026f0b7  call    ?FinishInitialization@CSpellerGlobalState@@QEAAJXZ; CSpellerGlobalState::FinishInitialization(void)
0x18026f0bc  mov     rcx, [rbx+0F8h]; pServiceInfo
0x18026f0c3  test    rcx, rcx
0x18026f0c6  jz      short loc_18026F0CE
0x18026f0c8  call    cs:__imp_MappingFreeServices
0x18026f0ce  mov     rcx, rbx; this
0x18026f0d1  call    ?RemoveSpellCheckingResources@CSpellerGlobalState@@AEAAXXZ; CSpellerGlobalState::RemoveSpellCheckingResources(void)
0x18026f0d6  mov     rdi, [rbx+28h]
0x18026f0da  test    rdi, rdi
0x18026f0dd  jz      short loc_18026F0F1
0x18026f0df  mov     rcx, [rdi+10h]; Block
0x18026f0e3  call    cs:__imp_free
0x18026f0e9  mov     rcx, rdi; Block
0x18026f0ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18026f0f1  mov     rdi, [rbx+18h]
0x18026f0f5  test    rdi, rdi
0x18026f0f8  jz      short loc_18026F10C
0x18026f0fa  mov     rcx, [rdi+10h]; Block
0x18026f0fe  call    cs:__imp_free
0x18026f104  mov     rcx, rdi; Block
0x18026f107  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18026f10c  mov     rdi, [rbx+20h]
0x18026f110  test    rdi, rdi
0x18026f113  jz      short loc_18026F127
0x18026f115  mov     rcx, [rdi+10h]; Block
0x18026f119  call    cs:__imp_free
0x18026f11f  mov     rcx, rdi; Block
0x18026f122  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18026f127  mov     rcx, [rbx+80h]
0x18026f12e  test    rcx, rcx
0x18026f131  jz      short loc_18026F152
0x18026f133  mov     rax, [rcx]
0x18026f136  mov     rax, [rax+20h]
0x18026f13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026f13f  mov     rcx, [rbx+80h]
0x18026f146  mov     rax, [rcx]
0x18026f149  mov     rax, [rax+10h]
0x18026f14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026f152  mov     rdi, [rbx+38h]
0x18026f156  test    rdi, rdi
0x18026f159  jz      short loc_18026F16B
0x18026f15b  mov     rcx, rdi; this
0x18026f15e  call    ??1CSpellContextHandler@@QEAA@XZ; CSpellContextHandler::~CSpellContextHandler(void)
0x18026f163  mov     rcx, rdi; Block
0x18026f166  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18026f16b  mov     rcx, [rbx+88h]; hLibModule
0x18026f172  test    rcx, rcx
0x18026f175  jz      short loc_18026F17D
0x18026f177  call    cs:__imp_FreeLibrary
0x18026f17d  mov     rcx, rbx; this
0x18026f180  call    ?FreeSpellCheckErrors@CSpellerGlobalState@@AEAAXXZ; CSpellerGlobalState::FreeSpellCheckErrors(void)
0x18026f185  mov     rcx, [rbx+140h]; pv
0x18026f18c  test    rcx, rcx
0x18026f18f  jz      short loc_18026F197
0x18026f191  call    cs:__imp_CoTaskMemFree
0x18026f197  lea     rdi, [rbx+50h]
0x18026f19b  cmp     qword ptr [rdi], 0
0x18026f19f  jz      short loc_18026F1B8
0x18026f1a1  mov     rcx, rdi
0x18026f1a4  call    ??$LogSpellerStatistics@AEAPEAVCSpellCheckerTelemetryStatistics@@@CSpellCheckerTelemetry@@SAXAEAPEAVCSpellCheckerTelemetryStatistics@@@Z; CSpellCheckerTelemetry::LogSpellerStatistics<CSpellCheckerTelemetryStatistics * &>(CSpellCheckerTelemetryStatistics * &)
0x18026f1a9  mov     rcx, [rdi]; Block
0x18026f1ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18026f1b1  mov     qword ptr [rdi], 0
0x18026f1b8  lea     rcx, [rbx+128h]
0x18026f1bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18026f1c4  lea     rcx, [rbx+100h]; this
0x18026f1cb  call    ??1CMultilingualSpeller@@QEAA@XZ; CMultilingualSpeller::~CMultilingualSpeller(void)
0x18026f1d0  mov     rcx, [rbx+0F0h]; Block
0x18026f1d7  call    cs:__imp_free
0x18026f1dd  lea     rcx, [rbx+30h]
0x18026f1e1  mov     rbx, [rsp+28h+arg_0]
0x18026f1e6  add     rsp, 20h
0x18026f1ea  pop     rdi
0x18026f1eb  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
