# ComputerAccountHelper::CreateByName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180072958`
- end: `0x180072a70`
- name: `?CreateByName@ComputerAccountHelper@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a15c`

## callees

- `0x18000b6b4`
- `0x18000cfe4`
- `0x18002001c`
- `0x180072958`
- `0x180072e80`
- `0x180072f1c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072996`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072996`

## string_xrefs

- `0x1800729a9`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\computeraccounthelper.cpp`
- `0x180072a06`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\computeraccounthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComputerAccountHelper::CreateByName(struct IPropertyStore *a1, __int64 a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(__int64, __int64, struct IPropertyStore **); // r9
  __int64 v7; // r10
  int v8; // eax
  ComputerAccountHelper *v9; // rcx
  bool v10; // r8
  __int64 v11; // rdx
  ComputerAccountHelper *v12; // rcx
  unsigned int v13; // r8d
  int v15; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  struct IPropertyStore *v17; // [rsp+40h] [rbp+10h] BYREF
  LPVOID v18; // [rsp+58h] [rbp+28h] BYREF

  v17 = a1;
  v18 = 0;
  v3 = CoCreateInstance(&CLSID_LocalUserAccounts, 0, 3u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &v18);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v17 = 0;
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v8 = v6(v7, v5, &v17);
    v4 = v8;
    if ( v8 >= 0 )
    {
      v8 = ComputerAccountHelper::SetUserMustChangePasswordAtNextLogon(v9, v17, v10);
      v4 = v8;
      if ( v8 >= 0 )
      {
        v8 = ComputerAccountHelper::SetUserAccountControl(v12, v17, v13);
        v4 = v8;
        if ( v8 >= 0 )
        {
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v17);
          v4 = 0;
          goto LABEL_11;
        }
        v11 = 61;
      }
      else
      {
        v11 = 60;
      }
    }
    else
    {
      v11 = 59;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\computeraccounthelper.cpp",
      (const char *)(unsigned int)v8,
      v15);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v17);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\computeraccounthelper.cpp",
      (const char *)(unsigned int)v3,
      v15);
  }
LABEL_11:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v18);
  return v4;
}

```

## disassembly

```asm
0x180072958  mov     r11, rsp
0x18007295b  mov     [r11+10h], rbx
0x18007295f  mov     [r11+18h], rdi
0x180072963  mov     [r11+8], rcx
0x180072967  push    rbp
0x180072968  mov     rbp, rsp
0x18007296b  sub     rsp, 30h
0x18007296f  mov     rdi, rdx
0x180072972  mov     [rbp+arg_18], 0
0x18007297a  lea     rax, [rbp+arg_18]
0x18007297e  mov     [r11-18h], rax
0x180072982  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x180072989  xor     edx, edx; pUnkOuter
0x18007298b  lea     r8d, [rdx+3]; dwClsContext
0x18007298f  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x180072996  call    cs:__imp_CoCreateInstance
0x18007299c  mov     ebx, eax
0x18007299e  test    eax, eax
0x1800729a0  jns     short loc_1800729BF
0x1800729a2  mov     rcx, [rbp+8]; this
0x1800729a6  mov     r9d, eax; char *
0x1800729a9  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800729b0  mov     edx, 38h ; '8'; void *
0x1800729b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800729ba  jmp     loc_180072A55
0x1800729bf  mov     [rbp+arg_0], 0
0x1800729c7  mov     r10, [rbp+arg_18]
0x1800729cb  mov     rax, [r10]
0x1800729ce  mov     r9, [rax+38h]
0x1800729d2  mov     [rbp+arg_0], 0
0x1800729da  mov     rcx, rdi
0x1800729dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800729e2  lea     r8, [rbp+arg_0]
0x1800729e6  mov     rdx, rax
0x1800729e9  mov     rcx, r10
0x1800729ec  mov     rax, r9
0x1800729ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800729f4  mov     ebx, eax
0x1800729f6  test    eax, eax
0x1800729f8  jns     short loc_180072A1E
0x1800729fa  mov     edx, 3Bh ; ';'; void *
0x1800729ff  mov     rcx, [rbp+8]; this
0x180072a03  mov     r9d, eax; char *
0x180072a06  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180072a0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072a12  nop
0x180072a13  lea     rcx, [rbp+arg_0]
0x180072a17  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072a1c  jmp     short loc_180072A55
0x180072a1e  mov     rdx, [rbp+arg_0]; struct IPropertyStore *
0x180072a22  call    ?SetUserMustChangePasswordAtNextLogon@ComputerAccountHelper@@AEAAJPEAUIPropertyStore@@_N@Z; ComputerAccountHelper::SetUserMustChangePasswordAtNextLogon(IPropertyStore *,bool)
0x180072a27  mov     ebx, eax
0x180072a29  test    eax, eax
0x180072a2b  jns     short loc_180072A34
0x180072a2d  mov     edx, 3Ch ; '<'
0x180072a32  jmp     short loc_1800729FF
0x180072a34  mov     rdx, [rbp+arg_0]; struct IPropertyStore *
0x180072a38  call    ?SetUserAccountControl@ComputerAccountHelper@@AEAAJPEAUIPropertyStore@@K@Z; ComputerAccountHelper::SetUserAccountControl(IPropertyStore *,ulong)
0x180072a3d  mov     ebx, eax
0x180072a3f  test    eax, eax
0x180072a41  jns     short loc_180072A4A
0x180072a43  mov     edx, 3Dh ; '='
0x180072a48  jmp     short loc_1800729FF
0x180072a4a  lea     rcx, [rbp+arg_0]
0x180072a4e  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072a53  xor     ebx, ebx
0x180072a55  lea     rcx, [rbp+arg_18]
0x180072a59  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180072a5e  mov     eax, ebx
0x180072a60  mov     rbx, [rsp+30h+arg_8]
0x180072a65  mov     rdi, [rsp+30h+arg_10]
0x180072a6a  add     rsp, 30h
0x180072a6e  pop     rbp
0x180072a6f  retn
```
