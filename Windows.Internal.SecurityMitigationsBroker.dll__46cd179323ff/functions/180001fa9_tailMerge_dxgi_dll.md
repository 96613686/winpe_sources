# __tailMerge_dxgi_dll

- ea: `0x180001fa9`
- end: `0x180002022`
- name: `__tailMerge_dxgi_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002028`

## callees

- `0x180001fa9`
- `0x180006880`

## pseudocode

```c
__int64 __fastcall _tailMerge_dxgi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dxgi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001fa9  mov     [rsp+arg_0], rcx
0x180001fae  mov     [rsp+arg_8], rdx
0x180001fb3  mov     [rsp+arg_10], r8
0x180001fb8  mov     [rsp+arg_18], r9
0x180001fbd  sub     rsp, 68h
0x180001fc1  movdqa  [rsp+68h+var_48], xmm0
0x180001fc7  movdqa  [rsp+68h+var_38], xmm1
0x180001fcd  movdqa  [rsp+68h+var_28], xmm2
0x180001fd3  movdqa  [rsp+68h+var_18], xmm3
0x180001fd9  mov     rdx, rax
0x180001fdc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dxgi_dll
0x180001fe3  call    __delayLoadHelper2
0x180001fe8  movdqa  xmm0, [rsp+68h+var_48]
0x180001fee  movdqa  xmm1, [rsp+68h+var_38]
0x180001ff4  movdqa  xmm2, [rsp+68h+var_28]
0x180001ffa  movdqa  xmm3, [rsp+68h+var_18]
0x180002000  mov     rcx, [rsp+68h+arg_0]
0x180002005  mov     rdx, [rsp+68h+arg_8]
0x18000200a  mov     r8, [rsp+68h+arg_10]
0x180002012  mov     r9, [rsp+68h+arg_18]
0x18000201a  add     rsp, 68h
0x18000201e  jmp     short $+2
0x180002020  jmp     rax
```
