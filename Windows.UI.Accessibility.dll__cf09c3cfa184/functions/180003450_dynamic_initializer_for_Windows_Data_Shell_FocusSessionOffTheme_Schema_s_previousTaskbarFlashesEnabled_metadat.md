# _dynamic_initializer_for__Windows::Data::Shell::FocusSessionOffTheme::Schema::s_previousTaskbarFlashesEnabled_metadata__

- ea: `0x180003450`
- end: `0x180003493`
- name: `_dynamic_initializer_for__Windows::Data::Shell::FocusSessionOffTheme::Schema::s_previousTaskbarFlashesEnabled_metadata__`
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

- `0x180003465`: `previousTaskbarFlashesEnabled`

## pseudocode

```c
int dynamic_initializer_for__Windows::Data::Shell::FocusSessionOffTheme::Schema::s_previousTaskbarFlashesEnabled_metadata__()
{
  __int64 v0; // rax
  _BYTE v2[24]; // [rsp+20h] [rbp-18h] BYREF

  v0 = std::map<std::string,std::string>::map<std::string,std::string>(v2);
  bond::reflection::MetadataInit(
    Windows::Data::Shell::FocusSessionOffTheme::Schema::s_previousTaskbarFlashesEnabled_metadata,
    "previousTaskbarFlashesEnabled",
    0,
    v0);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(v2);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::Data::Shell::FocusSessionOffTheme::Schema::s_previousTaskbarFlashesEnabled_metadata__);
}

```

## disassembly

```asm
0x180003450  sub     rsp, 38h
0x180003454  lea     rcx, [rsp+38h+var_18]
0x180003459  call    ??0?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::string,std::string>::map<std::string,std::string>(void)
0x18000345e  nop
0x18000345f  mov     r9, rax
0x180003462  xor     r8d, r8d
0x180003465  lea     rdx, aPrevioustaskba_0; "previousTaskbarFlashesEnabled"
0x18000346c  lea     rcx, ?s_previousTaskbarFlashesEnabled_metadata@Schema@FocusSessionOffTheme@Shell@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Shell::FocusSessionOffTheme::Schema::s_previousTaskbarFlashesEnabled_metadata
0x180003473  call    ?MetadataInit@reflection@bond@@YA?AUMetadata@2@PEBDW4Modifier@4_bond_enumerators@2@AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@Z; bond::reflection::MetadataInit(char const *,bond::_bond_enumerators::Modifier::Modifier,std::map<std::string,std::string> const &)
0x180003478  nop
0x180003479  lea     rcx, [rsp+38h+var_18]
0x18000347e  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x180003483  lea     rcx, _dynamic_atexit_destructor_for__Windows__Data__Shell__FocusSessionOffTheme__Schema__s_previousTaskbarFlashesEnabled_metadata__
0x18000348a  add     rsp, 38h
0x18000348e  jmp     atexit
```
