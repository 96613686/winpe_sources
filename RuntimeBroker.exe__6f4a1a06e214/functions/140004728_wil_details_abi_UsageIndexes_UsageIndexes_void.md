# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140004728`
- end: `0x140004788`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `96`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046c8`
- `0x14000ad30`
- `0x14000c104`

## callees

- `0x140004728`
- `0x1400079c4`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this, void *a2)
{
  wil::details *v3; // rcx
  wil::details *v4; // rcx
  wil::details *v5; // rcx

  v3 = (wil::details *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v3 )
    wil::details::FreeProcessHeap(v3, a2);
  v4 = (wil::details *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
    wil::details::FreeProcessHeap(v4, a2);
  v5 = (wil::details *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v5 )
    wil::details::FreeProcessHeap(v5, a2);
}

```

## disassembly

```asm
0x140004728  push    rbx
0x14000472a  sub     rsp, 20h
0x14000472e  mov     rbx, rcx
0x140004731  mov     rcx, [rcx+0B0h]; this
0x140004738  mov     qword ptr [rbx+0B0h], 0
0x140004743  test    rcx, rcx
0x140004746  jnz     short loc_140004770
0x140004748  mov     rcx, [rbx+70h]; this
0x14000474c  mov     qword ptr [rbx+70h], 0
0x140004754  test    rcx, rcx
0x140004757  jnz     short loc_140004777
0x140004759  mov     rcx, [rbx+30h]; this
0x14000475d  mov     qword ptr [rbx+30h], 0
0x140004765  test    rcx, rcx
0x140004768  jnz     short loc_14000477E
0x14000476a  add     rsp, 20h
0x14000476e  pop     rbx
0x14000476f  retn
0x140004770  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140004775  jmp     short loc_140004748
0x140004777  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000477c  jmp     short loc_140004759
0x14000477e  add     rsp, 20h
0x140004782  pop     rbx
0x140004783  jmp     ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
```
