# std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>>,std::default_delete<std::set<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>>>>::~unique_ptr<std::set<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>>,std::default_delete<std::set<CodeIntegrity::Management::SiPolicyView,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyView>>>>(void)

- ea: `0x18000a324`
- end: `0x18000a33a`
- name: `??1?$unique_ptr@V?$set@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@@std@@@2@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ad4c`
- `0x180014ee0`
- `0x18002a2cf`
- `0x18002b880`

## callees

- `0x18000a324`
- `0x18000a6e4`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyView>>::~unique_ptr<std::set<CodeIntegrity::Management::SiPolicyView>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<std::set<CodeIntegrity::Management::SiPolicyView>>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000a324  sub     rsp, 28h
0x18000a328  mov     rdx, [rcx]
0x18000a32b  test    rdx, rdx
0x18000a32e  jz      short loc_18000A335
0x18000a330  call    ??R?$default_delete@V?$set@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@@std@@@std@@QEBAXPEAV?$set@VSiPolicyView@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VSiPolicyView@Management@CodeIntegrity@@@5@@1@@Z; std::default_delete<std::set<CodeIntegrity::Management::SiPolicyView>>::operator()(std::set<CodeIntegrity::Management::SiPolicyView> *)
0x18000a335  add     rsp, 28h
0x18000a339  retn
```
