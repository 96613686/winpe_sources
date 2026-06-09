# _lambda_3d1b66ac7311afd2bf2e08de84efe645_::operator()

- ea: `0x1800740a4`
- end: `0x1800742c4`
- name: `_lambda_3d1b66ac7311afd2bf2e08de84efe645_::operator()`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180061514`

## callees

- `0x180005580`
- `0x180005660`
- `0x180010200`
- `0x180012108`
- `0x1800177ec`
- `0x180029d20`
- `0x18004490c`
- `0x180045074`
- `0x180060e38`
- `0x1800740a4`
- `0x1800810d0`

## import_xrefs

- `msvcrt!wcstoul` at `0x18007417e`
- `msvcrt!wcstoul` at `0x18007417e`
- `msvcrt!swprintf_s` at `0x1800741a6`
- `msvcrt!swprintf_s` at `0x1800741a6`

## string_xrefs

- `0x180074219`: `ServiceName`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall lambda_3d1b66ac7311afd2bf2e08de84efe645_::operator()(__int64 a1, __int64 a2, bool a3)
{
  const wchar_t *v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // r9
  __int64 i; // rax
  __int64 v9; // r9
  _QWORD *v10; // rcx
  wchar_t *v11; // rbx
  unsigned int v12; // eax
  HKEY *v13; // rbx
  const WCHAR *v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  _QWORD v20[5]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[32]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *EndPtr; // [rsp+88h] [rbp-78h] BYREF
  HKEY v23; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v24[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v25; // [rsp+B0h] [rbp-50h]
  _BYTE v26[16]; // [rsp+B8h] [rbp-48h] BYREF
  _WORD v27[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+D8h] [rbp-28h]
  __int64 v29; // [rsp+E0h] [rbp-20h]
  wchar_t Buffer[64]; // [rsp+F0h] [rbp-10h] BYREF

  v20[4] = -2;
  v4 = *(const wchar_t **)a1;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 24LL) >= 8u )
    v4 = *(const wchar_t **)v4;
  NetSetupDevice::NetSetupDevice((NetSetupDevice *)v26, v4, a3);
  v25 = 7;
  v24[2] = 0;
  LOWORD(v24[0]) = 0;
  if ( (unsigned __int8)NetSetupDevice::GetStringProperty(v26, &DEVPKEY_Device_Driver, v24) )
  {
    v7 = v24;
    if ( v25 >= 8 )
      v7 = (_QWORD *)v24[0];
    for ( i = *(_QWORD *)std::wstring::end(v24, &v23, v6, v7); i != v9 && *(_WORD *)(i - 2) != 92; i -= 2 )
      ;
    v10 = v24;
    if ( v25 >= 8 )
      v10 = (_QWORD *)v24[0];
    if ( (_QWORD *)i != v10 )
    {
      v11 = (wchar_t *)(i + 2);
      EndPtr = 0;
      v12 = wcstoul((const wchar_t *)(i + 2), &EndPtr, 10);
      if ( EndPtr != v11 )
      {
        v13 = *(HKEY **)(a1 + 8);
        swprintf_s(Buffer, 0x40u, L"%lu", v12 + 1);
        std::wstring::wstring(v20, Buffer);
        v14 = (const WCHAR *)v20;
        if ( v20[3] >= 8u )
          v14 = (const WCHAR *)v20[0];
        RegistryKey::CreateSubKey(v13, (HKEY)&v23, v14, 2u, 0, 0);
        LOBYTE(v15) = 1;
        std::wstring::_Tidy(v20, v15, 0);
        v16 = StringFromGuid(v21, **(_QWORD **)(a1 + 16) + 20LL);
        RegistryKey::SetValue(&v23, L"ServiceName", v16);
        LOBYTE(v17) = 1;
        std::wstring::_Tidy(v21, v17, 0);
        v29 = 7;
        v28 = 0;
        v27[0] = 0;
        if ( (unsigned __int8)NetSetupDevice::GetStringProperty(v26, &DEVPKEY_Device_DeviceDesc, v27) )
          RegistryKey::SetValue(&v23, L"Description", (__int64)v27);
        LOBYTE(v18) = 1;
        std::wstring::_Tidy(v27, v18, 0);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
      }
    }
  }
  LOBYTE(v5) = 1;
  return std::wstring::_Tidy(v24, v5, 0);
}

```

## disassembly

```asm
0x1800740a4  mov     rax, rsp
0x1800740a7  push    rbp
0x1800740a8  lea     rbp, [rsp-80h]
0x1800740ad  sub     rsp, 180h
0x1800740b4  mov     [rsp+180h+var_120], 0FFFFFFFFFFFFFFFEh
0x1800740bd  mov     [rax+10h], rbx
0x1800740c1  mov     [rax+18h], rdi
0x1800740c5  mov     rax, cs:__security_cookie
0x1800740cc  xor     rax, rsp
0x1800740cf  mov     [rbp+80h+var_10], rax
0x1800740d3  mov     rdi, rcx
0x1800740d6  mov     rdx, [rcx]
0x1800740d9  cmp     qword ptr [rdx+18h], 8
0x1800740de  jb      short loc_1800740E3
0x1800740e0  mov     rdx, [rdx]; wchar_t *
0x1800740e3  lea     rcx, [rbp+80h+var_C8]; this
0x1800740e7  call    ??0NetSetupDevice@@QEAA@PEB_W_N@Z; NetSetupDevice::NetSetupDevice(wchar_t const *,bool)
0x1800740ec  mov     [rbp+80h+var_D0], 7
0x1800740f4  mov     [rbp+80h+var_D8], 0
0x1800740fc  xor     eax, eax
0x1800740fe  mov     word ptr [rbp+80h+var_E8], ax
0x180074102  lea     r8, [rbp+80h+var_E8]
0x180074106  lea     rdx, DEVPKEY_Device_Driver
0x18007410d  lea     rcx, [rbp+80h+var_C8]
0x180074111  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x180074116  test    al, al
0x180074118  jz      loc_180074295
0x18007411e  lea     r9, [rbp+80h+var_E8]
0x180074122  cmp     [rbp+80h+var_D0], 8
0x180074127  cmovnb  r9, [rbp+80h+var_E8]
0x18007412c  lea     rdx, [rbp+80h+var_F0]
0x180074130  lea     rcx, [rbp+80h+var_E8]
0x180074134  call    ?end@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@2@XZ; std::wstring::end(void)
0x180074139  mov     rax, [rax]
0x18007413c  cmp     rax, r9
0x18007413f  jz      short loc_18007414E
0x180074141  cmp     word ptr [rax-2], 5Ch ; '\'
0x180074146  jz      short loc_18007414E
0x180074148  add     rax, 0FFFFFFFFFFFFFFFEh
0x18007414c  jmp     short loc_18007413C
0x18007414e  lea     rcx, [rbp+80h+var_E8]
0x180074152  cmp     [rbp+80h+var_D0], 8
0x180074157  cmovnb  rcx, [rbp+80h+var_E8]
0x18007415c  cmp     rax, rcx
0x18007415f  jz      loc_180074295
0x180074165  lea     rbx, [rax+2]
0x180074169  mov     [rbp+80h+EndPtr], 0
0x180074171  mov     r8d, 0Ah; Radix
0x180074177  lea     rdx, [rbp+80h+EndPtr]; EndPtr
0x18007417b  mov     rcx, rbx; String
0x18007417e  call    cs:__imp_wcstoul
0x180074184  cmp     [rbp+80h+EndPtr], rbx
0x180074188  jz      loc_180074295
0x18007418e  mov     rbx, [rdi+8]
0x180074192  lea     r9d, [rax+1]
0x180074196  lea     r8, aLu; "%lu"
0x18007419d  mov     edx, 40h ; '@'; BufferCount
0x1800741a2  lea     rcx, [rbp+80h+Buffer]; Buffer
0x1800741a6  call    cs:__imp_swprintf_s
0x1800741ac  lea     rdx, [rbp+80h+Buffer]
0x1800741b0  lea     rcx, [rsp+180h+var_140]
0x1800741b5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800741ba  nop
0x1800741bb  lea     r8, [rsp+180h+var_140]
0x1800741c0  cmp     [rsp+180h+var_128], 8
0x1800741c6  cmovnb  r8, [rsp+180h+var_140]
0x1800741cc  mov     [rsp+180h+var_158], 0
0x1800741d5  mov     [rsp+180h+var_160], 0
0x1800741de  mov     r9d, 2
0x1800741e4  lea     rdx, [rbp+80h+var_F0]
0x1800741e8  mov     rcx, rbx
0x1800741eb  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x1800741f0  nop
0x1800741f1  xor     r8d, r8d
0x1800741f4  mov     dl, 1
0x1800741f6  lea     rcx, [rsp+180h+var_140]
0x1800741fb  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180074200  mov     rax, [rdi+10h]
0x180074204  mov     rdx, [rax]
0x180074207  add     rdx, 14h
0x18007420b  lea     rcx, [rsp+180h+var_118]
0x180074210  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x180074215  nop
0x180074216  mov     r8, rax
0x180074219  lea     rdx, aServicename; "ServiceName"
0x180074220  lea     rcx, [rbp+80h+var_F0]
0x180074224  call    ?SetValue@RegistryKey@@QEBAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RegistryKey::SetValue(wchar_t const *,std::wstring const &)
0x180074229  nop
0x18007422a  xor     r8d, r8d
0x18007422d  mov     dl, 1
0x18007422f  lea     rcx, [rsp+180h+var_118]
0x180074234  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180074239  mov     [rbp+80h+var_A0], 7
0x180074241  mov     [rbp+80h+var_A8], 0
0x180074249  xor     eax, eax
0x18007424b  mov     [rbp+80h+var_B8], ax
0x18007424f  lea     r8, [rbp+80h+var_B8]
0x180074253  lea     rdx, DEVPKEY_Device_DeviceDesc
0x18007425a  lea     rcx, [rbp+80h+var_C8]
0x18007425e  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x180074263  test    al, al
0x180074265  jz      short loc_18007427C
0x180074267  lea     r8, [rbp+80h+var_B8]
0x18007426b  lea     rdx, aDescription; "Description"
0x180074272  lea     rcx, [rbp+80h+var_F0]
0x180074276  call    ?SetValue@RegistryKey@@QEBAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RegistryKey::SetValue(wchar_t const *,std::wstring const &)
0x18007427b  nop
0x18007427c  xor     r8d, r8d
0x18007427f  mov     dl, 1
0x180074281  lea     rcx, [rbp+80h+var_B8]
0x180074285  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18007428a  nop
0x18007428b  lea     rcx, [rbp+80h+var_F0]
0x18007428f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180074294  nop
0x180074295  xor     r8d, r8d
0x180074298  mov     dl, 1
0x18007429a  lea     rcx, [rbp+80h+var_E8]
0x18007429e  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800742a3  mov     rcx, [rbp+80h+var_10]
0x1800742a7  xor     rcx, rsp; StackCookie
0x1800742aa  call    __security_check_cookie
0x1800742af  lea     r11, [rsp+180h+var_s0]
0x1800742b7  mov     rbx, [r11+18h]
0x1800742bb  mov     rdi, [r11+20h]
0x1800742bf  mov     rsp, r11
0x1800742c2  pop     rbp
0x1800742c3  retn
```
