# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x18000caf4`
- end: `0x18000cb7c`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bf0c`

## callees

- `0x180001490`
- `0x18000caf4`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000cb51`
- `msvcrt!memmove_s` at `0x18000cb51`

## pseudocode

```c
_QWORD *__fastcall std::string::erase(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  unsigned __int64 v11; // rax

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
    if ( v7 < 0x10 )
    {
      v9 = a1 + 1;
      v10 = a1 + 1;
    }
    else
    {
      v9 = (_QWORD *)*v8;
      v10 = (_QWORD *)*v8;
    }
    memmove_s((char *)v9 + a2, v7 - a2, (char *)v10 + a2 + v3, v6 - v3);
    v11 = a1[3] - v3;
    if ( a1[4] >= 0x10u )
      v8 = (_QWORD *)*v8;
    a1[3] = v11;
    *((_BYTE *)v8 + v11) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000caf4  push    rbx
0x18000caf6  push    rbp
0x18000caf7  push    rsi
0x18000caf8  push    rdi
0x18000caf9  sub     rsp, 28h
0x18000cafd  mov     rsi, r8
0x18000cb00  mov     rbp, rdx
0x18000cb03  mov     rbx, rcx
0x18000cb06  cmp     [rcx+18h], rdx
0x18000cb0a  jnb     short loc_18000CB11
0x18000cb0c  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18000cb11  mov     r9, [rbx+18h]
0x18000cb15  sub     r9, rbp
0x18000cb18  cmp     r9, rsi
0x18000cb1b  cmovb   rsi, r9
0x18000cb1f  test    rsi, rsi
0x18000cb22  jz      short loc_18000CB70
0x18000cb24  mov     rdx, [rbx+20h]
0x18000cb28  lea     rdi, [rbx+8]
0x18000cb2c  cmp     rdx, 10h
0x18000cb30  jb      short loc_18000CB3A
0x18000cb32  mov     rax, [rdi]
0x18000cb35  mov     rcx, rax
0x18000cb38  jmp     short loc_18000CB40
0x18000cb3a  mov     rax, rdi
0x18000cb3d  mov     rcx, rdi
0x18000cb40  lea     r8, [rcx+rbp]
0x18000cb44  sub     r9, rsi; SourceSize
0x18000cb47  add     r8, rsi; Source
0x18000cb4a  lea     rcx, [rax+rbp]; Destination
0x18000cb4e  sub     rdx, rbp; DestinationSize
0x18000cb51  call    cs:__imp_memmove_s
0x18000cb57  mov     rax, [rbx+18h]
0x18000cb5b  sub     rax, rsi
0x18000cb5e  cmp     qword ptr [rbx+20h], 10h
0x18000cb63  jb      short loc_18000CB68
0x18000cb65  mov     rdi, [rdi]
0x18000cb68  mov     [rbx+18h], rax
0x18000cb6c  mov     byte ptr [rax+rdi], 0
0x18000cb70  mov     rax, rbx
0x18000cb73  add     rsp, 28h
0x18000cb77  pop     rdi
0x18000cb78  pop     rsi
0x18000cb79  pop     rbp
0x18000cb7a  pop     rbx
0x18000cb7b  retn
```
