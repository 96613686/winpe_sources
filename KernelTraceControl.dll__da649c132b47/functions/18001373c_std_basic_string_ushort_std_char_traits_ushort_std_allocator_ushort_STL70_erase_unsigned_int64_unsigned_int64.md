# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x18001373c`
- end: `0x1800137f7`
- name: `?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `187`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180013934`
- `0x180017b30`

## callees

- `0x18001373c`
- `0x1800276c0`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800137ba`
- `msvcrt!memmove_s` at `0x1800137ba`

## pseudocode

```c
_QWORD *__fastcall std::wstring::erase(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rbx
  _QWORD *v9; // r8
  _QWORD *v10; // rcx
  unsigned __int64 v11; // rax
  bool v12; // cf

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
      v9 = a1 + 1;
    else
      v9 = (_QWORD *)*v8;
    if ( v7 < 8 )
      v10 = a1 + 1;
    else
      v10 = (_QWORD *)*v8;
    memmove_s((char *)v10 + 2 * a2, 2 * (v7 - a2), (char *)v9 + 2 * a2 + 2 * v3, 2 * (v6 - v3));
    v11 = a1[3] - v3;
    v12 = a1[4] < 8u;
    a1[3] = v11;
    if ( !v12 )
      v8 = (_QWORD *)*v8;
    *((_WORD *)v8 + v11) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001373c  mov     rax, rsp
0x18001373f  mov     [rax+8], rbx
0x180013743  mov     [rax+10h], rbp
0x180013747  mov     [rax+18h], rsi
0x18001374b  mov     [rax+20h], rdi
0x18001374f  push    r14
0x180013751  sub     rsp, 20h
0x180013755  mov     rsi, r8
0x180013758  mov     r14, rdx
0x18001375b  mov     rdi, rcx
0x18001375e  cmp     [rcx+18h], rdx
0x180013762  jnb     short loc_180013769
0x180013764  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180013769  mov     r9, [rdi+18h]
0x18001376d  sub     r9, r14
0x180013770  cmp     r9, rsi
0x180013773  cmovb   rsi, r9
0x180013777  xor     ebp, ebp
0x180013779  test    rsi, rsi
0x18001377c  jz      short loc_1800137D9
0x18001377e  mov     rdx, [rdi+20h]
0x180013782  lea     rbx, [rdi+8]
0x180013786  cmp     rdx, 8
0x18001378a  jb      short loc_180013791
0x18001378c  mov     r8, [rbx]
0x18001378f  jmp     short loc_180013794
0x180013791  mov     r8, rbx
0x180013794  cmp     rdx, 8
0x180013798  jb      short loc_18001379F
0x18001379a  mov     rcx, [rbx]
0x18001379d  jmp     short loc_1800137A2
0x18001379f  mov     rcx, rbx
0x1800137a2  sub     r9, rsi
0x1800137a5  lea     rax, [r14+rsi]
0x1800137a9  sub     rdx, r14
0x1800137ac  lea     r8, [r8+rax*2]; Source
0x1800137b0  add     r9, r9; SourceSize
0x1800137b3  lea     rcx, [rcx+r14*2]; Destination
0x1800137b7  add     rdx, rdx; DestinationSize
0x1800137ba  call    cs:__imp_memmove_s
0x1800137c0  mov     rax, [rdi+18h]
0x1800137c4  sub     rax, rsi
0x1800137c7  cmp     qword ptr [rdi+20h], 8
0x1800137cc  mov     [rdi+18h], rax
0x1800137d0  jb      short loc_1800137D5
0x1800137d2  mov     rbx, [rbx]
0x1800137d5  mov     [rbx+rax*2], bp
0x1800137d9  mov     rbx, [rsp+28h+arg_0]
0x1800137de  mov     rax, rdi
0x1800137e1  mov     rdi, [rsp+28h+arg_18]
0x1800137e6  mov     rbp, [rsp+28h+arg_8]
0x1800137eb  mov     rsi, [rsp+28h+arg_10]
0x1800137f0  add     rsp, 20h
0x1800137f4  pop     r14
0x1800137f6  retn
```
