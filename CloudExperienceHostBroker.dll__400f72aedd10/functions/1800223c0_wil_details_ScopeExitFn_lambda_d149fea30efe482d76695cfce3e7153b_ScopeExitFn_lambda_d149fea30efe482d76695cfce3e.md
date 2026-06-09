# wil::details::ScopeExitFn__lambda_d149fea30efe482d76695cfce3e7153b___::_ScopeExitFn__lambda_d149fea30efe482d76695cfce3e7153b___

- ea: `0x1800223c0`
- end: `0x180022409`
- name: `wil::details::ScopeExitFn__lambda_d149fea30efe482d76695cfce3e7153b___::_ScopeExitFn__lambda_d149fea30efe482d76695cfce3e7153b___`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036de1`
- `0x180036e05`

## callees

- `0x1800223c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800223fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800223fe`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_d149fea30efe482d76695cfce3e7153b___::_ScopeExitFn__lambda_d149fea30efe482d76695cfce3e7153b___(
        __int64 a1)
{
  _BYTE *v1; // rdx
  _DWORD *v2; // rax
  __int64 i; // rax

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v1 = **(_BYTE ***)a1;
    if ( v1 )
    {
      v2 = *(_DWORD **)(a1 + 8);
      if ( *v2 )
      {
        for ( i = (unsigned int)*v2; i; --i )
          *v1++ = 0;
        CoTaskMemFree(**(LPVOID **)a1);
      }
    }
  }
}

```

## disassembly

```asm
0x1800223c0  sub     rsp, 28h
0x1800223c4  xor     r8d, r8d
0x1800223c7  cmp     [rcx+10h], r8b
0x1800223cb  jz      short loc_180022404
0x1800223cd  mov     [rcx+10h], r8b
0x1800223d1  mov     rax, [rcx]
0x1800223d4  mov     rdx, [rax]
0x1800223d7  test    rdx, rdx
0x1800223da  jz      short loc_180022404
0x1800223dc  mov     rax, [rcx+8]
0x1800223e0  cmp     [rax], r8d
0x1800223e3  jbe     short loc_180022404
0x1800223e5  mov     eax, [rax]
0x1800223e7  test    rax, rax
0x1800223ea  jz      short loc_1800223F8
0x1800223ec  mov     [rdx], r8b
0x1800223ef  inc     rdx
0x1800223f2  sub     rax, 1
0x1800223f6  jnz     short loc_1800223EC
0x1800223f8  mov     rcx, [rcx]
0x1800223fb  mov     rcx, [rcx]; pv
0x1800223fe  call    cs:__imp_CoTaskMemFree
0x180022404  add     rsp, 28h
0x180022408  retn
```
