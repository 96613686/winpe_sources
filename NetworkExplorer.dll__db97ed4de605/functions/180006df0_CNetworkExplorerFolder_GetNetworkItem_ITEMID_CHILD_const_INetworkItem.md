# CNetworkExplorerFolder::_GetNetworkItem(_ITEMID_CHILD const *,INetworkItem * *)

- ea: `0x180006df0`
- end: `0x180006e8a`
- name: `?_GetNetworkItem@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAUINetworkItem@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(CNetworkExplorerFolder *__hidden this, const struct _ITEMID_CHILD *, struct INetworkItem **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006030`
- `0x180006d88`

## callees

- `0x180002874`
- `0x180004cf4`
- `0x180006df0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e72`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::_GetNetworkItem(
        CNetworkExplorerFolder *this,
        const struct _ITEMID_CHILD *a2,
        struct INetworkItem **a3)
{
  int FIID; // edi
  struct INetworkItemFactory *v6; // rbx
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF
  struct INetworkItemFactory *v9; // [rsp+48h] [rbp+20h] BYREF

  *a3 = 0;
  pv = 0;
  FIID = CNetworkExplorerFolder::_GetFIID(this, a2, (unsigned __int16 **)&pv);
  if ( FIID >= 0 )
  {
    v9 = 0;
    FIID = CNetworkExplorerFolder::GetFactory(this, &v9);
    if ( FIID >= 0 )
    {
      v6 = v9;
      FIID = (*(__int64 (__fastcall **)(struct INetworkItemFactory *, LPVOID, struct INetworkItem **))(*(_QWORD *)v9 + 72LL))(
               v9,
               pv,
               a3);
      (*(void (__fastcall **)(struct INetworkItemFactory *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    CoTaskMemFree(pv);
  }
  return (unsigned int)FIID;
}

```

## disassembly

```asm
0x180006df0  mov     rax, rsp
0x180006df3  mov     [rax+8], rbx
0x180006df7  mov     [rax+10h], rsi
0x180006dfb  push    rdi
0x180006dfc  sub     rsp, 20h
0x180006e00  mov     rsi, r8
0x180006e03  mov     qword ptr [r8], 0
0x180006e0a  lea     r8, [rax+18h]; unsigned __int16 **
0x180006e0e  mov     qword ptr [rax+18h], 0
0x180006e16  mov     rbx, rcx
0x180006e19  call    ?_GetFIID@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetFIID(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x180006e1e  mov     edi, eax
0x180006e20  test    eax, eax
0x180006e22  js      short loc_180006E78
0x180006e24  lea     rdx, [rsp+28h+arg_18]; struct INetworkItemFactory **
0x180006e29  mov     [rsp+28h+arg_18], 0
0x180006e32  mov     rcx, rbx; this
0x180006e35  call    ?GetFactory@CNetworkExplorerFolder@@QEAAJPEAPEAUINetworkItemFactory@@@Z; CNetworkExplorerFolder::GetFactory(INetworkItemFactory * *)
0x180006e3a  mov     edi, eax
0x180006e3c  test    eax, eax
0x180006e3e  js      short loc_180006E6D
0x180006e40  mov     rbx, [rsp+28h+arg_18]
0x180006e45  mov     r8, rsi
0x180006e48  mov     rdx, [rsp+28h+pv]
0x180006e4d  mov     rcx, rbx
0x180006e50  mov     rax, [rbx]
0x180006e53  mov     rax, [rax+48h]
0x180006e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e5c  mov     edi, eax
0x180006e5e  mov     rcx, rbx
0x180006e61  mov     rax, [rbx]
0x180006e64  mov     rax, [rax+10h]
0x180006e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e6d  mov     rcx, [rsp+28h+pv]; pv
0x180006e72  call    cs:__imp_CoTaskMemFree
0x180006e78  mov     rbx, [rsp+28h+arg_0]
0x180006e7d  mov     eax, edi
0x180006e7f  mov     rsi, [rsp+28h+arg_8]
0x180006e84  add     rsp, 20h
0x180006e88  pop     rdi
0x180006e89  retn
```
