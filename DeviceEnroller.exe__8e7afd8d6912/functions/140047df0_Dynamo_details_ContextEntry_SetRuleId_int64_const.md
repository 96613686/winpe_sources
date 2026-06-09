# Dynamo::details::ContextEntry::SetRuleId(__int64 const *)

- ea: `0x140047df0`
- end: `0x140047efc`
- name: `?SetRuleId@ContextEntry@details@Dynamo@@UEAAXPEB_J@Z`
- size: `268`
- prototype: `void(Dynamo::details::ContextEntry *__hidden this, const __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1400419a4`
- `0x140047df0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140047e78`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140047e78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140047e91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140047e91`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140047e45`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140047e45`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140047ea4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140047ea4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Dynamo::details::ContextEntry::SetRuleId(Dynamo::details::ContextEntry *this, const BYTE *a2)
{
  HKEY v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  const char *v7; // r9
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v3 = (HKEY)*((_QWORD *)this + 2);
  if ( a2 )
  {
    hKey = 0;
    v4 = RegCreateKeyExW(v3, L"RuleId", 0, 0, 1u, 0x20006u, 0, &hKey, 0);
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x8D,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\contextentry.cpp",
        (const char *)v4,
        dwOptionsa);
    v5 = RegSetValueExW(hKey, L"RuleId", 0, 0xBu, a2, 8u);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x8E,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\contextentry.cpp",
        (const char *)v5,
        dwOptionsb);
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    v6 = RegDeleteKeyW(v3, L"RuleId");
    v7 = 0;
    if ( v6 != 2 )
      v7 = (const char *)v6;
    if ( (_DWORD)v7 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x94,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\contextentry.cpp",
        v7,
        dwOptions);
  }
}

```

## disassembly

```asm
0x140047df0  mov     r11, rsp
0x140047df3  push    rbx
0x140047df4  sub     rsp, 50h
0x140047df8  mov     rbx, rdx
0x140047dfb  mov     rcx, [rcx+10h]; hKey
0x140047dff  test    rdx, rdx
0x140047e02  jz      loc_140047E9D
0x140047e08  mov     qword ptr [r11+10h], 0
0x140047e10  mov     qword ptr [r11-18h], 0
0x140047e18  lea     rax, [r11+10h]
0x140047e1c  mov     [r11-20h], rax
0x140047e20  mov     qword ptr [r11-28h], 0
0x140047e28  mov     [rsp+58h+samDesired], 20006h; samDesired
0x140047e30  mov     [rsp+58h+dwOptions], 1; unsigned int
0x140047e38  xor     r9d, r9d; lpClass
0x140047e3b  xor     r8d, r8d; Reserved
0x140047e3e  lea     rdx, aRuleid; "RuleId"
0x140047e45  call    cs:__imp_RegCreateKeyExW
0x140047e4b  mov     rcx, [rsp+58h]; this
0x140047e50  test    eax, eax
0x140047e52  jnz     loc_140047EE7
0x140047e58  mov     [rsp+58h+samDesired], 8; cbData
0x140047e60  mov     qword ptr [rsp+58h+dwOptions], rbx; unsigned int
0x140047e65  lea     r9d, [rax+0Bh]; dwType
0x140047e69  xor     r8d, r8d; Reserved
0x140047e6c  lea     rdx, aRuleid; "RuleId"
0x140047e73  mov     rcx, [rsp+58h+hKey]; hKey
0x140047e78  call    cs:__imp_RegSetValueExW
0x140047e7e  mov     rcx, [rsp+58h]; this
0x140047e83  test    eax, eax
0x140047e85  jnz     short loc_140047EBB
0x140047e87  mov     rcx, [rsp+58h+hKey]; hKey
0x140047e8c  test    rcx, rcx
0x140047e8f  jz      short loc_140047E97
0x140047e91  call    cs:__imp_RegCloseKey
0x140047e97  add     rsp, 50h
0x140047e9b  pop     rbx
0x140047e9c  retn
0x140047e9d  lea     rdx, aRuleid; "RuleId"
0x140047ea4  call    cs:__imp_RegDeleteKeyW
0x140047eaa  xor     r9d, r9d
0x140047ead  cmp     eax, 2
0x140047eb0  cmovnz  r9d, eax; char *
0x140047eb4  test    r9d, r9d
0x140047eb7  jnz     short loc_140047ED0
0x140047eb9  jmp     short loc_140047E97
0x140047ebb  mov     r9d, eax; char *
0x140047ebe  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140047ec5  mov     edx, 8Eh; void *
0x140047eca  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140047ed0  mov     rcx, [rsp+58h]; this
0x140047ed5  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140047edc  mov     edx, 94h; void *
0x140047ee1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140047ee7  mov     r9d, eax; char *
0x140047eea  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140047ef1  mov     edx, 8Dh; void *
0x140047ef6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
