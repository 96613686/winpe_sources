# SqliteDatabase::FindReplacement(IWpnNotification *)

- ea: `0x1800094b8`
- end: `0x1800097aa`
- name: `?FindReplacement@SqliteDatabase@@AEAAPEAUIWpnNotification@@PEAU2@@Z`
- size: `754`
- prototype: `struct IWpnNotification *__fastcall(SqliteDatabase *__hidden this, struct IWpnNotification *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009980`

## callees

- `0x1800082c4`
- `0x1800094b8`
- `0x18000caec`
- `0x18000e5f4`
- `0x18001575c`
- `0x18001592c`
- `0x18002b6d4`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009518`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000974b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000979c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009518`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000974b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000979c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
struct IWpnNotification *__fastcall SqliteDatabase::FindReplacement(SqliteDatabase *this, struct IWpnNotification *a2)
{
  int v4; // eax
  void *v5; // rcx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rax
  unsigned __int16 *v11; // rbx
  const unsigned __int16 *v12; // r8
  SqliteDatabase *v13; // rcx
  __int64 v14; // rbx
  unsigned __int16 *v15; // [rsp+20h] [rbp-49h] BYREF
  __int64 v16; // [rsp+28h] [rbp-41h]
  __int64 v17; // [rsp+30h] [rbp-39h]
  unsigned __int16 *v18; // [rsp+38h] [rbp-31h] BYREF
  __int64 v19; // [rsp+40h] [rbp-29h]
  __int64 v20; // [rsp+48h] [rbp-21h]
  unsigned __int16 *v21; // [rsp+50h] [rbp-19h] BYREF
  __int64 v22; // [rsp+58h] [rbp-11h]
  __int64 v23; // [rsp+60h] [rbp-9h]
  LPVOID pv[3]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v25[16]; // [rsp+80h] [rbp+17h] BYREF
  struct Statement *v26; // [rsp+90h] [rbp+27h]
  _BYTE v27[16]; // [rsp+A0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  struct Notification *v29; // [rsp+D8h] [rbp+6Fh] BYREF

  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v4 = (*(__int64 (__fastcall **)(struct IWpnNotification *, LPVOID *))(*(_QWORD *)a2 + 56LL))(a2, pv);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v4,
      (int)v15);
  v5 = pv[0];
  if ( !pv[0] || !*(_WORD *)pv[0] )
    goto LABEL_4;
  v21 = 0;
  v22 = -1;
  v23 = -1;
  v7 = (*(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 64LL))(a2, &v21);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8A6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v7,
      (int)v15);
  v18 = 0;
  v19 = -1;
  v20 = -1;
  v8 = (*(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 40LL))(a2, &v18);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8A9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v8,
      (int)v15);
  v15 = 0;
  v16 = -1;
  v17 = -1;
  v9 = (*(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(a2, &v15);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8AC,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v9,
      (int)v15);
  v10 = std::shared_ptr<TileSession>::shared_ptr<TileSession>(v27, (char *)this + 48);
  AutoAddToCache::AutoAddToCache(
    v25,
    v10,
    "SELECT [N].[Id], [H].[PrimaryId], [N].[Type], [N].[Payload], [N].[Tag], [N].[Group], [N].[ExpiryTime], [N].[ArrivalT"
    "ime], [N].[ActivityId], [N].[DataVersion], [N].[PayloadType], [N].[BootId], [N].[ExpiresOnReboot] FROM [Notification"
    "] AS [N] INNER JOIN [NotificationHandler] AS [H] ON [N].[HandlerId]=[H].[RecordId] WHERE [H].[PrimaryId]=? AND [Type"
    "]=? AND [Tag]=? AND [Group]=?");
  Statement::Bind(v26, 1, v15);
  Statement::Bind(v26, 2, v18);
  v11 = (unsigned __int16 *)&word_180124798;
  v12 = &word_180124798;
  if ( pv[0] )
    v12 = (const unsigned __int16 *)pv[0];
  Statement::Bind(v26, 3, v12);
  if ( v21 )
    v11 = v21;
  Statement::Bind(v26, 4, v11);
  v29 = 0;
  if ( !SqliteDatabase::BuildNotification(v13, v26, 0, &v29) )
  {
    if ( v29 )
      (*(void (__fastcall **)(struct Notification *))(*(_QWORD *)v29 + 16LL))(v29);
    AutoAddToCache::~AutoAddToCache((AutoAddToCache *)v25);
    if ( v15 )
    {
      CoTaskMemFree(v15);
      v15 = 0;
    }
    v16 = 0;
    v17 = 0;
    if ( v18 )
    {
      CoTaskMemFree(v18);
      v18 = 0;
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
    v5 = pv[0];
LABEL_4:
    if ( v5 )
      CoTaskMemFree(v5);
    return 0;
  }
  v14 = ((unsigned __int64)v29 + 32) & ((unsigned __int128)-(__int128)(unsigned __int64)v29 >> 64);
  AutoAddToCache::~AutoAddToCache((AutoAddToCache *)v25);
  if ( v15 )
  {
    CoTaskMemFree(v15);
    v15 = 0;
  }
  v16 = 0;
  v17 = 0;
  if ( v18 )
  {
    CoTaskMemFree(v18);
    v18 = 0;
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
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (struct IWpnNotification *)v14;
}

```

## disassembly

```asm
0x1800094b8  mov     [rsp-8+arg_0], rbx
0x1800094bd  mov     [rsp-8+arg_10], rsi
0x1800094c2  push    rbp
0x1800094c3  push    rdi
0x1800094c4  push    r14
0x1800094c6  lea     rbp, [rsp-47h]
0x1800094cb  sub     rsp, 0B0h
0x1800094d2  mov     rbx, rdx
0x1800094d5  mov     rdi, rcx
0x1800094d8  xor     esi, esi
0x1800094da  mov     [rbp+57h+pv], rsi
0x1800094de  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800094e2  mov     [rbp+57h+var_50], r14
0x1800094e6  mov     [rbp+57h+var_48], r14
0x1800094ea  mov     rax, [rdx]
0x1800094ed  lea     rdx, [rbp+57h+pv]
0x1800094f1  mov     rcx, rbx
0x1800094f4  mov     rax, [rax+38h]
0x1800094f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094fd  mov     rcx, [rbp+5Fh]; this
0x180009501  test    eax, eax
0x180009503  js      short loc_180009538
0x180009505  mov     rcx, [rbp+57h+pv]; pv
0x180009509  test    rcx, rcx
0x18000950c  jz      short loc_180009513
0x18000950e  cmp     [rcx], si
0x180009511  jnz     short loc_18000954D
0x180009513  test    rcx, rcx
0x180009516  jz      short loc_18000951E
0x180009518  call    cs:__imp_CoTaskMemFree
0x18000951e  xor     eax, eax
0x180009520  lea     r11, [rsp+0C0h+var_10]
0x180009528  mov     rbx, [r11+20h]
0x18000952c  mov     rsi, [r11+30h]
0x180009530  mov     rsp, r11
0x180009533  pop     r14
0x180009535  pop     rdi
0x180009536  pop     rbp
0x180009537  retn
0x180009538  mov     r9d, eax; char *
0x18000953b  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009542  mov     edx, 89Eh; void *
0x180009547  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000954d  mov     [rbp+57h+var_70], rsi
0x180009551  mov     [rbp+57h+var_68], r14
0x180009555  mov     [rbp+57h+var_60], r14
0x180009559  mov     rax, [rbx]
0x18000955c  lea     rdx, [rbp+57h+var_70]
0x180009560  mov     rcx, rbx
0x180009563  mov     rax, [rax+40h]
0x180009567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000956c  mov     rcx, [rbp+5Fh]; this
0x180009570  test    eax, eax
0x180009572  js      loc_1800096E8
0x180009578  mov     [rbp+57h+var_88], rsi
0x18000957c  mov     [rbp+57h+var_80], r14
0x180009580  mov     [rbp+57h+var_78], r14
0x180009584  mov     rax, [rbx]
0x180009587  lea     rdx, [rbp+57h+var_88]
0x18000958b  mov     rcx, rbx
0x18000958e  mov     rax, [rax+28h]
0x180009592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009597  mov     rcx, [rbp+5Fh]; this
0x18000959b  test    eax, eax
0x18000959d  js      loc_1800096FD
0x1800095a3  mov     [rbp+57h+var_A0], rsi
0x1800095a7  mov     [rbp+57h+var_98], r14
0x1800095ab  mov     [rbp+57h+var_90], r14
0x1800095af  mov     rax, [rbx]
0x1800095b2  lea     rdx, [rbp+57h+var_A0]
0x1800095b6  mov     rcx, rbx
0x1800095b9  mov     rax, [rax+20h]
0x1800095bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c2  mov     rcx, [rbp+5Fh]; this
0x1800095c6  test    eax, eax
0x1800095c8  js      loc_180009712
0x1800095ce  lea     rdx, [rdi+30h]
0x1800095d2  lea     rcx, [rbp+57h+var_20]
0x1800095d6  call    ??0?$shared_ptr@VTileSession@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<TileSession>::shared_ptr<TileSession>(std::shared_ptr<TileSession> const &)
0x1800095db  lea     r8, aSelectNIdHPrim_3; "SELECT [N].[Id], [H].[PrimaryId], [N].["...
0x1800095e2  mov     rdx, rax
0x1800095e5  lea     rcx, [rbp+57h+var_40]
0x1800095e9  call    ??0AutoAddToCache@@QEAA@V?$shared_ptr@VDatabase@@@std@@PEBD@Z; AutoAddToCache::AutoAddToCache(std::shared_ptr<Database>,char const *)
0x1800095ee  nop
0x1800095ef  mov     r8, [rbp+57h+var_A0]; unsigned __int16 *
0x1800095f3  mov     edx, 1; int
0x1800095f8  mov     rcx, [rbp+57h+var_30]; this
0x1800095fc  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x180009601  mov     r8, [rbp+57h+var_88]; unsigned __int16 *
0x180009605  mov     edx, 2; int
0x18000960a  mov     rcx, [rbp+57h+var_30]; this
0x18000960e  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x180009613  mov     rax, [rbp+57h+pv]
0x180009617  lea     rbx, word_180124798
0x18000961e  mov     r8, rbx
0x180009621  test    rax, rax
0x180009624  cmovnz  r8, rax; unsigned __int16 *
0x180009628  mov     edx, 3; int
0x18000962d  mov     rcx, [rbp+57h+var_30]; this
0x180009631  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x180009636  mov     rax, [rbp+57h+var_70]
0x18000963a  test    rax, rax
0x18000963d  cmovnz  rbx, rax
0x180009641  mov     r8, rbx; unsigned __int16 *
0x180009644  mov     edx, 4; int
0x180009649  mov     rcx, [rbp+57h+var_30]; this
0x18000964d  call    ?Bind@Statement@@QEAAXHPEBG@Z; Statement::Bind(int,ushort const *)
0x180009652  mov     [rbp+57h+arg_8], rsi
0x180009656  lea     r9, [rbp+57h+arg_8]; struct Notification **
0x18000965a  xor     r8d, r8d; bool
0x18000965d  mov     rdx, [rbp+57h+var_30]; struct Statement *
0x180009661  call    ?BuildNotification@SqliteDatabase@@AEAA_NPEAVStatement@@_NPEAPEAVNotification@@@Z; SqliteDatabase::BuildNotification(Statement *,bool,Notification * *)
0x180009666  test    al, al
0x180009668  jnz     loc_180009727
0x18000966e  mov     rcx, [rbp+57h+arg_8]
0x180009672  test    rcx, rcx
0x180009675  jz      short loc_180009684
0x180009677  mov     rax, [rcx]
0x18000967a  mov     rax, [rax+10h]
0x18000967e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009683  nop
0x180009684  lea     rcx, [rbp+57h+var_40]; this
0x180009688  call    ??1AutoAddToCache@@QEAA@XZ; AutoAddToCache::~AutoAddToCache(void)
0x18000968d  nop
0x18000968e  mov     rcx, [rbp+57h+var_A0]; pv
0x180009692  test    rcx, rcx
0x180009695  jz      short loc_1800096A1
0x180009697  call    cs:__imp_CoTaskMemFree
0x18000969d  mov     [rbp+57h+var_A0], rsi
0x1800096a1  mov     [rbp+57h+var_98], rsi
0x1800096a5  mov     [rbp+57h+var_90], rsi
0x1800096a9  mov     rcx, [rbp+57h+var_88]; pv
0x1800096ad  test    rcx, rcx
0x1800096b0  jz      short loc_1800096BC
0x1800096b2  call    cs:__imp_CoTaskMemFree
0x1800096b8  mov     [rbp+57h+var_88], rsi
0x1800096bc  mov     [rbp+57h+var_80], rsi
0x1800096c0  mov     [rbp+57h+var_78], rsi
0x1800096c4  mov     rcx, [rbp+57h+var_70]; pv
0x1800096c8  test    rcx, rcx
0x1800096cb  jz      short loc_1800096D7
0x1800096cd  call    cs:__imp_CoTaskMemFree
0x1800096d3  mov     [rbp+57h+var_70], rsi
0x1800096d7  mov     [rbp+57h+var_68], rsi
0x1800096db  mov     [rbp+57h+var_60], rsi
0x1800096df  mov     rcx, [rbp+57h+pv]
0x1800096e3  jmp     loc_180009513
0x1800096e8  mov     r9d, eax; char *
0x1800096eb  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800096f2  mov     edx, 8A6h; void *
0x1800096f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800096fd  mov     r9d, eax; char *
0x180009700  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009707  mov     edx, 8A9h; void *
0x18000970c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009712  mov     r9d, eax; char *
0x180009715  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000971c  mov     edx, 8ACh; void *
0x180009721  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009727  mov     rcx, [rbp+57h+arg_8]
0x18000972b  lea     rax, [rcx+20h]
0x18000972f  neg     rcx
0x180009732  sbb     rbx, rbx
0x180009735  and     rbx, rax
0x180009738  lea     rcx, [rbp+57h+var_40]; this
0x18000973c  call    ??1AutoAddToCache@@QEAA@XZ; AutoAddToCache::~AutoAddToCache(void)
0x180009741  nop
0x180009742  mov     rcx, [rbp+57h+var_A0]; pv
0x180009746  test    rcx, rcx
0x180009749  jz      short loc_180009755
0x18000974b  call    cs:__imp_CoTaskMemFree
0x180009751  mov     [rbp+57h+var_A0], rsi
0x180009755  mov     [rbp+57h+var_98], rsi
0x180009759  mov     [rbp+57h+var_90], rsi
0x18000975d  mov     rcx, [rbp+57h+var_88]; pv
0x180009761  test    rcx, rcx
0x180009764  jz      short loc_180009770
0x180009766  call    cs:__imp_CoTaskMemFree
0x18000976c  mov     [rbp+57h+var_88], rsi
0x180009770  mov     [rbp+57h+var_80], rsi
0x180009774  mov     [rbp+57h+var_78], rsi
0x180009778  mov     rcx, [rbp+57h+var_70]; pv
0x18000977c  test    rcx, rcx
0x18000977f  jz      short loc_18000978B
0x180009781  call    cs:__imp_CoTaskMemFree
0x180009787  mov     [rbp+57h+var_70], rsi
0x18000978b  mov     [rbp+57h+var_68], rsi
0x18000978f  mov     [rbp+57h+var_60], rsi
0x180009793  mov     rcx, [rbp+57h+pv]; pv
0x180009797  test    rcx, rcx
0x18000979a  jz      short loc_1800097A2
0x18000979c  call    cs:__imp_CoTaskMemFree
0x1800097a2  mov     rax, rbx
0x1800097a5  jmp     loc_180009520
```
