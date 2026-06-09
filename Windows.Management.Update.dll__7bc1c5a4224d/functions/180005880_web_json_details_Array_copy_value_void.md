# web::json::details::_Array::_copy_value(void)

- ea: `0x180005880`
- end: `0x180005990`
- name: `?_copy_value@_Array@details@json@web@@UEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@XZ`
- size: `272`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180002cfc`
- `0x180005620`
- `0x180005880`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall web::json::details::_Array::_copy_value(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rsi
  unsigned __int64 v5; // rdx
  _QWORD *v6; // rbx
  _QWORD *v7; // rbp
  _QWORD *i; // rdi
  __int64 *v9; // rax
  __int64 v10; // rcx
  _QWORD *v12; // [rsp+88h] [rbp+10h] BYREF
  _QWORD *v13; // [rsp+90h] [rbp+18h]
  _QWORD *v14; // [rsp+98h] [rbp+20h]

  v12 = a2;
  v4 = operator new(0x20u);
  v13 = v4;
  if ( v4 )
  {
    *v4 = &web::json::details::_Array::`vftable';
    v4[1] = 0;
    v4[2] = 0;
    v4[3] = 0;
    v5 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 3;
    if ( v5 )
    {
      std::vector<web::json::value>::_Buy_nonzero(v4 + 1, v5);
      v14 = v4 + 1;
      v6 = (_QWORD *)v4[1];
      v7 = *(_QWORD **)(a1 + 16);
      for ( i = *(_QWORD **)(a1 + 8); i != v7; ++i )
      {
        v9 = (__int64 *)(**(__int64 (__fastcall ***)(_QWORD, _QWORD **))*i)(*i, &v12);
        v10 = *v9;
        *v9 = 0;
        *v6 = v10;
        if ( v12 )
          (*(void (__fastcall **)(_QWORD *, __int64))(*v12 + 192LL))(v12, 1);
        ++v6;
      }
      v4[2] = v6;
    }
  }
  else
  {
    v4 = 0;
  }
  *a2 = v4;
  return a2;
}

```

## disassembly

```asm
0x180005880  mov     [rsp+arg_8], rdx
0x180005885  push    rbx
0x180005886  push    rbp
0x180005887  push    rsi
0x180005888  push    rdi
0x180005889  push    r12
0x18000588b  push    r14
0x18000588d  push    r15
0x18000588f  sub     rsp, 40h
0x180005893  mov     r15, rdx
0x180005896  mov     rdi, rcx
0x180005899  xor     r12d, r12d
0x18000589c  mov     ecx, 20h ; ' '; Size
0x1800058a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800058a6  mov     rsi, rax
0x1800058a9  mov     [rsp+78h+arg_10], rax
0x1800058b1  test    rax, rax
0x1800058b4  jz      loc_180005978
0x1800058ba  lea     rax, ??_7_Array@details@json@web@@6B@; const web::json::details::_Array::`vftable'
0x1800058c1  mov     [rsi], rax
0x1800058c4  lea     r14, [rsi+8]
0x1800058c8  mov     [r14], r12
0x1800058cb  mov     [r14+8], r12
0x1800058cf  mov     [r14+10h], r12
0x1800058d3  mov     rdx, [rdi+10h]
0x1800058d7  sub     rdx, [rdi+8]
0x1800058db  sar     rdx, 3
0x1800058df  test    rdx, rdx
0x1800058e2  jz      loc_180005976
0x1800058e8  mov     rcx, r14
0x1800058eb  call    ?_Buy_nonzero@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAX_K@Z; std::vector<web::json::value>::_Buy_nonzero(unsigned __int64)
0x1800058f0  mov     [rsp+78h+arg_18], r14
0x1800058f8  mov     rbx, [r14]
0x1800058fb  mov     rbp, [rdi+10h]
0x1800058ff  mov     rdi, [rdi+8]
0x180005903  mov     [rsp+78h+var_50], rbx
0x180005908  mov     [rsp+78h+var_48], rbx
0x18000590d  mov     [rsp+78h+var_40], r14
0x180005912  cmp     rdi, rbp
0x180005915  jz      short loc_180005972
0x180005917  nop     word ptr [rax+rax+00000000h]
0x180005920  mov     rcx, [rdi]
0x180005923  mov     rax, [rcx]
0x180005926  lea     rdx, [rsp+78h+arg_8]
0x18000592e  mov     rax, [rax]
0x180005931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005936  mov     rcx, [rax]
0x180005939  mov     [rax], r12
0x18000593c  mov     [rbx], rcx
0x18000593f  mov     rcx, [rsp+78h+arg_8]
0x180005947  test    rcx, rcx
0x18000594a  jz      short loc_180005960
0x18000594c  mov     rax, [rcx]
0x18000594f  mov     edx, 1
0x180005954  mov     rax, [rax+0C0h]
0x18000595b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005960  add     rbx, 8
0x180005964  mov     [rsp+78h+var_48], rbx
0x180005969  add     rdi, 8
0x18000596d  cmp     rdi, rbp
0x180005970  jnz     short loc_180005920
0x180005972  mov     [r14+8], rbx
0x180005976  jmp     short loc_18000597B
0x180005978  mov     rsi, r12
0x18000597b  mov     [r15], rsi
0x18000597e  mov     rax, r15
0x180005981  add     rsp, 40h
0x180005985  pop     r15
0x180005987  pop     r14
0x180005989  pop     r12
0x18000598b  pop     rdi
0x18000598c  pop     rsi
0x18000598d  pop     rbp
0x18000598e  pop     rbx
0x18000598f  retn
```
