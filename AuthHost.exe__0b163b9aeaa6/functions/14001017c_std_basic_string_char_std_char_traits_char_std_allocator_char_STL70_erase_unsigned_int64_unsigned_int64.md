# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x14001017c`
- end: `0x140010204`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fa74`

## callees

- `0x1400027b0`
- `0x14001017c`

## import_xrefs

- `msvcrt!memmove_s` at `0x1400101d9`
- `msvcrt!memmove_s` at `0x1400101d9`

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
0x14001017c  push    rbx
0x14001017e  push    rbp
0x14001017f  push    rsi
0x140010180  push    rdi
0x140010181  sub     rsp, 28h
0x140010185  mov     rsi, r8
0x140010188  mov     rbp, rdx
0x14001018b  mov     rbx, rcx
0x14001018e  cmp     [rcx+18h], rdx
0x140010192  jnb     short loc_140010199
0x140010194  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x140010199  mov     r9, [rbx+18h]
0x14001019d  sub     r9, rbp
0x1400101a0  cmp     r9, rsi
0x1400101a3  cmovb   rsi, r9
0x1400101a7  test    rsi, rsi
0x1400101aa  jz      short loc_1400101F8
0x1400101ac  mov     rdx, [rbx+20h]
0x1400101b0  lea     rdi, [rbx+8]
0x1400101b4  cmp     rdx, 10h
0x1400101b8  jb      short loc_1400101C2
0x1400101ba  mov     rax, [rdi]
0x1400101bd  mov     rcx, rax
0x1400101c0  jmp     short loc_1400101C8
0x1400101c2  mov     rax, rdi
0x1400101c5  mov     rcx, rdi
0x1400101c8  lea     r8, [rcx+rbp]
0x1400101cc  sub     r9, rsi; SourceSize
0x1400101cf  add     r8, rsi; Source
0x1400101d2  lea     rcx, [rax+rbp]; Destination
0x1400101d6  sub     rdx, rbp; DestinationSize
0x1400101d9  call    cs:__imp_memmove_s
0x1400101df  mov     rax, [rbx+18h]
0x1400101e3  sub     rax, rsi
0x1400101e6  cmp     qword ptr [rbx+20h], 10h
0x1400101eb  jb      short loc_1400101F0
0x1400101ed  mov     rdi, [rdi]
0x1400101f0  mov     [rbx+18h], rax
0x1400101f4  mov     byte ptr [rax+rdi], 0
0x1400101f8  mov     rax, rbx
0x1400101fb  add     rsp, 28h
0x1400101ff  pop     rdi
0x140010200  pop     rsi
0x140010201  pop     rbp
0x140010202  pop     rbx
0x140010203  retn
```
