# boost::assign_detail::generic_list<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::operator()<char [20],char [49]>(char const (&)[20],char const (&)[49])

- ea: `0x18002b8c8`
- end: `0x18002b918`
- name: `??$?R$$BY0BE@D$$BY0DB@D@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@QEAAAEAV012@AEAY0BE@$$CBDAEAY0DB@$$CBD@Z`
- size: `80`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d29c`
- `0x18002d644`
- `0x18002d840`
- `0x18002d920`

## callees

- `0x180019bd8`
- `0x18002e374`

## string_xrefs

- `0x18002b8f0`: `MicrosoftDevice.Default.InputWelcomebackSettings`

## pseudocode

```c
__int64 __fastcall boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator()<char [20],char [49]>(
        __int64 a1)
{
  _BYTE v3[32]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v4[40]; // [rsp+40h] [rbp-28h] BYREF

  std::string::string(v3, "CloudData.SyncGroup");
  std::string::string(v4, "MicrosoftDevice.Default.InputWelcomebackSettings");
  boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(a1, v3);
  return a1;
}

```

## disassembly

```asm
0x18002b8c8  mov     r11, rsp
0x18002b8cb  mov     [r11+18h], r8
0x18002b8cf  push    rbx
0x18002b8d0  sub     rsp, 60h
0x18002b8d4  mov     rbx, rcx
0x18002b8d7  lea     rax, [r11-48h]
0x18002b8db  mov     [r11+18h], rax
0x18002b8df  lea     rdx, aClouddataSyncg; "CloudData.SyncGroup"
0x18002b8e6  lea     rcx, [r11-48h]
0x18002b8ea  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002b8ef  nop
0x18002b8f0  lea     rdx, aMicrosoftdevic; "MicrosoftDevice.Default.InputWelcomebac"...
0x18002b8f7  lea     rcx, [rsp+68h+var_28]
0x18002b8fc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002b901  nop
0x18002b902  lea     rdx, [rsp+68h+var_48]
0x18002b907  mov     rcx, rbx
0x18002b90a  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(std::pair<std::string,std::string>)
0x18002b90f  mov     rax, rbx
0x18002b912  add     rsp, 60h
0x18002b916  pop     rbx
0x18002b917  retn
```
