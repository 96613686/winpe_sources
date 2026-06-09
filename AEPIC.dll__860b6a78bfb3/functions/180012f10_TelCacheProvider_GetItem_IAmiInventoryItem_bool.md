# TelCacheProvider::GetItem(IAmiInventoryItem *,bool)

- ea: `0x180012f10`
- end: `0x18001309a`
- name: `?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z`
- size: `394`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, struct IAmiInventoryItem *, bool)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018768`
- `0x18001ce30`
- `0x18001eab4`
- `0x1800c4280`
- `0x1800d18a0`

## callees

- `0x180010df4`
- `0x180012f10`
- `0x1800179fc`
- `0x1800295dc`
- `0x1800eb010`

## string_xrefs

- `0x180012fe1`: `InventoryCache::ClearBatchMark failed. [%#x]`
- `0x18001302e`: `Failed to retrieve inventory item %ls from the cache`
- `0x180012fac`: `TelCacheProvider::GetItem`
- `0x180012ff2`: `TelCacheProvider::GetItem`
- `0x180013040`: `TelCacheProvider::GetItem`
- `0x180012f96`: `InventoryCache::OpenItem(%ls) failed. [%#x]`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::GetItem(TelCacheProvider *this, struct IAmiInventoryItem *a2, char a3)
{
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, __int64 *); // rbx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  const wchar_t *v12; // rax
  int v13; // eax
  int v14; // edi
  const wchar_t *v15; // rax
  __int64 v16; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  v16 = 0;
  Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((TelCacheProvider *)((char *)this + 104));
  v7 = *((_QWORD *)this + 11);
  v8 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v7 + 8LL);
  v9 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
  v10 = v8(v7, v9, &v16);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( a3 && (v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 160LL))(v16), v11 = v13, v13 < 0) )
    {
      AslLogCallPrintf(1, "TelCacheProvider::GetItem", 1032, "InventoryCache::ClearBatchMark failed. [%#x]", v13);
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, __int64))(*(_QWORD *)a2 + 40LL))(a2, v16);
      if ( v14 )
      {
        v15 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
        AslLogCallPrintf(
          3,
          "TelCacheProvider::GetItem",
          1040,
          "Failed to retrieve inventory item %ls from the cache",
          v15);
        if ( v14 > 0 )
          v11 = (unsigned __int16)v14 | 0x80070000;
        else
          v11 = v14;
      }
    }
  }
  else if ( v10 != -2147024894 )
  {
    v12 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
    AslLogCallPrintf(1, "TelCacheProvider::GetItem", 1022, "InventoryCache::OpenItem(%ls) failed. [%#x]", v12, v11);
  }
  Windows::Compat::Inventory::InventorySynchronization::ReleaseLock((TelCacheProvider *)((char *)this + 104));
  if ( v16 )
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 11) + 128LL))(*((_QWORD *)this + 11), &v16);
  return v11;
}

```

## disassembly

```asm
0x180012f10  push    rbx
0x180012f12  push    rbp
0x180012f13  push    rsi
0x180012f14  push    rdi
0x180012f15  push    r14
0x180012f17  push    r15
0x180012f19  sub     rsp, 38h
0x180012f1d  cmp     qword ptr [rcx+58h], 0
0x180012f22  mov     r14b, r8b
0x180012f25  mov     rsi, rdx
0x180012f28  mov     rbp, rcx
0x180012f2b  jnz     short loc_180012F37
0x180012f2d  mov     eax, 80004002h
0x180012f32  jmp     loc_18001308D
0x180012f37  add     rcx, 68h ; 'h'; this
0x180012f3b  mov     [rsp+68h+arg_0], 0
0x180012f44  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x180012f49  mov     rdi, [rbp+58h]
0x180012f4d  mov     rcx, rsi
0x180012f50  mov     rax, [rdi]
0x180012f53  mov     rbx, [rax+8]
0x180012f57  mov     rax, [rsi]
0x180012f5a  mov     rax, [rax+8]
0x180012f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f63  mov     rdx, rax
0x180012f66  lea     r8, [rsp+68h+arg_0]
0x180012f6b  mov     rax, rbx
0x180012f6e  mov     rcx, rdi
0x180012f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f76  mov     ebx, eax
0x180012f78  test    eax, eax
0x180012f7a  jns     short loc_180012FC2
0x180012f7c  cmp     eax, 80070002h
0x180012f81  jz      loc_180013062
0x180012f87  mov     rcx, [rsi]
0x180012f8a  mov     rax, [rcx+8]
0x180012f8e  mov     rcx, rsi
0x180012f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f96  lea     r9, aInventorycache_1; "InventoryCache::OpenItem(%ls) failed. ["...
0x180012f9d  mov     [rsp+68h+var_40], ebx
0x180012fa1  mov     r8d, 3FEh
0x180012fa7  mov     [rsp+68h+var_48], rax
0x180012fac  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x180012fb3  mov     ecx, 1
0x180012fb8  call    AslLogCallPrintf
0x180012fbd  jmp     loc_180013062
0x180012fc2  test    r14b, r14b
0x180012fc5  jz      short loc_180013005
0x180012fc7  mov     rcx, [rsp+68h+arg_0]
0x180012fcc  mov     rax, [rcx]
0x180012fcf  mov     rax, [rax+0A0h]
0x180012fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fdb  mov     ebx, eax
0x180012fdd  test    eax, eax
0x180012fdf  jns     short loc_180013005
0x180012fe1  lea     r9, aInventorycache; "InventoryCache::ClearBatchMark failed. "...
0x180012fe8  mov     dword ptr [rsp+68h+var_48], eax
0x180012fec  mov     r8d, 408h
0x180012ff2  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x180012ff9  mov     ecx, 1
0x180012ffe  call    AslLogCallPrintf
0x180013003  jmp     short loc_180013062
0x180013005  mov     rax, [rsi]
0x180013008  mov     rcx, rsi
0x18001300b  mov     rdx, [rsp+68h+arg_0]
0x180013010  mov     rax, [rax+28h]
0x180013014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013019  mov     edi, eax
0x18001301b  test    eax, eax
0x18001301d  jz      short loc_180013062
0x18001301f  mov     rcx, [rsi]
0x180013022  mov     rax, [rcx+8]
0x180013026  mov     rcx, rsi
0x180013029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001302e  lea     r9, aFailedToRetrie; "Failed to retrieve inventory item %ls f"...
0x180013035  mov     [rsp+68h+var_48], rax
0x18001303a  mov     r8d, 410h
0x180013040  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x180013047  mov     ecx, 3
0x18001304c  call    AslLogCallPrintf
0x180013051  test    edi, edi
0x180013053  jg      short loc_180013059
0x180013055  mov     ebx, edi
0x180013057  jmp     short loc_180013062
0x180013059  movzx   ebx, di
0x18001305c  or      ebx, 80070000h
0x180013062  lea     rcx, [rbp+68h]; this
0x180013066  call    ?ReleaseLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::ReleaseLock(void)
0x18001306b  cmp     [rsp+68h+arg_0], 0
0x180013071  jz      short loc_18001308B
0x180013073  mov     rcx, [rbp+58h]
0x180013077  lea     rdx, [rsp+68h+arg_0]
0x18001307c  mov     rax, [rcx]
0x18001307f  mov     rax, [rax+80h]
0x180013086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001308b  mov     eax, ebx
0x18001308d  add     rsp, 38h
0x180013091  pop     r15
0x180013093  pop     r14
0x180013095  pop     rdi
0x180013096  pop     rsi
0x180013097  pop     rbp
0x180013098  pop     rbx
0x180013099  retn
```
