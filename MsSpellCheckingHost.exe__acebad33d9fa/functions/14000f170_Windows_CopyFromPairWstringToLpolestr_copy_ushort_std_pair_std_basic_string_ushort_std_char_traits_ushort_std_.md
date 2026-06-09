# Windows::CopyFromPairWstringToLpolestr::copy(ushort * *,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const *)

- ea: `0x14000f170`
- end: `0x14000f37f`
- name: `?copy@CopyFromPairWstringToLpolestr@Windows@@SAJPEAPEAGPEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000ba60`

## callees

- `0x140006dec`
- `0x1400082ac`
- `0x14000eeb4`
- `0x14000f060`
- `0x14000f170`
- `0x140011e10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000f25e`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f27d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f2a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f34e`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f25e`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f27d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f2a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f34e`
- `msvcrt!memcpy_s` at `0x14000f31d`
- `msvcrt!memcpy_s` at `0x14000f31d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000f2d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000f2d6`

## pseudocode

```c
__int64 __fastcall Windows::CopyFromPairWstringToLpolestr::copy(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  void **v5; // rdx
  char v6; // bl
  __int64 v7; // rax
  _QWORD *v8; // rax
  unsigned int v9; // eax
  __int64 v10; // r14
  unsigned __int64 v11; // rax
  void *v12; // rcx
  unsigned int v13; // ebx
  void **v14; // r8
  void *Source[2]; // [rsp+28h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-90h]
  unsigned __int64 v18; // [rsp+40h] [rbp-88h]
  void *v19[3]; // [rsp+48h] [rbp-80h] BYREF
  unsigned __int64 v20; // [rsp+60h] [rbp-68h]
  void *v21[3]; // [rsp+68h] [rbp-60h] BYREF
  unsigned __int64 v22; // [rsp+80h] [rbp-48h]
  void *v23[4]; // [rsp+88h] [rbp-40h] BYREF

  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    *a1 = 0;
    v18 = 7;
    v17 = 0;
    LOWORD(Source[0]) = 0;
    v3 = a2 + 32;
    if ( *(_QWORD *)(a2 + 48) )
    {
      v7 = std::operator+<unsigned short>(v21);
      v8 = (_QWORD *)std::wstring::append(v7, v3);
      std::wstring::wstring(v23, v8);
      v5 = v23;
      v6 = 22;
      v4 = -1;
    }
    else
    {
      v20 = 7;
      v19[2] = 0;
      LOWORD(v19[0]) = 0;
      v4 = -1;
      std::wstring::assign(v19, (void **)a2, 0, 0xFFFFFFFFFFFFFFFFuLL);
      v5 = v19;
      v6 = 1;
    }
    std::wstring::assign(Source, v5, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( (v6 & 4) != 0 )
    {
      v6 &= ~4u;
      if ( v23[3] >= (void *)8 )
        operator delete(v23[0]);
    }
    if ( (v6 & 2) != 0 )
    {
      v6 &= ~2u;
      if ( v22 >= 8 )
        operator delete(v21[0]);
      v22 = 7;
      v21[2] = 0;
      LOWORD(v21[0]) = 0;
    }
    if ( (v6 & 1) != 0 && v20 >= 8 )
      operator delete(v19[0]);
    *a1 = 0;
    v9 = v17 + 1;
    if ( (unsigned __int64)(v17 + 1) > 0xFFFFFFFF )
    {
      v13 = -2147024362;
      goto LABEL_33;
    }
    v10 = v9;
    v11 = 8LL * v9;
    if ( v11 > 0xFFFFFFFF || (v12 = CoTaskMemAlloc((unsigned int)v11), (*a1 = v12) == 0) )
    {
      v13 = -2147024882;
      goto LABEL_33;
    }
    v13 = 0;
    if ( v18 < 8 )
    {
      v14 = Source;
    }
    else
    {
      v14 = (void **)Source[0];
      if ( !Source[0] )
      {
        LODWORD(v4) = 0;
        goto LABEL_23;
      }
    }
    do
      ++v4;
    while ( *((_WORD *)v14 + v4) );
LABEL_23:
    if ( memcpy_s(v12, 2 * v10, v14, 2LL * ((int)v4 + 1)) )
      v13 = -2147467259;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v13 = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_14000F33D);
    }
  }
LABEL_33:
  if ( v18 >= 8 )
    operator delete(Source[0]);
  return v13;
}

```

## disassembly

```asm
0x14000f170  mov     r11, rsp
0x14000f173  mov     [r11+18h], rbx
0x14000f177  mov     [r11+20h], rsi
0x14000f17b  push    rdi
0x14000f17c  push    r14
0x14000f17e  push    r15
0x14000f180  sub     rsp, 0B0h
0x14000f187  mov     rax, cs:__security_cookie
0x14000f18e  xor     rax, rsp
0x14000f191  mov     [rsp+0C8h+var_20], rax
0x14000f199  mov     rsi, rcx
0x14000f19c  xor     r15d, r15d
0x14000f19f  mov     [rsp+0C8h+var_A8], r15d
0x14000f1a4  mov     [rcx], r15
0x14000f1a7  lea     r14d, [r15+7]
0x14000f1ab  mov     [rsp+0C8h+var_88], r14
0x14000f1b0  mov     [rsp+0C8h+var_90], r15
0x14000f1b5  mov     word ptr [rsp+0C8h+Source], r15w
0x14000f1bb  lea     rbx, [rdx+20h]
0x14000f1bf  cmp     [rbx+10h], r15
0x14000f1c3  jnz     short loc_14000F1EF
0x14000f1c5  mov     [r11-68h], r14
0x14000f1c9  mov     [r11-70h], r15
0x14000f1cd  mov     [r11-80h], r15w
0x14000f1d2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000f1d6  mov     r9, rdi
0x14000f1d9  xor     r8d, r8d
0x14000f1dc  lea     rcx, [r11-80h]; void *
0x14000f1e0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000f1e5  lea     rdx, [rsp+0C8h+var_80]
0x14000f1ea  lea     ebx, [rdi+2]
0x14000f1ed  jmp     short loc_14000F22E
0x14000f1ef  lea     rcx, [rsp+0C8h+var_60]
0x14000f1f4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x14000f1f9  nop
0x14000f1fa  mov     [rsp+0C8h+var_A8], 2
0x14000f202  mov     rdx, rbx
0x14000f205  mov     rcx, rax
0x14000f208  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x14000f20d  mov     rdx, rax
0x14000f210  lea     rcx, [rsp+0C8h+var_40]
0x14000f218  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14000f21d  lea     rdx, [rsp+0C8h+var_40]
0x14000f225  mov     ebx, 16h
0x14000f22a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000f22e  mov     [rsp+0C8h+var_A8], ebx
0x14000f232  mov     r9, rdi
0x14000f235  xor     r8d, r8d
0x14000f238  lea     rcx, [rsp+0C8h+Source]; void *
0x14000f23d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000f242  nop
0x14000f243  test    bl, 4
0x14000f246  jz      short loc_14000F265
0x14000f248  and     ebx, 0FFFFFFFBh
0x14000f24b  cmp     [rsp+0C8h+var_28], 8
0x14000f254  jb      short loc_14000F265
0x14000f256  mov     rcx, [rsp+0C8h+var_40]
0x14000f25e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000f264  nop
0x14000f265  test    bl, 2
0x14000f268  jz      short loc_14000F296
0x14000f26a  and     ebx, 0FFFFFFFDh
0x14000f26d  cmp     [rsp+0C8h+var_48], 8
0x14000f276  jb      short loc_14000F283
0x14000f278  mov     rcx, [rsp+0C8h+var_60]
0x14000f27d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000f283  mov     [rsp+0C8h+var_48], r14
0x14000f28b  mov     [rsp+0C8h+var_50], r15
0x14000f290  mov     word ptr [rsp+0C8h+var_60], r15w
0x14000f296  test    bl, 1
0x14000f299  jz      short loc_14000F2AF
0x14000f29b  cmp     [rsp+0C8h+var_68], 8
0x14000f2a1  jb      short loc_14000F2AF
0x14000f2a3  mov     rcx, [rsp+0C8h+var_80]
0x14000f2a8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000f2ae  nop
0x14000f2af  mov     [rsi], r15
0x14000f2b2  mov     rax, [rsp+0C8h+var_90]
0x14000f2b7  inc     rax
0x14000f2ba  mov     ecx, 0FFFFFFFFh
0x14000f2bf  cmp     rax, rcx
0x14000f2c2  ja      short loc_14000F336
0x14000f2c4  mov     r14d, eax
0x14000f2c7  lea     rax, ds:0[r14*8]
0x14000f2cf  cmp     rax, rcx
0x14000f2d2  ja      short loc_14000F32F
0x14000f2d4  mov     ecx, eax; cb
0x14000f2d6  call    cs:__imp_CoTaskMemAlloc
0x14000f2dc  mov     rcx, rax; Destination
0x14000f2df  mov     [rsi], rax
0x14000f2e2  test    rax, rax
0x14000f2e5  jz      short loc_14000F32F
0x14000f2e7  mov     ebx, r15d
0x14000f2ea  cmp     [rsp+0C8h+var_88], 8
0x14000f2f0  jb      short loc_14000F301
0x14000f2f2  mov     r8, [rsp+0C8h+Source]
0x14000f2f7  test    r8, r8
0x14000f2fa  jnz     short loc_14000F306
0x14000f2fc  mov     edi, r15d
0x14000f2ff  jmp     short loc_14000F310
0x14000f301  lea     r8, [rsp+0C8h+Source]; Source
0x14000f306  inc     rdi
0x14000f309  cmp     [r8+rdi*2], r15w
0x14000f30e  jnz     short loc_14000F306
0x14000f310  lea     eax, [rdi+1]
0x14000f313  movsxd  r9, eax
0x14000f316  add     r9, r9; SourceSize
0x14000f319  lea     rdx, [r14+r14]; DestinationSize
0x14000f31d  call    cs:__imp_memcpy_s
0x14000f323  mov     ecx, 80004005h
0x14000f328  test    eax, eax
0x14000f32a  cmovnz  ebx, ecx
0x14000f32d  jmp     short loc_14000F341
0x14000f32f  mov     ebx, 8007000Eh
0x14000f334  jmp     short loc_14000F341
0x14000f336  mov     ebx, 80070216h
0x14000f33b  jmp     short loc_14000F341
0x14000f33d  mov     ebx, [rsp+0C8h+var_A8]
0x14000f341  cmp     [rsp+0C8h+var_88], 8
0x14000f347  jb      short loc_14000F354
0x14000f349  mov     rcx, [rsp+0C8h+Source]
0x14000f34e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000f354  mov     eax, ebx
0x14000f356  mov     rcx, [rsp+0C8h+var_20]
0x14000f35e  xor     rcx, rsp; StackCookie
0x14000f361  call    __security_check_cookie
0x14000f366  lea     r11, [rsp+0C8h+var_18]
0x14000f36e  mov     rbx, [r11+30h]
0x14000f372  mov     rsi, [r11+38h]
0x14000f376  mov     rsp, r11
0x14000f379  pop     r15
0x14000f37b  pop     r14
0x14000f37d  pop     rdi
0x14000f37e  retn
```
