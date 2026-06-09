# IShellFolder_SetNameOf_Proxy

- ea: `0x18000ac70`
- end: `0x18000acde`
- name: `IShellFolder_SetNameOf_Proxy`
- size: `110`
- prototype: `HRESULT __stdcall(IShellFolder *This, HWND hwnd, LPCITEMIDLIST pidl, LPCWSTR pszName, SHGDNF uFlags, LPITEMIDLIST *ppidlOut)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ac70`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000acb0`
- `RPCRT4!NdrClientCall3` at `0x18000acb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000acd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000acd0`

## pseudocode

```c
HRESULT __stdcall IShellFolder_SetNameOf_Proxy(
        IShellFolder *This,
        HWND hwnd,
        LPCITEMIDLIST pidl,
        LPCWSTR pszName,
        SHGDNF uFlags,
        LPITEMIDLIST *ppidlOut)
{
  HRESULT Pointer; // ebx
  LPVOID pv[3]; // [rsp+50h] [rbp-18h] BYREF

  pv[0] = 0;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&stru_180209CA0,
                            0xCu,
                            0,
                            This,
                            hwnd,
                            pidl,
                            pszName,
                            uFlags,
                            pv).Pointer;
  if ( ppidlOut )
    *ppidlOut = (LPITEMIDLIST)pv[0];
  else
    CoTaskMemFree(pv[0]);
  return Pointer;
}

```

## disassembly

```asm
0x18000ac70  mov     r11, rsp
0x18000ac73  push    rbx
0x18000ac74  sub     rsp, 60h
0x18000ac78  lea     rax, [r11-18h]
0x18000ac7c  mov     qword ptr [r11-18h], 0
0x18000ac84  mov     [r11-28h], rax
0x18000ac88  mov     eax, [rsp+68h+uFlags]
0x18000ac8f  mov     [rsp+68h+var_30], eax
0x18000ac93  mov     [r11-38h], r9
0x18000ac97  mov     r9, rcx
0x18000ac9a  mov     [r11-40h], r8
0x18000ac9e  lea     rcx, stru_180209CA0; pProxyInfo
0x18000aca5  xor     r8d, r8d; pReturnValue
0x18000aca8  mov     [r11-48h], rdx
0x18000acac  lea     edx, [r8+0Ch]; nProcNum
0x18000acb0  call    cs:__imp_NdrClientCall3
0x18000acb6  mov     rdx, [rsp+68h+ppidlOut]
0x18000acbe  mov     rbx, rax
0x18000acc1  mov     rcx, [rsp+68h+pv]; pv
0x18000acc6  test    rdx, rdx
0x18000acc9  jz      short loc_18000ACD0
0x18000accb  mov     [rdx], rcx
0x18000acce  jmp     short loc_18000ACD6
0x18000acd0  call    cs:__imp_CoTaskMemFree
0x18000acd6  mov     eax, ebx
0x18000acd8  add     rsp, 60h
0x18000acdc  pop     rbx
0x18000acdd  retn
```
