# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(bool,unsigned __int64)

- ea: `0x140007204`
- end: `0x14000725f`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD *, char, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000333c`
- `0x1400035ac`
- `0x140004a60`
- `0x140006e80`
- `0x140008130`
- `0x140009c6c`

## callees

- `0x140007204`
- `0x140007998`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140007237`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007237`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy(_QWORD *a1, char a2, __int64 a3)
{
  void *v5; // rsi
  __int64 result; // rax

  if ( a2 && a1[3] >= 8u )
  {
    v5 = (void *)*a1;
    if ( a3 )
      std::char_traits<unsigned short>::copy(a1, *a1, a3);
    operator delete(v5);
  }
  result = 0;
  a1[3] = 7;
  a1[2] = a3;
  *((_WORD *)a1 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x140007204  mov     [rsp+arg_0], rbx
0x140007209  mov     [rsp+arg_8], rsi
0x14000720e  push    rdi
0x14000720f  sub     rsp, 20h
0x140007213  mov     rdi, r8
0x140007216  mov     rbx, rcx
0x140007219  test    dl, dl
0x14000721b  jz      short loc_14000723D
0x14000721d  cmp     qword ptr [rcx+18h], 8
0x140007222  jb      short loc_14000723D
0x140007224  mov     rsi, [rcx]
0x140007227  test    r8, r8
0x14000722a  jz      short loc_140007234
0x14000722c  mov     rdx, rsi
0x14000722f  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x140007234  mov     rcx, rsi
0x140007237  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000723d  mov     rsi, [rsp+28h+arg_8]
0x140007242  xor     eax, eax
0x140007244  mov     qword ptr [rbx+18h], 7
0x14000724c  mov     [rbx+10h], rdi
0x140007250  mov     [rbx+rdi*2], ax
0x140007254  mov     rbx, [rsp+28h+arg_0]
0x140007259  add     rsp, 20h
0x14000725d  pop     rdi
0x14000725e  retn
```
