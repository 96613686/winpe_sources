# wil::details::ScopeExitFn<_lambda_e444c0c7c01247f58c35406cc2249eb4_>::~ScopeExitFn<_lambda_e444c0c7c01247f58c35406cc2249eb4_>(void)

- ea: `0x1800121a4`
- end: `0x1800121e9`
- name: `??1?$ScopeExitFn@V_lambda_e444c0c7c01247f58c35406cc2249eb4_@@@details@wil@@QEAA@XZ`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800369aa`

## callees

- `0x1800121a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121de`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn<_lambda_e444c0c7c01247f58c35406cc2249eb4_>::~ScopeExitFn<_lambda_e444c0c7c01247f58c35406cc2249eb4_>(
        __int64 a1)
{
  _BYTE *v1; // rdx
  unsigned int *v2; // rax
  __int64 v3; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v1 = **(_BYTE ***)a1;
    if ( v1 )
    {
      v2 = *(unsigned int **)(a1 + 8);
      v3 = *v2;
      if ( *v2 )
      {
        do
        {
          *v1++ = 0;
          --v3;
        }
        while ( v3 );
      }
      CoTaskMemFree(**(LPVOID **)a1);
    }
  }
}

```

## disassembly

```asm
0x1800121a4  sub     rsp, 28h
0x1800121a8  xor     r9d, r9d
0x1800121ab  cmp     [rcx+10h], r9b
0x1800121af  jz      short loc_1800121E4
0x1800121b1  mov     [rcx+10h], r9b
0x1800121b5  mov     rax, [rcx]
0x1800121b8  mov     rdx, [rax]
0x1800121bb  test    rdx, rdx
0x1800121be  jz      short loc_1800121E4
0x1800121c0  mov     rax, [rcx+8]
0x1800121c4  mov     r8d, [rax]
0x1800121c7  test    r8, r8
0x1800121ca  jz      short loc_1800121D8
0x1800121cc  mov     [rdx], r9b
0x1800121cf  inc     rdx
0x1800121d2  sub     r8, 1
0x1800121d6  jnz     short loc_1800121CC
0x1800121d8  mov     rcx, [rcx]
0x1800121db  mov     rcx, [rcx]; pv
0x1800121de  call    cs:__imp_CoTaskMemFree
0x1800121e4  add     rsp, 28h
0x1800121e8  retn
```
