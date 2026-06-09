# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140003d98`
- end: `0x140003def`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003d40`
- `0x140005978`
- `0x140005d40`

## callees

- `0x140003d98`
- `0x14000469c`

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
0x140003d98  push    rbx
0x140003d9a  sub     rsp, 20h
0x140003d9e  mov     rbx, rcx
0x140003da1  mov     rcx, [rcx+0B0h]; this
0x140003da8  mov     qword ptr [rbx+0B0h], 0
0x140003db3  test    rcx, rcx
0x140003db6  jz      short loc_140003DBD
0x140003db8  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140003dbd  mov     rcx, [rbx+70h]; this
0x140003dc1  mov     qword ptr [rbx+70h], 0
0x140003dc9  test    rcx, rcx
0x140003dcc  jz      short loc_140003DD3
0x140003dce  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140003dd3  mov     rcx, [rbx+30h]; this
0x140003dd7  mov     qword ptr [rbx+30h], 0
0x140003ddf  test    rcx, rcx
0x140003de2  jz      short loc_140003DE9
0x140003de4  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140003de9  add     rsp, 20h
0x140003ded  pop     rbx
0x140003dee  retn
```
