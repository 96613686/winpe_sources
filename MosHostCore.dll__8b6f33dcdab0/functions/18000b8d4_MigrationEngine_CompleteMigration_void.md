# MigrationEngine::CompleteMigration(void)

- ea: `0x18000b8d4`
- end: `0x18000bb28`
- name: `?CompleteMigration@MigrationEngine@@AEAAJXZ`
- size: `596`
- prototype: `__int64 __fastcall(MigrationEngine *this, unsigned __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000b6f4`
- `0x18000bb30`
- `0x18000bc20`
- `0x18000c350`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x18000b8d4`
- `0x18000c800`
- `0x18000c9cc`
- `0x18000cd30`
- `0x18000cf2c`
- `0x1800203f0`
- `0x180025010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000b943`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000b943`

## pseudocode

```c
__int64 __fastcall MigrationEngine::CompleteMigration(MigrationEngine *this, unsigned __int64 a2)
{
  int v3; // eax
  __int64 v4; // rcx
  int v5; // r8d
  __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  _DWORD *v8; // rdi
  unsigned int v9; // esi
  int v10; // eax
  int v11; // ecx
  bool v12; // bp
  bool v13; // r14
  OfflineMapsTelemetry *v14; // rax
  unsigned int v15; // ebp
  bool v16; // r14
  bool v17; // r15
  OfflineMapsTelemetry *v18; // rax
  bool v19; // bp
  bool v20; // r14
  OfflineMapsTelemetry *v21; // rax
  unsigned int v22; // esi
  bool v23; // bp
  bool v24; // r14
  OfflineMapsTelemetry *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 result; // rax

  if ( !*((_BYTE *)this + 3352) )
  {
    v3 = RegUtils::DeleteMapsPersistedRegValue(this, L"MigrationTargetDeviceGuid");
    if ( v3 >= 0 )
    {
      v3 = RegUtils::DeleteMapsPersistedRegValue(v4, L"MigrationFlags");
      if ( v3 >= 0 )
      {
        v3 = RegUtils::DeleteMapsPersistedRegValue(v6, L"MigrationMapsToRestore");
        if ( v3 >= 0 )
          goto LABEL_9;
        v5 = 408;
      }
      else
      {
        v5 = 407;
      }
    }
    else
    {
      v5 = 406;
    }
    ZTraceReportPropagation(v3, "MigrationEngine::ClearSavedMigration", v5, this);
LABEL_9:
    v8 = (_DWORD *)((char *)this + 3312);
    v9 = *((_DWORD *)this + 828);
    v10 = *((_DWORD *)this + 417);
    v11 = *((_DWORD *)this + 5);
    if ( *((_DWORD *)this + 831) )
    {
      v12 = v10 != 0;
      v13 = v11 != 0;
      if ( OfflineMapsTelemetry::IsEnabled(v11, v7) )
      {
        v14 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::StorageMigrationCanceledMosHost_(
          v14,
          v13,
          *((_DWORD *)this + 137),
          v12,
          *((_DWORD *)this + 549),
          *((_DWORD *)this + 412),
          *((_DWORD *)this + 824),
          v9);
      }
    }
    else if ( *((int *)this + 837) >= 0 )
    {
      v19 = v10 != 0;
      v20 = v11 != 0;
      if ( OfflineMapsTelemetry::IsEnabled(v11, v7) )
      {
        v21 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::StorageMigrationCompleteMosHost_(
          v21,
          v20,
          *((_DWORD *)this + 137),
          v19,
          *((_DWORD *)this + 549),
          *((_DWORD *)this + 412),
          *((_DWORD *)this + 824),
          v9);
      }
    }
    else
    {
      v15 = *((_DWORD *)this + 829);
      v16 = v10 != 0;
      v17 = v11 != 0;
      if ( OfflineMapsTelemetry::IsEnabled(v11, v7) )
      {
        v18 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::StorageMigrationFailedMosHost_(
          v18,
          v17,
          *((_DWORD *)this + 137),
          v16,
          *((_DWORD *)this + 549),
          *((_DWORD *)this + 412),
          *((_DWORD *)this + 824),
          v9,
          *((_DWORD *)this + 837),
          v15);
      }
    }
    goto LABEL_19;
  }
  v8 = (_DWORD *)((char *)this + 3312);
  v22 = *((_DWORD *)this + 828);
  v23 = *((_DWORD *)this + 417) != 0;
  v24 = *((_DWORD *)this + 5) != 0;
  if ( OfflineMapsTelemetry::IsEnabled((unsigned __int8)this, a2) )
  {
    v25 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::StorageMigrationSuspendedMosHost_(
      v25,
      v24,
      *((_DWORD *)this + 137),
      v23,
      *((_DWORD *)this + 549),
      *((_DWORD *)this + 412),
      *((_DWORD *)this + 824),
      v22);
  }
LABEL_19:
  v26 = *(_QWORD *)this;
  v27 = *((unsigned int *)this + 837);
  *v8 = 0;
  (*(void (__fastcall **)(MigrationEngine *, __int64, char *))(v26 + 16))(this, v27, (char *)this + 3360);
  result = 0;
  *((_DWORD *)this + 829) = 0;
  return result;
}

```

## disassembly

```asm
0x18000b8d4  push    rbx
0x18000b8d6  push    rbp
0x18000b8d7  push    rsi
0x18000b8d8  push    rdi
0x18000b8d9  push    r14
0x18000b8db  push    r15
0x18000b8dd  sub     rsp, 58h
0x18000b8e1  cmp     byte ptr [rcx+0D18h], 0
0x18000b8e8  mov     rbx, rcx
0x18000b8eb  jnz     loc_18000BA8C
0x18000b8f1  lea     rdx, Value; "MigrationTargetDeviceGuid"
0x18000b8f8  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18000b8fd  test    eax, eax
0x18000b8ff  jns     short loc_18000B909
0x18000b901  mov     r8d, 196h
0x18000b907  jmp     short loc_18000B937
0x18000b909  lea     rdx, aMigrationflags; "MigrationFlags"
0x18000b910  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18000b915  test    eax, eax
0x18000b917  jns     short loc_18000B921
0x18000b919  mov     r8d, 197h
0x18000b91f  jmp     short loc_18000B937
0x18000b921  lea     rdx, aMigrationmapst; "MigrationMapsToRestore"
0x18000b928  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18000b92d  test    eax, eax
0x18000b92f  jns     short loc_18000B949
0x18000b931  mov     r8d, 198h
0x18000b937  mov     r9, rbx
0x18000b93a  lea     rdx, aMigrationengin_6; "MigrationEngine::ClearSavedMigration"
0x18000b941  mov     ecx, eax
0x18000b943  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000b949  cmp     dword ptr [rbx+0CFCh], 0
0x18000b950  lea     rdi, [rbx+0CF0h]
0x18000b957  mov     esi, [rdi]
0x18000b959  mov     eax, [rbx+684h]
0x18000b95f  mov     ecx, [rbx+14h]; unsigned __int8
0x18000b962  jz      short loc_18000B9BE
0x18000b964  test    eax, eax
0x18000b966  setnz   bpl
0x18000b96a  test    ecx, ecx
0x18000b96c  setnz   r14b
0x18000b970  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000b975  test    al, al
0x18000b977  jz      loc_18000BAED
0x18000b97d  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000b982  mov     ecx, [rbx+0CE0h]
0x18000b988  mov     r9b, bpl; bool
0x18000b98b  mov     r8d, [rbx+224h]; unsigned int
0x18000b992  mov     dl, r14b; bool
0x18000b995  mov     [rsp+88h+var_50], esi; unsigned int
0x18000b999  mov     [rsp+88h+var_58], ecx; unsigned int
0x18000b99d  mov     ecx, [rbx+670h]
0x18000b9a3  mov     [rsp+88h+var_60], ecx; unsigned int
0x18000b9a7  mov     ecx, [rbx+894h]
0x18000b9ad  mov     [rsp+88h+var_68], ecx; unsigned int
0x18000b9b1  mov     rcx, rax; this
0x18000b9b4  call    ?StorageMigrationCanceledMosHost_@OfflineMapsTelemetry@@QEAAX_NI0IIII@Z; OfflineMapsTelemetry::StorageMigrationCanceledMosHost_(bool,uint,bool,uint,uint,uint,uint)
0x18000b9b9  jmp     loc_18000BAED
0x18000b9be  cmp     dword ptr [rbx+0D14h], 0
0x18000b9c5  jge     short loc_18000BA35
0x18000b9c7  mov     ebp, [rbx+0CF4h]
0x18000b9cd  test    eax, eax
0x18000b9cf  setnz   r14b
0x18000b9d3  test    ecx, ecx
0x18000b9d5  setnz   r15b
0x18000b9d9  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000b9de  test    al, al
0x18000b9e0  jz      loc_18000BAED
0x18000b9e6  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000b9eb  mov     ecx, [rbx+0D14h]
0x18000b9f1  mov     r9b, r14b; bool
0x18000b9f4  mov     r8d, [rbx+224h]; unsigned int
0x18000b9fb  mov     dl, r15b; bool
0x18000b9fe  mov     [rsp+88h+var_40], ebp; unsigned int
0x18000ba02  mov     [rsp+88h+var_48], ecx; int
0x18000ba06  mov     ecx, [rbx+0CE0h]
0x18000ba0c  mov     [rsp+88h+var_50], esi; unsigned int
0x18000ba10  mov     [rsp+88h+var_58], ecx; unsigned int
0x18000ba14  mov     ecx, [rbx+670h]
0x18000ba1a  mov     [rsp+88h+var_60], ecx; unsigned int
0x18000ba1e  mov     ecx, [rbx+894h]
0x18000ba24  mov     [rsp+88h+var_68], ecx; unsigned int
0x18000ba28  mov     rcx, rax; this
0x18000ba2b  call    ?StorageMigrationFailedMosHost_@OfflineMapsTelemetry@@QEAAX_NI0IIIIJI@Z; OfflineMapsTelemetry::StorageMigrationFailedMosHost_(bool,uint,bool,uint,uint,uint,uint,long,uint)
0x18000ba30  jmp     loc_18000BAED
0x18000ba35  test    eax, eax
0x18000ba37  setnz   bpl
0x18000ba3b  test    ecx, ecx
0x18000ba3d  setnz   r14b
0x18000ba41  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000ba46  test    al, al
0x18000ba48  jz      loc_18000BAED
0x18000ba4e  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000ba53  mov     ecx, [rbx+0CE0h]
0x18000ba59  mov     r9b, bpl; bool
0x18000ba5c  mov     r8d, [rbx+224h]; unsigned int
0x18000ba63  mov     dl, r14b; bool
0x18000ba66  mov     [rsp+88h+var_50], esi; unsigned int
0x18000ba6a  mov     [rsp+88h+var_58], ecx; unsigned int
0x18000ba6e  mov     ecx, [rbx+670h]
0x18000ba74  mov     [rsp+88h+var_60], ecx; unsigned int
0x18000ba78  mov     ecx, [rbx+894h]
0x18000ba7e  mov     [rsp+88h+var_68], ecx; unsigned int
0x18000ba82  mov     rcx, rax; this
0x18000ba85  call    ?StorageMigrationCompleteMosHost_@OfflineMapsTelemetry@@QEAAX_NI0IIII@Z; OfflineMapsTelemetry::StorageMigrationCompleteMosHost_(bool,uint,bool,uint,uint,uint,uint)
0x18000ba8a  jmp     short loc_18000BAED
0x18000ba8c  cmp     dword ptr [rcx+684h], 0
0x18000ba93  lea     rdi, [rcx+0CF0h]
0x18000ba9a  mov     esi, [rdi]
0x18000ba9c  setnz   bpl
0x18000baa0  cmp     dword ptr [rcx+14h], 0
0x18000baa4  setnz   r14b
0x18000baa8  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000baad  test    al, al
0x18000baaf  jz      short loc_18000BAED
0x18000bab1  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000bab6  mov     ecx, [rbx+0CE0h]
0x18000babc  mov     r9b, bpl; bool
0x18000babf  mov     r8d, [rbx+224h]; unsigned int
0x18000bac6  mov     dl, r14b; bool
0x18000bac9  mov     [rsp+88h+var_50], esi; unsigned int
0x18000bacd  mov     [rsp+88h+var_58], ecx; unsigned int
0x18000bad1  mov     ecx, [rbx+670h]
0x18000bad7  mov     [rsp+88h+var_60], ecx; unsigned int
0x18000badb  mov     ecx, [rbx+894h]
0x18000bae1  mov     [rsp+88h+var_68], ecx; unsigned int
0x18000bae5  mov     rcx, rax; this
0x18000bae8  call    ?StorageMigrationSuspendedMosHost_@OfflineMapsTelemetry@@QEAAX_NI0IIII@Z; OfflineMapsTelemetry::StorageMigrationSuspendedMosHost_(bool,uint,bool,uint,uint,uint,uint)
0x18000baed  mov     rax, [rbx]
0x18000baf0  lea     r8, [rbx+0D20h]
0x18000baf7  mov     edx, [rbx+0D14h]
0x18000bafd  mov     rcx, rbx
0x18000bb00  mov     dword ptr [rdi], 0
0x18000bb06  mov     rax, [rax+10h]
0x18000bb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb0f  xor     eax, eax
0x18000bb11  mov     dword ptr [rbx+0CF4h], 0
0x18000bb1b  add     rsp, 58h
0x18000bb1f  pop     r15
0x18000bb21  pop     r14
0x18000bb23  pop     rdi
0x18000bb24  pop     rsi
0x18000bb25  pop     rbp
0x18000bb26  pop     rbx
0x18000bb27  retn
```
