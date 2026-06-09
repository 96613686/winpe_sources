# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180011f78`
- end: `0x1800122e7`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `879`
- prototype: ``
- caller_count: `16`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fd20`
- `0x18001008c`
- `0x180010524`
- `0x1800106d4`
- `0x180010870`
- `0x180011114`
- `0x180011384`
- `0x1800114cc`
- `0x180011c78`
- `0x180011cd8`
- `0x180011d38`
- `0x180011d98`
- `0x180011df8`
- `0x180011e58`
- `0x180011eb8`
- `0x180011f18`

## callees

- `0x180002590`
- `0x180003090`
- `0x1800030b4`
- `0x180003470`
- `0x180003b8d`
- `0x180003bbd`
- `0x180003bc9`
- `0x180003bd5`
- `0x18000f29c`
- `0x18000fa64`
- `0x18000fba4`
- `0x180011f78`
- `0x180013890`
- `0x180024f28`
- `0x180033010`

## string_xrefs

- `0x180011fe0`: `combase.dll`
- `0x180012227`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  char *v13; // rdx
  __int64 v14; // r8
  LPCWSTR *v15; // r14
  char *v16; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdi
  LPCWSTR *v20; // rcx
  unsigned __int64 v21; // rcx
  LPCWSTR *v22; // r8
  _WORD *v23; // rdi
  unsigned __int64 v24; // rdi
  LPCWSTR *v25; // rcx
  const WCHAR *v26; // rcx
  HMODULE v27; // rdi
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // r8
  LPCWSTR *v30; // rcx
  FARPROC v31; // rax
  unsigned int (__fastcall ***v33)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v36; // [rsp+50h] [rbp-28h]
  unsigned __int64 v37; // [rsp+58h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
    return a1;
  }
  ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
  if ( ActivationFactory_0 == -2147221008 )
  {
    Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
    ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
    if ( !ProcAddress )
    {
      *a1 = -2147221008;
      return a1;
    }
    v33 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v33);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  *(_OWORD *)lpLibFileName = 0;
  v36 = 0;
  v37 = 0;
  v12 = *a2;
  if ( *a2 )
  {
    v13 = *(char **)(v12 + 16);
    v14 = *(unsigned int *)(v12 + 4);
  }
  else
  {
    v13 = byte_180035C10;
    v14 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v13, v14);
  while ( 1 )
  {
    do
    {
      v15 = lpLibFileName;
      if ( v37 > 7 )
        v15 = (LPCWSTR *)lpLibFileName[0];
      if ( !v36
        || (v16 = (char *)v15 + 2 * v36,
            last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46),
            (char *)last_trivial_2 == v16)
        || (v18 = (last_trivial_2 - (__int64)v15) >> 1, v18 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_57;
      }
      v19 = v36;
      if ( v18 > v36 )
      {
        v21 = v18 - v36;
        if ( v18 - v36 > v37 - v36 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpLibFileName);
        }
        else
        {
          v36 = (last_trivial_2 - (__int64)v15) >> 1;
          v22 = lpLibFileName;
          if ( v37 > 7 )
            v22 = (LPCWSTR *)lpLibFileName[0];
          v23 = (_WORD *)v22 + v19;
          if ( v21 )
          {
            while ( v21 )
            {
              *v23++ = 0;
              --v21;
            }
          }
          *((_WORD *)v22 + v18) = 0;
        }
      }
      else
      {
        v36 = (last_trivial_2 - (__int64)v15) >> 1;
        v20 = lpLibFileName;
        if ( v37 > 7 )
          v20 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v20 + v18) = 0;
      }
      v24 = v36;
      if ( v37 - v36 < 4 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          lpLibFileName,
          4);
      }
      else
      {
        v36 += 4LL;
        v25 = lpLibFileName;
        if ( v37 > 7 )
          v25 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v25 + 2 * v24) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v25 + v24 + 4) = 0;
      }
      v26 = (const WCHAR *)lpLibFileName;
      if ( v37 > 7 )
        v26 = lpLibFileName[0];
      v27 = LoadLibraryExW_0(v26, 0, 0x1000u);
      v28 = v36;
      v29 = v36 - 4;
      v30 = lpLibFileName;
      if ( v36 >= 4 )
      {
        v36 -= 4LL;
        if ( v37 > 7 )
          v30 = (LPCWSTR *)lpLibFileName[0];
LABEL_45:
        *((_WORD *)v30 + v29) = 0;
        continue;
      }
      if ( v37 - v36 >= 0xFFFFFFFFFFFFFFFCuLL )
      {
        v36 -= 4LL;
        if ( v37 > 7 )
          v30 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v30 + 2 * v28) = 0;
        goto LABEL_45;
      }
      std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpLibFileName);
    }
    while ( !v27 );
    v31 = WINRT_IMPL_GetProcAddress(v27, "DllGetActivationFactory");
    if ( !v31 )
      goto LABEL_53;
    v33 = 0;
    if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v31)(
            *a2,
            &v33)
      && !(**v33)(v33, a3, a4) )
    {
      break;
    }
    if ( v33 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v33);
LABEL_53:
    WINRT_IMPL_FreeLibrary(v27);
  }
  *a1 = 0;
  if ( v33 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v33);
LABEL_57:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180011f78  push    rbp
0x180011f7a  push    rbx
0x180011f7b  push    rsi
0x180011f7c  push    rdi
0x180011f7d  push    r12
0x180011f7f  push    r13
0x180011f81  push    r14
0x180011f83  push    r15
0x180011f85  mov     rbp, rsp
0x180011f88  sub     rsp, 78h
0x180011f8c  mov     rax, cs:__security_cookie
0x180011f93  xor     rax, rsp
0x180011f96  mov     [rbp+var_18], rax
0x180011f9a  mov     r13, r9
0x180011f9d  mov     r12, r8
0x180011fa0  mov     r15, rdx
0x180011fa3  mov     rsi, rcx
0x180011fa6  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180011fad  xor     r14d, r14d
0x180011fb0  mov     r8, r9
0x180011fb3  mov     rdx, r12
0x180011fb6  mov     rcx, [r15]
0x180011fb9  test    rax, rax
0x180011fbc  jz      short loc_180011FCA
0x180011fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fc3  mov     [rsi], eax
0x180011fc5  jmp     loc_1800122C7
0x180011fca  call    RoGetActivationFactory_0
0x180011fcf  mov     ebx, eax
0x180011fd1  cmp     eax, 800401F0h
0x180011fd6  jnz     short loc_180012028
0x180011fd8  xor     edx, edx; hFile
0x180011fda  mov     r8d, 1000h; dwFlags
0x180011fe0  lea     rcx, LibFileName; "combase.dll"
0x180011fe7  call    LoadLibraryExW_0
0x180011fec  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180011ff3  mov     rcx, rax; hModule
0x180011ff6  call    WINRT_IMPL_GetProcAddress
0x180011ffb  test    rax, rax
0x180011ffe  jnz     short loc_18001200B
0x180012000  mov     dword ptr [rsi], 800401F0h
0x180012006  jmp     loc_1800122C7
0x18001200b  mov     [rbp+var_48], r14
0x18001200f  lea     rcx, [rbp+var_48]
0x180012013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012018  mov     r8, r13
0x18001201b  mov     rdx, r12
0x18001201e  mov     rcx, [r15]
0x180012021  call    RoGetActivationFactory_0
0x180012026  mov     ebx, eax
0x180012028  test    ebx, ebx
0x18001202a  jnz     short loc_180012034
0x18001202c  mov     [rsi], r14d
0x18001202f  jmp     loc_1800122C7
0x180012034  mov     [rbp+pperrinfo], r14
0x180012038  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001203c  xor     ecx, ecx; dwReserved
0x18001203e  call    GetErrorInfo_0
0x180012043  xorps   xmm0, xmm0
0x180012046  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18001204a  mov     [rbp+var_28], r14
0x18001204e  mov     [rbp+var_20], r14
0x180012052  mov     rax, [r15]
0x180012055  test    rax, rax
0x180012058  jz      short loc_180012064
0x18001205a  mov     rdx, [rax+10h]
0x18001205e  mov     r8d, [rax+4]
0x180012062  jmp     short loc_18001206E
0x180012064  lea     rdx, byte_180035C10
0x18001206b  mov     r8, r14
0x18001206e  lea     rcx, [rbp+lpLibFileName]
0x180012072  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180012077  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001207b  mov     rax, [rbp+var_28]
0x18001207f  lea     r14, [rbp+lpLibFileName]
0x180012083  cmp     [rbp+var_20], 7
0x180012088  cmova   r14, [rbp+lpLibFileName]
0x18001208d  test    rax, rax
0x180012090  jz      loc_1800122A1
0x180012096  dec     rax
0x180012099  cmp     rax, rcx
0x18001209c  cmovnb  rax, rcx
0x1800120a0  inc     rax
0x1800120a3  lea     rdi, [r14+rax*2]
0x1800120a7  mov     r8d, 2Eh ; '.'
0x1800120ad  mov     rdx, rdi
0x1800120b0  mov     rcx, r14
0x1800120b3  call    __std_find_last_trivial_2
0x1800120b8  mov     rdx, rax
0x1800120bb  cmp     rax, rdi
0x1800120be  jz      loc_1800122A1
0x1800120c4  sub     rdx, r14
0x1800120c7  sar     rdx, 1
0x1800120ca  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800120ce  jz      loc_1800122A1
0x1800120d4  mov     rdi, [rbp+var_28]
0x1800120d8  cmp     rdx, rdi
0x1800120db  ja      short loc_1800120F7
0x1800120dd  mov     [rbp+var_28], rdx
0x1800120e1  lea     rcx, [rbp+lpLibFileName]
0x1800120e5  cmp     [rbp+var_20], 7
0x1800120ea  cmova   rcx, [rbp+lpLibFileName]
0x1800120ef  xor     eax, eax
0x1800120f1  mov     [rcx+rdx*2], ax
0x1800120f5  jmp     short loc_180012144
0x1800120f7  mov     rcx, rdx
0x1800120fa  sub     rcx, rdi
0x1800120fd  mov     rax, [rbp+var_20]
0x180012101  sub     rax, rdi
0x180012104  cmp     rcx, rax
0x180012107  ja      short loc_180012135
0x180012109  mov     [rbp+var_28], rdx
0x18001210d  lea     r8, [rbp+lpLibFileName]
0x180012111  cmp     [rbp+var_20], 7
0x180012116  cmova   r8, [rbp+lpLibFileName]
0x18001211b  lea     rdi, [r8+rdi*2]
0x18001211f  test    rcx, rcx
0x180012122  jz      short loc_18001212C
0x180012124  xor     eax, eax
0x180012126  movzx   eax, ax
0x180012129  rep stosw
0x18001212c  xor     eax, eax
0x18001212e  mov     [r8+rdx*2], ax
0x180012133  jmp     short loc_180012144
0x180012135  mov     r9, rcx
0x180012138  mov     rdx, rcx
0x18001213b  lea     rcx, [rbp+lpLibFileName]; Src
0x18001213f  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180012144  mov     rdi, [rbp+var_28]
0x180012148  mov     rax, [rbp+var_20]
0x18001214c  sub     rax, rdi
0x18001214f  mov     ecx, 4
0x180012154  cmp     rax, rcx
0x180012157  jb      short loc_180012185
0x180012159  lea     rdx, [rdi+4]
0x18001215d  mov     [rbp+var_28], rdx
0x180012161  lea     rcx, [rbp+lpLibFileName]
0x180012165  cmp     [rbp+var_20], 7
0x18001216a  cmova   rcx, [rbp+lpLibFileName]
0x18001216f  mov     rax, 6C006C0064002Eh
0x180012179  mov     [rcx+rdi*2], rax
0x18001217d  xor     eax, eax
0x18001217f  mov     [rcx+rdx*2], ax
0x180012183  jmp     short loc_18001219D
0x180012185  mov     [rsp+78h+var_58], rcx; __int64
0x18001218a  lea     r9, aDll; ".dll"
0x180012191  mov     rdx, rcx
0x180012194  lea     rcx, [rbp+lpLibFileName]; Src
0x180012198  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18001219d  lea     rcx, [rbp+lpLibFileName]
0x1800121a1  cmp     [rbp+var_20], 7
0x1800121a6  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800121ab  xor     edx, edx; hFile
0x1800121ad  mov     r8d, 1000h; dwFlags
0x1800121b3  call    LoadLibraryExW_0
0x1800121b8  mov     rdi, rax
0x1800121bb  mov     rdx, [rbp+var_28]
0x1800121bf  lea     r8, [rdx-4]
0x1800121c3  lea     rcx, [rbp+lpLibFileName]; Src
0x1800121c7  cmp     r8, rdx
0x1800121ca  ja      short loc_1800121DE
0x1800121cc  mov     [rbp+var_28], r8
0x1800121d0  cmp     [rbp+var_20], 7
0x1800121d5  cmova   rcx, [rbp+lpLibFileName]
0x1800121da  xor     eax, eax
0x1800121dc  jmp     short loc_180012205
0x1800121de  mov     rax, [rbp+var_20]
0x1800121e2  sub     rax, rdx
0x1800121e5  mov     r10, 0FFFFFFFFFFFFFFFCh
0x1800121ec  cmp     rax, r10
0x1800121ef  jb      short loc_18001220C
0x1800121f1  mov     [rbp+var_28], r8
0x1800121f5  cmp     [rbp+var_20], 7
0x1800121fa  cmova   rcx, [rbp+lpLibFileName]
0x1800121ff  xor     eax, eax
0x180012201  mov     [rcx+rdx*2], rax
0x180012205  mov     [rcx+r8*2], ax
0x18001220a  jmp     short loc_180012217
0x18001220c  mov     r9, r10
0x18001220f  mov     rdx, r10
0x180012212  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180012217  test    rdi, rdi
0x18001221a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012221  jz      loc_18001207B
0x180012227  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x18001222e  mov     rcx, rdi; hModule
0x180012231  call    WINRT_IMPL_GetProcAddress
0x180012236  test    rax, rax
0x180012239  jz      short loc_18001227C
0x18001223b  mov     [rbp+var_48], 0
0x180012243  lea     rdx, [rbp+var_48]
0x180012247  mov     rcx, [r15]
0x18001224a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001224f  test    eax, eax
0x180012251  jnz     short loc_18001226C
0x180012253  mov     rcx, [rbp+var_48]
0x180012257  mov     rax, [rcx]
0x18001225a  mov     r8, r13
0x18001225d  mov     rdx, r12
0x180012260  mov     rax, [rax]
0x180012263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012268  test    eax, eax
0x18001226a  jz      short loc_180012289
0x18001226c  cmp     [rbp+var_48], 0
0x180012271  jz      short loc_18001227C
0x180012273  lea     rcx, [rbp+var_48]
0x180012277  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001227c  mov     rcx, rdi; hLibModule
0x18001227f  call    WINRT_IMPL_FreeLibrary
0x180012284  jmp     loc_180012077
0x180012289  mov     dword ptr [rsi], 0
0x18001228f  cmp     [rbp+var_48], 0
0x180012294  jz      short loc_1800122AE
0x180012296  lea     rcx, [rbp+var_48]
0x18001229a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001229f  jmp     short loc_1800122AE
0x1800122a1  mov     rdx, [rbp+pperrinfo]; perrinfo
0x1800122a5  xor     ecx, ecx; dwReserved
0x1800122a7  call    SetErrorInfo_0
0x1800122ac  mov     [rsi], ebx
0x1800122ae  lea     rcx, [rbp+lpLibFileName]
0x1800122b2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800122b7  cmp     [rbp+pperrinfo], 0
0x1800122bc  jz      short loc_1800122C7
0x1800122be  lea     rcx, [rbp+pperrinfo]
0x1800122c2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800122c7  mov     rax, rsi
0x1800122ca  mov     rcx, [rbp+var_18]
0x1800122ce  xor     rcx, rsp; StackCookie
0x1800122d1  call    __security_check_cookie
0x1800122d6  add     rsp, 78h
0x1800122da  pop     r15
0x1800122dc  pop     r14
0x1800122de  pop     r13
0x1800122e0  pop     r12
0x1800122e2  pop     rdi
0x1800122e3  pop     rsi
0x1800122e4  pop     rbx
0x1800122e5  pop     rbp
0x1800122e6  retn
```
