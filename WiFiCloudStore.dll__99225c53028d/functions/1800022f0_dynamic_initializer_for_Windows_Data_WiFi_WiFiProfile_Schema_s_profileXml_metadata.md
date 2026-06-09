# _dynamic_initializer_for__Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata__

- ea: `0x1800022f0`
- end: `0x180002358`
- name: `_dynamic_initializer_for__Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata__`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ae1c`
- `0x18000c38c`
- `0x18000c544`
- `0x180025308`
- `0x18002a3e0`

## string_xrefs

- `0x18000230d`: `profileXml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int dynamic_initializer_for__Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata__()
{
  __int64 v0; // r8
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  v2 = 0;
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Alloc_sentinel_and_proxy(&v2);
  bond::reflection::MetadataInit(Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata, "profileXml", v0, &v2);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>>>(
    (__int64)&v2,
    (__int64)&v2,
    *(char **)(v2 + 8));
  std::_Deallocate<16>((void *)v2, 0x60u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata__);
}

```

## disassembly

```asm
0x1800022f0  sub     rsp, 38h
0x1800022f4  xorps   xmm0, xmm0
0x1800022f7  movdqu  [rsp+38h+var_18], xmm0
0x1800022fd  lea     rcx, [rsp+38h+var_18]
0x180002302  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180002307  nop
0x180002308  lea     r9, [rsp+38h+var_18]
0x18000230d  lea     rdx, aProfilexml; "profileXml"
0x180002314  lea     rcx, ?s_profileXml_metadata@Schema@WiFiProfile@WiFi@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::WiFi::WiFiProfile::Schema::s_profileXml_metadata
0x18000231b  call    ?MetadataInit@reflection@bond@@YA?AUMetadata@2@PEBDW4Modifier@4_bond_enumerators@2@AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@Z; bond::reflection::MetadataInit(char const *,bond::_bond_enumerators::Modifier::Modifier,std::map<std::string,std::string> const &)
0x180002320  nop
0x180002321  mov     r8, qword ptr [rsp+38h+var_18]
0x180002326  mov     r8, [r8+8]
0x18000232a  lea     rdx, [rsp+38h+var_18]
0x18000232f  lea     rcx, [rsp+38h+var_18]
0x180002334  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>> &,std::_Tree_node<std::pair<std::string const,std::string>,void *> *)
0x180002339  mov     edx, 60h ; '`'
0x18000233e  mov     rcx, qword ptr [rsp+38h+var_18]
0x180002343  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180002348  lea     rcx, _dynamic_atexit_destructor_for__Windows__Data__WiFi__WiFiProfile__Schema__s_profileXml_metadata__
0x18000234f  add     rsp, 38h
0x180002353  jmp     atexit
```
