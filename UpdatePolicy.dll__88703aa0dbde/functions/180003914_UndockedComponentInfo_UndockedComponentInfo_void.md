# UndockedComponentInfo::~UndockedComponentInfo(void)

- ea: `0x180003914`
- end: `0x18000397b`
- name: `??1UndockedComponentInfo@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(UndockedComponentInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003128`

## callees

- `0x180003914`
- `0x18000a150`

## pseudocode

```c
void __fastcall UndockedComponentInfo::~UndockedComponentInfo(UndockedComponentInfo *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    SusFree(v2);
    *((_QWORD *)this + 4) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    SusFree(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    SusFree(v4);
    *((_QWORD *)this + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    SusFree(v5);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180003914  push    rbx
0x180003916  sub     rsp, 20h
0x18000391a  mov     rbx, rcx
0x18000391d  mov     rcx, [rcx+20h]; lpMem
0x180003921  test    rcx, rcx
0x180003924  jz      short loc_180003933
0x180003926  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000392b  mov     qword ptr [rbx+20h], 0
0x180003933  mov     rcx, [rbx+18h]; lpMem
0x180003937  test    rcx, rcx
0x18000393a  jz      short loc_180003949
0x18000393c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180003941  mov     qword ptr [rbx+18h], 0
0x180003949  mov     rcx, [rbx+10h]; lpMem
0x18000394d  test    rcx, rcx
0x180003950  jz      short loc_18000395F
0x180003952  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180003957  mov     qword ptr [rbx+10h], 0
0x18000395f  mov     rcx, [rbx+8]; lpMem
0x180003963  test    rcx, rcx
0x180003966  jz      short loc_180003975
0x180003968  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000396d  mov     qword ptr [rbx+8], 0
0x180003975  add     rsp, 20h
0x180003979  pop     rbx
0x18000397a  retn
```
