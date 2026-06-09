# McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult(_McpPrinterSearchResult *)

- ea: `0x180025a80`
- end: `0x180025b92`
- name: `?FreeMcpPrinterSearchResult@McpManagementHelpers@McpManagement@@SAXPEAU_McpPrinterSearchResult@@@Z`
- size: `274`
- prototype: `void __fastcall(struct _McpPrinterSearchResult *pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800268a0`

## callees

- `0x180025a80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ac2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ac2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult(struct _McpPrinterSearchResult *pv)
{
  unsigned __int64 i; // rsi
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  if ( pv )
  {
    if ( *((_QWORD *)pv + 1) )
    {
      for ( i = 0; i < *((unsigned int *)pv + 1); ++i )
      {
        v3 = *(void **)(*((_QWORD *)pv + 1) + 40 * i);
        if ( v3 )
        {
          CoTaskMemFree(v3);
          *(_QWORD *)(*((_QWORD *)pv + 1) + 40 * i) = 0;
        }
        v4 = *(void **)(*((_QWORD *)pv + 1) + 40 * i + 8);
        if ( v4 )
        {
          CoTaskMemFree(v4);
          *(_QWORD *)(*((_QWORD *)pv + 1) + 40 * i + 8) = 0;
        }
        v5 = *(void **)(*((_QWORD *)pv + 1) + 40 * i + 16);
        if ( v5 )
        {
          CoTaskMemFree(v5);
          *(_QWORD *)(*((_QWORD *)pv + 1) + 40 * i + 16) = 0;
        }
        v6 = *(void **)(*((_QWORD *)pv + 1) + 40 * i + 24);
        if ( v6 )
        {
          CoTaskMemFree(v6);
          *(_QWORD *)(*((_QWORD *)pv + 1) + 40 * i + 24) = 0;
        }
        v7 = *(void **)(*((_QWORD *)pv + 1) + 40 * i + 32);
        if ( v7 )
        {
          CoTaskMemFree(v7);
          *(_QWORD *)(*((_QWORD *)pv + 1) + 40 * i + 32) = 0;
        }
      }
      CoTaskMemFree(*((LPVOID *)pv + 1));
      *((_QWORD *)pv + 1) = 0;
    }
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x180025a80  test    rcx, rcx
0x180025a83  jz      locret_180025B91
0x180025a89  mov     [rsp+arg_0], rbx
0x180025a8e  mov     [rsp+arg_8], rsi
0x180025a93  push    rdi
0x180025a94  sub     rsp, 20h
0x180025a98  cmp     qword ptr [rcx+8], 0
0x180025a9d  mov     rbx, rcx
0x180025aa0  jz      loc_180025B79
0x180025aa6  xor     esi, esi
0x180025aa8  cmp     [rcx+4], esi
0x180025aab  jbe     loc_180025B67
0x180025ab1  mov     rax, [rbx+8]
0x180025ab5  lea     rdi, [rsi+rsi*4]
0x180025ab9  mov     rcx, [rax+rdi*8]; pv
0x180025abd  test    rcx, rcx
0x180025ac0  jz      short loc_180025AD4
0x180025ac2  call    cs:__imp_CoTaskMemFree
0x180025ac8  mov     rax, [rbx+8]
0x180025acc  mov     qword ptr [rax+rdi*8], 0
0x180025ad4  mov     rax, [rbx+8]
0x180025ad8  mov     rcx, [rax+rdi*8+8]; pv
0x180025add  test    rcx, rcx
0x180025ae0  jz      short loc_180025AF5
0x180025ae2  call    cs:__imp_CoTaskMemFree
0x180025ae8  mov     rax, [rbx+8]
0x180025aec  mov     qword ptr [rax+rdi*8+8], 0
0x180025af5  mov     rax, [rbx+8]
0x180025af9  mov     rcx, [rax+rdi*8+10h]; pv
0x180025afe  test    rcx, rcx
0x180025b01  jz      short loc_180025B16
0x180025b03  call    cs:__imp_CoTaskMemFree
0x180025b09  mov     rax, [rbx+8]
0x180025b0d  mov     qword ptr [rax+rdi*8+10h], 0
0x180025b16  mov     rax, [rbx+8]
0x180025b1a  mov     rcx, [rax+rdi*8+18h]; pv
0x180025b1f  test    rcx, rcx
0x180025b22  jz      short loc_180025B37
0x180025b24  call    cs:__imp_CoTaskMemFree
0x180025b2a  mov     rax, [rbx+8]
0x180025b2e  mov     qword ptr [rax+rdi*8+18h], 0
0x180025b37  mov     rax, [rbx+8]
0x180025b3b  mov     rcx, [rax+rdi*8+20h]; pv
0x180025b40  test    rcx, rcx
0x180025b43  jz      short loc_180025B58
0x180025b45  call    cs:__imp_CoTaskMemFree
0x180025b4b  mov     rax, [rbx+8]
0x180025b4f  mov     qword ptr [rax+rdi*8+20h], 0
0x180025b58  mov     eax, [rbx+4]
0x180025b5b  inc     rsi
0x180025b5e  cmp     rsi, rax
0x180025b61  jb      loc_180025AB1
0x180025b67  mov     rcx, [rbx+8]; pv
0x180025b6b  call    cs:__imp_CoTaskMemFree
0x180025b71  mov     qword ptr [rbx+8], 0
0x180025b79  mov     rcx, rbx; pv
0x180025b7c  call    cs:__imp_CoTaskMemFree
0x180025b82  mov     rbx, [rsp+28h+arg_0]
0x180025b87  mov     rsi, [rsp+28h+arg_8]
0x180025b8c  add     rsp, 20h
0x180025b90  pop     rdi
0x180025b91  retn
```
