# CsqRemoveIo(_FLT_CALLBACK_DATA_QUEUE *,_FLT_CALLBACK_DATA *)

- ea: `0x140002070`
- end: `0x1400020c2`
- name: `?CsqRemoveIo@@YAXPEAU_FLT_CALLBACK_DATA_QUEUE@@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `82`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002070`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140002098`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140002098`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400020af`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400020af`

## pseudocode

```c
void __fastcall CsqRemoveIo(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)
{
  PVOID v2; // r8
  __int64 v3; // rbx
  PVOID v4; // rax

  v2 = Cbd->QueueContext[0];
  if ( v2 )
  {
    v3 = *(_QWORD *)&Cbdq[1].Csq.Type;
    **(_QWORD **)(v3 + 112) = v2;
    if ( *(_QWORD *)v3 )
    {
      v4 = RtlLookupElementGenericTableAvl(*(PRTL_AVL_TABLE *)v3, (PVOID)(v3 + 112));
      if ( v4 )
        RtlDeleteElementGenericTableAvl(*(PRTL_AVL_TABLE *)v3, v4);
    }
  }
}

```

## disassembly

```asm
0x140002070  push    rbx
0x140002072  sub     rsp, 20h
0x140002076  mov     r8, [rdx+40h]
0x14000207a  test    r8, r8
0x14000207d  jz      short loc_1400020BB
0x14000207f  mov     rbx, [rcx+80h]
0x140002086  lea     rdx, [rbx+70h]; Buffer
0x14000208a  mov     rax, [rdx]
0x14000208d  mov     [rax], r8
0x140002090  mov     rcx, [rbx]; Table
0x140002093  test    rcx, rcx
0x140002096  jz      short loc_1400020BB
0x140002098  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14000209f  nop     dword ptr [rax+rax+00h]
0x1400020a4  test    rax, rax
0x1400020a7  jz      short loc_1400020BB
0x1400020a9  mov     rcx, [rbx]; Table
0x1400020ac  mov     rdx, rax; Buffer
0x1400020af  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400020b6  nop     dword ptr [rax+rax+00h]
0x1400020bb  add     rsp, 20h
0x1400020bf  pop     rbx
0x1400020c0  retn
```
