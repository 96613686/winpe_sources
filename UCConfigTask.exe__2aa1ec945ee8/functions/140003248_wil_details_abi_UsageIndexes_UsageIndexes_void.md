# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140003248`
- end: `0x14000329f`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400030b0`
- `0x1400052f4`
- `0x140005898`
- `0x140008890`

## callees

- `0x140003248`
- `0x140003ccc`

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
0x140003248  push    rbx
0x14000324a  sub     rsp, 20h
0x14000324e  mov     rbx, rcx
0x140003251  mov     rcx, [rcx+0B0h]; this
0x140003258  mov     qword ptr [rbx+0B0h], 0
0x140003263  test    rcx, rcx
0x140003266  jz      short loc_14000326D
0x140003268  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000326d  mov     rcx, [rbx+70h]; this
0x140003271  mov     qword ptr [rbx+70h], 0
0x140003279  test    rcx, rcx
0x14000327c  jz      short loc_140003283
0x14000327e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140003283  mov     rcx, [rbx+30h]; this
0x140003287  mov     qword ptr [rbx+30h], 0
0x14000328f  test    rcx, rcx
0x140003292  jz      short loc_140003299
0x140003294  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140003299  add     rsp, 20h
0x14000329d  pop     rbx
0x14000329e  retn
```
