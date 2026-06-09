# VfsCtxTableElementLookup

- ea: `0x14000559c`
- end: `0x14000566e`
- name: `VfsCtxTableElementLookup`
- size: `210`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, PVOID Buffer)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140005674`
- `0x140009218`
- `0x140009298`
- `0x140009d44`

## callees

- `0x14000559c`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14000564e`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000564e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400055bf`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400055bf`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400055eb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400055eb`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400055fd`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400055fd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005634`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005634`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005628`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005628`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400055da`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400055da`

## pseudocode

```c
volatile signed __int32 *__fastcall VfsCtxTableElementLookup(PRTL_AVL_TABLE Table, PVOID Buffer)
{
  struct _ERESOURCE *RightChild; // rbx
  volatile signed __int32 *v6; // rax
  volatile signed __int32 *v7; // rbx

  if ( (*(_DWORD *)&Table[1].BalancedRoot.Balance & 1) != 0
    && !ExAcquireRundownProtection((PEX_RUNDOWN_REF)&Table[1].BalancedRoot.LeftChild) )
  {
    return 0;
  }
  RightChild = (struct _ERESOURCE *)Table[1].BalancedRoot.RightChild;
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(RightChild, 1u);
  v6 = (volatile signed __int32 *)RtlLookupElementGenericTableAvl(Table, Buffer);
  v7 = v6;
  if ( v6 )
  {
    if ( *(_DWORD *)&Table[1].BalancedRoot.Reserved[3] )
      _InterlockedIncrement(v6 + 20);
    else
      _InterlockedIncrement(v6 + 8);
  }
  ExReleaseResourceLite((PERESOURCE)Table[1].BalancedRoot.RightChild);
  KeLeaveCriticalRegion();
  if ( (*(_DWORD *)&Table[1].BalancedRoot.Balance & 1) != 0 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)&Table[1].BalancedRoot.LeftChild);
  return v7;
}

```

## disassembly

```asm
0x14000559c  mov     [rsp+arg_0], rbx
0x1400055a1  mov     [rsp+arg_8], rsi
0x1400055a6  push    rdi
0x1400055a7  sub     rsp, 20h
0x1400055ab  mov     eax, [rcx+80h]
0x1400055b1  mov     rsi, rdx
0x1400055b4  mov     rdi, rcx
0x1400055b7  test    al, 1
0x1400055b9  jz      short loc_1400055D6
0x1400055bb  add     rcx, 70h ; 'p'; RunRef
0x1400055bf  call    cs:__imp_ExAcquireRundownProtection
0x1400055c6  nop     dword ptr [rax+rax+00h]
0x1400055cb  test    al, al
0x1400055cd  jnz     short loc_1400055D6
0x1400055cf  xor     eax, eax
0x1400055d1  jmp     loc_14000565D
0x1400055d6  mov     rbx, [rdi+78h]
0x1400055da  call    cs:__imp_KeEnterCriticalRegion
0x1400055e1  nop     dword ptr [rax+rax+00h]
0x1400055e6  mov     dl, 1; Wait
0x1400055e8  mov     rcx, rbx; Resource
0x1400055eb  call    cs:__imp_ExAcquireResourceSharedLite
0x1400055f2  nop     dword ptr [rax+rax+00h]
0x1400055f7  mov     rdx, rsi; Buffer
0x1400055fa  mov     rcx, rdi; Table
0x1400055fd  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140005604  nop     dword ptr [rax+rax+00h]
0x140005609  mov     rbx, rax
0x14000560c  test    rax, rax
0x14000560f  jz      short loc_140005624
0x140005611  cmp     dword ptr [rdi+84h], 0
0x140005618  jnz     short loc_140005620
0x14000561a  lock inc dword ptr [rax+20h]
0x14000561e  jmp     short loc_140005624
0x140005620  lock inc dword ptr [rax+50h]
0x140005624  mov     rcx, [rdi+78h]; Resource
0x140005628  call    cs:__imp_ExReleaseResourceLite
0x14000562f  nop     dword ptr [rax+rax+00h]
0x140005634  call    cs:__imp_KeLeaveCriticalRegion
0x14000563b  nop     dword ptr [rax+rax+00h]
0x140005640  mov     eax, [rdi+80h]
0x140005646  test    al, 1
0x140005648  jz      short loc_14000565A
0x14000564a  lea     rcx, [rdi+70h]; RunRef
0x14000564e  call    cs:__imp_ExReleaseRundownProtection
0x140005655  nop     dword ptr [rax+rax+00h]
0x14000565a  mov     rax, rbx
0x14000565d  mov     rbx, [rsp+28h+arg_0]
0x140005662  mov     rsi, [rsp+28h+arg_8]
0x140005667  add     rsp, 20h
0x14000566b  pop     rdi
0x14000566c  retn
```
