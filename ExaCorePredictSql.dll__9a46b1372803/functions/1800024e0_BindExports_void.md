# BindExports(void)

- ea: `0x1800024e0`
- end: `0x1800026a6`
- name: `?BindExports@@YAXXZ`
- size: `454`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180001340`

## callees

- `0x180001d30`
- `0x180002030`
- `0x1800024e0`
- `0x180002aa0`
- `0x180003a10`
- `0x180004ac0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800024f7`
- `KERNEL32!GetProcAddress` at `0x180002512`
- `KERNEL32!GetProcAddress` at `0x18000252d`
- `KERNEL32!GetProcAddress` at `0x180002548`
- `KERNEL32!GetProcAddress` at `0x180002563`
- `KERNEL32!GetProcAddress` at `0x18000257e`
- `KERNEL32!GetProcAddress` at `0x180002599`
- `KERNEL32!GetProcAddress` at `0x1800024f7`
- `KERNEL32!GetProcAddress` at `0x180002512`
- `KERNEL32!GetProcAddress` at `0x18000252d`
- `KERNEL32!GetProcAddress` at `0x180002548`
- `KERNEL32!GetProcAddress` at `0x180002563`
- `KERNEL32!GetProcAddress` at `0x18000257e`
- `KERNEL32!GetProcAddress` at `0x180002599`
- `KERNEL32!FreeLibrary` at `0x1800025f3`
- `KERNEL32!FreeLibrary` at `0x1800025f3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180002635`

## string_xrefs

- `0x18000258b`: `SetUseCachedAllocator`

## pseudocode

```c
void __fastcall BindExports(HINSTANCE *a1)
{
  __int64 v1; // rbx
  void (*ProcAddress)(bool); // rax
  _QWORD *ThreadLocalStoragePointer; // rax
  void *(__cdecl *v4)(size_t); // rbx
  std::exception *v5; // rax
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+40h] [rbp-8h]
  std::exception *v8; // [rsp+50h] [rbp+8h] BYREF

  LoadPredictModule(a1);
  g_fnInitializeScoringSql = (void (*)(void))GetProcAddress(g_predictModule, "InitializeScoringSql");
  g_fnLoadModelSql = (void (*)(const struct _SQLSatellite_ArgsArray *, const struct _SQLSatellite_TableSchema *, struct _SQLSatellite_TableSchema *, struct TFPErrorDetails *, void **))GetProcAddress(g_predictModule, "LoadModelSql");
  g_fnScoreSql = (void (*)(void *, const struct _SQLSatellite_ArgsArray *, const struct _SQLSatellite_TableSchema *, struct _SQLSatellite_TableSchema *, struct CSQLBxInMemDataColumnChunk **, struct CSQLBxInMemDataColumnChunk **, struct TFPErrorDetails *))GetProcAddress(g_predictModule, "ScoreSql");
  g_fnUnloadModelSql = (void (*)(void *, struct TFPErrorDetails *))GetProcAddress(g_predictModule, "UnloadModelSql");
  g_fnTerminateScoringSql = (void (*)(void))GetProcAddress(g_predictModule, "TerminateScoringSql");
  g_fnSetMemoryAllocators = (void (*)(bool, void *(*)(unsigned __int64), void *(*)(unsigned __int64, unsigned __int64), void *(*)(void *, unsigned __int64), void (*)(void *)))GetProcAddress(g_predictModule, "SetMemoryAllocators");
  ProcAddress = (void (*)(bool))GetProcAddress(g_predictModule, "SetUseCachedAllocator");
  g_fnSetUseCachedAllocator = ProcAddress;
  if ( !g_fnInitializeScoringSql
    || !g_fnLoadModelSql
    || !g_fnScoreSql
    || !g_fnUnloadModelSql
    || !g_fnTerminateScoringSql
    || !g_fnSetMemoryAllocators
    || !ProcAddress )
  {
    v7 = v1;
    FreeLibrary(g_predictModule);
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    g_predictModule = 0;
    if ( !*(_BYTE *)(ThreadLocalStoragePointer[tls_index] + 1LL)
      || (v4 = (void *(__cdecl *)(size_t))g_pCachedMalloc) == 0 )
    {
      v4 = malloc;
      if ( g_pMalloc )
        v4 = (void *(__cdecl *)(size_t))g_pMalloc;
    }
    v5 = (std::exception *)((__int64 (__fastcall *)(__int64))v4)(24);
    if ( v5 )
    {
      v8 = std::exception::exception(v5, "Failed to load predict functions");
      throw (std::exception **)&v8;
    }
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x1800024e0  sub     rsp, 48h
0x1800024e4  call    ?LoadPredictModule@@YAXAEAPEAUHINSTANCE__@@@Z; LoadPredictModule(HINSTANCE__ * &)
0x1800024e9  mov     rcx, cs:?g_predictModule@@3PEAUHINSTANCE__@@EA; hModule
0x1800024f0  lea     rdx, ProcName; "InitializeScoringSql"
0x1800024f7  call    cs:__imp_GetProcAddress
0x1800024fd  mov     rcx, cs:?g_predictModule@@3PEAUHINSTANCE__@@EA; hModule
0x180002504  lea     rdx, aLoadmodelsql; "LoadModelSql"
0x18000250b  mov     cs:?g_fnInitializeScoringSql@@3P6AXXZEA, rax; void (*g_fnInitializeScoringSql)(void)
0x180002512  call    cs:__imp_GetProcAddress
0x180002518  mov     rcx, cs:?g_predictModule@@3PEAUHINSTANCE__@@EA; hModule
0x18000251f  lea     rdx, aScoresql; "ScoreSql"
0x180002526  mov     cs:?g_fnLoadModelSql@@3P6AXAEBU_SQLSatellite_ArgsArray@@AEBU_SQLSatellite_TableSchema@@AEAU2@AEAUTFPErrorDetails@@PEAPEAX@ZEA, rax; void (*g_fnLoadModelSql)(_SQLSatellite_ArgsArray const &,_SQLSatellite_TableSchema const &,_SQLSatellite_TableSchema &,TFPErrorDetails &,void * *)
0x18000252d  call    cs:__imp_GetProcAddress
0x180002533  mov     rcx, cs:?g_predictModule@@3PEAUHINSTANCE__@@EA; hModule
0x18000253a  lea     rdx, aUnloadmodelsql; "UnloadModelSql"
0x180002541  mov     cs:?g_fnScoreSql@@3P6AXPEAXAEBU_SQLSatellite_ArgsArray@@AEBU_SQLSatellite_TableSchema@@PEAU2@PEAPEAVCSQLBxInMemDataColumnChunk@@4AEAUTFPErrorDetails@@@ZEA, rax; void (*g_fnScoreSql)(void *,_SQLSatellite_ArgsArray const &,_SQLSatellite_TableSchema const &,_SQLSatellite_TableSchema *,CSQLBxInMemDataColumnChunk * *,CSQLBxInMemDataColumnChunk * *,TFPErrorDetails &)
0x180002548  call    cs:__imp_GetProcAddress
0x18000254e  mov     rcx, cs:?g_predictModule@@3PEAUHINSTANCE__@@EA; hModule
0x180002555  lea     rdx, aTerminatescori; "TerminateScoringSql"
0x18000255c  mov     cs:?g_fnUnloadModelSql@@3P6AXPEAXAEAUTFPErrorDetails@@@ZEA, rax; void (*g_fnUnloadModelSql)(void *,TFPErrorDetails &)
0x180002563  call    cs:__imp_GetProcAddress
0x180002569  mov     rcx, cs:?g_predictModule@@3PEAUHINSTANCE__@@EA; hModule
0x180002570  lea     rdx, aSetmemoryalloc; "SetMemoryAllocators"
0x180002577  mov     cs:?g_fnTerminateScoringSql@@3P6AXXZEA, rax; void (*g_fnTerminateScoringSql)(void)
0x18000257e  call    cs:__imp_GetProcAddress
0x180002584  mov     rcx, cs:?g_predictModule@@3PEAUHINSTANCE__@@EA; hModule
0x18000258b  lea     rdx, aSetusecachedal; "SetUseCachedAllocator"
0x180002592  mov     cs:?g_fnSetMemoryAllocators@@3P6AX_NP6APEAX_K@ZP6APEAX11@ZP6APEAXPEAX1@ZP6AX4@Z@ZEA, rax; void (*g_fnSetMemoryAllocators)(bool,void * (*)(unsigned __int64),void * (*)(unsigned __int64,unsigned __int64),void * (*)(void *,unsigned __int64),void (*)(void *))
0x180002599  call    cs:__imp_GetProcAddress
0x18000259f  cmp     cs:?g_fnInitializeScoringSql@@3P6AXXZEA, 0; void (*g_fnInitializeScoringSql)(void)
0x1800025a7  mov     cs:?g_fnSetUseCachedAllocator@@3P6AX_N@ZEA, rax; void (*g_fnSetUseCachedAllocator)(bool)
0x1800025ae  jz      short loc_1800025E7
0x1800025b0  cmp     cs:?g_fnLoadModelSql@@3P6AXAEBU_SQLSatellite_ArgsArray@@AEBU_SQLSatellite_TableSchema@@AEAU2@AEAUTFPErrorDetails@@PEAPEAX@ZEA, 0; void (*g_fnLoadModelSql)(_SQLSatellite_ArgsArray const &,_SQLSatellite_TableSchema const &,_SQLSatellite_TableSchema &,TFPErrorDetails &,void * *)
0x1800025b8  jz      short loc_1800025E7
0x1800025ba  cmp     cs:?g_fnScoreSql@@3P6AXPEAXAEBU_SQLSatellite_ArgsArray@@AEBU_SQLSatellite_TableSchema@@PEAU2@PEAPEAVCSQLBxInMemDataColumnChunk@@4AEAUTFPErrorDetails@@@ZEA, 0; void (*g_fnScoreSql)(void *,_SQLSatellite_ArgsArray const &,_SQLSatellite_TableSchema const &,_SQLSatellite_TableSchema *,CSQLBxInMemDataColumnChunk * *,CSQLBxInMemDataColumnChunk * *,TFPErrorDetails &)
0x1800025c2  jz      short loc_1800025E7
0x1800025c4  cmp     cs:?g_fnUnloadModelSql@@3P6AXPEAXAEAUTFPErrorDetails@@@ZEA, 0; void (*g_fnUnloadModelSql)(void *,TFPErrorDetails &)
0x1800025cc  jz      short loc_1800025E7
0x1800025ce  cmp     cs:?g_fnTerminateScoringSql@@3P6AXXZEA, 0; void (*g_fnTerminateScoringSql)(void)
0x1800025d6  jz      short loc_1800025E7
0x1800025d8  cmp     cs:?g_fnSetMemoryAllocators@@3P6AX_NP6APEAX_K@ZP6APEAX11@ZP6APEAXPEAX1@ZP6AX4@Z@ZEA, 0; void (*g_fnSetMemoryAllocators)(bool,void * (*)(unsigned __int64),void * (*)(unsigned __int64,unsigned __int64),void * (*)(void *,unsigned __int64),void (*)(void *))
0x1800025e0  jz      short loc_1800025E7
0x1800025e2  test    rax, rax
0x1800025e5  jnz     short loc_18000265F
0x1800025e7  mov     rcx, cs:?g_predictModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800025ee  mov     [rsp+48h+var_8], rbx
0x1800025f3  call    cs:__imp_FreeLibrary
0x1800025f9  mov     ecx, cs:_tls_index
0x1800025ff  mov     rax, gs:58h
0x180002608  mov     edx, 1
0x18000260d  mov     cs:?g_predictModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_predictModule
0x180002618  mov     rax, [rax+rcx*8]
0x18000261c  cmp     byte ptr [rdx+rax], 0
0x180002620  jz      short loc_18000262E
0x180002622  mov     rbx, cs:?g_pCachedMalloc@@3P6APEAX_K@ZEA; void * (*g_pCachedMalloc)(unsigned __int64)
0x180002629  test    rbx, rbx
0x18000262c  jnz     short loc_180002643
0x18000262e  mov     rax, cs:?g_pMalloc@@3P6APEAX_K@ZEA; void * (*g_pMalloc)(unsigned __int64)
0x180002635  mov     rbx, cs:__imp_malloc
0x18000263c  test    rax, rax
0x18000263f  cmovnz  rbx, rax
0x180002643  mov     rcx, rbx
0x180002646  call    cs:__guard_check_icall_fptr
0x18000264c  mov     ecx, 18h
0x180002651  call    rbx ; void * (*g_pCachedMalloc)(unsigned __int64)
0x180002653  mov     rbx, [rsp+48h+var_8]
0x180002658  test    rax, rax
0x18000265b  jz      short loc_180002664
0x18000265d  jmp     short loc_180002680
0x18000265f  add     rsp, 48h
0x180002663  retn
0x180002664  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002669  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000266e  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180002675  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000267a  call    _CxxThrowException_0
0x180002680  lea     rdx, aFailedToLoadPr; "Failed to load predict functions"
0x180002687  mov     rcx, rax; this
0x18000268a  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x18000268f  lea     rdx, _TI2PEAVexception@std@@; pThrowInfo
0x180002696  mov     [rsp+48h+arg_0], rax
0x18000269b  lea     rcx, [rsp+48h+arg_0]; pExceptionObject
0x1800026a0  call    _CxxThrowException_0
```
