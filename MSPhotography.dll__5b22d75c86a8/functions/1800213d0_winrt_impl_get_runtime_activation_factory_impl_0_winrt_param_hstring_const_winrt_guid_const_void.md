# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x1800213d0`
- end: `0x180021624`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `596`
- prototype: ``
- caller_count: `6`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020f4c`
- `0x180020fac`
- `0x18002100c`
- `0x18002106c`
- `0x1800210cc`
- `0x18002112c`

## callees

- `0x180002420`
- `0x180003303`
- `0x180003327`
- `0x180003333`
- `0x180003a6a`
- `0x180003a82`
- `0x180003aa6`
- `0x18001d764`
- `0x18001e658`
- `0x18001f264`
- `0x18001fb50`
- `0x1800213d0`
- `0x180027c2c`
- `0x1800284bc`
- `0x180028530`
- `0x180142010`

## string_xrefs

- `0x180021439`: `combase.dll`
- `0x180021538`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  HMODULE v16; // rdi
  FARPROC v17; // rax
  __int64 v18; // rax
  unsigned int (__fastcall ***v20)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v23; // [rsp+50h] [rbp-28h]
  unsigned __int64 v24; // [rsp+58h] [rbp-20h]

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
    v20 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v20);
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
      v18 = std::wstring::rfind(lpLibFileName);
      if ( v18 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_24;
      }
      std::wstring::resize(lpLibFileName, v18);
      if ( v24 - v23 < 4 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          lpLibFileName,
          4);
      }
      else
      {
        v23 += 4;
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(lpLibFileName);
        *(_QWORD *)(v12 + 2 * v13) = 0x6C006C0064002ELL;
        *(_WORD *)(v12 + 2 * v14) = 0;
      }
      v15 = (const WCHAR *)lpLibFileName;
      if ( v24 > 7 )
        v15 = lpLibFileName[0];
      v16 = LoadLibraryExW_0(v15, 0, 0x1000u);
      std::wstring::resize(lpLibFileName, v23 - 4);
    }
    while ( !v16 );
    v17 = WINRT_IMPL_GetProcAddress(v16, "DllGetActivationFactory");
    if ( v17 )
      break;
LABEL_21:
    WINRT_IMPL_FreeLibrary(v16);
  }
  v20 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v17)(*a2, &v20)
    || (**v20)(v20, a3, a4) )
  {
    if ( v20 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
    goto LABEL_21;
  }
  *a1 = 0;
  if ( v20 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
LABEL_24:
  if ( v24 > 7 )
    std::_Deallocate<16>(lpLibFileName[0], 2 * v24 + 2);
  LOWORD(lpLibFileName[0]) = 0;
  v24 = 7;
  v23 = 0;
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x1800213d0  push    rbp
0x1800213d2  push    rbx
0x1800213d3  push    rsi
0x1800213d4  push    rdi
0x1800213d5  push    r12
0x1800213d7  push    r13
0x1800213d9  push    r14
0x1800213db  push    r15
0x1800213dd  mov     rbp, rsp
0x1800213e0  sub     rsp, 78h
0x1800213e4  mov     rax, cs:__security_cookie
0x1800213eb  xor     rax, rsp
0x1800213ee  mov     [rbp+var_18], rax
0x1800213f2  mov     r15, r9
0x1800213f5  mov     r14, r8
0x1800213f8  mov     r12, rdx
0x1800213fb  mov     rsi, rcx
0x1800213fe  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180021405  xor     r13d, r13d
0x180021408  mov     r8, r9
0x18002140b  mov     rdx, r14
0x18002140e  mov     rcx, [r12]
0x180021412  test    rax, rax
0x180021415  jz      short loc_180021423
0x180021417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002141c  mov     [rsi], eax
0x18002141e  jmp     loc_1800215F0
0x180021423  call    RoGetActivationFactory_0
0x180021428  mov     ebx, eax
0x18002142a  cmp     eax, 800401F0h
0x18002142f  jnz     short loc_180021482
0x180021431  xor     edx, edx; hFile
0x180021433  mov     r8d, 1000h; dwFlags
0x180021439  lea     rcx, LibFileName; "combase.dll"
0x180021440  call    LoadLibraryExW_0
0x180021445  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18002144c  mov     rcx, rax; hModule
0x18002144f  call    WINRT_IMPL_GetProcAddress
0x180021454  test    rax, rax
0x180021457  jnz     short loc_180021464
0x180021459  mov     dword ptr [rsi], 800401F0h
0x18002145f  jmp     loc_1800215F0
0x180021464  mov     [rbp+var_48], r13
0x180021468  lea     rcx, [rbp+var_48]
0x18002146c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021471  mov     r8, r15
0x180021474  mov     rdx, r14
0x180021477  mov     rcx, [r12]
0x18002147b  call    RoGetActivationFactory_0
0x180021480  mov     ebx, eax
0x180021482  test    ebx, ebx
0x180021484  jnz     short loc_18002148E
0x180021486  mov     [rsi], r13d
0x180021489  jmp     loc_1800215F0
0x18002148e  mov     [rbp+pperrinfo], r13
0x180021492  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180021496  xor     ecx, ecx; dwReserved
0x180021498  call    GetErrorInfo_0
0x18002149d  mov     rdx, r12
0x1800214a0  lea     rcx, [rbp+lpLibFileName]
0x1800214a4  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x1800214a9  jmp     loc_180021595
0x1800214ae  mov     rdx, rax
0x1800214b1  lea     rcx, [rbp+lpLibFileName]
0x1800214b5  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800214ba  mov     r8, [rbp+var_28]
0x1800214be  mov     rax, [rbp+var_20]
0x1800214c2  sub     rax, r8
0x1800214c5  lea     rcx, [rbp+lpLibFileName]; Src
0x1800214c9  cmp     rax, 4
0x1800214cd  jb      short loc_1800214F1
0x1800214cf  lea     rdx, [r8+4]
0x1800214d3  mov     [rbp+var_28], rdx
0x1800214d7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEAAPEAGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800214dc  mov     rcx, 6C006C0064002Eh
0x1800214e6  mov     [rax+r8*2], rcx
0x1800214ea  mov     [rax+rdx*2], r13w
0x1800214ef  jmp     short loc_180021504
0x1800214f1  mov     [rsp+78h+var_58], 4; __int64
0x1800214fa  mov     edx, 4
0x1800214ff  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180021504  lea     rcx, [rbp+lpLibFileName]
0x180021508  cmp     [rbp+var_20], 7
0x18002150d  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180021512  xor     edx, edx; hFile
0x180021514  mov     r8d, 1000h; dwFlags
0x18002151a  call    LoadLibraryExW_0
0x18002151f  mov     rdi, rax
0x180021522  mov     rdx, [rbp+var_28]
0x180021526  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18002152a  lea     rcx, [rbp+lpLibFileName]
0x18002152e  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180021533  test    rdi, rdi
0x180021536  jz      short loc_180021595
0x180021538  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x18002153f  mov     rcx, rdi; hModule
0x180021542  call    WINRT_IMPL_GetProcAddress
0x180021547  test    rax, rax
0x18002154a  jz      short loc_18002158D
0x18002154c  mov     [rbp+var_48], r13
0x180021550  lea     rdx, [rbp+var_48]
0x180021554  mov     rcx, [r12]
0x180021558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002155d  test    eax, eax
0x18002155f  jnz     short loc_18002157E
0x180021561  mov     rcx, [rbp+var_48]
0x180021565  mov     rax, [rcx]
0x180021568  mov     r8, r15
0x18002156b  mov     rdx, r14
0x18002156e  mov     rax, [rax]
0x180021571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021576  test    eax, eax
0x180021578  jz      loc_180021610
0x18002157e  cmp     [rbp+var_48], r13
0x180021582  jz      short loc_18002158D
0x180021584  lea     rcx, [rbp+var_48]
0x180021588  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002158d  mov     rcx, rdi; hLibModule
0x180021590  call    WINRT_IMPL_FreeLibrary
0x180021595  lea     rcx, [rbp+lpLibFileName]
0x180021599  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x18002159e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800215a2  jnz     loc_1800214AE
0x1800215a8  mov     rdx, [rbp+pperrinfo]; perrinfo
0x1800215ac  xor     ecx, ecx; dwReserved
0x1800215ae  call    SetErrorInfo_0
0x1800215b3  mov     [rsi], ebx
0x1800215b5  mov     rdx, [rbp+var_20]
0x1800215b9  cmp     rdx, 7
0x1800215bd  jbe     short loc_1800215D0
0x1800215bf  lea     rdx, ds:2[rdx*2]
0x1800215c7  mov     rcx, [rbp+lpLibFileName]
0x1800215cb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800215d0  cmp     [rbp+pperrinfo], r13
0x1800215d4  mov     word ptr [rbp+lpLibFileName], r13w
0x1800215d9  mov     [rbp+var_20], 7
0x1800215e1  mov     [rbp+var_28], r13
0x1800215e5  jz      short loc_1800215F0
0x1800215e7  lea     rcx, [rbp+pperrinfo]
0x1800215eb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800215f0  mov     rax, rsi
0x1800215f3  mov     rcx, [rbp+var_18]
0x1800215f7  xor     rcx, rsp; StackCookie
0x1800215fa  call    __security_check_cookie
0x1800215ff  add     rsp, 78h
0x180021603  pop     r15
0x180021605  pop     r14
0x180021607  pop     r13
0x180021609  pop     r12
0x18002160b  pop     rdi
0x18002160c  pop     rsi
0x18002160d  pop     rbx
0x18002160e  pop     rbp
0x18002160f  retn
0x180021610  mov     [rsi], r13d
0x180021613  cmp     [rbp+var_48], r13
0x180021617  jz      short loc_1800215B5
0x180021619  lea     rcx, [rbp+var_48]
0x18002161d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021622  jmp     short loc_1800215B5
```
