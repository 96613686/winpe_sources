# Common::StringBuffer::~StringBuffer(void)

- ea: `0x14000859c`
- end: `0x1400085b3`
- name: `??1StringBuffer@Common@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Common::StringBuffer *this, unsigned __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400084a0`
- `0x140008524`
- `0x140008bc4`
- `0x140008ec8`
- `0x140009310`
- `0x14000ec26`
- `0x14000ec38`
- `0x14000ec5c`
- `0x14000ec6e`
- `0x14000ec80`
- `0x14000eed0`

## callees

- `0x140003644`
- `0x14000859c`

## pseudocode

```c
void __fastcall Common::StringBuffer::~StringBuffer(Common::StringBuffer *this, unsigned __int64 a2)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x14000859c  sub     rsp, 28h
0x1400085a0  mov     rcx, [rcx+8]; void *
0x1400085a4  test    rcx, rcx
0x1400085a7  jz      short loc_1400085AE
0x1400085a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400085ae  add     rsp, 28h
0x1400085b2  retn
```
