# SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveValuesToSystemAccts(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1400446a4`
- end: `0x1400447ad`
- name: `?IntlSaveValuesToSystemAccts@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEAUHKEY__@@PEBG1@Z`
- size: `265`
- prototype: `void __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140044284`

## callees

- `0x140005f30`
- `0x14000ed38`
- `0x14002c070`
- `0x140043a60`
- `0x140043c2c`
- `0x140043cc8`
- `0x1400446a4`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x140044702`
- `KERNEL32!RegOpenKeyExW` at `0x140044702`
- `KERNEL32!RegCreateKeyExW` at `0x14004474c`
- `KERNEL32!RegCreateKeyExW` at `0x14004474c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveValuesToSystemAccts(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HKEY *phkResult; // rax
  HKEY *v6; // rax
  HKEY hKeya; // [rsp+50h] [rbp-20h] BYREF
  HKEY v8; // [rsp+58h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-10h] BYREF

  v8 = 0;
  hKeya = 0;
  dwDisposition = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v8);
  if ( !RegOpenKeyExW(hKey, L"Control Panel\\International", 0, 0xF003Fu, phkResult) )
  {
    v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKeya);
    if ( !RegCreateKeyExW(HKEY_USERS, a3, 0, 0, 0, 0x20006u, 0, v6, &dwDisposition) )
    {
      if ( dwDisposition != 1 )
      {
        SystemSettings::DataModel::CopyCurrentUserSettings::IntlDeleteRegKeyValues(hKeya);
        SystemSettings::DataModel::CopyCurrentUserSettings::IntlDeleteRegSubKeys(hKeya);
      }
      SystemSettings::DataModel::CopyCurrentUserSettings::IntlCreateRegTree(v8, hKeya);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v8);
}

```

## disassembly

```asm
0x1400446a4  mov     [rsp-8+arg_8], rbx
0x1400446a9  mov     [rsp-8+arg_18], rdi
0x1400446ae  push    rbp
0x1400446af  mov     rbp, rsp
0x1400446b2  sub     rsp, 70h
0x1400446b6  mov     rax, cs:__security_cookie
0x1400446bd  xor     rax, rsp
0x1400446c0  mov     [rbp+var_8], rax
0x1400446c4  mov     rdi, r8
0x1400446c7  mov     rbx, rcx
0x1400446ca  mov     [rbp+var_18], 0
0x1400446d2  mov     [rbp+hKey], 0
0x1400446da  mov     [rbp+dwDisposition], 0
0x1400446e1  lea     rcx, [rbp+var_18]
0x1400446e5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400446ea  mov     [rsp+70h+phkResult], rax; phkResult
0x1400446ef  mov     r9d, 0F003Fh; samDesired
0x1400446f5  xor     r8d, r8d; ulOptions
0x1400446f8  lea     rdx, aControlPanelIn; "Control Panel\\International"
0x1400446ff  mov     rcx, rbx; hKey
0x140044702  call    cs:__imp_RegOpenKeyExW
0x140044708  test    eax, eax
0x14004470a  jnz     short loc_14004477C
0x14004470c  lea     rcx, [rbp+hKey]
0x140044710  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140044715  lea     rcx, [rbp+dwDisposition]
0x140044719  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x14004471e  mov     [rsp+70h+var_38], rax; phkResult
0x140044723  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004472c  mov     [rsp+70h+samDesired], 20006h; samDesired
0x140044734  mov     dword ptr [rsp+70h+phkResult], 0; dwOptions
0x14004473c  xor     r9d, r9d; lpClass
0x14004473f  xor     r8d, r8d; Reserved
0x140044742  mov     rdx, rdi; lpSubKey
0x140044745  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14004474c  call    cs:__imp_RegCreateKeyExW
0x140044752  test    eax, eax
0x140044754  jnz     short loc_14004477C
0x140044756  cmp     [rbp+dwDisposition], 1
0x14004475a  jz      short loc_14004476E
0x14004475c  mov     rcx, [rbp+hKey]; hKey
0x140044760  call    ?IntlDeleteRegKeyValues@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEAUHKEY__@@@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlDeleteRegKeyValues(HKEY__ *)
0x140044765  mov     rcx, [rbp+hKey]; hKey
0x140044769  call    ?IntlDeleteRegSubKeys@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEAUHKEY__@@@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlDeleteRegSubKeys(HKEY__ *)
0x14004476e  mov     rdx, [rbp+hKey]; HKEY
0x140044772  mov     rcx, [rbp+var_18]; HKEY
0x140044776  call    ?IntlCreateRegTree@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEAUHKEY__@@0@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlCreateRegTree(HKEY__ *,HKEY__ *)
0x14004477b  nop
0x14004477c  lea     rcx, [rbp+hKey]
0x140044780  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140044785  nop
0x140044786  lea     rcx, [rbp+var_18]
0x14004478a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14004478f  mov     rcx, [rbp+var_8]
0x140044793  xor     rcx, rsp; StackCookie
0x140044796  call    __security_check_cookie
0x14004479b  lea     r11, [rsp+70h+var_s0]
0x1400447a0  mov     rbx, [r11+18h]
0x1400447a4  mov     rdi, [r11+28h]
0x1400447a8  mov     rsp, r11
0x1400447ab  pop     rbp
0x1400447ac  retn
```
