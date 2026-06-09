# wil::str_printf<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(ushort const *,...)

- ea: `0x18002eb00`
- end: `0x18002eb83`
- name: `??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ`
- size: `131`
- prototype: `__int64(__int64, __int64, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e970`

## callees

- `0x1800289dc`
- `0x18002eb00`
- `0x18002eb8c`

## string_xrefs

- `0x18002eb67`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 wil::str_printf<std::wstring>(__int64 a1, __int64 a2, ...)
{
  int v3; // eax
  va_list v5; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  va_copy(v5, va);
  v3 = wil::details::str_vprintf_nothrow<std::wstring>(a1, a2, &v5);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7F0,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v3,
      1);
  return a1;
}

```

## disassembly

```asm
0x18002eb00  mov     r11, rsp
0x18002eb03  mov     [r11+10h], rdx
0x18002eb07  mov     [r11+8], rcx
0x18002eb0b  mov     [r11+18h], r8
0x18002eb0f  mov     [r11+20h], r9
0x18002eb13  push    rbx
0x18002eb14  sub     rsp, 30h
0x18002eb18  mov     rbx, rcx
0x18002eb1b  mov     [rsp+38h+var_18], 0
0x18002eb23  xorps   xmm0, xmm0
0x18002eb26  movups  xmmword ptr [rcx], xmm0
0x18002eb29  mov     qword ptr [rcx+10h], 0
0x18002eb31  mov     qword ptr [rcx+18h], 7
0x18002eb39  xor     eax, eax
0x18002eb3b  mov     [rcx], ax
0x18002eb3e  mov     [rsp+38h+var_18], 1; int
0x18002eb46  mov     [r11-10h], rax
0x18002eb4a  lea     rax, [r11+18h]
0x18002eb4e  mov     [r11-10h], rax
0x18002eb52  lea     r8, [r11-10h]
0x18002eb56  call    ??$str_vprintf_nothrow@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEAPEAD@Z; wil::details::str_vprintf_nothrow<std::wstring>(std::wstring &,ushort const *,char * &)
0x18002eb5b  test    eax, eax
0x18002eb5d  jns     short loc_18002EB79
0x18002eb5f  mov     rcx, [rsp+38h]; this
0x18002eb64  mov     r9d, eax; char *
0x18002eb67  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002eb6e  mov     edx, 7F0h; void *
0x18002eb73  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002eb79  mov     rax, rbx
0x18002eb7c  add     rsp, 30h
0x18002eb80  pop     rbx
0x18002eb81  retn
```
