# PrintCore::RegHelpers::OpenKey(HKEY__ * const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x18000af7c`
- end: `0x18000b028`
- name: `?OpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `172`
- prototype: `HKEY __fastcall(HKEY *, __int64, REGSAM)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800098d8`
- `0x1800193bc`
- `0x1800194dc`
- `0x18001a404`

## callees

- `0x180007468`
- `0x18000af7c`
- `0x18000e164`
- `0x18000e1ac`
- `0x18000e790`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000afc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000afc6`

## pseudocode

```c
HKEY __fastcall PrintCore::RegHelpers::OpenKey(HKEY *a1, __int64 a2, REGSAM a3)
{
  const WCHAR *v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  HKEY v9; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v13,
    0);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v7 = RegOpenKeyExW(*a1, v6, 0, a3, &v13);
  if ( v7 == 2 || v7 == 1018 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
    return 0;
  }
  else
  {
    if ( v7 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x30, v8, (const char *)v7, phkResult);
    v9 = v13;
    v13 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
    return v9;
  }
}

```

## disassembly

```asm
0x18000af7c  mov     rax, rsp
0x18000af7f  mov     [rax+10h], rbx
0x18000af83  mov     [rax+18h], rsi
0x18000af87  push    rdi
0x18000af88  sub     rsp, 30h
0x18000af8c  mov     edi, r8d
0x18000af8f  mov     rbx, rdx
0x18000af92  mov     rsi, rcx
0x18000af95  mov     qword ptr [rax+8], 0
0x18000af9d  xor     edx, edx
0x18000af9f  lea     rcx, [rax+8]
0x18000afa3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000afa8  mov     rcx, rbx
0x18000afab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000afb0  lea     rcx, [rsp+38h+arg_0]
0x18000afb5  mov     qword ptr [rsp+38h+phkResult], rcx; unsigned int
0x18000afba  mov     r9d, edi; samDesired
0x18000afbd  xor     r8d, r8d; ulOptions
0x18000afc0  mov     rdx, rax; lpSubKey
0x18000afc3  mov     rcx, [rsi]; hKey
0x18000afc6  call    cs:__imp_RegOpenKeyExW
0x18000afcc  cmp     eax, 2
0x18000afcf  jz      short loc_18000B00C
0x18000afd1  cmp     eax, 3FAh
0x18000afd6  jz      short loc_18000B00C
0x18000afd8  mov     rcx, [rsp+38h]; this
0x18000afdd  test    eax, eax
0x18000afdf  jz      short loc_18000AFEF
0x18000afe1  mov     r9d, eax; char *
0x18000afe4  mov     edx, 30h ; '0'; void *
0x18000afe9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000afef  mov     rbx, [rsp+38h+arg_0]
0x18000aff4  mov     [rsp+38h+arg_0], 0
0x18000affd  lea     rcx, [rsp+38h+arg_0]
0x18000b002  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000b007  mov     rax, rbx
0x18000b00a  jmp     short loc_18000B018
0x18000b00c  lea     rcx, [rsp+38h+arg_0]
0x18000b011  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000b016  xor     eax, eax
0x18000b018  mov     rbx, [rsp+38h+arg_8]
0x18000b01d  mov     rsi, [rsp+38h+arg_10]
0x18000b022  add     rsp, 30h
0x18000b026  pop     rdi
0x18000b027  retn
```
