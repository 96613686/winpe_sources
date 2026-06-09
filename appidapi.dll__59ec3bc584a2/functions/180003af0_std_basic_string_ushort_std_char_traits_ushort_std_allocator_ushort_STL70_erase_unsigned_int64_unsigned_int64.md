# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x180003af0`
- end: `0x180003b83`
- name: `?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039e8`

## callees

- `0x180001700`
- `0x180003af0`

## import_xrefs

- `msvcrt!memmove_s` at `0x180003b55`
- `msvcrt!memmove_s` at `0x180003b55`

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
0x180003af0  push    rbx
0x180003af2  push    rsi
0x180003af3  push    rdi
0x180003af4  push    r14
0x180003af6  sub     rsp, 28h
0x180003afa  mov     rsi, r8
0x180003afd  mov     r14, rdx
0x180003b00  mov     rbx, rcx
0x180003b03  cmp     [rcx+18h], rdx
0x180003b07  jnb     short loc_180003B0E
0x180003b09  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180003b0e  mov     r9, [rbx+18h]
0x180003b12  sub     r9, r14
0x180003b15  cmp     r9, rsi
0x180003b18  cmovb   rsi, r9
0x180003b1c  test    rsi, rsi
0x180003b1f  jz      short loc_180003B76
0x180003b21  mov     rdx, [rbx+20h]
0x180003b25  lea     rdi, [rbx+8]
0x180003b29  cmp     rdx, 8
0x180003b2d  jb      short loc_180003B37
0x180003b2f  mov     rcx, [rdi]
0x180003b32  mov     r8, rcx
0x180003b35  jmp     short loc_180003B3D
0x180003b37  mov     rcx, rdi
0x180003b3a  mov     r8, rdi
0x180003b3d  sub     r9, rsi
0x180003b40  lea     rax, [r14+rsi]
0x180003b44  sub     rdx, r14
0x180003b47  lea     r8, [r8+rax*2]; Source
0x180003b4b  add     r9, r9; SourceSize
0x180003b4e  lea     rcx, [rcx+r14*2]; Destination
0x180003b52  add     rdx, rdx; DestinationSize
0x180003b55  call    cs:__imp_memmove_s
0x180003b5b  mov     rcx, [rbx+18h]
0x180003b5f  sub     rcx, rsi
0x180003b62  cmp     qword ptr [rbx+20h], 8
0x180003b67  jb      short loc_180003B6C
0x180003b69  mov     rdi, [rdi]
0x180003b6c  xor     eax, eax
0x180003b6e  mov     [rbx+18h], rcx
0x180003b72  mov     [rdi+rcx*2], ax
0x180003b76  mov     rax, rbx
0x180003b79  add     rsp, 28h
0x180003b7d  pop     r14
0x180003b7f  pop     rdi
0x180003b80  pop     rsi
0x180003b81  pop     rbx
0x180003b82  retn
```
