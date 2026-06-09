# TelCacheProvider::BatchBegin(void)

- ea: `0x180016828`
- end: `0x180016a35`
- name: `?BatchBegin@TelCacheProvider@@QEAAJXZ`
- size: `525`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800257a8`

## callees

- `0x180014ed4`
- `0x180016828`
- `0x18002435c`
- `0x180024458`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016a1f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016a1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016a15`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016a15`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800169ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800169ff`

## string_xrefs

- `0x180016863`: `BatchBegin called but batch already in progress [%#x]`
- `0x180016874`: `TelCacheProvider::BatchBegin`
- `0x1800168f0`: `InventoryCache::GetMetadata [%#x]`
- `0x180016901`: `TelCacheProvider::GetVersion`
- `0x18001695f`: `InventoryCache::SetMetadata failed [%#x]`
- `0x1800169bc`: `InventoryCache::BatchBegin failed [%#x]`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::BatchBegin(TelCacheProvider *this)
{
  char *v3; // rdi
  unsigned int v4; // ebp
  __int64 v5; // rcx
  int v6; // eax
  int v7; // r14d
  TelCacheProvider *v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  char v13; // cl
  __int64 v14; // [rsp+20h] [rbp-48h]
  unsigned int v15; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  v3 = (char *)this + 104;
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( *((_BYTE *)this + 96) )
  {
    v4 = -2147418113;
    AslLogCallPrintf(
      1,
      "TelCacheProvider::BatchBegin",
      1074,
      "BatchBegin called but batch already in progress [%#x]",
      -2147418113);
  }
  else
  {
    if ( *((_BYTE *)this + 97)
      && *(_QWORD *)this
      && (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this) )
    {
      v5 = *((_QWORD *)this + 11);
      v15 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *))(*(_QWORD *)v5 + 72LL))(
             v5,
             L"ProviderVersion",
             &v15);
      v7 = v6;
      if ( v6 == -2147024894 )
      {
        v15 = 0;
        v7 = 1;
      }
      else if ( v6 >= 0 )
      {
        v7 = 0;
      }
      else
      {
        AslLogCallPrintf(1, "TelCacheProvider::GetVersion", 1801, "InventoryCache::GetMetadata [%#x]", v6);
      }
      v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 120LL))(*((_QWORD *)this + 11));
      if ( *((_WORD *)this + 4) )
      {
        TelCacheProvider::ShouldForceFullSync(this, 0);
        v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 11) + 80LL))(
               *((_QWORD *)this + 11),
               L"ProviderSyncId",
               (char *)this + 8);
        v4 = v9;
        if ( v9 < 0 )
        {
          LODWORD(v14) = v9;
          AslLogCallPrintf(1, "TelCacheProvider::BatchBegin", 1101, "InventoryCache::SetMetadata failed [%#x]", v14);
          goto LABEL_23;
        }
      }
      if ( !v7 )
      {
        v10 = TelCacheProvider::SetVersion(v8, *((struct Windows::Compat::Inventory::InventoryCache **)this + 11), v15);
        v4 = v10;
        if ( v10 < 0 )
        {
          LODWORD(v14) = v10;
          AslLogCallPrintf(1, "TelCacheProvider::BatchBegin", 1111, "SetVersion failed [%#x]", v14);
          goto LABEL_23;
        }
      }
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 11) + 104LL))(*((_QWORD *)this + 11), 0);
      v4 = v11;
      if ( v11 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::BatchBegin", 1121, "InventoryCache::BatchBegin failed [%#x]", v11);
        goto LABEL_23;
      }
    }
    *((_BYTE *)this + 96) = 1;
  }
LABEL_23:
  if ( v3[36] )
  {
    v12 = *((_QWORD *)v3 + 3);
    v13 = 0;
    if ( *(_DWORD *)(v12 + 4) == 1 )
    {
      v3[36] = 0;
      v13 = 1;
    }
    --*(_DWORD *)(v12 + 4);
    if ( !v13 )
      return v4;
    goto LABEL_30;
  }
  if ( !WaitForSingleObject(*(HANDLE *)v3, 0xFFFFFFFF) )
  {
    --**((_DWORD **)v3 + 3);
    --*((_DWORD *)v3 + 8);
    ReleaseMutex(*(HANDLE *)v3);
LABEL_30:
    SetEvent(*((HANDLE *)v3 + 2));
  }
  return v4;
}

```

## disassembly

```asm
0x180016828  push    rbx
0x18001682a  push    rbp
0x18001682b  push    rdi
0x18001682c  push    r12
0x18001682e  push    r14
0x180016830  push    r15
0x180016832  sub     rsp, 38h
0x180016836  xor     r12d, r12d
0x180016839  mov     rbx, rcx
0x18001683c  cmp     [rcx+58h], r12
0x180016840  jnz     short loc_18001684C
0x180016842  mov     eax, 80004002h
0x180016847  jmp     loc_180016A27
0x18001684c  lea     rdi, [rcx+68h]
0x180016850  mov     rcx, rdi; this
0x180016853  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180016858  cmp     [rbx+60h], r12b
0x18001685c  jz      short loc_18001688A
0x18001685e  mov     ebp, 8000FFFFh
0x180016863  lea     r9, aBatchbeginCall; "BatchBegin called but batch already in "...
0x18001686a  mov     dword ptr [rsp+68h+var_48], ebp
0x18001686e  mov     r8d, 432h
0x180016874  lea     rdx, aTelcacheprovid_0; "TelCacheProvider::BatchBegin"
0x18001687b  mov     ecx, 1
0x180016880  call    AslLogCallPrintf
0x180016885  jmp     loc_1800169D2
0x18001688a  cmp     [rbx+61h], r12b
0x18001688e  jz      loc_1800169A0
0x180016894  mov     rcx, [rbx]
0x180016897  test    rcx, rcx
0x18001689a  jz      loc_1800169A0
0x1800168a0  mov     rax, [rcx]
0x1800168a3  mov     rax, [rax+38h]
0x1800168a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168ac  test    al, al
0x1800168ae  jz      loc_1800169A0
0x1800168b4  mov     rcx, [rbx+58h]
0x1800168b8  lea     r8, [rsp+68h+arg_0]
0x1800168bd  mov     [rsp+68h+arg_0], r12d
0x1800168c2  lea     rdx, aProviderversio; "ProviderVersion"
0x1800168c9  mov     rax, [rcx]
0x1800168cc  mov     rax, [rax+48h]
0x1800168d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168d5  mov     r14d, eax
0x1800168d8  cmp     eax, 80070002h
0x1800168dd  jnz     short loc_1800168EC
0x1800168df  mov     [rsp+68h+arg_0], r12d
0x1800168e4  mov     r14d, 1
0x1800168ea  jmp     short loc_180016917
0x1800168ec  test    eax, eax
0x1800168ee  jns     short loc_180016914
0x1800168f0  lea     r9, aInventorycache_0; "InventoryCache::GetMetadata [%#x]"
0x1800168f7  mov     dword ptr [rsp+68h+var_48], eax
0x1800168fb  mov     r8d, 709h
0x180016901  lea     rdx, aTelcacheprovid_30; "TelCacheProvider::GetVersion"
0x180016908  mov     ecx, 1
0x18001690d  call    AslLogCallPrintf
0x180016912  jmp     short loc_180016917
0x180016914  mov     r14d, r12d
0x180016917  mov     rcx, [rbx+58h]
0x18001691b  mov     rax, [rcx]
0x18001691e  mov     rax, [rax+78h]
0x180016922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016927  mov     ebp, eax
0x180016929  cmp     [rbx+8], r12w
0x18001692e  jz      short loc_180016971
0x180016930  xor     edx, edx; unsigned __int16 *
0x180016932  mov     rcx, rbx; this
0x180016935  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x18001693a  mov     rcx, [rbx+58h]
0x18001693e  lea     r8, [rbx+8]
0x180016942  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x180016949  mov     rax, [rcx]
0x18001694c  mov     rax, [rax+50h]
0x180016950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016955  mov     ebp, eax
0x180016957  test    eax, eax
0x180016959  jns     short loc_180016971
0x18001695b  mov     dword ptr [rsp+68h+var_48], eax
0x18001695f  lea     r9, aInventorycache_4; "InventoryCache::SetMetadata failed [%#x"...
0x180016966  mov     r8d, 44Dh
0x18001696c  jmp     loc_180016874
0x180016971  test    r14d, r14d
0x180016974  jnz     short loc_1800169CE
0x180016976  mov     r8d, [rsp+68h+arg_0]; unsigned int
0x18001697b  mov     rdx, [rbx+58h]; struct Windows::Compat::Inventory::InventoryCache *
0x18001697f  call    ?SetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@K@Z; TelCacheProvider::SetVersion(Windows::Compat::Inventory::InventoryCache *,ulong)
0x180016984  mov     ebp, eax
0x180016986  test    eax, eax
0x180016988  jns     short loc_1800169CE
0x18001698a  mov     dword ptr [rsp+68h+var_48], eax
0x18001698e  lea     r9, aSetversionFail; "SetVersion failed [%#x]"
0x180016995  mov     r8d, 457h
0x18001699b  jmp     loc_180016874
0x1800169a0  mov     rcx, [rbx+58h]
0x1800169a4  xor     edx, edx
0x1800169a6  mov     rax, [rcx]
0x1800169a9  mov     rax, [rax+68h]
0x1800169ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169b2  mov     ebp, eax
0x1800169b4  test    eax, eax
0x1800169b6  jns     short loc_1800169CE
0x1800169b8  mov     dword ptr [rsp+68h+var_48], eax
0x1800169bc  lea     r9, aInventorycache_10; "InventoryCache::BatchBegin failed [%#x]"
0x1800169c3  mov     r8d, 461h
0x1800169c9  jmp     loc_180016874
0x1800169ce  mov     byte ptr [rbx+60h], 1
0x1800169d2  cmp     [rdi+24h], r12b
0x1800169d6  jz      short loc_1800169F7
0x1800169d8  mov     rax, [rdi+18h]
0x1800169dc  mov     cl, r12b
0x1800169df  cmp     dword ptr [rax+4], 1
0x1800169e3  jnz     short loc_1800169EB
0x1800169e5  mov     [rdi+24h], r12b
0x1800169e9  mov     cl, 1
0x1800169eb  or      ebx, 0FFFFFFFFh
0x1800169ee  add     [rax+4], ebx
0x1800169f1  test    cl, cl
0x1800169f3  jz      short loc_180016A25
0x1800169f5  jmp     short loc_180016A1B
0x1800169f7  mov     rcx, [rdi]; hHandle
0x1800169fa  or      ebx, 0FFFFFFFFh
0x1800169fd  mov     edx, ebx; dwMilliseconds
0x1800169ff  call    cs:__imp_WaitForSingleObject
0x180016a05  test    eax, eax
0x180016a07  jnz     short loc_180016A25
0x180016a09  mov     rax, [rdi+18h]
0x180016a0d  add     [rax], ebx
0x180016a0f  add     [rdi+20h], ebx
0x180016a12  mov     rcx, [rdi]; hMutex
0x180016a15  call    cs:__imp_ReleaseMutex
0x180016a1b  mov     rcx, [rdi+10h]; hEvent
0x180016a1f  call    cs:__imp_SetEvent
0x180016a25  mov     eax, ebp
0x180016a27  add     rsp, 38h
0x180016a2b  pop     r15
0x180016a2d  pop     r14
0x180016a2f  pop     r12
0x180016a31  pop     rdi
0x180016a32  pop     rbp
0x180016a33  pop     rbx
0x180016a34  retn
```
