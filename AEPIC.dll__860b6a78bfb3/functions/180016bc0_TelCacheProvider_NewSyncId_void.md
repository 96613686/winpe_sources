# TelCacheProvider::NewSyncId(void)

- ea: `0x180016bc0`
- end: `0x180016d84`
- name: `?NewSyncId@TelCacheProvider@@AEAAXXZ`
- size: `452`
- prototype: `void __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800186cc`
- `0x180018768`
- `0x18001eab4`

## callees

- `0x180005890`
- `0x180010d28`
- `0x180016bc0`
- `0x1800179fc`
- `0x18001aa44`
- `0x1800295dc`
- `0x18002ac34`
- `0x1800eb010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180016c10`
- `RPCRT4!UuidCreate` at `0x180016c10`

## string_xrefs

- `0x180016c5f`: `InventoryCache::SetMetadata failed [%#x]`
- `0x180016cbe`: `InventoryCache::GetItemCount failed [%#x]`
- `0x180016cf3`: `New syncId generated for a non-empty cache so forcing a full sync`
- `0x180016d2f`: `InventoryCache::BatchBegin failed [%#x]`
- `0x180016ccf`: `TelCacheProvider::NewSyncId`
- `0x180016d00`: `TelCacheProvider::NewSyncId`
- `0x180016d53`: `TelCacheProvider::NewSyncId`

## pseudocode

```c
void __fastcall TelCacheProvider::NewSyncId(TelCacheProvider *this)
{
  __int64 v2; // rdx
  int v3; // eax
  int v4; // eax
  __int64 v5; // r14
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  int v11; // [rsp+20h] [rbp-58h]
  int v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  int v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+30h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-40h] BYREF

  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( !*(_QWORD *)this || !*((_QWORD *)this + 11) )
  {
    v14 = -2147024809;
    AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1719, "Object not yet initialized. [%#x]", v14);
    goto LABEL_16;
  }
  Uuid = 0;
  *((_WORD *)this + 4) = 0;
  UuidCreate(&Uuid);
  v3 = AslGuidToString((char *)this + 8, v2, &Uuid);
  if ( v3 )
  {
    v11 = v3;
    AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1734, "AslGuidToString failed [%d]", v11);
  }
  else
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 11) + 80LL))(
           *((_QWORD *)this + 11),
           L"ProviderSyncId",
           (char *)this + 8);
    if ( v4 >= 0 )
    {
      v5 = *(_QWORD *)this;
      if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) )
        (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v5 + 88LL))(v5, (char *)this + 8);
      v6 = *((_QWORD *)this + 11);
      v15 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 32LL))(v6, &v15);
      if ( v7 >= 0 )
      {
        if ( v15 )
        {
          AslLogCallPrintf(
            3,
            "TelCacheProvider::NewSyncId",
            1767,
            "New syncId generated for a non-empty cache so forcing a full sync");
          v8 = *((_QWORD *)this + 11);
          LOBYTE(v9) = 1;
          *((_BYTE *)this + 97) = 1;
          v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 104LL))(v8, v9);
          if ( v10 < 0 )
          {
            v13 = v10;
            AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1773, "InventoryCache::BatchBegin failed [%#x]", v13);
            goto LABEL_16;
          }
        }
      }
      else
      {
        AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1757, "InventoryCache::GetItemCount failed [%#x]", v7);
      }
      TelCacheProvider::ShouldForceFullSync(this, 0);
    }
    else
    {
      v12 = v4;
      AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1742, "InventoryCache::SetMetadata failed [%#x]", v12);
    }
  }
LABEL_16:
  Windows::Compat::Inventory::InventorySynchronization::ReleaseLock((TelCacheProvider *)((char *)this + 104));
}

```

## disassembly

```asm
0x180016bc0  push    rbx
0x180016bc2  push    rsi
0x180016bc3  push    rdi
0x180016bc4  push    r14
0x180016bc6  sub     rsp, 58h
0x180016bca  mov     rax, cs:__security_cookie
0x180016bd1  xor     rax, rsp
0x180016bd4  mov     [rsp+78h+var_30], rax
0x180016bd9  mov     rbx, rcx
0x180016bdc  add     rcx, 68h ; 'h'; this
0x180016be0  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180016be5  cmp     qword ptr [rbx], 0
0x180016be9  jz      loc_180016D3E
0x180016bef  cmp     qword ptr [rbx+58h], 0
0x180016bf4  jz      loc_180016D3E
0x180016bfa  xorps   xmm0, xmm0
0x180016bfd  lea     rdi, [rbx+8]
0x180016c01  xor     eax, eax
0x180016c03  lea     rcx, [rsp+78h+Uuid]; Uuid
0x180016c08  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x180016c0d  mov     [rdi], ax
0x180016c10  call    cs:__imp_UuidCreate
0x180016c16  lea     r8, [rsp+78h+Uuid]
0x180016c1b  mov     rcx, rdi
0x180016c1e  call    AslGuidToString
0x180016c23  test    eax, eax
0x180016c25  jz      short loc_180016C3D
0x180016c27  mov     [rsp+78h+var_58], eax
0x180016c2b  lea     r9, aAslguidtostrin; "AslGuidToString failed [%d]"
0x180016c32  mov     r8d, 6C6h
0x180016c38  jmp     loc_180016D53
0x180016c3d  mov     rcx, [rbx+58h]
0x180016c41  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x180016c48  mov     r8, rdi
0x180016c4b  mov     rax, [rcx]
0x180016c4e  mov     rax, [rax+50h]
0x180016c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c57  test    eax, eax
0x180016c59  jns     short loc_180016C71
0x180016c5b  mov     [rsp+78h+var_58], eax
0x180016c5f  lea     r9, aInventorycache_5; "InventoryCache::SetMetadata failed [%#x"...
0x180016c66  mov     r8d, 6CEh
0x180016c6c  jmp     loc_180016D53
0x180016c71  mov     rcx, [rbx+58h]
0x180016c75  mov     r14, [rbx]
0x180016c78  mov     rax, [rcx]
0x180016c7b  mov     rax, [rax+88h]
0x180016c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c87  test    eax, eax
0x180016c89  jnz     short loc_180016C9D
0x180016c8b  mov     rax, [r14]
0x180016c8e  mov     rdx, rdi
0x180016c91  mov     rcx, r14
0x180016c94  mov     rax, [rax+58h]
0x180016c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c9d  mov     rcx, [rbx+58h]
0x180016ca1  lea     rdx, [rsp+78h+var_48]
0x180016ca6  mov     [rsp+78h+var_48], 0
0x180016cae  mov     rax, [rcx]
0x180016cb1  mov     rax, [rax+20h]
0x180016cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cba  test    eax, eax
0x180016cbc  jns     short loc_180016CEC
0x180016cbe  lea     r9, aInventorycache_2; "InventoryCache::GetItemCount failed [%#"...
0x180016cc5  mov     [rsp+78h+var_58], eax
0x180016cc9  mov     r8d, 6DDh
0x180016ccf  lea     rdx, aTelcacheprovid_11; "TelCacheProvider::NewSyncId"
0x180016cd6  mov     ecx, 1
0x180016cdb  call    AslLogCallPrintf
0x180016ce0  xor     edx, edx; unsigned __int16 *
0x180016ce2  mov     rcx, rbx; this
0x180016ce5  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x180016cea  jmp     short loc_180016D64
0x180016cec  cmp     [rsp+78h+var_48], 0
0x180016cf1  jbe     short loc_180016CE0
0x180016cf3  lea     r9, aNewSyncidGener; "New syncId generated for a non-empty ca"...
0x180016cfa  mov     r8d, 6E7h
0x180016d00  lea     rdx, aTelcacheprovid_11; "TelCacheProvider::NewSyncId"
0x180016d07  mov     ecx, 3
0x180016d0c  call    AslLogCallPrintf
0x180016d11  mov     rcx, [rbx+58h]
0x180016d15  mov     dl, 1
0x180016d17  mov     byte ptr [rbx+61h], 1
0x180016d1b  mov     rax, [rcx]
0x180016d1e  mov     rax, [rax+68h]
0x180016d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d27  test    eax, eax
0x180016d29  jns     short loc_180016CE0
0x180016d2b  mov     [rsp+78h+var_58], eax
0x180016d2f  lea     r9, aInventorycache_9; "InventoryCache::BatchBegin failed [%#x]"
0x180016d36  mov     r8d, 6EDh
0x180016d3c  jmp     short loc_180016D53
0x180016d3e  mov     [rsp+78h+var_58], 80070057h
0x180016d46  lea     r9, aObjectNotYetIn; "Object not yet initialized. [%#x]"
0x180016d4d  mov     r8d, 6B7h
0x180016d53  lea     rdx, aTelcacheprovid_11; "TelCacheProvider::NewSyncId"
0x180016d5a  mov     ecx, 1
0x180016d5f  call    AslLogCallPrintf
0x180016d64  lea     rcx, [rbx+68h]; this
0x180016d68  call    ?ReleaseLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::ReleaseLock(void)
0x180016d6d  mov     rcx, [rsp+78h+var_30]
0x180016d72  xor     rcx, rsp; StackCookie
0x180016d75  call    __security_check_cookie
0x180016d7a  add     rsp, 58h
0x180016d7e  pop     r14
0x180016d80  pop     rdi
0x180016d81  pop     rsi
0x180016d82  pop     rbx
0x180016d83  retn
```
