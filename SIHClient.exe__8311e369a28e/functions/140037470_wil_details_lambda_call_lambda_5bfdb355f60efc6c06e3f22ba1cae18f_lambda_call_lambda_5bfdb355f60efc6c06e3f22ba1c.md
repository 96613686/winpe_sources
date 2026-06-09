# wil::details::lambda_call__lambda_5bfdb355f60efc6c06e3f22ba1cae18f___::_lambda_call__lambda_5bfdb355f60efc6c06e3f22ba1cae18f___

- ea: `0x140037470`
- end: `0x1400374a7`
- name: `wil::details::lambda_call__lambda_5bfdb355f60efc6c06e3f22ba1cae18f___::_lambda_call__lambda_5bfdb355f60efc6c06e3f22ba1cae18f___`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14004fcb2`

## callees

- `0x140037470`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14003749c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14003749c`

## pseudocode

```c
int __fastcall wil::details::lambda_call__lambda_5bfdb355f60efc6c06e3f22ba1cae18f___::_lambda_call__lambda_5bfdb355f60efc6c06e3f22ba1cae18f___(
        __int64 a1)
{
  LPCWSTR *v1; // rax

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v1 = *(LPCWSTR **)a1;
    if ( **(_BYTE **)a1 )
    {
      v1 = *(LPCWSTR **)(a1 + 8);
      if ( *v1 )
        LODWORD(v1) = RegDeleteKeyW(HKEY_LOCAL_MACHINE, *v1);
    }
  }
  return (int)v1;
}

```

## disassembly

```asm
0x140037470  sub     rsp, 28h
0x140037474  xor     r8d, r8d
0x140037477  cmp     [rcx+10h], r8b
0x14003747b  jz      short loc_1400374A2
0x14003747d  mov     [rcx+10h], r8b
0x140037481  mov     rax, [rcx]
0x140037484  cmp     [rax], r8b
0x140037487  jz      short loc_1400374A2
0x140037489  mov     rax, [rcx+8]
0x14003748d  mov     rdx, [rax]; lpSubKey
0x140037490  test    rdx, rdx
0x140037493  jz      short loc_1400374A2
0x140037495  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003749c  call    cs:__imp_RegDeleteKeyW
0x1400374a2  add     rsp, 28h
0x1400374a6  retn
```
