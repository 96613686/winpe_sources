# CpuManager::RegisterProcess(void *,ProcessRegistrationToken__ * *)

- ea: `0x140076390`
- end: `0x140076512`
- name: `?RegisterProcess@CpuManager@@UEAAJPEAXPEAPEAUProcessRegistrationToken__@@@Z`
- size: `386`
- prototype: `int(CpuManager *__hidden this, void *, struct ProcessRegistrationToken__ **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140075684`
- `0x140076390`
- `0x140076c98`
- `0x140076d70`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400764fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400764fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400763d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400763d2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400763ba`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400763ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CpuManager::RegisterProcess(CpuManager *this, void *a2, struct ProcessRegistrationToken__ **a3)
{
  struct ProcessRegistrationToken__ **v3; // r12
  void *v4; // r13
  CpuManager *v5; // rsi
  DWORD ProcessId; // ebx
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
  ProcessId = GetProcessId(a2);
  v15 = ProcessId;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 16);
  v18 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 16));
  v20 = (char *)v5 + 16;
  v8 = (*(__int64 (__fastcall **)(CpuManager *))(*(_QWORD *)v5 + 128LL))(v5);
  if ( v8 < 0 )
    goto LABEL_12;
  v16 = 0;
  v9 = (char *)v5 + 56;
  v17 = (char *)v5 + 56;
  v14 = 0;
  v25 = 0;
  Node = ATL::CAtlMap<unsigned long,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::GetNode(
           (int)v5 + 56,
           ProcessId,
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
            (char *)v5 + 56,
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
  v8 = (*(__int64 (__fastcall **)(CpuManager *, void *, __int64))(*(_QWORD *)v5 + 80LL))(v5, v4, v11 + 16);
  if ( v8 >= 0 )
  {
LABEL_11:
    *v3 = (struct ProcessRegistrationToken__ *)v11;
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
0x140076390  mov     [rsp+arg_10], r8
0x140076395  mov     [rsp+arg_8], rdx
0x14007639a  mov     [rsp+arg_0], rcx
0x14007639f  push    rbx
0x1400763a0  push    rsi
0x1400763a1  push    rdi
0x1400763a2  push    r12
0x1400763a4  push    r13
0x1400763a6  push    r14
0x1400763a8  push    r15
0x1400763aa  sub     rsp, 70h
0x1400763ae  mov     r12, r8
0x1400763b1  mov     r13, rdx
0x1400763b4  mov     rsi, rcx
0x1400763b7  mov     rcx, rdx; Process
0x1400763ba  call    cs:__imp_GetProcessId
0x1400763c0  mov     ebx, eax
0x1400763c2  mov     [rsp+0A8h+var_74], eax
0x1400763c6  lea     r14, [rsi+10h]
0x1400763ca  mov     [rsp+0A8h+var_60], r14
0x1400763cf  mov     rcx, r14; lpCriticalSection
0x1400763d2  call    cs:__imp_EnterCriticalSection
0x1400763d8  mov     [rsp+0A8h+var_48], r14
0x1400763dd  mov     rax, [rsi]
0x1400763e0  mov     rcx, rsi
0x1400763e3  mov     rax, [rax+80h]
0x1400763ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400763ef  mov     edi, eax
0x1400763f1  test    eax, eax
0x1400763f3  js      loc_1400764F2
0x1400763f9  mov     [rsp+0A8h+var_70], 0
0x140076402  lea     r15, [rsi+38h]
0x140076406  mov     [rsp+0A8h+var_68], r15
0x14007640b  mov     [rsp+0A8h+var_78], 0
0x140076413  mov     [rsp+0A8h+arg_18], 0
0x14007641e  lea     rax, [rsp+0A8h+var_58]
0x140076423  mov     [rsp+0A8h+var_88], rax
0x140076428  lea     r9, [rsp+0A8h+arg_18]
0x140076430  lea     r8, [rsp+0A8h+var_78]
0x140076435  mov     edx, ebx
0x140076437  mov     rcx, r15
0x14007643a  call    ?GetNode@?$CAtlMap@KUListValue@HandleRegistrations@CpuManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UListValue@HandleRegistrations@CpuManager@@@5@@ATL@@AEBAPEAVCNode@12@KAEAI0AEAPEAV312@@Z; ATL::CAtlMap<ulong,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::GetNode(ulong,uint &,uint &,ATL::CAtlMap<ulong,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::CNode * &)
0x14007643f  mov     rbx, rax
0x140076442  test    rax, rax
0x140076445  jnz     loc_1400764E8
0x14007644b  xorps   xmm0, xmm0
0x14007644e  movups  [rsp+0A8h+var_58], xmm0
0x140076453  mov     dword ptr [rsp+0A8h+var_58], 1
0x14007645b  lea     r8, [rsp+0A8h+var_58]
0x140076460  mov     edx, [rsp+0A8h+var_74]
0x140076464  mov     rcx, r15
0x140076467  call    ?SetAt@?$CAtlMap@KUListValue@HandleRegistrations@CpuManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UListValue@HandleRegistrations@CpuManager@@@5@@ATL@@QEAAPEAU__POSITION@@KAEBUListValue@HandleRegistrations@CpuManager@@@Z; ATL::CAtlMap<ulong,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::SetAt(ulong,CpuManager::HandleRegistrations::ListValue const &)
0x14007646c  mov     rbx, rax
0x14007646f  mov     [rsp+0A8h+var_70], rax
0x140076474  jmp     short loc_1400764A8
0x140076476  mov     edi, [rsp+0A8h+arg_18]
0x14007647d  mov     rsi, [rsp+0A8h+arg_0]
0x140076485  mov     rbx, [rsp+0A8h+var_70]
0x14007648a  mov     r14, [rsp+0A8h+var_60]
0x14007648f  mov     r15, [rsp+0A8h+var_68]
0x140076494  test    edi, edi
0x140076496  js      short loc_1400764C4
0x140076498  mov     r12, [rsp+0A8h+arg_10]
0x1400764a0  mov     r13, [rsp+0A8h+arg_8]
0x1400764a8  mov     rax, [rsi]
0x1400764ab  lea     r8, [rbx+10h]
0x1400764af  mov     rdx, r13
0x1400764b2  mov     rcx, rsi
0x1400764b5  mov     rax, [rax+50h]
0x1400764b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400764be  mov     edi, eax
0x1400764c0  test    eax, eax
0x1400764c2  jns     short loc_1400764EC
0x1400764c4  test    rbx, rbx
0x1400764c7  jz      short loc_1400764D4
0x1400764c9  mov     rdx, rbx
0x1400764cc  mov     rcx, r15
0x1400764cf  call    ?RemoveAtPos@?$CAtlMap@KUListValue@HandleRegistrations@CpuManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@UListValue@HandleRegistrations@CpuManager@@@5@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,CpuManager::HandleRegistrations::ListValue,ATL::CElementTraits<ulong>,ATL::CElementTraits<CpuManager::HandleRegistrations::ListValue>>::RemoveAtPos(__POSITION *)
0x1400764d4  mov     rax, [rsi]
0x1400764d7  mov     rcx, rsi
0x1400764da  mov     rax, [rax+88h]
0x1400764e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400764e6  jmp     short loc_1400764F2
0x1400764e8  lock inc dword ptr [rax+8]
0x1400764ec  mov     [r12], rbx
0x1400764f0  xor     edi, edi
0x1400764f2  test    r14, r14
0x1400764f5  jz      short loc_140076500
0x1400764f7  mov     rcx, r14; lpCriticalSection
0x1400764fa  call    cs:__imp_LeaveCriticalSection
0x140076500  mov     eax, edi
0x140076502  add     rsp, 70h
0x140076506  pop     r15
0x140076508  pop     r14
0x14007650a  pop     r13
0x14007650c  pop     r12
0x14007650e  pop     rdi
0x14007650f  pop     rsi
0x140076510  pop     rbx
0x140076511  retn
```
