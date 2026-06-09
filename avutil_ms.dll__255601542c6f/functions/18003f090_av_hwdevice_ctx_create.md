# av_hwdevice_ctx_create

- ea: `0x18003f090`
- end: `0x18003f0be`
- name: `av_hwdevice_ctx_create`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002f210`

## pseudocode

```c
__int64 __fastcall av_hwdevice_ctx_create(_QWORD *a1)
{
  __int64 result; // rax
  _QWORD v3[3]; // [rsp+20h] [rbp-18h] BYREF

  v3[0] = 0;
  av_buffer_unref(v3);
  result = 4294967284LL;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18003f090  push    rbx
0x18003f092  sub     rsp, 30h
0x18003f096  mov     rbx, rcx
0x18003f099  mov     [rsp+38h+var_18], 0
0x18003f0a2  lea     rcx, [rsp+38h+var_18]
0x18003f0a7  call    av_buffer_unref
0x18003f0ac  mov     eax, 0FFFFFFF4h
0x18003f0b1  mov     qword ptr [rbx], 0
0x18003f0b8  add     rsp, 30h
0x18003f0bc  pop     rbx
0x18003f0bd  retn
```
