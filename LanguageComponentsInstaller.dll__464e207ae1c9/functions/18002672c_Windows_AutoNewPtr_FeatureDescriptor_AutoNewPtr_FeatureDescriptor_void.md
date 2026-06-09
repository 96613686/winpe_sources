# Windows::AutoNewPtr<FeatureDescriptor>::~AutoNewPtr<FeatureDescriptor>(void)

- ea: `0x18002672c`
- end: `0x180026751`
- name: `??1?$AutoNewPtr@UFeatureDescriptor@@@Windows@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002977e`

## callees

- `0x180003a34`
- `0x18002672c`

## pseudocode

```c
void __fastcall Windows::AutoNewPtr<FeatureDescriptor>::~AutoNewPtr<FeatureDescriptor>(void **a1)
{
  void *v1; // rax

  v1 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18002672c  sub     rsp, 28h
0x180026730  mov     rax, [rcx]
0x180026733  test    rax, rax
0x180026736  jz      short loc_18002674C
0x180026738  mov     qword ptr [rcx], 0
0x18002673f  mov     edx, 18h
0x180026744  mov     rcx, rax; Block
0x180026747  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002674c  add     rsp, 28h
0x180026750  retn
```
