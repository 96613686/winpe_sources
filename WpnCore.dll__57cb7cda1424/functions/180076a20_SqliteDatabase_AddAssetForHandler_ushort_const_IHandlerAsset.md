# SqliteDatabase::AddAssetForHandler(ushort const *,IHandlerAsset *)

- ea: `0x180076a20`
- end: `0x180076c97`
- name: `?AddAssetForHandler@SqliteDatabase@@UEAAJPEBGPEAUIHandlerAsset@@@Z`
- size: `631`
- prototype: `__int64 __fastcall(SqliteDatabase *__hidden this, const unsigned __int16 *, struct IHandlerAsset *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800082c4`
- `0x18000de40`
- `0x18000e598`
- `0x18000e5f4`
- `0x18001575c`
- `0x18001592c`
- `0x18002b6d4`
- `0x180049644`
- `0x180076a20`
- `0x180076ca0`
- `0x1800a0b2c`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076a5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076a5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076c61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076c61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076c0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076c47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076c0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076c47`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall SqliteDatabase::AddAssetForHandler(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned __int16 *a2,
        struct IHandlerAsset *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  LPCWSTR *p_LockCount; // r15
  _QWORD *OwningThread; // rax
  bool v9; // zf
  char v10; // al
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned __int16 *v16; // rdi
  unsigned __int16 *v17[3]; // [rsp+20h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-80h] BYREF
  __int64 v19; // [rsp+40h] [rbp-78h]
  __int64 v20; // [rsp+48h] [rbp-70h]
  unsigned __int16 *v21; // [rsp+50h] [rbp-68h] BYREF
  __int64 v22; // [rsp+58h] [rbp-60h]
  __int64 v23; // [rsp+60h] [rbp-58h]
  _BYTE v24[16]; // [rsp+68h] [rbp-50h] BYREF
  Statement *v25; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+C8h] [rbp+10h] BYREF

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  v6 = this + 3;
  EnterCriticalSection(this + 3);
  v27 = this + 3;
  p_LockCount = (LPCWSTR *)&this[-1].LockCount;
  OwningThread = this->OwningThread;
  if ( !OwningThread || (v9 = *OwningThread == 0, v10 = 0, v9) )
    v10 = 1;
  if ( v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9FA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)0x8007139FLL,
      (int)v17[0]);
  if ( BYTE4(this[4].OwningThread) )
  {
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v27);
    return 0;
  }
  else
  {
    v12 = std::shared_ptr<TileSession>::shared_ptr<TileSession>(v17, &this->OwningThread);
    AutoAddToCache::AutoAddToCache(
      v24,
      v12,
      "INSERT INTO [HandlerAssets] ([HandlerId], [AssetKey], [AssetValue]) SELECT [RecordId], ?, ? FROM [NotificationHand"
      "ler] WHERE [PrimaryId]=?");
    memset(v17, 0, sizeof(v17));
    v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            (__int64)v17,
            a2,
            0xFFFFFFFFFFFFFFFFuLL);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA02,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v13,
        (int)v17[0]);
    v21 = 0;
    v22 = -1;
    v23 = -1;
    v14 = (*(__int64 (__fastcall **)(struct IHandlerAsset *, unsigned __int16 **))(*(_QWORD *)a3 + 24LL))(a3, &v21);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA04,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v14,
        (int)v17[0]);
    pv = 0;
    v19 = -1;
    v20 = -1;
    v15 = (*(__int64 (__fastcall **)(struct IHandlerAsset *, LPVOID *))(*(_QWORD *)a3 + 32LL))(a3, &pv);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA06,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v15,
        (int)v17[0]);
    Statement::Bind(v25, 1, v21);
    Statement::Bind(v25, 2, (const unsigned __int16 *)pv);
    v16 = v17[0];
    Statement::Bind(v25, 3, v17[0]);
    Statement::FetchNoRow(v25);
    SqliteDatabase::BackupAsset(p_LockCount, a3);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v19 = 0;
    v20 = 0;
    if ( v21 )
    {
      CoTaskMemFree(v21);
      v21 = 0;
    }
    v22 = 0;
    v23 = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    AutoAddToCache::~AutoAddToCache((AutoAddToCache *)v24);
    if ( v6 )
      LeaveCriticalSection(v6);
    return 0;
  }
}

```

## disassembly

```asm
0x180076a20  mov     [rsp+arg_10], rbx
0x180076a25  push    rsi
0x180076a26  push    rdi
0x180076a27  push    r12
0x180076a29  push    r14
0x180076a2b  push    r15
0x180076a2d  sub     rsp, 90h
0x180076a34  mov     rsi, r8
0x180076a37  mov     r14, rdx
0x180076a3a  mov     rdi, rcx
0x180076a3d  xor     r12d, r12d
0x180076a40  test    rdx, rdx
0x180076a43  jnz     short loc_180076A4A
0x180076a45  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "handlerKey != nullptr")
0x180076a4a  test    rsi, rsi
0x180076a4d  jnz     short loc_180076A54
0x180076a4f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "asset != nullptr")
0x180076a54  lea     rbx, [rdi+78h]
0x180076a58  mov     rcx, rbx; lpCriticalSection
0x180076a5b  call    cs:__imp_EnterCriticalSection
0x180076a61  mov     [rsp+0B8h+arg_8], rbx
0x180076a69  lea     r15, [rdi-20h]
0x180076a6d  mov     rax, [r15+30h]
0x180076a71  test    rax, rax
0x180076a74  jz      short loc_180076A7E
0x180076a76  cmp     [rax], r12
0x180076a79  mov     al, r12b
0x180076a7c  jnz     short loc_180076A80
0x180076a7e  mov     al, 1
0x180076a80  mov     rcx, [rsp+0B8h]; this
0x180076a88  test    al, al
0x180076a8a  jz      short loc_180076AA3
0x180076a8c  mov     r9d, 8007139Fh; char *
0x180076a92  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180076a99  mov     edx, 9FAh; void *
0x180076a9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180076aa3  cmp     [rdi+0B4h], r12b
0x180076aaa  jz      short loc_180076AC0
0x180076aac  lea     rcx, [rsp+0B8h+arg_8]; this
0x180076ab4  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x180076ab9  xor     eax, eax
0x180076abb  jmp     loc_180076C7F
0x180076ac0  lea     rdx, [rdi+10h]
0x180076ac4  lea     rcx, [rsp+0B8h+var_98]
0x180076ac9  call    ??0?$shared_ptr@VTileSession@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<TileSession>::shared_ptr<TileSession>(std::shared_ptr<TileSession> const &)
0x180076ace  lea     r8, aInsertIntoHand; "INSERT INTO [HandlerAssets] ([HandlerId"...
0x180076ad5  mov     rdx, rax
0x180076ad8  lea     rcx, [rsp+0B8h+var_50]
0x180076add  call    ??0AutoAddToCache@@QEAA@V?$shared_ptr@VDatabase@@@std@@PEBD@Z; AutoAddToCache::AutoAddToCache(std::shared_ptr<Database>,char const *)
0x180076ae2  nop
0x180076ae3  mov     [rsp+0B8h+var_98], r12; int
0x180076ae8  mov     [rsp+0B8h+var_90], r12
0x180076aed  mov     [rsp+0B8h+var_88], r12
0x180076af2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180076af6  mov     r8, rdi
0x180076af9  mov     rdx, r14
0x180076afc  lea     rcx, [rsp+0B8h+var_98]
0x180076b01  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180076b06  mov     rcx, [rsp+0B8h]; this
0x180076b0e  test    eax, eax
0x180076b10  jns     short loc_180076B26
0x180076b12  mov     r9d, eax; char *
0x180076b15  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180076b1c  mov     edx, 0A02h; void *
0x180076b21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180076b26  mov     [rsp+0B8h+var_68], r12
0x180076b2b  mov     [rsp+0B8h+var_60], rdi
0x180076b30  mov     [rsp+0B8h+var_58], rdi
0x180076b35  mov     rax, [rsi]
0x180076b38  lea     rdx, [rsp+0B8h+var_68]
0x180076b3d  mov     rcx, rsi
0x180076b40  mov     rax, [rax+18h]
0x180076b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b49  mov     rcx, [rsp+0B8h]; this
0x180076b51  test    eax, eax
0x180076b53  jns     short loc_180076B69
0x180076b55  mov     r9d, eax; char *
0x180076b58  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180076b5f  mov     edx, 0A04h; void *
0x180076b64  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180076b69  mov     [rsp+0B8h+pv], r12
0x180076b6e  mov     [rsp+0B8h+var_78], rdi
0x180076b73  mov     [rsp+0B8h+var_70], rdi
0x180076b78  mov     rax, [rsi]
0x180076b7b  lea     rdx, [rsp+0B8h+pv]
0x180076b80  mov     rcx, rsi
0x180076b83  mov     rax, [rax+20h]
0x180076b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b8c  mov     rcx, [rsp+0B8h]; this
0x180076b94  test    eax, eax
0x180076b96  jns     short loc_180076BAC
0x180076b98  mov     r9d, eax; char *
0x180076b9b  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180076ba2  mov     edx, 0A06h; void *
0x180076ba7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180076bac  mov     r8, [rsp+0B8h+var_68]; unsigned __int16 *
0x180076bb1  mov     edx, 1; int
0x180076bb6  mov     rcx, [rsp+0B8h+var_40]; this
0x180076bbb  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x180076bc0  mov     r8, [rsp+0B8h+pv]; unsigned __int16 *
0x180076bc5  mov     edx, 2; int
0x180076bca  mov     rcx, [rsp+0B8h+var_40]; this
0x180076bcf  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x180076bd4  mov     rdi, [rsp+0B8h+var_98]
0x180076bd9  mov     r8, rdi; unsigned __int16 *
0x180076bdc  mov     edx, 3; int
0x180076be1  mov     rcx, [rsp+0B8h+var_40]; this
0x180076be6  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x180076beb  mov     rcx, [rsp+0B8h+var_40]; this
0x180076bf0  call    ?FetchNoRow@Statement@@QEAAXXZ; Statement::FetchNoRow(void)
0x180076bf5  mov     rdx, rsi; struct IHandlerAsset *
0x180076bf8  mov     rcx, r15; this
0x180076bfb  call    ?BackupAsset@SqliteDatabase@@AEAAXPEAUIHandlerAsset@@@Z; SqliteDatabase::BackupAsset(IHandlerAsset *)
0x180076c00  nop
0x180076c01  mov     rcx, [rsp+0B8h+pv]; pv
0x180076c06  test    rcx, rcx
0x180076c09  jz      short loc_180076C16
0x180076c0b  call    cs:__imp_CoTaskMemFree
0x180076c11  mov     [rsp+0B8h+pv], r12
0x180076c16  mov     [rsp+0B8h+var_78], r12
0x180076c1b  mov     [rsp+0B8h+var_70], r12
0x180076c20  mov     rcx, [rsp+0B8h+var_68]; pv
0x180076c25  test    rcx, rcx
0x180076c28  jz      short loc_180076C35
0x180076c2a  call    cs:__imp_CoTaskMemFree
0x180076c30  mov     [rsp+0B8h+var_68], r12
0x180076c35  mov     [rsp+0B8h+var_60], r12
0x180076c3a  mov     [rsp+0B8h+var_58], r12
0x180076c3f  test    rdi, rdi
0x180076c42  jz      short loc_180076C4E
0x180076c44  mov     rcx, rdi; pv
0x180076c47  call    cs:__imp_CoTaskMemFree
0x180076c4d  nop
0x180076c4e  lea     rcx, [rsp+0B8h+var_50]; this
0x180076c53  call    ??1AutoAddToCache@@QEAA@XZ; AutoAddToCache::~AutoAddToCache(void)
0x180076c58  nop
0x180076c59  test    rbx, rbx
0x180076c5c  jz      short loc_180076C67
0x180076c5e  mov     rcx, rbx; lpCriticalSection
0x180076c61  call    cs:__imp_LeaveCriticalSection
0x180076c67  xor     eax, eax
0x180076c69  jmp     short loc_180076C7F
0x180076c6b  lea     rcx, [rsp+0B8h+arg_8]; this
0x180076c73  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x180076c78  mov     eax, [rsp+0B8h+arg_0]
0x180076c7f  mov     rbx, [rsp+0B8h+arg_10]
0x180076c87  add     rsp, 90h
0x180076c8e  pop     r15
0x180076c90  pop     r14
0x180076c92  pop     r12
0x180076c94  pop     rdi
0x180076c95  pop     rsi
0x180076c96  retn
```
