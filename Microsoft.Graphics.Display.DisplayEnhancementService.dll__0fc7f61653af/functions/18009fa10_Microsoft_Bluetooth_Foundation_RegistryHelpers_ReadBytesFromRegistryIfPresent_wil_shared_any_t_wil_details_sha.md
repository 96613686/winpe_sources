# Microsoft::Bluetooth::Foundation::RegistryHelpers::ReadBytesFromRegistryIfPresent<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>>(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009fa10`
- end: `0x18009fb79`
- name: `??$ReadBytesFromRegistryIfPresent@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@RegistryHelpers@Foundation@Bluetooth@Microsoft@@SA?AV?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@1@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(_QWORD *, HKEY **, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b1904`

## callees

- `0x1800058bc`
- `0x18000fa0c`
- `0x180013578`
- `0x18009f9dc`
- `0x18009fa10`
- `0x1800a16c4`
- `0x1800a919c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009fa74`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009fb0c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009fa74`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009fb0c`

## string_xrefs

- `0x18009fb2b`: `onecore\private\drivers\inc\bluetooth\foundation\RegistryHelpers.h`
- `0x18009fb67`: `onecore\private\drivers\inc\bluetooth\foundation\RegistryHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Microsoft::Bluetooth::Foundation::RegistryHelpers::ReadBytesFromRegistryIfPresent<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>>(
        _QWORD *a1,
        HKEY **a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rax
  __int64 v9; // rdx
  const WCHAR *v10; // rax
  HKEY **v11; // rdx
  const WCHAR *v12; // r8
  HKEY v13; // rcx
  unsigned int ValueW; // eax
  _QWORD *v15; // rbx
  __int64 v16; // rdx
  _QWORD *v17; // rbx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rdx
  const WCHAR *v21; // rax
  void *pvData; // rdx
  const WCHAR *v23; // r8
  HKEY v24; // rcx
  unsigned int v25; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-30h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  DWORD pcbData; // [rsp+98h] [rbp+48h] BYREF
  _QWORD *v31; // [rsp+A0h] [rbp+50h] BYREF
  _QWORD *v32; // [rsp+A8h] [rbp+58h] BYREF

  pcbData = 0;
  v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4, a2, a3);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v9, v8);
  if ( *v11 )
    v13 = **v11;
  else
    v13 = 0;
  ValueW = RegGetValueW(v13, v10, v12, 8u, 0, 0, &pcbData);
  v31 = 0;
  if ( ValueW )
  {
    if ( ValueW != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\RegistryHelpers.h",
        (const char *)ValueW,
        pdwType);
    goto LABEL_13;
  }
  v15 = operator new(0x18u);
  v32 = v15;
  v16 = pcbData;
  *v15 = 0;
  v15[1] = 0;
  v15[2] = 0;
  std::vector<unsigned char>::_Construct_n<>(v15, v16);
  v32 = v15;
  std::unique_ptr<std::vector<unsigned char>>::operator=<std::default_delete<std::vector<unsigned char>>,0>(
    (__int64 *)&v31,
    (__int64 *)&v32);
  std::unique_ptr<std::vector<unsigned char>>::~unique_ptr<std::vector<unsigned char>>(&v32);
  v17 = v31;
  v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4, *v31, v18);
  v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v20, v19);
  if ( *a2 )
    v24 = **a2;
  else
    v24 = 0;
  v25 = RegGetValueW(v24, v21, v23, 8u, 0, pvData, &pcbData);
  if ( v25 )
  {
    if ( v25 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1DF,
        (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\RegistryHelpers.h",
        (const char *)v25,
        pdwTypea);
LABEL_13:
    *a1 = 0;
    goto LABEL_14;
  }
  v31 = 0;
  *a1 = v17;
LABEL_14:
  std::unique_ptr<std::vector<unsigned char>>::~unique_ptr<std::vector<unsigned char>>(&v31);
  return a1;
}

```

## disassembly

```asm
0x18009fa10  push    rbp
0x18009fa12  push    rbx
0x18009fa13  push    rsi
0x18009fa14  push    rdi
0x18009fa15  push    r12
0x18009fa17  push    r14
0x18009fa19  push    r15
0x18009fa1b  mov     rbp, rsp
0x18009fa1e  sub     rsp, 50h
0x18009fa22  mov     rsi, r9
0x18009fa25  mov     r14, r8
0x18009fa28  mov     r15, rdx
0x18009fa2b  mov     rdi, rcx
0x18009fa2e  xor     r12d, r12d
0x18009fa31  mov     [rbp+arg_8], r12d
0x18009fa35  mov     rcx, r9
0x18009fa38  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009fa3d  mov     r8, rax
0x18009fa40  mov     rcx, r14
0x18009fa43  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009fa48  mov     rcx, [rdx]
0x18009fa4b  test    rcx, rcx
0x18009fa4e  jz      short loc_18009FA55
0x18009fa50  mov     rcx, [rcx]
0x18009fa53  jmp     short loc_18009FA58
0x18009fa55  mov     rcx, r12; hkey
0x18009fa58  lea     rdx, [rbp+arg_8]
0x18009fa5c  mov     [rsp+50h+pcbData], rdx; pcbData
0x18009fa61  mov     [rsp+50h+pvData], r12; pvData
0x18009fa66  mov     [rsp+50h+pdwType], r12; unsigned int
0x18009fa6b  mov     r9d, 8; dwFlags
0x18009fa71  mov     rdx, rax; lpSubKey
0x18009fa74  call    cs:__imp_RegGetValueW
0x18009fa7a  mov     [rbp+arg_10], r12
0x18009fa7e  test    eax, eax
0x18009fa80  jnz     loc_18009FB3D
0x18009fa86  lea     ecx, [rax+18h]; Size
0x18009fa89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009fa8e  mov     rbx, rax
0x18009fa91  mov     [rbp+arg_18], rax
0x18009fa95  mov     edx, [rbp+arg_8]
0x18009fa98  mov     [rax], r12
0x18009fa9b  mov     [rax+8], r12
0x18009fa9f  mov     [rax+10h], r12
0x18009faa3  mov     rcx, rax
0x18009faa6  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x18009faab  nop
0x18009faac  mov     [rbp+arg_18], rbx
0x18009fab0  lea     rdx, [rbp+arg_18]
0x18009fab4  lea     rcx, [rbp+arg_10]
0x18009fab8  call    ??$?4U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@std@@$0A@@?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<std::vector<uchar>>::operator=<std::default_delete<std::vector<uchar>>,0>(std::unique_ptr<std::vector<uchar>> &&)
0x18009fabd  lea     rcx, [rbp+arg_18]
0x18009fac1  call    ??1?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<uchar>>::~unique_ptr<std::vector<uchar>>(void)
0x18009fac6  mov     rbx, [rbp+arg_10]
0x18009faca  mov     rdx, [rbx]
0x18009facd  mov     rcx, rsi
0x18009fad0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009fad5  mov     r8, rax
0x18009fad8  mov     rcx, r14
0x18009fadb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009fae0  mov     rcx, [r15]
0x18009fae3  test    rcx, rcx
0x18009fae6  jz      short loc_18009FAED
0x18009fae8  mov     rcx, [rcx]
0x18009faeb  jmp     short loc_18009FAF0
0x18009faed  mov     rcx, r12; hkey
0x18009faf0  lea     r10, [rbp+arg_8]
0x18009faf4  mov     [rsp+50h+pcbData], r10; pcbData
0x18009faf9  mov     [rsp+50h+pvData], rdx; pvData
0x18009fafe  mov     [rsp+50h+pdwType], r12; unsigned int
0x18009fb03  mov     r9d, 8; dwFlags
0x18009fb09  mov     rdx, rax; lpSubKey
0x18009fb0c  call    cs:__imp_RegGetValueW
0x18009fb12  test    eax, eax
0x18009fb14  jnz     short loc_18009FB1F
0x18009fb16  mov     [rbp+arg_10], r12
0x18009fb1a  mov     [rdi], rbx
0x18009fb1d  jmp     short loc_18009FB45
0x18009fb1f  cmp     eax, 2
0x18009fb22  jz      short loc_18009FB42
0x18009fb24  mov     rcx, [rbp+38h]; this
0x18009fb28  mov     r9d, eax; char *
0x18009fb2b  lea     r8, aOnecorePrivate; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18009fb32  mov     edx, 1DFh; void *
0x18009fb37  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009fb3d  cmp     eax, 2
0x18009fb40  jnz     short loc_18009FB60
0x18009fb42  mov     [rdi], r12
0x18009fb45  lea     rcx, [rbp+arg_10]
0x18009fb49  call    ??1?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<uchar>>::~unique_ptr<std::vector<uchar>>(void)
0x18009fb4e  mov     rax, rdi
0x18009fb51  add     rsp, 50h
0x18009fb55  pop     r15
0x18009fb57  pop     r14
0x18009fb59  pop     r12
0x18009fb5b  pop     rdi
0x18009fb5c  pop     rsi
0x18009fb5d  pop     rbx
0x18009fb5e  pop     rbp
0x18009fb5f  retn
0x18009fb60  mov     rcx, [rbp+38h]; this
0x18009fb64  mov     r9d, eax; char *
0x18009fb67  lea     r8, aOnecorePrivate; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18009fb6e  mov     edx, 1C9h; void *
0x18009fb73  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
