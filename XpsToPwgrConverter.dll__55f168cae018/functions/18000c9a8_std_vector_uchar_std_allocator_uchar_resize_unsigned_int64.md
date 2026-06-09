# std::vector<uchar,std::allocator<uchar>>::resize(unsigned __int64)

- ea: `0x18000c9a8`
- end: `0x18000ca18`
- name: `?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z`
- size: `112`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b238`
- `0x18000b498`
- `0x18000b74c`
- `0x18000ba80`
- `0x18000bd40`
- `0x18000c078`
- `0x18000c514`
- `0x18000c7c4`
- `0x18000d9dc`
- `0x18000dc78`

## callees

- `0x180002194`
- `0x18000c33c`
- `0x18000c9a8`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::resize(__int64 *a1, unsigned __int64 a2)
{
  char *v2; // rsi
  __int64 v4; // rdx
  char *v6; // rcx
  char *v7; // rax
  size_t v8; // rbx

  v2 = (char *)a1[1];
  v4 = *a1;
  v6 = &v2[-*a1];
  if ( a2 >= (unsigned __int64)v6 )
  {
    if ( a2 <= (unsigned __int64)v6 )
      return;
    if ( a2 > a1[2] - v4 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a1, a2);
      return;
    }
    v8 = a2 - (_QWORD)v6;
    memset_0(v2, 0, v8);
    v7 = &v2[v8];
  }
  else
  {
    v7 = (char *)(v4 + a2);
  }
  a1[1] = (__int64)v7;
}

```

## disassembly

```asm
0x18000c9a8  mov     [rsp+arg_0], rbx
0x18000c9ad  mov     [rsp+arg_8], rsi
0x18000c9b2  push    rdi
0x18000c9b3  sub     rsp, 20h
0x18000c9b7  mov     rsi, [rcx+8]
0x18000c9bb  mov     rbx, rdx
0x18000c9be  mov     rdx, [rcx]
0x18000c9c1  mov     rdi, rcx
0x18000c9c4  mov     rcx, rsi
0x18000c9c7  sub     rcx, rdx
0x18000c9ca  cmp     rbx, rcx
0x18000c9cd  jnb     short loc_18000C9D5
0x18000c9cf  lea     rax, [rdx+rbx]
0x18000c9d3  jmp     short loc_18000CA04
0x18000c9d5  jbe     short loc_18000CA08
0x18000c9d7  mov     rax, [rdi+10h]
0x18000c9db  sub     rax, rdx
0x18000c9de  cmp     rbx, rax
0x18000c9e1  jbe     short loc_18000C9F0
0x18000c9e3  mov     rdx, rbx
0x18000c9e6  mov     rcx, rdi
0x18000c9e9  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000c9ee  jmp     short loc_18000CA08
0x18000c9f0  sub     rbx, rcx
0x18000c9f3  xor     edx, edx; Val
0x18000c9f5  mov     r8, rbx; Size
0x18000c9f8  mov     rcx, rsi; void *
0x18000c9fb  call    memset_0
0x18000ca00  lea     rax, [rbx+rsi]
0x18000ca04  mov     [rdi+8], rax
0x18000ca08  mov     rbx, [rsp+28h+arg_0]
0x18000ca0d  mov     rsi, [rsp+28h+arg_8]
0x18000ca12  add     rsp, 20h
0x18000ca16  pop     rdi
0x18000ca17  retn
```
