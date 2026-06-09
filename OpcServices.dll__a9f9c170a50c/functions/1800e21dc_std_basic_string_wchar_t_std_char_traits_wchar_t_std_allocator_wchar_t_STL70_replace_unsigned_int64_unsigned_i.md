# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::replace(unsigned __int64,unsigned __int64,unsigned __int64,wchar_t)

- ea: `0x1800e21dc`
- end: `0x1800e22d7`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K00_W@Z`
- size: `251`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800172f4`
- `0x180018d18`

## callees

- `0x18001c4b0`
- `0x180075cd0`
- `0x1800cdb60`
- `0x1800e21dc`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800e2245`
- `msvcrt!memmove_s` at `0x1800e229d`
- `msvcrt!memmove_s` at `0x1800e2245`
- `msvcrt!memmove_s` at `0x1800e229d`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(_QWORD *a1)
{
  __int64 v1; // rax
  _BOOL8 v3; // rsi
  _QWORD *v4; // rbx
  __int64 v5; // r14
  __int64 v6; // rbp
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax

  v1 = a1[3];
  v3 = v1 != 0;
  if ( (unsigned __int64)(v1 - v3) >= 0xFFFFFFFFFFFFFFFEuLL )
    std::_String_base::_Xlen();
  v4 = a1 + 1;
  v5 = a1[3] - v3;
  v6 = v5 + 1;
  if ( (unsigned __int8)std::wstring::_Grow(a1, v5 + 1, 0) )
  {
    if ( !v3 )
    {
      v7 = a1[4];
      v4 = a1 + 1;
      if ( v7 < 8 )
      {
        v8 = a1 + 1;
        v9 = a1 + 1;
      }
      else
      {
        v8 = (_QWORD *)*v4;
        v9 = (_QWORD *)*v4;
      }
      memmove_s((char *)v8 + 2, 2 * v7 - 2, v9, 2 * v5);
    }
    std::wstring::_Chassign(a1, 0, 1, 47);
    if ( a1[4] >= 8u )
      v4 = (_QWORD *)*v4;
    a1[3] = v6;
    *((_WORD *)v4 + v6) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800e21dc  push    rbx
0x1800e21de  push    rbp
0x1800e21df  push    rsi
0x1800e21e0  push    rdi
0x1800e21e1  push    r14
0x1800e21e3  sub     rsp, 20h
0x1800e21e7  mov     rax, [rcx+18h]
0x1800e21eb  mov     esi, 1
0x1800e21f0  cmp     rax, rsi
0x1800e21f3  mov     rdi, rcx
0x1800e21f6  cmovb   rsi, rax
0x1800e21fa  sub     rax, rsi
0x1800e21fd  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800e2201  jb      short loc_1800E2208
0x1800e2203  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x1800e2208  mov     r14, [rdi+18h]
0x1800e220c  lea     rbx, [rdi+8]
0x1800e2210  sub     r14, rsi
0x1800e2213  cmp     rsi, 1
0x1800e2217  jbe     short loc_1800E224B
0x1800e2219  mov     rdx, [rdi+20h]
0x1800e221d  cmp     rdx, 8
0x1800e2221  jb      short loc_1800E222B
0x1800e2223  mov     rcx, [rbx]
0x1800e2226  mov     rax, rcx
0x1800e2229  jmp     short loc_1800E2231
0x1800e222b  mov     rcx, rbx
0x1800e222e  mov     rax, rbx
0x1800e2231  lea     r9, [r14+r14]; SourceSize
0x1800e2235  add     rcx, 2; Destination
0x1800e2239  lea     r8, [rax+rsi*2]; Source
0x1800e223d  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]; DestinationSize
0x1800e2245  call    cs:__imp_memmove_s
0x1800e224b  mov     rbp, [rdi+18h]
0x1800e224f  xor     r8d, r8d
0x1800e2252  sub     rbp, rsi
0x1800e2255  mov     rcx, rdi
0x1800e2258  inc     rbp
0x1800e225b  mov     rdx, rbp
0x1800e225e  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800e2263  test    al, al
0x1800e2265  jz      short loc_1800E22C9
0x1800e2267  cmp     rsi, 1
0x1800e226b  jnb     short loc_1800E22A3
0x1800e226d  mov     rdx, [rdi+20h]
0x1800e2271  lea     rbx, [rdi+8]
0x1800e2275  cmp     rdx, 8
0x1800e2279  jb      short loc_1800E2283
0x1800e227b  mov     rcx, [rbx]
0x1800e227e  mov     rax, rcx
0x1800e2281  jmp     short loc_1800E2289
0x1800e2283  mov     rcx, rbx
0x1800e2286  mov     rax, rbx
0x1800e2289  lea     r9, [r14+r14]; SourceSize
0x1800e228d  add     rcx, 2; Destination
0x1800e2291  lea     r8, [rax+rsi*2]; Source
0x1800e2295  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]; DestinationSize
0x1800e229d  call    cs:__imp_memmove_s
0x1800e22a3  xor     edx, edx
0x1800e22a5  mov     rcx, rdi
0x1800e22a8  lea     r9d, [rdx+2Fh]
0x1800e22ac  lea     r8d, [rdx+1]
0x1800e22b0  call    ?_Chassign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0_W@Z; std::wstring::_Chassign(unsigned __int64,unsigned __int64,wchar_t)
0x1800e22b5  cmp     qword ptr [rdi+20h], 8
0x1800e22ba  jb      short loc_1800E22BF
0x1800e22bc  mov     rbx, [rbx]
0x1800e22bf  xor     eax, eax
0x1800e22c1  mov     [rdi+18h], rbp
0x1800e22c5  mov     [rbx+rbp*2], ax
0x1800e22c9  mov     rax, rdi
0x1800e22cc  add     rsp, 20h
0x1800e22d0  pop     r14
0x1800e22d2  pop     rdi
0x1800e22d3  pop     rsi
0x1800e22d4  pop     rbp
0x1800e22d5  pop     rbx
0x1800e22d6  retn
```
