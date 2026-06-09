# Microsoft::Windows::Autopilot::DppContextUtils::GetContext(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1801a4494`
- end: `0x1801a46b5`
- name: `?GetContext@DppContextUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `545`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f6924`
- `0x1801a46bc`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006e43c`
- `0x180077de0`
- `0x180080bac`
- `0x180084574`
- `0x180084d5c`
- `0x18008a26c`
- `0x18008d290`
- `0x1801a4494`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a44db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a44db`
- `OLEAUT32!__imp_VariantInit` at `0x1801a45f3`
- `OLEAUT32!__imp_VariantInit` at `0x1801a45f3`
- `OLEAUT32!__imp_VariantClear` at `0x1801a4637`
- `OLEAUT32!__imp_VariantClear` at `0x1801a466f`
- `OLEAUT32!__imp_VariantClear` at `0x1801a4637`
- `OLEAUT32!__imp_VariantClear` at `0x1801a466f`

## string_xrefs

- `0x1801a450a`: `./Device/Vendor/MSFT/DevicePreparation/BootstrapperAgent/ExecutionContext`
- `0x1801a44f4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\dppcontextutils.cpp`
- `0x1801a4575`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\dppcontextutils.cpp`
- `0x1801a4622`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\dppcontextutils.cpp`

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
0x1801a4494  push    rbp
0x1801a4496  push    rbx
0x1801a4497  push    rsi
0x1801a4498  push    rdi
0x1801a4499  lea     rbp, [rsp-3Fh]
0x1801a449e  sub     rsp, 98h
0x1801a44a5  mov     rax, cs:__security_cookie
0x1801a44ac  xor     rax, rsp
0x1801a44af  mov     [rbp+57h+var_28], rax
0x1801a44b3  mov     rsi, rcx
0x1801a44b6  mov     [rbp+57h+var_70], 0
0x1801a44be  lea     rax, [rbp+57h+var_70]
0x1801a44c2  mov     qword ptr [rsp+0B0h+ppv], rax; int
0x1801a44c7  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1801a44ce  xor     edx, edx; pUnkOuter
0x1801a44d0  lea     r8d, [rdx+1]; dwClsContext
0x1801a44d4  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1801a44db  call    cs:__imp_CoCreateInstance
0x1801a44e2  nop     dword ptr [rax+rax+00h]
0x1801a44e7  mov     ebx, eax
0x1801a44e9  test    eax, eax
0x1801a44eb  jns     short loc_1801A450A
0x1801a44ed  mov     rcx, [rbp+5Fh]; this
0x1801a44f1  mov     r9d, eax; char *
0x1801a44f4  lea     r8, aOnecoreuapAdmi_57; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a44fb  mov     edx, 36h ; '6'; void *
0x1801a4500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a4505  jmp     loc_1801A4691
0x1801a450a  lea     rdx, aDeviceVendorMs; "./Device/Vendor/MSFT/DevicePreparation/"...
0x1801a4511  lea     rcx, [rbp+57h+var_48]
0x1801a4515  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801a451a  nop
0x1801a451b  mov     [rbp+57h+var_80], 0
0x1801a4523  mov     rdi, [rbp+57h+var_70]
0x1801a4527  mov     rax, [rdi]
0x1801a452a  mov     rbx, [rax+50h]
0x1801a452e  mov     [rbp+57h+var_80], 0
0x1801a4536  lea     rcx, [rbp+57h+var_48]
0x1801a453a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a453f  mov     rdx, rax
0x1801a4542  lea     rcx, [rbp+57h+var_50]
0x1801a4546  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801a454b  nop
0x1801a454c  lea     r8, [rbp+57h+var_80]
0x1801a4550  mov     rdx, [rax]
0x1801a4553  mov     rcx, rdi
0x1801a4556  mov     rax, rbx
0x1801a4559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a455e  mov     ebx, eax
0x1801a4560  lea     rcx, [rbp+57h+var_50]
0x1801a4564  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801a4569  test    ebx, ebx
0x1801a456b  jns     short loc_1801A459E
0x1801a456d  mov     r9d, ebx; char *
0x1801a4570  mov     edx, 3Bh ; ';'; void *
0x1801a4575  lea     r8, aOnecoreuapAdmi_57; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a457c  mov     rcx, [rbp+5Fh]; this
0x1801a4580  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a4585  nop
0x1801a4586  lea     rcx, [rbp+57h+var_80]
0x1801a458a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801a458f  nop
0x1801a4590  lea     rcx, [rbp+57h+var_48]
0x1801a4594  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a4599  jmp     loc_1801A4691
0x1801a459e  mov     [rbp+57h+var_78], 0
0x1801a45a5  mov     rcx, [rbp+57h+var_80]
0x1801a45a9  mov     rax, [rcx]
0x1801a45ac  lea     rdx, [rbp+57h+var_78]
0x1801a45b0  mov     rax, [rax+0E0h]
0x1801a45b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a45bc  mov     ebx, eax
0x1801a45be  test    eax, eax
0x1801a45c0  jns     short loc_1801A45CC
0x1801a45c2  mov     r9d, eax
0x1801a45c5  mov     edx, 3Eh ; '>'
0x1801a45ca  jmp     short loc_1801A4575
0x1801a45cc  cmp     [rbp+57h+var_78], 0
0x1801a45d0  jnz     short loc_1801A45EF
0x1801a45d2  lea     rcx, [rbp+57h+var_80]
0x1801a45d6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801a45db  nop
0x1801a45dc  lea     rcx, [rbp+57h+var_48]
0x1801a45e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a45e5  mov     ebx, 80070490h
0x1801a45ea  jmp     loc_1801A4691
0x1801a45ef  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801a45f3  call    cs:__imp_VariantInit
0x1801a45fa  nop     dword ptr [rax+rax+00h]
0x1801a45ff  nop
0x1801a4600  mov     rcx, [rbp+57h+var_80]
0x1801a4604  mov     rax, [rcx]
0x1801a4607  lea     rdx, [rbp+57h+pvarg]
0x1801a460b  mov     rax, [rax+68h]
0x1801a460f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a4614  mov     ebx, eax
0x1801a4616  test    eax, eax
0x1801a4618  jns     short loc_1801A4648
0x1801a461a  mov     r9d, eax; char *
0x1801a461d  mov     edx, 46h ; 'F'; void *
0x1801a4622  lea     r8, aOnecoreuapAdmi_57; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a4629  mov     rcx, [rbp+5Fh]; this
0x1801a462d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a4632  nop
0x1801a4633  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801a4637  call    cs:__imp_VariantClear
0x1801a463e  nop     dword ptr [rax+rax+00h]
0x1801a4643  jmp     loc_1801A4586
0x1801a4648  cmp     word ptr [rbp+57h+pvarg], 8
0x1801a464d  jz      short loc_1801A465E
0x1801a464f  mov     ebx, 8000FFFFh
0x1801a4654  mov     r9d, ebx
0x1801a4657  mov     edx, 47h ; 'G'
0x1801a465c  jmp     short loc_1801A4622
0x1801a465e  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x1801a4662  mov     rcx, rsi
0x1801a4665  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801a466a  nop
0x1801a466b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801a466f  call    cs:__imp_VariantClear
0x1801a4676  nop     dword ptr [rax+rax+00h]
0x1801a467b  nop
0x1801a467c  lea     rcx, [rbp+57h+var_80]
0x1801a4680  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801a4685  nop
0x1801a4686  lea     rcx, [rbp+57h+var_48]
0x1801a468a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a468f  xor     ebx, ebx
0x1801a4691  lea     rcx, [rbp+57h+var_70]
0x1801a4695  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1801a469a  mov     eax, ebx
0x1801a469c  mov     rcx, [rbp+57h+var_28]
0x1801a46a0  xor     rcx, rsp; StackCookie
0x1801a46a3  call    __security_check_cookie
0x1801a46a8  add     rsp, 98h
0x1801a46af  pop     rdi
0x1801a46b0  pop     rsi
0x1801a46b1  pop     rbx
0x1801a46b2  pop     rbp
0x1801a46b3  retn
```
