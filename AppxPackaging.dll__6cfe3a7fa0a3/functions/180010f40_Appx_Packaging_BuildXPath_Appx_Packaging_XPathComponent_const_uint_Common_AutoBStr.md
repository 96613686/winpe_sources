# Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)

- ea: `0x180010f40`
- end: `0x180011506`
- name: `?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z`
- size: `1478`
- prototype: `__int64 __fastcall(Appx::Packaging *this, const struct Appx::Packaging::XPathComponent *, BSTR *, struct Common::AutoBStr *)`
- caller_count: `76`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000bac0`
- `0x18000d010`
- `0x18000e420`
- `0x18000eaf0`
- `0x18000f3f4`
- `0x18000f7d0`
- `0x180010454`
- `0x1800104a0`
- `0x180011a70`
- `0x180011cd0`
- `0x180013d5c`
- `0x180013e00`
- `0x180014630`
- `0x180014c80`
- `0x180014ef0`
- `0x1800154e4`
- `0x1800159f0`
- `0x180015b40`
- `0x1800160e8`
- `0x1800164a4`
- `0x180016eb0`
- `0x180018b70`
- `0x180018c60`
- `0x1800192d4`
- `0x1800199a4`
- `0x18001b1a8`
- `0x18001c1b4`
- `0x18001c8a8`
- `0x18002119c`
- `0x180021514`
- `0x18002179c`
- `0x18002191c`
- `0x180022400`
- `0x18002dd14`
- `0x18002ed4c`
- `0x18002f11c`
- `0x180030a18`
- `0x180033250`
- `0x180033bd8`
- `0x180035d8c`
- `0x1800362f4`
- `0x1800369a0`
- `0x180038bf8`
- `0x18003d5e4`
- `0x1800426b0`
- `0x180044a38`
- `0x180049210`
- `0x180049b60`
- `0x18004fe00`
- `0x1800501fc`

## callees

- `0x180010f40`
- `0x1800423a0`
- `0x180071f50`
- `0x1800992c4`
- `0x18009d729`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180011008`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180011008`
- `OLEAUT32!__imp_SysFreeString` at `0x180010fb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180010fb2`

## string_xrefs

- `0x18001125d`: `onecore\printscan\appxpackaging\lib\core\src\xpathhelper.cpp`
- `0x180011488`: `onecore\printscan\appxpackaging\lib\core\src\xpathhelper.cpp`
- `0x1800114ed`: `onecore\printscan\appxpackaging\lib\core\src\xpathhelper.cpp`
- `0x180011230`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180011240`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800112dd`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001130c`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001131c`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180011352`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180011362`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800113a2`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180011470`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800114b5`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::BuildXPath(
        Appx::Packaging *this,
        const struct Appx::Packaging::XPathComponent *a2,
        BSTR *a3,
        struct Common::AutoBStr *a4)
{
  OLECHAR **v4; // r9
  void **v5; // r10
  unsigned int v6; // r14d
  __int64 v8; // rbx
  int v9; // ebx
  const OLECHAR *v10; // rdi
  unsigned __int64 v11; // rdx
  const OLECHAR *v12; // rax
  __int64 v13; // rcx
  BSTR v14; // rax
  char *v16; // r12
  unsigned int v17; // r13d
  int v18; // eax
  unsigned int v19; // edi
  char *v20; // rdi
  int v21; // eax
  __int64 v22; // r13
  int v23; // eax
  OLECHAR *v24; // rcx
  __int64 v25; // rsi
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 v29; // rdx
  unsigned __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // r9
  __int64 v36; // r13
  int v37; // eax
  unsigned int v38; // esi
  OLECHAR *v39; // rcx
  unsigned int v40; // esi
  __int64 v41; // r13
  int v42; // eax
  unsigned __int64 v43; // rdx
  void **v44; // [rsp+20h] [rbp-38h] BYREF
  OLECHAR **v45; // [rsp+28h] [rbp-30h]
  OLECHAR **v46; // [rsp+30h] [rbp-28h]
  OLECHAR *strIn[2]; // [rsp+38h] [rbp-20h] BYREF
  int v48; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  int v50; // [rsp+98h] [rbp+40h]
  void *Src; // [rsp+A8h] [rbp+50h]
  void *Srca; // [rsp+A8h] [rbp+50h]

  v48 = 0;
  v4 = strIn;
  v45 = strIn;
  v46 = strIn;
  v5 = &Common::StringBufferBuilder::`vftable';
  v6 = (unsigned int)a2;
  v44 = &Common::StringBufferBuilder::`vftable';
  v8 = 0;
  *(_OWORD *)strIn = 0;
  while ( 1 )
  {
    if ( (unsigned int)v8 >= v6 )
    {
      v9 = 0;
      v10 = strIn[1];
      SysFreeString(*a3);
      *a3 = 0;
      if ( v10 )
      {
        v12 = v10;
        v13 = 0x7FFFFFFF;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v13;
        }
        while ( v13 );
        v9 = -2147024809;
        if ( v13 )
        {
          v11 = 0;
          if ( (unsigned int)(0x7FFFFFFF - v13) <= 0x3FFFFFFF )
          {
            v14 = SysAllocStringLen(v10, 0x7FFFFFFF - (int)v13);
            v9 = 0;
            *a3 = v14;
            if ( !v14 )
              v9 = -2147024882;
          }
          if ( v9 >= 0 )
            goto LABEL_12;
        }
        else
        {
          v9 = -2147024809;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x42,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xpathhelper.cpp",
          (const char *)(unsigned int)v9,
          (int)v44);
      }
LABEL_12:
      if ( strIn[1] )
        operator delete(strIn[1], v11);
      return (unsigned int)v9;
    }
    if ( (_DWORD)v8 )
    {
      if ( *(_DWORD *)v4 == 0x3FFFFFFF )
      {
        v19 = -2147023613;
      }
      else
      {
        v31 = ((__int64 (__fastcall *)(void ***, _QWORD))*v5)(&v44, (unsigned int)(*(_DWORD *)v4 + 1));
        v19 = v31;
        if ( v31 >= 0 )
        {
          v45[1][*(_DWORD *)v45 - 1] = 47;
          v4 = v45;
          v5 = v44;
          goto LABEL_16;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B,
          (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
          (const char *)(unsigned int)v31,
          (int)v44);
      }
      v29 = 41;
      goto LABEL_38;
    }
LABEL_16:
    v16 = (char *)this + 40 * v8;
    if ( (unsigned int)(*(_DWORD *)v16 - 4) > 1 )
      goto LABEL_17;
    if ( *(_DWORD *)v4 == 0x3FFFFFFF )
    {
      v19 = -2147023613;
      goto LABEL_47;
    }
    v21 = ((__int64 (__fastcall *)(void ***, _QWORD))*v5)(&v44, (unsigned int)(*(_DWORD *)v4 + 1));
    v19 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v21,
        (int)v44);
LABEL_47:
      v29 = 45;
      goto LABEL_38;
    }
    v45[1][*(_DWORD *)v45 - 1] = 64;
    v4 = v45;
    v5 = v44;
LABEL_17:
    if ( ((*(_DWORD *)v16 - 3) & 0xFFFFFFFD) != 0 )
      goto LABEL_18;
    v22 = *(unsigned int *)v4;
    if ( (unsigned int)v22 > 0xFFFFFFEF )
    {
      v19 = -2147024362;
      v32 = 263;
      v33 = 2147942934LL;
      goto LABEL_49;
    }
    if ( (unsigned int)(v22 + 16) > 0x3FFFFFFF )
    {
      v19 = -2147023613;
      goto LABEL_50;
    }
    v23 = ((__int64 (__fastcall *)(void ***))*v5)(&v44);
    v19 = v23;
    if ( v23 < 0 )
    {
      v33 = (unsigned int)v23;
      v32 = 269;
LABEL_49:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v33,
        (int)v44);
LABEL_50:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v19,
        (int)v44);
      v29 = 49;
      goto LABEL_38;
    }
    v24 = v45[1];
    *(_OWORD *)&v24[v22] = xmmword_180117790;
    *(_OWORD *)&v24[v22 + 8] = xmmword_1801177A0;
    v4 = v45;
    v5 = v44;
LABEL_18:
    v17 = *((_DWORD *)this + 10 * v8 + 4);
    v50 = *(_DWORD *)v4;
    if ( *(_DWORD *)v4 > ~v17 )
    {
      v19 = -2147024362;
      v27 = 263;
      v28 = 2147942934LL;
LABEL_36:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v28,
        (int)v44);
LABEL_37:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v19,
        (int)v44);
      v29 = 51;
      goto LABEL_38;
    }
    if ( *(_DWORD *)v4 + v17 > 0x3FFFFFFF )
    {
      v19 = -2147023613;
      goto LABEL_37;
    }
    Src = (void *)*((_QWORD *)this + 5 * v8 + 1);
    v18 = ((__int64 (__fastcall *)(void ***))*v5)(&v44);
    v19 = v18;
    if ( v18 < 0 )
    {
      v28 = (unsigned int)v18;
      v27 = 269;
      goto LABEL_36;
    }
    memcpy_0(&v45[1][v50], Src, 2LL * v17);
    v20 = (char *)this + 40 * v8;
    if ( *((_DWORD *)v20 + 8) )
    {
      if ( ((*((_DWORD *)this + 10 * v8) - 3) & 0xFFFFFFFD) == 0 )
        break;
    }
LABEL_22:
    if ( ((*(_DWORD *)v16 - 3) & 0xFFFFFFFD) != 0 )
      goto LABEL_23;
    v25 = *(unsigned int *)v45;
    if ( (unsigned int)v25 > 0xFFFFFFFD )
    {
      v19 = -2147024362;
      v34 = 263;
      v35 = 2147942934LL;
      goto LABEL_53;
    }
    if ( (unsigned int)(v25 + 2) > 0x3FFFFFFF )
    {
      v19 = -2147023613;
      goto LABEL_54;
    }
    v26 = ((__int64 (__fastcall *)(void ***))*v44)(&v44);
    v19 = v26;
    if ( v26 < 0 )
    {
      v35 = (unsigned int)v26;
      v34 = 269;
LABEL_53:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v35,
        (int)v44);
LABEL_54:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v19,
        (int)v44);
      v29 = 62;
      goto LABEL_38;
    }
    *(_DWORD *)&v45[1][v25] = 6094887;
LABEL_23:
    v4 = v45;
    v8 = (unsigned int)(v8 + 1);
    v5 = v44;
  }
  v36 = *(unsigned int *)v45;
  v37 = Common::StringBuilder::Insert((Common::StringBuilder *)&v44, *(_DWORD *)v45, 0x17u);
  v38 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v37,
      (int)v44);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xpathhelper.cpp",
      (const char *)v38,
      (int)v44);
    if ( strIn[1] )
      operator delete(strIn[1], v43);
    return v38;
  }
  v39 = v45[1];
  *(_OWORD *)&v39[v36] = xmmword_180117C00;
  *(_OWORD *)&v39[v36 + 8] = xmmword_180117C10;
  *(_OWORD *)&v39[v36 + 15] = *(__int128 *)((char *)&xmmword_180117C10 + 14);
  v40 = *((_DWORD *)v20 + 8);
  Srca = (void *)*((_QWORD *)v16 + 3);
  v41 = *(unsigned int *)v45;
  v42 = Common::StringBuilder::Insert((Common::StringBuilder *)&v44, *(_DWORD *)v45, v40);
  v19 = v42;
  if ( v42 >= 0 )
  {
    memcpy_0(&v45[1][v41], Srca, 2LL * v40);
    goto LABEL_22;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x79,
    (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)(unsigned int)v42,
    (int)v44);
  v29 = 57;
LABEL_38:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v29,
    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xpathhelper.cpp",
    (const char *)v19,
    (int)v44);
  if ( strIn[1] )
    operator delete(strIn[1], v30);
  return v19;
}

```

## disassembly

```asm
0x180010f40  mov     [rsp-30h+arg_10], r8
0x180010f45  push    rbp
0x180010f46  push    rbx
0x180010f47  push    rsi
0x180010f48  push    r13
0x180010f4a  push    r14
0x180010f4c  push    r15
0x180010f4e  mov     rbp, rsp
0x180010f51  sub     rsp, 58h
0x180010f55  xor     eax, eax
0x180010f57  mov     [rsp+58h+arg_0], rdi
0x180010f5f  mov     [rbp+var_10], eax
0x180010f62  lea     r9, [rbp+strIn]
0x180010f66  lea     rax, [rbp+strIn]
0x180010f6a  mov     [rbp+var_30], r9
0x180010f6e  xorps   xmm0, xmm0
0x180010f71  mov     [rbp+var_28], rax
0x180010f75  lea     r10, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180010f7c  mov     [rsp+58h+var_8], r12
0x180010f81  mov     r14d, edx
0x180010f84  mov     [rbp+var_38], r10
0x180010f88  mov     r15, rcx
0x180010f8b  xor     ebx, ebx
0x180010f8d  movups  xmmword ptr [rbp+strIn], xmm0
0x180010f91  mov     r13d, 40h ; '@'
0x180010f97  mov     esi, 2Fh ; '/'
0x180010f9c  cmp     ebx, r14d
0x180010f9f  jb      loc_180011058
0x180010fa5  mov     rsi, [rbp+arg_10]
0x180010fa9  xor     ebx, ebx
0x180010fab  mov     rdi, [rbp+strIn+8]
0x180010faf  mov     rcx, [rsi]; bstrString
0x180010fb2  call    cs:__imp_SysFreeString
0x180010fb9  nop     dword ptr [rax+rax+00h]
0x180010fbe  mov     [rsi], rbx
0x180010fc1  test    rdi, rdi
0x180010fc4  jz      short loc_18001102C
0x180010fc6  mov     r8d, 7FFFFFFFh
0x180010fcc  mov     rax, rdi
0x180010fcf  mov     ecx, r8d
0x180010fd2  cmp     [rax], bx
0x180010fd5  jz      short loc_180010FE1
0x180010fd7  add     rax, 2
0x180010fdb  sub     rcx, 1
0x180010fdf  jnz     short loc_180010FD2
0x180010fe1  xor     eax, eax
0x180010fe3  mov     ebx, 80070057h
0x180010fe8  test    rcx, rcx
0x180010feb  mov     edx, ebx
0x180010fed  cmovnz  edx, eax
0x180010ff0  jz      loc_1800114E7
0x180010ff6  sub     r8d, ecx
0x180010ff9  cmp     r8d, 3FFFFFFFh
0x180011000  ja      short loc_180011024
0x180011002  mov     edx, r8d; ui
0x180011005  mov     rcx, rdi; strIn
0x180011008  call    cs:__imp_SysAllocStringLen
0x18001100f  nop     dword ptr [rax+rax+00h]
0x180011014  xor     ebx, ebx
0x180011016  mov     ecx, 8007000Eh
0x18001101b  test    rax, rax
0x18001101e  mov     [rsi], rax
0x180011021  cmovz   ebx, ecx
0x180011024  test    ebx, ebx
0x180011026  js      loc_1800114E9
0x18001102c  mov     rcx, [rbp+strIn+8]; void *
0x180011030  test    rcx, rcx
0x180011033  jz      short loc_18001103A
0x180011035  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001103a  mov     eax, ebx
0x18001103c  mov     r12, [rsp+58h+var_8]
0x180011041  mov     rdi, [rsp+58h+arg_0]
0x180011049  add     rsp, 58h
0x18001104d  pop     r15
0x18001104f  pop     r14
0x180011051  pop     r13
0x180011053  pop     rsi
0x180011054  pop     rbx
0x180011055  pop     rbp
0x180011056  retn
0x180011058  test    ebx, ebx
0x18001105a  jnz     loc_180011288
0x180011060  lea     rax, [rbx+rbx*4]
0x180011064  lea     r12, [r15+rax*8]
0x180011068  mov     eax, [r15+rax*8]
0x18001106c  sub     eax, 4
0x18001106f  cmp     eax, 1
0x180011072  jbe     loc_18001112D
0x180011078  mov     eax, [r12]
0x18001107c  sub     eax, 3
0x18001107f  test    eax, 0FFFFFFFDh
0x180011084  jz      loc_180011172
0x18001108a  mov     ecx, [r9]
0x18001108d  lea     rax, [rbx+rbx*4]
0x180011091  mov     r13d, [r15+rax*8+10h]
0x180011096  mov     eax, r13d
0x180011099  mov     [rbp+arg_8], ecx
0x18001109c  not     eax
0x18001109e  cmp     ecx, eax
0x1800110a0  ja      loc_18001121F
0x1800110a6  lea     edx, [rcx+r13]
0x1800110aa  cmp     edx, 3FFFFFFFh
0x1800110b0  ja      loc_180011281
0x1800110b6  lea     rax, [rbx+rbx*4]
0x1800110ba  mov     rax, [r15+rax*8+8]
0x1800110bf  lea     rcx, [rbp+var_38]
0x1800110c3  mov     [rbp+Src], rax
0x1800110c7  mov     rax, [r10]
0x1800110ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110cf  mov     edi, eax
0x1800110d1  test    eax, eax
0x1800110d3  js      loc_1800112CC
0x1800110d9  mov     rax, [rbp+var_30]
0x1800110dd  mov     r8d, r13d
0x1800110e0  mov     r9d, [rbp+arg_8]
0x1800110e4  add     r8, r8; Size
0x1800110e7  mov     rdx, [rbp+Src]; Src
0x1800110eb  mov     rcx, [rax+8]
0x1800110ef  lea     rcx, [rcx+r9*2]; void *
0x1800110f3  call    memcpy_0
0x1800110f8  lea     rax, [rbx+rbx*4]
0x1800110fc  cmp     dword ptr [r15+rax*8+20h], 0
0x180011102  lea     rdi, [r15+rax*8]
0x180011106  ja      loc_1800113C0
0x18001110c  mov     eax, [r12]
0x180011110  sub     eax, 3
0x180011113  test    eax, 0FFFFFFFDh
0x180011118  jz      loc_1800111D3
0x18001111e  mov     r9, [rbp+var_30]
0x180011122  inc     ebx
0x180011124  mov     r10, [rbp+var_38]
0x180011128  jmp     loc_180010F91
0x18001112d  mov     edx, [r9]
0x180011130  cmp     edx, 3FFFFFFFh
0x180011136  jz      loc_1800114DD
0x18001113c  mov     rax, [r10]
0x18001113f  lea     rcx, [rbp+var_38]
0x180011143  inc     edx
0x180011145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001114a  mov     edi, eax
0x18001114c  test    eax, eax
0x18001114e  js      loc_1800112D9
0x180011154  mov     rdx, [rbp+var_30]
0x180011158  mov     ecx, [rdx]
0x18001115a  mov     rax, [rdx+8]
0x18001115e  dec     ecx
0x180011160  mov     [rax+rcx*2], r13w
0x180011165  mov     r9, [rbp+var_30]
0x180011169  mov     r10, [rbp+var_38]
0x18001116d  jmp     loc_180011078
0x180011172  mov     r13d, [r9]
0x180011175  cmp     r13d, 0FFFFFFEFh
0x180011179  ja      loc_1800112FB
0x18001117f  lea     edx, [r13+10h]
0x180011183  cmp     edx, 3FFFFFFFh
0x180011189  ja      loc_18001133A
0x18001118f  mov     rax, [r10]
0x180011192  lea     rcx, [rbp+var_38]
0x180011196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001119b  mov     edi, eax
0x18001119d  test    eax, eax
0x18001119f  js      loc_180011387
0x1800111a5  mov     rax, [rbp+var_30]
0x1800111a9  movups  xmm0, cs:xmmword_180117790
0x1800111b0  mov     rcx, [rax+8]
0x1800111b4  movups  xmmword ptr [rcx+r13*2], xmm0
0x1800111b9  movups  xmm1, cs:xmmword_1801177A0
0x1800111c0  movups  xmmword ptr [rcx+r13*2+10h], xmm1
0x1800111c6  mov     r9, [rbp+var_30]
0x1800111ca  mov     r10, [rbp+var_38]
0x1800111ce  jmp     loc_18001108A
0x1800111d3  mov     rax, [rbp+var_30]
0x1800111d7  mov     esi, [rax]
0x1800111d9  cmp     esi, 0FFFFFFFDh
0x1800111dc  ja      loc_180011341
0x1800111e2  lea     edx, [rsi+2]
0x1800111e5  cmp     edx, 3FFFFFFFh
0x1800111eb  ja      loc_180011380
0x1800111f1  mov     rax, [rbp+var_38]
0x1800111f5  lea     rcx, [rbp+var_38]
0x1800111f9  mov     rax, [rax]
0x1800111fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011201  mov     edi, eax
0x180011203  test    eax, eax
0x180011205  js      loc_180011394
0x18001120b  mov     rax, [rbp+var_30]
0x18001120f  mov     rcx, [rax+8]
0x180011213  mov     dword ptr [rcx+rsi*2], 5D0027h
0x18001121a  jmp     loc_18001111E
0x18001121f  mov     edi, 80070216h
0x180011224  mov     edx, 107h; void *
0x180011229  mov     r9d, edi; char *
0x18001122c  mov     rcx, [rbp+30h]; this
0x180011230  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180011237  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001123c  mov     rcx, [rbp+30h]; this
0x180011240  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180011247  mov     r9d, edi; char *
0x18001124a  mov     edx, 79h ; 'y'; void *
0x18001124f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011254  mov     edx, 33h ; '3'; void *
0x180011259  mov     rcx, [rbp+30h]; this
0x18001125d  lea     r8, aOnecorePrintsc_117; "onecore\\printscan\\appxpackaging\\lib"...
0x180011264  mov     r9d, edi; char *
0x180011267  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001126c  mov     rcx, [rbp+strIn+8]; void *
0x180011270  test    rcx, rcx
0x180011273  jz      short loc_18001127A
0x180011275  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001127a  mov     eax, edi
0x18001127c  jmp     loc_18001103C
0x180011281  mov     edi, 80070503h
0x180011286  jmp     short loc_18001123C
0x180011288  mov     edx, [r9]
0x18001128b  cmp     edx, 3FFFFFFFh
0x180011291  jz      loc_1800114D3
0x180011297  mov     rax, [r10]
0x18001129a  lea     rcx, [rbp+var_38]
0x18001129e  inc     edx
0x1800112a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112a5  mov     edi, eax
0x1800112a7  test    eax, eax
0x1800112a9  js      loc_18001139E
0x1800112af  mov     rdx, [rbp+var_30]
0x1800112b3  mov     ecx, [rdx]
0x1800112b5  mov     rax, [rdx+8]
0x1800112b9  dec     ecx
0x1800112bb  mov     [rax+rcx*2], si
0x1800112bf  mov     r9, [rbp+var_30]
0x1800112c3  mov     r10, [rbp+var_38]
0x1800112c7  jmp     loc_180011060
0x1800112cc  mov     r9d, eax
0x1800112cf  mov     edx, 10Dh
0x1800112d4  jmp     loc_18001122C
0x1800112d9  mov     rcx, [rbp+30h]; this
0x1800112dd  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x1800112e4  mov     r9d, eax; char *
0x1800112e7  mov     edx, 1Bh; void *
0x1800112ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800112f1  mov     edx, 2Dh ; '-'
0x1800112f6  jmp     loc_180011259
0x1800112fb  mov     edi, 80070216h
0x180011300  mov     edx, 107h; void *
0x180011305  mov     r9d, edi; char *
0x180011308  mov     rcx, [rbp+30h]; this
0x18001130c  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180011313  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011318  mov     rcx, [rbp+30h]; this
0x18001131c  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180011323  mov     r9d, edi; char *
0x180011326  mov     edx, 79h ; 'y'; void *
0x18001132b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011330  mov     edx, 31h ; '1'
0x180011335  jmp     loc_180011259
0x18001133a  mov     edi, 80070503h
0x18001133f  jmp     short loc_180011318
0x180011341  mov     edi, 80070216h
0x180011346  mov     edx, 107h; void *
0x18001134b  mov     r9d, edi; char *
0x18001134e  mov     rcx, [rbp+30h]; this
0x180011352  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180011359  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001135e  mov     rcx, [rbp+30h]; this
0x180011362  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180011369  mov     r9d, edi; char *
0x18001136c  mov     edx, 79h ; 'y'; void *
0x180011371  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011376  mov     edx, 3Eh ; '>'
0x18001137b  jmp     loc_180011259
0x180011380  mov     edi, 80070503h
0x180011385  jmp     short loc_18001135E
0x180011387  mov     r9d, eax
0x18001138a  mov     edx, 10Dh
0x18001138f  jmp     loc_180011308
0x180011394  mov     r9d, eax
0x180011397  mov     edx, 10Dh
0x18001139c  jmp     short loc_18001134E
0x18001139e  mov     rcx, [rbp+30h]; this
0x1800113a2  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x1800113a9  mov     r9d, eax; char *
0x1800113ac  mov     edx, 1Bh; void *
0x1800113b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800113b6  mov     edx, 29h ; ')'
0x1800113bb  jmp     loc_180011259
0x1800113c0  lea     rax, [rbx+rbx*4]
0x1800113c4  mov     ecx, [r15+rax*8]
0x1800113c8  sub     ecx, 3
0x1800113cb  test    ecx, 0FFFFFFFDh
0x1800113d1  jnz     loc_18001110C
0x1800113d7  mov     rax, [rbp+var_30]
0x1800113db  lea     rcx, [rbp+var_38]; this
0x1800113df  mov     r8d, 17h; unsigned int
0x1800113e5  mov     r13d, [rax]
0x1800113e8  mov     edx, r13d; unsigned int
0x1800113eb  call    ?Insert@StringBuilder@Common@@QEAAJKK@Z; Common::StringBuilder::Insert(ulong,ulong)
0x1800113f0  mov     esi, eax
0x1800113f2  test    eax, eax
0x1800113f4  js      short loc_18001146C
0x1800113f6  mov     rax, [rbp+var_30]
0x1800113fa  movups  xmm0, cs:xmmword_180117C00
  ... truncated ...
```
