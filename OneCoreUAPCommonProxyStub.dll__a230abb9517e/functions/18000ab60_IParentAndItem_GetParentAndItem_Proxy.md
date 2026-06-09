# IParentAndItem_GetParentAndItem_Proxy

- ea: `0x18000ab60`
- end: `0x18000ac21`
- name: `IParentAndItem_GetParentAndItem_Proxy`
- size: `193`
- prototype: `HRESULT __stdcall(IParentAndItem *This, LPITEMIDLIST *ppidlParent, IShellFolder **ppsf, LPITEMIDLIST *ppidlChild)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ab60`
- `0x18000c010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000abbb`
- `RPCRT4!NdrClientCall3` at `0x18000abbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac0d`

## pseudocode

```c
HRESULT __stdcall IParentAndItem_GetParentAndItem_Proxy(
        IParentAndItem *This,
        LPITEMIDLIST *ppidlParent,
        IShellFolder **ppsf,
        LPITEMIDLIST *ppidlChild)
{
  HRESULT Pointer; // r14d
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF
  IShellFolder *v10; // [rsp+80h] [rbp+40h] BYREF
  LPVOID v11; // [rsp+88h] [rbp+48h] BYREF

  pv = 0;
  v10 = 0;
  v11 = 0;
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1801F62E8, 4u, 0, This, &pv, &v10, &v11).Pointer;
  if ( ppidlParent )
    *ppidlParent = (LPITEMIDLIST)pv;
  else
    CoTaskMemFree(pv);
  if ( ppsf )
  {
    *ppsf = v10;
  }
  else if ( v10 )
  {
    ((void (__fastcall *)(IShellFolder *))v10->lpVtbl->Release)(v10);
  }
  if ( ppidlChild )
    *ppidlChild = (LPITEMIDLIST)v11;
  else
    CoTaskMemFree(v11);
  return Pointer;
}

```

## disassembly

```asm
0x18000ab60  push    rbp
0x18000ab62  push    rbx
0x18000ab63  push    rsi
0x18000ab64  push    rdi
0x18000ab65  push    r14
0x18000ab67  mov     rbp, rsp
0x18000ab6a  sub     rsp, 40h
0x18000ab6e  lea     rax, [rbp+arg_18]
0x18000ab72  mov     [rbp+pv], 0
0x18000ab7a  mov     [rsp+40h+var_10], rax
0x18000ab7f  mov     rdi, r8
0x18000ab82  xor     r8d, r8d; pReturnValue
0x18000ab85  mov     [rbp+arg_10], 0
0x18000ab8d  lea     rax, [rbp+arg_10]
0x18000ab91  mov     [rbp+arg_18], 0
0x18000ab99  mov     [rsp+40h+var_18], rax
0x18000ab9e  mov     rbx, r9
0x18000aba1  lea     rax, [rbp+pv]
0x18000aba5  mov     rsi, rdx
0x18000aba8  mov     r9, rcx
0x18000abab  mov     [rsp+40h+var_20], rax
0x18000abb0  lea     edx, [r8+4]; nProcNum
0x18000abb4  lea     rcx, stru_1801F62E8; pProxyInfo
0x18000abbb  call    cs:__imp_NdrClientCall3
0x18000abc1  mov     rcx, [rbp+pv]; pv
0x18000abc5  mov     r14, rax
0x18000abc8  test    rsi, rsi
0x18000abcb  jz      short loc_18000ABD2
0x18000abcd  mov     [rsi], rcx
0x18000abd0  jmp     short loc_18000ABD8
0x18000abd2  call    cs:__imp_CoTaskMemFree
0x18000abd8  test    rdi, rdi
0x18000abdb  jz      short loc_18000ABE6
0x18000abdd  mov     rax, [rbp+arg_10]
0x18000abe1  mov     [rdi], rax
0x18000abe4  jmp     short loc_18000ABFB
0x18000abe6  mov     rcx, [rbp+arg_10]
0x18000abea  test    rcx, rcx
0x18000abed  jz      short loc_18000ABFB
0x18000abef  mov     rax, [rcx]
0x18000abf2  mov     rax, [rax+10h]
0x18000abf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abfb  test    rbx, rbx
0x18000abfe  jz      short loc_18000AC09
0x18000ac00  mov     rax, [rbp+arg_18]
0x18000ac04  mov     [rbx], rax
0x18000ac07  jmp     short loc_18000AC13
0x18000ac09  mov     rcx, [rbp+arg_18]; pv
0x18000ac0d  call    cs:__imp_CoTaskMemFree
0x18000ac13  mov     eax, r14d
0x18000ac16  add     rsp, 40h
0x18000ac1a  pop     r14
0x18000ac1c  pop     rdi
0x18000ac1d  pop     rsi
0x18000ac1e  pop     rbx
0x18000ac1f  pop     rbp
0x18000ac20  retn
```
