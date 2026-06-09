# av_mallocz

- ea: `0x180044aa0`
- end: `0x180044ad5`
- name: `av_mallocz`
- size: `53`
- prototype: `void *__fastcall(size_t)`
- caller_count: `74`
- callee_count: `3`
- tags: ``

## callers

- `0x180029ef0`
- `0x18002a450`
- `0x18002a6e0`
- `0x18002a790`
- `0x18002df80`
- `0x18002ec70`
- `0x18002eeb0`
- `0x18002ef20`
- `0x18002f150`
- `0x18002f22c`
- `0x18002f35c`
- `0x18002f620`
- `0x1800303b0`
- `0x180033640`
- `0x180035780`
- `0x180035c20`
- `0x180036210`
- `0x180036760`
- `0x1800367c0`
- `0x1800369e0`
- `0x180036dd0`
- `0x180037300`
- `0x180038698`
- `0x180038958`
- `0x1800395c0`
- `0x180039a40`
- `0x18003a5f0`
- `0x18003ac50`
- `0x18003c780`
- `0x18003cda0`
- `0x18003eb30`
- `0x18003eba0`
- `0x18003f1c0`
- `0x18003f280`
- `0x18003f2d0`
- `0x18003fd70`
- `0x18003fdf0`
- `0x18003fee0`
- `0x18003ff60`
- `0x1800400d0`
- `0x180040250`
- `0x1800402d0`
- `0x180043990`
- `0x180043a10`
- `0x180044320`
- `0x180044670`
- `0x180044fcc`
- `0x180045200`
- `0x180046c30`
- `0x18004dd50`

## callees

- `0x180044a20`
- `0x180044aa0`
- `0x18007b020`

## pseudocode

```c
void *__fastcall av_mallocz(size_t a1)
{
  void *v2; // rax
  void *v3; // rbx

  v2 = av_malloc(a1);
  v3 = v2;
  if ( v2 )
    sub_18007B020(v2, 0, a1);
  return v3;
}

```

## disassembly

```asm
0x180044aa0  mov     [rsp+arg_0], rbx
0x180044aa5  push    rdi
0x180044aa6  sub     rsp, 20h
0x180044aaa  mov     rdi, rcx
0x180044aad  call    av_malloc
0x180044ab2  mov     rbx, rax
0x180044ab5  test    rax, rax
0x180044ab8  jz      short loc_180044AC7
0x180044aba  mov     r8, rdi
0x180044abd  xor     edx, edx
0x180044abf  mov     rcx, rax
0x180044ac2  call    sub_18007B020
0x180044ac7  mov     rax, rbx
0x180044aca  mov     rbx, [rsp+28h+arg_0]
0x180044acf  add     rsp, 20h
0x180044ad3  pop     rdi
0x180044ad4  retn
```
