# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(bool,unsigned __int64)

- ea: `0x140006480`
- end: `0x1400064db`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD *, char, __int64)`
- caller_count: `48`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140003c10`
- `0x140003d00`
- `0x140004128`
- `0x140006230`
- `0x14000636c`
- `0x140006dc8`
- `0x1400071a0`
- `0x140009238`
- `0x1400098b0`
- `0x140009964`
- `0x14000a39c`
- `0x14000a5e0`
- `0x14000cd78`
- `0x14000d134`
- `0x14000d470`
- `0x14000d898`
- `0x14000e194`
- `0x14000e9bc`
- `0x14000faf4`
- `0x140010a2c`
- `0x1400117f0`
- `0x140011954`
- `0x140012050`
- `0x140015a38`
- `0x140015b7c`
- `0x140016a88`
- `0x140017174`
- `0x140017610`
- `0x1400177bc`
- `0x140017c9c`
- `0x140018258`
- `0x140018b40`
- `0x140018d08`
- `0x140018e48`
- `0x140019054`
- `0x1400196dc`
- `0x140019750`
- `0x14001984c`
- `0x140019c6c`
- `0x140019d68`
- `0x140019e94`
- `0x140019fcc`
- `0x14001a0c4`
- `0x14001a244`
- `0x14001a418`
- `0x14001a550`
- `0x14001acc5`
- `0x14001b480`

## callees

- `0x140006480`
- `0x14000679c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400064b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400064b3`

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
0x140006480  mov     [rsp+arg_0], rbx
0x140006485  mov     [rsp+arg_8], rsi
0x14000648a  push    rdi
0x14000648b  sub     rsp, 20h
0x14000648f  mov     rdi, r8
0x140006492  mov     rbx, rcx
0x140006495  test    dl, dl
0x140006497  jz      short loc_1400064B9
0x140006499  cmp     qword ptr [rcx+18h], 8
0x14000649e  jb      short loc_1400064B9
0x1400064a0  mov     rsi, [rcx]
0x1400064a3  test    r8, r8
0x1400064a6  jz      short loc_1400064B0
0x1400064a8  mov     rdx, rsi
0x1400064ab  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x1400064b0  mov     rcx, rsi
0x1400064b3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400064b9  mov     rsi, [rsp+28h+arg_8]
0x1400064be  xor     eax, eax
0x1400064c0  mov     qword ptr [rbx+18h], 7
0x1400064c8  mov     [rbx+10h], rdi
0x1400064cc  mov     [rbx+rdi*2], ax
0x1400064d0  mov     rbx, [rsp+28h+arg_0]
0x1400064d5  add     rsp, 20h
0x1400064d9  pop     rdi
0x1400064da  retn
```
