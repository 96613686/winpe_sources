# CreateColorTransformer(void)

- ea: `0x180014480`
- end: `0x1800144a4`
- name: `?CreateColorTransformer@@YAPEAUIUnknown@@XZ`
- size: `36`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180009590`
- `0x180014480`
- `0x1800215e8`

## pseudocode

```c
struct IUnknown *CreateColorTransformer(void)
{
  struct IUnknown *result; // rax

  result = (struct IUnknown *)operator new(0x130u);
  if ( result )
    return (struct IUnknown *)CIcmColorTransform::CIcmColorTransform((CIcmColorTransform *)result);
  return result;
}

```

## disassembly

```asm
0x180014480  sub     rsp, 28h
0x180014484  mov     ecx, 130h; Size
0x180014489  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001448e  test    rax, rax
0x180014491  jnz     short loc_180014498
0x180014493  add     rsp, 28h
0x180014497  retn
0x180014498  mov     rcx, rax; this
0x18001449b  add     rsp, 28h
0x18001449f  jmp     ??0CIcmColorTransform@@QEAA@XZ; CIcmColorTransform::CIcmColorTransform(void)
```
