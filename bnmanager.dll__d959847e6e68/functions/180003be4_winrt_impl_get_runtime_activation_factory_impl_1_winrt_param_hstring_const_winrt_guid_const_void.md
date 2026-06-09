# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180003be4`
- end: `0x180004338`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `1876`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180003a28`

## callees

- `0x1800013c0`
- `0x1800017c0`
- `0x1800017e4`
- `0x180001bc8`
- `0x180002278`
- `0x180002338`
- `0x180002359`
- `0x180002371`
- `0x180002389`
- `0x1800023a1`
- `0x1800023b9`
- `0x1800025d0`
- `0x180003be4`
- `0x180005178`
- `0x18000bbd0`
- `0x18000bbf8`
- `0x18000c010`
- `0x18000d010`

## string_xrefs

- `0x180003c5d`: `combase.dll`
- `0x180004267`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  void **v13; // rsi
  char *v14; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // r12
  void **v18; // rcx
  unsigned __int64 v19; // rsi
  unsigned __int64 v20; // r13
  void **v21; // rdx
  _WORD *v22; // rdi
  unsigned __int64 i; // rcx
  unsigned __int64 v24; // rdi
  unsigned __int64 v25; // rcx
  size_t v26; // rcx
  void *v27; // rax
  _QWORD *v28; // r15
  size_t v29; // r8
  _WORD *v30; // rdi
  _BYTE *v31; // r13
  unsigned __int64 k; // rcx
  unsigned __int64 v33; // rdx
  _BYTE *v34; // rcx
  unsigned __int64 j; // rcx
  unsigned __int64 v36; // r15
  unsigned __int64 v37; // r14
  void **v38; // rcx
  _QWORD *v39; // rdi
  unsigned __int64 v40; // r12
  unsigned __int64 v41; // rsi
  unsigned __int64 v42; // rcx
  size_t v43; // rcx
  void *v44; // rax
  size_t v45; // r15
  _BYTE *v46; // rsi
  unsigned __int64 v47; // rdx
  _BYTE *v48; // rcx
  void **v49; // rcx
  HMODULE v50; // rsi
  unsigned __int64 v51; // r14
  unsigned __int64 v52; // r15
  void **v53; // rdx
  unsigned __int64 v54; // r13
  void **v55; // rdx
  _WORD *v56; // rdi
  unsigned __int64 ii; // rcx
  unsigned __int64 v58; // rdi
  __int64 v59; // rcx
  size_t v60; // rcx
  void *v61; // rax
  _QWORD *v62; // rsi
  size_t v63; // r8
  _WORD *v64; // rdi
  _BYTE *v65; // r14
  __int64 n; // rcx
  unsigned __int64 v67; // rdx
  _BYTE *v68; // rcx
  unsigned __int64 m; // rcx
  FARPROC v70; // rax
  __int64 v71; // rax
  _DWORD *v72; // rdi
  IErrorInfo *pperrinfo; // [rsp+20h] [rbp-49h] BYREF
  unsigned __int64 v74; // [rsp+28h] [rbp-41h] BYREF
  __int64 v75; // [rsp+30h] [rbp-39h] BYREF
  _DWORD *v76; // [rsp+38h] [rbp-31h]
  _QWORD *v77; // [rsp+40h] [rbp-29h]
  _QWORD *v78; // [rsp+48h] [rbp-21h]
  void *Src[2]; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v80; // [rsp+60h] [rbp-9h]
  unsigned __int64 v81; // [rsp+68h] [rbp-1h]

  v78 = a4;
  v77 = a2;
  v76 = a1;
  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
    return a1;
  }
  ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
  if ( ActivationFactory_0 == -2147221008 )
  {
    Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
    ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
    if ( !ProcAddress )
    {
      *a1 = ActivationFactory_0;
      return a1;
    }
    v74 = 0;
    ((void (__fastcall *)(unsigned __int64 *))ProcAddress)(&v74);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  std::wstring::wstring(Src, a2);
  while ( 1 )
  {
    v13 = Src;
    if ( v81 > 7 )
      v13 = (void **)Src[0];
    if ( !v80 )
      break;
    v14 = (char *)v13 + 2 * v80;
    last_trivial_2 = _std_find_last_trivial_2(v13, v14, 46);
    if ( (char *)last_trivial_2 == v14 )
      break;
    v16 = (last_trivial_2 - (__int64)v13) >> 1;
    if ( v16 == -1 )
      break;
    v17 = v80;
    if ( v16 <= v80 )
    {
      v80 = (last_trivial_2 - (__int64)v13) >> 1;
      v18 = Src;
      if ( v81 > 7 )
        v18 = (void **)Src[0];
      *((_WORD *)v18 + v16) = 0;
      goto LABEL_61;
    }
    v19 = v16 - v80;
    v20 = v81;
    v74 = v81;
    if ( v16 - v80 <= v81 - v80 )
    {
      v80 = v16;
      v21 = Src;
      if ( v81 > 7 )
        v21 = (void **)Src[0];
      v22 = (_WORD *)v21 + v17;
      if ( v19 )
      {
        for ( i = v16 - v17; i; --i )
          *v22++ = 0;
        do
          --v19;
        while ( v19 );
      }
      *((_WORD *)v21 + v16) = 0;
      goto LABEL_61;
    }
    if ( 0x7FFFFFFFFFFFFFFELL - v80 < v19 )
      goto LABEL_140;
    v24 = v16 | 7;
    if ( (v16 | 7) > 0x7FFFFFFFFFFFFFFELL || (v25 = v81 >> 1, v81 > 0x7FFFFFFFFFFFFFFELL - (v81 >> 1)) )
    {
      v24 = 0x7FFFFFFFFFFFFFFELL;
      v26 = -2;
LABEL_33:
      if ( v26 < 0x1000 )
      {
        v28 = operator new(v26);
      }
      else
      {
        if ( v26 + 39 < v26 )
          goto LABEL_141;
        v27 = operator new(v26 + 39);
        if ( !v27 )
          goto LABEL_134;
        v28 = (_QWORD *)(((unsigned __int64)v27 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v28 - 1) = v27;
      }
      goto LABEL_43;
    }
    if ( v24 < v25 + v81 )
      v24 = v25 + v81;
    if ( v24 + 1 > 0x7FFFFFFFFFFFFFFFLL )
LABEL_141:
      __scrt_throw_std_bad_array_new_length();
    v26 = 2 * (v24 + 1);
    if ( v26 )
      goto LABEL_33;
    v28 = 0;
LABEL_43:
    v80 = v16;
    v81 = v24;
    v29 = 2 * v17;
    v30 = (_WORD *)v28 + v17;
    if ( v20 <= 7 )
    {
      memcpy_0(v28, Src, v29);
      if ( v19 )
      {
        for ( j = v16 - v17; j; --j )
          *v30++ = 0;
        do
          --v19;
        while ( v19 );
      }
      *((_WORD *)v28 + v16) = 0;
    }
    else
    {
      v31 = Src[0];
      memcpy_0(v28, Src[0], v29);
      if ( v19 )
      {
        for ( k = v16 - v17; k; --k )
          *v30++ = 0;
        do
          --v19;
        while ( v19 );
      }
      *((_WORD *)v28 + v16) = 0;
      v33 = 2 * v74 + 2;
      if ( v33 < 0x1000 )
      {
        v34 = v31;
      }
      else
      {
        v34 = (_BYTE *)*((_QWORD *)v31 - 1);
        if ( (unsigned __int64)(v31 - v34 - 8) > 0x1F )
          goto LABEL_134;
        v33 = 2 * v74 + 41;
      }
      operator delete(v34, v33);
    }
    Src[0] = v28;
LABEL_61:
    v36 = v80;
    v37 = v81;
    if ( v81 - v80 >= 4 )
    {
      v80 += 4LL;
      v38 = Src;
      if ( v81 > 7 )
        v38 = (void **)Src[0];
      *(void **)((char *)v38 + 2 * v36) = *(void **)L".dll";
      *((_WORD *)v38 + v36 + 4) = 0;
      v39 = Src[0];
      goto LABEL_87;
    }
    if ( 0x7FFFFFFFFFFFFFFELL - v80 < 4 )
      goto LABEL_140;
    v40 = v80 + 4;
    v41 = (v80 + 4) | 7;
    if ( v41 > 0x7FFFFFFFFFFFFFFELL || (v42 = v81 >> 1, v81 > 0x7FFFFFFFFFFFFFFELL - (v81 >> 1)) )
    {
      v41 = 0x7FFFFFFFFFFFFFFELL;
      v43 = -2;
LABEL_69:
      if ( v43 < 0x1000 )
      {
        v39 = operator new(v43);
      }
      else
      {
        if ( v43 + 39 < v43 )
          goto LABEL_141;
        v44 = operator new(v43 + 39);
        if ( !v44 )
          goto LABEL_134;
        v39 = (_QWORD *)(((unsigned __int64)v44 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v39 - 1) = v44;
      }
      goto LABEL_79;
    }
    if ( v41 < v81 + v42 )
      v41 = v81 + v42;
    if ( v41 + 1 > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_141;
    v43 = 2 * (v41 + 1);
    if ( v43 )
      goto LABEL_69;
    v39 = 0;
LABEL_79:
    v80 = v36 + 4;
    v81 = v41;
    v45 = 2 * v36;
    if ( v37 <= 7 )
    {
      memcpy_0(v39, Src, v45);
      *(_QWORD *)((char *)v39 + v45) = *(_QWORD *)L".dll";
      *((_WORD *)v39 + v40) = 0;
    }
    else
    {
      v46 = Src[0];
      memcpy_0(v39, Src[0], v45);
      *(_QWORD *)((char *)v39 + v45) = *(_QWORD *)L".dll";
      *((_WORD *)v39 + v40) = 0;
      v47 = 2 * v37 + 2;
      if ( v47 < 0x1000 )
      {
        v48 = v46;
      }
      else
      {
        v48 = (_BYTE *)*((_QWORD *)v46 - 1);
        if ( (unsigned __int64)(v46 - v48 - 8) > 0x1F )
          goto LABEL_134;
        v47 = 2 * v37 + 41;
      }
      operator delete(v48, v47);
    }
    Src[0] = v39;
LABEL_87:
    v49 = Src;
    if ( v81 > 7 )
      v49 = (void **)v39;
    v50 = LoadLibraryExW_0((LPCWSTR)v49, 0, 0x1000u);
    v74 = (unsigned __int64)v50;
    v51 = v80;
    v52 = v80 - 4;
    if ( v80 < 4 )
    {
      v54 = v81;
      if ( v81 - v80 < 0xFFFFFFFFFFFFFFFCuLL )
      {
        if ( 0x7FFFFFFFFFFFFFFELL - v80 < 0xFFFFFFFFFFFFFFFCuLL )
LABEL_140:
          std::_Xlen_string();
        v58 = v52 | 7;
        if ( (v52 | 7) <= 0x7FFFFFFFFFFFFFFELL && (v59 = v81 >> 1, v81 <= 0x7FFFFFFFFFFFFFFELL - (v81 >> 1)) )
        {
          if ( v58 < v59 + v81 )
            v58 = v59 + v81;
          if ( v58 + 1 > 0x7FFFFFFFFFFFFFFFLL )
            goto LABEL_141;
          v60 = 2 * (v58 + 1);
          if ( v60 )
            goto LABEL_104;
          v62 = 0;
        }
        else
        {
          v58 = 0x7FFFFFFFFFFFFFFELL;
          v60 = -2;
LABEL_104:
          if ( v60 < 0x1000 )
          {
            v62 = operator new(v60);
          }
          else
          {
            if ( v60 + 39 < v60 )
              goto LABEL_141;
            v61 = operator new(v60 + 39);
            if ( !v61 )
LABEL_134:
              __fastfail(5u);
            v62 = (_QWORD *)(((unsigned __int64)v61 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v62 - 1) = v61;
          }
        }
        v80 = v52;
        v81 = v58;
        v63 = 2 * v51;
        v64 = (_WORD *)v62 + v51;
        if ( v54 <= 7 )
        {
          memcpy_0(v62, Src, v63);
          for ( m = v52 - v51; m; --m )
            *v64++ = 0;
          *((_WORD *)v62 + v52) = 0;
        }
        else
        {
          v65 = Src[0];
          memcpy_0(v62, Src[0], v63);
          for ( n = -4; n; --n )
            *v64++ = 0;
          *((_WORD *)v62 + v52) = 0;
          v67 = 2 * v54 + 2;
          if ( v67 < 0x1000 )
          {
            v68 = v65;
          }
          else
          {
            v68 = (_BYTE *)*((_QWORD *)v65 - 1);
            if ( (unsigned __int64)(v65 - v68 - 8) > 0x1F )
              goto LABEL_134;
            v67 = 2 * v54 + 41;
          }
          operator delete(v68, v67);
        }
        Src[0] = v62;
        v50 = (HMODULE)v74;
        goto LABEL_128;
      }
      v80 -= 4LL;
      v55 = Src;
      if ( v81 > 7 )
        v55 = (void **)Src[0];
      v56 = (_WORD *)v55 + v51;
      for ( ii = v52 - v51; ii; --ii )
        *v56++ = 0;
      *((_WORD *)v55 + v52) = 0;
    }
    else
    {
      v80 -= 4LL;
      v53 = Src;
      if ( v81 > 7 )
        v53 = (void **)Src[0];
      *((_WORD *)v53 + v52) = 0;
    }
LABEL_128:
    if ( v50 )
    {
      v70 = WINRT_IMPL_GetProcAddress(v50, "DllGetActivationFactory");
      if ( v70 )
      {
        v75 = 0;
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v70)(*v77, &v75) )
        {
          v71 = v75;
          v75 = 0;
          *v78 = v71;
          v72 = v76;
          *v76 = 0;
          goto LABEL_137;
        }
        if ( v75 )
          winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v75);
      }
      WINRT_IMPL_FreeLibrary(v50);
    }
  }
  SetErrorInfo_0(0, pperrinfo);
  v72 = v76;
  *v76 = ActivationFactory_0;
LABEL_137:
  std::wstring::~wstring(Src);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
  return v72;
}

```

## disassembly

```asm
0x180003be4  push    rbp
0x180003be6  push    rbx
0x180003be7  push    rsi
0x180003be8  push    rdi
0x180003be9  push    r12
0x180003beb  push    r13
0x180003bed  push    r14
0x180003bef  push    r15
0x180003bf1  lea     rbp, [rsp-1Fh]
0x180003bf6  sub     rsp, 88h
0x180003bfd  mov     rax, cs:__security_cookie
0x180003c04  xor     rax, rsp
0x180003c07  mov     [rbp+57h+var_50], rax
0x180003c0b  mov     r14, r9
0x180003c0e  mov     [rbp+57h+var_78], r9
0x180003c12  mov     rdi, r8
0x180003c15  mov     r15, rdx
0x180003c18  mov     [rbp+57h+var_80], rdx
0x180003c1c  mov     rsi, rcx
0x180003c1f  mov     [rbp+57h+var_88], rcx
0x180003c23  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180003c2a  mov     r8, r9
0x180003c2d  mov     rdx, rdi
0x180003c30  mov     rcx, [r15]
0x180003c33  test    rax, rax
0x180003c36  jz      short loc_180003C47
0x180003c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c3d  mov     [rsi], eax
0x180003c3f  mov     rax, rsi
0x180003c42  jmp     loc_18000430C
0x180003c47  call    RoGetActivationFactory_0
0x180003c4c  mov     ebx, eax
0x180003c4e  cmp     eax, 800401F0h
0x180003c53  jnz     short loc_180003CA2
0x180003c55  xor     edx, edx; hFile
0x180003c57  mov     r8d, 1000h; dwFlags
0x180003c5d  lea     rcx, LibFileName; "combase.dll"
0x180003c64  call    LoadLibraryExW_0
0x180003c69  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x180003c70  mov     rcx, rax; hModule
0x180003c73  call    WINRT_IMPL_GetProcAddress
0x180003c78  test    rax, rax
0x180003c7b  jnz     short loc_180003C81
0x180003c7d  mov     [rsi], ebx
0x180003c7f  jmp     short loc_180003C3F
0x180003c81  mov     [rbp+57h+var_98], 0
0x180003c89  lea     rcx, [rbp+57h+var_98]
0x180003c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c92  mov     r8, r14
0x180003c95  mov     rdx, rdi
0x180003c98  mov     rcx, [r15]
0x180003c9b  call    RoGetActivationFactory_0
0x180003ca0  mov     ebx, eax
0x180003ca2  test    ebx, ebx
0x180003ca4  jnz     short loc_180003CAA
0x180003ca6  mov     [rsi], ebx
0x180003ca8  jmp     short loc_180003C3F
0x180003caa  mov     [rbp+57h+pperrinfo], 0
0x180003cb2  lea     rdx, [rbp+57h+pperrinfo]; pperrinfo
0x180003cb6  xor     ecx, ecx; dwReserved
0x180003cb8  call    GetErrorInfo_0
0x180003cbd  mov     rdx, r15
0x180003cc0  lea     rcx, [rbp+57h+Src]
0x180003cc4  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x180003cc9  or      r12, 0FFFFFFFFFFFFFFFFh
0x180003ccd  mov     r15, 7FFFFFFFFFFFFFFEh
0x180003cd7  mov     r13, 7FFFFFFFFFFFFFFFh
0x180003ce1  mov     rax, [rbp+57h+var_60]
0x180003ce5  lea     rsi, [rbp+57h+Src]
0x180003ce9  cmp     [rbp+57h+var_58], 7
0x180003cee  cmova   rsi, [rbp+57h+Src]
0x180003cf3  test    rax, rax
0x180003cf6  jz      loc_1800042DF
0x180003cfc  dec     rax
0x180003cff  cmp     rax, r12
0x180003d02  cmovnb  rax, r12
0x180003d06  inc     rax
0x180003d09  lea     rdi, [rsi+rax*2]
0x180003d0d  mov     r8d, 2Eh ; '.'
0x180003d13  mov     rdx, rdi
0x180003d16  mov     rcx, rsi
0x180003d19  call    __std_find_last_trivial_2
0x180003d1e  mov     r14, rax
0x180003d21  cmp     rax, rdi
0x180003d24  jz      loc_1800042DF
0x180003d2a  sub     r14, rsi
0x180003d2d  sar     r14, 1
0x180003d30  cmp     r14, r12
0x180003d33  jz      loc_1800042DF
0x180003d39  mov     r12, [rbp+57h+var_60]
0x180003d3d  cmp     r14, r12
0x180003d40  ja      short loc_180003D60
0x180003d42  mov     [rbp+57h+var_60], r14
0x180003d46  lea     rcx, [rbp+57h+Src]
0x180003d4a  cmp     [rbp+57h+var_58], 7
0x180003d4f  cmova   rcx, [rbp+57h+Src]
0x180003d54  xor     eax, eax
0x180003d56  mov     [rcx+r14*2], ax
0x180003d5b  jmp     loc_180003EFF
0x180003d60  mov     rsi, r14
0x180003d63  sub     rsi, r12
0x180003d66  mov     r13, [rbp+57h+var_58]
0x180003d6a  mov     [rbp+57h+var_98], r13
0x180003d6e  mov     rax, r13
0x180003d71  sub     rax, r12
0x180003d74  cmp     rsi, rax
0x180003d77  ja      short loc_180003DB0
0x180003d79  mov     [rbp+57h+var_60], r14
0x180003d7d  lea     rdx, [rbp+57h+Src]
0x180003d81  cmp     r13, 7
0x180003d85  cmova   rdx, [rbp+57h+Src]
0x180003d8a  lea     rdi, [rdx+r12*2]
0x180003d8e  test    rsi, rsi
0x180003d91  jz      short loc_180003DA4
0x180003d93  xor     eax, eax
0x180003d95  movzx   eax, ax
0x180003d98  mov     rcx, rsi
0x180003d9b  rep stosw
0x180003d9e  sub     rsi, 1
0x180003da2  jnz     short loc_180003D9E
0x180003da4  xor     eax, eax
0x180003da6  mov     [rdx+r14*2], ax
0x180003dab  jmp     loc_180003EF5
0x180003db0  mov     rax, r15
0x180003db3  sub     rax, r12
0x180003db6  cmp     rax, rsi
0x180003db9  jb      loc_18000432C
0x180003dbf  mov     rdi, r14
0x180003dc2  or      rdi, 7
0x180003dc6  cmp     rdi, r15
0x180003dc9  ja      short loc_180003DDC
0x180003dcb  mov     rcx, r13
0x180003dce  shr     rcx, 1
0x180003dd1  mov     rax, r15
0x180003dd4  sub     rax, rcx
0x180003dd7  cmp     r13, rax
0x180003dda  jbe     short loc_180003E1B
0x180003ddc  mov     rdi, r15
0x180003ddf  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180003de6  cmp     rcx, 1000h
0x180003ded  jb      short loc_180003E47
0x180003def  lea     rax, [rcx+27h]
0x180003df3  cmp     rax, rcx
0x180003df6  jbe     loc_180004332
0x180003dfc  mov     rcx, rax; Size
0x180003dff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e04  test    rax, rax
0x180003e07  jz      loc_1800042B9
0x180003e0d  lea     r15, [rax+27h]
0x180003e11  and     r15, 0FFFFFFFFFFFFFFE0h
0x180003e15  mov     [r15-8], rax
0x180003e19  jmp     short loc_180003E4F
0x180003e1b  lea     rax, [rcx+r13]
0x180003e1f  cmp     rdi, rax
0x180003e22  cmovb   rdi, rax
0x180003e26  lea     rcx, [rdi+1]
0x180003e2a  mov     rax, 7FFFFFFFFFFFFFFFh
0x180003e34  cmp     rcx, rax
0x180003e37  ja      loc_180004332
0x180003e3d  add     rcx, rcx
0x180003e40  jnz     short loc_180003DE6
0x180003e42  xor     r15d, r15d
0x180003e45  jmp     short loc_180003E4F
0x180003e47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e4c  mov     r15, rax
0x180003e4f  mov     [rbp+57h+var_60], r14
0x180003e53  mov     [rbp+57h+var_58], rdi
0x180003e57  lea     r8, [r12+r12]; Size
0x180003e5b  lea     rdi, [r8+r15]
0x180003e5f  mov     rcx, r15; void *
0x180003e62  cmp     r13, 7
0x180003e66  jbe     short loc_180003ECB
0x180003e68  mov     r13, [rbp+57h+Src]
0x180003e6c  mov     rdx, r13; Src
0x180003e6f  call    memcpy_0
0x180003e74  test    rsi, rsi
0x180003e77  jz      short loc_180003E8A
0x180003e79  xor     eax, eax
0x180003e7b  movzx   eax, ax
0x180003e7e  mov     rcx, rsi
0x180003e81  rep stosw
0x180003e84  sub     rsi, 1
0x180003e88  jnz     short loc_180003E84
0x180003e8a  xor     eax, eax
0x180003e8c  mov     [r15+r14*2], ax
0x180003e91  mov     rdx, [rbp+57h+var_98]
0x180003e95  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180003e9d  cmp     rdx, 1000h
0x180003ea4  jb      short loc_180003EC1
0x180003ea6  mov     rcx, [r13-8]
0x180003eaa  sub     r13, rcx
0x180003ead  sub     r13, 8
0x180003eb1  cmp     r13, 1Fh
0x180003eb5  ja      loc_1800042B9
0x180003ebb  add     rdx, 27h ; '''
0x180003ebf  jmp     short loc_180003EC4
0x180003ec1  mov     rcx, r13; void *
0x180003ec4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003ec9  jmp     short loc_180003EF1
0x180003ecb  lea     rdx, [rbp+57h+Src]; Src
0x180003ecf  call    memcpy_0
0x180003ed4  test    rsi, rsi
0x180003ed7  jz      short loc_180003EEA
0x180003ed9  xor     eax, eax
0x180003edb  movzx   eax, ax
0x180003ede  mov     rcx, rsi
0x180003ee1  rep stosw
0x180003ee4  sub     rsi, 1
0x180003ee8  jnz     short loc_180003EE4
0x180003eea  xor     eax, eax
0x180003eec  mov     [r15+r14*2], ax
0x180003ef1  mov     [rbp+57h+Src], r15
0x180003ef5  mov     r13, 7FFFFFFFFFFFFFFFh
0x180003eff  mov     r15, [rbp+57h+var_60]
0x180003f03  mov     r14, [rbp+57h+var_58]
0x180003f07  mov     rax, r14
0x180003f0a  sub     rax, r15
0x180003f0d  cmp     rax, 4
0x180003f11  jb      short loc_180003F42
0x180003f13  lea     rdx, [r15+4]
0x180003f17  mov     [rbp+57h+var_60], rdx
0x180003f1b  lea     rcx, [rbp+57h+Src]
0x180003f1f  cmp     r14, 7
0x180003f23  cmova   rcx, [rbp+57h+Src]
0x180003f28  mov     rax, qword ptr cs:aDll; ".dll"
0x180003f2f  mov     [rcx+r15*2], rax
0x180003f33  xor     eax, eax
0x180003f35  mov     [rcx+rdx*2], ax
0x180003f39  mov     rdi, [rbp+57h+Src]
0x180003f3d  jmp     loc_18000406F
0x180003f42  mov     rdx, 7FFFFFFFFFFFFFFEh
0x180003f4c  mov     rax, rdx
0x180003f4f  sub     rax, r15
0x180003f52  cmp     rax, 4
0x180003f56  jb      loc_18000432C
0x180003f5c  lea     r12, [r15+4]
0x180003f60  mov     rsi, r12
0x180003f63  or      rsi, 7
0x180003f67  cmp     rsi, rdx
0x180003f6a  ja      short loc_180003F7D
0x180003f6c  mov     rcx, r14
0x180003f6f  shr     rcx, 1
0x180003f72  mov     rax, rdx
0x180003f75  sub     rax, rcx
0x180003f78  cmp     r14, rax
0x180003f7b  jbe     short loc_180003FBC
0x180003f7d  mov     rsi, rdx
0x180003f80  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180003f87  cmp     rcx, 1000h
0x180003f8e  jb      short loc_180003FDD
0x180003f90  lea     rax, [rcx+27h]
0x180003f94  cmp     rax, rcx
0x180003f97  jbe     loc_180004332
0x180003f9d  mov     rcx, rax; Size
0x180003fa0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003fa5  test    rax, rax
0x180003fa8  jz      loc_1800042B9
0x180003fae  lea     rdi, [rax+27h]
0x180003fb2  and     rdi, 0FFFFFFFFFFFFFFE0h
0x180003fb6  mov     [rdi-8], rax
0x180003fba  jmp     short loc_180003FE5
0x180003fbc  lea     rax, [r14+rcx]
0x180003fc0  cmp     rsi, rax
0x180003fc3  cmovb   rsi, rax
0x180003fc7  lea     rcx, [rsi+1]
0x180003fcb  cmp     rcx, r13
0x180003fce  ja      loc_180004332
0x180003fd4  add     rcx, rcx
0x180003fd7  jnz     short loc_180003F87
0x180003fd9  xor     edi, edi
0x180003fdb  jmp     short loc_180003FE5
0x180003fdd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003fe2  mov     rdi, rax
0x180003fe5  mov     [rbp+57h+var_60], r12
0x180003fe9  mov     [rbp+57h+var_58], rsi
0x180003fed  add     r15, r15
0x180003ff0  mov     r8, r15; Size
0x180003ff3  mov     rcx, rdi; void *
0x180003ff6  cmp     r14, 7
0x180003ffa  jbe     short loc_180004050
0x180003ffc  mov     rsi, [rbp+57h+Src]
0x180004000  mov     rdx, rsi; Src
0x180004003  call    memcpy_0
0x180004008  mov     rax, qword ptr cs:aDll; ".dll"
0x18000400f  mov     [r15+rdi], rax
0x180004013  xor     eax, eax
0x180004015  mov     [rdi+r12*2], ax
0x18000401a  lea     rdx, ds:2[r14*2]; unsigned __int64
0x180004022  cmp     rdx, 1000h
0x180004029  jb      short loc_180004046
0x18000402b  mov     rcx, [rsi-8]
0x18000402f  sub     rsi, rcx
0x180004032  sub     rsi, 8
0x180004036  cmp     rsi, 1Fh
0x18000403a  ja      loc_1800042B9
0x180004040  add     rdx, 27h ; '''
0x180004044  jmp     short loc_180004049
0x180004046  mov     rcx, rsi; void *
0x180004049  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000404e  jmp     short loc_18000406B
  ... truncated ...
```
