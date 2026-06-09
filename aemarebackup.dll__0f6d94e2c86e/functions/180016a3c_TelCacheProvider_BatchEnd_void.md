# TelCacheProvider::BatchEnd(void)

- ea: `0x180016a3c`
- end: `0x180017063`
- name: `?BatchEnd@TelCacheProvider@@QEAAJXZ`
- size: `1575`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800257a8`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x180007122`
- `0x18001441c`
- `0x180014ed4`
- `0x180016550`
- `0x180016a3c`
- `0x18001b554`
- `0x18001b710`
- `0x18001bb7c`
- `0x18001d840`
- `0x180020440`
- `0x180021f2c`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b9c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001702d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001702d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017022`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017022`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017008`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016a7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016a94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016a7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016a94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016c42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016c42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016bdf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016bdf`

## string_xrefs

- `0x180016c95`: `InventoryCache::NextBatchMarkedItem failed. [%#x]`
- `0x180016e17`: `InventoryCache::GetNextItem failed. [%#x]`
- `0x180016ee8`: `TelCacheProvider::GetItem failed. [%#x]`
- `0x180016f5d`: `IAmiInventoryTelemetryItem::OnRemove(%ls) failed. [%#x]`
- `0x180016d54`: `InventoryCache::RemoveItem failed. [%#x]`
- `0x180016f9c`: `InventoryCache::RemoveItem failed. [%#x]`
- `0x180016aff`: `TelCacheProvider::BatchEnd`
- `0x180016c7d`: `TelCacheProvider::BatchEnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TelCacheProvider::BatchEnd(TelCacheProvider *this)
{
  HANDLE ProcessHeap; // r13
  unsigned __int64 v4; // rdi
  char *v5; // r12
  signed int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // rbx
  _QWORD *v13; // rdx
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  SIZE_T v16; // rdi
  wchar_t *v17; // rax
  wchar_t *v18; // rbx
  int v19; // eax
  int ItemCount; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // edi
  unsigned __int64 v24; // r12
  _QWORD *v25; // rdx
  unsigned __int64 v26; // rax
  int v27; // eax
  struct IAmiInventoryItem *v28; // r14
  int i; // eax
  __int64 v30; // rdx
  void (__fastcall *v31)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v32; // ebx
  const unsigned __int16 *v33; // rax
  unsigned __int128 v34; // rax
  unsigned __int64 v35; // r12
  const wchar_t **v36; // rcx
  unsigned __int64 v37; // kr10_8
  const wchar_t *v38; // rdi
  struct IAmiInventoryItem *v39; // rbx
  signed int v40; // eax
  bool v41; // sf
  int Item; // eax
  __int64 (__fastcall *v43)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL); // rdi
  BOOL v44; // ebx
  const unsigned __int16 *SyncId; // rax
  int v46; // eax
  int v47; // eax
  char v48; // cl
  __int64 v49; // rax
  __int64 v50; // [rsp+20h] [rbp-E0h]
  const wchar_t *v51[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v52; // [rsp+40h] [rbp-C0h] BYREF
  int v53; // [rsp+44h] [rbp-BCh]
  struct IAmiInventoryItem *v54; // [rsp+48h] [rbp-B8h]
  HANDLE v55; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int128 v57; // [rsp+60h] [rbp-A0h]
  __int128 v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+80h] [rbp-80h]
  char *v60; // [rsp+88h] [rbp-78h]
  _WORD Src[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  GetProcessHeap();
  v59 = 0;
  ProcessHeap = GetProcessHeap();
  v55 = ProcessHeap;
  v51[0] = (const wchar_t *)16;
  v58 = 0x10u;
  v57 = 0;
  v4 = 0;
  v56 = 16;
  memset_0(Src, 0, 0x208u);
  v5 = (char *)this + 104;
  v60 = (char *)this + 104;
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( !*((_BYTE *)this + 96) )
  {
    v6 = -2147418113;
    v7 = "BatchEnd called but batch not in progress [%#x]";
    v8 = 1149;
LABEL_5:
    LODWORD(v50) = v6;
    AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", v8, v7, v50);
    goto LABEL_79;
  }
  *((_BYTE *)this + 96) = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64))(**((_QWORD **)this + 11) + 112LL))(
         *((_QWORD *)this + 11),
         Src,
         260);
  v10 = v57;
  if ( v6 < 0 )
    goto LABEL_27;
  v11 = 16;
  do
  {
    v51[0] = 0;
    v51[1] = 0;
    if ( !v59 )
      goto LABEL_18;
    v12 = 0;
    if ( !v10 )
      goto LABEL_18;
    while ( 1 )
    {
      v13 = 0;
      if ( v12 < v10 )
      {
        v54 = 0;
        v14 = v11 * v12;
        if ( !is_mul_ok(v11, v12) || (v13 = (_QWORD *)(v4 + v14), v4 + v14 < v4) )
          v13 = 0;
      }
      if ( !(unsigned int)_o__wcsicmp(Src, *v13) )
        break;
      if ( ++v12 >= v10 )
        goto LABEL_18;
    }
    if ( v12 == -1 )
    {
LABEL_18:
      v15 = -1;
      do
        ++v15;
      while ( Src[v15] );
      v16 = 2 * v15 + 2;
      v17 = (wchar_t *)HeapAlloc(ProcessHeap, 0, v16);
      v18 = v17;
      if ( v17 )
      {
        memset_0(v17, 0, v16);
        v51[0] = v18;
        memcpy_0(v18, Src, v16);
        v19 = RtlArray<RtlStringArray::RTL_STRING_ITEM>::Append(&v55, v51);
        v10 = v57;
        v11 = v56;
        ProcessHeap = v55;
        if ( !v19 )
          goto LABEL_25;
        v18 = (wchar_t *)v51[0];
      }
      if ( v18 )
        HeapFree(ProcessHeap, 0, v18);
    }
LABEL_25:
    v6 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64))(**((_QWORD **)this + 11) + 112LL))(
           *((_QWORD *)this + 11),
           Src,
           260);
    v4 = *((_QWORD *)&v58 + 1);
  }
  while ( v6 >= 0 );
  v51[0] = (const wchar_t *)v11;
  v5 = (char *)this + 104;
LABEL_27:
  if ( v6 == -2147024637 )
    v6 = 0;
  else
    AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1170, "InventoryCache::NextBatchMarkedItem failed. [%#x]", v6);
  v52 = 0;
  if ( *((_BYTE *)this + 97)
    && *(_QWORD *)this
    && (*(unsigned __int8 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v9, 0) )
  {
    *((_BYTE *)this + 97) = 0;
    goto LABEL_79;
  }
  ItemCount = TelCacheProvider::GetItemCount(this, &v52);
  v22 = 0;
  if ( ItemCount < 0 || v10 <= (unsigned __int64)v52 >> 1 )
  {
    *((_QWORD *)&v34 + 1) = 0;
    v53 = 0;
    if ( !v10 )
      goto LABEL_79;
    v35 = (unsigned __int64)v51[0];
    while ( 1 )
    {
      v36 = 0;
      if ( DWORD2(v34) < v10 )
      {
        v54 = 0;
        v37 = DWORD2(v34);
        v34 = v35 * (unsigned __int128)DWORD2(v34);
        if ( !is_mul_ok(v35, v37) || (v36 = (const wchar_t **)(v4 + v34), v4 + (unsigned __int64)v34 < v4) )
          v36 = 0;
      }
      v38 = *v36;
      v51[0] = *v36;
      if ( *(_QWORD *)this
        && (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)this + 56LL))(
             *(_QWORD *)this,
             *((_QWORD *)&v34 + 1),
             0) )
      {
        v39 = *(struct IAmiInventoryItem **)this;
        v54 = v39;
        v40 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, const wchar_t *))(*(_QWORD *)v39 + 16LL))(v39, v38);
        v41 = v40 < 0;
        if ( v40 > 0 )
        {
          v40 = (unsigned __int16)v40 | 0x80070000;
          v41 = v40 < 0;
        }
        if ( v41 )
          AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1237, "IAmiInventoryItem::SetItemKey failed. [%#x]", v40);
        Item = TelCacheProvider::GetItem(this, v39, 0);
        if ( Item < 0 )
          AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1243, "TelCacheProvider::GetItem failed. [%#x]", Item);
        v43 = *(__int64 (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL))(*(_QWORD *)v39 + 80LL);
        v44 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) == 0;
        SyncId = TelCacheProvider::RetrieveSyncId(this);
        v46 = v43(v54, SyncId, v44);
        v6 = v46;
        if ( v46 > 0 )
          v6 = (unsigned __int16)v46 | 0x80070000;
        if ( v6 < 0 )
        {
          AslLogCallPrintf(
            1,
            "TelCacheProvider::BatchEnd",
            1249,
            "IAmiInventoryTelemetryItem::OnRemove(%ls) failed. [%#x]",
            v51[0],
            v6);
LABEL_76:
          v22 = 0;
          goto LABEL_77;
        }
        v38 = v51[0];
      }
      v47 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 11) + 24LL))(
              *((_QWORD *)this + 11),
              v38,
              v22);
      v6 = v47;
      v22 = 0;
      if ( v47 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1257, "InventoryCache::RemoveItem failed. [%#x]", v47);
        goto LABEL_76;
      }
LABEL_77:
      *((_QWORD *)&v34 + 1) = (unsigned int)(v53 + 1);
      v53 = DWORD2(v34);
      v4 = *((_QWORD *)&v58 + 1);
      if ( DWORD2(v34) >= v10 )
      {
        v5 = v60;
        goto LABEL_79;
      }
    }
  }
  v23 = 0;
  if ( v10 )
  {
    v24 = *((_QWORD *)&v58 + 1);
    do
    {
      v25 = 0;
      if ( v23 < v10 )
      {
        v26 = (unsigned __int64)v51[0] * v23;
        if ( !is_mul_ok((unsigned __int64)v51[0], v23) || (v25 = (_QWORD *)(v24 + v26), v24 + v26 < v24) )
          v25 = 0;
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 11) + 24LL))(
              *((_QWORD *)this + 11),
              *v25,
              0);
      v6 = v27;
      if ( v27 < 0 )
        AslLogCallPrintf(1, "TelCacheProvider::BatchEnd", 1195, "InventoryCache::RemoveItem failed. [%#x]", v27);
      ++v23;
    }
    while ( v23 < v10 );
    v5 = (char *)this + 104;
  }
  if ( *(_QWORD *)this
    && (*(unsigned __int8 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v21, 0) )
  {
    v28 = *(struct IAmiInventoryItem **)this;
    TelCacheProvider::NewSyncId(this);
    for ( i = TelCacheProvider::GetFirstItem(this, v28); i >= 0; i = TelCacheProvider::GetNextItem(this, v28) )
    {
      v31 = *(void (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, BOOL))(*(_QWORD *)v28 + 72LL);
      v32 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 11) + 136LL))(
              *((_QWORD *)this + 11),
              v30,
              0) == 0;
      v33 = TelCacheProvider::RetrieveSyncId(this);
      v31(v28, v33, v32);
    }
    v6 = 0;
    if ( i != -2147024637 )
      v6 = i;
    if ( v6 < 0 )
    {
      v7 = "InventoryCache::GetNextItem failed. [%#x]";
      v8 = 1218;
      goto LABEL_5;
    }
  }
LABEL_79:
  if ( v5[36] )
  {
    v48 = 0;
    v49 = *((_QWORD *)v5 + 3);
    if ( *(_DWORD *)(v49 + 4) == 1 )
    {
      v5[36] = 0;
      v48 = 1;
    }
    --*(_DWORD *)(v49 + 4);
    if ( v48 )
LABEL_86:
      SetEvent(*((HANDLE *)v5 + 2));
  }
  else if ( !WaitForSingleObject(*(HANDLE *)v5, 0xFFFFFFFF) )
  {
    --**((_DWORD **)v5 + 3);
    --*((_DWORD *)v5 + 8);
    ReleaseMutex(*(HANDLE *)v5);
    goto LABEL_86;
  }
  RtlNameValueArray::Free((RtlNameValueArray *)&v55);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016a3c  push    rbp
0x180016a3e  push    rbx
0x180016a3f  push    rsi
0x180016a40  push    rdi
0x180016a41  push    r12
0x180016a43  push    r13
0x180016a45  push    r14
0x180016a47  push    r15
0x180016a49  lea     rbp, [rsp-1B8h]
0x180016a51  sub     rsp, 2B8h
0x180016a58  mov     rax, cs:__security_cookie
0x180016a5f  xor     rax, rsp
0x180016a62  mov     [rbp+1F0h+var_50], rax
0x180016a69  mov     rsi, rcx
0x180016a6c  xor     ebx, ebx
0x180016a6e  cmp     [rcx+58h], rbx
0x180016a72  jnz     short loc_180016A7E
0x180016a74  mov     eax, 80004002h
0x180016a79  jmp     loc_180017040
0x180016a7e  call    cs:__imp_GetProcessHeap
0x180016a84  mov     [rbp+1F0h+var_270], ebx
0x180016a87  xorps   xmm0, xmm0
0x180016a8a  movups  [rsp+2F0h+var_2A0], xmm0
0x180016a8f  movups  [rsp+2F0h+var_280], xmm0
0x180016a94  call    cs:__imp_GetProcessHeap
0x180016a9a  mov     r13, rax
0x180016a9d  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180016aa2  mov     eax, 10h
0x180016aa7  mov     [rsp+2F0h+var_2C0], rax
0x180016aac  mov     qword ptr [rsp+2F0h+var_280], rax
0x180016ab1  xorps   xmm0, xmm0
0x180016ab4  movdqu  [rsp+2F0h+var_290], xmm0
0x180016aba  mov     rdi, rbx
0x180016abd  mov     qword ptr [rsp+2F0h+var_280+8], rbx
0x180016ac2  mov     qword ptr [rsp+2F0h+var_2A0+8], rax
0x180016ac7  xor     edx, edx; Val
0x180016ac9  mov     r8d, 208h; Size
0x180016acf  lea     rcx, [rbp+1F0h+Src]; void *
0x180016ad3  call    memset_0
0x180016ad8  lea     r12, [rsi+68h]
0x180016adc  mov     [rbp+1F0h+var_268], r12
0x180016ae0  mov     rcx, r12; this
0x180016ae3  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180016ae8  cmp     [rsi+60h], bl
0x180016aeb  jnz     short loc_180016B20
0x180016aed  mov     ebx, 8000FFFFh
0x180016af2  lea     r9, aBatchendCalled; "BatchEnd called but batch not in progre"...
0x180016af9  mov     r8d, 47Dh
0x180016aff  lea     rdx, aTelcacheprovid_17; "TelCacheProvider::BatchEnd"
0x180016b06  mov     r15d, 1
0x180016b0c  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x180016b10  mov     ecx, r15d
0x180016b13  call    AslLogCallPrintf
0x180016b18  xor     r8d, r8d
0x180016b1b  jmp     loc_180016FD6
0x180016b20  mov     [rsi+60h], bl
0x180016b23  mov     rcx, [rsi+58h]
0x180016b27  mov     rax, [rcx]
0x180016b2a  mov     r8d, 104h
0x180016b30  lea     rdx, [rbp+1F0h+Src]
0x180016b34  mov     rax, [rax+70h]
0x180016b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b3d  mov     ebx, eax
0x180016b3f  mov     r15d, 1
0x180016b45  xor     r8d, r8d
0x180016b48  mov     r14, qword ptr [rsp+2F0h+var_290]
0x180016b4d  test    eax, eax
0x180016b4f  js      loc_180016C7D
0x180016b55  lea     r12d, [r15+0Fh]
0x180016b59  mov     [rsp+2F0h+var_2C0], r8
0x180016b5e  mov     [rsp+2F0h+var_2B8], r8
0x180016b63  cmp     [rbp+1F0h+var_270], r8d
0x180016b67  jz      short loc_180016BBD
0x180016b69  mov     rbx, r8
0x180016b6c  test    r14, r14
0x180016b6f  jz      short loc_180016BBD
0x180016b71  mov     rdx, r8
0x180016b74  cmp     rbx, r14
0x180016b77  jnb     short loc_180016B95
0x180016b79  mov     [rsp+2F0h+var_2A8], r8
0x180016b7e  mov     rax, rbx
0x180016b81  mul     r12
0x180016b84  test    rdx, rdx
0x180016b87  jnz     short loc_180016B92
0x180016b89  lea     rdx, [rdi+rax]
0x180016b8d  cmp     rdx, rdi
0x180016b90  jnb     short loc_180016B95
0x180016b92  mov     rdx, r8
0x180016b95  mov     rdx, [rdx]
0x180016b98  lea     rcx, [rbp+1F0h+Src]
0x180016b9c  call    cs:__imp__o__wcsicmp
0x180016ba2  xor     r8d, r8d
0x180016ba5  test    eax, eax
0x180016ba7  jz      short loc_180016BB3
0x180016ba9  add     rbx, r15
0x180016bac  cmp     rbx, r14
0x180016baf  jb      short loc_180016B71
0x180016bb1  jmp     short loc_180016BBD
0x180016bb3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180016bb7  jnz     loc_180016C48
0x180016bbd  lea     rcx, [rbp+1F0h+Src]
0x180016bc1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016bc5  inc     rax
0x180016bc8  cmp     [rcx+rax*2], r8w
0x180016bcd  jnz     short loc_180016BC5
0x180016bcf  lea     rdi, ds:2[rax*2]
0x180016bd7  mov     r8, rdi; dwBytes
0x180016bda  xor     edx, edx; dwFlags
0x180016bdc  mov     rcx, r13; hHeap
0x180016bdf  call    cs:__imp_HeapAlloc
0x180016be5  mov     rbx, rax
0x180016be8  test    rax, rax
0x180016beb  jz      short loc_180016C35
0x180016bed  mov     r8, rdi; Size
0x180016bf0  xor     edx, edx; Val
0x180016bf2  mov     rcx, rax; void *
0x180016bf5  call    memset_0
0x180016bfa  mov     [rsp+2F0h+var_2C0], rbx
0x180016bff  mov     r8, rdi; Size
0x180016c02  lea     rdx, [rbp+1F0h+Src]; Src
0x180016c06  mov     rcx, rbx; void *
0x180016c09  call    memcpy_0
0x180016c0e  lea     rdx, [rsp+2F0h+var_2C0]
0x180016c13  lea     rcx, [rsp+2F0h+var_2A0]
0x180016c18  call    ?Append@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJAEBURTL_STRING_ITEM@RtlStringArray@@@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Append(RtlStringArray::RTL_STRING_ITEM const &)
0x180016c1d  mov     r14, qword ptr [rsp+2F0h+var_290]
0x180016c22  mov     r12, qword ptr [rsp+2F0h+var_2A0+8]
0x180016c27  mov     r13, qword ptr [rsp+2F0h+var_2A0]
0x180016c2c  test    eax, eax
0x180016c2e  jz      short loc_180016C48
0x180016c30  mov     rbx, [rsp+2F0h+var_2C0]
0x180016c35  test    rbx, rbx
0x180016c38  jz      short loc_180016C48
0x180016c3a  mov     r8, rbx; lpMem
0x180016c3d  xor     edx, edx; dwFlags
0x180016c3f  mov     rcx, r13; hHeap
0x180016c42  call    cs:__imp_HeapFree
0x180016c48  mov     rcx, [rsi+58h]
0x180016c4c  mov     rax, [rcx]
0x180016c4f  mov     r8d, 104h
0x180016c55  lea     rdx, [rbp+1F0h+Src]
0x180016c59  mov     rax, [rax+70h]
0x180016c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c62  mov     ebx, eax
0x180016c64  xor     r8d, r8d
0x180016c67  test    eax, eax
0x180016c69  mov     rdi, qword ptr [rsp+2F0h+var_280+8]
0x180016c6e  jns     loc_180016B59
0x180016c74  mov     [rsp+2F0h+var_2C0], r12
0x180016c79  lea     r12, [rsi+68h]
0x180016c7d  lea     r13, aTelcacheprovid_17; "TelCacheProvider::BatchEnd"
0x180016c84  cmp     ebx, 80070103h
0x180016c8a  jnz     short loc_180016C91
0x180016c8c  mov     ebx, r8d
0x180016c8f  jmp     short loc_180016CB0
0x180016c91  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x180016c95  lea     r9, aInventorycache_5; "InventoryCache::NextBatchMarkedItem fai"...
0x180016c9c  mov     r8d, 492h
0x180016ca2  mov     rdx, r13
0x180016ca5  mov     ecx, r15d
0x180016ca8  call    AslLogCallPrintf
0x180016cad  xor     r8d, r8d
0x180016cb0  mov     [rsp+2F0h+var_2B0], r8d
0x180016cb5  cmp     [rsi+61h], r8b
0x180016cb9  jz      short loc_180016CDF
0x180016cbb  mov     rcx, [rsi]
0x180016cbe  test    rcx, rcx
0x180016cc1  jz      short loc_180016CDF
0x180016cc3  mov     rax, [rcx]
0x180016cc6  mov     rax, [rax+38h]
0x180016cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ccf  xor     r8d, r8d
0x180016cd2  test    al, al
0x180016cd4  jz      short loc_180016CDF
0x180016cd6  mov     [rsi+61h], r8b
0x180016cda  jmp     loc_180016FD6
0x180016cdf  lea     rdx, [rsp+2F0h+var_2B0]; unsigned int *
0x180016ce4  mov     rcx, rsi; this
0x180016ce7  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x180016cec  xor     r8d, r8d
0x180016cef  test    eax, eax
0x180016cf1  js      loc_180016E2C
0x180016cf7  mov     eax, [rsp+2F0h+var_2B0]
0x180016cfb  shr     rax, 1
0x180016cfe  cmp     r14, rax
0x180016d01  jbe     loc_180016E2C
0x180016d07  mov     edi, r8d
0x180016d0a  test    r14, r14
0x180016d0d  jz      short loc_180016D7D
0x180016d0f  mov     r12, qword ptr [rsp+2F0h+var_280+8]
0x180016d14  mov     rdx, r8
0x180016d17  mov     eax, edi
0x180016d19  cmp     rax, r14
0x180016d1c  jnb     short loc_180016D34
0x180016d1e  mul     [rsp+2F0h+var_2C0]
0x180016d23  test    rdx, rdx
0x180016d26  jnz     short loc_180016D31
0x180016d28  lea     rdx, [r12+rax]
0x180016d2c  cmp     rdx, r12
0x180016d2f  jnb     short loc_180016D34
0x180016d31  mov     rdx, r8
0x180016d34  mov     rcx, [rsi+58h]
0x180016d38  mov     rax, [rcx]
0x180016d3b  mov     rdx, [rdx]
0x180016d3e  mov     rax, [rax+18h]
0x180016d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d47  mov     ebx, eax
0x180016d49  xor     r8d, r8d
0x180016d4c  test    eax, eax
0x180016d4e  jns     short loc_180016D6F
0x180016d50  mov     dword ptr [rsp+2F0h+var_2D0], eax
0x180016d54  lea     r9, aInventorycache_9; "InventoryCache::RemoveItem failed. [%#x"...
0x180016d5b  mov     r8d, 4ABh
0x180016d61  mov     rdx, r13
0x180016d64  mov     ecx, r15d
0x180016d67  call    AslLogCallPrintf
0x180016d6c  xor     r8d, r8d
0x180016d6f  add     edi, r15d
0x180016d72  mov     eax, edi
0x180016d74  cmp     rax, r14
0x180016d77  jb      short loc_180016D14
0x180016d79  lea     r12, [rsi+68h]
0x180016d7d  mov     rcx, [rsi]
0x180016d80  test    rcx, rcx
0x180016d83  jz      loc_180016FD6
0x180016d89  mov     rax, [rcx]
0x180016d8c  mov     rax, [rax+38h]
0x180016d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d95  xor     r8d, r8d
0x180016d98  test    al, al
0x180016d9a  jz      loc_180016FD6
0x180016da0  mov     r14, [rsi]
0x180016da3  mov     rcx, rsi; this
0x180016da6  call    ?NewSyncId@TelCacheProvider@@AEAAXXZ; TelCacheProvider::NewSyncId(void)
0x180016dab  mov     rdx, r14; struct IAmiInventoryItem *
0x180016dae  mov     rcx, rsi; this
0x180016db1  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x180016db6  jmp     short loc_180016DFD
0x180016db8  mov     rax, [r14]
0x180016dbb  mov     rdi, [rax+48h]
0x180016dbf  mov     rcx, [rsi+58h]
0x180016dc3  mov     rax, [rcx]
0x180016dc6  mov     rax, [rax+88h]
0x180016dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dd2  xor     ebx, ebx
0x180016dd4  test    eax, eax
0x180016dd6  setz    bl
0x180016dd9  mov     rcx, rsi; this
0x180016ddc  call    ?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ; TelCacheProvider::RetrieveSyncId(void)
0x180016de1  mov     r8d, ebx
0x180016de4  mov     rdx, rax
0x180016de7  mov     rcx, r14
0x180016dea  mov     rax, rdi
0x180016ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016df2  mov     rdx, r14; struct IAmiInventoryItem *
0x180016df5  mov     rcx, rsi; this
0x180016df8  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x180016dfd  xor     r8d, r8d
0x180016e00  test    eax, eax
0x180016e02  jns     short loc_180016DB8
0x180016e04  mov     ebx, r8d
0x180016e07  cmp     eax, 80070103h
0x180016e0c  cmovnz  ebx, eax
0x180016e0f  test    ebx, ebx
0x180016e11  jns     loc_180016FD6
0x180016e17  lea     r9, aInventorycache_6; "InventoryCache::GetNextItem failed. [%#"...
0x180016e1e  mov     r8d, 4C2h
0x180016e24  mov     rdx, r13
0x180016e27  jmp     loc_180016B0C
0x180016e2c  mov     edx, r8d
0x180016e2f  mov     [rsp+2F0h+var_2AC], edx
0x180016e33  test    r14, r14
0x180016e36  jz      loc_180016FD6
0x180016e3c  mov     r12, [rsp+2F0h+var_2C0]
0x180016e41  mov     rcx, r8
0x180016e44  mov     eax, edx
0x180016e46  cmp     rax, r14
0x180016e49  jnb     short loc_180016E64
0x180016e4b  mov     [rsp+2F0h+var_2A8], r8
0x180016e50  mul     r12
0x180016e53  test    rdx, rdx
0x180016e56  jnz     short loc_180016E61
0x180016e58  lea     rcx, [rdi+rax]
0x180016e5c  cmp     rcx, rdi
0x180016e5f  jnb     short loc_180016E64
0x180016e61  mov     rcx, r8
0x180016e64  mov     rdi, [rcx]
0x180016e67  mov     [rsp+2F0h+var_2C0], rdi
0x180016e6c  mov     rcx, [rsi]
0x180016e6f  test    rcx, rcx
0x180016e72  jz      loc_180016F7C
0x180016e78  mov     rax, [rcx]
0x180016e7b  mov     rax, [rax+38h]
0x180016e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e84  test    al, al
0x180016e86  jz      loc_180016F7C
0x180016e8c  mov     rbx, [rsi]
0x180016e8f  mov     [rsp+2F0h+var_2A8], rbx
0x180016e94  mov     rax, [rbx]
0x180016e97  mov     rdx, rdi
  ... truncated ...
```
