# CpuManager::RegisterThread(void *,ThreadRegistrationToken__ * *)

- ea: `0x140076520`
- end: `0x1400766a5`
- name: `?RegisterThread@CpuManager@@UEAAJPEAXPEAPEAUThreadRegistrationToken__@@@Z`
- size: `389`
- prototype: `int(CpuManager *__hidden this, void *, struct ThreadRegistrationToken__ **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140075684`
- `0x140076520`
- `0x140076c98`
- `0x140076d70`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007668d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007668d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140076562`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140076562`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x14007654a`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x14007654a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CpuManager::RegisterThread(CpuManager *this, void *a2, struct ThreadRegistrationToken__ **a3)
{
  struct ThreadRegistrationToken__ **v3; // r12
  void *v4; // r13
  CpuManager *v5; // rsi
  DWORD ThreadId; // ebx
  struct _RTL_CRITICAL_SECTION *v7; // r14
  int v8; // edi
  char *v9; // r15
  __int64 Node; // rax
  __int64 v11; // rbx
  ATL::CAtlException *v13; // rbx
  int v14; // [rsp+30h] [rbp-78h] BYREF
  DWORD v15; // [rsp+34h] [rbp-74h]
  __int64 v16; // [rsp+38h] [rbp-70h]
  char *v17; // [rsp+40h] [rbp-68h]
  struct _RTL_CRITICAL_SECTION *v18; // [rsp+48h] [rbp-60h]
  __int128 v19; // [rsp+50h] [rbp-58h] BYREF
  char *v20; // [rsp+60h] [rbp-48h]
  ATL::CAtlException *v21; // [rsp+68h] [rbp-40h] BYREF
  int v25; // [rsp+C8h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = this;
  ThreadId = GetThreadId(a2);
  v15 = ThreadId;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 16);
  v18 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 16));
  v20 = (char *)v5 + 16;
  v8 = (*(__int64 (__fastcall **)(CpuManager *))(*(_QWORD *)v5 + 128LL))(v5);
  if ( v8 < 0 )
    goto LABEL_12;
  v16 = 0;
  v9 = (char *)v5 + 128;
  v17 = (char *)v5 + 128;
  v14 = 0;
  v25 = 0;
  Node = ATL::CAtlMap<unsigned long,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::GetNode(
           (int)v5 + 128,
           ThreadId,
           (unsigned int)&v14,
           (unsigned int)&v25,
           (__int64)&v19);
  v11 = Node;
  if ( Node )
  {
    _InterlockedIncrement((volatile signed __int32 *)(Node + 8));
    goto LABEL_11;
  }
  try
  {
    v19 = 0;
    LODWORD(v19) = 1;
    v11 = ATL::CAtlMap<unsigned long,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::SetAt(
            (char *)v5 + 128,
            v15,
            &v19);
    v16 = v11;
  }
  catch ( ATL::CAtlException *v21 )
  {
    v13 = v21;
    if ( *(_DWORD *)v21 == -1073741571 )
      _o__resetstkoflw();
    v25 = *(_DWORD *)v13;
    v8 = v25;
    v5 = this;
    v11 = v16;
    v7 = v18;
    v9 = v17;
    if ( v25 < 0 )
      goto LABEL_7;
    v3 = a3;
    v4 = a2;
  }
  v8 = (*(__int64 (__fastcall **)(CpuManager *, void *, __int64))(*(_QWORD *)v5 + 96LL))(v5, v4, v11 + 16);
  if ( v8 >= 0 )
  {
LABEL_11:
    *v3 = (struct ThreadRegistrationToken__ *)v11;
    v8 = 0;
    goto LABEL_12;
  }
LABEL_7:
  if ( v11 )
    ATL::CAtlMap<unsigned long,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::RemoveAtPos(
      v9,
      v11);
  (*(void (__fastcall **)(CpuManager *))(*(_QWORD *)v5 + 136LL))(v5);
LABEL_12:
  if ( v7 )
    LeaveCriticalSection(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140076520  mov     [rsp+arg_10], r8
0x140076525  mov     [rsp+arg_8], rdx
0x14007652a  mov     [rsp+arg_0], rcx
0x14007652f  push    rbx
0x140076530  push    rsi
0x140076531  push    rdi
0x140076532  push    r12
0x140076534  push    r13
0x140076536  push    r14
0x140076538  push    r15
0x14007653a  sub     rsp, 70h
0x14007653e  mov     r12, r8
0x140076541  mov     r13, rdx
0x140076544  mov     rsi, rcx
0x140076547  mov     rcx, rdx; Thread
0x14007654a  call    cs:__imp_GetThreadId
0x140076550  mov     ebx, eax
0x140076552  mov     [rsp+0A8h+var_74], eax
0x140076556  lea     r14, [rsi+10h]
0x14007655a  mov     [rsp+0A8h+var_60], r14
0x14007655f  mov     rcx, r14; lpCriticalSection
0x140076562  call    cs:__imp_EnterCriticalSection
0x140076568  mov     [rsp+0A8h+var_48], r14
0x14007656d  mov     rax, [rsi]
0x140076570  mov     rcx, rsi
0x140076573  mov     rax, [rax+80h]
0x14007657a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007657f  mov     edi, eax
0x140076581  test    eax, eax
0x140076583  js      loc_140076685
0x140076589  mov     [rsp+0A8h+var_70], 0
0x140076592  lea     r15, [rsi+80h]
0x140076599  mov     [rsp+0A8h+var_68], r15
0x14007659e  mov     [rsp+0A8h+var_78], 0
0x1400765a6  mov     [rsp+0A8h+arg_18], 0
0x1400765b1  lea     rax, [rsp+0A8h+var_58]
0x1400765b6  mov     [rsp+0A8h+var_88], rax
0x1400765bb  lea     r9, [rsp+0A8h+arg_18]
0x1400765c3  lea     r8, [rsp+0A8h+var_78]
0x1400765c8  mov     edx, ebx
0x1400765ca  mov     rcx, r15
0x1400765cd  call    ?GetNode@?$CAtlMap@KUListValue@HandleRegistrations@CpuManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UListValue@HandleRegistrations@CpuManager@@@5@@ATL@@AEBAPEAVCNode@12@KAEAI0AEAPEAV312@@Z; ATL::CAtlMap<ulong,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::GetNode(ulong,uint &,uint &,ATL::CAtlMap<ulong,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::CNode * &)
0x1400765d2  mov     rbx, rax
0x1400765d5  test    rax, rax
0x1400765d8  jnz     loc_14007667B
0x1400765de  xorps   xmm0, xmm0
0x1400765e1  movups  [rsp+0A8h+var_58], xmm0
0x1400765e6  mov     dword ptr [rsp+0A8h+var_58], 1
0x1400765ee  lea     r8, [rsp+0A8h+var_58]
0x1400765f3  mov     edx, [rsp+0A8h+var_74]
0x1400765f7  mov     rcx, r15
0x1400765fa  call    ?SetAt@?$CAtlMap@KUListValue@HandleRegistrations@CpuManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UListValue@HandleRegistrations@CpuManager@@@5@@ATL@@QEAAPEAU__POSITION@@KAEBUListValue@HandleRegistrations@CpuManager@@@Z; ATL::CAtlMap<ulong,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::SetAt(ulong,CpuManager::HandleRegistrations::ListValue const &)
0x1400765ff  mov     rbx, rax
0x140076602  mov     [rsp+0A8h+var_70], rax
0x140076607  jmp     short loc_14007663B
0x140076609  mov     edi, [rsp+0A8h+arg_18]
0x140076610  mov     rsi, [rsp+0A8h+arg_0]
0x140076618  mov     rbx, [rsp+0A8h+var_70]
0x14007661d  mov     r14, [rsp+0A8h+var_60]
0x140076622  mov     r15, [rsp+0A8h+var_68]
0x140076627  test    edi, edi
0x140076629  js      short loc_140076657
0x14007662b  mov     r12, [rsp+0A8h+arg_10]
0x140076633  mov     r13, [rsp+0A8h+arg_8]
0x14007663b  mov     rax, [rsi]
0x14007663e  lea     r8, [rbx+10h]
0x140076642  mov     rdx, r13
0x140076645  mov     rcx, rsi
0x140076648  mov     rax, [rax+60h]
0x14007664c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076651  mov     edi, eax
0x140076653  test    eax, eax
0x140076655  jns     short loc_14007667F
0x140076657  test    rbx, rbx
0x14007665a  jz      short loc_140076667
0x14007665c  mov     rdx, rbx
0x14007665f  mov     rcx, r15
0x140076662  call    ?RemoveAtPos@?$CAtlMap@KUListValue@HandleRegistrations@CpuManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UListValue@HandleRegistrations@CpuManager@@@5@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::RemoveAtPos(__POSITION *)
0x140076667  mov     rax, [rsi]
0x14007666a  mov     rcx, rsi
0x14007666d  mov     rax, [rax+88h]
0x140076674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076679  jmp     short loc_140076685
0x14007667b  lock inc dword ptr [rax+8]
0x14007667f  mov     [r12], rbx
0x140076683  xor     edi, edi
0x140076685  test    r14, r14
0x140076688  jz      short loc_140076693
0x14007668a  mov     rcx, r14; lpCriticalSection
0x14007668d  call    cs:__imp_LeaveCriticalSection
0x140076693  mov     eax, edi
0x140076695  add     rsp, 70h
0x140076699  pop     r15
0x14007669b  pop     r14
0x14007669d  pop     r13
0x14007669f  pop     r12
0x1400766a1  pop     rdi
0x1400766a2  pop     rsi
0x1400766a3  pop     rbx
0x1400766a4  retn
```
