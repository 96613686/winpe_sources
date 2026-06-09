# std::_Tree<std::_Tmap_traits<std::type_index,std::shared_ptr<Spectre::Engine::SceneCustomData>,std::less<std::type_index>,std::allocator<std::pair<std::type_index const,std::shared_ptr<Spectre::Engine::SceneCustomData>>>,0>>::_Lower_bound_duplicate<std::type_index>(std::_Tree_node<std::pair<std::type_index const,std::shared_ptr<Spectre::Engine::SceneCustomData>>,void *> * const,std::type_index const &)

- ea: `0x18002e11c`
- end: `0x18002e14a`
- name: `??$_Lower_bound_duplicate@Vtype_index@std@@@?$_Tree@V?$_Tmap_traits@Vtype_index@std@@V?$shared_ptr@USceneCustomData@Engine@Spectre@@@2@U?$less@Vtype_index@std@@@2@V?$allocator@U?$pair@$$CBVtype_index@std@@V?$shared_ptr@USceneCustomData@Engine@Spectre@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVtype_index@std@@V?$shared_ptr@USceneCustomData@Engine@Spectre@@@2@@std@@PEAX@1@AEBVtype_index@1@@Z`
- size: `46`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d60c`
- `0x18002e3a4`
- `0x180036de8`

## callees

- `0x18002e11c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002e135`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002e135`

## pseudocode

```c
bool __fastcall std::_Tree<std::_Tmap_traits<std::type_index,std::shared_ptr<Spectre::Engine::SceneCustomData>,std::less<std::type_index>,std::allocator<std::pair<std::type_index const,std::shared_ptr<Spectre::Engine::SceneCustomData>>>,0>>::_Lower_bound_duplicate<std::type_index>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  return !*(_BYTE *)(a2 + 25) && (int)__std_type_info_compare(*a3 + 8LL, *(_QWORD *)(a2 + 32) + 8LL) >= 0;
}

```

## disassembly

```asm
0x18002e11c  sub     rsp, 28h
0x18002e120  cmp     byte ptr [rdx+19h], 0
0x18002e124  jnz     short loc_18002E143
0x18002e126  mov     rdx, [rdx+20h]
0x18002e12a  mov     rcx, [r8]
0x18002e12d  add     rdx, 8
0x18002e131  add     rcx, 8
0x18002e135  call    cs:__imp___std_type_info_compare
0x18002e13b  test    eax, eax
0x18002e13d  js      short loc_18002E143
0x18002e13f  mov     al, 1
0x18002e141  jmp     short loc_18002E145
0x18002e143  xor     al, al
0x18002e145  add     rsp, 28h
0x18002e149  retn
```
