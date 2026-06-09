# MigrationEngine::DeleteNewMapData(void)

- ea: `0x18000bb30`
- end: `0x18000bc17`
- name: `?DeleteNewMapData@MigrationEngine@@AEAAJXZ`
- size: `231`
- prototype: `__int64 __fastcall(MigrationEngine *this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x18000b8d4`
- `0x18000bb30`
- `0x18000cb98`
- `0x18002016c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000bb8a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000bc06`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000bb8a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000bc06`

## string_xrefs

- `0x18000bb7b`: `MigrationEngine::DeleteNewMapData`
- `0x18000bbf7`: `MigrationEngine::DeleteNewMapData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MigrationEngine::DeleteNewMapData(MigrationEngine *this, int a2)
{
  int v3; // eax
  int v4; // eax
  int v5; // edi
  bool v6; // si
  bool v7; // bp
  unsigned __int64 v8; // rdx
  unsigned __int8 v9; // cl
  OfflineMapsTelemetry *v10; // rax
  int v11; // eax

  v3 = *((_DWORD *)this + 828) - 3;
  *((_DWORD *)this + 829) = 120;
  if ( (v3 & 0xFFFFFFFD) != 0 )
    __int2c();
  v4 = RecursiveRemoveDirectoryEx((const unsigned __int16 *)this + 838, a2, *((_DWORD *)this + 417) == 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    ZTraceReportIgnore(v4, "MigrationEngine::DeleteNewMapData", 420, this);
    v6 = *((_DWORD *)this + 417) != 0;
    v7 = *((_DWORD *)this + 5) != 0;
    if ( OfflineMapsTelemetry::IsEnabled(v9, v8) )
    {
      v10 = OfflineMapsTelemetry::Instance();
      OfflineMapsTelemetry::StorageMigrationDeleteNewDataFailedMosHost_(
        v10,
        v7,
        *((_DWORD *)this + 137),
        v6,
        *((_DWORD *)this + 549),
        *((_DWORD *)this + 412),
        *((_DWORD *)this + 824),
        v5);
    }
  }
  v11 = MigrationEngine::CompleteMigration(this);
  if ( v11 < 0 )
    ZTraceReportIgnore(v11, "MigrationEngine::DeleteNewMapData", 433, this);
  return 0;
}

```

## disassembly

```asm
0x18000bb30  push    rbx
0x18000bb32  push    rbp
0x18000bb33  push    rsi
0x18000bb34  push    rdi
0x18000bb35  sub     rsp, 48h
0x18000bb39  mov     eax, [rcx+0CF0h]
0x18000bb3f  mov     rbx, rcx
0x18000bb42  sub     eax, 3
0x18000bb45  mov     dword ptr [rcx+0CF4h], 78h ; 'x'
0x18000bb4f  test    eax, 0FFFFFFFDh
0x18000bb54  jz      short loc_18000BB58
0x18000bb56  int     2Ch; Windows NT - assertion failure
0x18000bb58  xor     r8d, r8d
0x18000bb5b  cmp     [rcx+684h], r8d
0x18000bb62  setz    r8b; int
0x18000bb66  add     rcx, 68Ch; unsigned __int16 *
0x18000bb6d  call    ?RecursiveRemoveDirectoryEx@@YAJPEBGHH@Z; RecursiveRemoveDirectoryEx(ushort const *,int,int)
0x18000bb72  mov     edi, eax
0x18000bb74  test    eax, eax
0x18000bb76  jns     short loc_18000BBE8
0x18000bb78  mov     r9, rbx
0x18000bb7b  lea     rdx, aMigrationengin_10; "MigrationEngine::DeleteNewMapData"
0x18000bb82  mov     r8d, 1A4h
0x18000bb88  mov     ecx, eax
0x18000bb8a  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18000bb90  cmp     dword ptr [rbx+684h], 0
0x18000bb97  setnz   sil
0x18000bb9b  cmp     dword ptr [rbx+14h], 0
0x18000bb9f  setnz   bpl
0x18000bba3  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000bba8  test    al, al
0x18000bbaa  jz      short loc_18000BBE8
0x18000bbac  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000bbb1  mov     ecx, [rbx+0CE0h]
0x18000bbb7  mov     r9b, sil; bool
0x18000bbba  mov     r8d, [rbx+224h]; unsigned int
0x18000bbc1  mov     dl, bpl; bool
0x18000bbc4  mov     [rsp+68h+var_30], edi; int
0x18000bbc8  mov     [rsp+68h+var_38], ecx; unsigned int
0x18000bbcc  mov     ecx, [rbx+670h]
0x18000bbd2  mov     [rsp+68h+var_40], ecx; unsigned int
0x18000bbd6  mov     ecx, [rbx+894h]
0x18000bbdc  mov     [rsp+68h+var_48], ecx; unsigned int
0x18000bbe0  mov     rcx, rax; this
0x18000bbe3  call    ?StorageMigrationDeleteNewDataFailedMosHost_@OfflineMapsTelemetry@@QEAAX_NI0IIIJ@Z; OfflineMapsTelemetry::StorageMigrationDeleteNewDataFailedMosHost_(bool,uint,bool,uint,uint,uint,long)
0x18000bbe8  mov     rcx, rbx; this
0x18000bbeb  call    ?CompleteMigration@MigrationEngine@@AEAAJXZ; MigrationEngine::CompleteMigration(void)
0x18000bbf0  test    eax, eax
0x18000bbf2  jns     short loc_18000BC0C
0x18000bbf4  mov     r9, rbx
0x18000bbf7  lea     rdx, aMigrationengin_10; "MigrationEngine::DeleteNewMapData"
0x18000bbfe  mov     r8d, 1B1h
0x18000bc04  mov     ecx, eax
0x18000bc06  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18000bc0c  xor     eax, eax
0x18000bc0e  add     rsp, 48h
0x18000bc12  pop     rdi
0x18000bc13  pop     rsi
0x18000bc14  pop     rbp
0x18000bc15  pop     rbx
0x18000bc16  retn
```
