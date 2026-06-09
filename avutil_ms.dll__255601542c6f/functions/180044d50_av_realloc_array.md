# av_realloc_array

- ea: `0x180044d50`
- end: `0x180044d89`
- name: `av_realloc_array`
- size: `57`
- prototype: `void *__fastcall(__int64, __int64, __int64)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180036210`
- `0x180039a40`
- `0x180039c10`
- `0x18003ba10`
- `0x18003fd70`
- `0x18003fee0`
- `0x180040250`
- `0x1800402d0`
- `0x180046fd0`
- `0x180049a10`
- `0x1800506c0`

## callees

- `0x180044d10`
- `0x180044d50`
- `0x1800451b8`

## pseudocode

```c
void *__fastcall av_realloc_array(__int64 a1, __int64 a2, __int64 a3)
{
  void *v3; // r11
  unsigned __int64 v5; // [rsp+48h] [rbp+20h] BYREF

  if ( (int)av_size_mult_0(a2, a3, &v5) >= 0 )
    return av_realloc(v3, v5);
  else
    return 0;
}

```

## disassembly

```asm
0x180044d50  sub     rsp, 28h
0x180044d54  mov     rax, r8
0x180044d57  mov     r9, rdx
0x180044d5a  mov     r11, rcx
0x180044d5d  lea     r8, [rsp+28h+arg_18]
0x180044d62  mov     rdx, rax
0x180044d65  mov     rcx, r9
0x180044d68  call    av_size_mult_0
0x180044d6d  test    eax, eax
0x180044d6f  jns     short loc_180044D78
0x180044d71  xor     eax, eax
0x180044d73  add     rsp, 28h
0x180044d77  retn
0x180044d78  mov     rdx, [rsp+28h+arg_18]
0x180044d7d  mov     rcx, r11
0x180044d80  add     rsp, 28h
0x180044d84  jmp     av_realloc
```
