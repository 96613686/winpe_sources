# Microsoft::Bluetooth::Foundation::RegistryHelpers::ReadStringFromRegistryIfPresent<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18007f048`
- end: `0x18007f214`
- name: `??$ReadStringFromRegistryIfPresent@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@RegistryHelpers@Foundation@Bluetooth@Microsoft@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV45@@Z`
- size: `460`
- prototype: `__int64 __fastcall(__int64, HKEY *, __int64)`
- caller_count: `10`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180085b18`
- `0x180085bd8`
- `0x180085d84`
- `0x1800860fc`
- `0x18008647c`
- `0x1800867fc`
- `0x180086b4c`
- `0x180086ea0`
- `0x18008e914`
- `0x180091e74`

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
- `0x18007f048`
- `0x1800828f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007f0bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007f183`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007f0bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007f183`

## string_xrefs

- `0x18007f0e4`: `onecore\private\drivers\inc\bluetooth\foundation\RegistryHelpers.h`
- `0x18007f194`: `onecore\private\drivers\inc\bluetooth\foundation\RegistryHelpers.h`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Foundation::RegistryHelpers::ReadStringFromRegistryIfPresent<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(
        __int64 a1,
        HKEY *a2,
        __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  const WCHAR *v8; // rax
  unsigned int ValueW; // eax
  __int64 v10; // r8
  char *v11; // rsi
  unsigned __int64 v12; // rcx
  char *v13; // rax
  size_t v14; // rbx
  const WCHAR *v15; // rax
  PVOID pvData; // rdx
  unsigned int v17; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-39h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-39h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v22; // [rsp+48h] [rbp-11h] BYREF
  void *v23; // [rsp+50h] [rbp-9h]
  __int64 v24; // [rsp+58h] [rbp-1h]
  _BYTE v25[32]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  pcbData[1] = HIDWORD(a1);
  pcbData[0] = 0;
  std::vector<unsigned short>::vector<unsigned short>(&v22, 0);
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v6, v7);
  ValueW = RegGetValueW(*a2, 0, v8, 2u, 0, 0, pcbData);
  if ( ValueW == 2 || !pcbData[0] )
  {
    std::wstring::wstring(a1, &dword_180100DC4);
    goto LABEL_16;
  }
  if ( ValueW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\RegistryHelpers.h",
      (const char *)ValueW,
      pdwType);
  v11 = (char *)v23;
  v12 = ((__int64)v23 - v22) >> 1;
  if ( pcbData[0] < v12 )
  {
    v13 = (char *)(v22 + 2LL * pcbData[0]);
LABEL_11:
    v23 = v13;
    goto LABEL_12;
  }
  if ( pcbData[0] > v12 )
  {
    if ( pcbData[0] <= (unsigned __int64)((v24 - v22) >> 1) )
    {
      v14 = 2 * (pcbData[0] - v12);
      memset_0(v23, 0, v14);
      v13 = &v11[v14];
      goto LABEL_11;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&v22, pcbData[0]);
  }
LABEL_12:
  v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v22, v10);
  v17 = RegGetValueW(*a2, 0, v15, 2u, 0, pvData, pcbData);
  if ( v17 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\RegistryHelpers.h",
      (const char *)v17,
      pdwTypea);
  std::wstring::wstring(v25);
  std::wstring::assign(v25, v22);
  std::wstring::wstring(a1, v25);
  std::wstring::_Tidy_deallocate(v25);
LABEL_16:
  std::vector<unsigned short>::_Tidy(&v22);
  return a1;
}

```

## disassembly

```asm
0x18007f048  mov     [rsp-8+arg_18], rbx
0x18007f04d  push    rbp
0x18007f04e  push    rsi
0x18007f04f  push    rdi
0x18007f050  push    r14
0x18007f052  push    r15
0x18007f054  lea     rbp, [rsp-37h]
0x18007f059  sub     rsp, 90h
0x18007f060  mov     rax, cs:__security_cookie
0x18007f067  xor     rax, rsp
0x18007f06a  mov     [rbp+57h+var_28], rax
0x18007f06e  mov     r15, r8
0x18007f071  mov     r14, rdx
0x18007f074  mov     rdi, rcx
0x18007f077  mov     qword ptr [rbp+57h+var_70], rcx
0x18007f07b  mov     [rbp+57h+var_70], 0
0x18007f082  xor     edx, edx
0x18007f084  lea     rcx, [rbp+57h+var_68]
0x18007f088  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18007f08d  nop
0x18007f08e  mov     rcx, r15
0x18007f091  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f096  lea     rcx, [rbp+57h+var_70]
0x18007f09a  mov     [rsp+0B0h+pcbData], rcx; pcbData
0x18007f09f  mov     [rsp+0B0h+pvData], 0; pvData
0x18007f0a8  mov     [rsp+0B0h+pdwType], 0; unsigned int
0x18007f0b1  mov     r9d, 2; dwFlags
0x18007f0b7  mov     r8, rax; lpValue
0x18007f0ba  xor     edx, edx; lpSubKey
0x18007f0bc  mov     rcx, [r14]; hkey
0x18007f0bf  call    cs:__imp_RegGetValueW
0x18007f0c5  cmp     eax, 2
0x18007f0c8  jz      loc_18007F1D5
0x18007f0ce  mov     ecx, [rbp+57h+var_70]
0x18007f0d1  test    ecx, ecx
0x18007f0d3  jz      loc_18007F1D5
0x18007f0d9  mov     r10, [rbp+5Fh]
0x18007f0dd  test    eax, eax
0x18007f0df  jz      short loc_18007F0F9
0x18007f0e1  mov     r9d, eax; char *
0x18007f0e4  lea     r8, aOnecorePrivate; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18007f0eb  mov     edx, 19Ah; void *
0x18007f0f0  mov     rcx, r10; this
0x18007f0f3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007f0f9  mov     rbx, rcx
0x18007f0fc  mov     rdx, [rbp+57h+var_68]
0x18007f100  mov     rsi, [rbp+57h+var_60]
0x18007f104  mov     rcx, rsi
0x18007f107  sub     rcx, rdx
0x18007f10a  sar     rcx, 1
0x18007f10d  cmp     rbx, rcx
0x18007f110  jnb     short loc_18007F118
0x18007f112  lea     rax, [rdx+rbx*2]
0x18007f116  jmp     short loc_18007F14E
0x18007f118  jbe     short loc_18007F152
0x18007f11a  mov     rax, [rbp+57h+var_58]
0x18007f11e  sub     rax, rdx
0x18007f121  sar     rax, 1
0x18007f124  cmp     rbx, rax
0x18007f127  jbe     short loc_18007F137
0x18007f129  mov     rdx, rbx
0x18007f12c  lea     rcx, [rbp+57h+var_68]
0x18007f130  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18007f135  jmp     short loc_18007F152
0x18007f137  sub     rbx, rcx
0x18007f13a  add     rbx, rbx
0x18007f13d  mov     r8, rbx; Size
0x18007f140  xor     edx, edx; Val
0x18007f142  mov     rcx, rsi; void *
0x18007f145  call    memset_0
0x18007f14a  lea     rax, [rbx+rsi]
0x18007f14e  mov     [rbp+57h+var_60], rax
0x18007f152  mov     rdx, [rbp+57h+var_68]
0x18007f156  mov     rcx, r15
0x18007f159  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007f15e  lea     rcx, [rbp+57h+var_70]
0x18007f162  mov     [rsp+0B0h+pcbData], rcx; pcbData
0x18007f167  mov     [rsp+0B0h+pvData], rdx; pvData
0x18007f16c  mov     [rsp+0B0h+pdwType], 0; unsigned int
0x18007f175  mov     r9d, 2; dwFlags
0x18007f17b  mov     r8, rax; lpValue
0x18007f17e  xor     edx, edx; lpSubKey
0x18007f180  mov     rcx, [r14]; hkey
0x18007f183  call    cs:__imp_RegGetValueW
0x18007f189  mov     rcx, [rbp+5Fh]; this
0x18007f18d  test    eax, eax
0x18007f18f  jz      short loc_18007F1A6
0x18007f191  mov     r9d, eax; char *
0x18007f194  lea     r8, aOnecorePrivate; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18007f19b  mov     edx, 1A4h; void *
0x18007f1a0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007f1a6  lea     rcx, [rbp+57h+var_48]
0x18007f1aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007f1af  nop
0x18007f1b0  mov     rdx, [rbp+57h+var_68]
0x18007f1b4  lea     rcx, [rbp+57h+var_48]
0x18007f1b8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18007f1bd  lea     rdx, [rbp+57h+var_48]
0x18007f1c1  mov     rcx, rdi
0x18007f1c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18007f1c9  nop
0x18007f1ca  lea     rcx, [rbp+57h+var_48]
0x18007f1ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007f1d3  jmp     short loc_18007F1E5
0x18007f1d5  lea     rdx, dword_180100DC4
0x18007f1dc  mov     rcx, rdi
0x18007f1df  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007f1e4  nop
0x18007f1e5  lea     rcx, [rbp+57h+var_68]
0x18007f1e9  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18007f1ee  mov     rax, rdi
0x18007f1f1  mov     rcx, [rbp+57h+var_28]
0x18007f1f5  xor     rcx, rsp; StackCookie
0x18007f1f8  call    __security_check_cookie
0x18007f1fd  mov     rbx, [rsp+0B0h+arg_18]
0x18007f205  add     rsp, 90h
0x18007f20c  pop     r15
0x18007f20e  pop     r14
0x18007f210  pop     rdi
0x18007f211  pop     rsi
0x18007f212  pop     rbp
0x18007f213  retn
```
