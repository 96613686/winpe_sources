# CommonUtil::CAutoUniqueArrayPtr<wchar_t,void>::~CAutoUniqueArrayPtr<wchar_t,void>(void)

- ea: `0x14001d230`
- end: `0x14001d246`
- name: `??1?$CAutoUniqueArrayPtr@_WX@CommonUtil@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400259d0`
- `0x14002619d`
- `0x1400261b5`
- `0x1400261c1`
- `0x1400261cd`
- `0x1400261d9`
- `0x1400261e5`
- `0x140026240`
- `0x1400262cb`
- `0x140026359`
- `0x140026365`
- `0x140026375`
- `0x140026385`

## callees

- `0x140005c40`
- `0x14001d230`

## pseudocode

```c
void __fastcall CommonUtil::CAutoUniqueArrayPtr<wchar_t,void>::~CAutoUniqueArrayPtr<wchar_t,void>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x14001d230  sub     rsp, 28h
0x14001d234  mov     rcx, [rcx]; void *
0x14001d237  test    rcx, rcx
0x14001d23a  jz      short loc_14001D241
0x14001d23c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001d241  add     rsp, 28h
0x14001d245  retn
```
