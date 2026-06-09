# av_strdup

- ea: `0x180044f00`
- end: `0x180044f55`
- name: `av_strdup`
- size: `85`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x18002cf40`
- `0x180032620`
- `0x180035f40`
- `0x180036210`
- `0x180045b60`
- `0x180045cc0`
- `0x180047710`
- `0x180048524`
- `0x180048c50`
- `0x180049074`
- `0x180049c20`

## callees

- `0x180044d10`
- `0x180044f00`
- `0x180078c1a`
- `0x18007a960`

## pseudocode

```c
__m128i *__fastcall av_strdup(const __m128i *a1)
{
  __m128i *v1; // rbx
  unsigned __int64 v3; // rsi
  __m128i *v4; // rax

  v1 = 0;
  if ( a1 )
  {
    v3 = strlen(a1->m128i_i8) + 1;
    v4 = (__m128i *)av_realloc(0, v3);
    v1 = v4;
    if ( v4 )
      sub_18007A960(v4, a1, v3);
  }
  return v1;
}

```

## disassembly

```asm
0x180044f00  mov     [rsp+arg_0], rbx
0x180044f05  mov     [rsp+arg_8], rsi
0x180044f0a  push    rdi
0x180044f0b  sub     rsp, 20h
0x180044f0f  xor     ebx, ebx
0x180044f11  mov     rdi, rcx
0x180044f14  test    rcx, rcx
0x180044f17  jz      short loc_180044F42
0x180044f19  call    strlen
0x180044f1e  xor     ecx, ecx
0x180044f20  lea     rsi, [rax+1]
0x180044f24  mov     rdx, rsi
0x180044f27  call    av_realloc
0x180044f2c  mov     rbx, rax
0x180044f2f  test    rax, rax
0x180044f32  jz      short loc_180044F42
0x180044f34  mov     r8, rsi
0x180044f37  mov     rdx, rdi
0x180044f3a  mov     rcx, rax
0x180044f3d  call    sub_18007A960
0x180044f42  mov     rsi, [rsp+28h+arg_8]
0x180044f47  mov     rax, rbx
0x180044f4a  mov     rbx, [rsp+28h+arg_0]
0x180044f4f  add     rsp, 20h
0x180044f53  pop     rdi
0x180044f54  retn
```
