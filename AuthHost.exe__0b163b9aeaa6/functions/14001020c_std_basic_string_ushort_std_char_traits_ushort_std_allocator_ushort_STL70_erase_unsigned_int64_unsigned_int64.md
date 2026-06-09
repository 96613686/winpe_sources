# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x14001020c`
- end: `0x14001029f`
- name: `?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fbc8`

## callees

- `0x1400027b0`
- `0x14001020c`

## import_xrefs

- `msvcrt!memmove_s` at `0x140010271`
- `msvcrt!memmove_s` at `0x140010271`

## pseudocode

```c
_QWORD *__fastcall std::wstring::erase(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rcx
  _QWORD *v10; // r8
  unsigned __int64 v11; // rcx

  v3 = a3;
  if ( a1[3] < a2 )
    std::_String_base::_Xran();
  v6 = a1[3] - a2;
  if ( v6 < a3 )
    v3 = a1[3] - a2;
  if ( v3 )
  {
    v7 = a1[4];
    v8 = a1 + 1;
    if ( v7 < 8 )
    {
      v9 = a1 + 1;
      v10 = a1 + 1;
    }
    else
    {
      v9 = (_QWORD *)*v8;
      v10 = (_QWORD *)*v8;
    }
    memmove_s((char *)v9 + 2 * a2, 2 * (v7 - a2), (char *)v10 + 2 * a2 + 2 * v3, 2 * (v6 - v3));
    v11 = a1[3] - v3;
    if ( a1[4] >= 8u )
      v8 = (_QWORD *)*v8;
    a1[3] = v11;
    *((_WORD *)v8 + v11) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x14001020c  push    rbx
0x14001020e  push    rsi
0x14001020f  push    rdi
0x140010210  push    r14
0x140010212  sub     rsp, 28h
0x140010216  mov     rsi, r8
0x140010219  mov     r14, rdx
0x14001021c  mov     rbx, rcx
0x14001021f  cmp     [rcx+18h], rdx
0x140010223  jnb     short loc_14001022A
0x140010225  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x14001022a  mov     r9, [rbx+18h]
0x14001022e  sub     r9, r14
0x140010231  cmp     r9, rsi
0x140010234  cmovb   rsi, r9
0x140010238  test    rsi, rsi
0x14001023b  jz      short loc_140010292
0x14001023d  mov     rdx, [rbx+20h]
0x140010241  lea     rdi, [rbx+8]
0x140010245  cmp     rdx, 8
0x140010249  jb      short loc_140010253
0x14001024b  mov     rcx, [rdi]
0x14001024e  mov     r8, rcx
0x140010251  jmp     short loc_140010259
0x140010253  mov     rcx, rdi
0x140010256  mov     r8, rdi
0x140010259  sub     r9, rsi
0x14001025c  lea     rax, [r14+rsi]
0x140010260  sub     rdx, r14
0x140010263  lea     r8, [r8+rax*2]; Source
0x140010267  add     r9, r9; SourceSize
0x14001026a  lea     rcx, [rcx+r14*2]; Destination
0x14001026e  add     rdx, rdx; DestinationSize
0x140010271  call    cs:__imp_memmove_s
0x140010277  mov     rcx, [rbx+18h]
0x14001027b  sub     rcx, rsi
0x14001027e  cmp     qword ptr [rbx+20h], 8
0x140010283  jb      short loc_140010288
0x140010285  mov     rdi, [rdi]
0x140010288  xor     eax, eax
0x14001028a  mov     [rbx+18h], rcx
0x14001028e  mov     [rdi+rcx*2], ax
0x140010292  mov     rax, rbx
0x140010295  add     rsp, 28h
0x140010299  pop     r14
0x14001029b  pop     rdi
0x14001029c  pop     rsi
0x14001029d  pop     rbx
0x14001029e  retn
```
