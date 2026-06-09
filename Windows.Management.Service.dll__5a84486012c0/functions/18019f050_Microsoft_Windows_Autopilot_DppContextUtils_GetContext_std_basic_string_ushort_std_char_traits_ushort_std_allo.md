# Microsoft::Windows::Autopilot::DppContextUtils::GetContext(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18019f050`
- end: `0x18019f258`
- name: `?GetContext@DppContextUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `520`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f3ac4`
- `0x18019f260`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006defc`
- `0x18007755c`
- `0x18008019c`
- `0x1800839bc`
- `0x1800841e8`
- `0x18008939c`
- `0x18008c244`
- `0x18019f050`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019f097`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019f097`
- `OLEAUT32!__imp_VariantInit` at `0x18019f1a9`
- `OLEAUT32!__imp_VariantInit` at `0x18019f1a9`
- `OLEAUT32!__imp_VariantClear` at `0x18019f1e7`
- `OLEAUT32!__imp_VariantClear` at `0x18019f219`
- `OLEAUT32!__imp_VariantClear` at `0x18019f1e7`
- `OLEAUT32!__imp_VariantClear` at `0x18019f219`

## string_xrefs

- `0x18019f0c0`: `./Device/Vendor/MSFT/DevicePreparation/BootstrapperAgent/ExecutionContext`
- `0x18019f0aa`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\dppcontextutils.cpp`
- `0x18019f12b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\dppcontextutils.cpp`
- `0x18019f1d2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\dppcontextutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Windows::Autopilot::DppContextUtils::GetContext(__int64 a1)
{
  HRESULT v2; // eax
  int v3; // ebx
  LPVOID v4; // rdi
  __int64 (__fastcall *v5)(LPVOID, _QWORD, __int64 *); // rbx
  __int64 v6; // rax
  _QWORD *bstr; // rax
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  int ppv; // [rsp+20h] [rbp-39h]
  __int64 v16; // [rsp+30h] [rbp-29h] BYREF
  int v17; // [rsp+38h] [rbp-21h] BYREF
  LPVOID v18; // [rsp+40h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v20[8]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v21[32]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v18 = 0;
  v2 = CoCreateInstance(
         &GUID_66d0db14_5638_475f_a386_629522d8c461,
         0,
         1u,
         &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
         &v18);
  v3 = v2;
  if ( v2 >= 0 )
  {
    std::wstring::wstring(v21, L"./Device/Vendor/MSFT/DevicePreparation/BootstrapperAgent/ExecutionContext");
    v16 = 0;
    v4 = v18;
    v5 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v18 + 80LL);
    v16 = 0;
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
    bstr = (_QWORD *)wil::make_bstr(v20, v6);
    v3 = v5(v4, *bstr, &v16);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v20);
    if ( v3 >= 0 )
    {
      v17 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 224LL))(v16, &v17);
      v3 = v10;
      if ( v10 >= 0 )
      {
        if ( !v17 )
        {
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v16);
          std::wstring::_Tidy_deallocate(v21);
          v3 = -2147023728;
          goto LABEL_17;
        }
        VariantInit(&pvarg);
        v11 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v16 + 104LL))(v16, &pvarg);
        v3 = v11;
        if ( v11 >= 0 )
        {
          if ( pvarg.vt == 8 )
          {
            std::wstring::assign(a1, pvarg.llVal);
            VariantClear(&pvarg);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v16);
            std::wstring::_Tidy_deallocate(v21);
            v3 = 0;
            goto LABEL_17;
          }
          v3 = -2147418113;
          v12 = 2147549183LL;
          v13 = 71;
        }
        else
        {
          v12 = (unsigned int)v11;
          v13 = 70;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\dppcontextutils.cpp",
          (const char *)v12,
          ppv);
        VariantClear(&pvarg);
        goto LABEL_6;
      }
      v8 = (unsigned int)v10;
      v9 = 62;
    }
    else
    {
      v8 = (unsigned int)v3;
      v9 = 59;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\dppcontextutils.cpp",
      (const char *)v8,
      ppv);
LABEL_6:
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v16);
    std::wstring::_Tidy_deallocate(v21);
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x36,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\dppcontextutils.cpp",
    (const char *)(unsigned int)v2,
    ppv);
LABEL_17:
  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v18);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18019f050  push    rbp
0x18019f052  push    rbx
0x18019f053  push    rsi
0x18019f054  push    rdi
0x18019f055  lea     rbp, [rsp-3Fh]
0x18019f05a  sub     rsp, 98h
0x18019f061  mov     rax, cs:__security_cookie
0x18019f068  xor     rax, rsp
0x18019f06b  mov     [rbp+57h+var_28], rax
0x18019f06f  mov     rsi, rcx
0x18019f072  mov     [rbp+57h+var_70], 0
0x18019f07a  lea     rax, [rbp+57h+var_70]
0x18019f07e  mov     qword ptr [rsp+0B0h+ppv], rax; int
0x18019f083  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18019f08a  xor     edx, edx; pUnkOuter
0x18019f08c  lea     r8d, [rdx+1]; dwClsContext
0x18019f090  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18019f097  call    cs:__imp_CoCreateInstance
0x18019f09d  mov     ebx, eax
0x18019f09f  test    eax, eax
0x18019f0a1  jns     short loc_18019F0C0
0x18019f0a3  mov     rcx, [rbp+5Fh]; this
0x18019f0a7  mov     r9d, eax; char *
0x18019f0aa  lea     r8, aOnecoreuapAdmi_57; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f0b1  mov     edx, 36h ; '6'; void *
0x18019f0b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019f0bb  jmp     loc_18019F235
0x18019f0c0  lea     rdx, aDeviceVendorMs; "./Device/Vendor/MSFT/DevicePreparation/"...
0x18019f0c7  lea     rcx, [rbp+57h+var_48]
0x18019f0cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18019f0d0  nop
0x18019f0d1  mov     [rbp+57h+var_80], 0
0x18019f0d9  mov     rdi, [rbp+57h+var_70]
0x18019f0dd  mov     rax, [rdi]
0x18019f0e0  mov     rbx, [rax+50h]
0x18019f0e4  mov     [rbp+57h+var_80], 0
0x18019f0ec  lea     rcx, [rbp+57h+var_48]
0x18019f0f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019f0f5  mov     rdx, rax
0x18019f0f8  lea     rcx, [rbp+57h+var_50]
0x18019f0fc  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18019f101  nop
0x18019f102  lea     r8, [rbp+57h+var_80]
0x18019f106  mov     rdx, [rax]
0x18019f109  mov     rcx, rdi
0x18019f10c  mov     rax, rbx
0x18019f10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f114  mov     ebx, eax
0x18019f116  lea     rcx, [rbp+57h+var_50]
0x18019f11a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019f11f  test    ebx, ebx
0x18019f121  jns     short loc_18019F154
0x18019f123  mov     r9d, ebx; char *
0x18019f126  mov     edx, 3Bh ; ';'; void *
0x18019f12b  lea     r8, aOnecoreuapAdmi_57; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f132  mov     rcx, [rbp+5Fh]; this
0x18019f136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019f13b  nop
0x18019f13c  lea     rcx, [rbp+57h+var_80]
0x18019f140  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019f145  nop
0x18019f146  lea     rcx, [rbp+57h+var_48]
0x18019f14a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f14f  jmp     loc_18019F235
0x18019f154  mov     [rbp+57h+var_78], 0
0x18019f15b  mov     rcx, [rbp+57h+var_80]
0x18019f15f  mov     rax, [rcx]
0x18019f162  lea     rdx, [rbp+57h+var_78]
0x18019f166  mov     rax, [rax+0E0h]
0x18019f16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f172  mov     ebx, eax
0x18019f174  test    eax, eax
0x18019f176  jns     short loc_18019F182
0x18019f178  mov     r9d, eax
0x18019f17b  mov     edx, 3Eh ; '>'
0x18019f180  jmp     short loc_18019F12B
0x18019f182  cmp     [rbp+57h+var_78], 0
0x18019f186  jnz     short loc_18019F1A5
0x18019f188  lea     rcx, [rbp+57h+var_80]
0x18019f18c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019f191  nop
0x18019f192  lea     rcx, [rbp+57h+var_48]
0x18019f196  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f19b  mov     ebx, 80070490h
0x18019f1a0  jmp     loc_18019F235
0x18019f1a5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18019f1a9  call    cs:__imp_VariantInit
0x18019f1af  nop
0x18019f1b0  mov     rcx, [rbp+57h+var_80]
0x18019f1b4  mov     rax, [rcx]
0x18019f1b7  lea     rdx, [rbp+57h+pvarg]
0x18019f1bb  mov     rax, [rax+68h]
0x18019f1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f1c4  mov     ebx, eax
0x18019f1c6  test    eax, eax
0x18019f1c8  jns     short loc_18019F1F2
0x18019f1ca  mov     r9d, eax; char *
0x18019f1cd  mov     edx, 46h ; 'F'; void *
0x18019f1d2  lea     r8, aOnecoreuapAdmi_57; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019f1d9  mov     rcx, [rbp+5Fh]; this
0x18019f1dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019f1e2  nop
0x18019f1e3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18019f1e7  call    cs:__imp_VariantClear
0x18019f1ed  jmp     loc_18019F13C
0x18019f1f2  cmp     word ptr [rbp+57h+pvarg], 8
0x18019f1f7  jz      short loc_18019F208
0x18019f1f9  mov     ebx, 8000FFFFh
0x18019f1fe  mov     r9d, ebx
0x18019f201  mov     edx, 47h ; 'G'
0x18019f206  jmp     short loc_18019F1D2
0x18019f208  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x18019f20c  mov     rcx, rsi
0x18019f20f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18019f214  nop
0x18019f215  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18019f219  call    cs:__imp_VariantClear
0x18019f21f  nop
0x18019f220  lea     rcx, [rbp+57h+var_80]
0x18019f224  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019f229  nop
0x18019f22a  lea     rcx, [rbp+57h+var_48]
0x18019f22e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019f233  xor     ebx, ebx
0x18019f235  lea     rcx, [rbp+57h+var_70]
0x18019f239  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x18019f23e  mov     eax, ebx
0x18019f240  mov     rcx, [rbp+57h+var_28]
0x18019f244  xor     rcx, rsp; StackCookie
0x18019f247  call    __security_check_cookie
0x18019f24c  add     rsp, 98h
0x18019f253  pop     rdi
0x18019f254  pop     rsi
0x18019f255  pop     rbx
0x18019f256  pop     rbp
0x18019f257  retn
```
