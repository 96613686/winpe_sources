# win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(void)

- ea: `0x1800ec9b0`
- end: `0x1800eca00`
- name: `??1?$ScopedResourceArrayManager@PEA_W@win_dox@@QEAA@XZ`
- size: `80`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800fadd0`
- `0x180127320`
- `0x180127332`

## callees

- `0x1800ec9b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec9dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec9ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec9dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec9ef`

## pseudocode

```c
void __fastcall win_dox::ScopedResourceArrayManager<wchar_t *>::~ScopedResourceArrayManager<wchar_t *>(__int64 a1)
{
  unsigned __int64 i; // rdi
  void *v3; // rcx

  if ( !*(_BYTE *)(a1 + 16) && *(_QWORD *)a1 )
  {
    for ( i = 0; i < *(_QWORD *)(a1 + 8); ++i )
    {
      v3 = *(void **)(*(_QWORD *)a1 + 8 * i);
      if ( v3 )
        CoTaskMemFree(v3);
    }
    CoTaskMemFree(*(LPVOID *)a1);
  }
}

```

## disassembly

```asm
0x1800ec9b0  mov     [rsp+arg_0], rbx
0x1800ec9b5  push    rdi
0x1800ec9b6  sub     rsp, 20h
0x1800ec9ba  cmp     byte ptr [rcx+10h], 0
0x1800ec9be  mov     rbx, rcx
0x1800ec9c1  jnz     short loc_1800EC9F5
0x1800ec9c3  cmp     qword ptr [rcx], 0
0x1800ec9c7  jz      short loc_1800EC9F5
0x1800ec9c9  xor     edi, edi
0x1800ec9cb  cmp     [rcx+8], rdi
0x1800ec9cf  jbe     short loc_1800EC9EC
0x1800ec9d1  mov     rax, [rbx]
0x1800ec9d4  mov     rcx, [rax+rdi*8]; pv
0x1800ec9d8  test    rcx, rcx
0x1800ec9db  jz      short loc_1800EC9E3
0x1800ec9dd  call    cs:__imp_CoTaskMemFree
0x1800ec9e3  inc     rdi
0x1800ec9e6  cmp     rdi, [rbx+8]
0x1800ec9ea  jb      short loc_1800EC9D1
0x1800ec9ec  mov     rcx, [rbx]; pv
0x1800ec9ef  call    cs:__imp_CoTaskMemFree
0x1800ec9f5  mov     rbx, [rsp+28h+arg_0]
0x1800ec9fa  add     rsp, 20h
0x1800ec9fe  pop     rdi
0x1800ec9ff  retn
```
