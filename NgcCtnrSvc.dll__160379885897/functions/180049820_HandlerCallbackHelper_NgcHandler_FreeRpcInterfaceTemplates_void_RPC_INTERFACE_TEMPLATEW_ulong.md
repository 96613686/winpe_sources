# HandlerCallbackHelper<NgcHandler>::FreeRpcInterfaceTemplates(void *,RPC_INTERFACE_TEMPLATEW *,ulong)

- ea: `0x180049820`
- end: `0x180049879`
- name: `?FreeRpcInterfaceTemplates@?$HandlerCallbackHelper@VNgcHandler@@@@SAXPEAXPEAURPC_INTERFACE_TEMPLATEW@@K@Z`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180049820`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004986d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049847`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049847`

## pseudocode

```c
void __fastcall HandlerCallbackHelper<NgcHandler>::FreeRpcInterfaceTemplates(__int64 a1, _QWORD *a2, unsigned int a3)
{
  __int64 i; // rbx
  void *v6; // rcx

  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    v6 = (void *)a2[10 * i + 9];
    if ( v6 )
    {
      LocalFree(v6);
      a2[10 * i + 9] = 0;
    }
  }
  CoTaskMemFree(a2);
}

```

## disassembly

```asm
0x180049820  push    rbx
0x180049822  push    rbp
0x180049823  push    rsi
0x180049824  push    rdi
0x180049825  sub     rsp, 28h
0x180049829  xor     ebx, ebx
0x18004982b  mov     ebp, r8d
0x18004982e  mov     rdi, rdx
0x180049831  test    r8d, r8d
0x180049834  jz      short loc_180049862
0x180049836  lea     rsi, [rbx+rbx*4]
0x18004983a  add     rsi, rsi
0x18004983d  mov     rcx, [rdi+rsi*8+48h]; hMem
0x180049842  test    rcx, rcx
0x180049845  jz      short loc_18004985C
0x180049847  call    cs:__imp_LocalFree
0x18004984e  nop     dword ptr [rax+rax+00h]
0x180049853  mov     qword ptr [rdi+rsi*8+48h], 0
0x18004985c  inc     ebx
0x18004985e  cmp     ebx, ebp
0x180049860  jb      short loc_180049836
0x180049862  mov     rcx, rdi
0x180049865  add     rsp, 28h
0x180049869  pop     rdi
0x18004986a  pop     rsi
0x18004986b  pop     rbp
0x18004986c  pop     rbx
0x18004986d  jmp     cs:__imp_CoTaskMemFree
```
