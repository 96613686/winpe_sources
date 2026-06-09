# FreeCDPComEndpoint

- ea: `0x18003390c`
- end: `0x18003398c`
- name: `FreeCDPComEndpoint`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800337e0`

## callees

- `0x18003390c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003396e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003396e`

## pseudocode

```c
void __fastcall FreeCDPComEndpoint(__int64 a1)
{
  void *v2; // rcx
  LPVOID *v3; // rbx
  LPVOID *v4; // rsi

  CoTaskMemFree(*(LPVOID *)a1);
  v2 = *(void **)(a1 + 8);
  *(_QWORD *)a1 = 0;
  CoTaskMemFree(v2);
  v3 = *(LPVOID **)(a1 + 24);
  v4 = &v3[2 * *(unsigned __int16 *)(a1 + 32)];
  *(_QWORD *)(a1 + 8) = 0;
  while ( v3 != v4 )
  {
    CoTaskMemFree(*v3);
    *v3 = 0;
    v3 += 2;
  }
  CoTaskMemFree(*(LPVOID *)(a1 + 24));
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x18003390c  mov     [rsp+arg_0], rbx
0x180033911  mov     [rsp+arg_8], rsi
0x180033916  push    rdi
0x180033917  sub     rsp, 20h
0x18003391b  mov     rdi, rcx
0x18003391e  mov     rcx, [rcx]; pv
0x180033921  call    cs:__imp_CoTaskMemFree
0x180033927  mov     rcx, [rdi+8]; pv
0x18003392b  mov     qword ptr [rdi], 0
0x180033932  call    cs:__imp_CoTaskMemFree
0x180033938  movzx   esi, word ptr [rdi+20h]
0x18003393c  mov     rbx, [rdi+18h]
0x180033940  shl     rsi, 4
0x180033944  add     rsi, rbx
0x180033947  mov     qword ptr [rdi+8], 0
0x18003394f  jmp     short loc_180033965
0x180033951  mov     rcx, [rbx]; pv
0x180033954  call    cs:__imp_CoTaskMemFree
0x18003395a  mov     qword ptr [rbx], 0
0x180033961  add     rbx, 10h
0x180033965  cmp     rbx, rsi
0x180033968  jnz     short loc_180033951
0x18003396a  mov     rcx, [rdi+18h]; pv
0x18003396e  call    cs:__imp_CoTaskMemFree
0x180033974  mov     rbx, [rsp+28h+arg_0]
0x180033979  mov     rsi, [rsp+28h+arg_8]
0x18003397e  mov     qword ptr [rdi+18h], 0
0x180033986  add     rsp, 20h
0x18003398a  pop     rdi
0x18003398b  retn
```
