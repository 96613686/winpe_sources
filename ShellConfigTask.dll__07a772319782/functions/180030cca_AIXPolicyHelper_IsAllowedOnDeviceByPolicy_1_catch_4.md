# _AIXPolicyHelper::IsAllowedOnDeviceByPolicy_::_1_::catch$4

- ea: `0x180030cca`
- end: `0x180030d21`
- name: `_AIXPolicyHelper::IsAllowedOnDeviceByPolicy_::_1_::catch$4`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001d368`
- `0x180030cca`

## string_xrefs

- `0x180030cde`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
_BOOL8 __fastcall AIXPolicyHelper::IsAllowedOnDeviceByPolicy_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 200),
    (void *)0x243,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
    a4);
  return *(_BYTE *)(a2 + 232) || *(_BYTE *)(a2 + 69) || *(_BYTE *)(a2 + 70);
}

```

## disassembly

```asm
0x180030cca  mov     [rsp+arg_8], rdx
0x180030ccf  push    rbp
0x180030cd0  sub     rsp, 40h
0x180030cd4  mov     rbp, rdx
0x180030cd7  mov     rcx, [rbp+0C8h]; this
0x180030cde  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x180030ce5  mov     edx, 243h; void *
0x180030cea  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180030cef  cmp     byte ptr [rbp+0E8h], 0
0x180030cf6  jnz     short loc_180030D10
0x180030cf8  cmp     byte ptr [rbp+45h], 0
0x180030cfc  jnz     short loc_180030D10
0x180030cfe  cmp     byte ptr [rbp+46h], 0
0x180030d02  jnz     short loc_180030D10
0x180030d04  mov     rax, 0
0x180030d0e  jmp     short loc_180030D1A
0x180030d10  mov     rax, 1
0x180030d1a  add     rsp, 40h
0x180030d1e  pop     rbp
0x180030d1f  retn
```
