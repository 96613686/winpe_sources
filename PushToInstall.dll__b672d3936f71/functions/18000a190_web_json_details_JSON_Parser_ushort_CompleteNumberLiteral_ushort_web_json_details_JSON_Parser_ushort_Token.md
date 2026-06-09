# web::json::details::JSON_Parser<ushort>::CompleteNumberLiteral(ushort,web::json::details::JSON_Parser<ushort>::Token &)

- ea: `0x18000a190`
- end: `0x18000aa4d`
- name: `?CompleteNumberLiteral@?$JSON_Parser@G@details@json@web@@AEAA_NGAEAUToken@1234@@Z`
- size: `2237`
- prototype: `char __fastcall(__int64, unsigned __int16, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000acb0`

## callees

- `0x180002b50`
- `0x18000316c`
- `0x180003294`
- `0x180006980`
- `0x18000a190`
- `0x18000c210`
- `0x18000c690`
- `0x18000d75c`
- `0x18000dc5b`
- `0x180030a84`
- `0x18004f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstod_l` at `0x18000a99f`
- `api-ms-win-crt-private-l1-1-0!_o__wcstod_l` at `0x18000a99f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall web::json::details::JSON_Parser<unsigned short>::CompleteNumberLiteral(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3)
{
  unsigned __int16 v4; // bx
  char v6; // r12
  __int16 v7; // ax
  unsigned __int64 v8; // r14
  unsigned __int16 v9; // ax
  __int64 v10; // rbx
  __int16 v11; // ax
  __int16 v12; // r15
  wchar_t *v13; // rax
  size_t v14; // rdi
  __crt_locale_pointers *Locale; // rax
  int v16; // eax
  __int64 v17; // r14
  wchar_t *v18; // rdi
  wchar_t *v19; // rbx
  unsigned __int64 v20; // r12
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // r13
  size_t v25; // r13
  void *v26; // rax
  const struct std::nothrow_t *v27; // rdx
  wchar_t *v28; // rax
  unsigned __int64 v29; // rbx
  char v30; // r14
  __int64 v31; // r14
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // r15
  size_t v35; // r15
  _QWORD *v36; // rbx
  void *v37; // rax
  wchar_t *v38; // rdx
  char *v39; // rcx
  char *v40; // r8
  const struct std::nothrow_t *v41; // rdx
  wchar_t *v42; // rax
  wchar_t v43; // ax
  wchar_t v44; // r12
  wchar_t *v45; // r14
  signed __int64 v46; // rdi
  unsigned __int64 v47; // rcx
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // r15
  size_t v50; // r15
  _QWORD *v51; // rbx
  void *v52; // rax
  wchar_t *v53; // rdx
  char *v54; // rcx
  char *v55; // r8
  const struct std::nothrow_t *v56; // rdx
  wchar_t *v57; // rax
  __int16 v58; // ax
  __int16 v59; // cx
  __int16 v60; // ax
  __int16 i; // ax
  wchar_t *v62; // rbx
  struct __crt_locale_pointers *v63; // rax
  double v64; // xmm0_8
  char v65; // di
  unsigned __int64 v66; // rdx
  _BYTE *v67; // rcx
  wchar_t *Buffer[2]; // [rsp+30h] [rbp-20h] BYREF
  wchar_t *v69; // [rsp+40h] [rbp-10h]
  char v70; // [rsp+98h] [rbp+48h]
  __int16 v72; // [rsp+A8h] [rbp+58h] BYREF

  v4 = a2;
  if ( a2 == 45 )
  {
    v6 = 1;
    v70 = 1;
    v4 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
  }
  else
  {
    v6 = 0;
    v70 = 0;
  }
  if ( (unsigned __int16)(v4 - 48) > 9u )
    return 0;
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( v4 == 48 && v7 == 48 )
    return 0;
  v8 = v4 - 48LL;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( v9 >= 0x30u )
  {
    while ( v9 <= 0x39u )
    {
      if ( v8 > 0x1999999999999999LL
        || (v10 = (unsigned int)v9 - 48, v8 == 0x1999999999999999LL) && (unsigned int)v10 > 5 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
        goto LABEL_21;
      }
      (**(void (__fastcall ***)(__int64))a1)(a1);
      v8 = v10 + 10 * v8;
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      if ( v9 < 0x30u )
        break;
    }
  }
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v12 = v11;
  if ( v11 != 46 && v11 != 69 && v11 != 101 )
  {
    if ( v6 )
    {
      *(_BYTE *)(a3 + 64) = 1;
      if ( v8 <= 0x8000000000000000uLL )
      {
        *(_QWORD *)(a3 + 56) = -(__int64)v8;
        *(_DWORD *)a3 = 9;
      }
      else
      {
        *(double *)(a3 + 56) = 0.0 - ((double)(int)(v8 & 1 | (v8 >> 1)) + (double)(int)(v8 & 1 | (v8 >> 1)));
        *(_DWORD *)a3 = 8;
      }
      return 1;
    }
    else
    {
      *(_QWORD *)(a3 + 56) = v8;
      *(_DWORD *)a3 = 9;
      *(_BYTE *)(a3 + 64) = 0;
      return 1;
    }
  }
LABEL_21:
  v13 = (wchar_t *)operator new(0x30u);
  Buffer[0] = v13;
  v69 = v13 + 24;
  *(_OWORD *)v13 = 0;
  *((_OWORD *)v13 + 1) = 0;
  *((_OWORD *)v13 + 2) = 0;
  Buffer[1] = v13 + 24;
  v14 = v13 + 24 - Buffer[0];
  Locale = utility::details::scoped_c_thread_locale::c_locale();
  v16 = snwprintf_s_l(Buffer[0], v14, 0xFFFFFFFFFFFFFFFFuLL, L"%I64u", Locale, v8);
  v17 = v16;
  v18 = Buffer[1];
  v19 = Buffer[0];
  v20 = Buffer[1] - Buffer[0];
  if ( v16 >= v20 )
  {
    if ( v16 <= v20 )
      goto LABEL_48;
    v22 = v69 - Buffer[0];
    if ( v16 <= v22 )
    {
      v29 = v16 - v20;
      memset_0(Buffer[1], 0, v29 * 2);
      v18 = &Buffer[1][v29];
      v19 = Buffer[0];
      goto LABEL_47;
    }
    if ( (unsigned __int64)v16 > 0x7FFFFFFFFFFFFFFFLL )
LABEL_129:
      std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
    v23 = v22 >> 1;
    if ( v22 <= 0x7FFFFFFFFFFFFFFFLL - (v22 >> 1) )
    {
      v24 = v22 + v23;
      if ( v22 + v23 >= v16 )
      {
        if ( v24 > 0x7FFFFFFFFFFFFFFFLL )
          goto LABEL_130;
      }
      else
      {
        v24 = v16;
      }
      v25 = 2 * v24;
      if ( !v25 )
      {
        v19 = 0;
        goto LABEL_39;
      }
      if ( v25 < 0x1000 )
      {
        v19 = (wchar_t *)operator new(v25);
        goto LABEL_39;
      }
      if ( v25 + 39 >= v25 )
      {
        v26 = operator new(v25 + 39);
        if ( !v26 )
          goto LABEL_105;
        v19 = (wchar_t *)(((unsigned __int64)v26 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v19 - 1) = v26;
LABEL_39:
        memset_0(&v19[v20], 0, 2 * (v17 - v20));
        memmove_0(v19, Buffer[0], (char *)Buffer[1] - (char *)Buffer[0]);
        if ( !Buffer[0] )
        {
LABEL_45:
          Buffer[0] = v19;
          v18 = &v19[v17];
          v69 = &v19[v25 / 2];
          goto LABEL_47;
        }
        v27 = (const struct std::nothrow_t *)(2 * (v69 - Buffer[0]));
        if ( (unsigned __int64)v27 < 0x1000 )
        {
          v28 = Buffer[0];
          goto LABEL_44;
        }
        v28 = (wchar_t *)*((_QWORD *)Buffer[0] - 1);
        if ( (unsigned __int64)((char *)Buffer[0] - (char *)v28 - 8) <= 0x1F )
        {
          v27 = (const struct std::nothrow_t *)((char *)v27 + 39);
LABEL_44:
          operator delete(v28, v27);
          goto LABEL_45;
        }
LABEL_105:
        __fastfail(5u);
      }
    }
LABEL_130:
    __scrt_throw_std_bad_array_new_length();
  }
  v18 = &Buffer[0][v16];
LABEL_47:
  Buffer[1] = v18;
LABEL_48:
  v30 = 0;
  if ( v12 == -1 )
    goto LABEL_116;
  while ( 1 )
  {
    if ( (unsigned __int16)(v12 - 48) <= 9u )
    {
      v72 = v12;
      std::vector<unsigned short>::push_back(Buffer, &v72);
      goto LABEL_103;
    }
    if ( v12 != 46 )
      break;
    if ( v30 )
      goto LABEL_124;
    if ( v18 == v69 )
    {
      v31 = v18 - v19;
      if ( v31 == 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_129;
      v32 = v69 - v19;
      v33 = v32 >> 1;
      if ( v32 > 0x7FFFFFFFFFFFFFFFLL - (v32 >> 1) )
        goto LABEL_130;
      v34 = v31 + 1;
      if ( v33 + v32 >= v31 + 1 )
        v34 = v33 + v32;
      if ( v34 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_130;
      v35 = 2 * v34;
      if ( v35 )
      {
        if ( v35 < 0x1000 )
        {
          v36 = operator new(v35);
        }
        else
        {
          if ( v35 + 39 < v35 )
            goto LABEL_130;
          v37 = operator new(v35 + 39);
          if ( !v37 )
            goto LABEL_105;
          v36 = (_QWORD *)(((unsigned __int64)v37 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v36 - 1) = v37;
        }
      }
      else
      {
        v36 = 0;
      }
      *((_WORD *)v36 + v31) = 46;
      v38 = Buffer[0];
      v39 = (char *)v36;
      if ( v18 == Buffer[1] )
      {
        v40 = (char *)((char *)Buffer[1] - (char *)Buffer[0]);
      }
      else
      {
        memmove_0(v36, Buffer[0], (char *)v18 - (char *)Buffer[0]);
        v40 = (char *)((char *)Buffer[1] - (char *)v18);
        v39 = (char *)v36 + 2 * v31 + 2;
        v38 = v18;
      }
      memmove_0(v39, v38, (size_t)v40);
      if ( Buffer[0] )
      {
        v41 = (const struct std::nothrow_t *)(2 * (v69 - Buffer[0]));
        if ( (unsigned __int64)v41 < 0x1000 )
        {
          v42 = Buffer[0];
        }
        else
        {
          v42 = (wchar_t *)*((_QWORD *)Buffer[0] - 1);
          if ( (unsigned __int64)((char *)Buffer[0] - (char *)v42 - 8) > 0x1F )
            goto LABEL_105;
          v41 = (const struct std::nothrow_t *)((char *)v41 + 39);
        }
        operator delete(v42, v41);
      }
      Buffer[0] = (wchar_t *)v36;
      Buffer[1] = (wchar_t *)v36 + v31 + 1;
      v69 = (wchar_t *)((char *)v36 + v35);
    }
    else
    {
      *v18 = 46;
      ++Buffer[1];
    }
    (**(void (__fastcall ***)(__int64))a1)(a1);
    v43 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v44 = v43;
    if ( (unsigned __int16)(v43 - 48) > 9u )
      goto LABEL_123;
    v45 = Buffer[1];
    if ( Buffer[1] == v69 )
    {
      v46 = Buffer[1] - Buffer[0];
      if ( v46 == 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_129;
      v47 = v69 - Buffer[0];
      v48 = v47 >> 1;
      if ( v47 > 0x7FFFFFFFFFFFFFFFLL - (v47 >> 1) )
        goto LABEL_130;
      v49 = v46 + 1;
      if ( v48 + v47 >= v46 + 1 )
        v49 = v48 + v47;
      if ( v49 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_130;
      v50 = 2 * v49;
      if ( v50 )
      {
        if ( v50 < 0x1000 )
        {
          v51 = operator new(v50);
        }
        else
        {
          if ( v50 + 39 < v50 )
            goto LABEL_130;
          v52 = operator new(v50 + 39);
          if ( !v52 )
            goto LABEL_105;
          v51 = (_QWORD *)(((unsigned __int64)v52 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v51 - 1) = v52;
        }
      }
      else
      {
        v51 = 0;
      }
      *((_WORD *)v51 + v46) = v44;
      v53 = Buffer[0];
      v54 = (char *)v51;
      if ( v45 == Buffer[1] )
      {
        v55 = (char *)((char *)Buffer[1] - (char *)Buffer[0]);
      }
      else
      {
        memmove_0(v51, Buffer[0], (char *)v45 - (char *)Buffer[0]);
        v55 = (char *)((char *)Buffer[1] - (char *)v45);
        v54 = (char *)v51 + 2 * v46 + 2;
        v53 = v45;
      }
      memmove_0(v54, v53, (size_t)v55);
      if ( Buffer[0] )
      {
        v56 = (const struct std::nothrow_t *)(2 * (v69 - Buffer[0]));
        if ( (unsigned __int64)v56 < 0x1000 )
        {
          v57 = Buffer[0];
        }
        else
        {
          v57 = (wchar_t *)*((_QWORD *)Buffer[0] - 1);
          if ( (unsigned __int64)((char *)Buffer[0] - (char *)v57 - 8) > 0x1F )
            goto LABEL_105;
          v56 = (const struct std::nothrow_t *)((char *)v56 + 39);
        }
        operator delete(v57, v56);
      }
      Buffer[0] = (wchar_t *)v51;
      Buffer[1] = (wchar_t *)v51 + v46 + 1;
      v69 = (wchar_t *)((char *)v51 + v50);
    }
    else
    {
      *Buffer[1]++ = v43;
    }
    v30 = 1;
LABEL_103:
    (**(void (__fastcall ***)(__int64))a1)(a1);
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    if ( v12 == -1 )
      goto LABEL_116;
    v18 = Buffer[1];
    v19 = Buffer[0];
  }
  if ( ((v12 - 69) & 0xFFDF) != 0 )
    goto LABEL_116;
  v72 = v12;
  std::vector<unsigned short>::push_back(Buffer, &v72);
  (**(void (__fastcall ***)(__int64))a1)(a1);
  v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v59 = v58;
  if ( v58 == 43 )
  {
    v60 = 43;
    goto LABEL_111;
  }
  if ( v58 == 45 )
  {
    v60 = 45;
LABEL_111:
    v72 = v60;
    std::vector<unsigned short>::push_back(Buffer, &v72);
    (**(void (__fastcall ***)(__int64))a1)(a1);
    v59 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( (unsigned __int16)(v59 - 48) > 9u )
  {
LABEL_123:
    v19 = Buffer[0];
LABEL_124:
    v65 = 0;
  }
  else
  {
    v72 = v59;
    std::vector<unsigned short>::push_back(Buffer, &v72);
    (**(void (__fastcall ***)(__int64))a1)(a1);
    for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
          (unsigned __int16)i >= 0x30u;
          i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) )
    {
      if ( (unsigned __int16)i > 0x39u )
        break;
      v72 = i;
      std::vector<unsigned short>::push_back(Buffer, &v72);
      (**(void (__fastcall ***)(__int64))a1)(a1);
    }
LABEL_116:
    v72 = 0;
    std::vector<unsigned short>::push_back(Buffer, &v72);
    v62 = Buffer[0];
    v63 = utility::details::scoped_c_thread_locale::c_locale();
    v64 = _o__wcstod_l(v62, 0, v63);
    *(double *)(a3 + 56) = v64;
    if ( v70 )
      *(_QWORD *)(a3 + 56) = *(_QWORD *)&v64 ^ _xmm;
    *(_DWORD *)a3 = 8;
    v65 = 1;
    v19 = Buffer[0];
  }
  if ( !v19 )
    return v65;
  v66 = 2 * (v69 - v19);
  if ( v66 < 0x1000 )
  {
    operator delete(v19, (const struct std::nothrow_t *)v66);
    return v65;
  }
  v67 = (_BYTE *)*((_QWORD *)v19 - 1);
  if ( (unsigned __int64)((char *)v19 - v67 - 8) > 0x1F )
    __fastfail(5u);
  operator delete(v67, (const struct std::nothrow_t *)(v66 + 39));
  return v65;
}

```

## disassembly

```asm
0x18000a190  mov     [rsp-38h+arg_0], rbx
0x18000a195  mov     [rsp-38h+arg_10], r8
0x18000a19a  push    rbp
0x18000a19b  push    rsi
0x18000a19c  push    rdi
0x18000a19d  push    r12
0x18000a19f  push    r13
0x18000a1a1  push    r14
0x18000a1a3  push    r15
0x18000a1a5  mov     rbp, rsp
0x18000a1a8  sub     rsp, 50h
0x18000a1ac  mov     rdi, r8
0x18000a1af  movzx   ebx, dx
0x18000a1b2  mov     rsi, rcx
0x18000a1b5  cmp     dx, 2Dh ; '-'
0x18000a1b9  jnz     short loc_18000A1D2
0x18000a1bb  mov     r12b, 1
0x18000a1be  mov     [rbp+arg_8], r12b
0x18000a1c2  mov     rax, [rcx]
0x18000a1c5  mov     rax, [rax]
0x18000a1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1cd  movzx   ebx, ax
0x18000a1d0  jmp     short loc_18000A1D9
0x18000a1d2  xor     r12b, r12b
0x18000a1d5  mov     [rbp+arg_8], r12b
0x18000a1d9  lea     eax, [rbx-30h]
0x18000a1dc  cmp     ax, 9
0x18000a1e0  ja      loc_18000AA27
0x18000a1e6  mov     rax, [rsi]
0x18000a1e9  mov     rcx, rsi
0x18000a1ec  mov     rax, [rax+8]
0x18000a1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1f5  cmp     bx, 30h ; '0'
0x18000a1f9  jnz     short loc_18000A204
0x18000a1fb  cmp     ax, bx
0x18000a1fe  jz      loc_18000AA27
0x18000a204  movzx   r14d, bx
0x18000a208  sub     r14, 30h ; '0'
0x18000a20c  mov     rax, [rsi]
0x18000a20f  mov     rcx, rsi
0x18000a212  mov     rax, [rax+8]
0x18000a216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a21b  cmp     ax, 30h ; '0'
0x18000a21f  jb      short loc_18000A27E
0x18000a221  mov     r15, 1999999999999999h
0x18000a22b  nop     dword ptr [rax+rax+00h]
0x18000a230  cmp     ax, 39h ; '9'
0x18000a234  ja      short loc_18000A27E
0x18000a236  cmp     r14, r15
0x18000a239  ja      loc_18000A2D9
0x18000a23f  movzx   ebx, ax
0x18000a242  add     ebx, 0FFFFFFD0h
0x18000a245  cmp     r14, r15
0x18000a248  jnz     short loc_18000A253
0x18000a24a  cmp     ebx, 5
0x18000a24d  ja      loc_18000A2D9
0x18000a253  mov     rax, [rsi]
0x18000a256  mov     rcx, rsi
0x18000a259  mov     rax, [rax]
0x18000a25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a261  lea     rcx, [r14+r14*4]
0x18000a265  lea     r14, [rbx+rcx*2]
0x18000a269  mov     rax, [rsi]
0x18000a26c  mov     rcx, rsi
0x18000a26f  mov     rax, [rax+8]
0x18000a273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a278  cmp     ax, 30h ; '0'
0x18000a27c  jnb     short loc_18000A230
0x18000a27e  mov     rax, [rsi]
0x18000a281  mov     rcx, rsi
0x18000a284  mov     rax, [rax+8]
0x18000a288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a28d  movzx   r15d, ax
0x18000a291  cmp     ax, 2Eh ; '.'
0x18000a295  jz      short loc_18000A2EC
0x18000a297  cmp     ax, 45h ; 'E'
0x18000a29b  jz      short loc_18000A2EC
0x18000a29d  cmp     ax, 65h ; 'e'
0x18000a2a1  jz      short loc_18000A2EC
0x18000a2a3  test    r12b, r12b
0x18000a2a6  jz      loc_18000A3C5
0x18000a2ac  mov     byte ptr [rdi+40h], 1
0x18000a2b0  mov     rax, 8000000000000000h
0x18000a2ba  cmp     r14, rax
0x18000a2bd  jbe     loc_18000A3B1
0x18000a2c3  xorps   xmm1, xmm1
0x18000a2c6  test    r14, r14
0x18000a2c9  js      loc_18000A382
0x18000a2cf  cvtsi2sd xmm1, r14
0x18000a2d4  jmp     loc_18000A398
0x18000a2d9  mov     rax, [rsi]
0x18000a2dc  mov     rcx, rsi
0x18000a2df  mov     rax, [rax+8]
0x18000a2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2e8  movzx   r15d, ax
0x18000a2ec  xorps   xmm0, xmm0
0x18000a2ef  movdqu  xmmword ptr [rbp+Buffer], xmm0
0x18000a2f4  mov     [rbp+var_10], 0
0x18000a2fc  mov     ecx, 30h ; '0'; Size
0x18000a301  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a306  mov     [rbp+Buffer], rax
0x18000a30a  lea     rdi, [rax+30h]
0x18000a30e  mov     [rbp+var_10], rdi
0x18000a312  xorps   xmm0, xmm0
0x18000a315  movups  xmmword ptr [rax], xmm0
0x18000a318  movups  xmmword ptr [rax+10h], xmm0
0x18000a31c  movups  xmmword ptr [rax+20h], xmm0
0x18000a320  mov     [rbp+Buffer+8], rdi
0x18000a324  mov     rbx, [rbp+Buffer]
0x18000a328  sub     rdi, rbx
0x18000a32b  sar     rdi, 1
0x18000a32e  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x18000a333  mov     [rsp+50h+var_28], r14
0x18000a338  mov     [rsp+50h+Locale], rax; Locale
0x18000a33d  lea     r9, aI64u; "%I64u"
0x18000a344  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000a34b  mov     rdx, rdi; BufferCount
0x18000a34e  mov     rcx, rbx; Buffer
0x18000a351  call    _snwprintf_s_l
0x18000a356  movsxd  r14, eax
0x18000a359  mov     rdi, [rbp+Buffer+8]
0x18000a35d  mov     r12, rdi
0x18000a360  mov     rbx, [rbp+Buffer]
0x18000a364  sub     r12, rbx
0x18000a367  sar     r12, 1
0x18000a36a  mov     r13, 7FFFFFFFFFFFFFFFh
0x18000a374  cmp     r14, r12
0x18000a377  jnb     short loc_18000A3DA
0x18000a379  lea     rdi, [rbx+r14*2]
0x18000a37d  jmp     loc_18000A51C
0x18000a382  mov     rax, r14
0x18000a385  shr     rax, 1
0x18000a388  and     r14d, 1
0x18000a38c  or      rax, r14
0x18000a38f  cvtsi2sd xmm1, rax
0x18000a394  addsd   xmm1, xmm1
0x18000a398  xorps   xmm0, xmm0
0x18000a39b  subsd   xmm0, xmm1
0x18000a39f  movsd   qword ptr [rdi+38h], xmm0
0x18000a3a4  mov     dword ptr [rdi], 8
0x18000a3aa  mov     al, 1
0x18000a3ac  jmp     loc_18000AA29
0x18000a3b1  neg     r14
0x18000a3b4  mov     [rdi+38h], r14
0x18000a3b8  mov     dword ptr [rdi], 9
0x18000a3be  mov     al, 1
0x18000a3c0  jmp     loc_18000AA29
0x18000a3c5  mov     [rdi+38h], r14
0x18000a3c9  mov     dword ptr [rdi], 9
0x18000a3cf  mov     byte ptr [rdi+40h], 0
0x18000a3d3  mov     al, 1
0x18000a3d5  jmp     loc_18000AA29
0x18000a3da  jbe     loc_18000A520
0x18000a3e0  mov     rcx, [rbp+var_10]
0x18000a3e4  sub     rcx, rbx
0x18000a3e7  sar     rcx, 1
0x18000a3ea  cmp     r14, rcx
0x18000a3ed  jbe     loc_18000A501
0x18000a3f3  cmp     r14, r13
0x18000a3f6  ja      loc_18000AA41
0x18000a3fc  mov     rdx, rcx
0x18000a3ff  shr     rdx, 1
0x18000a402  mov     rax, r13
0x18000a405  sub     rax, rdx
0x18000a408  cmp     rcx, rax
0x18000a40b  ja      loc_18000AA47
0x18000a411  lea     r13, [rcx+rdx]
0x18000a415  cmp     r13, r14
0x18000a418  jnb     short loc_18000A41F
0x18000a41a  mov     r13, r14
0x18000a41d  jmp     short loc_18000A432
0x18000a41f  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a429  cmp     r13, rax
0x18000a42c  ja      loc_18000AA47
0x18000a432  add     r13, r13
0x18000a435  jnz     short loc_18000A43B
0x18000a437  xor     ebx, ebx
0x18000a439  jmp     short loc_18000A478
0x18000a43b  cmp     r13, 1000h
0x18000a442  jb      short loc_18000A46D
0x18000a444  lea     rcx, [r13+27h]; Size
0x18000a448  cmp     rcx, r13
0x18000a44b  jbe     loc_18000AA47
0x18000a451  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a456  test    rax, rax
0x18000a459  jz      loc_18000A86C
0x18000a45f  lea     rbx, [rax+27h]
0x18000a463  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18000a467  mov     [rbx-8], rax
0x18000a46b  jmp     short loc_18000A478
0x18000a46d  mov     rcx, r13; Size
0x18000a470  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a475  mov     rbx, rax
0x18000a478  mov     r8, r14
0x18000a47b  sub     r8, r12
0x18000a47e  add     r8, r8; Size
0x18000a481  lea     rcx, [rbx+r12*2]; void *
0x18000a485  xor     edx, edx; Val
0x18000a487  call    memset_0
0x18000a48c  mov     r8, [rbp+Buffer+8]
0x18000a490  mov     rdx, [rbp+Buffer]; Src
0x18000a494  sub     r8, rdx; Size
0x18000a497  mov     rcx, rbx; void *
0x18000a49a  call    memmove_0
0x18000a49f  mov     rcx, [rbp+Buffer]
0x18000a4a3  test    rcx, rcx
0x18000a4a6  jz      short loc_18000A4E5
0x18000a4a8  mov     rax, [rbp+var_10]
0x18000a4ac  sub     rax, rcx
0x18000a4af  sar     rax, 1
0x18000a4b2  lea     rdx, [rax+rax]; struct std::nothrow_t *
0x18000a4b6  cmp     rdx, 1000h
0x18000a4bd  jb      short loc_18000A4DA
0x18000a4bf  mov     rax, [rcx-8]
0x18000a4c3  sub     rcx, rax
0x18000a4c6  sub     rcx, 8
0x18000a4ca  cmp     rcx, 1Fh
0x18000a4ce  ja      loc_18000A86C
0x18000a4d4  add     rdx, 27h ; '''
0x18000a4d8  jmp     short loc_18000A4DD
0x18000a4da  mov     rax, rcx
0x18000a4dd  mov     rcx, rax; void *
0x18000a4e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a4e5  mov     [rbp+Buffer], rbx
0x18000a4e9  lea     rdi, [rbx+r14*2]
0x18000a4ed  lea     rax, [rbx+r13]
0x18000a4f1  mov     [rbp+var_10], rax
0x18000a4f5  mov     r13, 7FFFFFFFFFFFFFFFh
0x18000a4ff  jmp     short loc_18000A51C
0x18000a501  sub     r14, r12
0x18000a504  lea     rbx, [r14+r14]
0x18000a508  mov     r8, rbx; Size
0x18000a50b  xor     edx, edx; Val
0x18000a50d  mov     rcx, rdi; void *
0x18000a510  call    memset_0
0x18000a515  add     rdi, rbx
0x18000a518  mov     rbx, [rbp+Buffer]
0x18000a51c  mov     [rbp+Buffer+8], rdi
0x18000a520  xor     r14b, r14b
0x18000a523  mov     eax, 0FFFFh
0x18000a528  cmp     r15w, ax
0x18000a52c  jz      loc_18000A97B
0x18000a532  mov     ecx, 2Eh ; '.'
0x18000a537  lea     eax, [r15-30h]
0x18000a53b  cmp     ax, 9
0x18000a53f  ja      short loc_18000A558
0x18000a541  mov     [rbp+arg_18], r15w
0x18000a546  lea     rdx, [rbp+arg_18]
0x18000a54a  lea     rcx, [rbp+Buffer]
0x18000a54e  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18000a553  jmp     loc_18000A825
0x18000a558  cmp     r15w, 2Eh ; '.'
0x18000a55d  jnz     loc_18000A873
0x18000a563  test    r14b, r14b
0x18000a566  jnz     loc_18000AA0D
0x18000a56c  cmp     rdi, [rbp+var_10]
0x18000a570  jz      short loc_18000A57F
0x18000a572  mov     [rdi], cx
0x18000a575  add     [rbp+Buffer+8], 2
0x18000a57a  jmp     loc_18000A6A9
0x18000a57f  mov     r14, rdi
0x18000a582  sub     r14, rbx
0x18000a585  sar     r14, 1
0x18000a588  cmp     r14, r13
0x18000a58b  jz      loc_18000AA41
0x18000a591  mov     rcx, [rbp+var_10]
0x18000a595  sub     rcx, rbx
0x18000a598  sar     rcx, 1
0x18000a59b  mov     rdx, rcx
0x18000a59e  shr     rdx, 1
0x18000a5a1  mov     rax, r13
0x18000a5a4  sub     rax, rdx
0x18000a5a7  cmp     rcx, rax
0x18000a5aa  ja      loc_18000AA47
0x18000a5b0  lea     r12, [r14+1]
0x18000a5b4  lea     rax, [rdx+rcx]
0x18000a5b8  mov     r15, r12
0x18000a5bb  cmp     rax, r12
0x18000a5be  cmovnb  r15, rax
0x18000a5c2  cmp     r15, r13
0x18000a5c5  ja      loc_18000AA47
0x18000a5cb  add     r15, r15
0x18000a5ce  jnz     short loc_18000A5D4
0x18000a5d0  xor     ebx, ebx
0x18000a5d2  jmp     short loc_18000A611
0x18000a5d4  cmp     r15, 1000h
0x18000a5db  jb      short loc_18000A606
0x18000a5dd  lea     rcx, [r15+27h]; Size
0x18000a5e1  cmp     rcx, r15
0x18000a5e4  jbe     loc_18000AA47
0x18000a5ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a5ef  test    rax, rax
0x18000a5f2  jz      loc_18000A86C
0x18000a5f8  lea     rbx, [rax+27h]
0x18000a5fc  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18000a600  mov     [rbx-8], rax
0x18000a604  jmp     short loc_18000A611
0x18000a606  mov     rcx, r15; Size
0x18000a609  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a60e  mov     rbx, rax
  ... truncated ...
```
