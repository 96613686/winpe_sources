# CNetworkItemFactory::CreateIDList(INetworkItem *,_ITEMIDLIST * *)

- ea: `0x180003280`
- end: `0x1800032e4`
- name: `?CreateIDList@CNetworkItemFactory@@UEAAJPEAUINetworkItem@@PEAPEFAU_ITEMIDLIST@@@Z`
- size: `100`
- prototype: `__int64 __fastcall(CNetworkItemFactory *__hidden this, struct INetworkItem *, struct _ITEMIDLIST **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003280`
- `0x1800054b0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::CreateIDList(
        CNetworkItemFactory *this,
        struct INetworkItem *a2,
        struct _ITEMIDLIST **a3)
{
  __int64 v3; // rax
  __int64 v5; // rcx
  int ItemID; // ebx
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  v3 = *(_QWORD *)a2;
  v8 = 0;
  ItemID = (*(__int64 (__fastcall **)(struct INetworkItem *, __int64 *))(v3 + 120))(a2, &v8);
  if ( ItemID >= 0 )
  {
    ItemID = CItemIDFactory<DSPROFILEITEM,999534523>::s_CreateItemID(v5, v8, a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)ItemID;
}

```

## disassembly

```asm
0x180003280  mov     [rsp+arg_0], rbx
0x180003285  push    rdi
0x180003286  sub     rsp, 20h
0x18000328a  mov     qword ptr [r8], 0
0x180003291  mov     rcx, rdx
0x180003294  mov     rax, [rdx]
0x180003297  mov     rdi, r8
0x18000329a  lea     rdx, [rsp+28h+arg_8]
0x18000329f  mov     [rsp+28h+arg_8], 0
0x1800032a8  mov     rax, [rax+78h]
0x1800032ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b1  mov     ebx, eax
0x1800032b3  test    eax, eax
0x1800032b5  js      short loc_1800032D7
0x1800032b7  mov     rdx, [rsp+28h+arg_8]
0x1800032bc  mov     r8, rdi
0x1800032bf  call    ?s_CreateItemID@?$CItemIDFactory@UDSPROFILEITEM@@$0DLJDKPLL@@@SAJPEFBUDSPROFILEITEM@@PEAUIPropertyStore@@PEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@@Z; CItemIDFactory<DSPROFILEITEM,999534523>::s_CreateItemID(DSPROFILEITEM const *,IPropertyStore *,_ITEMIDLIST * *,IMalloc *)
0x1800032c4  mov     rcx, [rsp+28h+arg_8]
0x1800032c9  mov     ebx, eax
0x1800032cb  mov     rax, [rcx]
0x1800032ce  mov     rax, [rax+10h]
0x1800032d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d7  mov     eax, ebx
0x1800032d9  mov     rbx, [rsp+28h+arg_0]
0x1800032de  add     rsp, 20h
0x1800032e2  pop     rdi
0x1800032e3  retn
```
