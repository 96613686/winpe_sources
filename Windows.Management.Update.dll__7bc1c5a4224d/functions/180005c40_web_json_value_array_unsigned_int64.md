# web::json::value::array(unsigned __int64)

- ea: `0x180005c40`
- end: `0x180005cd5`
- name: `?array@value@json@web@@SA?AV123@_K@Z`
- size: `149`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018440`

## callees

- `0x180002cfc`
- `0x1800044a0`
- `0x180005620`
- `0x180005c40`

## pseudocode

```c
_QWORD *__fastcall web::json::value::array(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v4; // rbx

  v4 = operator new(0x20u);
  if ( v4 )
  {
    *v4 = &web::json::details::_Array::`vftable';
    v4[1] = 0;
    v4[2] = 0;
    v4[3] = 0;
    if ( a2 )
    {
      std::vector<web::json::value>::_Buy_nonzero(v4 + 1, a2);
      v4[2] = std::_Uninitialized_value_construct_n<std::allocator<web::json::value>>((_QWORD *)v4[1], a2);
    }
  }
  else
  {
    v4 = 0;
  }
  *a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x180005c40  mov     [rsp+arg_8], rbx
0x180005c45  mov     [rsp+arg_18], rbp
0x180005c4a  mov     [rsp+arg_0], rcx
0x180005c4f  push    rsi
0x180005c50  push    rdi
0x180005c51  push    r14
0x180005c53  sub     rsp, 30h
0x180005c57  mov     rbp, rdx
0x180005c5a  mov     rsi, rcx
0x180005c5d  xor     r14d, r14d
0x180005c60  mov     ecx, 20h ; ' '; Size
0x180005c65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c6a  mov     rbx, rax
0x180005c6d  mov     [rsp+48h+arg_0], rax
0x180005c72  test    rax, rax
0x180005c75  jz      short loc_180005CB9
0x180005c77  lea     rax, ??_7_Array@details@json@web@@6B@; const web::json::details::_Array::`vftable'
0x180005c7e  mov     [rbx], rax
0x180005c81  lea     rdi, [rbx+8]
0x180005c85  mov     [rdi], r14
0x180005c88  mov     [rdi+8], r14
0x180005c8c  mov     [rdi+10h], r14
0x180005c90  test    rbp, rbp
0x180005c93  jz      short loc_180005CB7
0x180005c95  mov     rdx, rbp
0x180005c98  mov     rcx, rdi
0x180005c9b  call    ?_Buy_nonzero@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAX_K@Z; std::vector<web::json::value>::_Buy_nonzero(unsigned __int64)
0x180005ca0  mov     [rsp+48h+arg_10], rdi
0x180005ca5  mov     r8, rdi
0x180005ca8  mov     rdx, rbp
0x180005cab  mov     rcx, [rdi]
0x180005cae  call    ??$_Uninitialized_value_construct_n@V?$allocator@Vvalue@json@web@@@std@@@std@@YAPEAVvalue@json@web@@PEAV123@_KAEAV?$allocator@Vvalue@json@web@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<web::json::value>>(web::json::value *,unsigned __int64,std::allocator<web::json::value> &)
0x180005cb3  mov     [rdi+8], rax
0x180005cb7  jmp     short loc_180005CBC
0x180005cb9  mov     rbx, r14
0x180005cbc  mov     [rsi], rbx
0x180005cbf  mov     rax, rsi
0x180005cc2  mov     rbx, [rsp+48h+arg_8]
0x180005cc7  mov     rbp, [rsp+48h+arg_18]
0x180005ccc  add     rsp, 30h
0x180005cd0  pop     r14
0x180005cd2  pop     rdi
0x180005cd3  pop     rsi
0x180005cd4  retn
```
