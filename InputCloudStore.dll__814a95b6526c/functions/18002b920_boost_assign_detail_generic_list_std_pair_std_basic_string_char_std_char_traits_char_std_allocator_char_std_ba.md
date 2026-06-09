# boost::assign_detail::generic_list<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>::operator()<char [30],char [16]>(char const (&)[30],char const (&)[16])

- ea: `0x18002b920`
- end: `0x18002b970`
- name: `??$?R$$BY0BO@D$$BY0BA@D@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@QEAAAEAV012@AEAY0BO@$$CBDAEAY0BA@$$CBD@Z`
- size: `80`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d29c`
- `0x18002d644`
- `0x18002d840`
- `0x18002d920`

## callees

- `0x180019bd8`
- `0x18002e374`

## string_xrefs

- `0x18002b948`: `CopyRestoreData`

## pseudocode

```c
__int64 __fastcall boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator()<char [30],char [16]>(
        __int64 a1)
{
  _BYTE v3[32]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v4[40]; // [rsp+40h] [rbp-28h] BYREF

  std::string::string(v3, "CloudData.BackupRestorePolicy");
  std::string::string(v4, "CopyRestoreData");
  boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(a1, v3);
  return a1;
}

```

## disassembly

```asm
0x18002b920  mov     r11, rsp
0x18002b923  mov     [r11+18h], r8
0x18002b927  push    rbx
0x18002b928  sub     rsp, 60h
0x18002b92c  mov     rbx, rcx
0x18002b92f  lea     rax, [r11-48h]
0x18002b933  mov     [r11+18h], rax
0x18002b937  lea     rdx, aClouddataBacku; "CloudData.BackupRestorePolicy"
0x18002b93e  lea     rcx, [r11-48h]
0x18002b942  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002b947  nop
0x18002b948  lea     rdx, aCopyrestoredat; "CopyRestoreData"
0x18002b94f  lea     rcx, [rsp+68h+var_28]
0x18002b954  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002b959  nop
0x18002b95a  lea     rdx, [rsp+68h+var_48]
0x18002b95f  mov     rcx, rbx
0x18002b962  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(std::pair<std::string,std::string>)
0x18002b967  mov     rax, rbx
0x18002b96a  add     rsp, 60h
0x18002b96e  pop     rbx
0x18002b96f  retn
```
