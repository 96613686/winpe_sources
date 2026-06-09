# TelCacheProvider::NewSyncId(void)

- ea: `0x180064f04`
- end: `0x1800650cd`
- name: `?NewSyncId@TelCacheProvider@@AEAAXXZ`
- size: `457`
- prototype: `void __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002da48`
- `0x18004eda4`
- `0x1800658d4`

## callees

- `0x18000fb00`
- `0x18000fbf4`
- `0x1800197d4`
- `0x180059920`
- `0x180064f04`
- `0x180066814`
- `0x18006b25c`
- `0x180130010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180064f54`
- `RPCRT4!UuidCreate` at `0x180064f54`

## string_xrefs

- `0x180064fa8`: `InventoryCache::SetMetadata failed [%#x]`
- `0x180065007`: `InventoryCache::GetItemCount failed [%#x]`
- `0x18006503c`: `New syncId generated for a non-empty cache so forcing a full sync`
- `0x180065078`: `InventoryCache::BatchBegin failed [%#x]`
- `0x180065018`: `TelCacheProvider::NewSyncId`
- `0x180065049`: `TelCacheProvider::NewSyncId`
- `0x18006509c`: `TelCacheProvider::NewSyncId`

## pseudocode

```c
void __fastcall TelCacheProvider::NewSyncId(TelCacheProvider *this)
{
  const char *v2; // r9
  int v3; // r8d
  __int64 v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rdx
  int v8; // [rsp+30h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-40h] BYREF

  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( !*(_QWORD *)this || !*((_QWORD *)this + 11) )
  {
    v2 = "Object not yet initialized. [%#x]";
    v3 = 1719;
    goto LABEL_16;
  }
  Uuid = 0;
  *((_WORD *)this + 4) = 0;
  UuidCreate(&Uuid);
  if ( (unsigned int)AslGuidToString((char *)this + 8, 39) )
  {
    v2 = "AslGuidToString failed [%d]";
    v3 = 1734;
LABEL_16:
    AslLogCallPrintf(1, (unsigned int)"TelCacheProvider::NewSyncId", v3, (_DWORD)v2);
    goto LABEL_17;
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 11) + 80LL))(
         *((_QWORD *)this + 11),
         L"ProviderSyncId",
         (char *)this + 8) < 0 )
  {
    v2 = "InventoryCache::SetMetadata failed [%#x]";
    v3 = 1742;
    goto LABEL_16;
  }
  v4 = *(_QWORD *)this;
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) )
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v4 + 88LL))(v4, (char *)this + 8);
  v5 = *((_QWORD *)this + 11);
  v8 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 32LL))(v5, &v8) >= 0 )
  {
    if ( v8 )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"TelCacheProvider::NewSyncId",
        1767,
        (unsigned int)"New syncId generated for a non-empty cache so forcing a full sync");
      v6 = *((_QWORD *)this + 11);
      LOBYTE(v7) = 1;
      *((_BYTE *)this + 97) = 1;
      if ( (*(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 104LL))(v6, v7) < 0 )
      {
        v2 = "InventoryCache::BatchBegin failed [%#x]";
        v3 = 1773;
        goto LABEL_16;
      }
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"TelCacheProvider::NewSyncId",
      1757,
      (unsigned int)"InventoryCache::GetItemCount failed [%#x]");
  }
  TelCacheProvider::ShouldForceFullSync(this, 0);
LABEL_17:
  Windows::Compat::Inventory::InventorySynchronization::ReleaseLock((TelCacheProvider *)((char *)this + 104));
}

```

## disassembly

```asm
0x180064f04  push    rbx
0x180064f06  push    rsi
0x180064f07  push    rdi
0x180064f08  push    r14
0x180064f0a  sub     rsp, 58h
0x180064f0e  mov     rax, cs:__security_cookie
0x180064f15  xor     rax, rsp
0x180064f18  mov     [rsp+78h+var_30], rax
0x180064f1d  mov     rbx, rcx
0x180064f20  add     rcx, 68h ; 'h'; this
0x180064f24  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180064f29  cmp     qword ptr [rbx], 0
0x180064f2d  jz      loc_180065087
0x180064f33  cmp     qword ptr [rbx+58h], 0
0x180064f38  jz      loc_180065087
0x180064f3e  xorps   xmm0, xmm0
0x180064f41  lea     rdi, [rbx+8]
0x180064f45  xor     eax, eax
0x180064f47  lea     rcx, [rsp+78h+Uuid]; Uuid
0x180064f4c  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x180064f51  mov     [rdi], ax
0x180064f54  call    cs:__imp_UuidCreate
0x180064f5a  lea     r8, [rsp+78h+Uuid]
0x180064f5f  mov     edx, 27h ; '''
0x180064f64  mov     rcx, rdi
0x180064f67  call    AslGuidToString
0x180064f6c  test    eax, eax
0x180064f6e  jz      short loc_180064F86
0x180064f70  mov     [rsp+78h+var_58], eax
0x180064f74  lea     r9, aAslguidtostrin_0; "AslGuidToString failed [%d]"
0x180064f7b  mov     r8d, 6C6h
0x180064f81  jmp     loc_18006509C
0x180064f86  mov     rcx, [rbx+58h]
0x180064f8a  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x180064f91  mov     r8, rdi
0x180064f94  mov     rax, [rcx]
0x180064f97  mov     rax, [rax+50h]
0x180064f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064fa0  test    eax, eax
0x180064fa2  jns     short loc_180064FBA
0x180064fa4  mov     [rsp+78h+var_58], eax
0x180064fa8  lea     r9, aInventorycache_6; "InventoryCache::SetMetadata failed [%#x"...
0x180064faf  mov     r8d, 6CEh
0x180064fb5  jmp     loc_18006509C
0x180064fba  mov     rcx, [rbx+58h]
0x180064fbe  mov     r14, [rbx]
0x180064fc1  mov     rax, [rcx]
0x180064fc4  mov     rax, [rax+88h]
0x180064fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064fd0  test    eax, eax
0x180064fd2  jnz     short loc_180064FE6
0x180064fd4  mov     rax, [r14]
0x180064fd7  mov     rdx, rdi
0x180064fda  mov     rcx, r14
0x180064fdd  mov     rax, [rax+58h]
0x180064fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064fe6  mov     rcx, [rbx+58h]
0x180064fea  lea     rdx, [rsp+78h+var_48]
0x180064fef  mov     [rsp+78h+var_48], 0
0x180064ff7  mov     rax, [rcx]
0x180064ffa  mov     rax, [rax+20h]
0x180064ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065003  test    eax, eax
0x180065005  jns     short loc_180065035
0x180065007  lea     r9, aInventorycache_2; "InventoryCache::GetItemCount failed [%#"...
0x18006500e  mov     [rsp+78h+var_58], eax
0x180065012  mov     r8d, 6DDh
0x180065018  lea     rdx, aTelcacheprovid_12; "TelCacheProvider::NewSyncId"
0x18006501f  mov     ecx, 1
0x180065024  call    AslLogCallPrintf
0x180065029  xor     edx, edx; unsigned __int16 *
0x18006502b  mov     rcx, rbx; this
0x18006502e  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x180065033  jmp     short loc_1800650AD
0x180065035  cmp     [rsp+78h+var_48], 0
0x18006503a  jbe     short loc_180065029
0x18006503c  lea     r9, aNewSyncidGener; "New syncId generated for a non-empty ca"...
0x180065043  mov     r8d, 6E7h
0x180065049  lea     rdx, aTelcacheprovid_12; "TelCacheProvider::NewSyncId"
0x180065050  mov     ecx, 3
0x180065055  call    AslLogCallPrintf
0x18006505a  mov     rcx, [rbx+58h]
0x18006505e  mov     dl, 1
0x180065060  mov     byte ptr [rbx+61h], 1
0x180065064  mov     rax, [rcx]
0x180065067  mov     rax, [rax+68h]
0x18006506b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065070  test    eax, eax
0x180065072  jns     short loc_180065029
0x180065074  mov     [rsp+78h+var_58], eax
0x180065078  lea     r9, aInventorycache_10; "InventoryCache::BatchBegin failed [%#x]"
0x18006507f  mov     r8d, 6EDh
0x180065085  jmp     short loc_18006509C
0x180065087  mov     [rsp+78h+var_58], 80070057h
0x18006508f  lea     r9, aObjectNotYetIn; "Object not yet initialized. [%#x]"
0x180065096  mov     r8d, 6B7h
0x18006509c  lea     rdx, aTelcacheprovid_12; "TelCacheProvider::NewSyncId"
0x1800650a3  mov     ecx, 1
0x1800650a8  call    AslLogCallPrintf
0x1800650ad  lea     rcx, [rbx+68h]; this
0x1800650b1  call    ?ReleaseLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::ReleaseLock(void)
0x1800650b6  mov     rcx, [rsp+78h+var_30]
0x1800650bb  xor     rcx, rsp; StackCookie
0x1800650be  call    __security_check_cookie
0x1800650c3  add     rsp, 58h
0x1800650c7  pop     r14
0x1800650c9  pop     rdi
0x1800650ca  pop     rsi
0x1800650cb  pop     rbx
0x1800650cc  retn
```
