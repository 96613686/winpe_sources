# TelCacheProvider::AddItem(IAmiInventoryItem *)

- ea: `0x180015b48`
- end: `0x180015fca`
- name: `?AddItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z`
- size: `1154`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, struct IAmiInventoryItem *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800257a8`
- `0x180025a20`
- `0x180041eac`

## callees

- `0x180014ed4`
- `0x180014fa0`
- `0x180015b48`
- `0x180021f2c`
- `0x18002772c`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015e85`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015ee4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015f3c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015f8f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015e85`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015ee4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015f3c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015f8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015e7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015eda`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015f32`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015f85`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015e7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015eda`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015f32`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015f85`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015e65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015ec0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015f1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015f6f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015e65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015ec0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015f1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015f6f`

## string_xrefs

- `0x180015deb`: `TelCacheProvider::AddItem`
- `0x180015dda`: `InventoryCache::ClearBatchMark failed. [%#x]`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::AddItem(TelCacheProvider *this, struct IAmiInventoryItem *a2)
{
  HANDLE *v5; // rsi
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, __int64 *); // rbx
  __int64 v8; // rax
  int v9; // r12d
  bool v10; // r13
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, __int64 *); // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  void (__fastcall *v15)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v16; // ebx
  const unsigned __int16 *SyncId; // rax
  void (__fastcall *v18)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v19; // ebx
  const unsigned __int16 *v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, __int64 *); // rbx
  __int64 v23; // rax
  void (__fastcall *v24)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v25; // ebx
  const unsigned __int16 *v26; // rax
  int v27; // eax
  int v28; // eax
  _DWORD *v29; // rax
  char v30; // cl
  _DWORD *v31; // rax
  char v32; // cl
  _DWORD *v33; // rax
  char v34; // cl
  _DWORD *v35; // rax
  char v36; // cl
  char v37; // [rsp+70h] [rbp+40h]
  __int64 v38; // [rsp+80h] [rbp+50h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  v5 = (HANDLE *)((char *)this + 104);
  v38 = 0;
  Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((TelCacheProvider *)((char *)this + 104));
  v6 = *((_QWORD *)this + 11);
  v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v6 + 8LL);
  v8 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
  v9 = v7(v6, v8, &v38);
  if ( v9 < 0
    || (*(unsigned __int8 (__fastcall **)(struct IAmiInventoryItem *, __int64))(*(_QWORD *)a2 + 32LL))(a2, v38) )
  {
    v10 = 0;
    if ( v38 )
    {
      v37 = 0;
      if ( *((_BYTE *)this + 97)
        && (*(unsigned __int8 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 56LL))(a2) )
      {
        v15 = *(void (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL))(*(_QWORD *)a2 + 72LL);
        v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) == 0;
        SyncId = TelCacheProvider::RetrieveSyncId(this);
        v15(a2, SyncId, v16);
      }
      goto LABEL_21;
    }
  }
  else
  {
    v10 = 1;
  }
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((Windows::Compat::Inventory::InventorySynchronization *)v5);
  v37 = 1;
  if ( v38 )
  {
LABEL_17:
    if ( v10 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 56LL))(a2) )
      {
        v24 = *(void (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL))(*(_QWORD *)a2 + 72LL);
        v25 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) == 0;
        v26 = TelCacheProvider::RetrieveSyncId(this);
        v24(a2, v26, v25);
      }
      (*(void (__fastcall **)(struct IAmiInventoryItem *, __int64))(*(_QWORD *)a2 + 24LL))(a2, v38);
    }
LABEL_21:
    if ( *((_BYTE *)this + 96) || *((_BYTE *)this + 97) )
    {
      v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 160LL))(v38);
      v9 = v27;
      if ( v27 < 0 )
        AslLogCallPrintf(1, "TelCacheProvider::AddItem", 926, "InventoryCache::ClearBatchMark failed. [%#x]", v27);
    }
    goto LABEL_25;
  }
  v11 = *((_QWORD *)this + 11);
  v12 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v11 + 8LL);
  v13 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
  v9 = v12(v11, v13, &v38);
  v14 = *(_QWORD *)a2;
  if ( v9 >= 0 )
  {
    v10 = (*(unsigned __int8 (__fastcall **)(struct IAmiInventoryItem *, __int64))(v14 + 32))(a2, v38) == 0;
    goto LABEL_17;
  }
  if ( (*(unsigned __int8 (__fastcall **)(struct IAmiInventoryItem *))(v14 + 56))(a2) )
  {
    v18 = *(void (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL))(*(_QWORD *)a2 + 72LL);
    v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) == 0;
    v20 = TelCacheProvider::RetrieveSyncId(this);
    v18(a2, v20, v19);
  }
  v21 = *((_QWORD *)this + 11);
  v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v21 + 16LL);
  v23 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 8LL))(a2);
  v9 = v22(v21, v23, &v38);
  if ( v9 >= 0 )
  {
    (*(void (__fastcall **)(struct IAmiInventoryItem *, __int64))(*(_QWORD *)a2 + 24LL))(a2, v38);
    goto LABEL_17;
  }
LABEL_25:
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    if ( *((_BYTE *)v5 + 36) )
    {
      v33 = v5[3];
      v34 = 0;
      if ( v33[1] == 1 )
      {
        *((_BYTE *)v5 + 36) = 0;
        v34 = 1;
      }
      --v33[1];
      if ( !v34 )
      {
LABEL_54:
        if ( !v37 )
          goto LABEL_63;
        if ( *((_BYTE *)v5 + 36) )
        {
          v35 = v5[3];
          v36 = 0;
          if ( v35[1] == 1 )
          {
            *((_BYTE *)v5 + 36) = 0;
            v36 = 1;
          }
          --v35[1];
          if ( !v36 )
            goto LABEL_63;
        }
        else
        {
          if ( WaitForSingleObject(*v5, 0xFFFFFFFF) )
            goto LABEL_63;
          --*(_DWORD *)v5[3];
          --*((_DWORD *)v5 + 8);
          ReleaseMutex(*v5);
        }
        SetEvent(v5[2]);
LABEL_63:
        if ( v38 )
          (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 11) + 128LL))(*((_QWORD *)this + 11), &v38);
        return (unsigned int)v9;
      }
    }
    else
    {
      if ( WaitForSingleObject(*v5, 0xFFFFFFFF) )
        goto LABEL_54;
      --*(_DWORD *)v5[3];
      --*((_DWORD *)v5 + 8);
      ReleaseMutex(*v5);
    }
    SetEvent(v5[2]);
    goto LABEL_54;
  }
  if ( v38 )
  {
    v28 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 11) + 128LL))(
            *((_QWORD *)this + 11),
            &v38);
    v38 = 0;
    if ( v9 >= 0 )
      v9 = v28;
  }
  if ( !*((_BYTE *)v5 + 36) )
  {
    if ( WaitForSingleObject(*v5, 0xFFFFFFFF) )
      goto LABEL_37;
    --*(_DWORD *)v5[3];
    --*((_DWORD *)v5 + 8);
    ReleaseMutex(*v5);
    goto LABEL_36;
  }
  v29 = v5[3];
  v30 = 0;
  if ( v29[1] == 1 )
  {
    *((_BYTE *)v5 + 36) = 0;
    v30 = 1;
  }
  --v29[1];
  if ( v30 )
LABEL_36:
    SetEvent(v5[2]);
LABEL_37:
  if ( v37 )
  {
    if ( *((_BYTE *)v5 + 36) )
    {
      v31 = v5[3];
      v32 = 0;
      if ( v31[1] == 1 )
      {
        *((_BYTE *)v5 + 36) = 0;
        v32 = 1;
      }
      --v31[1];
      if ( !v32 )
        return (unsigned int)v9;
      goto LABEL_45;
    }
    if ( !WaitForSingleObject(*v5, 0xFFFFFFFF) )
    {
      --*(_DWORD *)v5[3];
      --*((_DWORD *)v5 + 8);
      ReleaseMutex(*v5);
LABEL_45:
      SetEvent(v5[2]);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180015b48  mov     [rsp-38h+arg_8], rbx
0x180015b4d  push    rbp
0x180015b4e  push    rsi
0x180015b4f  push    rdi
0x180015b50  push    r12
0x180015b52  push    r13
0x180015b54  push    r14
0x180015b56  push    r15
0x180015b58  mov     rbp, rsp
0x180015b5b  sub     rsp, 30h
0x180015b5f  cmp     qword ptr [rcx+58h], 0
0x180015b64  mov     r14, rdx
0x180015b67  mov     r15, rcx
0x180015b6a  jnz     short loc_180015B76
0x180015b6c  mov     eax, 80004002h
0x180015b71  jmp     loc_180015FB5
0x180015b76  lea     rsi, [rcx+68h]
0x180015b7a  mov     [rbp+arg_10], 0
0x180015b82  mov     rcx, rsi; this
0x180015b85  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x180015b8a  mov     rdi, [r15+58h]
0x180015b8e  mov     rcx, r14
0x180015b91  mov     rax, [rdi]
0x180015b94  mov     rbx, [rax+8]
0x180015b98  mov     rax, [r14]
0x180015b9b  mov     rax, [rax+8]
0x180015b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ba4  mov     rdx, rax
0x180015ba7  lea     r8, [rbp+arg_10]
0x180015bab  mov     rax, rbx
0x180015bae  mov     rcx, rdi
0x180015bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bb6  xor     edi, edi
0x180015bb8  mov     r12d, eax
0x180015bbb  test    eax, eax
0x180015bbd  js      loc_180015C4B
0x180015bc3  mov     rcx, [r14]
0x180015bc6  mov     rdx, [rbp+arg_10]
0x180015bca  mov     rax, [rcx+20h]
0x180015bce  mov     rcx, r14
0x180015bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bd6  test    al, al
0x180015bd8  jnz     short loc_180015C4B
0x180015bda  mov     r13b, 1
0x180015bdd  mov     rcx, rsi; this
0x180015be0  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180015be5  mov     [rbp+arg_0], 1
0x180015be9  cmp     [rbp+arg_10], rdi
0x180015bed  jnz     loc_180015D4D
0x180015bf3  mov     rdi, [r15+58h]
0x180015bf7  mov     rcx, r14
0x180015bfa  mov     rdx, [r14]
0x180015bfd  mov     rax, [rdi]
0x180015c00  mov     rbx, [rax+8]
0x180015c04  mov     rax, [rdx+8]
0x180015c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c0d  mov     rdx, rax
0x180015c10  lea     r8, [rbp+arg_10]
0x180015c14  mov     rax, rbx
0x180015c17  mov     rcx, rdi
0x180015c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c1f  mov     r12d, eax
0x180015c22  xor     edi, edi
0x180015c24  mov     rax, [r14]
0x180015c27  mov     rcx, r14
0x180015c2a  test    r12d, r12d
0x180015c2d  js      loc_180015CBA
0x180015c33  mov     rdx, [rbp+arg_10]
0x180015c37  mov     rax, [rax+20h]
0x180015c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c40  test    al, al
0x180015c42  setz    r13b
0x180015c46  jmp     loc_180015D4D
0x180015c4b  mov     r13b, dil
0x180015c4e  cmp     [rbp+arg_10], rdi
0x180015c52  jz      short loc_180015BDD
0x180015c54  mov     [rbp+arg_0], dil
0x180015c58  cmp     [r15+61h], dil
0x180015c5c  jz      loc_180015DB4
0x180015c62  mov     rax, [r14]
0x180015c65  mov     rcx, r14
0x180015c68  mov     rax, [rax+38h]
0x180015c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c71  test    al, al
0x180015c73  jz      loc_180015DB4
0x180015c79  mov     rax, [r14]
0x180015c7c  mov     rcx, [r15+58h]
0x180015c80  mov     rdi, [rax+48h]
0x180015c84  mov     rax, [rcx]
0x180015c87  mov     rax, [rax+88h]
0x180015c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c93  xor     ebx, ebx
0x180015c95  mov     rcx, r15; this
0x180015c98  test    eax, eax
0x180015c9a  setz    bl
0x180015c9d  call    ?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ; TelCacheProvider::RetrieveSyncId(void)
0x180015ca2  mov     rdx, rax
0x180015ca5  mov     r8d, ebx
0x180015ca8  mov     rax, rdi
0x180015cab  mov     rcx, r14
0x180015cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cb3  xor     edi, edi
0x180015cb5  jmp     loc_180015DB4
0x180015cba  mov     rax, [rax+38h]
0x180015cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cc3  test    al, al
0x180015cc5  jz      short loc_180015D01
0x180015cc7  mov     rax, [r14]
0x180015cca  mov     rcx, [r15+58h]
0x180015cce  mov     rdi, [rax+48h]
0x180015cd2  mov     rax, [rcx]
0x180015cd5  mov     rax, [rax+88h]
0x180015cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ce1  xor     ebx, ebx
0x180015ce3  mov     rcx, r15; this
0x180015ce6  test    eax, eax
0x180015ce8  setz    bl
0x180015ceb  call    ?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ; TelCacheProvider::RetrieveSyncId(void)
0x180015cf0  mov     rdx, rax
0x180015cf3  mov     r8d, ebx
0x180015cf6  mov     rax, rdi
0x180015cf9  mov     rcx, r14
0x180015cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d01  mov     rdi, [r15+58h]
0x180015d05  mov     rcx, r14
0x180015d08  mov     rdx, [r14]
0x180015d0b  mov     rax, [rdi]
0x180015d0e  mov     rbx, [rax+10h]
0x180015d12  mov     rax, [rdx+8]
0x180015d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d1b  mov     rdx, rax
0x180015d1e  lea     r8, [rbp+arg_10]
0x180015d22  mov     rax, rbx
0x180015d25  mov     rcx, rdi
0x180015d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d2d  xor     edi, edi
0x180015d2f  mov     r12d, eax
0x180015d32  test    eax, eax
0x180015d34  js      loc_180015DFC
0x180015d3a  mov     rax, [r14]
0x180015d3d  mov     rcx, r14
0x180015d40  mov     rdx, [rbp+arg_10]
0x180015d44  mov     rax, [rax+18h]
0x180015d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d4d  test    r13b, r13b
0x180015d50  jz      short loc_180015DB4
0x180015d52  mov     rax, [r14]
0x180015d55  mov     rcx, r14
0x180015d58  mov     rax, [rax+38h]
0x180015d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d61  test    al, al
0x180015d63  jz      short loc_180015DA1
0x180015d65  mov     rax, [r14]
0x180015d68  mov     rcx, [r15+58h]
0x180015d6c  mov     rdi, [rax+48h]
0x180015d70  mov     rax, [rcx]
0x180015d73  mov     rax, [rax+88h]
0x180015d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d7f  xor     ebx, ebx
0x180015d81  mov     rcx, r15; this
0x180015d84  test    eax, eax
0x180015d86  setz    bl
0x180015d89  call    ?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ; TelCacheProvider::RetrieveSyncId(void)
0x180015d8e  mov     rdx, rax
0x180015d91  mov     r8d, ebx
0x180015d94  mov     rax, rdi
0x180015d97  mov     rcx, r14
0x180015d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d9f  xor     edi, edi
0x180015da1  mov     rax, [r14]
0x180015da4  mov     rcx, r14
0x180015da7  mov     rdx, [rbp+arg_10]
0x180015dab  mov     rax, [rax+18h]
0x180015daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015db4  cmp     [r15+60h], dil
0x180015db8  jnz     short loc_180015DC0
0x180015dba  cmp     [r15+61h], dil
0x180015dbe  jz      short loc_180015DFC
0x180015dc0  mov     rcx, [rbp+arg_10]
0x180015dc4  mov     rax, [rcx]
0x180015dc7  mov     rax, [rax+0A0h]
0x180015dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dd3  mov     r12d, eax
0x180015dd6  test    eax, eax
0x180015dd8  jns     short loc_180015DFC
0x180015dda  lea     r9, aInventorycache; "InventoryCache::ClearBatchMark failed. "...
0x180015de1  mov     [rsp+30h+var_10], eax
0x180015de5  mov     r8d, 39Eh
0x180015deb  lea     rdx, aTelcacheprovid_28; "TelCacheProvider::AddItem"
0x180015df2  mov     ecx, 1
0x180015df7  call    AslLogCallPrintf
0x180015dfc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180015e03  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180015e08  test    al, al
0x180015e0a  jz      loc_180015EEF
0x180015e10  cmp     [rbp+arg_10], rdi
0x180015e14  jz      short loc_180015E38
0x180015e16  mov     rcx, [r15+58h]
0x180015e1a  lea     rdx, [rbp+arg_10]
0x180015e1e  mov     rax, [rcx]
0x180015e21  mov     rax, [rax+80h]
0x180015e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e2d  test    r12d, r12d
0x180015e30  mov     [rbp+arg_10], rdi
0x180015e34  cmovns  r12d, eax
0x180015e38  cmp     [rsi+24h], dil
0x180015e3c  jz      short loc_180015E5D
0x180015e3e  mov     rax, [rsi+18h]
0x180015e42  mov     cl, dil
0x180015e45  cmp     dword ptr [rax+4], 1
0x180015e49  jnz     short loc_180015E51
0x180015e4b  mov     [rsi+24h], dil
0x180015e4f  mov     cl, 1
0x180015e51  or      ebx, 0FFFFFFFFh
0x180015e54  add     [rax+4], ebx
0x180015e57  test    cl, cl
0x180015e59  jz      short loc_180015E8B
0x180015e5b  jmp     short loc_180015E81
0x180015e5d  mov     rcx, [rsi]; hHandle
0x180015e60  or      ebx, 0FFFFFFFFh
0x180015e63  mov     edx, ebx; dwMilliseconds
0x180015e65  call    cs:__imp_WaitForSingleObject
0x180015e6b  test    eax, eax
0x180015e6d  jnz     short loc_180015E8B
0x180015e6f  mov     rax, [rsi+18h]
0x180015e73  add     [rax], ebx
0x180015e75  add     [rsi+20h], ebx
0x180015e78  mov     rcx, [rsi]; hMutex
0x180015e7b  call    cs:__imp_ReleaseMutex
0x180015e81  mov     rcx, [rsi+10h]; hEvent
0x180015e85  call    cs:__imp_SetEvent
0x180015e8b  cmp     [rbp+arg_0], dil
0x180015e8f  jz      loc_180015FB2
0x180015e95  cmp     [rsi+24h], dil
0x180015e99  jz      short loc_180015EBB
0x180015e9b  mov     rax, [rsi+18h]
0x180015e9f  mov     cl, dil
0x180015ea2  cmp     dword ptr [rax+4], 1
0x180015ea6  jnz     short loc_180015EAE
0x180015ea8  mov     [rsi+24h], dil
0x180015eac  mov     cl, 1
0x180015eae  add     [rax+4], ebx
0x180015eb1  test    cl, cl
0x180015eb3  jz      loc_180015FB2
0x180015eb9  jmp     short loc_180015EE0
0x180015ebb  mov     rcx, [rsi]; hHandle
0x180015ebe  mov     edx, ebx; dwMilliseconds
0x180015ec0  call    cs:__imp_WaitForSingleObject
0x180015ec6  test    eax, eax
0x180015ec8  jnz     loc_180015FB2
0x180015ece  mov     rax, [rsi+18h]
0x180015ed2  add     [rax], ebx
0x180015ed4  add     [rsi+20h], ebx
0x180015ed7  mov     rcx, [rsi]; hMutex
0x180015eda  call    cs:__imp_ReleaseMutex
0x180015ee0  mov     rcx, [rsi+10h]; hEvent
0x180015ee4  call    cs:__imp_SetEvent
0x180015eea  jmp     loc_180015FB2
0x180015eef  cmp     [rsi+24h], dil
0x180015ef3  jz      short loc_180015F14
0x180015ef5  mov     rax, [rsi+18h]
0x180015ef9  mov     cl, dil
0x180015efc  cmp     dword ptr [rax+4], 1
0x180015f00  jnz     short loc_180015F08
0x180015f02  mov     [rsi+24h], dil
0x180015f06  mov     cl, 1
0x180015f08  or      ebx, 0FFFFFFFFh
0x180015f0b  add     [rax+4], ebx
0x180015f0e  test    cl, cl
0x180015f10  jz      short loc_180015F42
0x180015f12  jmp     short loc_180015F38
0x180015f14  mov     rcx, [rsi]; hHandle
0x180015f17  or      ebx, 0FFFFFFFFh
0x180015f1a  mov     edx, ebx; dwMilliseconds
0x180015f1c  call    cs:__imp_WaitForSingleObject
0x180015f22  test    eax, eax
0x180015f24  jnz     short loc_180015F42
0x180015f26  mov     rax, [rsi+18h]
0x180015f2a  add     [rax], ebx
0x180015f2c  add     [rsi+20h], ebx
0x180015f2f  mov     rcx, [rsi]; hMutex
0x180015f32  call    cs:__imp_ReleaseMutex
0x180015f38  mov     rcx, [rsi+10h]; hEvent
0x180015f3c  call    cs:__imp_SetEvent
0x180015f42  cmp     [rbp+arg_0], dil
0x180015f46  jz      short loc_180015F95
0x180015f48  cmp     [rsi+24h], dil
0x180015f4c  jz      short loc_180015F6A
0x180015f4e  mov     rax, [rsi+18h]
0x180015f52  mov     cl, dil
0x180015f55  cmp     dword ptr [rax+4], 1
0x180015f59  jnz     short loc_180015F61
0x180015f5b  mov     [rsi+24h], dil
0x180015f5f  mov     cl, 1
0x180015f61  add     [rax+4], ebx
0x180015f64  test    cl, cl
0x180015f66  jz      short loc_180015F95
0x180015f68  jmp     short loc_180015F8B
0x180015f6a  mov     rcx, [rsi]; hHandle
0x180015f6d  mov     edx, ebx; dwMilliseconds
  ... truncated ...
```
