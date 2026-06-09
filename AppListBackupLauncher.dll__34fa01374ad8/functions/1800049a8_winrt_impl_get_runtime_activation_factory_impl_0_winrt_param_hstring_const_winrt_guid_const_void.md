# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x1800049a8`
- end: `0x180004ceb`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `835`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800047c0`

## callees

- `0x180001f00`
- `0x180002300`
- `0x180002eac`
- `0x180002ec4`
- `0x180002ee5`
- `0x180002ef1`
- `0x180002f45`
- `0x180002f5d`
- `0x1800032ac`
- `0x180004428`
- `0x1800045b4`
- `0x1800049a8`
- `0x180005ac4`
- `0x18000f544`
- `0x180012010`

## string_xrefs

- `0x180004a11`: `combase.dll`
- `0x180004c2a`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  LPCWSTR *v12; // r14
  char *v13; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  LPCWSTR *v17; // rcx
  unsigned __int64 v18; // rcx
  LPCWSTR *v19; // r8
  _WORD *v20; // rdi
  unsigned __int64 v21; // rdi
  LPCWSTR *v22; // rcx
  const WCHAR *v23; // rcx
  HMODULE v24; // rdi
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // r8
  LPCWSTR *v27; // rcx
  FARPROC v28; // rax
  unsigned int (__fastcall ***v30)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-28h]
  unsigned __int64 v34; // [rsp+58h] [rbp-20h]

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
    v30 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v30);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  std::wstring::wstring(lpLibFileName, a2);
  while ( 1 )
  {
    do
    {
      v12 = lpLibFileName;
      if ( v34 > 7 )
        v12 = (LPCWSTR *)lpLibFileName[0];
      if ( !v33
        || (v13 = (char *)v12 + 2 * v33,
            last_trivial_2 = _std_find_last_trivial_2(v12, v13, 46),
            (char *)last_trivial_2 == v13)
        || (v15 = (last_trivial_2 - (__int64)v12) >> 1, v15 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_54;
      }
      v16 = v33;
      if ( v15 > v33 )
      {
        v18 = v15 - v33;
        if ( v15 - v33 > v34 - v33 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpLibFileName);
        }
        else
        {
          v33 = (last_trivial_2 - (__int64)v12) >> 1;
          v19 = lpLibFileName;
          if ( v34 > 7 )
            v19 = (LPCWSTR *)lpLibFileName[0];
          v20 = (_WORD *)v19 + v16;
          if ( v18 )
          {
            while ( v18 )
            {
              *v20++ = 0;
              --v18;
            }
          }
          *((_WORD *)v19 + v15) = 0;
        }
      }
      else
      {
        v33 = (last_trivial_2 - (__int64)v12) >> 1;
        v17 = lpLibFileName;
        if ( v34 > 7 )
          v17 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v17 + v15) = 0;
      }
      v21 = v33;
      if ( v34 - v33 < 4 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          lpLibFileName,
          4);
      }
      else
      {
        v33 += 4LL;
        v22 = lpLibFileName;
        if ( v34 > 7 )
          v22 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v22 + 2 * v21) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v22 + v21 + 4) = 0;
      }
      v23 = (const WCHAR *)lpLibFileName;
      if ( v34 > 7 )
        v23 = lpLibFileName[0];
      v24 = LoadLibraryExW_0(v23, 0, 0x1000u);
      v25 = v33;
      v26 = v33 - 4;
      v27 = lpLibFileName;
      if ( v33 >= 4 )
      {
        v33 -= 4LL;
        if ( v34 > 7 )
          v27 = (LPCWSTR *)lpLibFileName[0];
LABEL_42:
        *((_WORD *)v27 + v26) = 0;
        continue;
      }
      if ( v34 - v33 >= 0xFFFFFFFFFFFFFFFCuLL )
      {
        v33 -= 4LL;
        if ( v34 > 7 )
          v27 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v27 + 2 * v25) = 0;
        goto LABEL_42;
      }
      std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpLibFileName);
    }
    while ( !v24 );
    v28 = WINRT_IMPL_GetProcAddress(v24, "DllGetActivationFactory");
    if ( !v28 )
      goto LABEL_50;
    v30 = 0;
    if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v28)(
            *a2,
            &v30)
      && !(**v30)(v30, a3, a4) )
    {
      break;
    }
    if ( v30 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v30);
LABEL_50:
    WINRT_IMPL_FreeLibrary(v24);
  }
  *a1 = 0;
  if ( v30 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v30);
LABEL_54:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x1800049a8  push    rbp
0x1800049aa  push    rbx
0x1800049ab  push    rsi
0x1800049ac  push    rdi
0x1800049ad  push    r12
0x1800049af  push    r13
0x1800049b1  push    r14
0x1800049b3  push    r15
0x1800049b5  mov     rbp, rsp
0x1800049b8  sub     rsp, 78h
0x1800049bc  mov     rax, cs:__security_cookie
0x1800049c3  xor     rax, rsp
0x1800049c6  mov     [rbp+var_18], rax
0x1800049ca  mov     r12, r9
0x1800049cd  mov     r15, r8
0x1800049d0  mov     r13, rdx
0x1800049d3  mov     rsi, rcx
0x1800049d6  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x1800049dd  xor     r14d, r14d
0x1800049e0  mov     r8, r9
0x1800049e3  mov     rdx, r15
0x1800049e6  mov     rcx, [r13+0]
0x1800049ea  test    rax, rax
0x1800049ed  jz      short loc_1800049FB
0x1800049ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f4  mov     [rsi], eax
0x1800049f6  jmp     loc_180004CCB
0x1800049fb  call    RoGetActivationFactory_0
0x180004a00  mov     ebx, eax
0x180004a02  cmp     eax, 800401F0h
0x180004a07  jnz     short loc_180004A5A
0x180004a09  xor     edx, edx; hFile
0x180004a0b  mov     r8d, 1000h; dwFlags
0x180004a11  lea     rcx, LibFileName; "combase.dll"
0x180004a18  call    LoadLibraryExW_0
0x180004a1d  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x180004a24  mov     rcx, rax; hModule
0x180004a27  call    WINRT_IMPL_GetProcAddress
0x180004a2c  test    rax, rax
0x180004a2f  jnz     short loc_180004A3C
0x180004a31  mov     dword ptr [rsi], 800401F0h
0x180004a37  jmp     loc_180004CCB
0x180004a3c  mov     [rbp+var_48], r14
0x180004a40  lea     rcx, [rbp+var_48]
0x180004a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a49  mov     r8, r12
0x180004a4c  mov     rdx, r15
0x180004a4f  mov     rcx, [r13+0]
0x180004a53  call    RoGetActivationFactory_0
0x180004a58  mov     ebx, eax
0x180004a5a  test    ebx, ebx
0x180004a5c  jnz     short loc_180004A66
0x180004a5e  mov     [rsi], r14d
0x180004a61  jmp     loc_180004CCB
0x180004a66  mov     [rbp+pperrinfo], r14
0x180004a6a  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180004a6e  xor     ecx, ecx; dwReserved
0x180004a70  call    GetErrorInfo_0
0x180004a75  mov     rdx, r13
0x180004a78  lea     rcx, [rbp+lpLibFileName]
0x180004a7c  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x180004a81  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180004a85  mov     rax, [rbp+var_28]
0x180004a89  lea     r14, [rbp+lpLibFileName]
0x180004a8d  cmp     [rbp+var_20], 7
0x180004a92  cmova   r14, [rbp+lpLibFileName]
0x180004a97  test    rax, rax
0x180004a9a  jz      loc_180004CA5
0x180004aa0  dec     rax
0x180004aa3  cmp     rax, rcx
0x180004aa6  cmovnb  rax, rcx
0x180004aaa  inc     rax
0x180004aad  lea     rdi, [r14+rax*2]
0x180004ab1  mov     r8d, 2Eh ; '.'
0x180004ab7  mov     rdx, rdi
0x180004aba  mov     rcx, r14
0x180004abd  call    __std_find_last_trivial_2
0x180004ac2  mov     rdx, rax
0x180004ac5  cmp     rax, rdi
0x180004ac8  jz      loc_180004CA5
0x180004ace  sub     rdx, r14
0x180004ad1  sar     rdx, 1
0x180004ad4  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180004ad8  jz      loc_180004CA5
0x180004ade  mov     rdi, [rbp+var_28]
0x180004ae2  cmp     rdx, rdi
0x180004ae5  ja      short loc_180004B01
0x180004ae7  mov     [rbp+var_28], rdx
0x180004aeb  lea     rcx, [rbp+lpLibFileName]
0x180004aef  cmp     [rbp+var_20], 7
0x180004af4  cmova   rcx, [rbp+lpLibFileName]
0x180004af9  xor     eax, eax
0x180004afb  mov     [rcx+rdx*2], ax
0x180004aff  jmp     short loc_180004B4E
0x180004b01  mov     rcx, rdx
0x180004b04  sub     rcx, rdi
0x180004b07  mov     rax, [rbp+var_20]
0x180004b0b  sub     rax, rdi
0x180004b0e  cmp     rcx, rax
0x180004b11  ja      short loc_180004B3F
0x180004b13  mov     [rbp+var_28], rdx
0x180004b17  lea     r8, [rbp+lpLibFileName]
0x180004b1b  cmp     [rbp+var_20], 7
0x180004b20  cmova   r8, [rbp+lpLibFileName]
0x180004b25  lea     rdi, [r8+rdi*2]
0x180004b29  test    rcx, rcx
0x180004b2c  jz      short loc_180004B36
0x180004b2e  xor     eax, eax
0x180004b30  movzx   eax, ax
0x180004b33  rep stosw
0x180004b36  xor     eax, eax
0x180004b38  mov     [r8+rdx*2], ax
0x180004b3d  jmp     short loc_180004B4E
0x180004b3f  mov     r9, rcx
0x180004b42  mov     rdx, rcx
0x180004b45  lea     rcx, [rbp+lpLibFileName]; Src
0x180004b49  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180004b4e  mov     rdi, [rbp+var_28]
0x180004b52  mov     rax, [rbp+var_20]
0x180004b56  sub     rax, rdi
0x180004b59  mov     ecx, 4
0x180004b5e  cmp     rax, rcx
0x180004b61  jb      short loc_180004B8F
0x180004b63  lea     rdx, [rdi+4]
0x180004b67  mov     [rbp+var_28], rdx
0x180004b6b  lea     rcx, [rbp+lpLibFileName]
0x180004b6f  cmp     [rbp+var_20], 7
0x180004b74  cmova   rcx, [rbp+lpLibFileName]
0x180004b79  mov     rax, 6C006C0064002Eh
0x180004b83  mov     [rcx+rdi*2], rax
0x180004b87  xor     eax, eax
0x180004b89  mov     [rcx+rdx*2], ax
0x180004b8d  jmp     short loc_180004BA0
0x180004b8f  mov     [rsp+78h+var_58], rcx; __int64
0x180004b94  mov     rdx, rcx
0x180004b97  lea     rcx, [rbp+lpLibFileName]; Src
0x180004b9b  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180004ba0  lea     rcx, [rbp+lpLibFileName]
0x180004ba4  cmp     [rbp+var_20], 7
0x180004ba9  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180004bae  xor     edx, edx; hFile
0x180004bb0  mov     r8d, 1000h; dwFlags
0x180004bb6  call    LoadLibraryExW_0
0x180004bbb  mov     rdi, rax
0x180004bbe  mov     rdx, [rbp+var_28]
0x180004bc2  lea     r8, [rdx-4]
0x180004bc6  lea     rcx, [rbp+lpLibFileName]; Src
0x180004bca  cmp     r8, rdx
0x180004bcd  ja      short loc_180004BE1
0x180004bcf  mov     [rbp+var_28], r8
0x180004bd3  cmp     [rbp+var_20], 7
0x180004bd8  cmova   rcx, [rbp+lpLibFileName]
0x180004bdd  xor     eax, eax
0x180004bdf  jmp     short loc_180004C08
0x180004be1  mov     rax, [rbp+var_20]
0x180004be5  sub     rax, rdx
0x180004be8  mov     r10, 0FFFFFFFFFFFFFFFCh
0x180004bef  cmp     rax, r10
0x180004bf2  jb      short loc_180004C0F
0x180004bf4  mov     [rbp+var_28], r8
0x180004bf8  cmp     [rbp+var_20], 7
0x180004bfd  cmova   rcx, [rbp+lpLibFileName]
0x180004c02  xor     eax, eax
0x180004c04  mov     [rcx+rdx*2], rax
0x180004c08  mov     [rcx+r8*2], ax
0x180004c0d  jmp     short loc_180004C1A
0x180004c0f  mov     r9, r10
0x180004c12  mov     rdx, r10
0x180004c15  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180004c1a  test    rdi, rdi
0x180004c1d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180004c24  jz      loc_180004A85
0x180004c2a  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x180004c31  mov     rcx, rdi; hModule
0x180004c34  call    WINRT_IMPL_GetProcAddress
0x180004c39  test    rax, rax
0x180004c3c  jz      short loc_180004C80
0x180004c3e  mov     [rbp+var_48], 0
0x180004c46  lea     rdx, [rbp+var_48]
0x180004c4a  mov     rcx, [r13+0]
0x180004c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c53  test    eax, eax
0x180004c55  jnz     short loc_180004C70
0x180004c57  mov     rcx, [rbp+var_48]
0x180004c5b  mov     rax, [rcx]
0x180004c5e  mov     r8, r12
0x180004c61  mov     rdx, r15
0x180004c64  mov     rax, [rax]
0x180004c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c6c  test    eax, eax
0x180004c6e  jz      short loc_180004C8D
0x180004c70  cmp     [rbp+var_48], 0
0x180004c75  jz      short loc_180004C80
0x180004c77  lea     rcx, [rbp+var_48]
0x180004c7b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004c80  mov     rcx, rdi; hLibModule
0x180004c83  call    WINRT_IMPL_FreeLibrary
0x180004c88  jmp     loc_180004A81
0x180004c8d  mov     dword ptr [rsi], 0
0x180004c93  cmp     [rbp+var_48], 0
0x180004c98  jz      short loc_180004CB2
0x180004c9a  lea     rcx, [rbp+var_48]
0x180004c9e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004ca3  jmp     short loc_180004CB2
0x180004ca5  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180004ca9  xor     ecx, ecx; dwReserved
0x180004cab  call    SetErrorInfo_0
0x180004cb0  mov     [rsi], ebx
0x180004cb2  lea     rcx, [rbp+lpLibFileName]
0x180004cb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004cbb  cmp     [rbp+pperrinfo], 0
0x180004cc0  jz      short loc_180004CCB
0x180004cc2  lea     rcx, [rbp+pperrinfo]
0x180004cc6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004ccb  mov     rax, rsi
0x180004cce  mov     rcx, [rbp+var_18]
0x180004cd2  xor     rcx, rsp; StackCookie
0x180004cd5  call    __security_check_cookie
0x180004cda  add     rsp, 78h
0x180004cde  pop     r15
0x180004ce0  pop     r14
0x180004ce2  pop     r13
0x180004ce4  pop     r12
0x180004ce6  pop     rdi
0x180004ce7  pop     rsi
0x180004ce8  pop     rbx
0x180004ce9  pop     rbp
0x180004cea  retn
```
