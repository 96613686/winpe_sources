# std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiServer,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiServer>>::~unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiServer,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiServer>>(void)

- ea: `0x14000f9e0`
- end: `0x14000f9fb`
- name: `??1?$unique_ptr@VUtcDecoderHostApiServer@Diagnostics@Microsoft@@U?$default_delete@VUtcDecoderHostApiServer@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001780d`

## callees

- `0x1400088f4`
- `0x14000f9e0`

## pseudocode

```c
void __fastcall std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiServer>::~unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiServer>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1, 1u);
}

```

## disassembly

```asm
0x14000f9e0  sub     rsp, 28h
0x14000f9e4  mov     rcx, [rcx]; void *
0x14000f9e7  test    rcx, rcx
0x14000f9ea  jz      short loc_14000F9F6
0x14000f9ec  mov     edx, 1; unsigned __int64
0x14000f9f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f9f6  add     rsp, 28h
0x14000f9fa  retn
```
