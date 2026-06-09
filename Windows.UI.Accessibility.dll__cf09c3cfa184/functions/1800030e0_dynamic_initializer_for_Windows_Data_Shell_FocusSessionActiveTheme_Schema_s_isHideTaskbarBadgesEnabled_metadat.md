# _dynamic_initializer_for__Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarBadgesEnabled_metadata__

- ea: `0x1800030e0`
- end: `0x180003123`
- name: `_dynamic_initializer_for__Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarBadgesEnabled_metadata__`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003e70`
- `0x180030a48`
- `0x180030b98`
- `0x1800310a4`

## string_xrefs

- `0x1800030f5`: `isHideTaskbarBadgesEnabled`

## pseudocode

```c
int dynamic_initializer_for__Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarBadgesEnabled_metadata__()
{
  __int64 v0; // rax
  _BYTE v2[24]; // [rsp+20h] [rbp-18h] BYREF

  v0 = std::map<std::string,std::string>::map<std::string,std::string>(v2);
  bond::reflection::MetadataInit(
    Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarBadgesEnabled_metadata,
    "isHideTaskbarBadgesEnabled",
    0,
    v0);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(v2);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarBadgesEnabled_metadata__);
}

```

## disassembly

```asm
0x1800030e0  sub     rsp, 38h
0x1800030e4  lea     rcx, [rsp+38h+var_18]
0x1800030e9  call    ??0?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::string,std::string>::map<std::string,std::string>(void)
0x1800030ee  nop
0x1800030ef  mov     r9, rax
0x1800030f2  xor     r8d, r8d
0x1800030f5  lea     rdx, aIshidetaskbarb; "isHideTaskbarBadgesEnabled"
0x1800030fc  lea     rcx, ?s_isHideTaskbarBadgesEnabled_metadata@Schema@FocusSessionActiveTheme@Shell@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Shell::FocusSessionActiveTheme::Schema::s_isHideTaskbarBadgesEnabled_metadata
0x180003103  call    ?MetadataInit@reflection@bond@@YA?AUMetadata@2@PEBDW4Modifier@4_bond_enumerators@2@AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@Z; bond::reflection::MetadataInit(char const *,bond::_bond_enumerators::Modifier::Modifier,std::map<std::string,std::string> const &)
0x180003108  nop
0x180003109  lea     rcx, [rsp+38h+var_18]
0x18000310e  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x180003113  lea     rcx, _dynamic_atexit_destructor_for__Windows__Data__Shell__FocusSessionActiveTheme__Schema__s_isHideTaskbarBadgesEnabled_metadata__
0x18000311a  add     rsp, 38h
0x18000311e  jmp     atexit
```
