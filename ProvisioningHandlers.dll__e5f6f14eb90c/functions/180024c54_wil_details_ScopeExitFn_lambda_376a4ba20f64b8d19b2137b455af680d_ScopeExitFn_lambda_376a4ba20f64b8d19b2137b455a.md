# wil::details::ScopeExitFn__lambda_376a4ba20f64b8d19b2137b455af680d___::_ScopeExitFn__lambda_376a4ba20f64b8d19b2137b455af680d___

- ea: `0x180024c54`
- end: `0x180024cd0`
- name: `wil::details::ScopeExitFn__lambda_376a4ba20f64b8d19b2137b455af680d___::_ScopeExitFn__lambda_376a4ba20f64b8d19b2137b455af680d___`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b0c9`

## callees

- `0x180024c54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024ca9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024ca9`

## pseudocode

```c
_QWORD *__fastcall wil::details::ScopeExitFn__lambda_376a4ba20f64b8d19b2137b455af680d___::_ScopeExitFn__lambda_376a4ba20f64b8d19b2137b455af680d___(
        __int64 a1)
{
  _QWORD *result; // rax
  unsigned int i; // esi

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    result = *(_QWORD **)a1;
    if ( **(_QWORD **)a1 )
    {
      result = *(_QWORD **)(a1 + 8);
      for ( i = 0; i < *(_DWORD *)result; ++i )
      {
        CoTaskMemFree(*(LPVOID *)(**(_QWORD **)a1 + 24LL * i));
        CoTaskMemFree(*(LPVOID *)(**(_QWORD **)a1 + 24LL * i + 8));
        result = *(_QWORD **)(a1 + 8);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024c54  mov     [rsp+arg_0], rbx
0x180024c59  mov     [rsp+arg_8], rsi
0x180024c5e  push    rdi
0x180024c5f  sub     rsp, 20h
0x180024c63  mov     rdi, rcx
0x180024c66  xor     ecx, ecx
0x180024c68  cmp     [rdi+10h], cl
0x180024c6b  jz      short loc_180024CBF
0x180024c6d  mov     [rdi+10h], cl
0x180024c70  mov     rax, [rdi]
0x180024c73  cmp     [rax], rcx
0x180024c76  jz      short loc_180024CBF
0x180024c78  mov     rax, [rdi+8]
0x180024c7c  mov     esi, ecx
0x180024c7e  cmp     [rax], ecx
0x180024c80  jbe     short loc_180024CBF
0x180024c82  mov     eax, esi
0x180024c84  lea     rbx, [rax+rax*2]
0x180024c88  mov     rax, [rdi]
0x180024c8b  mov     rcx, [rax]
0x180024c8e  mov     rcx, [rcx+rbx*8]; pv
0x180024c92  call    cs:__imp_CoTaskMemFree
0x180024c99  nop     dword ptr [rax+rax+00h]
0x180024c9e  mov     rax, [rdi]
0x180024ca1  mov     rcx, [rax]
0x180024ca4  mov     rcx, [rcx+rbx*8+8]; pv
0x180024ca9  call    cs:__imp_CoTaskMemFree
0x180024cb0  nop     dword ptr [rax+rax+00h]
0x180024cb5  mov     rax, [rdi+8]
0x180024cb9  inc     esi
0x180024cbb  cmp     esi, [rax]
0x180024cbd  jb      short loc_180024C82
0x180024cbf  mov     rbx, [rsp+28h+arg_0]
0x180024cc4  mov     rsi, [rsp+28h+arg_8]
0x180024cc9  add     rsp, 20h
0x180024ccd  pop     rdi
0x180024cce  retn
```
