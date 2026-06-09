# av_refstruct_replace

- ea: `0x18004e1d0`
- end: `0x18004e22f`
- name: `av_refstruct_replace`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003bfe0`

## callees

- `0x18004e1d0`
- `0x18004e230`
- `0x18007a960`

## pseudocode

```c
__int64 __fastcall av_refstruct_replace(__m128i *a1, __int64 a2)
{
  __int64 result; // rax
  __m128i v5; // [rsp+38h] [rbp+10h] BYREF

  result = sub_18007A960(&v5, a1, 8u);
  if ( a2 != v5.m128i_i64[0] )
  {
    result = av_refstruct_unref(a1);
    if ( a2 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)(a2 - 64));
      v5.m128i_i64[0] = a2;
      return sub_18007A960(a1, &v5, 8u);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004e1d0  mov     [rsp+arg_0], rbx
0x18004e1d5  push    rdi
0x18004e1d6  sub     rsp, 20h
0x18004e1da  mov     rbx, rdx
0x18004e1dd  mov     rdi, rcx
0x18004e1e0  mov     rdx, rcx
0x18004e1e3  mov     r8d, 8
0x18004e1e9  lea     rcx, [rsp+28h+arg_8]
0x18004e1ee  call    sub_18007A960
0x18004e1f3  cmp     rbx, qword ptr [rsp+28h+arg_8]
0x18004e1f8  jz      short loc_18004E224
0x18004e1fa  mov     rcx, rdi
0x18004e1fd  call    av_refstruct_unref
0x18004e202  test    rbx, rbx
0x18004e205  jz      short loc_18004E224
0x18004e207  lock inc qword ptr [rbx-40h]
0x18004e20c  mov     r8d, 8
0x18004e212  mov     qword ptr [rsp+28h+arg_8], rbx
0x18004e217  lea     rdx, [rsp+28h+arg_8]
0x18004e21c  mov     rcx, rdi
0x18004e21f  call    sub_18007A960
0x18004e224  mov     rbx, [rsp+28h+arg_0]
0x18004e229  add     rsp, 20h
0x18004e22d  pop     rdi
0x18004e22e  retn
```
