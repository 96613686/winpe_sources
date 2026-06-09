# PolicyProvider::GetValueAllocFromLocUri(ushort const *,ushort,ushort * *)

- ea: `0x180055c4c`
- end: `0x180055e91`
- name: `?GetValueAllocFromLocUri@PolicyProvider@@CAJPEBGGPEAPEAG@Z`
- size: `581`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800497d0`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001ec78`
- `0x180047c28`
- `0x1800539bc`
- `0x1800541fc`
- `0x180055c4c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055c99`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055c99`
- `OLEAUT32!__imp_VariantInit` at `0x180055d63`
- `OLEAUT32!__imp_VariantInit` at `0x180055d63`
- `OLEAUT32!__imp_VariantClear` at `0x180055d88`
- `OLEAUT32!__imp_VariantClear` at `0x180055e5a`
- `OLEAUT32!__imp_VariantClear` at `0x180055d88`
- `OLEAUT32!__imp_VariantClear` at `0x180055e5a`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180055db2`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180055db2`

## string_xrefs

- `0x180055cac`: `onecore\base\flighting\flightsettings\broker\libs\ctac\policyprovider.cpp`
- `0x180055d00`: `onecore\base\flighting\flightsettings\broker\libs\ctac\policyprovider.cpp`
- `0x180055dc5`: `onecore\base\flighting\flightsettings\broker\libs\ctac\policyprovider.cpp`
- `0x180055e0e`: `onecore\base\flighting\flightsettings\broker\libs\ctac\policyprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PolicyProvider::GetValueAllocFromLocUri(
        const unsigned __int16 *a1,
        USHORT a2,
        unsigned __int16 **a3)
{
  HRESULT v6; // eax
  int v7; // ebx
  __int64 bstr_nothrow; // rax
  __int64 v9; // rbx
  LPVOID v10; // rsi
  __int64 (__fastcall *v11)(LPVOID, __int64, __int64 *); // rdi
  HRESULT v12; // eax
  int v13; // eax
  unsigned __int16 *v14; // rax
  int ppv; // [rsp+20h] [rbp-39h]
  __int64 v17; // [rsp+30h] [rbp-29h] BYREF
  LPVOID v18; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v19[8]; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 *v20; // [rsp+48h] [rbp-11h] BYREF
  __int64 v21; // [rsp+50h] [rbp-9h]
  __int64 v22; // [rsp+58h] [rbp-1h]
  VARIANTARG pvarg; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v25; // [rsp+D8h] [rbp+7Fh] BYREF

  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  v6 = CoCreateInstance(
         &GUID_66d0db14_5638_475f_a386_629522d8c461,
         0,
         1u,
         &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
         &v18);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v17 = 0;
    bstr_nothrow = wil::make_bstr_nothrow(v19, a1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v17,
      bstr_nothrow);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v19);
    v9 = v17;
    if ( v17 )
    {
      v25 = 0;
      v10 = v18;
      v11 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v18 + 80LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
      v7 = v11(v10, v9, &v25);
      if ( v7 >= 0 )
      {
        VariantInit(&pvarg);
        v7 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v25 + 104LL))(v25, &pvarg);
        if ( v7 >= 0 )
        {
          if ( pvarg.vt == 8 || (v12 = VariantChangeTypeEx(&pvarg, &pvarg, 0x400u, a2, 8u), v7 = v12, v12 >= 0) )
          {
            v20 = 0;
            v21 = 0;
            v22 = 0;
            v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                    &v20,
                    pvarg.llVal,
                    -1);
            v7 = v13;
            if ( v13 >= 0 )
            {
              v14 = v20;
              v20 = 0;
              v22 = 0;
              v21 = 0;
              *a3 = v14;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v20);
              VariantClear(&pvarg);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
              v7 = 0;
              goto LABEL_16;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x84,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\policyprovider.cpp",
              (const char *)(unsigned int)v13,
              ppv);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v20);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7F,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\policyprovider.cpp",
              (const char *)(unsigned int)v12,
              ppv);
          }
        }
        VariantClear(&pvarg);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    }
    else
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\policyprovider.cpp",
        (const char *)0x8007000ELL,
        ppv);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\policyprovider.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  }
LABEL_16:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180055c4c  push    rbp
0x180055c4e  push    rbx
0x180055c4f  push    rsi
0x180055c50  push    rdi
0x180055c51  push    r14
0x180055c53  push    r15
0x180055c55  lea     rbp, [rsp-2Fh]
0x180055c5a  sub     rsp, 88h
0x180055c61  mov     r14, r8
0x180055c64  movzx   r15d, dx
0x180055c68  mov     rdi, rcx
0x180055c6b  mov     [rbp+57h+var_78], 0
0x180055c73  lea     rcx, [rbp+57h+var_78]
0x180055c77  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180055c7c  lea     rax, [rbp+57h+var_78]
0x180055c80  mov     qword ptr [rsp+0B0h+ppv], rax; int
0x180055c85  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180055c8c  xor     edx, edx; pUnkOuter
0x180055c8e  lea     r8d, [rdx+1]; dwClsContext
0x180055c92  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180055c99  call    cs:__imp_CoCreateInstance
0x180055c9f  mov     ebx, eax
0x180055ca1  test    eax, eax
0x180055ca3  jns     short loc_180055CC2
0x180055ca5  mov     rcx, [rbp+5Fh]; this
0x180055ca9  mov     r9d, eax; char *
0x180055cac  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\flightsetting"...
0x180055cb3  mov     edx, 6Dh ; 'm'; void *
0x180055cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055cbd  jmp     loc_180055E76
0x180055cc2  mov     [rbp+57h+var_80], 0
0x180055cca  mov     rdx, rdi
0x180055ccd  lea     rcx, [rbp+57h+var_70]
0x180055cd1  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180055cd6  mov     rdx, rax
0x180055cd9  lea     rcx, [rbp+57h+var_80]
0x180055cdd  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180055ce2  lea     rcx, [rbp+57h+var_70]
0x180055ce6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180055ceb  mov     rbx, [rbp+57h+var_80]
0x180055cef  test    rbx, rbx
0x180055cf2  jnz     short loc_180055D20
0x180055cf4  mov     rcx, [rbp+5Fh]; this
0x180055cf8  mov     ebx, 8007000Eh
0x180055cfd  mov     r9d, ebx; char *
0x180055d00  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\flightsetting"...
0x180055d07  mov     edx, 71h ; 'q'; void *
0x180055d0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055d11  nop
0x180055d12  lea     rcx, [rbp+57h+var_80]
0x180055d16  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180055d1b  jmp     loc_180055E76
0x180055d20  mov     [rbp+57h+arg_18], 0
0x180055d28  mov     rsi, [rbp+57h+var_78]
0x180055d2c  mov     rax, [rsi]
0x180055d2f  mov     rdi, [rax+50h]
0x180055d33  lea     rcx, [rbp+57h+arg_18]
0x180055d37  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180055d3c  lea     r8, [rbp+57h+arg_18]
0x180055d40  mov     rdx, rbx
0x180055d43  mov     rcx, rsi
0x180055d46  mov     rax, rdi
0x180055d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d4e  mov     ebx, eax
0x180055d50  test    eax, eax
0x180055d52  jns     short loc_180055D5F
0x180055d54  lea     rcx, [rbp+57h+arg_18]
0x180055d58  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180055d5d  jmp     short loc_180055D12
0x180055d5f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180055d63  call    cs:__imp_VariantInit
0x180055d69  nop
0x180055d6a  mov     rcx, [rbp+57h+arg_18]
0x180055d6e  mov     rax, [rcx]
0x180055d71  lea     rdx, [rbp+57h+pvarg]
0x180055d75  mov     rax, [rax+68h]
0x180055d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d7e  mov     ebx, eax
0x180055d80  test    eax, eax
0x180055d82  jns     short loc_180055D90
0x180055d84  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180055d88  call    cs:__imp_VariantClear
0x180055d8e  jmp     short loc_180055D54
0x180055d90  mov     eax, 8
0x180055d95  cmp     ax, word ptr [rbp+57h+pvarg]
0x180055d99  jz      short loc_180055DD8
0x180055d9b  mov     word ptr [rsp+0B0h+ppv], ax; int
0x180055da0  movzx   r9d, r15w; wFlags
0x180055da4  mov     r8d, 400h; lcid
0x180055daa  lea     rdx, [rbp+57h+pvarg]; pvarSrc
0x180055dae  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x180055db2  call    cs:__imp_VariantChangeTypeEx
0x180055db8  mov     ebx, eax
0x180055dba  test    eax, eax
0x180055dbc  jns     short loc_180055DD8
0x180055dbe  mov     rcx, [rbp+5Fh]; this
0x180055dc2  mov     r9d, eax; char *
0x180055dc5  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\flightsetting"...
0x180055dcc  mov     edx, 7Fh; void *
0x180055dd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055dd6  jmp     short loc_180055D84
0x180055dd8  mov     [rbp+57h+var_68], 0
0x180055de0  mov     [rbp+57h+var_60], 0
0x180055de8  mov     [rbp+57h+var_58], 0
0x180055df0  or      r8, 0FFFFFFFFFFFFFFFFh
0x180055df4  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x180055df8  lea     rcx, [rbp+57h+var_68]
0x180055dfc  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180055e01  mov     ebx, eax
0x180055e03  test    eax, eax
0x180055e05  jns     short loc_180055E2D
0x180055e07  mov     rcx, [rbp+5Fh]; this
0x180055e0b  mov     r9d, eax; char *
0x180055e0e  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\flightsetting"...
0x180055e15  mov     edx, 84h; void *
0x180055e1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055e1f  lea     rcx, [rbp+57h+var_68]
0x180055e23  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180055e28  jmp     loc_180055D84
0x180055e2d  mov     rax, [rbp+57h+var_68]
0x180055e31  mov     [rbp+57h+var_68], 0
0x180055e39  mov     [rbp+57h+var_58], 0
0x180055e41  mov     [rbp+57h+var_60], 0
0x180055e49  mov     [r14], rax
0x180055e4c  lea     rcx, [rbp+57h+var_68]
0x180055e50  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180055e55  nop
0x180055e56  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180055e5a  call    cs:__imp_VariantClear
0x180055e60  nop
0x180055e61  lea     rcx, [rbp+57h+arg_18]
0x180055e65  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180055e6a  nop
0x180055e6b  lea     rcx, [rbp+57h+var_80]
0x180055e6f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180055e74  xor     ebx, ebx
0x180055e76  lea     rcx, [rbp+57h+var_78]
0x180055e7a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180055e7f  mov     eax, ebx
0x180055e81  add     rsp, 88h
0x180055e88  pop     r15
0x180055e8a  pop     r14
0x180055e8c  pop     rdi
0x180055e8d  pop     rsi
0x180055e8e  pop     rbx
0x180055e8f  pop     rbp
0x180055e90  retn
```
