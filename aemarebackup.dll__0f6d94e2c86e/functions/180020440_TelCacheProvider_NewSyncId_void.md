# TelCacheProvider::NewSyncId(void)

- ea: `0x180020440`
- end: `0x18002064f`
- name: `?NewSyncId@TelCacheProvider@@AEAAXXZ`
- size: `527`
- prototype: `void __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180016a3c`
- `0x180021f2c`
- `0x180022178`

## callees

- `0x180004ea0`
- `0x180014ed4`
- `0x180020440`
- `0x180024458`
- `0x18004bf64`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020632`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020632`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020628`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020628`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020612`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020612`
- `RPCRT4!UuidCreate` at `0x180020493`
- `RPCRT4!UuidCreate` at `0x180020493`

## string_xrefs

- `0x1800204e2`: `InventoryCache::SetMetadata failed [%#x]`
- `0x180020541`: `InventoryCache::GetItemCount failed [%#x]`
- `0x180020576`: `New syncId generated for a non-empty cache so forcing a full sync`
- `0x1800205b2`: `InventoryCache::BatchBegin failed [%#x]`
- `0x180020552`: `TelCacheProvider::NewSyncId`
- `0x180020583`: `TelCacheProvider::NewSyncId`
- `0x1800205d6`: `TelCacheProvider::NewSyncId`

## pseudocode

```c
void __fastcall TelCacheProvider::NewSyncId(TelCacheProvider *this)
{
  char *v1; // rbx
  __int64 v3; // rdx
  int v4; // eax
  int v5; // eax
  __int64 v6; // r14
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rax
  char v13; // cl
  int v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+20h] [rbp-58h]
  int v16; // [rsp+20h] [rbp-58h]
  int v17; // [rsp+20h] [rbp-58h]
  int v18; // [rsp+30h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-40h] BYREF

  v1 = (char *)this + 104;
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( *(_QWORD *)this && *((_QWORD *)this + 11) )
  {
    Uuid = 0;
    *((_WORD *)this + 4) = 0;
    UuidCreate(&Uuid);
    v4 = AslGuidToString((char *)this + 8, v3, &Uuid);
    if ( v4 )
    {
      v14 = v4;
      AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1734, "AslGuidToString failed [%d]", v14);
      goto LABEL_16;
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 11) + 80LL))(
           *((_QWORD *)this + 11),
           L"ProviderSyncId",
           (char *)this + 8);
    if ( v5 < 0 )
    {
      v15 = v5;
      AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1742, "InventoryCache::SetMetadata failed [%#x]", v15);
      goto LABEL_16;
    }
    v6 = *(_QWORD *)this;
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) )
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v6 + 88LL))(v6, (char *)this + 8);
    v7 = *((_QWORD *)this + 11);
    v18 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 32LL))(v7, &v18);
    if ( v8 < 0 )
    {
      AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1757, "InventoryCache::GetItemCount failed [%#x]", v8);
LABEL_11:
      TelCacheProvider::ShouldForceFullSync(this, 0);
      goto LABEL_16;
    }
    if ( !v18 )
      goto LABEL_11;
    AslLogCallPrintf(
      3,
      "TelCacheProvider::NewSyncId",
      1767,
      "New syncId generated for a non-empty cache so forcing a full sync");
    v9 = *((_QWORD *)this + 11);
    LOBYTE(v10) = 1;
    *((_BYTE *)this + 97) = 1;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 104LL))(v9, v10);
    if ( v11 >= 0 )
      goto LABEL_11;
    v16 = v11;
    AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1773, "InventoryCache::BatchBegin failed [%#x]", v16);
  }
  else
  {
    v17 = -2147024809;
    AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1719, "Object not yet initialized. [%#x]", v17);
  }
LABEL_16:
  if ( !v1[36] )
  {
    if ( WaitForSingleObject(*(HANDLE *)v1, 0xFFFFFFFF) )
      return;
    --**((_DWORD **)v1 + 3);
    --*((_DWORD *)v1 + 8);
    ReleaseMutex(*(HANDLE *)v1);
    goto LABEL_23;
  }
  v12 = *((_QWORD *)v1 + 3);
  v13 = 0;
  if ( *(_DWORD *)(v12 + 4) == 1 )
  {
    v1[36] = 0;
    v13 = 1;
  }
  --*(_DWORD *)(v12 + 4);
  if ( v13 )
LABEL_23:
    SetEvent(*((HANDLE *)v1 + 2));
}

```

## disassembly

```asm
0x180020440  push    rbx
0x180020442  push    rsi
0x180020443  push    rdi
0x180020444  push    r14
0x180020446  sub     rsp, 58h
0x18002044a  mov     rax, cs:__security_cookie
0x180020451  xor     rax, rsp
0x180020454  mov     [rsp+78h+var_30], rax
0x180020459  lea     rbx, [rcx+68h]
0x18002045d  mov     rdi, rcx
0x180020460  mov     rcx, rbx; this
0x180020463  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180020468  cmp     qword ptr [rdi], 0
0x18002046c  jz      loc_1800205C1
0x180020472  cmp     qword ptr [rdi+58h], 0
0x180020477  jz      loc_1800205C1
0x18002047d  xorps   xmm0, xmm0
0x180020480  lea     rsi, [rdi+8]
0x180020484  xor     eax, eax
0x180020486  lea     rcx, [rsp+78h+Uuid]; Uuid
0x18002048b  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x180020490  mov     [rsi], ax
0x180020493  call    cs:__imp_UuidCreate
0x180020499  lea     r8, [rsp+78h+Uuid]
0x18002049e  mov     rcx, rsi
0x1800204a1  call    AslGuidToString
0x1800204a6  test    eax, eax
0x1800204a8  jz      short loc_1800204C0
0x1800204aa  mov     [rsp+78h+var_58], eax
0x1800204ae  lea     r9, aAslguidtostrin; "AslGuidToString failed [%d]"
0x1800204b5  mov     r8d, 6C6h
0x1800204bb  jmp     loc_1800205D6
0x1800204c0  mov     rcx, [rdi+58h]
0x1800204c4  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x1800204cb  mov     r8, rsi
0x1800204ce  mov     rax, [rcx]
0x1800204d1  mov     rax, [rax+50h]
0x1800204d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204da  test    eax, eax
0x1800204dc  jns     short loc_1800204F4
0x1800204de  mov     [rsp+78h+var_58], eax
0x1800204e2  lea     r9, aInventorycache_4; "InventoryCache::SetMetadata failed [%#x"...
0x1800204e9  mov     r8d, 6CEh
0x1800204ef  jmp     loc_1800205D6
0x1800204f4  mov     rcx, [rdi+58h]
0x1800204f8  mov     r14, [rdi]
0x1800204fb  mov     rax, [rcx]
0x1800204fe  mov     rax, [rax+88h]
0x180020505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002050a  test    eax, eax
0x18002050c  jnz     short loc_180020520
0x18002050e  mov     rax, [r14]
0x180020511  mov     rdx, rsi
0x180020514  mov     rcx, r14
0x180020517  mov     rax, [rax+58h]
0x18002051b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020520  mov     rcx, [rdi+58h]
0x180020524  lea     rdx, [rsp+78h+var_48]
0x180020529  mov     [rsp+78h+var_48], 0
0x180020531  mov     rax, [rcx]
0x180020534  mov     rax, [rax+20h]
0x180020538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002053d  test    eax, eax
0x18002053f  jns     short loc_18002056F
0x180020541  lea     r9, aInventorycache_2; "InventoryCache::GetItemCount failed [%#"...
0x180020548  mov     [rsp+78h+var_58], eax
0x18002054c  mov     r8d, 6DDh
0x180020552  lea     rdx, aTelcacheprovid_14; "TelCacheProvider::NewSyncId"
0x180020559  mov     ecx, 1
0x18002055e  call    AslLogCallPrintf
0x180020563  xor     edx, edx; unsigned __int16 *
0x180020565  mov     rcx, rdi; this
0x180020568  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x18002056d  jmp     short loc_1800205E7
0x18002056f  cmp     [rsp+78h+var_48], 0
0x180020574  jbe     short loc_180020563
0x180020576  lea     r9, aNewSyncidGener; "New syncId generated for a non-empty ca"...
0x18002057d  mov     r8d, 6E7h
0x180020583  lea     rdx, aTelcacheprovid_14; "TelCacheProvider::NewSyncId"
0x18002058a  mov     ecx, 3
0x18002058f  call    AslLogCallPrintf
0x180020594  mov     rcx, [rdi+58h]
0x180020598  mov     dl, 1
0x18002059a  mov     byte ptr [rdi+61h], 1
0x18002059e  mov     rax, [rcx]
0x1800205a1  mov     rax, [rax+68h]
0x1800205a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205aa  test    eax, eax
0x1800205ac  jns     short loc_180020563
0x1800205ae  mov     [rsp+78h+var_58], eax
0x1800205b2  lea     r9, aInventorycache_10; "InventoryCache::BatchBegin failed [%#x]"
0x1800205b9  mov     r8d, 6EDh
0x1800205bf  jmp     short loc_1800205D6
0x1800205c1  mov     [rsp+78h+var_58], 80070057h
0x1800205c9  lea     r9, aObjectNotYetIn; "Object not yet initialized. [%#x]"
0x1800205d0  mov     r8d, 6B7h
0x1800205d6  lea     rdx, aTelcacheprovid_14; "TelCacheProvider::NewSyncId"
0x1800205dd  mov     ecx, 1
0x1800205e2  call    AslLogCallPrintf
0x1800205e7  cmp     byte ptr [rbx+24h], 0
0x1800205eb  jz      short loc_18002060A
0x1800205ed  mov     rax, [rbx+18h]
0x1800205f1  xor     cl, cl
0x1800205f3  cmp     dword ptr [rax+4], 1
0x1800205f7  jnz     short loc_1800205FE
0x1800205f9  mov     [rbx+24h], cl
0x1800205fc  mov     cl, 1
0x1800205fe  or      edi, 0FFFFFFFFh
0x180020601  add     [rax+4], edi
0x180020604  test    cl, cl
0x180020606  jz      short loc_180020638
0x180020608  jmp     short loc_18002062E
0x18002060a  mov     rcx, [rbx]; hHandle
0x18002060d  or      edi, 0FFFFFFFFh
0x180020610  mov     edx, edi; dwMilliseconds
0x180020612  call    cs:__imp_WaitForSingleObject
0x180020618  test    eax, eax
0x18002061a  jnz     short loc_180020638
0x18002061c  mov     rax, [rbx+18h]
0x180020620  add     [rax], edi
0x180020622  add     [rbx+20h], edi
0x180020625  mov     rcx, [rbx]; hMutex
0x180020628  call    cs:__imp_ReleaseMutex
0x18002062e  mov     rcx, [rbx+10h]; hEvent
0x180020632  call    cs:__imp_SetEvent
0x180020638  mov     rcx, [rsp+78h+var_30]
0x18002063d  xor     rcx, rsp; StackCookie
0x180020640  call    __security_check_cookie
0x180020645  add     rsp, 58h
0x180020649  pop     r14
0x18002064b  pop     rdi
0x18002064c  pop     rsi
0x18002064d  pop     rbx
0x18002064e  retn
```
