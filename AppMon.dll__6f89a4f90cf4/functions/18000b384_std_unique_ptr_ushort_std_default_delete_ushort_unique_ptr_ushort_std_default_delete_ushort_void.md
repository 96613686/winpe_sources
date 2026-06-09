# std::unique_ptr<ushort,std::default_delete<ushort>>::~unique_ptr<ushort,std::default_delete<ushort>>(void)

- ea: `0x18000b384`
- end: `0x18000b39f`
- name: `??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bafc`
- `0x18000f98a`
- `0x18000f99c`
- `0x18000f9ae`
- `0x18000f9c0`
- `0x18000f9d2`
- `0x18000f9e4`

## callees

- `0x1800019f0`
- `0x18000b384`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000b384  sub     rsp, 28h
0x18000b388  mov     rcx, [rcx]; void *
0x18000b38b  test    rcx, rcx
0x18000b38e  jz      short loc_18000B39A
0x18000b390  mov     edx, 2; unsigned __int64
0x18000b395  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b39a  add     rsp, 28h
0x18000b39e  retn
```
