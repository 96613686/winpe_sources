# AssignedAccessAdminHelperImpl::CreateBstrSafeArrayVector(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x140062b04`
- end: `0x140062c06`
- name: `?CreateBstrSafeArrayVector@AssignedAccessAdminHelperImpl@@AEAAPEAUtagSAFEARRAY@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140062f80`

## callees

- `0x140029eb8`
- `0x14002a2c0`
- `0x14002a2e0`
- `0x140062ac4`
- `0x140062ae4`
- `0x140062b04`
- `0x140063e9c`
- `0x140063ef4`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140062b5d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140062b5d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x140062b29`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x140062b29`

## string_xrefs

- `0x140062b3c`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`
- `0x140062b6e`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccessadminhelperimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
SAFEARRAY *__fastcall AssignedAccessAdminHelperImpl::CreateBstrSafeArrayVector(void *a1, __int64 *a2)
{
  SAFEARRAY *Vector; // rax
  const char *v4; // r9
  HRESULT v5; // eax
  __int64 v6; // rdi
  __int64 i; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  SAFEARRAY *v10; // rbx
  SAFEARRAY **v12; // [rsp+20h] [rbp-10h] BYREF
  char v13; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  void *ppvData; // [rsp+50h] [rbp+20h] BYREF
  SAFEARRAY *v16; // [rsp+58h] [rbp+28h] BYREF
  __int64 v17; // [rsp+60h] [rbp+30h] BYREF

  ppvData = a1;
  Vector = SafeArrayCreateVector(8u, 1, (a2[1] - *a2) >> 5);
  v16 = Vector;
  if ( !Vector )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xEC,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      v4);
  ppvData = 0;
  v5 = SafeArrayAccessData(Vector, &ppvData);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccessadminhelperimpl.cpp",
      (const char *)(unsigned int)v5,
      (int)v12);
  v12 = &v16;
  v13 = 1;
  v6 = a2[1];
  for ( i = *a2; i != v6; i += 32 )
  {
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
    wil::make_bstr(&v17, v8);
    v9 = v17;
    v17 = 0;
    *(_QWORD *)ppvData = v9;
    ppvData = (char *)ppvData + 8;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  }
  wil::details::lambda_call__lambda_4ef84a5b3a6043562d711a7c7c152ffe___::reset(&v12);
  v10 = v16;
  v16 = 0;
  wil::details::lambda_call__lambda_4ef84a5b3a6043562d711a7c7c152ffe___::reset(&v12);
  wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>(&v16);
  return v10;
}

```

## disassembly

```asm
0x140062b04  mov     [rsp-18h+ppvData], rcx
0x140062b09  push    rbp
0x140062b0a  push    rbx
0x140062b0b  push    rdi
0x140062b0c  mov     rbp, rsp
0x140062b0f  sub     rsp, 30h
0x140062b13  mov     rbx, rdx
0x140062b16  mov     r8, [rdx+8]
0x140062b1a  sub     r8, [rdx]
0x140062b1d  sar     r8, 5; cElements
0x140062b21  mov     ecx, 8; vt
0x140062b26  lea     edx, [rcx-7]; lLbound
0x140062b29  call    cs:__imp_SafeArrayCreateVector
0x140062b2f  mov     [rbp+arg_8], rax
0x140062b33  mov     rcx, [rbp+18h]; this
0x140062b37  test    rax, rax
0x140062b3a  jnz     short loc_140062B4E
0x140062b3c  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x140062b43  mov     edx, 0ECh; void *
0x140062b48  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140062b4e  mov     [rbp+ppvData], 0
0x140062b56  lea     rdx, [rbp+ppvData]; ppvData
0x140062b5a  mov     rcx, rax; psa
0x140062b5d  call    cs:__imp_SafeArrayAccessData
0x140062b63  mov     rcx, [rbp+18h]; this
0x140062b67  test    eax, eax
0x140062b69  jns     short loc_140062B80
0x140062b6b  mov     r9d, eax; char *
0x140062b6e  lea     r8, aPcshellShellSy_20; "pcshell\\shell\\systemsettings\\adminfl"...
0x140062b75  mov     edx, 0EEh; void *
0x140062b7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140062b80  lea     rax, [rbp+arg_8]
0x140062b84  mov     [rbp+var_10], rax
0x140062b88  mov     [rbp+var_8], 1
0x140062b8c  mov     rdi, [rbx+8]
0x140062b90  mov     rbx, [rbx]
0x140062b93  jmp     short loc_140062BCE
0x140062b95  mov     rcx, rbx
0x140062b98  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140062b9d  mov     rdx, rax
0x140062ba0  lea     rcx, [rbp+arg_10]
0x140062ba4  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x140062ba9  mov     rcx, [rbp+arg_10]
0x140062bad  mov     [rbp+arg_10], 0
0x140062bb5  mov     rax, [rbp+ppvData]
0x140062bb9  mov     [rax], rcx
0x140062bbc  add     [rbp+ppvData], 8
0x140062bc1  lea     rcx, [rbp+arg_10]
0x140062bc5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140062bca  add     rbx, 20h ; ' '
0x140062bce  cmp     rbx, rdi
0x140062bd1  jnz     short loc_140062B95
0x140062bd3  lea     rcx, [rbp+var_10]
0x140062bd7  call    wil__details__lambda_call__lambda_4ef84a5b3a6043562d711a7c7c152ffe_____reset
0x140062bdc  mov     rbx, [rbp+arg_8]
0x140062be0  mov     [rbp+arg_8], 0
0x140062be8  lea     rcx, [rbp+var_10]
0x140062bec  call    wil__details__lambda_call__lambda_4ef84a5b3a6043562d711a7c7c152ffe_____reset
0x140062bf1  nop
0x140062bf2  lea     rcx, [rbp+arg_8]
0x140062bf6  call    ??1?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>(void)
0x140062bfb  mov     rax, rbx
0x140062bfe  add     rsp, 30h
0x140062c02  pop     rdi
0x140062c03  pop     rbx
0x140062c04  pop     rbp
0x140062c05  retn
```
