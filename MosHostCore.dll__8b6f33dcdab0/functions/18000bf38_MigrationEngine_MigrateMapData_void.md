# MigrationEngine::MigrateMapData(void)

- ea: `0x18000bf38`
- end: `0x18000c1e4`
- name: `?MigrateMapData@MigrationEngine@@IEAAJXZ`
- size: `684`
- prototype: `__int64 __fastcall(MigrationEngine *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180015200`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x18000bf38`
- `0x18000c1ec`
- `0x18000cac0`
- `0x18000ce44`
- `0x18002016c`

## import_xrefs

- `MosStorage!MosQueryAnyPackagesFromPath` at `0x18000c05f`
- `MosStorage!MosQueryAnyPackagesFromPath` at `0x18000c05f`
- `MosStorage!MosQueryPackagesFromPath` at `0x18000c0d0`
- `MosStorage!MosQueryPackagesFromPath` at `0x18000c0d0`
- `MosStorage!MosStorageGetTotalMapDataInBytes` at `0x18000c094`
- `MosStorage!MosStorageGetTotalMapDataInBytes` at `0x18000c094`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c13f`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c13f`
- `ZTrace_Maps!ZTraceHelper` at `0x18000c034`
- `ZTrace_Maps!ZTraceHelper` at `0x18000c034`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000bf79`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000bf79`

## pseudocode

```c
__int64 __fastcall MigrationEngine::MigrateMapData(MigrationEngine *this, unsigned __int64 a2)
{
  char v2; // r15
  int v3; // eax
  int v5; // eax
  unsigned __int64 v6; // rdx
  unsigned __int8 v7; // cl
  _DWORD *v8; // rsi
  _DWORD *v9; // rbp
  bool v10; // di
  bool v11; // r14
  OfflineMapsTelemetry *v12; // rax
  int AnyPackagesFromPath; // eax
  int v14; // r8d
  int v15; // edx
  unsigned int v16; // edi
  unsigned int v17; // r14d
  bool v18; // si
  bool v19; // bp
  OfflineMapsTelemetry *v20; // rax

  v2 = 0;
  v3 = *((_DWORD *)this + 828) - 1;
  *((_DWORD *)this + 829) = 10;
  if ( (v3 & 0xFFFFFFFD) != 0 )
  {
    v5 = ZTraceReportOrigination(-2147024875, "MigrationEngine::MigrateMapData", 86, this);
    v8 = (_DWORD *)((char *)this + 1668);
    v9 = (_DWORD *)((char *)this + 20);
    goto LABEL_22;
  }
  v8 = (_DWORD *)((char *)this + 1668);
  *((_DWORD *)this + 828) = 2;
  v9 = (_DWORD *)((char *)this + 20);
  v10 = *((_DWORD *)this + 417) != 0;
  v11 = *((_DWORD *)this + 5) != 0;
  if ( OfflineMapsTelemetry::IsEnabled((unsigned __int8)this, a2) )
  {
    v12 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::StorageMigrationStartMosHost_(
      v12,
      v11,
      *((_DWORD *)this + 137),
      v10,
      *((_DWORD *)this + 549),
      *((_DWORD *)this + 412),
      *((_DWORD *)this + 824));
  }
  ZTraceHelper(
    3,
    "MigrationEngine::MigrateMapData",
    98,
    this,
    "[Migration] Migration is starting. Flags: %d - State: %d - Target: %ls",
    *((_DWORD *)this + 2),
    *((_DWORD *)this + 828),
    (const wchar_t *)this + 1102);
  if ( (*((_BYTE *)this + 8) & 1) == 0 )
    goto LABEL_18;
  *((_DWORD *)this + 829) = 20;
  AnyPackagesFromPath = MosQueryAnyPackagesFromPath((char *)this + 28, (char *)this + 3320, 0);
  if ( AnyPackagesFromPath >= 0 )
  {
    if ( *((_BYTE *)this + 3320) )
    {
      if ( !*((_QWORD *)this + 416) )
      {
        *((_DWORD *)this + 829) = 30;
        AnyPackagesFromPath = MosStorageGetTotalMapDataInBytes((unsigned __int64 *)this + 416);
        if ( AnyPackagesFromPath < 0 )
        {
          v14 = 114;
          goto LABEL_21;
        }
      }
      if ( !*((_BYTE *)this + 3344) )
      {
        *((_DWORD *)this + 829) = 40;
        AnyPackagesFromPath = MosQueryPackagesFromPath((char *)this + 1676, (char *)this + 3360, 0);
        if ( AnyPackagesFromPath < 0 )
        {
          v14 = 121;
          goto LABEL_21;
        }
        *((_DWORD *)this + 829) = 50;
        AnyPackagesFromPath = RecursiveRemoveDirectoryEx((const unsigned __int16 *)this + 838, v15, *v8 == 0);
        if ( AnyPackagesFromPath < 0 )
        {
          v14 = 125;
          goto LABEL_21;
        }
        *((_BYTE *)this + 3344) = 1;
      }
    }
LABEL_18:
    if ( !*((_BYTE *)this + 3320)
      || (AnyPackagesFromPath = MigrationEngine::MigrateMapDataInternal(this), AnyPackagesFromPath >= 0) )
    {
      v16 = 0;
      *((_DWORD *)this + 828) = 3;
      return v16;
    }
    v2 = 1;
    v14 = 136;
    goto LABEL_21;
  }
  v14 = 104;
LABEL_21:
  v5 = ZTraceReportPropagation(AnyPackagesFromPath, "MigrationEngine::MigrateMapData", v14, this);
LABEL_22:
  v16 = v5;
  if ( v5 < 0 )
  {
    if ( v2 )
    {
      if ( !*((_DWORD *)this + 831) )
      {
        v17 = *((_DWORD *)this + 829);
        v18 = *v8 != 0;
        v19 = *v9 != 0;
        if ( OfflineMapsTelemetry::IsEnabled(v7, v6) )
        {
          v20 = OfflineMapsTelemetry::Instance();
          OfflineMapsTelemetry::StorageMigrationCopyFailedMosHost_(
            v20,
            v19,
            *((_DWORD *)this + 137),
            v18,
            *((_DWORD *)this + 549),
            *((_DWORD *)this + 412),
            *((_DWORD *)this + 824),
            v16,
            v17);
        }
      }
    }
    *((_DWORD *)this + 828) = 5;
  }
  return v16;
}

```

## disassembly

```asm
0x18000bf38  push    rbx
0x18000bf3a  push    rbp
0x18000bf3b  push    rsi
0x18000bf3c  push    rdi
0x18000bf3d  push    r14
0x18000bf3f  push    r15
0x18000bf41  sub     rsp, 58h
0x18000bf45  mov     eax, [rcx+0CF0h]
0x18000bf4b  xor     r15b, r15b
0x18000bf4e  dec     eax
0x18000bf50  mov     dword ptr [rcx+0CF4h], 0Ah
0x18000bf5a  mov     rbx, rcx
0x18000bf5d  test    eax, 0FFFFFFFDh
0x18000bf62  jz      short loc_18000BF8F
0x18000bf64  mov     r9, rcx
0x18000bf67  lea     rdx, aMigrationengin_0; "MigrationEngine::MigrateMapData"
0x18000bf6e  mov     ecx, 80070015h
0x18000bf73  mov     r8d, 56h ; 'V'
0x18000bf79  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000bf7f  lea     rsi, [rbx+684h]
0x18000bf86  lea     rbp, [rbx+14h]
0x18000bf8a  jmp     loc_18000C145
0x18000bf8f  lea     rsi, [rcx+684h]
0x18000bf96  mov     dword ptr [rcx+0CF0h], 2
0x18000bfa0  cmp     dword ptr [rsi], 0
0x18000bfa3  lea     rbp, [rcx+14h]
0x18000bfa7  setnz   dil
0x18000bfab  cmp     dword ptr [rbp+0], 0
0x18000bfaf  setnz   r14b
0x18000bfb3  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000bfb8  test    al, al
0x18000bfba  jz      short loc_18000BFF4
0x18000bfbc  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000bfc1  mov     ecx, [rbx+0CE0h]
0x18000bfc7  mov     r9b, dil; bool
0x18000bfca  mov     r8d, [rbx+224h]; unsigned int
0x18000bfd1  mov     dl, r14b; bool
0x18000bfd4  mov     [rsp+88h+var_58], ecx; unsigned int
0x18000bfd8  mov     ecx, [rbx+670h]
0x18000bfde  mov     [rsp+88h+var_60], ecx; unsigned int
0x18000bfe2  mov     ecx, [rbx+894h]
0x18000bfe8  mov     [rsp+88h+var_68], ecx; unsigned int
0x18000bfec  mov     rcx, rax; this
0x18000bfef  call    ?StorageMigrationStartMosHost_@OfflineMapsTelemetry@@QEAAX_NI0III@Z; OfflineMapsTelemetry::StorageMigrationStartMosHost_(bool,uint,bool,uint,uint,uint)
0x18000bff4  lea     rax, [rbx+89Ch]
0x18000bffb  mov     r8d, 62h ; 'b'
0x18000c001  mov     qword ptr [rsp+88h+var_50], rax
0x18000c006  lea     rdi, aMigrationengin_0; "MigrationEngine::MigrateMapData"
0x18000c00d  mov     eax, [rbx+0CF0h]
0x18000c013  mov     r9, rbx
0x18000c016  mov     [rsp+88h+var_58], eax
0x18000c01a  mov     rdx, rdi
0x18000c01d  mov     eax, [rbx+8]
0x18000c020  lea     ecx, [r8-5Fh]
0x18000c024  mov     [rsp+88h+var_60], eax
0x18000c028  lea     rax, aMigrationMigra_0; "[Migration] Migration is starting. Flag"...
0x18000c02f  mov     qword ptr [rsp+88h+var_68], rax
0x18000c034  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000c03a  test    byte ptr [rbx+8], 1
0x18000c03e  jz      loc_18000C111
0x18000c044  lea     r14, [rbx+0CF8h]
0x18000c04b  mov     dword ptr [rbx+0CF4h], 14h
0x18000c055  mov     rdx, r14
0x18000c058  lea     rcx, [rbx+1Ch]
0x18000c05c  xor     r8d, r8d
0x18000c05f  call    cs:__imp_?MosQueryAnyPackagesFromPath@@YAJPEBGPEA_NW4StackMode@@@Z; MosQueryAnyPackagesFromPath(ushort const *,bool *,StackMode)
0x18000c065  test    eax, eax
0x18000c067  jns     short loc_18000C074
0x18000c069  mov     r8d, 68h ; 'h'
0x18000c06f  jmp     loc_18000C137
0x18000c074  cmp     [r14], r15b
0x18000c077  jz      loc_18000C111
0x18000c07d  lea     rcx, [rbx+0D00h]
0x18000c084  cmp     qword ptr [rcx], 0
0x18000c088  jnz     short loc_18000C0A9
0x18000c08a  mov     dword ptr [rbx+0CF4h], 1Eh
0x18000c094  call    cs:__imp_?MosStorageGetTotalMapDataInBytes@@YAJPEA_K@Z; MosStorageGetTotalMapDataInBytes(unsigned __int64 *)
0x18000c09a  test    eax, eax
0x18000c09c  jns     short loc_18000C0A9
0x18000c09e  mov     r8d, 72h ; 'r'
0x18000c0a4  jmp     loc_18000C137
0x18000c0a9  cmp     [rbx+0D10h], r15b
0x18000c0b0  jnz     short loc_18000C111
0x18000c0b2  lea     r14, [rbx+68Ch]
0x18000c0b9  mov     dword ptr [rbx+0CF4h], 28h ; '('
0x18000c0c3  mov     rcx, r14
0x18000c0c6  lea     rdx, [rbx+0D20h]
0x18000c0cd  xor     r8d, r8d
0x18000c0d0  call    cs:__imp_?MosQueryPackagesFromPath@@YAJPEBGPEAV?$vector@IV?$allocator@I@std@@@std@@W4StackMode@@@Z; MosQueryPackagesFromPath(ushort const *,std::vector<uint> *,StackMode)
0x18000c0d6  test    eax, eax
0x18000c0d8  jns     short loc_18000C0E2
0x18000c0da  mov     r8d, 79h ; 'y'
0x18000c0e0  jmp     short loc_18000C137
0x18000c0e2  xor     r8d, r8d
0x18000c0e5  mov     dword ptr [rbx+0CF4h], 32h ; '2'
0x18000c0ef  cmp     [rsi], r8d
0x18000c0f2  mov     rcx, r14; unsigned __int16 *
0x18000c0f5  setz    r8b; int
0x18000c0f9  call    ?RecursiveRemoveDirectoryEx@@YAJPEBGHH@Z; RecursiveRemoveDirectoryEx(ushort const *,int,int)
0x18000c0fe  test    eax, eax
0x18000c100  jns     short loc_18000C10A
0x18000c102  mov     r8d, 7Dh ; '}'
0x18000c108  jmp     short loc_18000C137
0x18000c10a  mov     byte ptr [rbx+0D10h], 1
0x18000c111  cmp     [rbx+0CF8h], r15b
0x18000c118  jz      loc_18000C1C9
0x18000c11e  mov     rcx, rbx; this
0x18000c121  call    ?MigrateMapDataInternal@MigrationEngine@@AEAAJXZ; MigrationEngine::MigrateMapDataInternal(void)
0x18000c126  test    eax, eax
0x18000c128  jns     loc_18000C1C9
0x18000c12e  mov     r15b, 1
0x18000c131  mov     r8d, 88h
0x18000c137  mov     r9, rbx
0x18000c13a  mov     rdx, rdi
0x18000c13d  mov     ecx, eax
0x18000c13f  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000c145  mov     edi, eax
0x18000c147  test    eax, eax
0x18000c149  jns     loc_18000C1D5
0x18000c14f  test    r15b, r15b
0x18000c152  jz      short loc_18000C1BD
0x18000c154  cmp     dword ptr [rbx+0CFCh], 0
0x18000c15b  jnz     short loc_18000C1BD
0x18000c15d  cmp     dword ptr [rsi], 0
0x18000c160  mov     r14d, [rbx+0CF4h]
0x18000c167  setnz   sil
0x18000c16b  cmp     dword ptr [rbp+0], 0
0x18000c16f  setnz   bpl
0x18000c173  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000c178  test    al, al
0x18000c17a  jz      short loc_18000C1BD
0x18000c17c  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000c181  mov     ecx, [rbx+0CE0h]
0x18000c187  mov     r9b, sil; bool
0x18000c18a  mov     r8d, [rbx+224h]; unsigned int
0x18000c191  mov     dl, bpl; bool
0x18000c194  mov     [rsp+88h+var_48], r14d; unsigned int
0x18000c199  mov     [rsp+88h+var_50], edi; int
0x18000c19d  mov     [rsp+88h+var_58], ecx; unsigned int
0x18000c1a1  mov     ecx, [rbx+670h]
0x18000c1a7  mov     [rsp+88h+var_60], ecx; unsigned int
0x18000c1ab  mov     ecx, [rbx+894h]
0x18000c1b1  mov     [rsp+88h+var_68], ecx; unsigned int
0x18000c1b5  mov     rcx, rax; this
0x18000c1b8  call    ?StorageMigrationCopyFailedMosHost_@OfflineMapsTelemetry@@QEAAX_NI0IIIJI@Z; OfflineMapsTelemetry::StorageMigrationCopyFailedMosHost_(bool,uint,bool,uint,uint,uint,long,uint)
0x18000c1bd  mov     dword ptr [rbx+0CF0h], 5
0x18000c1c7  jmp     short loc_18000C1D5
0x18000c1c9  xor     edi, edi
0x18000c1cb  mov     dword ptr [rbx+0CF0h], 3
0x18000c1d5  mov     eax, edi
0x18000c1d7  add     rsp, 58h
0x18000c1db  pop     r15
0x18000c1dd  pop     r14
0x18000c1df  pop     rdi
0x18000c1e0  pop     rsi
0x18000c1e1  pop     rbp
0x18000c1e2  pop     rbx
0x18000c1e3  retn
```
