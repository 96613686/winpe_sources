# ProtobufHelper::GetBstrPayload(UiaManagerProto::WstringMsg const &)

- ea: `0x180023c58`
- end: `0x180023ce0`
- name: `?GetBstrPayload@ProtobufHelper@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBVWstringMsg@UiaManagerProto@@@Z`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f78c`

## callees

- `0x180023c58`
- `0x180023ce8`
- `0x180031540`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180023cab`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180023cab`

## string_xrefs

- `0x180023c89`: `onecore\windows\accessibletech\uiamanager\dll\protobufhelper.cpp`
- `0x180023cc6`: `onecore\windows\accessibletech\uiamanager\dll\protobufhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BSTR *__fastcall ProtobufHelper::GetBstrPayload(BSTR *a1, __int64 a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  BSTR v6; // rax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *(_QWORD *)(a2 + 16) & 0xFFFFFFFFFFFFFFFEuLL;
  v4 = *(_QWORD *)(v3 + 16);
  if ( (v4 & 1) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\protobufhelper.cpp",
      (const char *)0x8000FFFFLL,
      0);
  v5 = v4 >> 1;
  if ( *(_QWORD *)(v3 + 24) > 0xFu )
    v3 = *(_QWORD *)v3;
  v6 = SysAllocStringLen((const OLECHAR *)v3, v5);
  *a1 = v6;
  if ( !v6 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\protobufhelper.cpp",
      v7);
  return a1;
}

```

## disassembly

```asm
0x180023c58  mov     [rsp+arg_0], rcx
0x180023c5d  push    rbx
0x180023c5e  sub     rsp, 30h
0x180023c62  mov     rbx, rcx
0x180023c65  mov     [rsp+38h+var_18], 0; int
0x180023c6d  mov     rcx, [rdx+10h]
0x180023c71  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180023c75  mov     rdx, [rcx+10h]
0x180023c79  mov     rax, [rsp+38h]
0x180023c7e  test    dl, 1
0x180023c81  jz      short loc_180023C9E
0x180023c83  mov     r9d, 8000FFFFh; char *
0x180023c89  lea     r8, aOnecoreWindows_26; "onecore\\windows\\accessibletech\\uiama"...
0x180023c90  mov     edx, 27h ; '''; void *
0x180023c95  mov     rcx, rax; this
0x180023c98  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023c9e  shr     rdx, 1; ui
0x180023ca1  cmp     qword ptr [rcx+18h], 0Fh
0x180023ca6  jbe     short loc_180023CAB
0x180023ca8  mov     rcx, [rcx]; strIn
0x180023cab  call    cs:__imp_SysAllocStringLen
0x180023cb1  mov     [rbx], rax
0x180023cb4  mov     [rsp+38h+var_18], 1
0x180023cbc  mov     rcx, [rsp+38h]; this
0x180023cc1  test    rax, rax
0x180023cc4  jnz     short loc_180023CD6
0x180023cc6  lea     r8, aOnecoreWindows_26; "onecore\\windows\\accessibletech\\uiama"...
0x180023ccd  lea     edx, [rax+2Bh]; void *
0x180023cd0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180023cd6  mov     rax, rbx
0x180023cd9  add     rsp, 30h
0x180023cdd  pop     rbx
0x180023cde  retn
```
