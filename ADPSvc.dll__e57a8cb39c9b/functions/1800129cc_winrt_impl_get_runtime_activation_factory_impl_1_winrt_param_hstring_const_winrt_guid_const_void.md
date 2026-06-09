# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x1800129cc`
- end: `0x180012f14`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `1352`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180012860`

## callees

- `0x180002250`
- `0x1800026f0`
- `0x180002de0`
- `0x180003380`
- `0x1800034f2`
- `0x1800039f0`
- `0x180003a65`
- `0x180003a95`
- `0x180003ac5`
- `0x180003ad1`
- `0x180007b84`
- `0x18000c0c4`
- `0x18000c13c`
- `0x18000c37c`
- `0x18000f220`
- `0x180011704`
- `0x1800129cc`
- `0x1800ca010`

## string_xrefs

- `0x180012a43`: `combase.dll`
- `0x180012e5b`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  const wchar_t *v12; // rdx
  void **v13; // rsi
  char *v14; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // rdi
  void **v18; // rcx
  unsigned __int64 v19; // rsi
  unsigned __int64 v20; // r15
  void **v21; // rdx
  _WORD *v22; // rdi
  unsigned __int64 k; // rcx
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  char *v26; // r13
  size_t v27; // r8
  char *v28; // rdi
  _BYTE *v29; // r15
  unsigned __int64 j; // rcx
  unsigned __int64 v31; // rdx
  _BYTE *v32; // rcx
  unsigned __int64 i; // rcx
  void **v34; // rcx
  unsigned __int64 v35; // rsi
  unsigned __int64 v36; // r15
  void **v37; // rdx
  unsigned __int64 v38; // rdi
  _WORD *v39; // rdi
  unsigned __int64 ii; // rcx
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  char *v43; // r13
  size_t v44; // r8
  char *v45; // rsi
  _BYTE *v46; // rsi
  _WORD *v47; // rdi
  __int64 n; // rcx
  unsigned __int64 v49; // rdi
  unsigned __int64 v50; // rdx
  _BYTE *v51; // rcx
  char *v52; // rdi
  __int64 m; // rcx
  HMODULE v54; // rsi
  FARPROC v55; // rax
  __int64 v56; // rax
  unsigned __int64 v58; // [rsp+20h] [rbp-59h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-51h] BYREF
  __int64 v60; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int64 v61; // [rsp+38h] [rbp-41h]
  unsigned __int64 v62; // [rsp+40h] [rbp-39h]
  HMODULE hModule; // [rsp+48h] [rbp-31h]
  _QWORD *v64; // [rsp+50h] [rbp-29h]
  _QWORD *v65; // [rsp+58h] [rbp-21h]
  void *Src[2]; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int64 v67; // [rsp+70h] [rbp-9h]
  unsigned __int64 v68; // [rsp+78h] [rbp-1h]

  v65 = a4;
  v64 = a2;
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
    v58 = 0;
    ((void (__fastcall *)(unsigned __int64 *))ProcAddress)(&v58);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  *(_OWORD *)Src = 0;
  v67 = 0;
  v68 = 0;
  if ( *a2 )
    v12 = *(const wchar_t **)(*a2 + 16LL);
  else
    v12 = &S2;
  std::wstring::_Construct<1,wchar_t const *>(Src, v12);
  while ( 1 )
  {
    v13 = Src;
    if ( v68 > 7 )
      v13 = (void **)Src[0];
    if ( !v67 )
      break;
    v14 = (char *)v13 + 2 * v67;
    last_trivial_2 = _std_find_last_trivial_2(v13, v14, 46);
    if ( (char *)last_trivial_2 == v14 )
      break;
    v16 = (last_trivial_2 - (__int64)v13) >> 1;
    if ( v16 == -1 )
      break;
    v17 = v67;
    if ( v16 > v67 )
    {
      v19 = v16 - v67;
      v20 = v68;
      v61 = v68;
      if ( v16 - v67 > v68 - v67 )
      {
        if ( 0x7FFFFFFFFFFFFFFELL - v67 < v19 )
          goto LABEL_100;
        v24 = v16 | 7;
        if ( (v16 | 7) > 0x7FFFFFFFFFFFFFFELL || (v25 = v68 >> 1, v68 > 0x7FFFFFFFFFFFFFFELL - (v68 >> 1)) )
        {
          v24 = 0x7FFFFFFFFFFFFFFELL;
        }
        else if ( v24 < v68 + v25 )
        {
          v24 = v68 + v25;
        }
        v58 = v24;
        v26 = (char *)std::wstring::_Allocate_for_capacity<0>(v24, &v58);
        v67 = v16;
        v68 = v58;
        v27 = 2 * v17;
        v28 = &v26[2 * v17];
        if ( v20 <= 7 )
        {
          memcpy_0(v26, Src, v27);
          if ( v19 )
          {
            for ( i = v19; i; --i )
            {
              *(_WORD *)v28 = 0;
              v28 += 2;
            }
            do
              --v19;
            while ( v19 );
          }
          *(_WORD *)&v26[2 * v16] = 0;
        }
        else
        {
          v29 = Src[0];
          memcpy_0(v26, Src[0], v27);
          if ( v19 )
          {
            for ( j = v19; j; --j )
            {
              *(_WORD *)v28 = 0;
              v28 += 2;
            }
            do
              --v19;
            while ( v19 );
          }
          *(_WORD *)&v26[2 * v16] = 0;
          v31 = 2 * v61 + 2;
          if ( v31 < 0x1000 )
          {
            v32 = v29;
          }
          else
          {
            v32 = (_BYTE *)*((_QWORD *)v29 - 1);
            if ( (unsigned __int64)(v29 - v32 - 8) > 0x1F )
              goto LABEL_94;
            v31 = 2 * v61 + 41;
          }
          operator delete(v32, v31);
        }
        Src[0] = v26;
      }
      else
      {
        v67 = v16;
        v21 = Src;
        if ( v68 > 7 )
          v21 = (void **)Src[0];
        v22 = (_WORD *)v21 + v17;
        if ( v19 )
        {
          for ( k = v19; k; --k )
            *v22++ = 0;
          do
            --v19;
          while ( v19 );
        }
        *((_WORD *)v21 + v16) = 0;
      }
    }
    else
    {
      v67 = (last_trivial_2 - (__int64)v13) >> 1;
      v18 = Src;
      if ( v68 > 7 )
        v18 = (void **)Src[0];
      *((_WORD *)v18 + v16) = 0;
    }
    std::wstring::operator+=(Src, L".dll");
    v34 = Src;
    if ( v68 > 7 )
      v34 = (void **)Src[0];
    hModule = LoadLibraryExW_0((LPCWSTR)v34, 0, 0x1000u);
    v35 = v67;
    v36 = v67 - 4;
    if ( v67 < 4 )
    {
      v38 = v68;
      v62 = v68;
      if ( v68 - v67 < 0xFFFFFFFFFFFFFFFCuLL )
      {
        if ( 0x7FFFFFFFFFFFFFFELL - v67 < 0xFFFFFFFFFFFFFFFCuLL )
LABEL_100:
          std::_Xlen_string();
        v41 = v36 | 7;
        if ( (v36 | 7) > 0x7FFFFFFFFFFFFFFELL || (v42 = v68 >> 1, v68 > 0x7FFFFFFFFFFFFFFELL - (v68 >> 1)) )
        {
          v41 = 0x7FFFFFFFFFFFFFFELL;
        }
        else if ( v41 < v68 + v42 )
        {
          v41 = v68 + v42;
        }
        v58 = v41;
        v43 = (char *)std::wstring::_Allocate_for_capacity<0>(v41, &v58);
        v67 = v36;
        v68 = v58;
        v44 = 2 * v35;
        v45 = &v43[2 * v35];
        v61 = (unsigned __int64)v45;
        if ( v38 <= 7 )
        {
          memcpy_0(v43, Src, v44);
          v52 = v45;
          for ( m = -4; m; --m )
          {
            *(_WORD *)v52 = 0;
            v52 += 2;
          }
          *(_WORD *)&v43[2 * v36] = 0;
        }
        else
        {
          v46 = Src[0];
          memcpy_0(v43, Src[0], v44);
          v47 = (_WORD *)v61;
          for ( n = -4; n; --n )
            *v47++ = 0;
          v49 = v62;
          *(_WORD *)&v43[2 * v36] = 0;
          v50 = 2 * v49 + 2;
          if ( v50 < 0x1000 )
          {
            v51 = v46;
          }
          else
          {
            v51 = (_BYTE *)*((_QWORD *)v46 - 1);
            if ( (unsigned __int64)(v46 - v51 - 8) > 0x1F )
LABEL_94:
              __fastfail(5u);
            v50 = 2 * v49 + 41;
          }
          operator delete(v51, v50);
        }
        Src[0] = v43;
        goto LABEL_88;
      }
      v67 -= 4LL;
      v37 = Src;
      if ( v68 > 7 )
        v37 = (void **)Src[0];
      v39 = (_WORD *)v37 + v35;
      for ( ii = v36 - v35; ii; --ii )
        *v39++ = 0;
    }
    else
    {
      v67 -= 4LL;
      v37 = Src;
      if ( v68 > 7 )
        v37 = (void **)Src[0];
    }
    *((_WORD *)v37 + v36) = 0;
LABEL_88:
    v54 = hModule;
    if ( hModule )
    {
      v55 = WINRT_IMPL_GetProcAddress(hModule, "DllGetActivationFactory");
      if ( v55 )
      {
        v60 = 0;
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v55)(*v64, &v60) )
        {
          v56 = v60;
          v60 = 0;
          *v65 = v56;
          *a1 = 0;
          goto LABEL_97;
        }
        if ( v60 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v60);
      }
      WINRT_IMPL_FreeLibrary(v54);
    }
  }
  SetErrorInfo_0(0, pperrinfo);
  *a1 = ActivationFactory_0;
LABEL_97:
  std::wstring::~wstring(Src);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x1800129cc  push    rbp
0x1800129ce  push    rbx
0x1800129cf  push    rsi
0x1800129d0  push    rdi
0x1800129d1  push    r12
0x1800129d3  push    r13
0x1800129d5  push    r14
0x1800129d7  push    r15
0x1800129d9  lea     rbp, [rsp-1Fh]
0x1800129de  sub     rsp, 98h
0x1800129e5  mov     rax, cs:__security_cookie
0x1800129ec  xor     rax, rsp
0x1800129ef  mov     [rbp+57h+var_50], rax
0x1800129f3  mov     rsi, r9
0x1800129f6  mov     [rbp+57h+var_78], r9
0x1800129fa  mov     rdi, r8
0x1800129fd  mov     r14, rdx
0x180012a00  mov     [rbp+57h+var_80], rdx
0x180012a04  mov     r12, rcx
0x180012a07  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180012a0e  xor     r13d, r13d
0x180012a11  mov     r8, r9
0x180012a14  mov     rdx, rdi
0x180012a17  mov     rcx, [r14]
0x180012a1a  test    rax, rax
0x180012a1d  jz      short loc_180012A2D
0x180012a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a24  mov     [r12], eax
0x180012a28  jmp     loc_180012EEB
0x180012a2d  call    RoGetActivationFactory_0
0x180012a32  mov     ebx, eax
0x180012a34  cmp     eax, 800401F0h
0x180012a39  jnz     short loc_180012A89
0x180012a3b  xor     edx, edx; hFile
0x180012a3d  mov     r8d, 1000h; dwFlags
0x180012a43  lea     rcx, LibFileName; "combase.dll"
0x180012a4a  call    LoadLibraryExW_0
0x180012a4f  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180012a56  mov     rcx, rax; hModule
0x180012a59  call    WINRT_IMPL_GetProcAddress
0x180012a5e  test    rax, rax
0x180012a61  jnz     short loc_180012A6C
0x180012a63  mov     [r12], ebx
0x180012a67  jmp     loc_180012EEB
0x180012a6c  mov     [rbp+57h+var_B0], r13
0x180012a70  lea     rcx, [rbp+57h+var_B0]
0x180012a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a79  mov     r8, rsi
0x180012a7c  mov     rdx, rdi
0x180012a7f  mov     rcx, [r14]
0x180012a82  call    RoGetActivationFactory_0
0x180012a87  mov     ebx, eax
0x180012a89  test    ebx, ebx
0x180012a8b  jnz     short loc_180012A96
0x180012a8d  mov     [r12], r13d
0x180012a91  jmp     loc_180012EEB
0x180012a96  mov     [rbp+57h+pperrinfo], r13
0x180012a9a  lea     rdx, [rbp+57h+pperrinfo]; pperrinfo
0x180012a9e  xor     ecx, ecx; dwReserved
0x180012aa0  call    GetErrorInfo_0
0x180012aa5  xorps   xmm0, xmm0
0x180012aa8  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180012aac  mov     [rbp+57h+var_60], r13
0x180012ab0  mov     [rbp+57h+var_58], r13
0x180012ab4  mov     rax, [r14]
0x180012ab7  test    rax, rax
0x180012aba  jz      short loc_180012AC6
0x180012abc  mov     rdx, [rax+10h]
0x180012ac0  mov     r8d, [rax+4]
0x180012ac4  jmp     short loc_180012AD0
0x180012ac6  lea     rdx, S2
0x180012acd  mov     r8, r13
0x180012ad0  lea     rcx, [rbp+57h+Src]
0x180012ad4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180012ad9  or      r15, 0FFFFFFFFFFFFFFFFh
0x180012add  mov     rax, [rbp+57h+var_60]
0x180012ae1  lea     rsi, [rbp+57h+Src]
0x180012ae5  cmp     [rbp+57h+var_58], 7
0x180012aea  cmova   rsi, [rbp+57h+Src]
0x180012aef  test    rax, rax
0x180012af2  jz      loc_180012EC4
0x180012af8  dec     rax
0x180012afb  cmp     rax, r15
0x180012afe  cmovnb  rax, r15
0x180012b02  inc     rax
0x180012b05  lea     rdi, [rsi+rax*2]
0x180012b09  mov     r8d, 2Eh ; '.'
0x180012b0f  mov     rdx, rdi
0x180012b12  mov     rcx, rsi
0x180012b15  call    __std_find_last_trivial_2
0x180012b1a  mov     r14, rax
0x180012b1d  cmp     rax, rdi
0x180012b20  jz      loc_180012EC4
0x180012b26  sub     r14, rsi
0x180012b29  sar     r14, 1
0x180012b2c  cmp     r14, r15
0x180012b2f  jz      loc_180012EC4
0x180012b35  mov     rdi, [rbp+57h+var_60]
0x180012b39  cmp     r14, rdi
0x180012b3c  ja      short loc_180012B5A
0x180012b3e  mov     [rbp+57h+var_60], r14
0x180012b42  lea     rcx, [rbp+57h+Src]
0x180012b46  cmp     [rbp+57h+var_58], 7
0x180012b4b  cmova   rcx, [rbp+57h+Src]
0x180012b50  mov     [rcx+r14*2], r13w
0x180012b55  jmp     loc_180012CAC
0x180012b5a  mov     rsi, r14
0x180012b5d  sub     rsi, rdi
0x180012b60  mov     r15, [rbp+57h+var_58]
0x180012b64  mov     [rbp+57h+var_98], r15
0x180012b68  mov     rax, r15
0x180012b6b  sub     rax, rdi
0x180012b6e  cmp     rsi, rax
0x180012b71  ja      short loc_180012BA7
0x180012b73  mov     [rbp+57h+var_60], r14
0x180012b77  lea     rdx, [rbp+57h+Src]
0x180012b7b  cmp     r15, 7
0x180012b7f  cmova   rdx, [rbp+57h+Src]
0x180012b84  lea     rdi, [rdx+rdi*2]
0x180012b88  test    rsi, rsi
0x180012b8b  jz      short loc_180012B9D
0x180012b8d  movzx   eax, r13w
0x180012b91  mov     rcx, rsi
0x180012b94  rep stosw
0x180012b97  sub     rsi, 1
0x180012b9b  jnz     short loc_180012B97
0x180012b9d  mov     [rdx+r14*2], r13w
0x180012ba2  jmp     loc_180012CAC
0x180012ba7  mov     r8, 7FFFFFFFFFFFFFFEh
0x180012bb1  mov     rax, r8
0x180012bb4  sub     rax, rdi
0x180012bb7  cmp     rax, rsi
0x180012bba  jb      loc_180012F0E
0x180012bc0  mov     rcx, r14
0x180012bc3  or      rcx, 7
0x180012bc7  cmp     rcx, r8
0x180012bca  jbe     short loc_180012BD1
0x180012bcc  mov     rcx, r8
0x180012bcf  jmp     short loc_180012BED
0x180012bd1  mov     rdx, r15
0x180012bd4  shr     rdx, 1
0x180012bd7  mov     rax, r8
0x180012bda  sub     rax, rdx
0x180012bdd  cmp     r15, rax
0x180012be0  ja      short loc_180012BCC
0x180012be2  lea     rax, [r15+rdx]
0x180012be6  cmp     rcx, rax
0x180012be9  cmovb   rcx, rax
0x180012bed  mov     [rbp+57h+var_B0], rcx
0x180012bf1  lea     rdx, [rbp+57h+var_B0]
0x180012bf5  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180012bfa  mov     r13, rax
0x180012bfd  mov     [rbp+57h+var_60], r14
0x180012c01  mov     rcx, [rbp+57h+var_B0]
0x180012c05  mov     [rbp+57h+var_58], rcx
0x180012c09  lea     r8, [rdi+rdi]; Size
0x180012c0d  lea     rdi, [r8+rax]
0x180012c11  mov     rcx, rax; void *
0x180012c14  cmp     r15, 7
0x180012c18  jbe     short loc_180012C7E
0x180012c1a  mov     r15, [rbp+57h+Src]
0x180012c1e  mov     rdx, r15; Src
0x180012c21  call    memcpy_0
0x180012c26  test    rsi, rsi
0x180012c29  jz      short loc_180012C3C
0x180012c2b  xor     eax, eax
0x180012c2d  movzx   eax, ax
0x180012c30  mov     rcx, rsi
0x180012c33  rep stosw
0x180012c36  sub     rsi, 1
0x180012c3a  jnz     short loc_180012C36
0x180012c3c  xor     eax, eax
0x180012c3e  mov     [r13+r14*2+0], ax
0x180012c44  mov     rdx, [rbp+57h+var_98]
0x180012c48  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180012c50  cmp     rdx, 1000h
0x180012c57  jb      short loc_180012C74
0x180012c59  mov     rcx, [r15-8]
0x180012c5d  sub     r15, rcx
0x180012c60  sub     r15, 8
0x180012c64  cmp     r15, 1Fh
0x180012c68  ja      loc_180012EA8
0x180012c6e  add     rdx, 27h ; '''
0x180012c72  jmp     short loc_180012C77
0x180012c74  mov     rcx, r15; void *
0x180012c77  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012c7c  jmp     short loc_180012CA5
0x180012c7e  lea     rdx, [rbp+57h+Src]; Src
0x180012c82  call    memcpy_0
0x180012c87  test    rsi, rsi
0x180012c8a  jz      short loc_180012C9D
0x180012c8c  xor     eax, eax
0x180012c8e  movzx   eax, ax
0x180012c91  mov     rcx, rsi
0x180012c94  rep stosw
0x180012c97  sub     rsi, 1
0x180012c9b  jnz     short loc_180012C97
0x180012c9d  xor     eax, eax
0x180012c9f  mov     [r13+r14*2+0], ax
0x180012ca5  mov     [rbp+57h+Src], r13
0x180012ca9  xor     r13d, r13d
0x180012cac  lea     rdx, aDll; ".dll"
0x180012cb3  lea     rcx, [rbp+57h+Src]; Src
0x180012cb7  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator+=(wchar_t const * const)
0x180012cbc  lea     rcx, [rbp+57h+Src]
0x180012cc0  cmp     [rbp+57h+var_58], 7
0x180012cc5  cmova   rcx, [rbp+57h+Src]; lpLibFileName
0x180012cca  xor     edx, edx; hFile
0x180012ccc  mov     r8d, 1000h; dwFlags
0x180012cd2  call    LoadLibraryExW_0
0x180012cd7  mov     [rbp+57h+hModule], rax
0x180012cdb  mov     rsi, [rbp+57h+var_60]
0x180012cdf  lea     r15, [rsi-4]
0x180012ce3  cmp     r15, rsi
0x180012ce6  ja      short loc_180012CFC
0x180012ce8  mov     [rbp+57h+var_60], r15
0x180012cec  lea     rdx, [rbp+57h+Src]
0x180012cf0  cmp     [rbp+57h+var_58], 7
0x180012cf5  cmova   rdx, [rbp+57h+Src]
0x180012cfa  jmp     short loc_180012D39
0x180012cfc  mov     r14, r15
0x180012cff  sub     r14, rsi
0x180012d02  mov     rdi, [rbp+57h+var_58]
0x180012d06  mov     [rbp+57h+var_90], rdi
0x180012d0a  mov     rax, rdi
0x180012d0d  sub     rax, rsi
0x180012d10  cmp     r14, rax
0x180012d13  ja      short loc_180012D43
0x180012d15  mov     [rbp+57h+var_60], r15
0x180012d19  lea     rdx, [rbp+57h+Src]
0x180012d1d  cmp     rdi, 7
0x180012d21  cmova   rdx, [rbp+57h+Src]
0x180012d26  lea     rdi, [rdx+rsi*2]
0x180012d2a  test    r14, r14
0x180012d2d  jz      short loc_180012D39
0x180012d2f  movzx   eax, r13w
0x180012d33  mov     rcx, r14
0x180012d36  rep stosw
0x180012d39  mov     [rdx+r15*2], r13w
0x180012d3e  jmp     loc_180012E47
0x180012d43  mov     r8, 7FFFFFFFFFFFFFFEh
0x180012d4d  mov     rax, r8
0x180012d50  sub     rax, rsi
0x180012d53  cmp     rax, r14
0x180012d56  jb      loc_180012F0E
0x180012d5c  mov     rcx, r15
0x180012d5f  or      rcx, 7
0x180012d63  cmp     rcx, r8
0x180012d66  jbe     short loc_180012D6D
0x180012d68  mov     rcx, r8
0x180012d6b  jmp     short loc_180012D89
0x180012d6d  mov     rdx, rdi
0x180012d70  shr     rdx, 1
0x180012d73  mov     rax, r8
0x180012d76  sub     rax, rdx
0x180012d79  cmp     rdi, rax
0x180012d7c  ja      short loc_180012D68
0x180012d7e  lea     rax, [rdi+rdx]
0x180012d82  cmp     rcx, rax
0x180012d85  cmovb   rcx, rax
0x180012d89  mov     [rbp+57h+var_B0], rcx
0x180012d8d  lea     rdx, [rbp+57h+var_B0]
0x180012d91  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180012d96  mov     r13, rax
0x180012d99  mov     [rbp+57h+var_60], r15
0x180012d9d  mov     rcx, [rbp+57h+var_B0]
0x180012da1  mov     [rbp+57h+var_58], rcx
0x180012da5  lea     r8, [rsi+rsi]; Size
0x180012da9  lea     rsi, [r8+rax]
0x180012dad  mov     [rbp+57h+var_98], rsi
0x180012db1  mov     rcx, rax; void *
0x180012db4  cmp     rdi, 7
0x180012db8  jbe     short loc_180012E1C
0x180012dba  mov     rsi, [rbp+57h+Src]
0x180012dbe  mov     rdx, rsi; Src
0x180012dc1  call    memcpy_0
0x180012dc6  test    r14, r14
0x180012dc9  jz      short loc_180012DDE
0x180012dcb  xor     eax, eax
0x180012dcd  movzx   eax, ax
0x180012dd0  mov     rdi, [rbp+57h+var_98]
0x180012dd4  mov     rcx, r14
0x180012dd7  rep stosw
0x180012dda  mov     rdi, [rbp+57h+var_90]
0x180012dde  xor     eax, eax
0x180012de0  mov     [r13+r15*2+0], ax
0x180012de6  lea     rdx, ds:2[rdi*2]; unsigned __int64
0x180012dee  cmp     rdx, 1000h
0x180012df5  jb      short loc_180012E12
0x180012df7  mov     rcx, [rsi-8]
0x180012dfb  sub     rsi, rcx
0x180012dfe  sub     rsi, 8
0x180012e02  cmp     rsi, 1Fh
0x180012e06  ja      loc_180012EA8
0x180012e0c  add     rdx, 27h ; '''
0x180012e10  jmp     short loc_180012E15
0x180012e12  mov     rcx, rsi; void *
0x180012e15  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012e1a  jmp     short loc_180012E40
0x180012e1c  lea     rdx, [rbp+57h+Src]; Src
  ... truncated ...
```
