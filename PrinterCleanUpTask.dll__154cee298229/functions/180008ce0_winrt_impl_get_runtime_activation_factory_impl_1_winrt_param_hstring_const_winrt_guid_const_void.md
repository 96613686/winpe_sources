# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180008ce0`
- end: `0x180008f7c`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `668`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008c20`

## callees

- `0x180002020`
- `0x180002c2c`
- `0x180002c44`
- `0x180003350`
- `0x180003441`
- `0x180003465`
- `0x180003471`
- `0x18000347d`
- `0x18000750c`
- `0x180007668`
- `0x180008008`
- `0x1800084d8`
- `0x180008ce0`
- `0x18000f0d0`
- `0x18000ff2c`
- `0x180018010`

## string_xrefs

- `0x180008d44`: `combase.dll`
- `0x180008eb2`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // r8
  __int64 v15; // r14
  unsigned __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 last_trivial_2; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // rdx
  const WCHAR *v23; // rax
  HMODULE v24; // rbx
  FARPROC v25; // rax
  __int64 v26; // rax
  __int64 v28; // [rsp+30h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *Src[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v31; // [rsp+50h] [rbp-20h]
  unsigned __int64 v32; // [rsp+58h] [rbp-18h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
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
      v28 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v28);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      std::wstring::wstring(Src, a2);
      while ( 1 )
      {
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        v15 = v12;
        if ( !v13 )
          break;
        v16 = v13 - 1;
        if ( v13 - 1 >= v14 )
          v16 = v14;
        v17 = v12 + 2 + 2 * v16;
        last_trivial_2 = _std_find_last_trivial_2(v12, v17, 46);
        if ( last_trivial_2 == v17 )
          break;
        v19 = (last_trivial_2 - v15) >> 1;
        if ( v19 == -1 )
          break;
        std::wstring::resize(Src, v19);
        if ( v32 - v31 < 4 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
            Src,
            4);
        }
        else
        {
          v31 += 4;
          v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
          *(_QWORD *)(v20 + 2 * v21) = 0x6C006C0064002ELL;
          *(_WORD *)(v20 + 2 * v22) = 0;
        }
        v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        v24 = LoadLibraryExW_0(v23, 0, 0x1000u);
        std::wstring::resize(Src, v31 - 4);
        if ( v24 )
        {
          v25 = WINRT_IMPL_GetProcAddress(v24, "DllGetActivationFactory");
          if ( v25 )
          {
            v28 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v25)(*a2, &v28) )
            {
              v26 = v28;
              v28 = 0;
              *a4 = v26;
              *a1 = 0;
              goto LABEL_26;
            }
            if ( v28 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
          }
          WINRT_IMPL_FreeLibrary(v24);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_26:
      if ( v32 > 7 )
        std::_Deallocate<16>(Src[0], 2 * v32 + 2);
      LOWORD(Src[0]) = 0;
      v32 = 7;
      v31 = 0;
      if ( pperrinfo )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
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
0x180008ce0  push    rbp
0x180008ce2  push    rbx
0x180008ce3  push    rsi
0x180008ce4  push    rdi
0x180008ce5  push    r12
0x180008ce7  push    r14
0x180008ce9  push    r15
0x180008ceb  mov     rbp, rsp
0x180008cee  sub     rsp, 70h
0x180008cf2  mov     rax, cs:__security_cookie
0x180008cf9  xor     rax, rsp
0x180008cfc  mov     [rbp+var_10], rax
0x180008d00  mov     r15, r9
0x180008d03  mov     rbx, r8
0x180008d06  mov     r12, rdx
0x180008d09  mov     rsi, rcx
0x180008d0c  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180008d13  mov     r8, r9
0x180008d16  mov     rdx, rbx
0x180008d19  mov     rcx, [r12]
0x180008d1d  test    rax, rax
0x180008d20  jz      short loc_180008D2E
0x180008d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d27  mov     [rsi], eax
0x180008d29  jmp     loc_180008F5E
0x180008d2e  call    RoGetActivationFactory_0
0x180008d33  mov     edi, eax
0x180008d35  cmp     eax, 800401F0h
0x180008d3a  jnz     short loc_180008D91
0x180008d3c  xor     edx, edx; hFile
0x180008d3e  mov     r8d, 1000h; dwFlags
0x180008d44  lea     rcx, LibFileName; "combase.dll"
0x180008d4b  call    LoadLibraryExW_0
0x180008d50  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x180008d57  mov     rcx, rax; hModule
0x180008d5a  call    WINRT_IMPL_GetProcAddress
0x180008d5f  test    rax, rax
0x180008d62  jnz     short loc_180008D6F
0x180008d64  mov     dword ptr [rsi], 800401F0h
0x180008d6a  jmp     loc_180008F5E
0x180008d6f  mov     [rbp+var_40], 0
0x180008d77  lea     rcx, [rbp+var_40]
0x180008d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d80  mov     r8, r15
0x180008d83  mov     rdx, rbx
0x180008d86  mov     rcx, [r12]
0x180008d8a  call    RoGetActivationFactory_0
0x180008d8f  mov     edi, eax
0x180008d91  test    edi, edi
0x180008d93  jnz     short loc_180008D9C
0x180008d95  mov     [rsi], edi
0x180008d97  jmp     loc_180008F5E
0x180008d9c  mov     [rbp+pperrinfo], 0
0x180008da4  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180008da8  xor     ecx, ecx; dwReserved
0x180008daa  call    GetErrorInfo_0
0x180008daf  mov     rdx, r12
0x180008db2  lea     rcx, [rbp+Src]
0x180008db6  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x180008dbb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008dbf  mov     rdx, [rbp+var_20]
0x180008dc3  lea     rcx, [rbp+Src]
0x180008dc7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180008dcc  mov     r14, rax
0x180008dcf  test    rdx, rdx
0x180008dd2  jz      loc_180008F15
0x180008dd8  lea     rcx, [rdx-1]
0x180008ddc  cmp     rcx, r8
0x180008ddf  cmovnb  rcx, r8
0x180008de3  add     rax, 2
0x180008de7  lea     rbx, [rax+rcx*2]
0x180008deb  mov     r8d, 2Eh ; '.'
0x180008df1  mov     rdx, rbx
0x180008df4  mov     rcx, r14
0x180008df7  call    __std_find_last_trivial_2
0x180008dfc  cmp     rax, rbx
0x180008dff  jz      loc_180008F15
0x180008e05  sub     rax, r14
0x180008e08  sar     rax, 1
0x180008e0b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008e0f  jz      loc_180008F15
0x180008e15  mov     rdx, rax
0x180008e18  lea     rcx, [rbp+Src]
0x180008e1c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180008e21  mov     r8, [rbp+var_20]
0x180008e25  mov     rax, [rbp+var_18]
0x180008e29  sub     rax, r8
0x180008e2c  mov     ecx, 4
0x180008e31  cmp     rax, rcx
0x180008e34  jb      short loc_180008E5D
0x180008e36  lea     rdx, [r8+4]
0x180008e3a  mov     [rbp+var_20], rdx
0x180008e3e  lea     rcx, [rbp+Src]
0x180008e42  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180008e47  mov     rcx, 6C006C0064002Eh
0x180008e51  mov     [rax+r8*2], rcx
0x180008e55  xor     ecx, ecx
0x180008e57  mov     [rax+rdx*2], cx
0x180008e5b  jmp     short loc_180008E75
0x180008e5d  mov     [rsp+70h+var_50], rcx; __int64
0x180008e62  lea     r9, aDll; ".dll"
0x180008e69  mov     rdx, rcx
0x180008e6c  lea     rcx, [rbp+Src]; Src
0x180008e70  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180008e75  lea     rcx, [rbp+Src]
0x180008e79  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180008e7e  mov     rcx, rax; lpLibFileName
0x180008e81  xor     edx, edx; hFile
0x180008e83  mov     r8d, 1000h; dwFlags
0x180008e89  call    LoadLibraryExW_0
0x180008e8e  mov     rbx, rax
0x180008e91  mov     rdx, [rbp+var_20]
0x180008e95  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180008e99  lea     rcx, [rbp+Src]
0x180008e9d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180008ea2  test    rbx, rbx
0x180008ea5  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180008eac  jz      loc_180008DBF
0x180008eb2  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x180008eb9  mov     rcx, rbx; hModule
0x180008ebc  call    WINRT_IMPL_GetProcAddress
0x180008ec1  test    rax, rax
0x180008ec4  jnz     short loc_180008ED3
0x180008ec6  mov     rcx, rbx; hLibModule
0x180008ec9  call    WINRT_IMPL_FreeLibrary
0x180008ece  jmp     loc_180008DBB
0x180008ed3  mov     [rbp+var_40], 0
0x180008edb  lea     rdx, [rbp+var_40]
0x180008edf  mov     rcx, [r12]
0x180008ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ee8  test    eax, eax
0x180008eea  jz      short loc_180008EFE
0x180008eec  cmp     [rbp+var_40], 0
0x180008ef1  jz      short loc_180008EC6
0x180008ef3  lea     rcx, [rbp+var_40]
0x180008ef7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008efc  jmp     short loc_180008EC6
0x180008efe  mov     rax, [rbp+var_40]
0x180008f02  mov     [rbp+var_40], 0
0x180008f0a  mov     [r15], rax
0x180008f0d  mov     dword ptr [rsi], 0
0x180008f13  jmp     short loc_180008F22
0x180008f15  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180008f19  xor     ecx, ecx; dwReserved
0x180008f1b  call    SetErrorInfo_0
0x180008f20  mov     [rsi], edi
0x180008f22  mov     rdx, [rbp+var_18]
0x180008f26  cmp     rdx, 7
0x180008f2a  jbe     short loc_180008F3D
0x180008f2c  lea     rdx, ds:2[rdx*2]
0x180008f34  mov     rcx, [rbp+Src]
0x180008f38  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008f3d  xor     eax, eax
0x180008f3f  cmp     [rbp+pperrinfo], rax
0x180008f43  mov     word ptr [rbp+Src], ax
0x180008f47  mov     [rbp+var_18], 7
0x180008f4f  mov     [rbp+var_20], rax
0x180008f53  jz      short loc_180008F5E
0x180008f55  lea     rcx, [rbp+pperrinfo]
0x180008f59  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008f5e  mov     rax, rsi
0x180008f61  mov     rcx, [rbp+var_10]
0x180008f65  xor     rcx, rsp; StackCookie
0x180008f68  call    __security_check_cookie
0x180008f6d  add     rsp, 70h
0x180008f71  pop     r15
0x180008f73  pop     r14
0x180008f75  pop     r12
0x180008f77  pop     rdi
0x180008f78  pop     rsi
0x180008f79  pop     rbx
0x180008f7a  pop     rbp
0x180008f7b  retn
```
