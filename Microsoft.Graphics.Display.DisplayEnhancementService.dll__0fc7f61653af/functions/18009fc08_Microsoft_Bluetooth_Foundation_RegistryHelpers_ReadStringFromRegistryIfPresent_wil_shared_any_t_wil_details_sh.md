# Microsoft::Bluetooth::Foundation::RegistryHelpers::ReadStringFromRegistryIfPresent<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>>(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009fc08`
- end: `0x18009fde3`
- name: `??$ReadStringFromRegistryIfPresent@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@RegistryHelpers@Foundation@Bluetooth@Microsoft@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV45@@Z`
- size: `475`
- prototype: `__int64 __fastcall(__int64, HKEY *, __int64)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b19d4`
- `0x1800b1aa8`
- `0x1800b1b14`
- `0x1800b1c10`

## callees

- `0x180005860`
- `0x180006440`
- `0x180009050`
- `0x18000fa0c`
- `0x18000fb14`
- `0x180011fc4`
- `0x180013578`
- `0x18001ed58`
- `0x180066310`
- `0x180074898`
- `0x18007538c`
- `0x1800828f0`
- `0x18009fc08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009fc87`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009fd52`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009fc87`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009fd52`

## string_xrefs

- `0x18009fcac`: `onecore\private\drivers\inc\bluetooth\foundation\RegistryHelpers.h`
- `0x18009fd63`: `onecore\private\drivers\inc\bluetooth\foundation\RegistryHelpers.h`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Foundation::RegistryHelpers::ReadStringFromRegistryIfPresent<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>>(
        __int64 a1,
        HKEY *a2,
        __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  const WCHAR *v8; // rax
  HKEY v9; // rcx
  unsigned int ValueW; // eax
  __int64 v11; // r8
  char *v12; // rsi
  unsigned __int64 v13; // rcx
  char *v14; // rax
  size_t v15; // rbx
  void *pvData; // rdx
  const WCHAR *v17; // r8
  HKEY v18; // rcx
  unsigned int v19; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-39h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-39h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v24; // [rsp+48h] [rbp-11h] BYREF
  void *v25; // [rsp+50h] [rbp-9h]
  __int64 v26; // [rsp+58h] [rbp-1h]
  _BYTE v27[32]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  pcbData[1] = HIDWORD(a1);
  pcbData[0] = 0;
  std::vector<unsigned short>::vector<unsigned short>(&v24, 0);
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v6, v7);
  v9 = *a2;
  if ( *a2 )
    v9 = *(HKEY *)v9;
  ValueW = RegGetValueW(v9, 0, v8, 2u, 0, 0, pcbData);
  if ( ValueW == 2 || !pcbData[0] )
  {
    std::wstring::wstring(a1, &dword_180100DC4);
    goto LABEL_21;
  }
  if ( ValueW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\RegistryHelpers.h",
      (const char *)ValueW,
      pdwType);
  v12 = (char *)v25;
  v13 = ((__int64)v25 - v24) >> 1;
  if ( pcbData[0] < v13 )
  {
    v14 = (char *)(v24 + 2LL * pcbData[0]);
LABEL_13:
    v25 = v14;
    goto LABEL_14;
  }
  if ( pcbData[0] > v13 )
  {
    if ( pcbData[0] <= (unsigned __int64)((v26 - v24) >> 1) )
    {
      v15 = 2 * (pcbData[0] - v13);
      memset_0(v25, 0, v15);
      v14 = &v12[v15];
      goto LABEL_13;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&v24, pcbData[0]);
  }
LABEL_14:
  v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v24, v11);
  if ( *a2 )
    v18 = *(HKEY *)*a2;
  else
    v18 = 0;
  v19 = RegGetValueW(v18, 0, v17, 2u, 0, pvData, pcbData);
  if ( v19 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\RegistryHelpers.h",
      (const char *)v19,
      pdwTypea);
  std::wstring::wstring(v27);
  std::wstring::assign(v27, v24);
  std::wstring::wstring(a1, v27);
  std::wstring::_Tidy_deallocate(v27);
LABEL_21:
  std::vector<unsigned short>::_Tidy(&v24);
  return a1;
}

```

## disassembly

```asm
0x18009fc08  mov     [rsp-8+arg_18], rbx
0x18009fc0d  push    rbp
0x18009fc0e  push    rsi
0x18009fc0f  push    rdi
0x18009fc10  push    r14
0x18009fc12  push    r15
0x18009fc14  lea     rbp, [rsp-37h]
0x18009fc19  sub     rsp, 90h
0x18009fc20  mov     rax, cs:__security_cookie
0x18009fc27  xor     rax, rsp
0x18009fc2a  mov     [rbp+57h+var_28], rax
0x18009fc2e  mov     r15, r8
0x18009fc31  mov     r14, rdx
0x18009fc34  mov     rdi, rcx
0x18009fc37  mov     qword ptr [rbp+57h+var_70], rcx
0x18009fc3b  mov     [rbp+57h+var_70], 0
0x18009fc42  xor     edx, edx
0x18009fc44  lea     rcx, [rbp+57h+var_68]
0x18009fc48  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18009fc4d  nop
0x18009fc4e  mov     rcx, r15
0x18009fc51  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009fc56  mov     rcx, [r14]
0x18009fc59  test    rcx, rcx
0x18009fc5c  jz      short loc_18009FC61
0x18009fc5e  mov     rcx, [rcx]; hkey
0x18009fc61  lea     rdx, [rbp+57h+var_70]
0x18009fc65  mov     [rsp+0B0h+pcbData], rdx; pcbData
0x18009fc6a  mov     [rsp+0B0h+pvData], 0; pvData
0x18009fc73  mov     [rsp+0B0h+pdwType], 0; unsigned int
0x18009fc7c  mov     r9d, 2; dwFlags
0x18009fc82  mov     r8, rax; lpValue
0x18009fc85  xor     edx, edx; lpSubKey
0x18009fc87  call    cs:__imp_RegGetValueW
0x18009fc8d  cmp     eax, 2
0x18009fc90  jz      loc_18009FDA4
0x18009fc96  mov     edx, [rbp+57h+var_70]
0x18009fc99  test    edx, edx
0x18009fc9b  jz      loc_18009FDA4
0x18009fca1  mov     rcx, [rbp+5Fh]; this
0x18009fca5  test    eax, eax
0x18009fca7  jz      short loc_18009FCBE
0x18009fca9  mov     r9d, eax; char *
0x18009fcac  lea     r8, aOnecorePrivate; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18009fcb3  mov     edx, 19Ah; void *
0x18009fcb8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009fcbe  mov     rbx, rdx
0x18009fcc1  mov     rdx, [rbp+57h+var_68]
0x18009fcc5  mov     rsi, [rbp+57h+var_60]
0x18009fcc9  mov     rcx, rsi
0x18009fccc  sub     rcx, rdx
0x18009fccf  sar     rcx, 1
0x18009fcd2  cmp     rbx, rcx
0x18009fcd5  jnb     short loc_18009FCDD
0x18009fcd7  lea     rax, [rdx+rbx*2]
0x18009fcdb  jmp     short loc_18009FD13
0x18009fcdd  jbe     short loc_18009FD17
0x18009fcdf  mov     rax, [rbp+57h+var_58]
0x18009fce3  sub     rax, rdx
0x18009fce6  sar     rax, 1
0x18009fce9  cmp     rbx, rax
0x18009fcec  jbe     short loc_18009FCFC
0x18009fcee  mov     rdx, rbx
0x18009fcf1  lea     rcx, [rbp+57h+var_68]
0x18009fcf5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18009fcfa  jmp     short loc_18009FD17
0x18009fcfc  sub     rbx, rcx
0x18009fcff  add     rbx, rbx
0x18009fd02  mov     r8, rbx; Size
0x18009fd05  xor     edx, edx; Val
0x18009fd07  mov     rcx, rsi; void *
0x18009fd0a  call    memset_0
0x18009fd0f  lea     rax, [rbx+rsi]
0x18009fd13  mov     [rbp+57h+var_60], rax
0x18009fd17  mov     rdx, [rbp+57h+var_68]
0x18009fd1b  mov     rcx, r15
0x18009fd1e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009fd23  mov     r8, rax; lpValue
0x18009fd26  mov     rax, [r14]
0x18009fd29  test    rax, rax
0x18009fd2c  jz      short loc_18009FD33
0x18009fd2e  mov     rcx, [rax]
0x18009fd31  jmp     short loc_18009FD35
0x18009fd33  xor     ecx, ecx; hkey
0x18009fd35  lea     rax, [rbp+57h+var_70]
0x18009fd39  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18009fd3e  mov     [rsp+0B0h+pvData], rdx; pvData
0x18009fd43  mov     [rsp+0B0h+pdwType], 0; unsigned int
0x18009fd4c  xor     edx, edx; lpSubKey
0x18009fd4e  lea     r9d, [rdx+2]; dwFlags
0x18009fd52  call    cs:__imp_RegGetValueW
0x18009fd58  mov     rcx, [rbp+5Fh]; this
0x18009fd5c  test    eax, eax
0x18009fd5e  jz      short loc_18009FD75
0x18009fd60  mov     r9d, eax; char *
0x18009fd63  lea     r8, aOnecorePrivate; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18009fd6a  mov     edx, 1A4h; void *
0x18009fd6f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009fd75  lea     rcx, [rbp+57h+var_48]
0x18009fd79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009fd7e  nop
0x18009fd7f  mov     rdx, [rbp+57h+var_68]
0x18009fd83  lea     rcx, [rbp+57h+var_48]
0x18009fd87  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18009fd8c  lea     rdx, [rbp+57h+var_48]
0x18009fd90  mov     rcx, rdi
0x18009fd93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18009fd98  nop
0x18009fd99  lea     rcx, [rbp+57h+var_48]
0x18009fd9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009fda2  jmp     short loc_18009FDB4
0x18009fda4  lea     rdx, dword_180100DC4
0x18009fdab  mov     rcx, rdi
0x18009fdae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009fdb3  nop
0x18009fdb4  lea     rcx, [rbp+57h+var_68]
0x18009fdb8  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18009fdbd  mov     rax, rdi
0x18009fdc0  mov     rcx, [rbp+57h+var_28]
0x18009fdc4  xor     rcx, rsp; StackCookie
0x18009fdc7  call    __security_check_cookie
0x18009fdcc  mov     rbx, [rsp+0B0h+arg_18]
0x18009fdd4  add     rsp, 90h
0x18009fddb  pop     r15
0x18009fddd  pop     r14
0x18009fddf  pop     rdi
0x18009fde0  pop     rsi
0x18009fde1  pop     rbp
0x18009fde2  retn
```
