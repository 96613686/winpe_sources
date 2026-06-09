# IIsSchemaClass::~IIsSchemaClass(void)

- ea: `0x180019bec`
- end: `0x180019c30`
- name: `??1IIsSchemaClass@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(IIsSchemaClass *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001a0a0`

## callees

- `0x1800010f0`
- `0x180019bec`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsMem` at `0x180019c06`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180019c15`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180019c24`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180019c06`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180019c15`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180019c24`

## pseudocode

```c
void __fastcall IIsSchemaClass::~IIsSchemaClass(void **this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  operator delete(*this);
  v2 = this[9];
  if ( v2 )
    FreeADsMem(v2);
  v3 = this[7];
  if ( v3 )
    FreeADsMem(v3);
  v4 = this[6];
  if ( v4 )
    FreeADsMem(v4);
}

```

## disassembly

```asm
0x180019bec  push    rbx
0x180019bee  sub     rsp, 20h
0x180019bf2  mov     rbx, rcx
0x180019bf5  mov     rcx, [rcx]; Block
0x180019bf8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019bfd  mov     rcx, [rbx+48h]; pMem
0x180019c01  test    rcx, rcx
0x180019c04  jz      short loc_180019C0C
0x180019c06  call    cs:__imp_FreeADsMem
0x180019c0c  mov     rcx, [rbx+38h]; pMem
0x180019c10  test    rcx, rcx
0x180019c13  jz      short loc_180019C1B
0x180019c15  call    cs:__imp_FreeADsMem
0x180019c1b  mov     rcx, [rbx+30h]; pMem
0x180019c1f  test    rcx, rcx
0x180019c22  jz      short loc_180019C2A
0x180019c24  call    cs:__imp_FreeADsMem
0x180019c2a  add     rsp, 20h
0x180019c2e  pop     rbx
0x180019c2f  retn
```
