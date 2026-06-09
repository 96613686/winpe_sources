# FreeCDPComResource

- ea: `0x180033994`
- end: `0x180033a1c`
- name: `FreeCDPComResource`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800337e0`

## callees

- `0x180033994`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339fe`

## pseudocode

```c
void __fastcall FreeCDPComResource(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // rax
  LPVOID *v4; // rdi
  LPVOID *v5; // rsi
  void *v6; // rcx

  CoTaskMemFree(*(LPVOID *)a1);
  v2 = *(void **)(a1 + 8);
  *(_QWORD *)a1 = 0;
  CoTaskMemFree(v2);
  v3 = *(unsigned __int16 *)(a1 + 32);
  v4 = *(LPVOID **)(a1 + 24);
  *(_QWORD *)(a1 + 8) = 0;
  v5 = &v4[v3];
  while ( v4 != v5 )
    CoTaskMemFree(*v4++);
  CoTaskMemFree(*(LPVOID *)(a1 + 24));
  v6 = *(void **)(a1 + 16);
  *(_QWORD *)(a1 + 24) = 0;
  CoTaskMemFree(v6);
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180033994  mov     [rsp+arg_0], rbx
0x180033999  mov     [rsp+arg_8], rsi
0x18003399e  push    rdi
0x18003399f  sub     rsp, 20h
0x1800339a3  mov     rbx, rcx
0x1800339a6  mov     rcx, [rcx]; pv
0x1800339a9  call    cs:__imp_CoTaskMemFree
0x1800339af  mov     rcx, [rbx+8]; pv
0x1800339b3  mov     qword ptr [rbx], 0
0x1800339ba  call    cs:__imp_CoTaskMemFree
0x1800339c0  movzx   eax, word ptr [rbx+20h]
0x1800339c4  mov     rdi, [rbx+18h]
0x1800339c8  mov     qword ptr [rbx+8], 0
0x1800339d0  lea     rsi, [rdi+rax*8]
0x1800339d4  jmp     short loc_1800339E3
0x1800339d6  mov     rcx, [rdi]; pv
0x1800339d9  call    cs:__imp_CoTaskMemFree
0x1800339df  add     rdi, 8
0x1800339e3  cmp     rdi, rsi
0x1800339e6  jnz     short loc_1800339D6
0x1800339e8  mov     rcx, [rbx+18h]; pv
0x1800339ec  call    cs:__imp_CoTaskMemFree
0x1800339f2  mov     rcx, [rbx+10h]; pv
0x1800339f6  mov     qword ptr [rbx+18h], 0
0x1800339fe  call    cs:__imp_CoTaskMemFree
0x180033a04  mov     rsi, [rsp+28h+arg_8]
0x180033a09  mov     qword ptr [rbx+10h], 0
0x180033a11  mov     rbx, [rsp+28h+arg_0]
0x180033a16  add     rsp, 20h
0x180033a1a  pop     rdi
0x180033a1b  retn
```
