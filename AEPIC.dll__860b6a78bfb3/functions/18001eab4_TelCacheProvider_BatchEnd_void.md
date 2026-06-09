# TelCacheProvider::BatchEnd(void)

- ea: `0x18001eab4`
- end: `0x18001ef7c`
- name: `?BatchEnd@TelCacheProvider@@QEAAJXZ`
- size: `1224`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18001f378`
- `0x180021990`

## callees

- `0x180005890`
- `0x180006938`
- `0x180010d28`
- `0x180012f10`
- `0x180016bc0`
- `0x1800179fc`
- `0x1800186cc`
- `0x18001b970`
- `0x18001e568`
- `0x18001e718`
- `0x18001eab4`
- `0x1800211ec`
- `0x18002135c`
- `0x1800213c0`
- `0x1800295dc`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eaf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eb0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eaf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eb0d`

## string_xrefs

- `0x18001ec0b`: `InventoryCache::NextBatchMarkedItem failed. [%#x]`
- `0x18001ed85`: `InventoryCache::GetNextItem failed. [%#x]`
- `0x18001ee5e`: `TelCacheProvider::GetItem failed. [%#x]`
- `0x18001eed3`: `IAmiInventoryTelemetryItem::OnRemove(%ls) failed. [%#x]`
- `0x18001eccf`: `InventoryCache::RemoveItem failed. [%#x]`
- `0x18001ef0f`: `InventoryCache::RemoveItem failed. [%#x]`
- `0x18001eb75`: `TelCacheProvider::BatchEnd`
- `0x18001ebed`: `TelCacheProvider::BatchEnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TelCacheProvider::BatchEnd(TelCacheProvider *this)
{
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // r13
  signed int v5; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  SIZE_T v8; // r8
  int ItemCount; // eax
  unsigned __int64 v10; // r12
  unsigned int v11; // edi
  _QWORD *v12; // rdx
  int v13; // eax
  struct IAmiInventoryItem *v14; // r12
  int i; // eax
  void (__fastcall *v16)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v17; // ebx
  const unsigned __int16 *SyncId; // rax
  unsigned int v19; // ecx
  unsigned __int64 *v20; // rax
  unsigned __int64 v21; // rdi
  struct IAmiInventoryItem *v22; // rbx
  signed int v23; // eax
  bool v24; // sf
  int Item; // eax
  __int64 (__fastcall *v26)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v27; // ebx
  const unsigned __int16 *v28; // rax
  int v29; // eax
  int v30; // eax
  __int64 v31; // [rsp+20h] [rbp-E0h]
  unsigned int v32; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v35; // [rsp+48h] [rbp-B8h]
  struct IAmiInventoryItem *v36; // [rsp+50h] [rbp-B0h]
  Windows::Compat::Inventory::InventorySynchronization *v37; // [rsp+58h] [rbp-A8h]
  HANDLE ProcessHeap; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v39; // [rsp+68h] [rbp-98h]
  __int128 v40; // [rsp+70h] [rbp-90h]
  __int128 v41; // [rsp+80h] [rbp-80h]
  int v42; // [rsp+90h] [rbp-70h]
  unsigned __int16 v43[264]; // [rsp+A0h] [rbp-60h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  GetProcessHeap();
  v42 = 0;
  ProcessHeap = GetProcessHeap();
  v3 = 16;
  v35 = 16;
  v41 = 0x10u;
  v40 = 0;
  v4 = 0;
  v39 = 16;
  memset_0(v43, 0, 0x208u);
  v37 = (TelCacheProvider *)((char *)this + 104);
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( *((_BYTE *)this + 96) )
  {
    *((_BYTE *)this + 96) = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 11) + 112LL))(
           *((_QWORD *)this + 11),
           v43,
           260);
    if ( v5 >= 0 )
    {
      do
      {
        RtlStringArray::Append((RtlStringArray *)&ProcessHeap, v43, v8);
        v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 11) + 112LL))(
               *((_QWORD *)this + 11),
               v43,
               260);
      }
      while ( v5 >= 0 );
      v4 = *((_QWORD *)&v41 + 1);
      v3 = v39;
      v35 = v39;
    }
    if ( v5 == -2147024637 )
      v5 = 0;
    else
      AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1170, "InventoryCache::NextBatchMarkedItem failed. [%#x]", v5);
    v32 = 0;
    if ( *((_BYTE *)this + 97)
      && *(_QWORD *)this
      && (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this) )
    {
      *((_BYTE *)this + 97) = 0;
      goto LABEL_56;
    }
    ItemCount = TelCacheProvider::GetItemCount(this, &v32);
    v10 = v40;
    if ( ItemCount >= 0 && (unsigned __int64)v40 > (unsigned __int64)v32 >> 1 )
    {
      v11 = 0;
      if ( (_QWORD)v40 )
      {
        do
        {
          v12 = 0;
          if ( v11 < v10 )
          {
            v33 = 0;
            if ( (int)ULongLongMult(v35, v11, &v33) < 0 || (v12 = (_QWORD *)(v4 + v33), v4 + v33 < v4) )
              v12 = 0;
          }
          v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 11) + 24LL))(
                  *((_QWORD *)this + 11),
                  *v12);
          v5 = v13;
          if ( v13 < 0 )
            AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1195, "InventoryCache::RemoveItem failed. [%#x]", v13);
          ++v11;
        }
        while ( v11 < v10 );
      }
      if ( !*(_QWORD *)this )
        goto LABEL_56;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this) )
        goto LABEL_56;
      v14 = *(struct IAmiInventoryItem **)this;
      TelCacheProvider::NewSyncId(this);
      for ( i = TelCacheProvider::GetFirstItem(this, v14); i >= 0; i = TelCacheProvider::GetNextItem(this, v14) )
      {
        v16 = *(void (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL))(*(_QWORD *)v14 + 72LL);
        v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) == 0;
        SyncId = TelCacheProvider::RetrieveSyncId(this);
        v16(v14, SyncId, v17);
      }
      v5 = 0;
      if ( i != -2147024637 )
        v5 = i;
      if ( v5 >= 0 )
        goto LABEL_56;
      v6 = "InventoryCache::GetNextItem failed. [%#x]";
      v7 = 1218;
      goto LABEL_5;
    }
    v19 = 0;
    LODWORD(v33) = 0;
    if ( !(_QWORD)v40 )
      goto LABEL_56;
    while ( 1 )
    {
      v20 = 0;
      if ( v19 < v10 )
      {
        v34 = 0;
        if ( (int)ULongLongMult(v3, v19, &v34) < 0 || (v20 = (unsigned __int64 *)(v4 + v34), v4 + v34 < v4) )
          v20 = 0;
      }
      v21 = *v20;
      v34 = *v20;
      if ( !*(_QWORD *)this || !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this) )
        goto LABEL_53;
      v22 = *(struct IAmiInventoryItem **)this;
      v36 = v22;
      v23 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, unsigned __int64))(*(_QWORD *)v22 + 16LL))(v22, v21);
      v24 = v23 < 0;
      if ( v23 > 0 )
      {
        v23 = (unsigned __int16)v23 | 0x80070000;
        v24 = v23 < 0;
      }
      if ( v24 )
        AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1237, "IAmiInventoryItem::SetItemKey failed. [%#x]", v23);
      Item = TelCacheProvider::GetItem(this, v22, 0);
      if ( Item < 0 )
        AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1243, "TelCacheProvider::GetItem failed. [%#x]", Item);
      v26 = *(__int64 (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL))(*(_QWORD *)v22 + 80LL);
      v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) == 0;
      v28 = TelCacheProvider::RetrieveSyncId(this);
      v29 = v26(v36, v28, v27);
      v5 = v29;
      if ( v29 > 0 )
        v5 = (unsigned __int16)v29 | 0x80070000;
      if ( v5 >= 0 )
        break;
      AslLogCallPrintf(
        1,
        "TelCacheProvider::BatchEnd",
        1249,
        "IAmiInventoryTelemetryItem::OnRemove(%ls) failed. [%#x]",
        (const wchar_t *)v34,
        v5);
LABEL_55:
      v19 = v33 + 1;
      LODWORD(v33) = v19;
      v3 = v35;
      if ( v19 >= v10 )
        goto LABEL_56;
    }
    v21 = v34;
LABEL_53:
    v30 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)this + 11) + 24LL))(
            *((_QWORD *)this + 11),
            v21);
    v5 = v30;
    if ( v30 < 0 )
      AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1257, "InventoryCache::RemoveItem failed. [%#x]", v30);
    goto LABEL_55;
  }
  v5 = -2147418113;
  v6 = "BatchEnd called but batch not in progress [%#x]";
  v7 = 1149;
LABEL_5:
  LODWORD(v31) = v5;
  AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", v7, v6, v31);
LABEL_56:
  Windows::Compat::Inventory::InventorySynchronization::ReleaseLock(v37);
  RtlNameValueArray::Free((RtlNameValueArray *)&ProcessHeap);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001eab4  push    rbp
0x18001eab6  push    rbx
0x18001eab7  push    rsi
0x18001eab8  push    rdi
0x18001eab9  push    r12
0x18001eabb  push    r13
0x18001eabd  push    r14
0x18001eabf  push    r15
0x18001eac1  lea     rbp, [rsp-1C8h]
0x18001eac9  sub     rsp, 2C8h
0x18001ead0  mov     rax, cs:__security_cookie
0x18001ead7  xor     rax, rsp
0x18001eada  mov     [rbp+200h+var_50], rax
0x18001eae1  mov     rsi, rcx
0x18001eae4  xor     r12d, r12d
0x18001eae7  cmp     [rcx+58h], r12
0x18001eaeb  jnz     short loc_18001EAF7
0x18001eaed  mov     eax, 80004002h
0x18001eaf2  jmp     loc_18001EF59
0x18001eaf7  call    cs:__imp_GetProcessHeap
0x18001eafd  mov     [rbp+200h+var_270], r12d
0x18001eb01  xorps   xmm0, xmm0
0x18001eb04  movups  [rsp+300h+var_2A0], xmm0
0x18001eb09  movups  [rbp+200h+var_280], xmm0
0x18001eb0d  call    cs:__imp_GetProcessHeap
0x18001eb13  mov     qword ptr [rsp+300h+var_2A0], rax
0x18001eb18  mov     edi, 10h
0x18001eb1d  mov     [rsp+300h+var_2B8], rdi
0x18001eb22  mov     qword ptr [rbp+200h+var_280], rdi
0x18001eb26  xorps   xmm0, xmm0
0x18001eb29  movdqu  [rsp+300h+var_290], xmm0
0x18001eb2f  mov     r13, r12
0x18001eb32  mov     qword ptr [rbp+200h+var_280+8], r12
0x18001eb36  mov     qword ptr [rsp+300h+var_2A0+8], rdi
0x18001eb3b  xor     edx, edx; Val
0x18001eb3d  mov     r8d, 208h; Size
0x18001eb43  lea     rcx, [rbp+200h+var_260]; void *
0x18001eb47  call    memset_0
0x18001eb4c  lea     rax, [rsi+68h]
0x18001eb50  mov     [rsp+300h+var_2A8], rax
0x18001eb55  mov     rcx, rax; this
0x18001eb58  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18001eb5d  cmp     [rsi+60h], r12b
0x18001eb61  jnz     short loc_18001EB8D
0x18001eb63  mov     ebx, 8000FFFFh
0x18001eb68  lea     r9, aBatchendCalled; "BatchEnd called but batch not in progre"...
0x18001eb6f  mov     r8d, 47Dh
0x18001eb75  lea     rdx, aTelcacheprovid_15; "TelCacheProvider::BatchEnd"
0x18001eb7c  lea     ecx, [rdi-0Fh]
0x18001eb7f  mov     dword ptr [rsp+300h+var_2E0], ebx
0x18001eb83  call    AslLogCallPrintf
0x18001eb88  jmp     loc_18001EF42
0x18001eb8d  mov     [rsi+60h], r12b
0x18001eb91  mov     rcx, [rsi+58h]
0x18001eb95  mov     rax, [rcx]
0x18001eb98  mov     r14d, 104h
0x18001eb9e  mov     r8d, r14d
0x18001eba1  lea     rdx, [rbp+200h+var_260]
0x18001eba5  mov     rax, [rax+70h]
0x18001eba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebae  mov     ebx, eax
0x18001ebb0  test    eax, eax
0x18001ebb2  js      short loc_18001EBED
0x18001ebb4  lea     rdx, [rbp+200h+var_260]; unsigned __int16 *
0x18001ebb8  lea     rcx, [rsp+300h+var_2A0]; this
0x18001ebbd  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18001ebc2  mov     rcx, [rsi+58h]
0x18001ebc6  mov     rax, [rcx]
0x18001ebc9  mov     r8d, r14d
0x18001ebcc  lea     rdx, [rbp+200h+var_260]
0x18001ebd0  mov     rax, [rax+70h]
0x18001ebd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebd9  mov     ebx, eax
0x18001ebdb  test    eax, eax
0x18001ebdd  jns     short loc_18001EBB4
0x18001ebdf  mov     r13, qword ptr [rbp+200h+var_280+8]
0x18001ebe3  mov     rdi, qword ptr [rsp+300h+var_2A0+8]
0x18001ebe8  mov     [rsp+300h+var_2B8], rdi
0x18001ebed  lea     r15, aTelcacheprovid_15; "TelCacheProvider::BatchEnd"
0x18001ebf4  mov     r14d, 1
0x18001ebfa  cmp     ebx, 80070103h
0x18001ec00  jnz     short loc_18001EC07
0x18001ec02  mov     ebx, r12d
0x18001ec05  jmp     short loc_18001EC23
0x18001ec07  mov     dword ptr [rsp+300h+var_2E0], ebx
0x18001ec0b  lea     r9, aInventorycache_6; "InventoryCache::NextBatchMarkedItem fai"...
0x18001ec12  mov     r8d, 492h
0x18001ec18  mov     rdx, r15
0x18001ec1b  mov     ecx, r14d
0x18001ec1e  call    AslLogCallPrintf
0x18001ec23  mov     [rsp+300h+var_2D0], r12d
0x18001ec28  cmp     [rsi+61h], r12b
0x18001ec2c  jz      short loc_18001EC4F
0x18001ec2e  mov     rcx, [rsi]
0x18001ec31  test    rcx, rcx
0x18001ec34  jz      short loc_18001EC4F
0x18001ec36  mov     rax, [rcx]
0x18001ec39  mov     rax, [rax+38h]
0x18001ec3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec42  test    al, al
0x18001ec44  jz      short loc_18001EC4F
0x18001ec46  mov     [rsi+61h], r12b
0x18001ec4a  jmp     loc_18001EF42
0x18001ec4f  lea     rdx, [rsp+300h+var_2D0]; unsigned int *
0x18001ec54  mov     rcx, rsi; this
0x18001ec57  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x18001ec5c  mov     r12, qword ptr [rsp+300h+var_290]
0x18001ec61  test    eax, eax
0x18001ec63  js      loc_18001ED9D
0x18001ec69  mov     eax, [rsp+300h+var_2D0]
0x18001ec6d  shr     rax, 1
0x18001ec70  cmp     r12, rax
0x18001ec73  jbe     loc_18001ED9D
0x18001ec79  xor     edi, edi
0x18001ec7b  test    r12, r12
0x18001ec7e  jz      short loc_18001ECF1
0x18001ec80  xor     edx, edx
0x18001ec82  mov     eax, edi
0x18001ec84  cmp     rax, r12
0x18001ec87  jnb     short loc_18001ECB2
0x18001ec89  mov     [rsp+300h+var_2C8], rdx
0x18001ec8e  lea     r8, [rsp+300h+var_2C8]; unsigned __int64 *
0x18001ec93  mov     edx, eax; unsigned __int64
0x18001ec95  mov     rcx, [rsp+300h+var_2B8]; unsigned __int64
0x18001ec9a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001ec9f  test    eax, eax
0x18001eca1  js      short loc_18001ECB0
0x18001eca3  mov     rdx, [rsp+300h+var_2C8]
0x18001eca8  add     rdx, r13
0x18001ecab  cmp     rdx, r13
0x18001ecae  jnb     short loc_18001ECB2
0x18001ecb0  xor     edx, edx
0x18001ecb2  mov     rcx, [rsi+58h]
0x18001ecb6  mov     rax, [rcx]
0x18001ecb9  mov     rdx, [rdx]
0x18001ecbc  mov     rax, [rax+18h]
0x18001ecc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecc5  mov     ebx, eax
0x18001ecc7  test    eax, eax
0x18001ecc9  jns     short loc_18001ECE7
0x18001eccb  mov     dword ptr [rsp+300h+var_2E0], eax
0x18001eccf  lea     r9, aInventorycache_8; "InventoryCache::RemoveItem failed. [%#x"...
0x18001ecd6  mov     r8d, 4ABh
0x18001ecdc  mov     rdx, r15
0x18001ecdf  mov     ecx, r14d
0x18001ece2  call    AslLogCallPrintf
0x18001ece7  add     edi, r14d
0x18001ecea  mov     eax, edi
0x18001ecec  cmp     rax, r12
0x18001ecef  jb      short loc_18001EC80
0x18001ecf1  mov     rcx, [rsi]
0x18001ecf4  test    rcx, rcx
0x18001ecf7  jz      loc_18001EF42
0x18001ecfd  mov     rax, [rcx]
0x18001ed00  mov     rax, [rax+38h]
0x18001ed04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed09  test    al, al
0x18001ed0b  jz      loc_18001EF42
0x18001ed11  mov     r12, [rsi]
0x18001ed14  mov     rcx, rsi; this
0x18001ed17  call    ?NewSyncId@TelCacheProvider@@AEAAXXZ; TelCacheProvider::NewSyncId(void)
0x18001ed1c  mov     rdx, r12; struct IAmiInventoryItem *
0x18001ed1f  mov     rcx, rsi; this
0x18001ed22  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x18001ed27  jmp     short loc_18001ED6F
0x18001ed29  mov     rax, [r12]
0x18001ed2d  mov     rdi, [rax+48h]
0x18001ed31  mov     rcx, [rsi+58h]
0x18001ed35  mov     rax, [rcx]
0x18001ed38  mov     rax, [rax+88h]
0x18001ed3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed44  xor     ebx, ebx
0x18001ed46  test    eax, eax
0x18001ed48  setz    bl
0x18001ed4b  mov     rcx, rsi; this
0x18001ed4e  call    ?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ; TelCacheProvider::RetrieveSyncId(void)
0x18001ed53  mov     r8d, ebx
0x18001ed56  mov     rdx, rax
0x18001ed59  mov     rcx, r12
0x18001ed5c  mov     rax, rdi
0x18001ed5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed64  mov     rdx, r12; struct IAmiInventoryItem *
0x18001ed67  mov     rcx, rsi; this
0x18001ed6a  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x18001ed6f  test    eax, eax
0x18001ed71  jns     short loc_18001ED29
0x18001ed73  xor     ebx, ebx
0x18001ed75  cmp     eax, 80070103h
0x18001ed7a  cmovnz  ebx, eax
0x18001ed7d  test    ebx, ebx
0x18001ed7f  jns     loc_18001EF42
0x18001ed85  lea     r9, aInventorycache_7; "InventoryCache::GetNextItem failed. [%#"...
0x18001ed8c  mov     r8d, 4C2h
0x18001ed92  mov     rdx, r15
0x18001ed95  mov     ecx, r14d
0x18001ed98  jmp     loc_18001EB7F
0x18001ed9d  xor     ecx, ecx
0x18001ed9f  mov     dword ptr [rsp+300h+var_2C8], ecx
0x18001eda3  test    r12, r12
0x18001eda6  jz      loc_18001EF42
0x18001edac  xor     eax, eax
0x18001edae  mov     edx, ecx; unsigned __int64
0x18001edb0  cmp     rdx, r12
0x18001edb3  jnb     short loc_18001EDDA
0x18001edb5  mov     [rsp+300h+var_2C0], rax
0x18001edba  lea     r8, [rsp+300h+var_2C0]; unsigned __int64 *
0x18001edbf  mov     rcx, rdi; unsigned __int64
0x18001edc2  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001edc7  test    eax, eax
0x18001edc9  js      short loc_18001EDD8
0x18001edcb  mov     rax, [rsp+300h+var_2C0]
0x18001edd0  add     rax, r13
0x18001edd3  cmp     rax, r13
0x18001edd6  jnb     short loc_18001EDDA
0x18001edd8  xor     eax, eax
0x18001edda  mov     rdi, [rax]
0x18001eddd  mov     [rsp+300h+var_2C0], rdi
0x18001ede2  mov     rcx, [rsi]
0x18001ede5  test    rcx, rcx
0x18001ede8  jz      loc_18001EEF2
0x18001edee  mov     rax, [rcx]
0x18001edf1  mov     rax, [rax+38h]
0x18001edf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edfa  test    al, al
0x18001edfc  jz      loc_18001EEF2
0x18001ee02  mov     rbx, [rsi]
0x18001ee05  mov     [rsp+300h+var_2B0], rbx
0x18001ee0a  mov     rax, [rbx]
0x18001ee0d  mov     rdx, rdi
0x18001ee10  mov     rcx, rbx
0x18001ee13  mov     rax, [rax+10h]
0x18001ee17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee1c  test    eax, eax
0x18001ee1e  jle     short loc_18001EE2A
0x18001ee20  movzx   eax, ax
0x18001ee23  or      eax, 80070000h
0x18001ee28  test    eax, eax
0x18001ee2a  jns     short loc_18001EE48
0x18001ee2c  mov     dword ptr [rsp+300h+var_2E0], eax
0x18001ee30  lea     r9, aIamiinventoryi_1; "IAmiInventoryItem::SetItemKey failed. ["...
0x18001ee37  mov     r8d, 4D5h
0x18001ee3d  mov     rdx, r15
0x18001ee40  mov     ecx, r14d
0x18001ee43  call    AslLogCallPrintf
0x18001ee48  xor     r8d, r8d; bool
0x18001ee4b  mov     rdx, rbx; struct IAmiInventoryItem *
0x18001ee4e  mov     rcx, rsi; this
0x18001ee51  call    ?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z; TelCacheProvider::GetItem(IAmiInventoryItem *,bool)
0x18001ee56  test    eax, eax
0x18001ee58  jns     short loc_18001EE76
0x18001ee5a  mov     dword ptr [rsp+300h+var_2E0], eax
0x18001ee5e  lea     r9, aTelcacheprovid_8; "TelCacheProvider::GetItem failed. [%#x]"
0x18001ee65  mov     r8d, 4DBh
0x18001ee6b  mov     rdx, r15
0x18001ee6e  mov     ecx, r14d
0x18001ee71  call    AslLogCallPrintf
0x18001ee76  mov     rax, [rbx]
0x18001ee79  mov     rdi, [rax+50h]
0x18001ee7d  mov     rcx, [rsi+58h]
0x18001ee81  mov     rax, [rcx]
0x18001ee84  mov     rax, [rax+88h]
0x18001ee8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee90  xor     ebx, ebx
0x18001ee92  test    eax, eax
0x18001ee94  setz    bl
0x18001ee97  mov     rcx, rsi; this
0x18001ee9a  call    ?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ; TelCacheProvider::RetrieveSyncId(void)
0x18001ee9f  mov     r8d, ebx
0x18001eea2  mov     rdx, rax
0x18001eea5  mov     rcx, [rsp+300h+var_2B0]
0x18001eeaa  mov     rax, rdi
0x18001eead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eeb2  mov     ebx, eax
0x18001eeb4  test    eax, eax
0x18001eeb6  jle     short loc_18001EEC1
0x18001eeb8  movzx   ebx, ax
0x18001eebb  or      ebx, 80070000h
0x18001eec1  test    ebx, ebx
0x18001eec3  jns     short loc_18001EEED
0x18001eec5  mov     [rsp+300h+var_2D8], ebx
0x18001eec9  mov     rax, [rsp+300h+var_2C0]
0x18001eece  mov     [rsp+300h+var_2E0], rax
0x18001eed3  lea     r9, aIamiinventoryt; "IAmiInventoryTelemetryItem::OnRemove(%l"...
0x18001eeda  mov     r8d, 4E1h
0x18001eee0  mov     rdx, r15
0x18001eee3  mov     ecx, r14d
0x18001eee6  call    AslLogCallPrintf
0x18001eeeb  jmp     short loc_18001EF27
0x18001eeed  mov     rdi, [rsp+300h+var_2C0]
0x18001eef2  mov     rcx, [rsi+58h]
0x18001eef6  mov     rax, [rcx]
0x18001eef9  mov     rdx, rdi
0x18001eefc  mov     rax, [rax+18h]
0x18001ef00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef05  mov     ebx, eax
0x18001ef07  test    eax, eax
0x18001ef09  jns     short loc_18001EF27
0x18001ef0b  mov     dword ptr [rsp+300h+var_2E0], eax
0x18001ef0f  lea     r9, aInventorycache_8; "InventoryCache::RemoveItem failed. [%#x"...
0x18001ef16  mov     r8d, 4E9h
  ... truncated ...
```
