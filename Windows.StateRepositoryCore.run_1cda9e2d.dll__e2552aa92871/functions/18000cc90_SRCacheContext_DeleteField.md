# SRCacheContext_DeleteField

- ea: `0x18000cc90`
- end: `0x18000cd19`
- name: `SRCacheContext_DeleteField`
- size: `137`
- prototype: `__int64 __fastcall(Common::RegistryKey *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000cc90`
- `0x18000fa88`

## string_xrefs

- `0x18000cce9`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000ccfd`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000cccb`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_DeleteField(Common::RegistryKey *a1, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-8h]
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_QWORD *)a1 )
  {
    v4 = Common::RegistryKey::DeleteValue(a1, a2);
    v2 = v4;
    if ( v4 > -2147024895 && (unsigned int)(v4 + 2147024892) > 0x7FF8FFFB )
      return 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D6,
      (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
      (const char *)(unsigned int)v4,
      v6);
    v3 = 333;
  }
  else
  {
    v2 = -2147019873;
    v3 = 331;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)v2,
    v6);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x26E,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)v2,
    v7);
  return v2;
}

```

## disassembly

```asm
0x18000cc90  push    rbx; int
0x18000cc92  sub     rsp, 20h
0x18000cc96  cmp     qword ptr [rcx], 0
0x18000cc9a  jnz     short loc_18000CCA8
0x18000cc9c  mov     ebx, 8007139Fh
0x18000cca1  mov     edx, 14Bh; unsigned __int16 *
0x18000cca6  jmp     short loc_18000CCE4
0x18000cca8  call    ?DeleteValue@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteValue(ushort const *)
0x18000ccad  mov     ebx, eax
0x18000ccaf  cmp     eax, 80070001h
0x18000ccb4  jle     short loc_18000CCC6
0x18000ccb6  add     eax, 7FF8FFFCh
0x18000ccbb  cmp     eax, 7FF8FFFBh
0x18000ccc0  jbe     short loc_18000CCC6
0x18000ccc2  xor     eax, eax
0x18000ccc4  jmp     short loc_18000CD13
0x18000ccc6  mov     rcx, [rsp+28h]; this
0x18000cccb  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\regist"...
0x18000ccd2  mov     r9d, ebx; char *
0x18000ccd5  mov     edx, 1D6h; void *
0x18000ccda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ccdf  mov     edx, 14Dh; void *
0x18000cce4  mov     rcx, [rsp+28h]; this
0x18000cce9  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000ccf0  mov     r9d, ebx; char *
0x18000ccf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ccf8  mov     rcx, [rsp+28h]; this
0x18000ccfd  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cd04  mov     r9d, ebx; char *
0x18000cd07  mov     edx, 26Eh; void *
0x18000cd0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd11  mov     eax, ebx
0x18000cd13  add     rsp, 20h
0x18000cd17  pop     rbx
0x18000cd18  retn
```
