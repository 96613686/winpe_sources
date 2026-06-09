# _dynamic_initializer_for__Windows::Data::Input::Devices::PenPerDevice::Schema::s_longPressCustomAppPath_metadata__

- ea: `0x1800026a0`
- end: `0x1800026e0`
- name: `_dynamic_initializer_for__Windows::Data::Input::Devices::PenPerDevice::Schema::s_longPressCustomAppPath_metadata__`
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

- `0x1800026b2`: `longPressCustomAppPath`

## pseudocode

```c
int dynamic_initializer_for__Windows::Data::Input::Devices::PenPerDevice::Schema::s_longPressCustomAppPath_metadata__()
{
  __int64 v0; // rax
  __int64 v1; // r8
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF

  v0 = std::map<std::string,std::string>::map<std::string,std::string>((__int64)v3);
  bond::reflection::MetadataInit(
    Windows::Data::Input::Devices::PenPerDevice::Schema::s_longPressCustomAppPath_metadata,
    "longPressCustomAppPath",
    v1,
    v0);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(v3);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::Data::Input::Devices::PenPerDevice::Schema::s_longPressCustomAppPath_metadata__);
}

```

## disassembly

```asm
0x1800026a0  sub     rsp, 38h
0x1800026a4  lea     rcx, [rsp+38h+var_18]
0x1800026a9  call    ??0?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::string,std::string>::map<std::string,std::string>(void)
0x1800026ae  nop
0x1800026af  mov     r9, rax
0x1800026b2  lea     rdx, aLongpresscusto_0; "longPressCustomAppPath"
0x1800026b9  lea     rcx, ?s_longPressCustomAppPath_metadata@Schema@PenPerDevice@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::PenPerDevice::Schema::s_longPressCustomAppPath_metadata
0x1800026c0  call    ?MetadataInit@reflection@bond@@YA?AUMetadata@2@PEBDW4Modifier@4_bond_enumerators@2@AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@Z; bond::reflection::MetadataInit(char const *,bond::_bond_enumerators::Modifier::Modifier,std::map<std::string,std::string> const &)
0x1800026c5  nop
0x1800026c6  lea     rcx, [rsp+38h+var_18]
0x1800026cb  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x1800026d0  lea     rcx, _dynamic_atexit_destructor_for__Windows__Data__Input__Devices__PenPerDevice__Schema__s_longPressCustomAppPath_metadata__
0x1800026d7  add     rsp, 38h
0x1800026db  jmp     atexit
```
