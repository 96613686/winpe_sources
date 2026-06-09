# SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *)

- ea: `0x1800215bc`
- end: `0x180021869`
- name: `?Unregister@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `685`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800120e0`
- `0x180012198`
- `0x1800123b0`
- `0x180012468`
- `0x1800125a4`
- `0x18001265c`
- `0x18001f470`

## callees

- `0x18000282c`
- `0x18001e840`
- `0x1800215bc`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002163e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002163e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002170b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002170b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800217c4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800217c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002183b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002183b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021719`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800217d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021719`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800217d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021631`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021729`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021631`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021729`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002178a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002178a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800217af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800217af`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180021610`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180021610`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x180021816`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x180021816`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::Unregister(
        __int64 a1,
        RTL_SRWLOCK *a2,
        __int64 a3)
{
  RTL_SRWLOCK *v3; // r15
  __int64 v4; // r14
  _BYTE *v5; // r12
  unsigned __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdx
  char v13; // r15
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  HANDLE EventW; // rbx
  char *v19; // rcx
  const char *v20; // r9
  void *v21; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  RTL_SRWLOCK *v26; // [rsp+68h] [rbp+10h]
  __int64 lpdwindex; // [rsp+70h] [rbp+18h] BYREF
  _BYTE *v28; // [rsp+78h] [rbp+20h]

  v26 = a2;
  v3 = a2;
  v4 = a1;
  v5 = (_BYTE *)(a1 + 106);
  v28 = (_BYTE *)(a1 + 106);
  if ( !*(_BYTE *)(a1 + 106) && *(_QWORD *)(a1 + 16) )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, (LPHANDLE)(a1 + 16), (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 160));
  AcquireSRWLockExclusive(v3 + 3);
  v6 = 0;
  v7 = 0xCBF29CE484222325uLL;
  do
    v7 = 0x100000001B3LL * (*((unsigned __int8 *)&v26 + v6++) ^ (unsigned __int64)v7);
  while ( v6 < 8 );
  v8 = *(_QWORD *)(v4 + 64);
  v9 = *(_QWORD **)(v8 + 16 * (*(_QWORD *)(v4 + 88) & v7) + 8);
  if ( v9 == *(_QWORD **)(v4 + 48) )
  {
LABEL_9:
    v9 = 0;
  }
  else
  {
    while ( v3 != (RTL_SRWLOCK *)v9[2] )
    {
      if ( v9 == *(_QWORD **)(v8 + 16 * (*(_QWORD *)(v4 + 88) & v7)) )
        goto LABEL_9;
      v9 = (_QWORD *)v9[1];
    }
  }
  if ( v9 )
  {
    v10 = 2 * (v7 & *(_QWORD *)(v4 + 88));
    if ( *(_QWORD **)(v8 + 16 * (v7 & *(_QWORD *)(v4 + 88)) + 8) == v9 )
    {
      if ( *(_QWORD **)(v8 + 16 * (v7 & *(_QWORD *)(v4 + 88))) == v9 )
      {
        v11 = *(_QWORD *)(v4 + 48);
        *(_QWORD *)(v8 + 16 * (v7 & *(_QWORD *)(v4 + 88))) = v11;
      }
      else
      {
        v11 = v9[1];
      }
      *(_QWORD *)(v8 + 8 * v10 + 8) = v11;
    }
    else if ( *(_QWORD **)(v8 + 16 * (v7 & *(_QWORD *)(v4 + 88))) == v9 )
    {
      *(_QWORD *)(v8 + 16 * (v7 & *(_QWORD *)(v4 + 88))) = *v9;
    }
    v12 = *v9;
    --*(_QWORD *)(v4 + 56);
    *(_QWORD *)v9[1] = v12;
    *(_QWORD *)(v12 + 8) = v9[1];
    operator delete(v9);
  }
  if ( v3 != (RTL_SRWLOCK *)-24LL )
    ReleaseSRWLockExclusive(v3 + 3);
  if ( v4 != -160 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 160));
  v13 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 112));
  lpdwindex = v4 + 112;
  LOBYTE(v14) = 3;
  LOBYTE(v15) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v15,
    v14);
  if ( !*(_DWORD *)(v4 + 152) && !*(_QWORD *)(v4 + 56) && !*(_BYTE *)(v4 + 208) && *(int *)(v4 + 224) >= 0 )
  {
    v13 = 1;
    *(_BYTE *)(v4 + 208) = 1;
    EventW = *(HANDLE *)(v4 + 200);
    if ( EventW )
      goto LABEL_31;
    EventW = CreateEventW(0, 1, 0, 0);
    v19 = *(char **)(v4 + 200);
    *(_QWORD *)(v4 + 200) = 0;
    if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v19);
    *(_QWORD *)(v4 + 200) = EventW;
    if ( EventW )
LABEL_31:
      ResetEvent(EventW);
  }
  if ( v4 != -112 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 112));
  if ( v13 )
  {
    try
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x545, v17, v20);
      v4 = a1;
      v5 = v28;
    }
    *v5 = 0;
    *(_DWORD *)(v4 + 224) = -2147418113;
    if ( *(_QWORD *)(v4 + 216) )
    {
      CoDecrementMTAUsage();
      *(_QWORD *)(v4 + 216) = 0;
    }
    *(_BYTE *)(v4 + 208) = 0;
    v21 = *(void **)(v4 + 200);
    if ( v21 )
      SetEvent(v21);
  }
  LOBYTE(v17) = 3;
  LOBYTE(v16) = 1;
  return wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
           `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
           v16,
           v17);
}

```

## disassembly

```asm
0x1800215bc  mov     rax, rsp
0x1800215bf  mov     [rax+10h], rdx
0x1800215c3  mov     [rax+8], rcx
0x1800215c7  push    rbx
0x1800215c8  push    rdi
0x1800215c9  push    r12
0x1800215cb  push    r14
0x1800215cd  push    r15
0x1800215cf  sub     rsp, 30h
0x1800215d3  mov     r15, rdx
0x1800215d6  mov     r14, rcx
0x1800215d9  lea     r12, [rcx+6Ah]
0x1800215dd  mov     [rsp+58h+arg_18], r12
0x1800215e2  cmp     byte ptr [r12], 0
0x1800215e7  jnz     short loc_180021616
0x1800215e9  lea     r9, [rcx+10h]; pHandles
0x1800215ed  cmp     qword ptr [r9], 0
0x1800215f1  jz      short loc_180021616
0x1800215f3  mov     dword ptr [rax+18h], 0
0x1800215fa  lea     rax, [rax+18h]
0x1800215fe  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180021603  mov     r8d, 1; cHandles
0x180021609  or      edx, 0FFFFFFFFh; dwTimeout
0x18002160c  lea     ecx, [r8+7]; dwFlags
0x180021610  call    cs:__imp_CoWaitForMultipleHandles
0x180021616  mov     r8b, 3
0x180021619  mov     dl, 1
0x18002161b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180021622  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180021627  lea     rdi, [r14+0A0h]
0x18002162e  mov     rcx, rdi; lpCriticalSection
0x180021631  call    cs:__imp_EnterCriticalSection
0x180021637  lea     rbx, [r15+18h]
0x18002163b  mov     rcx, rbx; SRWLock
0x18002163e  call    cs:__imp_AcquireSRWLockExclusive
0x180021644  nop
0x180021645  xor     ecx, ecx
0x180021647  mov     r8, 0CBF29CE484222325h
0x180021651  movzx   eax, byte ptr [rsp+rcx+58h+arg_8]
0x180021656  xor     r8, rax
0x180021659  mov     rdx, 100000001B3h
0x180021663  imul    r8, rdx
0x180021667  inc     rcx
0x18002166a  cmp     rcx, 8
0x18002166e  jb      short loc_180021651
0x180021670  mov     rdx, r8
0x180021673  and     rdx, [r14+58h]
0x180021677  mov     r9, [r14+40h]
0x18002167b  mov     rax, rdx
0x18002167e  add     rax, rax
0x180021681  mov     rcx, [r9+rax*8+8]
0x180021686  cmp     rcx, [r14+30h]
0x18002168a  jz      short loc_1800216A2
0x18002168c  add     rdx, rdx
0x18002168f  mov     rax, [r9+rdx*8]
0x180021693  cmp     r15, [rcx+10h]
0x180021697  jz      short loc_1800216A4
0x180021699  cmp     rcx, rax
0x18002169c  jnz     loc_18002185E
0x1800216a2  xor     ecx, ecx; Block
0x1800216a4  test    rcx, rcx
0x1800216a7  jz      short loc_180021703
0x1800216a9  mov     rdx, [r14+58h]
0x1800216ad  and     rdx, r8
0x1800216b0  add     rdx, rdx
0x1800216b3  cmp     [r9+rdx*8+8], rcx
0x1800216b8  jnz     short loc_1800216D5
0x1800216ba  cmp     [r9+rdx*8], rcx
0x1800216be  jnz     short loc_1800216CA
0x1800216c0  mov     rax, [r14+30h]
0x1800216c4  mov     [r9+rdx*8], rax
0x1800216c8  jmp     short loc_1800216CE
0x1800216ca  mov     rax, [rcx+8]
0x1800216ce  mov     [r9+rdx*8+8], rax
0x1800216d3  jmp     short loc_1800216E2
0x1800216d5  cmp     [r9+rdx*8], rcx
0x1800216d9  jnz     short loc_1800216E2
0x1800216db  mov     rax, [rcx]
0x1800216de  mov     [r9+rdx*8], rax
0x1800216e2  mov     rdx, [rcx]
0x1800216e5  dec     qword ptr [r14+38h]
0x1800216e9  mov     rax, [rcx+8]
0x1800216ed  mov     [rax], rdx
0x1800216f0  mov     rax, [rcx+8]
0x1800216f4  mov     [rdx+8], rax
0x1800216f8  mov     edx, 18h
0x1800216fd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021702  nop
0x180021703  test    rbx, rbx
0x180021706  jz      short loc_180021711
0x180021708  mov     rcx, rbx; SRWLock
0x18002170b  call    cs:__imp_ReleaseSRWLockExclusive
0x180021711  test    rdi, rdi
0x180021714  jz      short loc_18002171F
0x180021716  mov     rcx, rdi; lpCriticalSection
0x180021719  call    cs:__imp_LeaveCriticalSection
0x18002171f  xor     r15b, r15b
0x180021722  lea     rdi, [r14+70h]
0x180021726  mov     rcx, rdi; lpCriticalSection
0x180021729  call    cs:__imp_EnterCriticalSection
0x18002172f  mov     [rsp+58h+arg_10], rdi
0x180021734  mov     r8b, 3
0x180021737  mov     dl, 1
0x180021739  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180021740  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180021745  cmp     dword ptr [r14+98h], 0
0x18002174d  jnz     short loc_1800217CB
0x18002174f  cmp     qword ptr [r14+38h], 0
0x180021754  jnz     short loc_1800217CB
0x180021756  cmp     [r14+0D0h], r15b
0x18002175d  jnz     short loc_1800217CB
0x18002175f  cmp     dword ptr [r14+0E0h], 0
0x180021767  jl      short loc_1800217CB
0x180021769  mov     r15b, 1
0x18002176c  mov     [r14+0D0h], r15b
0x180021773  mov     rbx, [r14+0C8h]
0x18002177a  test    rbx, rbx
0x18002177d  jnz     short loc_1800217C1
0x18002177f  xor     r9d, r9d; lpName
0x180021782  xor     r8d, r8d; bInitialState
0x180021785  lea     edx, [rbx+1]; bManualReset
0x180021788  xor     ecx, ecx; lpEventAttributes
0x18002178a  call    cs:__imp_CreateEventW
0x180021790  mov     rbx, rax
0x180021793  mov     rcx, [r14+0C8h]; hObject
0x18002179a  mov     qword ptr [r14+0C8h], 0
0x1800217a5  lea     rax, [rcx-1]
0x1800217a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800217ad  ja      short loc_1800217B5
0x1800217af  call    cs:__imp_CloseHandle
0x1800217b5  mov     [r14+0C8h], rbx
0x1800217bc  test    rbx, rbx
0x1800217bf  jz      short loc_1800217CB
0x1800217c1  mov     rcx, rbx; hEvent
0x1800217c4  call    cs:__imp_ResetEvent
0x1800217ca  nop
0x1800217cb  test    rdi, rdi
0x1800217ce  jz      short loc_1800217D9
0x1800217d0  mov     rcx, rdi; lpCriticalSection
0x1800217d3  call    cs:__imp_LeaveCriticalSection
0x1800217d9  test    r15b, r15b
0x1800217dc  jz      short loc_180021841
0x1800217de  mov     rax, [r14]
0x1800217e1  mov     rcx, r14
0x1800217e4  mov     rax, [rax+10h]
0x1800217e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217ed  nop
0x1800217ee  jmp     short loc_1800217FA
0x1800217f0  mov     r14, [rsp+58h+arg_0]
0x1800217f5  mov     r12, [rsp+58h+arg_18]
0x1800217fa  mov     byte ptr [r12], 0
0x1800217ff  mov     dword ptr [r14+0E0h], 8000FFFFh
0x18002180a  mov     rcx, [r14+0D8h]
0x180021811  test    rcx, rcx
0x180021814  jz      short loc_180021827
0x180021816  call    cs:__imp_CoDecrementMTAUsage
0x18002181c  mov     qword ptr [r14+0D8h], 0
0x180021827  mov     byte ptr [r14+0D0h], 0
0x18002182f  mov     rcx, [r14+0C8h]; hEvent
0x180021836  test    rcx, rcx
0x180021839  jz      short loc_180021841
0x18002183b  call    cs:__imp_SetEvent
0x180021841  mov     r8b, 3
0x180021844  mov     dl, 1
0x180021846  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002184d  add     rsp, 30h
0x180021851  pop     r15
0x180021853  pop     r14
0x180021855  pop     r12
0x180021857  pop     rdi
0x180021858  pop     rbx
0x180021859  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002185e  mov     rcx, [rcx+8]
0x180021862  jmp     loc_180021693
```
