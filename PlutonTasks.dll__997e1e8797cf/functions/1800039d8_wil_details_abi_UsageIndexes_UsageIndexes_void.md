# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800039d8`
- end: `0x180003a2f`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003818`
- `0x180006368`
- `0x180006a18`
- `0x180009888`

## callees

- `0x1800039d8`
- `0x180004bcc`

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
0x1800039d8  push    rbx
0x1800039da  sub     rsp, 20h
0x1800039de  mov     rbx, rcx
0x1800039e1  mov     rcx, [rcx+0B0h]; this
0x1800039e8  mov     qword ptr [rbx+0B0h], 0
0x1800039f3  test    rcx, rcx
0x1800039f6  jz      short loc_1800039FD
0x1800039f8  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800039fd  mov     rcx, [rbx+70h]; this
0x180003a01  mov     qword ptr [rbx+70h], 0
0x180003a09  test    rcx, rcx
0x180003a0c  jz      short loc_180003A13
0x180003a0e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180003a13  mov     rcx, [rbx+30h]; this
0x180003a17  mov     qword ptr [rbx+30h], 0
0x180003a1f  test    rcx, rcx
0x180003a22  jz      short loc_180003A29
0x180003a24  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180003a29  add     rsp, 20h
0x180003a2d  pop     rbx
0x180003a2e  retn
```
