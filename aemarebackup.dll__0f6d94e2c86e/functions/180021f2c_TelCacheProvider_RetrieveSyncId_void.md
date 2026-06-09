# TelCacheProvider::RetrieveSyncId(void)

- ea: `0x180021f2c`
- end: `0x18002200c`
- name: `?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ`
- size: `224`
- prototype: `const unsigned __int16 *__fastcall(TelCacheProvider *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015b48`
- `0x180016a3c`
- `0x180022178`

## callees

- `0x180014fa0`
- `0x180020440`
- `0x180021f2c`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021ffa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021ffa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021ff0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021ff0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021fda`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021fda`

## string_xrefs

- `0x180021f8b`: `InventoryCache::GetMetadata failed [%#x]`
- `0x180021f9c`: `TelCacheProvider::RetrieveSyncId`

## pseudocode

```c
const unsigned __int16 *__fastcall TelCacheProvider::RetrieveSyncId(TelCacheProvider *this)
{
  char *v1; // rbx
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rax
  char v6; // cl
  int v8; // [rsp+60h] [rbp+8h] BYREF

  v1 = (char *)this + 104;
  Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((TelCacheProvider *)((char *)this + 104));
  if ( !*((_WORD *)this + 4) )
  {
    v3 = *((_QWORD *)this + 11);
    v8 = 39;
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, int *))(*(_QWORD *)v3 + 56LL))(
           v3,
           L"ProviderSyncId",
           (char *)this + 8,
           &v8);
    if ( v4 == -2147024894 )
    {
      TelCacheProvider::NewSyncId(this);
    }
    else if ( v4 < 0 )
    {
      AslLogCallPrintf(1, "TelCacheProvider::RetrieveSyncId", 1701, "InventoryCache::GetMetadata failed [%#x]", v4);
    }
  }
  if ( v1[36] )
  {
    v5 = *((_QWORD *)v1 + 3);
    v6 = 0;
    if ( *(_DWORD *)(v5 + 4) == 1 )
    {
      v1[36] = 0;
      v6 = 1;
    }
    --*(_DWORD *)(v5 + 4);
    if ( v6 )
      goto LABEL_13;
  }
  else if ( !WaitForSingleObject(*(HANDLE *)v1, 0xFFFFFFFF) )
  {
    --**((_DWORD **)v1 + 3);
    --*((_DWORD *)v1 + 8);
    ReleaseMutex(*(HANDLE *)v1);
LABEL_13:
    SetEvent(*((HANDLE *)v1 + 2));
  }
  return (const unsigned __int16 *)((char *)this + 8);
}

```

## disassembly

```asm
0x180021f2c  push    rbx
0x180021f2e  push    rbp
0x180021f2f  push    rsi
0x180021f30  push    rdi
0x180021f31  sub     rsp, 38h
0x180021f35  lea     rbx, [rcx+68h]
0x180021f39  mov     rdi, rcx
0x180021f3c  mov     rcx, rbx; this
0x180021f3f  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x180021f44  lea     rsi, [rdi+8]
0x180021f48  xor     ebp, ebp
0x180021f4a  cmp     [rsi], bp
0x180021f4d  jnz     short loc_180021FAD
0x180021f4f  mov     rcx, [rdi+58h]
0x180021f53  lea     r9, [rsp+58h+arg_0]
0x180021f58  mov     [rsp+58h+arg_0], 27h ; '''
0x180021f60  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x180021f67  mov     r8, rsi
0x180021f6a  mov     rax, [rcx]
0x180021f6d  mov     rax, [rax+38h]
0x180021f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f76  cmp     eax, 80070002h
0x180021f7b  jnz     short loc_180021F87
0x180021f7d  mov     rcx, rdi; this
0x180021f80  call    ?NewSyncId@TelCacheProvider@@AEAAXXZ; TelCacheProvider::NewSyncId(void)
0x180021f85  jmp     short loc_180021FAD
0x180021f87  test    eax, eax
0x180021f89  jns     short loc_180021FAD
0x180021f8b  lea     r9, aInventorycache_3; "InventoryCache::GetMetadata failed [%#x"...
0x180021f92  mov     [rsp+58h+var_38], eax
0x180021f96  mov     r8d, 6A5h
0x180021f9c  lea     rdx, aTelcacheprovid_23; "TelCacheProvider::RetrieveSyncId"
0x180021fa3  mov     ecx, 1
0x180021fa8  call    AslLogCallPrintf
0x180021fad  cmp     [rbx+24h], bpl
0x180021fb1  jz      short loc_180021FD2
0x180021fb3  mov     rax, [rbx+18h]
0x180021fb7  mov     cl, bpl
0x180021fba  cmp     dword ptr [rax+4], 1
0x180021fbe  jnz     short loc_180021FC6
0x180021fc0  mov     [rbx+24h], bpl
0x180021fc4  mov     cl, 1
0x180021fc6  or      edi, 0FFFFFFFFh
0x180021fc9  add     [rax+4], edi
0x180021fcc  test    cl, cl
0x180021fce  jz      short loc_180022000
0x180021fd0  jmp     short loc_180021FF6
0x180021fd2  mov     rcx, [rbx]; hHandle
0x180021fd5  or      edi, 0FFFFFFFFh
0x180021fd8  mov     edx, edi; dwMilliseconds
0x180021fda  call    cs:__imp_WaitForSingleObject
0x180021fe0  test    eax, eax
0x180021fe2  jnz     short loc_180022000
0x180021fe4  mov     rdx, [rbx+18h]
0x180021fe8  add     [rdx], edi
0x180021fea  add     [rbx+20h], edi
0x180021fed  mov     rcx, [rbx]; hMutex
0x180021ff0  call    cs:__imp_ReleaseMutex
0x180021ff6  mov     rcx, [rbx+10h]; hEvent
0x180021ffa  call    cs:__imp_SetEvent
0x180022000  mov     rax, rsi
0x180022003  add     rsp, 38h
0x180022007  pop     rdi
0x180022008  pop     rsi
0x180022009  pop     rbp
0x18002200a  pop     rbx
0x18002200b  retn
```
