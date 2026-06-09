# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180014d2c`
- end: `0x180015037`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `779`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001296c`

## callees

- `0x180003560`
- `0x18000411f`
- `0x180004290`
- `0x180004365`
- `0x180004371`
- `0x18000437d`
- `0x180004395`
- `0x1800043a1`
- `0x180011ec8`
- `0x18001213c`
- `0x1800125d0`
- `0x180014d2c`
- `0x180022b44`
- `0x180025200`
- `0x1800260f8`
- `0x180031010`

## string_xrefs

- `0x180014d91`: `combase.dll`
- `0x180014f31`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // r8
  __int64 v18; // r14
  unsigned __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 last_trivial_2; // rax
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // rdx
  __int128 *p_Src; // rcx
  const WCHAR *v26; // rax
  HMODULE v27; // rbx
  FARPROC v28; // rax
  bool v29; // zf
  unsigned int (__fastcall ***v31)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  __int128 Src; // [rsp+40h] [rbp-38h] BYREF
  __int64 v34; // [rsp+50h] [rbp-28h]
  unsigned __int64 v35; // [rsp+58h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
  }
  else
  {
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
      v31 = 0;
      ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v31);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      Src = 0;
      v34 = 0;
      v35 = 0;
      v12 = *a2;
      if ( *a2 )
      {
        v13 = *(__int64 **)(v12 + 16);
        v14 = *(unsigned int *)(v12 + 4);
      }
      else
      {
        v13 = &qword_180033FA8;
        v14 = 0;
      }
      std::wstring::_Construct<1,wchar_t const *>(&Src, v13, v14);
      while ( 1 )
      {
        v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&Src);
        v18 = v15;
        if ( !v16 )
          break;
        v19 = v16 - 1;
        if ( v16 - 1 >= v17 )
          v19 = v17;
        v20 = v15 + 2 + 2 * v19;
        last_trivial_2 = _std_find_last_trivial_2(v15, v20, 46);
        if ( last_trivial_2 == v20 )
          break;
        v22 = (last_trivial_2 - v18) >> 1;
        if ( v22 == -1 )
          break;
        std::wstring::resize(&Src, v22);
        v23 = v34;
        if ( v35 - v34 < 4 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64>(
            &Src,
            4);
        }
        else
        {
          v24 = v34 + 4;
          v34 += 4;
          p_Src = &Src;
          if ( v35 > 7 )
            p_Src = (__int128 *)Src;
          *(_QWORD *)((char *)p_Src + 2 * v23) = 0x6C006C0064002ELL;
          *((_WORD *)p_Src + v24) = 0;
        }
        v26 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&Src);
        v27 = LoadLibraryExW_0(v26, 0, 0x1000u);
        std::wstring::resize(&Src, v34 - 4);
        if ( v27 )
        {
          v28 = WINRT_IMPL_GetProcAddress(v27, "DllGetActivationFactory");
          if ( v28 )
          {
            v31 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v28)(
                    *a2,
                    &v31)
              && !(**v31)(v31, a3, a4) )
            {
              *a1 = 0;
              if ( v31 )
                winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v31);
              if ( v35 > 7 )
                std::_Deallocate<16>((_QWORD *)Src, 2 * v35 + 2);
              v34 = 0;
              LOWORD(Src) = 0;
              v29 = pperrinfo == 0;
              goto LABEL_38;
            }
            if ( v31 )
              winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v31);
          }
          WINRT_IMPL_FreeLibrary(v27);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
      if ( v35 > 7 )
        std::_Deallocate<16>((_QWORD *)Src, 2 * v35 + 2);
      v34 = 0;
      LOWORD(Src) = 0;
      v29 = pperrinfo == 0;
LABEL_38:
      v35 = 7;
      if ( !v29 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180014d2c  push    rbp
0x180014d2e  push    rbx
0x180014d2f  push    rsi
0x180014d30  push    rdi
0x180014d31  push    r12
0x180014d33  push    r13
0x180014d35  push    r14
0x180014d37  push    r15
0x180014d39  mov     rbp, rsp
0x180014d3c  sub     rsp, 78h
0x180014d40  mov     rax, cs:__security_cookie
0x180014d47  xor     rax, rsp
0x180014d4a  mov     [rbp+var_18], rax
0x180014d4e  mov     r13, r9
0x180014d51  mov     r12, r8
0x180014d54  mov     r15, rdx
0x180014d57  mov     rsi, rcx
0x180014d5a  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180014d61  mov     r8, r9
0x180014d64  mov     rdx, r12
0x180014d67  mov     rcx, [r15]
0x180014d6a  test    rax, rax
0x180014d6d  jz      short loc_180014D7B
0x180014d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d74  mov     [rsi], eax
0x180014d76  jmp     loc_180015017
0x180014d7b  call    RoGetActivationFactory_0
0x180014d80  mov     edi, eax
0x180014d82  cmp     eax, 800401F0h
0x180014d87  jnz     short loc_180014DDD
0x180014d89  xor     edx, edx; hFile
0x180014d8b  mov     r8d, 1000h; dwFlags
0x180014d91  lea     rcx, LibFileName; "combase.dll"
0x180014d98  call    LoadLibraryExW_0
0x180014d9d  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x180014da4  mov     rcx, rax; hModule
0x180014da7  call    WINRT_IMPL_GetProcAddress
0x180014dac  test    rax, rax
0x180014daf  jnz     short loc_180014DBC
0x180014db1  mov     dword ptr [rsi], 800401F0h
0x180014db7  jmp     loc_180015017
0x180014dbc  mov     [rbp+var_48], 0
0x180014dc4  lea     rcx, [rbp+var_48]
0x180014dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dcd  mov     r8, r13
0x180014dd0  mov     rdx, r12
0x180014dd3  mov     rcx, [r15]
0x180014dd6  call    RoGetActivationFactory_0
0x180014ddb  mov     edi, eax
0x180014ddd  test    edi, edi
0x180014ddf  jnz     short loc_180014DE8
0x180014de1  mov     [rsi], edi
0x180014de3  jmp     loc_180015017
0x180014de8  mov     [rbp+pperrinfo], 0
0x180014df0  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180014df4  xor     ecx, ecx; dwReserved
0x180014df6  call    GetErrorInfo_0
0x180014dfb  xorps   xmm0, xmm0
0x180014dfe  movups  [rbp+Src], xmm0
0x180014e02  mov     [rbp+var_28], 0
0x180014e0a  mov     [rbp+var_20], 0
0x180014e12  mov     rax, [r15]
0x180014e15  test    rax, rax
0x180014e18  jz      short loc_180014E24
0x180014e1a  mov     rdx, [rax+10h]
0x180014e1e  mov     r8d, [rax+4]
0x180014e22  jmp     short loc_180014E2E
0x180014e24  lea     rdx, qword_180033FA8
0x180014e2b  xor     r8d, r8d
0x180014e2e  lea     rcx, [rbp+Src]
0x180014e32  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180014e37  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014e3b  mov     rdx, [rbp+var_28]
0x180014e3f  lea     rcx, [rbp+Src]
0x180014e43  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180014e48  mov     r14, rax
0x180014e4b  test    rdx, rdx
0x180014e4e  jz      loc_180014FCA
0x180014e54  lea     rcx, [rdx-1]
0x180014e58  cmp     rcx, r8
0x180014e5b  cmovnb  rcx, r8
0x180014e5f  add     rax, 2
0x180014e63  lea     rbx, [rax+rcx*2]
0x180014e67  mov     r8d, 2Eh ; '.'
0x180014e6d  mov     rdx, rbx
0x180014e70  mov     rcx, r14
0x180014e73  call    __std_find_last_trivial_2
0x180014e78  cmp     rax, rbx
0x180014e7b  jz      loc_180014FCA
0x180014e81  sub     rax, r14
0x180014e84  sar     rax, 1
0x180014e87  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014e8b  jz      loc_180014FCA
0x180014e91  mov     rdx, rax
0x180014e94  lea     rcx, [rbp+Src]
0x180014e98  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180014e9d  mov     r8, [rbp+var_28]
0x180014ea1  mov     rax, [rbp+var_20]
0x180014ea5  sub     rax, r8
0x180014ea8  mov     ecx, 4
0x180014ead  cmp     rax, rcx
0x180014eb0  jb      short loc_180014EE0
0x180014eb2  lea     rdx, [r8+4]
0x180014eb6  mov     [rbp+var_28], rdx
0x180014eba  lea     rcx, [rbp+Src]
0x180014ebe  cmp     [rbp+var_20], 7
0x180014ec3  cmova   rcx, qword ptr [rbp+Src]
0x180014ec8  mov     rax, 6C006C0064002Eh
0x180014ed2  mov     [rcx+r8*2], rax
0x180014ed6  xor     r14d, r14d
0x180014ed9  mov     [rcx+rdx*2], r14w
0x180014ede  jmp     short loc_180014EF4
0x180014ee0  mov     [rsp+78h+var_58], rcx; __int64
0x180014ee5  mov     rdx, rcx
0x180014ee8  lea     rcx, [rbp+Src]; Src
0x180014eec  call    ??$_Reallocate_grow_by@V_lambda_942448a5eca1a40cdf35e7a483deabf2_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_942448a5eca1a40cdf35e7a483deabf2_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_942448a5eca1a40cdf35e7a483deabf2_,wchar_t const *,unsigned __int64)
0x180014ef1  xor     r14d, r14d
0x180014ef4  lea     rcx, [rbp+Src]
0x180014ef8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180014efd  mov     rcx, rax; lpLibFileName
0x180014f00  xor     edx, edx; hFile
0x180014f02  mov     r8d, 1000h; dwFlags
0x180014f08  call    LoadLibraryExW_0
0x180014f0d  mov     rbx, rax
0x180014f10  mov     rdx, [rbp+var_28]
0x180014f14  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180014f18  lea     rcx, [rbp+Src]
0x180014f1c  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180014f21  test    rbx, rbx
0x180014f24  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180014f2b  jz      loc_180014E3B
0x180014f31  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x180014f38  mov     rcx, rbx; hModule
0x180014f3b  call    WINRT_IMPL_GetProcAddress
0x180014f40  test    rax, rax
0x180014f43  jz      short loc_180014F81
0x180014f45  mov     [rbp+var_48], r14
0x180014f49  lea     rdx, [rbp+var_48]
0x180014f4d  mov     rcx, [r15]
0x180014f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f55  test    eax, eax
0x180014f57  jnz     short loc_180014F72
0x180014f59  mov     rcx, [rbp+var_48]
0x180014f5d  mov     rax, [rcx]
0x180014f60  mov     r8, r13
0x180014f63  mov     rdx, r12
0x180014f66  mov     rax, [rax]
0x180014f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f6e  test    eax, eax
0x180014f70  jz      short loc_180014F8E
0x180014f72  cmp     [rbp+var_48], r14
0x180014f76  jz      short loc_180014F81
0x180014f78  lea     rcx, [rbp+var_48]
0x180014f7c  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180014f81  mov     rcx, rbx; hLibModule
0x180014f84  call    WINRT_IMPL_FreeLibrary
0x180014f89  jmp     loc_180014E37
0x180014f8e  mov     [rsi], r14d
0x180014f91  cmp     [rbp+var_48], r14
0x180014f95  jz      short loc_180014FA0
0x180014f97  lea     rcx, [rbp+var_48]
0x180014f9b  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180014fa0  mov     rdx, [rbp+var_20]
0x180014fa4  cmp     rdx, 7
0x180014fa8  jbe     short loc_180014FBB
0x180014faa  lea     rdx, ds:2[rdx*2]
0x180014fb2  mov     rcx, qword ptr [rbp+Src]
0x180014fb6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014fbb  mov     [rbp+var_28], r14
0x180014fbf  mov     word ptr [rbp+Src], r14w
0x180014fc4  cmp     [rbp+pperrinfo], r14
0x180014fc8  jmp     short loc_180015004
0x180014fca  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180014fce  xor     ecx, ecx; dwReserved
0x180014fd0  call    SetErrorInfo_0
0x180014fd5  mov     [rsi], edi
0x180014fd7  mov     rdx, [rbp+var_20]
0x180014fdb  cmp     rdx, 7
0x180014fdf  jbe     short loc_180014FF2
0x180014fe1  lea     rdx, ds:2[rdx*2]
0x180014fe9  mov     rcx, qword ptr [rbp+Src]
0x180014fed  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014ff2  mov     [rbp+var_28], 0
0x180014ffa  xor     eax, eax
0x180014ffc  mov     word ptr [rbp+Src], ax
0x180015000  cmp     [rbp+pperrinfo], rax
0x180015004  mov     [rbp+var_20], 7
0x18001500c  jz      short loc_180015017
0x18001500e  lea     rcx, [rbp+pperrinfo]
0x180015012  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180015017  mov     rax, rsi
0x18001501a  mov     rcx, [rbp+var_18]
0x18001501e  xor     rcx, rsp; StackCookie
0x180015021  call    __security_check_cookie
0x180015026  add     rsp, 78h
0x18001502a  pop     r15
0x18001502c  pop     r14
0x18001502e  pop     r13
0x180015030  pop     r12
0x180015032  pop     rdi
0x180015033  pop     rsi
0x180015034  pop     rbx
0x180015035  pop     rbp
0x180015036  retn
```
