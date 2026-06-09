# TelCacheProvider::GetItem(IAmiInventoryItem *,bool)

- ea: `0x18001b710`
- end: `0x18001b8e5`
- name: `?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z`
- size: `469`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, struct IAmiInventoryItem *, bool)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015030`
- `0x180016a3c`
- `0x180022178`
- `0x180038b20`

## callees

- `0x180014fa0`
- `0x18001b710`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b8b0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b8b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b8a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b8a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b890`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b890`

## string_xrefs

- `0x18001b7e4`: `InventoryCache::ClearBatchMark failed. [%#x]`
- `0x18001b831`: `Failed to retrieve inventory item %ls from the cache`
- `0x18001b7af`: `TelCacheProvider::GetItem`
- `0x18001b7f5`: `TelCacheProvider::GetItem`
- `0x18001b843`: `TelCacheProvider::GetItem`
- `0x18001b799`: `InventoryCache::OpenItem(%ls) failed. [%#x]`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::GetItem(TelCacheProvider *this, struct IAmiInventoryItem *a2, char a3)
{
  char *v7; // rsi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rbx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  const wchar_t *v13; // rax
  int v14; // eax
  int v15; // edi
  const wchar_t *v16; // rax
  __int64 v17; // rax
  char v18; // cl
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  v7 = (char *)this + 104;
  v19 = 0;
  Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((TelCacheProvider *)((char *)this + 104));
  v8 = *((_QWORD *)this + 11);
  v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v8 + 8LL);
  v10 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
  v11 = v9(v8, v10, &v19);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( a3 && (v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 160LL))(v19), v12 = v14, v14 < 0) )
    {
      AslLogCallPrintf(1, "TelCacheProvider::GetItem", 1032, "InventoryCache::ClearBatchMark failed. [%#x]", v14);
    }
    else
    {
      v15 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, __int64))(*(_QWORD *)a2 + 40LL))(a2, v19);
      if ( v15 )
      {
        v16 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
        AslLogCallPrintf(
          3,
          "TelCacheProvider::GetItem",
          1040,
          "Failed to retrieve inventory item %ls from the cache",
          v16);
        if ( v15 > 0 )
          v12 = (unsigned __int16)v15 | 0x80070000;
        else
          v12 = v15;
      }
    }
  }
  else if ( v11 != -2147024894 )
  {
    v13 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
    AslLogCallPrintf(1, "TelCacheProvider::GetItem", 1022, "InventoryCache::OpenItem(%ls) failed. [%#x]", v13, v12);
  }
  if ( v7[36] )
  {
    v17 = *((_QWORD *)v7 + 3);
    v18 = 0;
    if ( *(_DWORD *)(v17 + 4) == 1 )
    {
      v7[36] = 0;
      v18 = 1;
    }
    --*(_DWORD *)(v17 + 4);
    if ( !v18 )
      goto LABEL_21;
    goto LABEL_20;
  }
  if ( !WaitForSingleObject(*(HANDLE *)v7, 0xFFFFFFFF) )
  {
    --**((_DWORD **)v7 + 3);
    --*((_DWORD *)v7 + 8);
    ReleaseMutex(*(HANDLE *)v7);
LABEL_20:
    SetEvent(*((HANDLE *)v7 + 2));
  }
LABEL_21:
  if ( v19 )
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 11) + 128LL))(*((_QWORD *)this + 11), &v19);
  return v12;
}

```

## disassembly

```asm
0x18001b710  push    rbx
0x18001b712  push    rbp
0x18001b713  push    rsi
0x18001b714  push    rdi
0x18001b715  push    r14
0x18001b717  push    r15
0x18001b719  sub     rsp, 38h
0x18001b71d  cmp     qword ptr [rcx+58h], 0
0x18001b722  mov     r15b, r8b
0x18001b725  mov     r14, rdx
0x18001b728  mov     rbp, rcx
0x18001b72b  jnz     short loc_18001B737
0x18001b72d  mov     eax, 80004002h
0x18001b732  jmp     loc_18001B8D8
0x18001b737  lea     rsi, [rcx+68h]
0x18001b73b  mov     [rsp+68h+arg_0], 0
0x18001b744  mov     rcx, rsi; this
0x18001b747  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x18001b74c  mov     rdi, [rbp+58h]
0x18001b750  mov     rcx, r14
0x18001b753  mov     rax, [rdi]
0x18001b756  mov     rbx, [rax+8]
0x18001b75a  mov     rax, [r14]
0x18001b75d  mov     rax, [rax+8]
0x18001b761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b766  mov     rdx, rax
0x18001b769  lea     r8, [rsp+68h+arg_0]
0x18001b76e  mov     rax, rbx
0x18001b771  mov     rcx, rdi
0x18001b774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b779  mov     ebx, eax
0x18001b77b  test    eax, eax
0x18001b77d  jns     short loc_18001B7C5
0x18001b77f  cmp     eax, 80070002h
0x18001b784  jz      loc_18001B865
0x18001b78a  mov     rcx, [r14]
0x18001b78d  mov     rax, [rcx+8]
0x18001b791  mov     rcx, r14
0x18001b794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b799  lea     r9, aInventorycache_1; "InventoryCache::OpenItem(%ls) failed. ["...
0x18001b7a0  mov     [rsp+68h+var_40], ebx
0x18001b7a4  mov     r8d, 3FEh
0x18001b7aa  mov     [rsp+68h+var_48], rax
0x18001b7af  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x18001b7b6  mov     ecx, 1
0x18001b7bb  call    AslLogCallPrintf
0x18001b7c0  jmp     loc_18001B865
0x18001b7c5  test    r15b, r15b
0x18001b7c8  jz      short loc_18001B808
0x18001b7ca  mov     rcx, [rsp+68h+arg_0]
0x18001b7cf  mov     rax, [rcx]
0x18001b7d2  mov     rax, [rax+0A0h]
0x18001b7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7de  mov     ebx, eax
0x18001b7e0  test    eax, eax
0x18001b7e2  jns     short loc_18001B808
0x18001b7e4  lea     r9, aInventorycache; "InventoryCache::ClearBatchMark failed. "...
0x18001b7eb  mov     dword ptr [rsp+68h+var_48], eax
0x18001b7ef  mov     r8d, 408h
0x18001b7f5  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x18001b7fc  mov     ecx, 1
0x18001b801  call    AslLogCallPrintf
0x18001b806  jmp     short loc_18001B865
0x18001b808  mov     rax, [r14]
0x18001b80b  mov     rcx, r14
0x18001b80e  mov     rdx, [rsp+68h+arg_0]
0x18001b813  mov     rax, [rax+28h]
0x18001b817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b81c  mov     edi, eax
0x18001b81e  test    eax, eax
0x18001b820  jz      short loc_18001B865
0x18001b822  mov     rcx, [r14]
0x18001b825  mov     rax, [rcx+8]
0x18001b829  mov     rcx, r14
0x18001b82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b831  lea     r9, aFailedToRetrie; "Failed to retrieve inventory item %ls f"...
0x18001b838  mov     [rsp+68h+var_48], rax
0x18001b83d  mov     r8d, 410h
0x18001b843  lea     rdx, aTelcacheprovid; "TelCacheProvider::GetItem"
0x18001b84a  mov     ecx, 3
0x18001b84f  call    AslLogCallPrintf
0x18001b854  test    edi, edi
0x18001b856  jg      short loc_18001B85C
0x18001b858  mov     ebx, edi
0x18001b85a  jmp     short loc_18001B865
0x18001b85c  movzx   ebx, di
0x18001b85f  or      ebx, 80070000h
0x18001b865  cmp     byte ptr [rsi+24h], 0
0x18001b869  jz      short loc_18001B888
0x18001b86b  mov     rax, [rsi+18h]
0x18001b86f  xor     cl, cl
0x18001b871  cmp     dword ptr [rax+4], 1
0x18001b875  jnz     short loc_18001B87C
0x18001b877  mov     [rsi+24h], cl
0x18001b87a  mov     cl, 1
0x18001b87c  or      edi, 0FFFFFFFFh
0x18001b87f  add     [rax+4], edi
0x18001b882  test    cl, cl
0x18001b884  jz      short loc_18001B8B6
0x18001b886  jmp     short loc_18001B8AC
0x18001b888  mov     rcx, [rsi]; hHandle
0x18001b88b  or      edi, 0FFFFFFFFh
0x18001b88e  mov     edx, edi; dwMilliseconds
0x18001b890  call    cs:__imp_WaitForSingleObject
0x18001b896  test    eax, eax
0x18001b898  jnz     short loc_18001B8B6
0x18001b89a  mov     rax, [rsi+18h]
0x18001b89e  add     [rax], edi
0x18001b8a0  add     [rsi+20h], edi
0x18001b8a3  mov     rcx, [rsi]; hMutex
0x18001b8a6  call    cs:__imp_ReleaseMutex
0x18001b8ac  mov     rcx, [rsi+10h]; hEvent
0x18001b8b0  call    cs:__imp_SetEvent
0x18001b8b6  cmp     [rsp+68h+arg_0], 0
0x18001b8bc  jz      short loc_18001B8D6
0x18001b8be  mov     rcx, [rbp+58h]
0x18001b8c2  lea     rdx, [rsp+68h+arg_0]
0x18001b8c7  mov     rax, [rcx]
0x18001b8ca  mov     rax, [rax+80h]
0x18001b8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8d6  mov     eax, ebx
0x18001b8d8  add     rsp, 38h
0x18001b8dc  pop     r15
0x18001b8de  pop     r14
0x18001b8e0  pop     rdi
0x18001b8e1  pop     rsi
0x18001b8e2  pop     rbp
0x18001b8e3  pop     rbx
0x18001b8e4  retn
```
