# std::_Uninit_move<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Wrap_alloc<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180002fbc`
- end: `0x180003072`
- name: `??$_Uninit_move@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `182`
- prototype: `_QWORD *__fastcall(_QWORD *Src, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b89c`

## callees

- `0x180001df2`
- `0x180002fbc`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_move<std::wstring *,std::wstring *,std::allocator<std::wstring>,std::wstring>(
        _QWORD *Src,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *i; // rdi
  _QWORD *v6; // rsi

  for ( i = Src; i != a2; i += 4 )
  {
    a3[3] = 7;
    a3[2] = 0;
    *(_WORD *)a3 = 0;
    v6 = i + 2;
    if ( i[3] >= 8u )
    {
      *a3 = *i;
      *i = 0;
    }
    else if ( *v6 != -1 )
    {
      memmove_0(a3, i, 2 * (*v6 + 1LL));
    }
    a3[2] = *v6;
    a3[3] = i[3];
    i[3] = 7;
    *v6 = 0;
    *(_WORD *)i = 0;
    a3 += 4;
  }
  return a3;
}

```

## disassembly

```asm
0x180002fbc  mov     [rsp+arg_0], rbx
0x180002fc1  mov     [rsp+arg_18], r9
0x180002fc6  mov     [rsp+arg_10], r8
0x180002fcb  push    rsi
0x180002fcc  push    rdi
0x180002fcd  push    r14
0x180002fcf  sub     rsp, 20h
0x180002fd3  mov     rbx, r8
0x180002fd6  mov     r14, rdx
0x180002fd9  mov     rdi, rcx
0x180002fdc  mov     [rsp+38h+arg_18], rbx
0x180002fe1  cmp     rcx, rdx
0x180002fe4  jz      short loc_180003061
0x180002fe6  mov     qword ptr [rbx+18h], 7
0x180002fee  mov     qword ptr [rbx+10h], 0
0x180002ff6  xor     eax, eax
0x180002ff8  mov     [rbx], ax
0x180002ffb  lea     rsi, [rdi+10h]
0x180002fff  cmp     qword ptr [rdi+18h], 8
0x180003004  jnb     short loc_18000301F
0x180003006  mov     r8, [rsi]
0x180003009  add     r8, 1
0x18000300d  jz      short loc_18000302C
0x18000300f  add     r8, r8; Size
0x180003012  mov     rdx, rdi; Src
0x180003015  mov     rcx, rbx; void *
0x180003018  call    memmove_0
0x18000301d  jmp     short loc_18000302C
0x18000301f  mov     rax, [rdi]
0x180003022  mov     [rbx], rax
0x180003025  mov     qword ptr [rdi], 0
0x18000302c  mov     rax, [rsi]
0x18000302f  mov     [rbx+10h], rax
0x180003033  mov     rax, [rdi+18h]
0x180003037  mov     [rbx+18h], rax
0x18000303b  mov     qword ptr [rdi+18h], 7
0x180003043  mov     qword ptr [rsi], 0
0x18000304a  xor     eax, eax
0x18000304c  mov     [rdi], ax
0x18000304f  add     rbx, 20h ; ' '
0x180003053  mov     [rsp+38h+arg_10], rbx
0x180003058  add     rdi, 20h ; ' '
0x18000305c  cmp     rdi, r14
0x18000305f  jnz     short loc_180002FE6
0x180003061  mov     rax, rbx
0x180003064  mov     rbx, [rsp+38h+arg_0]
0x180003069  add     rsp, 20h
0x18000306d  pop     r14
0x18000306f  pop     rdi
0x180003070  pop     rsi
0x180003071  retn
```
