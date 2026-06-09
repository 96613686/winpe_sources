# CMtfPredictionCandidate::_UpdateCachedStrings(void)

- ea: `0x18002aff8`
- end: `0x18002b33c`
- name: `?_UpdateCachedStrings@CMtfPredictionCandidate@@IEAAJXZ`
- size: `836`
- prototype: `__int64 __fastcall(CMtfPredictionCandidate *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x180027ef0`
- `0x180028380`
- `0x18002a2c0`
- `0x18002a5b0`

## callees

- `0x18001031c`
- `0x18002aff8`
- `0x18002b58c`
- `0x18002bc62`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002b281`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b29f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b2d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b2f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b30e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b32c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b281`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b29f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b2d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b2f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b30e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b32c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002b24d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002b268`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002b24d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002b268`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b033`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b041`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b033`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b041`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b19f`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b1b7`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b201`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b219`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b19f`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b1b7`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b201`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b219`

## pseudocode

```c
__int64 __fastcall CMtfPredictionCandidate::_UpdateCachedStrings(CMtfPredictionCandidate *this)
{
  unsigned __int64 v2; // rsi
  __int64 v3; // r15
  unsigned int v4; // edi
  __int64 v5; // rcx
  bool v6; // sf
  void (*v7)(void); // rax
  OLECHAR *v8; // rsi
  OLECHAR *v9; // r14
  bool v10; // zf
  int (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rcx
  const OLECHAR *v12; // rcx
  const OLECHAR *v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  BSTR pbstr[2]; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v18[2]; // [rsp+40h] [rbp-C0h]
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR *v22; // [rsp+78h] [rbp-88h]
  OLECHAR *v23; // [rsp+80h] [rbp-80h]
  int v24; // [rsp+88h] [rbp-78h]
  OLECHAR *Src[2]; // [rsp+C0h] [rbp-40h] BYREF
  UINT v26[2]; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v27; // [rsp+D8h] [rbp-28h]
  OLECHAR *strIn[2]; // [rsp+E0h] [rbp-20h] BYREF
  UINT ui[2]; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v30; // [rsp+F8h] [rbp-8h]

  if ( *((_BYTE *)this + 116) )
    return 0;
  SysFreeString(*((BSTR *)this + 11));
  *((_QWORD *)this + 11) = 0;
  SysFreeString(*((BSTR *)this + 10));
  *((_QWORD *)this + 10) = 0;
  v2 = 7;
  v30 = 7;
  *(_QWORD *)ui = 0;
  LOWORD(strIn[0]) = 0;
  v27 = 7;
  *(_QWORD *)v26 = 0;
  LOWORD(Src[0]) = 0;
  *(_OWORD *)pbstr = 0;
  *(_OWORD *)v18 = 0;
  v19 = 0;
  v20 = 0;
  LODWORD(pbstr[0]) = 7;
  memset_0(&v21, 0, 0x48u);
  v21 = 7;
  v3 = (__int64)(*((_QWORD *)this + 7) - *((_QWORD *)this + 6)) >> 3;
  v4 = 0;
  if ( !(_DWORD)v3 )
  {
LABEL_17:
    v12 = (const OLECHAR *)strIn;
    if ( v2 >= 8 )
      v12 = strIn[0];
    *((_QWORD *)this + 11) = SysAllocStringLen(v12, ui[0]);
    v13 = (const OLECHAR *)Src;
    if ( v27 >= 8 )
      v13 = Src[0];
    *((_QWORD *)this + 10) = SysAllocStringLen(v13, v26[0]);
    *((_BYTE *)this + 116) = 1;
    if ( v27 >= 8 )
      operator delete(Src[0]);
    v27 = 7;
    *(_QWORD *)v26 = 0;
    LOWORD(Src[0]) = 0;
    if ( v30 >= 8 )
      operator delete(strIn[0]);
    return 0;
  }
  while ( 1 )
  {
    v5 = *((_QWORD *)this + 6);
    if ( *(_QWORD *)(v5 + 8LL * v4) )
      break;
LABEL_15:
    if ( ++v4 >= (unsigned int)v3 )
    {
      v2 = v30;
      goto LABEL_17;
    }
  }
  v15 = 0;
  v16 = 0;
  if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(v5 + 8LL * v4))(
         *(_QWORD *)(v5 + 8LL * v4),
         &GUID_92445657_1419_4aaa_a92f_486ab29470c0,
         &v15) >= 0 )
  {
    v6 = (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v15 + 40LL))(v15, pbstr) < 0;
    v7 = *(void (**)(void))(*(_QWORD *)v15 + 16LL);
    if ( v6 )
      goto LABEL_26;
    v7();
    v8 = pbstr[1];
    v9 = v18[0];
    v10 = (_DWORD)v19 == 0;
LABEL_10:
    if ( v4 )
    {
      if ( !v10 )
      {
        std::wstring::append(strIn, L" ");
        std::wstring::append(Src, L" ");
      }
      SysStringLen(v8);
      std::wstring::append(strIn, v8);
      SysStringLen(v9);
      std::wstring::append(Src, v9);
    }
    else
    {
      SysStringLen(v8);
      std::wstring::assign(strIn, v8);
      SysStringLen(v9);
      std::wstring::assign(Src, v9);
    }
    goto LABEL_15;
  }
  v11 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 6) + 8LL * v4);
  if ( (**v11)(v11, &GUID_c4445657_6908_45eb_a6b9_2f1ea4b2a03a, &v16) >= 0 )
  {
    v6 = (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 40LL))(v16, &v21) < 0;
    v7 = *(void (**)(void))(*(_QWORD *)v16 + 16LL);
    if ( v6 )
    {
LABEL_26:
      v7();
      if ( v27 >= 8 )
        operator delete(Src[0]);
      LOWORD(Src[0]) = 0;
      *(_QWORD *)v26 = 0;
      v27 = 7;
      if ( v30 >= 8 )
        operator delete(strIn[0]);
      return 2147500037LL;
    }
    v7();
    v8 = v22;
    v9 = v23;
    v10 = v24 == 0;
    goto LABEL_10;
  }
  if ( v27 >= 8 )
    operator delete(Src[0]);
  v27 = 7;
  *(_QWORD *)v26 = 0;
  LOWORD(Src[0]) = 0;
  if ( v30 >= 8 )
    operator delete(strIn[0]);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18002aff8  push    rbp
0x18002affa  push    rbx
0x18002affb  push    rsi
0x18002affc  push    rdi
0x18002affd  push    r12
0x18002afff  push    r13
0x18002b001  push    r14
0x18002b003  push    r15
0x18002b005  lea     rbp, [rsp-18h]
0x18002b00a  sub     rsp, 118h
0x18002b011  mov     rax, cs:__security_cookie
0x18002b018  xor     rax, rsp
0x18002b01b  mov     [rbp+50h+var_50], rax
0x18002b01f  mov     rbx, rcx
0x18002b022  xor     r12d, r12d
0x18002b025  cmp     [rcx+74h], r12b
0x18002b029  jnz     loc_18002B2A5
0x18002b02f  mov     rcx, [rcx+58h]; bstrString
0x18002b033  call    cs:__imp_SysFreeString
0x18002b039  mov     [rbx+58h], r12
0x18002b03d  mov     rcx, [rbx+50h]; bstrString
0x18002b041  call    cs:__imp_SysFreeString
0x18002b047  mov     [rbx+50h], r12
0x18002b04b  lea     r13d, [r12+7]
0x18002b050  mov     esi, r13d
0x18002b053  mov     [rbp+50h+var_58], r13
0x18002b057  mov     qword ptr [rbp+50h+ui], r12
0x18002b05b  mov     word ptr [rbp+50h+strIn], r12w
0x18002b060  mov     [rbp+50h+var_78], r13
0x18002b064  mov     qword ptr [rbp+50h+var_80], r12
0x18002b068  mov     word ptr [rbp+50h+Src], r12w
0x18002b06d  xorps   xmm0, xmm0
0x18002b070  xor     eax, eax
0x18002b072  movups  xmmword ptr [rsp+150h+pbstr], xmm0
0x18002b077  movups  xmmword ptr [rsp+150h+var_110], xmm0
0x18002b07c  movups  [rsp+150h+var_100], xmm0
0x18002b081  mov     [rsp+150h+var_F0], rax
0x18002b086  mov     dword ptr [rsp+150h+pbstr], r13d
0x18002b08b  xor     edx, edx; Val
0x18002b08d  lea     r8d, [r12+48h]; Size
0x18002b092  lea     rcx, [rsp+150h+var_E0]; void *
0x18002b097  call    memset_0
0x18002b09c  mov     [rsp+150h+var_E0], r13d
0x18002b0a1  mov     r15, [rbx+38h]
0x18002b0a5  sub     r15, [rbx+30h]
0x18002b0a9  sar     r15, 3
0x18002b0ad  mov     edi, r12d
0x18002b0b0  test    r15d, r15d
0x18002b0b3  jz      loc_18002B23D
0x18002b0b9  mov     esi, edi
0x18002b0bb  mov     rcx, [rbx+30h]
0x18002b0bf  cmp     [rcx+rsi*8], r12
0x18002b0c3  jz      loc_18002B22E
0x18002b0c9  mov     [rsp+150h+var_130], r12
0x18002b0ce  mov     [rsp+150h+var_128], r12
0x18002b0d3  mov     rcx, [rcx+rsi*8]
0x18002b0d7  mov     rax, [rcx]
0x18002b0da  lea     r8, [rsp+150h+var_130]
0x18002b0df  lea     rdx, _GUID_92445657_1419_4aaa_a92f_486ab29470c0
0x18002b0e6  mov     rax, [rax]
0x18002b0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0ee  test    eax, eax
0x18002b0f0  js      short loc_18002B132
0x18002b0f2  mov     rcx, [rsp+150h+var_130]
0x18002b0f7  mov     rax, [rcx]
0x18002b0fa  lea     rdx, [rsp+150h+pbstr]
0x18002b0ff  mov     rax, [rax+28h]
0x18002b103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b108  mov     rcx, [rsp+150h+var_130]
0x18002b10d  test    eax, eax
0x18002b10f  mov     rax, [rcx]
0x18002b112  mov     rax, [rax+10h]
0x18002b116  js      loc_18002B2C7
0x18002b11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b121  mov     rsi, [rsp+150h+pbstr+8]
0x18002b126  mov     r14, [rsp+150h+var_110]
0x18002b12b  cmp     dword ptr [rsp+150h+var_100], r12d
0x18002b130  jmp     short loc_18002B195
0x18002b132  mov     rax, [rbx+30h]
0x18002b136  mov     rcx, [rax+rsi*8]
0x18002b13a  mov     rax, [rcx]
0x18002b13d  lea     r8, [rsp+150h+var_128]
0x18002b142  lea     rdx, _GUID_c4445657_6908_45eb_a6b9_2f1ea4b2a03a
0x18002b149  mov     rax, [rax]
0x18002b14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b151  test    eax, eax
0x18002b153  js      loc_18002B303
0x18002b159  mov     rcx, [rsp+150h+var_128]
0x18002b15e  mov     rax, [rcx]
0x18002b161  lea     rdx, [rsp+150h+var_E0]
0x18002b166  mov     rax, [rax+28h]
0x18002b16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b16f  mov     rcx, [rsp+150h+var_128]
0x18002b174  test    eax, eax
0x18002b176  mov     rax, [rcx]
0x18002b179  mov     rax, [rax+10h]
0x18002b17d  js      loc_18002B2C7
0x18002b183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b188  mov     rsi, [rsp+150h+var_D8]
0x18002b18d  mov     r14, [rbp+50h+var_D0]
0x18002b191  cmp     [rbp+50h+var_C8], r12d
0x18002b195  setnz   al
0x18002b198  test    edi, edi
0x18002b19a  jnz     short loc_18002B1CE
0x18002b19c  mov     rcx, rsi; pbstr
0x18002b19f  call    cs:__imp_SysStringLen
0x18002b1a5  mov     r8d, eax
0x18002b1a8  mov     rdx, rsi; Src
0x18002b1ab  lea     rcx, [rbp+50h+strIn]; void *
0x18002b1af  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002b1b4  mov     rcx, r14; pbstr
0x18002b1b7  call    cs:__imp_SysStringLen
0x18002b1bd  mov     r8d, eax
0x18002b1c0  mov     rdx, r14; Src
0x18002b1c3  lea     rcx, [rbp+50h+Src]; void *
0x18002b1c7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002b1cc  jmp     short loc_18002B22E
0x18002b1ce  test    al, al
0x18002b1d0  jz      short loc_18002B1FE
0x18002b1d2  mov     r8d, 1
0x18002b1d8  lea     rdx, asc_180035654; " "
0x18002b1df  lea     rcx, [rbp+50h+strIn]; Src
0x18002b1e3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002b1e8  mov     r8d, 1
0x18002b1ee  lea     rdx, asc_180035654; " "
0x18002b1f5  lea     rcx, [rbp+50h+Src]; Src
0x18002b1f9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002b1fe  mov     rcx, rsi; pbstr
0x18002b201  call    cs:__imp_SysStringLen
0x18002b207  mov     r8d, eax
0x18002b20a  mov     rdx, rsi; void *
0x18002b20d  lea     rcx, [rbp+50h+strIn]; Src
0x18002b211  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002b216  mov     rcx, r14; pbstr
0x18002b219  call    cs:__imp_SysStringLen
0x18002b21f  mov     r8d, eax
0x18002b222  mov     rdx, r14; void *
0x18002b225  lea     rcx, [rbp+50h+Src]; Src
0x18002b229  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002b22e  inc     edi
0x18002b230  cmp     edi, r15d
0x18002b233  jb      loc_18002B0B9
0x18002b239  mov     rsi, [rbp+50h+var_58]
0x18002b23d  lea     rcx, [rbp+50h+strIn]
0x18002b241  cmp     rsi, 8
0x18002b245  cmovnb  rcx, [rbp+50h+strIn]; strIn
0x18002b24a  mov     edx, [rbp+50h+ui]; ui
0x18002b24d  call    cs:__imp_SysAllocStringLen
0x18002b253  mov     [rbx+58h], rax
0x18002b257  lea     rcx, [rbp+50h+Src]
0x18002b25b  cmp     [rbp+50h+var_78], 8
0x18002b260  cmovnb  rcx, [rbp+50h+Src]; strIn
0x18002b265  mov     edx, [rbp+50h+var_80]; ui
0x18002b268  call    cs:__imp_SysAllocStringLen
0x18002b26e  mov     [rbx+50h], rax
0x18002b272  mov     byte ptr [rbx+74h], 1
0x18002b276  cmp     [rbp+50h+var_78], 8
0x18002b27b  jb      short loc_18002B287
0x18002b27d  mov     rcx, [rbp+50h+Src]
0x18002b281  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b287  mov     [rbp+50h+var_78], r13
0x18002b28b  mov     qword ptr [rbp+50h+var_80], r12
0x18002b28f  mov     word ptr [rbp+50h+Src], r12w
0x18002b294  cmp     [rbp+50h+var_58], 8
0x18002b299  jb      short loc_18002B2A5
0x18002b29b  mov     rcx, [rbp+50h+strIn]
0x18002b29f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b2a5  xor     eax, eax
0x18002b2a7  mov     rcx, [rbp+50h+var_50]
0x18002b2ab  xor     rcx, rsp; StackCookie
0x18002b2ae  call    __security_check_cookie
0x18002b2b3  add     rsp, 118h
0x18002b2ba  pop     r15
0x18002b2bc  pop     r14
0x18002b2be  pop     r13
0x18002b2c0  pop     r12
0x18002b2c2  pop     rdi
0x18002b2c3  pop     rsi
0x18002b2c4  pop     rbx
0x18002b2c5  pop     rbp
0x18002b2c6  retn
0x18002b2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2cc  nop
0x18002b2cd  cmp     [rbp+50h+var_78], 8
0x18002b2d2  jb      short loc_18002B2DE
0x18002b2d4  mov     rcx, [rbp+50h+Src]
0x18002b2d8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b2de  mov     word ptr [rbp+50h+Src], r12w
0x18002b2e3  mov     qword ptr [rbp+50h+var_80], r12
0x18002b2e7  mov     [rbp+50h+var_78], r13
0x18002b2eb  cmp     [rbp+50h+var_58], 8
0x18002b2f0  jb      short loc_18002B2FC
0x18002b2f2  mov     rcx, [rbp+50h+strIn]
0x18002b2f6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b2fc  mov     eax, 80004005h
0x18002b301  jmp     short loc_18002B2A7
0x18002b303  cmp     [rbp+50h+var_78], 8
0x18002b308  jb      short loc_18002B314
0x18002b30a  mov     rcx, [rbp+50h+Src]
0x18002b30e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b314  mov     [rbp+50h+var_78], r13
0x18002b318  mov     qword ptr [rbp+50h+var_80], r12
0x18002b31c  mov     word ptr [rbp+50h+Src], r12w
0x18002b321  cmp     [rbp+50h+var_58], 8
0x18002b326  jb      short loc_18002B332
0x18002b328  mov     rcx, [rbp+50h+strIn]
0x18002b32c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b332  mov     eax, 8000FFFFh
0x18002b337  jmp     loc_18002B2A7
```
