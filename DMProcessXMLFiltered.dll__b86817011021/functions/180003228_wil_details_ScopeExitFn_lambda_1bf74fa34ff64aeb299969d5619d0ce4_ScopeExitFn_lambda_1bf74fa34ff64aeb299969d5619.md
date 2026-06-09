# wil::details::ScopeExitFn__lambda_1bf74fa34ff64aeb299969d5619d0ce4___::_ScopeExitFn__lambda_1bf74fa34ff64aeb299969d5619d0ce4___

- ea: `0x180003228`
- end: `0x180003268`
- name: `wil::details::ScopeExitFn__lambda_1bf74fa34ff64aeb299969d5619d0ce4___::_ScopeExitFn__lambda_1bf74fa34ff64aeb299969d5619d0ce4___`
- size: `64`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007064`
- `0x180007076`

## callees

- `0x180003228`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003243`
- `OLEAUT32!__imp_SysFreeString` at `0x180003254`
- `OLEAUT32!__imp_SysFreeString` at `0x180003243`
- `OLEAUT32!__imp_SysFreeString` at `0x180003254`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_1bf74fa34ff64aeb299969d5619d0ce4___::_ScopeExitFn__lambda_1bf74fa34ff64aeb299969d5619d0ce4___(
        __int64 a1)
{
  BSTR *v1; // rbx
  OLECHAR *v2; // rcx

  if ( *(_BYTE *)(a1 + 8) )
  {
    v1 = *(BSTR **)a1;
    *(_BYTE *)(a1 + 8) = 0;
    if ( v1 )
    {
      SysFreeString(*v1);
      v2 = v1[2];
      *v1 = 0;
      SysFreeString(v2);
      v1[2] = 0;
    }
  }
}

```

## disassembly

```asm
0x180003228  push    rbx
0x18000322a  sub     rsp, 20h
0x18000322e  cmp     byte ptr [rcx+8], 0
0x180003232  jz      short loc_180003262
0x180003234  mov     rbx, [rcx]
0x180003237  mov     byte ptr [rcx+8], 0
0x18000323b  test    rbx, rbx
0x18000323e  jz      short loc_180003262
0x180003240  mov     rcx, [rbx]; bstrString
0x180003243  call    cs:__imp_SysFreeString
0x180003249  mov     rcx, [rbx+10h]; bstrString
0x18000324d  mov     qword ptr [rbx], 0
0x180003254  call    cs:__imp_SysFreeString
0x18000325a  mov     qword ptr [rbx+10h], 0
0x180003262  add     rsp, 20h
0x180003266  pop     rbx
0x180003267  retn
```
