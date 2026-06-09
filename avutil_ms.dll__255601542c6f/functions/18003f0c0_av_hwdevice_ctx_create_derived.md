# av_hwdevice_ctx_create_derived

- ea: `0x18003f0c0`
- end: `0x18003f0d6`
- name: `av_hwdevice_ctx_create_derived`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003f0e0`

## pseudocode

```c
__int64 __fastcall av_hwdevice_ctx_create_derived(__int64 *a1, int a2, __int64 a3)
{
  return av_hwdevice_ctx_create_derived_opts(a1, a2, a3);
}

```

## disassembly

```asm
0x18003f0c0  sub     rsp, 38h
0x18003f0c4  mov     [rsp+38h+var_18], r9d
0x18003f0c9  xor     r9d, r9d
0x18003f0cc  call    av_hwdevice_ctx_create_derived_opts
0x18003f0d1  add     rsp, 38h
0x18003f0d5  retn
```
