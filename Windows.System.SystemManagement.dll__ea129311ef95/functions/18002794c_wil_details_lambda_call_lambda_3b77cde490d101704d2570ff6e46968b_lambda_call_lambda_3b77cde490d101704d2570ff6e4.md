# wil::details::lambda_call__lambda_3b77cde490d101704d2570ff6e46968b___::_lambda_call__lambda_3b77cde490d101704d2570ff6e46968b___

- ea: `0x18002794c`
- end: `0x180027989`
- name: `wil::details::lambda_call__lambda_3b77cde490d101704d2570ff6e46968b___::_lambda_call__lambda_3b77cde490d101704d2570ff6e46968b___`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18002a0ee`

## callees

- `0x18000f824`
- `0x18002794c`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180027961`
- `OLEAUT32!__imp_VariantClear` at `0x180027961`

## string_xrefs

- `0x180027970`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

## pseudocode

```c
void __fastcall wil::details::lambda_call__lambda_3b77cde490d101704d2570ff6e46968b___::_lambda_call__lambda_3b77cde490d101704d2570ff6e46968b___(
        _BYTE *a1)
{
  HRESULT v1; // eax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a1[8] )
  {
    a1[8] = 0;
    v1 = VariantClear((VARIANTARG *)(*(_QWORD *)a1 + 16LL));
    if ( v1 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
        (const char *)(unsigned int)v1,
        v2);
  }
}

```

## disassembly

```asm
0x18002794c  sub     rsp, 28h
0x180027950  cmp     byte ptr [rcx+8], 0
0x180027954  jz      short loc_180027984
0x180027956  mov     byte ptr [rcx+8], 0
0x18002795a  mov     rcx, [rcx]
0x18002795d  add     rcx, 10h; pvarg
0x180027961  call    cs:__imp_VariantClear
0x180027967  test    eax, eax
0x180027969  jns     short loc_180027984
0x18002796b  mov     rcx, [rsp+28h]; this
0x180027970  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027977  mov     r9d, eax; char *
0x18002797a  mov     edx, 166h; void *
0x18002797f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027984  add     rsp, 28h
0x180027988  retn
```
