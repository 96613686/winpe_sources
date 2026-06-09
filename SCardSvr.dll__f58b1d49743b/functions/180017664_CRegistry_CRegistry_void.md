# CRegistry::~CRegistry(void)

- ea: `0x180017664`
- end: `0x1800176a1`
- name: `??1CRegistry@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800174e8`
- `0x18002f80c`
- `0x180031df0`
- `0x1800324dc`
- `0x180034464`
- `0x18003468b`
- `0x180034deb`
- `0x180036342`
- `0x18003679c`
- `0x1800367ae`

## callees

- `0x180017664`
- `0x180017730`
- `0x180023168`

## pseudocode

```c
void __fastcall CRegistry::~CRegistry(CRegistry *this)
{
  void *v2; // rcx

  CRegistry::Close(this);
  v2 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 2) = &CBuffer::`vftable';
  if ( v2 )
    operator delete[](v2);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x180017664  push    rbx
0x180017666  sub     rsp, 20h
0x18001766a  mov     rbx, rcx
0x18001766d  call    ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x180017672  mov     rcx, [rbx+18h]; Block
0x180017676  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001767d  mov     [rbx+10h], rax
0x180017681  test    rcx, rcx
0x180017684  jz      short loc_18001768B
0x180017686  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001768b  mov     qword ptr [rbx+18h], 0
0x180017693  mov     qword ptr [rbx+20h], 0
0x18001769b  add     rsp, 20h
0x18001769f  pop     rbx
0x1800176a0  retn
```
