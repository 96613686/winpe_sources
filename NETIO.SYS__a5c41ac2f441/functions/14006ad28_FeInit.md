# FeInit

- ea: `0x14006ad28`
- end: `0x14006b34f`
- name: `FeInit`
- size: `1575`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1400aa388`

## callees

- `0x140009520`
- `0x140009d80`
- `0x140009e00`
- `0x14000afa0`
- `0x14001ce80`
- `0x140044380`
- `0x140045a28`
- `0x14004f054`
- `0x14004fd24`
- `0x1400506ac`
- `0x140050834`
- `0x140050a90`
- `0x140064164`
- `0x1400659ac`
- `0x140066180`
- `0x140067c60`
- `0x14006ad28`
- `0x14006bbb8`
- `0x14006bf4c`
- `0x14006c02c`
- `0x14006c65c`
- `0x14006c6d0`
- `0x140077fa0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14006ae9a`
- `ntoskrnl!ZwClose` at `0x14006ae9a`
- `ntoskrnl!MmIsVerifierEnabled` at `0x14006ae14`
- `ntoskrnl!MmIsVerifierEnabled` at `0x14006ae14`
- `ntoskrnl!SeTokenFromAccessInformation` at `0x14006b136`
- `ntoskrnl!SeTokenFromAccessInformation` at `0x14006b136`
- `ntoskrnl!RtlGetVersion` at `0x14006b2f8`
- `ntoskrnl!RtlGetVersion` at `0x14006b2f8`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14006afa0`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14006afa0`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006b233`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006b275`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006b2b7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006b233`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006b275`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006b2b7`

## string_xrefs

- `0x14006ae25`: `\Registry\Machine\System\CurrentControlSet\Services\BFE\Parameters`

## pseudocode

```c
__int64 __fastcall FeInit(__int64 a1, __int64 a2, unsigned int a3)
{
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 inited; // rbx
  int v6; // eax
  PNPAGED_LOOKASIDE_LIST v7; // rcx
  __int64 v8; // r8
  const char *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  PNPAGED_LOOKASIDE_LIST v12; // rbx
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE VersionInformation[284]; // [rsp+60h] [rbp-A0h] BYREF

  Handle = 0;
  v15 = 0;
  memset(VersionInformation, 0, sizeof(VersionInformation));
  if ( (WPP_MAIN_CB.ActiveThreadCount & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = WPP_MAIN_CB.ActiveThreadCount & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline();
  isFeature_Firewall_042024Enabled = IsEnabledDeviceUsageNoInline != 0;
  if ( !a3 )
  {
    inited = WfpPoolAllocNonPaged(2304, 1399875159, &gWfpGlobal);
    if ( inited )
      goto LABEL_42;
    memset(gWfpGlobal, 0, 0x900u);
    inited = WfpObjectManagerInitialize();
    if ( inited )
      goto LABEL_42;
  }
  if ( (WPP_MAIN_CB.ActiveThreadCount & 0x10) != 0 )
    v6 = WPP_MAIN_CB.ActiveThreadCount & 1;
  else
    v6 = Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline();
  if ( v6 )
    InitializeWfpVerifierSettings();
  else
    MmIsVerifierEnabled((PULONG)&gWfpGlobal[13].L.ListEntry.Blink + 1);
  WfpRegOpenKey(&Handle);
  if ( !a3 )
  {
    LODWORD(gWfpGlobal[1].L.ListEntry.Flink) = 0;
    HIDWORD(gWfpGlobal[1].L.ListEntry.Flink) = 2;
  }
  BYTE4(gWfpGlobal[1].L.Free) = 0;
  *((_DWORD *)&gWfpGlobal[3].L.SingleListHead + 3) = 1;
  gWfpGlobal[1].L.ListEntry.Blink = (struct _LIST_ENTRY *)KfdFilterFreeNotify;
  inited = WfpSizeTMultiply(99, 136, &v15);
  if ( inited )
    goto LABEL_42;
  if ( a3 )
  {
    if ( *((_WORD *)&gWfpGlobal[3].L.SingleListHead + 4) != 99 )
    {
      v8 = 3221225485LL;
      v9 = "IsValidIndex";
      goto LABEL_41;
    }
  }
  else
  {
    v10 = v15;
    *((_WORD *)&gWfpGlobal[3].L.SingleListHead + 4) = 99;
    inited = WfpPoolAllocNonPaged(v10, 1399875159, &gWfpGlobal[3]);
    if ( inited )
      goto LABEL_42;
  }
  ExInitializeNPagedLookasideList(gWfpGlobal, 0, 0, 0x200u, 0x60u, 0x4D706657u, 0);
  *((_DWORD *)&gWfpGlobal[1].L.SingleListHead + 2) = 1;
  if ( !a3 )
  {
    inited = WfpInitFastRWLockModule();
    if ( inited )
      goto LABEL_42;
    inited = WfpCreateFastRWLock(&gWfpGlobal[1]);
    if ( inited )
      goto LABEL_42;
    *((_DWORD *)&gWfpGlobal[1].L.SingleListHead + 3) = 1;
    inited = WfpCreateFastRWLock(&gWfpGlobal[13].L.ListEntry);
    if ( inited )
      goto LABEL_42;
    *(_DWORD *)&gWfpGlobal[1].L.Depth = 1;
    inited = FeInitCalloutTable();
    if ( inited )
      goto LABEL_42;
    gWfpGlobal[1].L.AllocateMisses = 1;
    inited = FeInitClassifyContextModule();
    if ( inited )
      goto LABEL_42;
    gWfpGlobal[1].L.TotalFrees = 1;
  }
  inited = CreateFilterHashtable();
  if ( !inited )
  {
    gWfpGlobal[1].L.FreeMisses = 1;
    inited = InitLayers(a3);
    if ( !inited )
    {
      gWfpGlobal[1].L.TotalAllocates = 1;
      inited = InitIndexes();
      if ( !inited )
      {
        if ( !a3 )
        {
          inited = WfpCreateFastRWLock(&gWfpGlobal[3].L.AllocateEx);
          if ( inited )
            goto LABEL_42;
          LODWORD(gWfpGlobal[1].L.AllocateEx) = 1;
        }
        memset(&gWfpGlobal[3].L.ListEntry, 0, 0x1C0u);
        if ( !a3 )
          LODWORD(gWfpGlobal[7].L.ListHead.Alignment) = 1;
        inited = InitializeFastCaching();
        if ( !inited )
        {
          SeTokenFromAccessInformation(0, 0, 0, &accessTokenSize);
          inited = InitializeAccessPreCheckCache();
          if ( !inited )
          {
            if ( a3 )
            {
              LODWORD(gWfpGlobal[1].L.ListEntry.Flink) = 0;
            }
            else
            {
              v12 = gWfpGlobal;
              if ( *((_DWORD *)&gWfpGlobal[11].L.SingleListHead + 2) )
              {
                LOBYTE(v11) = 1;
                v12[11].L.ListHead.Alignment = NetioAllocateAndInitializeStackBlock(v11, 1114662487);
                v7 = gWfpGlobal;
                if ( !gWfpGlobal[11].L.ListHead.Alignment )
                {
                  v8 = 3221225495LL;
                  v9 = "NetioAllocateAndInitializeStackBlock";
LABEL_41:
                  inited = WfpReportSysErrorAsNtStatus(v7, v9, v8, 1);
                  if ( !inited )
                    return inited;
                  goto LABEL_42;
                }
                memset((char *)&gWfpGlobal[11].L.SingleListHead + 12, -1, 0x63u);
              }
            }
            IncrementEpoch(&gWfpGlobal[7]);
            if ( !a3 )
            {
              KeInitializeSpinLock((PKSPIN_LOCK)&gWfpGlobal[9].L.AllocateEx);
              gWfpGlobal[9].L.FreeEx = 0;
              LODWORD(gWfpGlobal[9].L.ListEntry.Flink) = 0;
              HIDWORD(gWfpGlobal[9].L.ListEntry.Flink) = 0;
              KeInitializeSpinLock((PKSPIN_LOCK)&gWfpGlobal[9].L.ListEntry.Blink);
              *(_QWORD *)&gWfpGlobal[9].L.LastTotalAllocates = 0;
              gWfpGlobal[9].L.Future[0] = 0;
              gWfpGlobal[9].L.Future[1] = 0;
              KeInitializeSpinLock((PKSPIN_LOCK)&gWfpGlobal[9].L.Future[2]);
              *(_QWORD *)&gWfpGlobal[9].L.Future[4] = 0;
              gWfpGlobal[9].L.Future[6] = 0;
              gWfpGlobal[9].L.Future[7] = 0;
              *(_DWORD *)VersionInformation = 284;
              gWfpGlobal[13].L.Future[2] = RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0
                                        && VersionInformation[282] != 1;
            }
            inited = WfpCreateFastRWLock(&gLayerStatsLock);
            if ( !inited )
            {
              gLayerStatsLockInitialized = 1;
              return inited;
            }
          }
        }
      }
    }
  }
LABEL_42:
  FeShutdown(0);
  WfpReportError(inited, "FeInit");
  return inited;
}

```

## disassembly

```asm
0x14006ad28  push    rbp
0x14006ad2a  push    rbx
0x14006ad2b  push    rsi
0x14006ad2c  push    rdi
0x14006ad2d  push    r14
0x14006ad2f  push    r15
0x14006ad31  lea     rbp, [rsp-98h]
0x14006ad39  sub     rsp, 198h
0x14006ad40  mov     rax, cs:__security_cookie
0x14006ad47  xor     rax, rsp
0x14006ad4a  mov     [rbp+0C0h+var_40], rax
0x14006ad51  xor     esi, esi
0x14006ad53  lea     rcx, [rsp+1C0h+VersionInformation]; void *
0x14006ad58  mov     edi, r8d
0x14006ad5b  mov     [rsp+1C0h+Handle], rsi
0x14006ad60  mov     r8d, 11Ch; Size
0x14006ad66  mov     [rsp+1C0h+var_180], esi
0x14006ad6a  xor     edx, edx; Val
0x14006ad6c  mov     [rsp+1C0h+var_170], rsi
0x14006ad71  call    memset
0x14006ad76  mov     eax, cs:WPP_MAIN_CB.ActiveThreadCount
0x14006ad7c  lea     r14d, [rsi+1]
0x14006ad80  test    al, 10h
0x14006ad82  jz      short loc_14006AD89
0x14006ad84  and     eax, r14d
0x14006ad87  jmp     short loc_14006AD8E
0x14006ad89  call    Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline
0x14006ad8e  test    eax, eax
0x14006ad90  mov     ecx, esi
0x14006ad92  setnz   cl
0x14006ad95  mov     cs:isFeature_Firewall_042024Enabled, ecx
0x14006ad9b  test    edi, edi
0x14006ad9d  jnz     short loc_14006ADE7
0x14006ad9f  mov     r15d, 900h
0x14006ada5  lea     r8, gWfpGlobal
0x14006adac  mov     ecx, r15d
0x14006adaf  mov     edx, 53706657h
0x14006adb4  call    WfpPoolAllocNonPaged
0x14006adb9  mov     rbx, rax
0x14006adbc  test    rax, rax
0x14006adbf  jnz     loc_14006B1AB
0x14006adc5  mov     rcx, cs:gWfpGlobal; void *
0x14006adcc  mov     r8d, r15d; Size
0x14006adcf  xor     edx, edx; Val
0x14006add1  call    memset
0x14006add6  call    WfpObjectManagerInitialize
0x14006addb  mov     rbx, rax
0x14006adde  test    rax, rax
0x14006ade1  jnz     loc_14006B1AB
0x14006ade7  mov     eax, cs:WPP_MAIN_CB.ActiveThreadCount
0x14006aded  test    al, 10h
0x14006adef  jz      short loc_14006ADF6
0x14006adf1  and     eax, r14d
0x14006adf4  jmp     short loc_14006ADFB
0x14006adf6  call    Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline
0x14006adfb  test    eax, eax
0x14006adfd  jz      short loc_14006AE06
0x14006adff  call    InitializeWfpVerifierSettings
0x14006ae04  jmp     short loc_14006AE20
0x14006ae06  mov     rcx, cs:gWfpGlobal
0x14006ae0d  add     rcx, 6CCh; VerifierFlags
0x14006ae14  call    cs:__imp_MmIsVerifierEnabled
0x14006ae1b  nop     dword ptr [rax+rax+00h]
0x14006ae20  lea     r8, [rsp+1C0h+var_180]
0x14006ae25  lea     rdx, aRegistryMachin_9; "\\Registry\\Machine\\System\\CurrentCon"...
0x14006ae2c  lea     rcx, [rsp+1C0h+Handle]; KeyHandle
0x14006ae31  call    WfpRegOpenKey
0x14006ae36  test    rax, rax
0x14006ae39  jnz     short loc_14006AEAB
0x14006ae3b  cmp     [rsp+1C0h+var_180], esi
0x14006ae3f  jz      short loc_14006AEAB
0x14006ae41  mov     rcx, [rsp+1C0h+Handle]; KeyHandle
0x14006ae46  lea     r9, [rsp+1C0h+var_180]
0x14006ae4b  lea     r8, [rsp+1C0h+var_17C]
0x14006ae50  mov     [rsp+1C0h+var_17C], esi
0x14006ae54  lea     rdx, aWfpstackexpans; "WfpStackExpansionEnabled"
0x14006ae5b  mov     [rsp+1C0h+var_180], esi
0x14006ae5f  call    WfpRegGetUint32Value
0x14006ae64  test    rax, rax
0x14006ae67  jnz     short loc_14006AE87
0x14006ae69  cmp     [rsp+1C0h+var_180], esi
0x14006ae6d  jz      short loc_14006AE87
0x14006ae6f  cmp     [rsp+1C0h+var_17C], esi
0x14006ae73  mov     ecx, esi
0x14006ae75  mov     rax, cs:gWfpGlobal
0x14006ae7c  setnz   cl
0x14006ae7f  mov     [rax+588h], ecx
0x14006ae85  jmp     short loc_14006AE95
0x14006ae87  mov     rax, cs:gWfpGlobal
0x14006ae8e  mov     [rax+588h], r14d
0x14006ae95  mov     rcx, [rsp+1C0h+Handle]; Handle
0x14006ae9a  call    cs:__imp_ZwClose
0x14006aea1  nop     dword ptr [rax+rax+00h]
0x14006aea6  mov     [rsp+1C0h+Handle], rsi
0x14006aeab  test    edi, edi
0x14006aead  jnz     short loc_14006AECD
0x14006aeaf  mov     rax, cs:gWfpGlobal
0x14006aeb6  mov     [rax+0C0h], esi
0x14006aebc  mov     rax, cs:gWfpGlobal
0x14006aec3  mov     dword ptr [rax+0C4h], 2
0x14006aecd  mov     rax, cs:gWfpGlobal
0x14006aed4  lea     rcx, KfdFilterFreeNotify
0x14006aedb  mov     edx, 88h
0x14006aee0  lea     r8, [rsp+1C0h+var_170]
0x14006aee5  mov     [rax+0BCh], sil
0x14006aeec  mov     rax, cs:gWfpGlobal
0x14006aef3  lea     r15d, [rdx-25h]
0x14006aef7  mov     [rax+18Ch], r14d
0x14006aefe  mov     rax, cs:gWfpGlobal
0x14006af05  mov     [rax+0C8h], rcx
0x14006af0c  mov     ecx, r15d
0x14006af0f  call    WfpSizeTMultiply
0x14006af14  mov     rbx, rax
0x14006af17  test    rax, rax
0x14006af1a  jnz     loc_14006B1AB
0x14006af20  mov     rax, cs:gWfpGlobal
0x14006af27  test    edi, edi
0x14006af29  jz      short loc_14006AF47
0x14006af2b  cmp     [rax+188h], r15w
0x14006af33  jz      short loc_14006AF78
0x14006af35  mov     r8d, 0C000000Dh
0x14006af3b  lea     rdx, aIsvalidindex; "IsValidIndex"
0x14006af42  jmp     loc_14006B19B
0x14006af47  mov     rcx, [rsp+1C0h+var_170]
0x14006af4c  mov     edx, 53706657h
0x14006af51  mov     [rax+188h], r15w
0x14006af59  mov     r8, cs:gWfpGlobal
0x14006af60  add     r8, 180h
0x14006af67  call    WfpPoolAllocNonPaged
0x14006af6c  mov     rbx, rax
0x14006af6f  test    rax, rax
0x14006af72  jnz     loc_14006B1AB
0x14006af78  mov     rcx, cs:gWfpGlobal; Lookaside
0x14006af7f  mov     r9d, 200h; Flags
0x14006af85  mov     [rsp+1C0h+Depth], si; Depth
0x14006af8a  xor     r8d, r8d; Free
0x14006af8d  mov     [rsp+1C0h+Tag], 4D706657h; Tag
0x14006af95  xor     edx, edx; Allocate
0x14006af97  mov     [rsp+1C0h+Size], 60h ; '`'; Size
0x14006afa0  call    cs:__imp_ExInitializeNPagedLookasideList
0x14006afa7  nop     dword ptr [rax+rax+00h]
0x14006afac  mov     rax, cs:gWfpGlobal
0x14006afb3  mov     [rax+88h], r14d
0x14006afba  test    edi, edi
0x14006afbc  jnz     loc_14006B068
0x14006afc2  call    WfpInitFastRWLockModule
0x14006afc7  mov     rbx, rax
0x14006afca  test    rax, rax
0x14006afcd  jnz     loc_14006B1AB
0x14006afd3  mov     rcx, cs:gWfpGlobal
0x14006afda  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14006afde  call    WfpCreateFastRWLock
0x14006afe3  mov     rbx, rax
0x14006afe6  test    rax, rax
0x14006afe9  jnz     loc_14006B1AB
0x14006afef  mov     rax, cs:gWfpGlobal
0x14006aff6  mov     [rax+8Ch], r14d
0x14006affd  mov     rcx, cs:gWfpGlobal
0x14006b004  add     rcx, 6C0h
0x14006b00b  call    WfpCreateFastRWLock
0x14006b010  mov     rbx, rax
0x14006b013  test    rax, rax
0x14006b016  jnz     loc_14006B1AB
0x14006b01c  mov     rax, cs:gWfpGlobal
0x14006b023  mov     [rax+90h], r14d
0x14006b02a  call    FeInitCalloutTable
0x14006b02f  mov     rbx, rax
0x14006b032  test    rax, rax
0x14006b035  jnz     loc_14006B1AB
0x14006b03b  mov     rax, cs:gWfpGlobal
0x14006b042  mov     [rax+98h], r14d
0x14006b049  call    FeInitClassifyContextModule
0x14006b04e  mov     rbx, rax
0x14006b051  test    rax, rax
0x14006b054  jnz     loc_14006B1AB
0x14006b05a  mov     rax, cs:gWfpGlobal
0x14006b061  mov     [rax+9Ch], r14d
0x14006b068  call    CreateFilterHashtable
0x14006b06d  mov     rbx, rax
0x14006b070  test    rax, rax
0x14006b073  jnz     loc_14006B1AB
0x14006b079  mov     rax, cs:gWfpGlobal
0x14006b080  mov     ecx, edi
0x14006b082  mov     [rax+0A0h], r14d
0x14006b089  call    InitLayers
0x14006b08e  mov     rbx, rax
0x14006b091  test    rax, rax
0x14006b094  jnz     loc_14006B1AB
0x14006b09a  mov     rax, cs:gWfpGlobal
0x14006b0a1  mov     [rax+94h], r14d
0x14006b0a8  call    InitIndexes
0x14006b0ad  mov     rbx, rax
0x14006b0b0  test    rax, rax
0x14006b0b3  jnz     loc_14006B1AB
0x14006b0b9  test    edi, edi
0x14006b0bb  jnz     short loc_14006B0EA
0x14006b0bd  mov     rcx, cs:gWfpGlobal
0x14006b0c4  add     rcx, 1B0h
0x14006b0cb  call    WfpCreateFastRWLock
0x14006b0d0  mov     rbx, rax
0x14006b0d3  test    rax, rax
0x14006b0d6  jnz     loc_14006B1AB
0x14006b0dc  mov     rax, cs:gWfpGlobal
0x14006b0e3  mov     [rax+0B0h], r14d
0x14006b0ea  mov     rcx, cs:gWfpGlobal
0x14006b0f1  xor     edx, edx; Val
0x14006b0f3  add     rcx, 1C0h; void *
0x14006b0fa  mov     r8d, 1C0h; Size
0x14006b100  call    memset
0x14006b105  test    edi, edi
0x14006b107  jnz     short loc_14006B117
0x14006b109  mov     rax, cs:gWfpGlobal
0x14006b110  mov     [rax+380h], r14d
0x14006b117  call    InitializeFastCaching
0x14006b11c  mov     rbx, rax
0x14006b11f  test    rax, rax
0x14006b122  jnz     loc_14006B1AB
0x14006b128  lea     r9, accessTokenSize
0x14006b12f  xor     r8d, r8d
0x14006b132  xor     edx, edx
0x14006b134  xor     ecx, ecx
0x14006b136  call    cs:__imp_SeTokenFromAccessInformation
0x14006b13d  nop     dword ptr [rax+rax+00h]
0x14006b142  call    InitializeAccessPreCheckCache
0x14006b147  mov     rbx, rax
0x14006b14a  test    rax, rax
0x14006b14d  jnz     short loc_14006B1AB
0x14006b14f  test    edi, edi
0x14006b151  jnz     loc_14006B1FD
0x14006b157  mov     rbx, cs:gWfpGlobal
0x14006b15e  cmp     [rbx+588h], esi
0x14006b164  jz      loc_14006B20A
0x14006b16a  mov     edx, 42706657h
0x14006b16f  mov     cl, r14b
0x14006b172  call    NetioAllocateAndInitializeStackBlock
0x14006b177  mov     [rbx+580h], rax
0x14006b17e  mov     rcx, cs:gWfpGlobal
0x14006b185  cmp     [rcx+580h], rsi
0x14006b18c  jnz     short loc_14006B1E9
0x14006b18e  mov     r8d, 0C0000017h
0x14006b194  lea     rdx, aNetioallocatea_0; "NetioAllocateAndInitializeStackBlock"
0x14006b19b  mov     r9d, r14d
0x14006b19e  call    WfpReportSysErrorAsNtStatus
0x14006b1a3  mov     rbx, rax
0x14006b1a6  test    rax, rax
0x14006b1a9  jz      short loc_14006B1C6
0x14006b1ab  xor     ecx, ecx
0x14006b1ad  call    FeShutdown
0x14006b1b2  test    rbx, rbx
0x14006b1b5  jz      short loc_14006B1C6
0x14006b1b7  lea     rdx, aFeinit; "FeInit"
0x14006b1be  mov     rcx, rbx
0x14006b1c1  call    WfpReportError
0x14006b1c6  mov     rax, rbx
0x14006b1c9  mov     rcx, [rbp+0C0h+var_40]
0x14006b1d0  xor     rcx, rsp; StackCookie
0x14006b1d3  call    __security_check_cookie
0x14006b1d8  add     rsp, 198h
0x14006b1df  pop     r15
0x14006b1e1  pop     r14
0x14006b1e3  pop     rdi
0x14006b1e4  pop     rsi
0x14006b1e5  pop     rbx
0x14006b1e6  pop     rbp
0x14006b1e7  retn
0x14006b1e9  add     rcx, 58Ch; void *
0x14006b1f0  mov     r8, r15; Size
0x14006b1f3  or      edx, 0FFFFFFFFh; Val
0x14006b1f6  call    memset
0x14006b1fb  jmp     short loc_14006B20A
0x14006b1fd  mov     rax, cs:gWfpGlobal
0x14006b204  mov     [rax+0C0h], esi
0x14006b20a  mov     rcx, cs:gWfpGlobal
0x14006b211  add     rcx, 380h
0x14006b218  call    IncrementEpoch
0x14006b21d  test    edi, edi
0x14006b21f  jnz     loc_14006B32B
0x14006b225  mov     rcx, cs:gWfpGlobal
0x14006b22c  add     rcx, 4B0h; SpinLock
0x14006b233  call    cs:__imp_KeInitializeSpinLock
0x14006b23a  nop     dword ptr [rax+rax+00h]
0x14006b23f  mov     rax, cs:gWfpGlobal
0x14006b246  mov     [rax+4B8h], rsi
0x14006b24d  mov     rax, cs:gWfpGlobal
0x14006b254  mov     [rax+4C0h], esi
0x14006b25a  mov     rax, cs:gWfpGlobal
0x14006b261  mov     [rax+4C4h], esi
0x14006b267  mov     rcx, cs:gWfpGlobal
0x14006b26e  add     rcx, 4C8h; SpinLock
0x14006b275  call    cs:__imp_KeInitializeSpinLock
0x14006b27c  nop     dword ptr [rax+rax+00h]
0x14006b281  mov     rax, cs:gWfpGlobal
0x14006b288  mov     [rax+4D0h], rsi
0x14006b28f  mov     rax, cs:gWfpGlobal
0x14006b296  mov     [rax+4D8h], esi
0x14006b29c  mov     rax, cs:gWfpGlobal
0x14006b2a3  mov     [rax+4DCh], esi
0x14006b2a9  mov     rcx, cs:gWfpGlobal
0x14006b2b0  add     rcx, 4E0h; SpinLock
0x14006b2b7  call    cs:__imp_KeInitializeSpinLock
  ... truncated ...
```
