# FreeCDPComResource

- ea: `0x18004ec9c`
- end: `0x18004ed24`
- name: `FreeCDPComResource`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d9d0`
- `0x18004e794`

## callees

- `0x18004ec9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ecb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ecc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ece1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ecf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ed06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ecb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ecc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ece1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ecf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ed06`

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
0x18004ec9c  mov     [rsp+arg_0], rbx
0x18004eca1  mov     [rsp+arg_8], rsi
0x18004eca6  push    rdi
0x18004eca7  sub     rsp, 20h
0x18004ecab  mov     rbx, rcx
0x18004ecae  mov     rcx, [rcx]; pv
0x18004ecb1  call    cs:__imp_CoTaskMemFree
0x18004ecb7  mov     rcx, [rbx+8]; pv
0x18004ecbb  mov     qword ptr [rbx], 0
0x18004ecc2  call    cs:__imp_CoTaskMemFree
0x18004ecc8  movzx   eax, word ptr [rbx+20h]
0x18004eccc  mov     rdi, [rbx+18h]
0x18004ecd0  mov     qword ptr [rbx+8], 0
0x18004ecd8  lea     rsi, [rdi+rax*8]
0x18004ecdc  jmp     short loc_18004ECEB
0x18004ecde  mov     rcx, [rdi]; pv
0x18004ece1  call    cs:__imp_CoTaskMemFree
0x18004ece7  add     rdi, 8
0x18004eceb  cmp     rdi, rsi
0x18004ecee  jnz     short loc_18004ECDE
0x18004ecf0  mov     rcx, [rbx+18h]; pv
0x18004ecf4  call    cs:__imp_CoTaskMemFree
0x18004ecfa  mov     rcx, [rbx+10h]; pv
0x18004ecfe  mov     qword ptr [rbx+18h], 0
0x18004ed06  call    cs:__imp_CoTaskMemFree
0x18004ed0c  mov     rsi, [rsp+28h+arg_8]
0x18004ed11  mov     qword ptr [rbx+10h], 0
0x18004ed19  mov     rbx, [rsp+28h+arg_0]
0x18004ed1e  add     rsp, 20h
0x18004ed22  pop     rdi
0x18004ed23  retn
```
