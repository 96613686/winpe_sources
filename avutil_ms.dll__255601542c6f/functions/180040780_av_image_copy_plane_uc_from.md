# av_image_copy_plane_uc_from

- ea: `0x180040780`
- end: `0x1800407f6`
- name: `av_image_copy_plane_uc_from`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180040780`
- `0x180041950`
- `0x180078050`

## pseudocode

```c
__int64 __fastcall av_image_copy_plane_uc_from(int a1, int a2, int a3, int a4, __int64 a5, int a6)
{
  __int64 result; // rax

  result = sub_180078050(a1, a2, a3, a4, a5, a6);
  if ( (int)result < 0 )
  {
    _mm_lfence();
    return sub_180041950(a1, a2, a3, a4, a5, a6);
  }
  return result;
}

```

## disassembly

```asm
0x180040780  mov     rax, rsp
0x180040783  mov     [rax+8], rbx
0x180040787  mov     [rax+10h], rbp
0x18004078b  mov     [rax+18h], rsi
0x18004078f  push    rdi
0x180040790  push    r14
0x180040792  push    r15
0x180040794  sub     rsp, 30h
0x180040798  mov     r14d, [rsp+48h+arg_28]
0x18004079d  mov     rbx, r9
0x1800407a0  mov     r15, [rsp+48h+arg_20]
0x1800407a5  mov     rdi, r8
0x1800407a8  mov     [rax-20h], r14d
0x1800407ac  mov     rsi, rdx
0x1800407af  mov     [rax-28h], r15
0x1800407b3  mov     rbp, rcx
0x1800407b6  call    sub_180078050
0x1800407bb  test    eax, eax
0x1800407bd  jns     short loc_1800407DD
0x1800407bf  lfence
0x1800407c2  mov     [rsp+48h+var_20], r14d
0x1800407c7  mov     r9, rbx
0x1800407ca  mov     r8, rdi
0x1800407cd  mov     [rsp+48h+var_28], r15
0x1800407d2  mov     rdx, rsi
0x1800407d5  mov     rcx, rbp
0x1800407d8  call    sub_180041950
0x1800407dd  mov     rbx, [rsp+48h+arg_0]
0x1800407e2  mov     rbp, [rsp+48h+arg_8]
0x1800407e7  mov     rsi, [rsp+48h+arg_10]
0x1800407ec  add     rsp, 30h
0x1800407f0  pop     r15
0x1800407f2  pop     r14
0x1800407f4  pop     rdi
0x1800407f5  retn
```
