# DeleteCachedCardData

- ea: `0x180021ddc`
- end: `0x180021e5d`
- name: `DeleteCachedCardData`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18001dbec`
- `0x18001dd04`
- `0x18001ebf4`

## callees

- `0x18000a772`
- `0x180016e0c`
- `0x1800226f8`
- `0x18002cfa0`

## pseudocode

```c
__int64 __fastcall DeleteCachedCardData(__int64 a1, size_t *a2)
{
  __int64 v5; // [rsp+20h] [rbp-258h] BYREF
  int v6; // [rsp+28h] [rbp-250h]
  _BYTE v7[8]; // [rsp+2Ch] [rbp-24Ch] BYREF
  unsigned __int16 v8[278]; // [rsp+34h] [rbp-244h] BYREF

  memset_0(v7, 0, 0x22Cu);
  v6 = 2;
  v5 = a1;
  StringCbCopyW(v8, 0x208u, a2);
  return MyCacheDeleteItem(&v5);
}

```

## disassembly

```asm
0x180021ddc  mov     [rsp+arg_10], rbx
0x180021de1  push    rdi
0x180021de2  sub     rsp, 270h
0x180021de9  mov     rax, cs:__security_cookie
0x180021df0  xor     rax, rsp
0x180021df3  mov     [rsp+278h+var_18], rax
0x180021dfb  mov     rdi, rdx
0x180021dfe  mov     rbx, rcx
0x180021e01  xor     edx, edx; Val
0x180021e03  lea     rcx, [rsp+278h+var_24C]; void *
0x180021e08  mov     r8d, 22Ch; Size
0x180021e0e  call    memset_0
0x180021e13  mov     r8, rdi; unsigned __int16 *
0x180021e16  mov     [rsp+278h+var_250], 2
0x180021e1e  mov     edx, 208h; unsigned __int64
0x180021e23  mov     [rsp+278h+var_258], rbx
0x180021e28  lea     rcx, [rsp+278h+var_244]; unsigned __int16 *
0x180021e2d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180021e32  lea     rcx, [rsp+278h+var_258]
0x180021e37  call    MyCacheDeleteItem
0x180021e3c  mov     rcx, [rsp+278h+var_18]
0x180021e44  xor     rcx, rsp; StackCookie
0x180021e47  call    __security_check_cookie
0x180021e4c  mov     rbx, [rsp+278h+arg_10]
0x180021e54  add     rsp, 270h
0x180021e5b  pop     rdi
0x180021e5c  retn
```
