# SRCacheManager_DeleteContext

- ea: `0x18000d710`
- end: `0x18000d789`
- name: `SRCacheManager_DeleteContext`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000d710`
- `0x18000fa08`

## string_xrefs

- `0x18000d754`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`
- `0x18000d76d`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`
- `0x18000d73b`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheManager_DeleteContext(HKEY *a1, const unsigned __int16 *a2)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  int v6; // [rsp+20h] [rbp-8h]
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = Common::RegistryKey::DeleteSubKeyTree(a1, a2);
  v3 = v2;
  if ( v2 > -2147024895 && (unsigned int)(v2 + 2147024892) > 0x7FF8FFFB )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFC,
    (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
    (const char *)(unsigned int)v2,
    v5);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7B,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
    (const char *)v3,
    v6);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xEB,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
    (const char *)v3,
    v7);
  return v3;
}

```

## disassembly

```asm
0x18000d710  push    rbx; int
0x18000d712  sub     rsp, 20h
0x18000d716  call    ?DeleteSubKeyTree@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteSubKeyTree(ushort const *)
0x18000d71b  mov     ebx, eax
0x18000d71d  cmp     eax, 80070001h
0x18000d722  jle     short loc_18000D736
0x18000d724  lea     ecx, [rax+7FF8FFFCh]
0x18000d72a  cmp     ecx, 7FF8FFFBh
0x18000d730  jbe     short loc_18000D736
0x18000d732  xor     eax, eax
0x18000d734  jmp     short loc_18000D783
0x18000d736  mov     rcx, [rsp+28h]; this
0x18000d73b  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\regist"...
0x18000d742  mov     r9d, ebx; char *
0x18000d745  mov     edx, 0FCh; void *
0x18000d74a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d74f  mov     rcx, [rsp+28h]; this
0x18000d754  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d75b  mov     r9d, ebx; char *
0x18000d75e  mov     edx, 7Bh ; '{'; void *
0x18000d763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d768  mov     rcx, [rsp+28h]; this
0x18000d76d  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d774  mov     r9d, ebx; char *
0x18000d777  mov     edx, 0EBh; void *
0x18000d77c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d781  mov     eax, ebx
0x18000d783  add     rsp, 20h
0x18000d787  pop     rbx
0x18000d788  retn
```
