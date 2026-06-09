# ResourceLoader6::SimpleResourceLoader::ParsePathsInto(ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180015784`
- end: `0x1800159b9`
- name: `?ParsePathsInto@SimpleResourceLoader@ResourceLoader6@@IEAAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `565`
- prototype: `void __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800154a0`

## callees

- `0x1800142e0`
- `0x180014cf0`
- `0x180014d28`
- `0x180014f2c`
- `0x180014ff4`
- `0x180015784`
- `0x18003e0d0`
- `0x18009e300`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800158e7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800158e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ResourceLoader6::SimpleResourceLoader::ParsePathsInto(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int16 v8; // ax
  void **v9; // rax
  char v10; // al
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdi
  void **v14; // rax
  void **v15; // rcx
  void **v16; // rax
  unsigned __int64 v17; // rdi
  __int64 v18; // [rsp+20h] [rbp-30h]
  void *v19[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v20; // [rsp+38h] [rbp-18h]
  unsigned __int64 v21; // [rsp+40h] [rbp-10h]

  if ( a2 )
  {
    HIWORD(v18) = -1;
    v5 = 0;
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v8 = *(_WORD *)(a2 + 2 * v5);
        if ( v8 == 59 || !v8 )
          break;
        ++v7;
        ++v5;
      }
      if ( v7 )
      {
        v21 = 7;
        v20 = 0;
        LOWORD(v19[0]) = 0;
        std::wstring::assign(v19, a2 + 2 * v6, v7);
        v9 = v19;
        if ( v21 >= 8 )
          v9 = (void **)v19[0];
        if ( *((_WORD *)v9 + v20 - 1) != 92 )
        {
          v16 = v19;
          if ( v21 >= 8 )
            v16 = (void **)v19[0];
          if ( *((_WORD *)v16 + v20 - 1) != 47 )
          {
            if ( v20 == -1 || v20 == -2 )
              std::_Xlength_error("string too long");
            v13 = v20 + 1;
            if ( (unsigned __int8)std::wstring::_Grow(v19, v20 + 1, 0) )
            {
              v14 = v19;
              if ( v21 >= 8 )
                v14 = (void **)v19[0];
              *((_WORD *)v14 + v20) = 92;
              v15 = v19;
              if ( v21 >= 8 )
                v15 = (void **)v19[0];
              v20 = v13;
              *((_WORD *)v15 + v13) = 0;
            }
          }
        }
        if ( (unsigned __int64)v19 >= a3[1] || (v10 = 1, *a3 > (unsigned __int64)v19) )
          v10 = 0;
        v11 = a3[2];
        if ( v10 )
        {
          v17 = (unsigned __int64)v19 - *a3;
          if ( a3[1] == v11 )
            std::vector<std::wstring>::_Reserve(a3);
          std::wstring::wstring(a3[1], *a3 + (v17 & 0xFFFFFFFFFFFFFFE0uLL));
        }
        else
        {
          if ( a3[1] == v11 )
            std::vector<std::wstring>::_Reserve(a3);
          v12 = a3[1];
          *(_QWORD *)(v12 + 24) = 7;
          *(_QWORD *)(v12 + 16) = 0;
          *(_WORD *)v12 = 0;
          std::wstring::assign(v12, v19, 0, -1);
        }
        a3[1] += 32LL;
        v7 = 0;
        if ( v21 >= 8 )
          operator delete(v19[0]);
        v21 = 7;
        v20 = 0;
        LOWORD(v19[0]) = 0;
        v8 = *(_WORD *)(a2 + 2 * v5);
      }
      if ( !v8 )
        break;
      v6 = ++v5;
    }
  }
}

```

## disassembly

```asm
0x180015784  test    rdx, rdx
0x180015787  jz      locret_1800158D5
0x18001578d  mov     rax, rsp
0x180015790  push    rbp
0x180015791  push    rdi
0x180015792  push    r12
0x180015794  push    r14
0x180015796  push    r15
0x180015798  mov     rbp, rsp
0x18001579b  sub     rsp, 50h
0x18001579f  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x1800157a7  mov     [rax+8], rbx
0x1800157ab  mov     [rax+20h], rsi
0x1800157af  mov     rax, cs:__security_cookie
0x1800157b6  xor     rax, rsp
0x1800157b9  mov     [rbp+var_8], rax
0x1800157bd  mov     rbx, r8
0x1800157c0  mov     r14, rdx
0x1800157c3  xor     r15d, r15d
0x1800157c6  mov     esi, r15d
0x1800157c9  mov     ecx, r15d
0x1800157cc  mov     edi, r15d
0x1800157cf  lea     r12d, [r15+7]
0x1800157d3  movzx   eax, word ptr [r14+rsi*2]
0x1800157d8  cmp     ax, 3Bh ; ';'
0x1800157dc  jz      short loc_1800157EB
0x1800157de  test    ax, ax
0x1800157e1  jz      short loc_1800157EB
0x1800157e3  inc     rdi
0x1800157e6  inc     rsi
0x1800157e9  jmp     short loc_1800157D3
0x1800157eb  test    rdi, rdi
0x1800157ee  jz      loc_1800158A0
0x1800157f4  mov     [rbp+var_18], r15
0x1800157f8  mov     [rbp+var_10], r15
0x1800157fc  mov     [rbp+var_10], r12
0x180015800  mov     [rbp+var_18], r15
0x180015804  mov     word ptr [rbp+var_28], r15w
0x180015809  lea     rdx, [r14+rcx*2]
0x18001580d  mov     r8, rdi
0x180015810  lea     rcx, [rbp+var_28]
0x180015814  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180015819  nop
0x18001581a  lea     rax, [rbp+var_28]
0x18001581e  cmp     [rbp+var_10], 8
0x180015823  cmovnb  rax, [rbp+var_28]
0x180015828  mov     rcx, [rbp+var_18]
0x18001582c  mov     edx, 5Ch ; '\'
0x180015831  cmp     [rax+rcx*2-2], dx
0x180015836  jnz     loc_18001594F
0x18001583c  lea     rax, [rbp+var_28]
0x180015840  cmp     rax, [rbx+8]
0x180015844  jb      loc_18001596B
0x18001584a  mov     al, r15b
0x18001584d  mov     rcx, [rbx+10h]
0x180015851  test    al, al
0x180015853  jnz     loc_18001597F
0x180015859  cmp     [rbx+8], rcx
0x18001585d  jz      short loc_1800158D6
0x18001585f  mov     rcx, [rbx+8]
0x180015863  mov     [rcx+18h], r12
0x180015867  mov     [rcx+10h], r15
0x18001586b  mov     [rcx], r15w
0x18001586f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180015873  xor     r8d, r8d
0x180015876  lea     rdx, [rbp+var_28]
0x18001587a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001587f  add     qword ptr [rbx+8], 20h ; ' '
0x180015884  mov     rdi, r15
0x180015887  cmp     [rbp+var_10], 8
0x18001588c  jnb     short loc_1800158E3
0x18001588e  mov     [rbp+var_10], r12
0x180015892  mov     [rbp+var_18], r15
0x180015896  mov     word ptr [rbp+var_28], r15w
0x18001589b  movzx   eax, word ptr [r14+rsi*2]
0x1800158a0  test    ax, ax
0x1800158a3  jz      short loc_1800158B1
0x1800158a5  lea     rcx, [rsi+1]
0x1800158a9  mov     rsi, rcx
0x1800158ac  jmp     loc_1800157D3
0x1800158b1  mov     rcx, [rbp+var_8]
0x1800158b5  xor     rcx, rsp; StackCookie
0x1800158b8  call    __security_check_cookie
0x1800158bd  lea     r11, [rsp+50h+var_s0]
0x1800158c2  mov     rbx, [r11+30h]
0x1800158c6  mov     rsi, [r11+48h]
0x1800158ca  mov     rsp, r11
0x1800158cd  pop     r15
0x1800158cf  pop     r14
0x1800158d1  pop     r12
0x1800158d3  pop     rdi
0x1800158d4  pop     rbp
0x1800158d5  retn
0x1800158d6  mov     rcx, rbx
0x1800158d9  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800158de  jmp     loc_18001585F
0x1800158e3  mov     rcx, [rbp+var_28]
0x1800158e7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800158ed  jmp     short loc_18001588E
0x1800158ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800158f3  sub     rax, rcx
0x1800158f6  cmp     rax, 1
0x1800158fa  jbe     loc_1800159AC
0x180015900  lea     rdi, [rcx+1]
0x180015904  xor     r8d, r8d
0x180015907  mov     rdx, rdi
0x18001590a  lea     rcx, [rbp+var_28]
0x18001590e  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180015913  test    al, al
0x180015915  jz      loc_18001583C
0x18001591b  mov     rcx, [rbp+var_18]
0x18001591f  lea     rax, [rbp+var_28]
0x180015923  cmp     [rbp+var_10], 8
0x180015928  cmovnb  rax, [rbp+var_28]
0x18001592d  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x180015933  lea     rcx, [rbp+var_28]
0x180015937  cmp     [rbp+var_10], 8
0x18001593c  cmovnb  rcx, [rbp+var_28]
0x180015941  mov     [rbp+var_18], rdi
0x180015945  mov     [rcx+rdi*2], r15w
0x18001594a  jmp     loc_18001583C
0x18001594f  lea     rax, [rbp+var_28]
0x180015953  cmp     [rbp+var_10], 8
0x180015958  cmovnb  rax, [rbp+var_28]
0x18001595d  cmp     word ptr [rax+rcx*2-2], 2Fh ; '/'
0x180015963  jz      loc_18001583C
0x180015969  jmp     short loc_1800158EF
0x18001596b  lea     rax, [rbp+var_28]
0x18001596f  cmp     [rbx], rax
0x180015972  mov     al, 1
0x180015974  jbe     loc_18001584D
0x18001597a  jmp     loc_18001584A
0x18001597f  lea     rdi, [rbp+var_28]
0x180015983  sub     rdi, [rbx]
0x180015986  cmp     [rbx+8], rcx
0x18001598a  jnz     short loc_180015994
0x18001598c  mov     rcx, rbx
0x18001598f  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x180015994  and     rdi, 0FFFFFFFFFFFFFFE0h
0x180015998  add     rdi, [rbx]
0x18001599b  mov     rdx, rdi
0x18001599e  mov     rcx, [rbx+8]
0x1800159a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800159a7  jmp     loc_18001587F
0x1800159ac  lea     rcx, aStringTooLong; "string too long"
0x1800159b3  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
