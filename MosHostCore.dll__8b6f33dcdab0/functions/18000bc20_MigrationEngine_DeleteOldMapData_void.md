# MigrationEngine::DeleteOldMapData(void)

- ea: `0x18000bc20`
- end: `0x18000bcfa`
- name: `?DeleteOldMapData@MigrationEngine@@AEAAJXZ`
- size: `218`
- prototype: `__int64 __fastcall(MigrationEngine *this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x18000b8d4`
- `0x18000bc20`
- `0x18000cc64`
- `0x18002016c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000bc6d`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000bce9`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000bc6d`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000bce9`

## string_xrefs

- `0x18000bc5e`: `MigrationEngine::DeleteOldMapData`
- `0x18000bcda`: `MigrationEngine::DeleteOldMapData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MigrationEngine::DeleteOldMapData(MigrationEngine *this, int a2)
{
  bool v2; // zf
  int v4; // eax
  int v5; // edi
  bool v6; // si
  bool v7; // bp
  unsigned __int64 v8; // rdx
  unsigned __int8 v9; // cl
  OfflineMapsTelemetry *v10; // rax
  int v11; // eax

  v2 = *((_DWORD *)this + 828) == 4;
  *((_DWORD *)this + 829) = 130;
  if ( !v2 )
    __int2c();
  v4 = RecursiveRemoveDirectoryEx((const unsigned __int16 *)this + 14, a2, *((_DWORD *)this + 5) == 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    ZTraceReportIgnore(v4, "MigrationEngine::DeleteOldMapData", 444, this);
    v6 = *((_DWORD *)this + 417) != 0;
    v7 = *((_DWORD *)this + 5) != 0;
    if ( OfflineMapsTelemetry::IsEnabled(v9, v8) )
    {
      v10 = OfflineMapsTelemetry::Instance();
      OfflineMapsTelemetry::StorageMigrationDeleteOldDataFailedMosHost_(
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
    ZTraceReportIgnore(v11, "MigrationEngine::DeleteOldMapData", 457, this);
  return 0;
}

```

## disassembly

```asm
0x18000bc20  push    rbx
0x18000bc22  push    rbp
0x18000bc23  push    rsi
0x18000bc24  push    rdi
0x18000bc25  sub     rsp, 48h
0x18000bc29  cmp     dword ptr [rcx+0CF0h], 4
0x18000bc30  mov     rbx, rcx
0x18000bc33  mov     dword ptr [rcx+0CF4h], 82h
0x18000bc3d  jz      short loc_18000BC41
0x18000bc3f  int     2Ch; Windows NT - assertion failure
0x18000bc41  xor     r8d, r8d
0x18000bc44  cmp     [rcx+14h], r8d
0x18000bc48  setz    r8b; int
0x18000bc4c  add     rcx, 1Ch; unsigned __int16 *
0x18000bc50  call    ?RecursiveRemoveDirectoryEx@@YAJPEBGHH@Z; RecursiveRemoveDirectoryEx(ushort const *,int,int)
0x18000bc55  mov     edi, eax
0x18000bc57  test    eax, eax
0x18000bc59  jns     short loc_18000BCCB
0x18000bc5b  mov     r9, rbx
0x18000bc5e  lea     rdx, aMigrationengin_3; "MigrationEngine::DeleteOldMapData"
0x18000bc65  mov     r8d, 1BCh
0x18000bc6b  mov     ecx, eax
0x18000bc6d  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18000bc73  cmp     dword ptr [rbx+684h], 0
0x18000bc7a  setnz   sil
0x18000bc7e  cmp     dword ptr [rbx+14h], 0
0x18000bc82  setnz   bpl
0x18000bc86  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000bc8b  test    al, al
0x18000bc8d  jz      short loc_18000BCCB
0x18000bc8f  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000bc94  mov     ecx, [rbx+0CE0h]
0x18000bc9a  mov     r9b, sil; bool
0x18000bc9d  mov     r8d, [rbx+224h]; unsigned int
0x18000bca4  mov     dl, bpl; bool
0x18000bca7  mov     [rsp+68h+var_30], edi; int
0x18000bcab  mov     [rsp+68h+var_38], ecx; unsigned int
0x18000bcaf  mov     ecx, [rbx+670h]
0x18000bcb5  mov     [rsp+68h+var_40], ecx; unsigned int
0x18000bcb9  mov     ecx, [rbx+894h]
0x18000bcbf  mov     [rsp+68h+var_48], ecx; unsigned int
0x18000bcc3  mov     rcx, rax; this
0x18000bcc6  call    ?StorageMigrationDeleteOldDataFailedMosHost_@OfflineMapsTelemetry@@QEAAX_NI0IIIJ@Z; OfflineMapsTelemetry::StorageMigrationDeleteOldDataFailedMosHost_(bool,uint,bool,uint,uint,uint,long)
0x18000bccb  mov     rcx, rbx; this
0x18000bcce  call    ?CompleteMigration@MigrationEngine@@AEAAJXZ; MigrationEngine::CompleteMigration(void)
0x18000bcd3  test    eax, eax
0x18000bcd5  jns     short loc_18000BCEF
0x18000bcd7  mov     r9, rbx
0x18000bcda  lea     rdx, aMigrationengin_3; "MigrationEngine::DeleteOldMapData"
0x18000bce1  mov     r8d, 1C9h
0x18000bce7  mov     ecx, eax
0x18000bce9  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18000bcef  xor     eax, eax
0x18000bcf1  add     rsp, 48h
0x18000bcf5  pop     rdi
0x18000bcf6  pop     rsi
0x18000bcf7  pop     rbp
0x18000bcf8  pop     rbx
0x18000bcf9  retn
```
