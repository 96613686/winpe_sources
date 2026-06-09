# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18000e324`
- end: `0x18000e705`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `993`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000e204`

## callees

- `0x1800021c0`
- `0x1800021e4`
- `0x1800025f8`
- `0x180002d85`
- `0x180003a40`
- `0x180003da9`
- `0x180003dcd`
- `0x180003dd9`
- `0x180003e2d`
- `0x180003e39`
- `0x180003e45`
- `0x18000b5d0`
- `0x18000c3e4`
- `0x18000e324`
- `0x18000f098`
- `0x1800148f0`
- `0x180014950`
- `0x180014c14`
- `0x18002d010`

## string_xrefs

- `0x18000e395`: `combase.dll`
- `0x18000e64f`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v6; // r13
  __int64 v8; // rcx
  int ActivationFactory_0; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  void **v15; // r14
  char *v16; // rbx
  __int64 last_trivial_2; // rax
  __int64 v18; // r15
  unsigned __int64 v19; // r12
  __int64 v20; // rdx
  void **v21; // rcx
  _QWORD *v22; // rbx
  __int64 v23; // r13
  unsigned __int64 v24; // r14
  __int64 v25; // rcx
  size_t v26; // rcx
  void *v27; // rax
  size_t v28; // r15
  _BYTE *v29; // r14
  unsigned __int64 v30; // rdx
  _BYTE *v31; // rcx
  void **v32; // rcx
  HMODULE v33; // rbx
  FARPROC v34; // rax
  __int64 v35; // rax
  __int64 v37; // [rsp+20h] [rbp-58h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-50h] BYREF
  _QWORD *v39; // [rsp+30h] [rbp-48h]
  _QWORD *v40; // [rsp+38h] [rbp-40h]
  void *Src[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v42; // [rsp+50h] [rbp-28h]
  unsigned __int64 v43; // [rsp+58h] [rbp-20h]

  v40 = a4;
  v6 = a2;
  v39 = a2;
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
    v37 = 0;
    ((void (__fastcall *)(__int64 *))ProcAddress)(&v37);
    ActivationFactory_0 = RoGetActivationFactory_0(*v6, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  *(_OWORD *)Src = 0;
  v42 = 0;
  v43 = 0;
  v12 = *v6;
  if ( *v6 )
  {
    v13 = *(const wchar_t **)(v12 + 16);
    v14 = *(unsigned int *)(v12 + 4);
  }
  else
  {
    v13 = &szFile;
    v14 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>(Src, v13, v14);
  while ( 1 )
  {
    v15 = Src;
    if ( v43 > 7 )
      v15 = (void **)Src[0];
    if ( !v42 )
      break;
    v16 = (char *)v15 + 2 * v42;
    last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46);
    if ( (char *)last_trivial_2 == v16 || (last_trivial_2 - (__int64)v15) >> 1 == -1 )
      break;
    std::wstring::resize(Src);
    v18 = v42;
    v19 = v43;
    if ( v43 - v42 < 4 )
    {
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v42) < 4 )
        std::_Xlen_string();
      v23 = v42 + 4;
      v24 = (v42 + 4) | 7;
      if ( v24 <= 0x7FFFFFFFFFFFFFFELL && (v25 = v43 >> 1, v43 <= 0x7FFFFFFFFFFFFFFELL - (v43 >> 1)) )
      {
        if ( v24 < v25 + v43 )
          v24 = v25 + v43;
        if ( v24 + 1 > 0x7FFFFFFFFFFFFFFFLL )
LABEL_59:
          __scrt_throw_std_bad_array_new_length();
        v26 = 2 * (v24 + 1);
        if ( v26 )
          goto LABEL_26;
        v22 = 0;
      }
      else
      {
        v24 = 0x7FFFFFFFFFFFFFFELL;
        v26 = -2;
LABEL_26:
        if ( v26 < 0x1000 )
        {
          v22 = operator new(v26);
        }
        else
        {
          if ( v26 + 39 < v26 )
            goto LABEL_59;
          v27 = operator new(v26 + 39);
          if ( !v27 )
LABEL_52:
            __fastfail(5u);
          v22 = (_QWORD *)(((unsigned __int64)v27 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v22 - 1) = v27;
        }
      }
      v42 = v18 + 4;
      v43 = v24;
      v28 = 2 * v18;
      if ( v19 <= 7 )
      {
        memcpy_0(v22, Src, v28);
        *(_QWORD *)((char *)v22 + v28) = *(_QWORD *)L".dll";
        *((_WORD *)v22 + v23) = 0;
      }
      else
      {
        v29 = Src[0];
        memcpy_0(v22, Src[0], v28);
        *(_QWORD *)((char *)v22 + v28) = *(_QWORD *)L".dll";
        *((_WORD *)v22 + v23) = 0;
        v30 = 2 * v19 + 2;
        if ( v30 < 0x1000 )
        {
          v31 = v29;
        }
        else
        {
          v31 = (_BYTE *)*((_QWORD *)v29 - 1);
          if ( (unsigned __int64)(v29 - v31 - 8) > 0x1F )
            goto LABEL_52;
          v30 = 2 * v19 + 41;
        }
        operator delete(v31, v30);
      }
      v6 = v39;
      Src[0] = v22;
      goto LABEL_44;
    }
    v20 = v42 + 4;
    v42 += 4;
    v21 = Src;
    if ( v43 > 7 )
      v21 = (void **)Src[0];
    *(void **)((char *)v21 + 2 * v18) = *(void **)L".dll";
    *((_WORD *)v21 + v20) = 0;
    v22 = Src[0];
LABEL_44:
    v32 = Src;
    if ( v43 > 7 )
      v32 = (void **)v22;
    v33 = LoadLibraryExW_0((LPCWSTR)v32, 0, 0x1000u);
    std::wstring::resize(Src);
    if ( v33 )
    {
      v34 = WINRT_IMPL_GetProcAddress(v33, "DllGetActivationFactory");
      if ( v34 )
      {
        v37 = 0;
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v34)(*v6, &v37) )
        {
          v35 = v37;
          v37 = 0;
          *v40 = v35;
          *a1 = 0;
          goto LABEL_55;
        }
        if ( v37 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v37);
      }
      WINRT_IMPL_FreeLibrary(v33);
    }
  }
  SetErrorInfo_0(0, pperrinfo);
  *a1 = ActivationFactory_0;
LABEL_55:
  std::wstring::~wstring(Src);
  if ( pperrinfo )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000e324  push    rbp
0x18000e326  push    rbx
0x18000e327  push    rsi
0x18000e328  push    rdi
0x18000e329  push    r12
0x18000e32b  push    r13
0x18000e32d  push    r14
0x18000e32f  push    r15
0x18000e331  mov     rbp, rsp
0x18000e334  sub     rsp, 78h
0x18000e338  mov     rax, cs:__security_cookie
0x18000e33f  xor     rax, rsp
0x18000e342  mov     [rbp+var_18], rax
0x18000e346  mov     r14, r9
0x18000e349  mov     [rbp+var_40], r9
0x18000e34d  mov     rbx, r8
0x18000e350  mov     r13, rdx
0x18000e353  mov     [rbp+var_48], rdx
0x18000e357  mov     rsi, rcx
0x18000e35a  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18000e361  xor     r15d, r15d
0x18000e364  mov     r8, r9
0x18000e367  mov     rdx, rbx
0x18000e36a  mov     rcx, [r13+0]
0x18000e36e  test    rax, rax
0x18000e371  jz      short loc_18000E37F
0x18000e373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e378  mov     [rsi], eax
0x18000e37a  jmp     loc_18000E6D9
0x18000e37f  call    RoGetActivationFactory_0
0x18000e384  mov     edi, eax
0x18000e386  cmp     eax, 800401F0h
0x18000e38b  jnz     short loc_18000E3DA
0x18000e38d  xor     edx, edx; hFile
0x18000e38f  mov     r8d, 1000h; dwFlags
0x18000e395  lea     rcx, LibFileName; "combase.dll"
0x18000e39c  call    LoadLibraryExW_0
0x18000e3a1  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18000e3a8  mov     rcx, rax; hModule
0x18000e3ab  call    WINRT_IMPL_GetProcAddress
0x18000e3b0  test    rax, rax
0x18000e3b3  jnz     short loc_18000E3BC
0x18000e3b5  mov     [rsi], edi
0x18000e3b7  jmp     loc_18000E6D9
0x18000e3bc  mov     [rbp+var_58], r15
0x18000e3c0  lea     rcx, [rbp+var_58]
0x18000e3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3c9  mov     r8, r14
0x18000e3cc  mov     rdx, rbx
0x18000e3cf  mov     rcx, [r13+0]
0x18000e3d3  call    RoGetActivationFactory_0
0x18000e3d8  mov     edi, eax
0x18000e3da  test    edi, edi
0x18000e3dc  jnz     short loc_18000E3E6
0x18000e3de  mov     [rsi], r15d
0x18000e3e1  jmp     loc_18000E6D9
0x18000e3e6  mov     [rbp+pperrinfo], r15
0x18000e3ea  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000e3ee  xor     ecx, ecx; dwReserved
0x18000e3f0  call    GetErrorInfo_0
0x18000e3f5  xorps   xmm0, xmm0
0x18000e3f8  movups  xmmword ptr [rbp+Src], xmm0
0x18000e3fc  mov     [rbp+var_28], r15
0x18000e400  mov     [rbp+var_20], r15
0x18000e404  mov     rax, [r13+0]
0x18000e408  test    rax, rax
0x18000e40b  jz      short loc_18000E417
0x18000e40d  mov     rdx, [rax+10h]
0x18000e411  mov     r8d, [rax+4]
0x18000e415  jmp     short loc_18000E421
0x18000e417  lea     rdx, szFile
0x18000e41e  mov     r8, r15
0x18000e421  lea     rcx, [rbp+Src]
0x18000e425  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e42a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000e42e  mov     rax, [rbp+var_28]
0x18000e432  lea     r14, [rbp+Src]
0x18000e436  cmp     [rbp+var_20], 7
0x18000e43b  cmova   r14, [rbp+Src]
0x18000e440  test    rax, rax
0x18000e443  jz      loc_18000E6B4
0x18000e449  dec     rax
0x18000e44c  cmp     rax, r12
0x18000e44f  cmovnb  rax, r12
0x18000e453  inc     rax
0x18000e456  lea     rbx, [r14+rax*2]
0x18000e45a  mov     r8d, 2Eh ; '.'
0x18000e460  mov     rdx, rbx
0x18000e463  mov     rcx, r14
0x18000e466  call    __std_find_last_trivial_2
0x18000e46b  cmp     rax, rbx
0x18000e46e  jz      loc_18000E6B4
0x18000e474  sub     rax, r14
0x18000e477  sar     rax, 1
0x18000e47a  cmp     rax, r12
0x18000e47d  jz      loc_18000E6B4
0x18000e483  mov     rdx, rax
0x18000e486  lea     rcx, [rbp+Src]; Src
0x18000e48a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000e48f  mov     r15, [rbp+var_28]
0x18000e493  mov     r12, [rbp+var_20]
0x18000e497  mov     rax, r12
0x18000e49a  sub     rax, r15
0x18000e49d  cmp     rax, 4
0x18000e4a1  jb      short loc_18000E4D4
0x18000e4a3  lea     rdx, [r15+4]
0x18000e4a7  mov     [rbp+var_28], rdx
0x18000e4ab  lea     rcx, [rbp+Src]
0x18000e4af  cmp     r12, 7
0x18000e4b3  cmova   rcx, [rbp+Src]
0x18000e4b8  mov     rax, qword ptr cs:aDll; ".dll"
0x18000e4bf  mov     [rcx+r15*2], rax
0x18000e4c3  xor     r15d, r15d
0x18000e4c6  mov     [rcx+rdx*2], r15w
0x18000e4cb  mov     rbx, [rbp+Src]
0x18000e4cf  jmp     loc_18000E611
0x18000e4d4  mov     rdx, 7FFFFFFFFFFFFFFEh
0x18000e4de  mov     rax, rdx
0x18000e4e1  sub     rax, r15
0x18000e4e4  cmp     rax, 4
0x18000e4e8  jb      loc_18000E6F9
0x18000e4ee  lea     r13, [r15+4]
0x18000e4f2  mov     r14, r13
0x18000e4f5  or      r14, 7
0x18000e4f9  cmp     r14, rdx
0x18000e4fc  ja      short loc_18000E50F
0x18000e4fe  mov     rcx, r12
0x18000e501  shr     rcx, 1
0x18000e504  mov     rax, rdx
0x18000e507  sub     rax, rcx
0x18000e50a  cmp     r12, rax
0x18000e50d  jbe     short loc_18000E54E
0x18000e50f  mov     r14, rdx
0x18000e512  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x18000e519  cmp     rcx, 1000h
0x18000e520  jb      short loc_18000E579
0x18000e522  lea     rax, [rcx+27h]
0x18000e526  cmp     rax, rcx
0x18000e529  jbe     loc_18000E6FF
0x18000e52f  mov     rcx, rax; Size
0x18000e532  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e537  test    rax, rax
0x18000e53a  jz      loc_18000E699
0x18000e540  lea     rbx, [rax+27h]
0x18000e544  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18000e548  mov     [rbx-8], rax
0x18000e54c  jmp     short loc_18000E581
0x18000e54e  lea     rax, [rcx+r12]
0x18000e552  cmp     r14, rax
0x18000e555  cmovb   r14, rax
0x18000e559  lea     rcx, [r14+1]
0x18000e55d  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000e567  cmp     rcx, rax
0x18000e56a  ja      loc_18000E6FF
0x18000e570  add     rcx, rcx
0x18000e573  jnz     short loc_18000E519
0x18000e575  xor     ebx, ebx
0x18000e577  jmp     short loc_18000E581
0x18000e579  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e57e  mov     rbx, rax
0x18000e581  mov     [rbp+var_28], r13
0x18000e585  mov     [rbp+var_20], r14
0x18000e589  add     r15, r15
0x18000e58c  mov     r8, r15; Size
0x18000e58f  mov     rcx, rbx; void *
0x18000e592  cmp     r12, 7
0x18000e596  jbe     short loc_18000E5ED
0x18000e598  mov     r14, [rbp+Src]
0x18000e59c  mov     rdx, r14; Src
0x18000e59f  call    memcpy_0
0x18000e5a4  mov     rax, qword ptr cs:aDll; ".dll"
0x18000e5ab  mov     [r15+rbx], rax
0x18000e5af  xor     r15d, r15d
0x18000e5b2  mov     [rbx+r13*2], r15w
0x18000e5b7  lea     rdx, ds:2[r12*2]; unsigned __int64
0x18000e5bf  cmp     rdx, 1000h
0x18000e5c6  jb      short loc_18000E5E3
0x18000e5c8  mov     rcx, [r14-8]
0x18000e5cc  sub     r14, rcx
0x18000e5cf  sub     r14, 8
0x18000e5d3  cmp     r14, 1Fh
0x18000e5d7  ja      loc_18000E699
0x18000e5dd  add     rdx, 27h ; '''
0x18000e5e1  jmp     short loc_18000E5E6
0x18000e5e3  mov     rcx, r14; void *
0x18000e5e6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e5eb  jmp     short loc_18000E609
0x18000e5ed  lea     rdx, [rbp+Src]; Src
0x18000e5f1  call    memcpy_0
0x18000e5f6  mov     rax, qword ptr cs:aDll; ".dll"
0x18000e5fd  mov     [r15+rbx], rax
0x18000e601  xor     r15d, r15d
0x18000e604  mov     [rbx+r13*2], r15w
0x18000e609  mov     r13, [rbp+var_48]
0x18000e60d  mov     [rbp+Src], rbx
0x18000e611  lea     rcx, [rbp+Src]
0x18000e615  cmp     [rbp+var_20], 7
0x18000e61a  cmova   rcx, rbx; lpLibFileName
0x18000e61e  xor     edx, edx; hFile
0x18000e620  mov     r8d, 1000h; dwFlags
0x18000e626  call    LoadLibraryExW_0
0x18000e62b  mov     rbx, rax
0x18000e62e  mov     rdx, [rbp+var_28]
0x18000e632  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18000e636  lea     rcx, [rbp+Src]; Src
0x18000e63a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000e63f  test    rbx, rbx
0x18000e642  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000e649  jz      loc_18000E42E
0x18000e64f  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18000e656  mov     rcx, rbx; hModule
0x18000e659  call    WINRT_IMPL_GetProcAddress
0x18000e65e  test    rax, rax
0x18000e661  jnz     short loc_18000E673
0x18000e663  mov     rcx, rbx; hLibModule
0x18000e666  call    WINRT_IMPL_FreeLibrary
0x18000e66b  or      r12, r12
0x18000e66e  jmp     loc_18000E42E
0x18000e673  mov     [rbp+var_58], r15
0x18000e677  lea     rdx, [rbp+var_58]
0x18000e67b  mov     rcx, [r13+0]
0x18000e67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e684  test    eax, eax
0x18000e686  jz      short loc_18000E6A0
0x18000e688  cmp     [rbp+var_58], r15
0x18000e68c  jz      short loc_18000E663
0x18000e68e  lea     rcx, [rbp+var_58]
0x18000e692  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000e697  jmp     short loc_18000E663
0x18000e699  mov     ecx, 5
0x18000e69e  int     29h; Win8: RtlFailFast(ecx)
0x18000e6a0  mov     rax, [rbp+var_58]
0x18000e6a4  mov     [rbp+var_58], r15
0x18000e6a8  mov     rcx, [rbp+var_40]
0x18000e6ac  mov     [rcx], rax
0x18000e6af  mov     [rsi], r15d
0x18000e6b2  jmp     short loc_18000E6C1
0x18000e6b4  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000e6b8  xor     ecx, ecx; dwReserved
0x18000e6ba  call    SetErrorInfo_0
0x18000e6bf  mov     [rsi], edi
0x18000e6c1  lea     rcx, [rbp+Src]
0x18000e6c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e6ca  cmp     [rbp+pperrinfo], r15
0x18000e6ce  jz      short loc_18000E6D9
0x18000e6d0  lea     rcx, [rbp+pperrinfo]
0x18000e6d4  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000e6d9  mov     rax, rsi
0x18000e6dc  mov     rcx, [rbp+var_18]
0x18000e6e0  xor     rcx, rsp; StackCookie
0x18000e6e3  call    __security_check_cookie
0x18000e6e8  add     rsp, 78h
0x18000e6ec  pop     r15
0x18000e6ee  pop     r14
0x18000e6f0  pop     r13
0x18000e6f2  pop     r12
0x18000e6f4  pop     rdi
0x18000e6f5  pop     rsi
0x18000e6f6  pop     rbx
0x18000e6f7  pop     rbp
0x18000e6f8  retn
0x18000e6f9  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000e6ff  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
