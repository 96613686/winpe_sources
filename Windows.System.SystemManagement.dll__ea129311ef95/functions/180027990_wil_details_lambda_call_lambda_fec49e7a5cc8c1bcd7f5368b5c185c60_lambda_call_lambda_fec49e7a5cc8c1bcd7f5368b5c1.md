# wil::details::lambda_call__lambda_fec49e7a5cc8c1bcd7f5368b5c185c60___::_lambda_call__lambda_fec49e7a5cc8c1bcd7f5368b5c185c60___

- ea: `0x180027990`
- end: `0x1800279fe`
- name: `wil::details::lambda_call__lambda_fec49e7a5cc8c1bcd7f5368b5c185c60___::_lambda_call__lambda_fec49e7a5cc8c1bcd7f5368b5c185c60___`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18002a0dc`

## callees

- `0x18000f824`
- `0x180027990`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800279aa`
- `OLEAUT32!__imp_VariantClear` at `0x1800279d5`
- `OLEAUT32!__imp_VariantClear` at `0x1800279aa`
- `OLEAUT32!__imp_VariantClear` at `0x1800279d5`

## string_xrefs

- `0x1800279b9`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x1800279e4`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

## pseudocode

```c
void __fastcall wil::details::lambda_call__lambda_fec49e7a5cc8c1bcd7f5368b5c185c60___::_lambda_call__lambda_fec49e7a5cc8c1bcd7f5368b5c185c60___(
        __int64 a1)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v2 = VariantClear((VARIANTARG *)(*(_QWORD *)a1 + 16LL));
    if ( v2 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
        (const char *)(unsigned int)v2,
        v4);
    v3 = VariantClear((VARIANTARG *)(*(_QWORD *)(a1 + 8) + 16LL));
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
        (const char *)(unsigned int)v3,
        v4);
  }
}

```

## disassembly

```asm
0x180027990  push    rbx; int
0x180027992  sub     rsp, 20h
0x180027996  cmp     byte ptr [rcx+10h], 0
0x18002799a  mov     rbx, rcx
0x18002799d  jz      short loc_1800279F8
0x18002799f  mov     byte ptr [rcx+10h], 0
0x1800279a3  mov     rcx, [rcx]
0x1800279a6  add     rcx, 10h; pvarg
0x1800279aa  call    cs:__imp_VariantClear
0x1800279b0  test    eax, eax
0x1800279b2  jns     short loc_1800279CD
0x1800279b4  mov     rcx, [rsp+28h]; this
0x1800279b9  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800279c0  mov     r9d, eax; char *
0x1800279c3  mov     edx, 53h ; 'S'; void *
0x1800279c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800279cd  mov     rcx, [rbx+8]
0x1800279d1  add     rcx, 10h; pvarg
0x1800279d5  call    cs:__imp_VariantClear
0x1800279db  test    eax, eax
0x1800279dd  jns     short loc_1800279F8
0x1800279df  mov     rcx, [rsp+28h]; this
0x1800279e4  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800279eb  mov     r9d, eax; char *
0x1800279ee  mov     edx, 54h ; 'T'; void *
0x1800279f3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800279f8  add     rsp, 20h
0x1800279fc  pop     rbx
0x1800279fd  retn
```
