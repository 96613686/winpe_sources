# CDedupOptimizer::CreateWeakReferencesForCandidate(SDirtyRangeCandidate const &)

- ea: `0x1400773b4`
- end: `0x1400774ca`
- name: `?CreateWeakReferencesForCandidate@CDedupOptimizer@@AEAAKAEBUSDirtyRangeCandidate@@@Z`
- size: `278`
- prototype: `unsigned int __fastcall(CDedupOptimizer *__hidden this, const struct SDirtyRangeCandidate *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140073760`

## callees

- `0x1400635dc`
- `0x1400773b4`
- `0x140077eac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077486`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14007746f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14007746f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14007745b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14007745b`

## pseudocode

```c
__int64 __fastcall CDedupOptimizer::CreateWeakReferencesForCandidate(
        CDedupOptimizer *this,
        const struct SDirtyRangeCandidate *a2)
{
  unsigned __int64 v4; // rbx
  __int64 v5; // rbp
  unsigned __int64 i; // rdi
  __int128 v7; // xmm0
  struct _TP_WORK *ThreadpoolWork; // rax
  __int128 v10; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h]
  unsigned __int64 v12; // [rsp+38h] [rbp-30h]
  __int64 v13; // [rsp+40h] [rbp-28h]
  DWORD LastError; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0x1000000;
  v5 = -*((_DWORD *)this + 60) & (*((_QWORD *)a2 + 2) + *((_DWORD *)this + 60) - 1);
  for ( i = *((_QWORD *)a2 + 2) + *((_QWORD *)a2 + 3) - v5; i; i -= v4 )
  {
    if ( i < v4 )
      v4 = i & -*((_DWORD *)this + 60);
    if ( v4 < *((unsigned int *)this + 60) )
      break;
    v7 = *(_OWORD *)a2;
    v11 = v5;
    v12 = v4;
    v13 = 0;
    v10 = v7;
    CDedupOptimizer::EnqueueForWeakRef(this, (const struct SDirtyRangeCandidate *)&v10);
    ThreadpoolWork = CreateThreadpoolWork(
                       CDedupOptimizer::CreateWeakReferenceCallback,
                       this,
                       (PTP_CALLBACK_ENVIRON)((char *)this + 312));
    if ( !ThreadpoolWork )
    {
      LastError = GetLastError();
      DedupUtil::Print<unsigned long &>(6, L"Unable to queue weak ref callback, error = 0x%x\n", &LastError);
      return LastError;
    }
    SubmitThreadpoolWork(ThreadpoolWork);
    v5 += v4;
  }
  return 0;
}

```

## disassembly

```asm
0x1400773b4  mov     [rsp+arg_8], rbx
0x1400773b9  mov     [rsp+arg_10], rbp
0x1400773be  push    rsi
0x1400773bf  push    rdi
0x1400773c0  push    r14
0x1400773c2  sub     rsp, 50h
0x1400773c6  mov     r8d, [rcx+0F0h]
0x1400773cd  mov     r14, rdx
0x1400773d0  mov     rdi, [rdx+18h]
0x1400773d4  mov     rsi, rcx
0x1400773d7  mov     ebx, 1000000h
0x1400773dc  lea     eax, [r8-1]
0x1400773e0  neg     r8d
0x1400773e3  movsxd  rbp, eax
0x1400773e6  add     rbp, [rdx+10h]
0x1400773ea  movsxd  rax, r8d
0x1400773ed  and     rbp, rax
0x1400773f0  sub     rdi, rbp
0x1400773f3  add     rdi, [rdx+10h]
0x1400773f7  test    rdi, rdi
0x1400773fa  jz      loc_1400774B2
0x140077400  cmp     rdi, rbx
0x140077403  jnb     short loc_140077413
0x140077405  mov     eax, [rsi+0F0h]
0x14007740b  neg     eax
0x14007740d  movsxd  rbx, eax
0x140077410  and     rbx, rdi
0x140077413  mov     eax, [rsi+0F0h]
0x140077419  cmp     rbx, rax
0x14007741c  jb      loc_1400774B2
0x140077422  movups  xmm0, xmmword ptr [r14]
0x140077426  xor     eax, eax
0x140077428  mov     [rsp+68h+var_38], rbp
0x14007742d  lea     rdx, [rsp+68h+var_48]; struct SDirtyRangeCandidate *
0x140077432  mov     [rsp+68h+var_30], rbx
0x140077437  mov     rcx, rsi; this
0x14007743a  mov     [rsp+68h+var_28], rax
0x14007743f  movdqu  [rsp+68h+var_48], xmm0
0x140077445  call    ?EnqueueForWeakRef@CDedupOptimizer@@AEAAXAEBUSDirtyRangeCandidate@@@Z; CDedupOptimizer::EnqueueForWeakRef(SDirtyRangeCandidate const &)
0x14007744a  lea     r8, [rsi+138h]; pcbe
0x140077451  mov     rdx, rsi; pv
0x140077454  lea     rcx, ?CreateWeakReferenceCallback@CDedupOptimizer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14007745b  call    cs:__imp_CreateThreadpoolWork
0x140077462  nop     dword ptr [rax+rax+00h]
0x140077467  test    rax, rax
0x14007746a  jz      short loc_140077486
0x14007746c  mov     rcx, rax; pwk
0x14007746f  call    cs:__imp_SubmitThreadpoolWork
0x140077476  nop     dword ptr [rax+rax+00h]
0x14007747b  add     rbp, rbx
0x14007747e  sub     rdi, rbx
0x140077481  jmp     loc_1400773F7
0x140077486  call    cs:__imp_GetLastError
0x14007748d  nop     dword ptr [rax+rax+00h]
0x140077492  lea     r8, [rsp+68h+arg_0]
0x140077497  mov     ecx, 6
0x14007749c  lea     rdx, aUnableToQueueW; "Unable to queue weak ref callback, erro"...
0x1400774a3  mov     [rsp+68h+arg_0], eax
0x1400774a7  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x1400774ac  mov     eax, [rsp+68h+arg_0]
0x1400774b0  jmp     short loc_1400774B4
0x1400774b2  xor     eax, eax
0x1400774b4  lea     r11, [rsp+68h+var_18]
0x1400774b9  mov     rbx, [r11+28h]
0x1400774bd  mov     rbp, [r11+30h]
0x1400774c1  mov     rsp, r11
0x1400774c4  pop     r14
0x1400774c6  pop     rdi
0x1400774c7  pop     rsi
0x1400774c8  retn
```
