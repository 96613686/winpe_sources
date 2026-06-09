# wil::details::ScopeExitFn__lambda_c225665da0a2dffe5d19b8ea675b1284___::_ScopeExitFn__lambda_c225665da0a2dffe5d19b8ea675b1284___

- ea: `0x1400038cc`
- end: `0x1400038f9`
- name: `wil::details::ScopeExitFn__lambda_c225665da0a2dffe5d19b8ea675b1284___::_ScopeExitFn__lambda_c225665da0a2dffe5d19b8ea675b1284___`
- size: `45`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000e306`

## callees

- `0x1400038cc`

## import_xrefs

- `dmcommandlineutils!FreeCommandLineOptions` at `0x1400038ee`
- `dmcommandlineutils!FreeCommandLineOptions` at `0x1400038ee`

## pseudocode

```c
__int64 __fastcall wil::details::ScopeExitFn__lambda_c225665da0a2dffe5d19b8ea675b1284___::_ScopeExitFn__lambda_c225665da0a2dffe5d19b8ea675b1284___(
        __int64 *a1)
{
  __int64 v1; // r8
  __int64 result; // rax

  if ( *((_BYTE *)a1 + 8) )
  {
    v1 = *a1;
    *((_BYTE *)a1 + 8) = 0;
    return FreeCommandLineOptions(&off_1400112E0, 9, v1);
  }
  return result;
}

```

## disassembly

```asm
0x1400038cc  sub     rsp, 28h
0x1400038d0  cmp     byte ptr [rcx+8], 0
0x1400038d4  jz      short loc_1400038F4
0x1400038d6  mov     r8, [rcx]
0x1400038d9  mov     r9d, 78h ; 'x'
0x1400038df  mov     byte ptr [rcx+8], 0
0x1400038e3  lea     rcx, off_1400112E0; "add"
0x1400038ea  lea     edx, [r9-6Fh]
0x1400038ee  call    cs:__imp_FreeCommandLineOptions
0x1400038f4  add     rsp, 28h
0x1400038f8  retn
```
