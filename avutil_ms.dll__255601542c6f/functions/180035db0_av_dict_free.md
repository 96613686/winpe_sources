# av_dict_free

- ea: `0x180035db0`
- end: `0x180035e26`
- name: `av_dict_free`
- size: `118`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x18003ba10`
- `0x18003bd20`
- `0x1800465b0`
- `0x180047a80`
- `0x180047b50`
- `0x180048c50`
- `0x180048e4c`
- `0x18004a608`
- `0x180050880`
- `0x180050d58`
- `0x180050d8c`

## callees

- `0x180035db0`
- `0x1800449d0`

## pseudocode

```c
void __fastcall av_dict_free(__m128i *a1)
{
  int *v1; // rbx
  int v3; // eax
  _QWORD *i; // rdi
  int v5; // eax
  __m128i *v6; // rcx

  v1 = (int *)a1->m128i_i64[0];
  if ( a1->m128i_i64[0] )
  {
    v3 = *v1;
    for ( i = v1 + 2; *v1; v3 = *v1 )
    {
      v5 = v3 - 1;
      v6 = (__m128i *)(*i + 16LL * v5);
      *v1 = v5;
      av_freep(v6);
      av_freep((__m128i *)(*i + 8LL + 16LL * *v1));
    }
    *v1 = v3 - 1;
    av_freep((__m128i *)(v1 + 2));
  }
  av_freep(a1);
}

```

## disassembly

```asm
0x180035db0  mov     [rsp+arg_0], rbx
0x180035db5  mov     [rsp+arg_8], rsi
0x180035dba  push    rdi
0x180035dbb  sub     rsp, 20h
0x180035dbf  mov     rbx, [rcx]
0x180035dc2  mov     rsi, rcx
0x180035dc5  test    rbx, rbx
0x180035dc8  jz      short loc_180035E0F
0x180035dca  mov     eax, [rbx]
0x180035dcc  lea     rdi, [rbx+8]
0x180035dd0  test    eax, eax
0x180035dd2  jz      short loc_180035E03
0x180035dd4  dec     eax
0x180035dd6  movsxd  rcx, eax
0x180035dd9  shl     rcx, 4
0x180035ddd  add     rcx, [rdi]
0x180035de0  mov     [rbx], eax
0x180035de2  call    av_freep
0x180035de7  movsxd  rcx, dword ptr [rbx]
0x180035dea  mov     rax, [rdi]
0x180035ded  shl     rcx, 4
0x180035df1  add     rax, 8
0x180035df5  add     rcx, rax
0x180035df8  call    av_freep
0x180035dfd  mov     eax, [rbx]
0x180035dff  test    eax, eax
0x180035e01  jnz     short loc_180035DD4
0x180035e03  dec     eax
0x180035e05  mov     rcx, rdi
0x180035e08  mov     [rbx], eax
0x180035e0a  call    av_freep
0x180035e0f  mov     rcx, rsi
0x180035e12  mov     rbx, [rsp+28h+arg_0]
0x180035e17  mov     rsi, [rsp+28h+arg_8]
0x180035e1c  add     rsp, 20h
0x180035e20  pop     rdi
0x180035e21  jmp     av_freep
```
