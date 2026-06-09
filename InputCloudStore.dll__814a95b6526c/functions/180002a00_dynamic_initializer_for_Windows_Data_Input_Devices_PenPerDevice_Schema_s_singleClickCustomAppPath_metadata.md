# _dynamic_initializer_for__Windows::Data::Input::Devices::PenPerDevice::Schema::s_singleClickCustomAppPath_metadata__

- ea: `0x180002a00`
- end: `0x180002a40`
- name: `_dynamic_initializer_for__Windows::Data::Input::Devices::PenPerDevice::Schema::s_singleClickCustomAppPath_metadata__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003910`
- `0x18002cdd8`
- `0x18002cf28`
- `0x18002dbb0`

## string_xrefs

- `0x180002a12`: `singleClickCustomAppPath`

## pseudocode

```c
int dynamic_initializer_for__Windows::Data::Input::Devices::PenPerDevice::Schema::s_singleClickCustomAppPath_metadata__()
{
  __int64 v0; // rax
  __int64 v1; // r8
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF

  v0 = std::map<std::string,std::string>::map<std::string,std::string>((__int64)v3);
  bond::reflection::MetadataInit(
    Windows::Data::Input::Devices::PenPerDevice::Schema::s_singleClickCustomAppPath_metadata,
    "singleClickCustomAppPath",
    v1,
    v0);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(v3);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::Data::Input::Devices::PenPerDevice::Schema::s_singleClickCustomAppPath_metadata__);
}

```

## disassembly

```asm
0x180002a00  sub     rsp, 38h
0x180002a04  lea     rcx, [rsp+38h+var_18]
0x180002a09  call    ??0?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::string,std::string>::map<std::string,std::string>(void)
0x180002a0e  nop
0x180002a0f  mov     r9, rax
0x180002a12  lea     rdx, aSingleclickcus_0; "singleClickCustomAppPath"
0x180002a19  lea     rcx, ?s_singleClickCustomAppPath_metadata@Schema@PenPerDevice@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::PenPerDevice::Schema::s_singleClickCustomAppPath_metadata
0x180002a20  call    ?MetadataInit@reflection@bond@@YA?AUMetadata@2@PEBDW4Modifier@4_bond_enumerators@2@AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@Z; bond::reflection::MetadataInit(char const *,bond::_bond_enumerators::Modifier::Modifier,std::map<std::string,std::string> const &)
0x180002a25  nop
0x180002a26  lea     rcx, [rsp+38h+var_18]
0x180002a2b  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x180002a30  lea     rcx, _dynamic_atexit_destructor_for__Windows__Data__Input__Devices__PenPerDevice__Schema__s_singleClickCustomAppPath_metadata__
0x180002a37  add     rsp, 38h
0x180002a3b  jmp     atexit
```
