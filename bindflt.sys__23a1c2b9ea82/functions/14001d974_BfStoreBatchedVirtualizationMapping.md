# BfStoreBatchedVirtualizationMapping

- ea: `0x14001d974`
- end: `0x14001e5c0`
- name: `BfStoreBatchedVirtualizationMapping`
- size: `3148`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140025c70`

## callees

- `0x140001348`
- `0x140003140`
- `0x140003304`
- `0x140004cc0`
- `0x14000f008`
- `0x140010898`
- `0x1400172f0`
- `0x140019c44`
- `0x14001d130`
- `0x14001d974`
- `0x14001e5c8`
- `0x14001e6fc`
- `0x140021b60`
- `0x140021d1c`
- `0x1400232f0`
- `0x140023cd8`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001da10`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001da10`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001e263`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001e263`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001da2c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e08b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001da2c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e08b`
- `ntoskrnl!PsGetCurrentSilo` at `0x14001d9cf`
- `ntoskrnl!PsGetCurrentSilo` at `0x14001d9cf`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001dd6a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001dd6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001de00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001de15`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001df6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e29d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e5a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001de00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001de15`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001df6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e29d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e5a1`
- `ntoskrnl!ExAllocatePool2` at `0x14001db45`
- `ntoskrnl!ExAllocatePool2` at `0x14001dc47`
- `ntoskrnl!ExAllocatePool2` at `0x14001db45`
- `ntoskrnl!ExAllocatePool2` at `0x14001dc47`
- `ntoskrnl!PsIsHostSilo` at `0x14001d9de`
- `ntoskrnl!PsIsHostSilo` at `0x14001d9de`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14001e27e`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14001e27e`
- `FLTMGR!FltReleaseContext` at `0x14001e1ab`
- `FLTMGR!FltReleaseContext` at `0x14001e563`
- `FLTMGR!FltReleaseContext` at `0x14001e588`
- `FLTMGR!FltReleaseContext` at `0x14001e1ab`
- `FLTMGR!FltReleaseContext` at `0x14001e563`
- `FLTMGR!FltReleaseContext` at `0x14001e588`
- `FLTMGR!FltReleaseResource` at `0x14001e54f`
- `FLTMGR!FltReleaseResource` at `0x14001e54f`
- `FLTMGR!FltObjectDereference` at `0x14001e18f`
- `FLTMGR!FltObjectDereference` at `0x14001e577`
- `FLTMGR!FltObjectDereference` at `0x14001e18f`
- `FLTMGR!FltObjectDereference` at `0x14001e577`
- `FLTMGR!FltGetInstanceContext` at `0x14001e22c`
- `FLTMGR!FltGetInstanceContext` at `0x14001e22c`

## pseudocode

```c
__int64 __fastcall BfStoreBatchedVirtualizationMapping(__int64 a1, unsigned int a2)
{
  unsigned __int16 *v2; // r13
  __int64 CurrentSilo; // rax
  int v6; // ebx
  unsigned int *v7; // r11
  unsigned int v8; // eax
  __int64 v9; // r14
  __int64 v10; // rdx
  int v11; // r8d
  __int64 v12; // r9
  int v13; // r10d
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  int v19; // edx
  _WORD *Pool2; // rbx
  unsigned __int16 v21; // ax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  unsigned __int16 v25; // r10
  unsigned __int16 v26; // cx
  __int64 v27; // rdx
  __int64 v28; // r9
  _WORD *v29; // rbx
  __int64 v30; // rdx
  char *v31; // rcx
  int v32; // eax
  int v33; // edx
  PVOID v34; // rbx
  int v35; // r9d
  unsigned int v36; // eax
  unsigned int v37; // edx
  int inserted; // eax
  int v39; // r9d
  int InstanceTierNode; // eax
  int v42; // eax
  int v43; // edx
  int v44; // eax
  int v45; // r9d
  int InstanceFromFileObject; // eax
  NTSTATUS InstanceContext; // eax
  int v48; // eax
  int v49; // r8d
  int v50; // eax
  int v51; // edx
  char v52; // [rsp+30h] [rbp-D0h]
  char v53; // [rsp+30h] [rbp-D0h]
  __int64 v54; // [rsp+38h] [rbp-C8h]
  unsigned int v55; // [rsp+50h] [rbp-B0h]
  UNICODE_STRING String1; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v57; // [rsp+68h] [rbp-98h]
  PVOID FltObject; // [rsp+70h] [rbp-90h]
  _WORD v59[2]; // [rsp+78h] [rbp-88h] BYREF
  int v60; // [rsp+7Ch] [rbp-84h]
  void *Src; // [rsp+80h] [rbp-80h]
  PVOID P[2]; // [rsp+88h] [rbp-78h] BYREF
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  unsigned __int16 *v65; // [rsp+A0h] [rbp-60h] BYREF
  PFLT_CONTEXT Context; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING String2; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v68; // [rsp+C0h] [rbp-40h]
  unsigned int v69; // [rsp+C4h] [rbp-3Ch]
  int v70; // [rsp+C8h] [rbp-38h]
  unsigned int v71; // [rsp+CCh] [rbp-34h]
  int v72[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-28h] BYREF
  PFLT_CONTEXT v74; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int *v75; // [rsp+E8h] [rbp-18h]
  _WORD v76[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v77; // [rsp+F4h] [rbp-Ch]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  __int64 i; // [rsp+100h] [rbp+0h]
  char v82; // [rsp+170h] [rbp+70h]
  unsigned __int16 v83; // [rsp+170h] [rbp+70h]
  char v84; // [rsp+178h] [rbp+78h]

  v65 = 0;
  v2 = 0;
  v82 = 0;
  *(_OWORD *)P = 0;
  FltObject = 0;
  String2 = 0;
  Context = 0;
  v84 = 0;
  v73 = 0;
  v74 = 0;
  *(_QWORD *)v72 = 0;
  CurrentSilo = PsGetCurrentSilo();
  if ( (unsigned __int8)PsIsHostSilo(CurrentSilo) )
  {
    v6 = BfpValidateBatchedMappingConfig(a1, a2);
    if ( v6 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sD(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          6,
          145,
          (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
          226);
    }
    else
    {
      ExAcquireFastMutex(&FastMutex);
      if ( !byte_14000B1C0 )
      {
        ExReleaseFastMutex(&FastMutex);
        v7 = (unsigned int *)(a1 + *(unsigned int *)(a1 + 24) + 32LL);
        v8 = 0;
        v9 = a1 + *(unsigned int *)(a1 + 28) + 32LL;
        v75 = v7;
        for ( i = v9; ; v9 = i )
        {
          v55 = v8;
          v82 = 0;
          if ( v8 >= *v7 )
            goto LABEL_48;
          v10 = 8LL * v8;
          v77 = 0;
          v60 = 0;
          *(_DWORD *)(&String1.MaximumLength + 1) = 0;
          v11 = HIWORD(v7[v10 + 1]);
          v12 = LOWORD(v7[v10 + 7]);
          v13 = LOWORD(v7[v10 + 5]);
          v14 = v7[v10 + 8];
          v68 = v7[v10 + 2];
          v83 = HIWORD(v7[v10 + 3]);
          v71 = v7[v10 + 4];
          v69 = v7[v10 + 6];
          v78 = a1 + v14 + 32;
          v15 = LOWORD(v7[v10 + 1]);
          v63 = v11;
          v64 = v13;
          v57 = v12;
          v16 = *(_QWORD *)(v9 + 8 * v15 + 4);
          v59[0] = v16;
          v59[1] = v16;
          v76[0] = v12;
          Src = (void *)(a1 + HIDWORD(v16) + 32);
          v17 = LOWORD(v7[v10 + 3]);
          v76[1] = v12;
          v18 = *(_QWORD *)(v9 + 8 * v17 + 4);
          String1.Length = v18;
          String1.MaximumLength = v18;
          String1.Buffer = (PWSTR)(HIDWORD(v18) + a1 + 32);
          Pool2 = (_WORD *)ExAllocatePool2(256, v11 + v13 + 8 + (unsigned int)(unsigned __int16)v16, 1886209602, v12);
          if ( !Pool2 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v19) = 2;
              WPP_RECORDER_SF_sD(
                WPP_GLOBAL_Control->DeviceExtension,
                v19,
                8,
                52,
                (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                54);
            }
            v6 = -1073741670;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v54) = -1073741670;
              v39 = 53;
              v52 = -70;
              goto LABEL_41;
            }
LABEL_44:
            v82 = 0;
            goto LABEL_47;
          }
          *(_DWORD *)Pool2 = 6;
          Pool2[2] = 0;
          *Pool2 = v59[0] + 6;
          Pool2[2] = v59[0];
          Pool2[1] = v59[0];
          memmove(Pool2 + 3, Src, v59[0]);
          v21 = v63;
          v22 = (unsigned int)v59[0] + 6;
          v23 = v68;
          *Pool2 += v63;
          Pool2[2] += v21;
          v70 = v22;
          memmove((char *)Pool2 + v22, (const void *)(a1 + v23 + 32), v21);
          v25 = v64;
          if ( (_WORD)v64 )
          {
            v26 = Pool2[2];
            v27 = (unsigned int)(v70 + v63);
            v28 = v69;
            if ( Pool2[((unsigned __int64)v26 >> 1) + 2] != 92 )
            {
              *Pool2 += 2;
              Pool2[2] = v26 + 2;
              *(_WORD *)((char *)Pool2 + v27) = 92;
              LODWORD(v27) = v27 + 2;
            }
            Pool2[2] += v25;
            *Pool2 += v25;
            memmove((char *)Pool2 + (unsigned int)v27, (const void *)(a1 + v28 + 32), v25);
          }
          P[0] = Pool2;
          v29 = (_WORD *)ExAllocatePool2(256, v83 + 6 + (unsigned int)String1.Length, 1886209602, v24);
          if ( !v29 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              || (LOBYTE(v19) = 2,
                  WPP_RECORDER_SF_sD(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v19,
                    8,
                    52,
                    (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                    (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                    54),
                  WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
            {
              v6 = -1073741670;
            }
            else
            {
              v6 = -1073741670;
              v39 = 54;
              LODWORD(v54) = -1073741670;
              v52 = -62;
LABEL_41:
              LOBYTE(v19) = 2;
              WPP_RECORDER_SF_sDd(
                WPP_GLOBAL_Control->DeviceExtension,
                v19,
                8,
                v39,
                (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                v52,
                v54);
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v54) = -1073741670;
              LOBYTE(v19) = 2;
              WPP_RECORDER_SF_sDd(
                WPP_GLOBAL_Control->DeviceExtension,
                v19,
                6,
                147,
                (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                73,
                v54);
            }
            goto LABEL_44;
          }
          *(_DWORD *)v29 = 6;
          v29[2] = 0;
          *v29 = String1.Length + 6;
          v29[2] = String1.Length;
          v29[1] = String1.Length;
          memmove(v29 + 3, String1.Buffer, String1.Length);
          v30 = v71;
          v31 = (char *)v29 + String1.Length + 6;
          *v29 += v83;
          v29[2] += v83;
          memmove(v31, (const void *)(a1 + v30 + 32), v83);
          P[1] = v29;
          v82 = 1;
          if ( *(_WORD *)Src == 92 && *((_WORD *)Src + 1) == 92 && *((_WORD *)Src + 2) == 63 )
          {
            *((_WORD *)P[0] + 1) = 96;
            v29 = P[1];
          }
          if ( *String1.Buffer == 92 && String1.Buffer[1] == 92 && String1.Buffer[2] == 63 )
            v29[1] = 96;
          v32 = BfValidateContainerRootId((unsigned __int16 *)P[0], *(unsigned __int16 *)P[0]);
          v6 = v32;
          if ( v32 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v54) = v32;
              v45 = 148;
              v53 = 95;
LABEL_111:
              v49 = 6;
LABEL_112:
              LOBYTE(v33) = 2;
              WPP_RECORDER_SF_sDd(
                WPP_GLOBAL_Control->DeviceExtension,
                v33,
                v49,
                v45,
                (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                v53,
                v54);
            }
LABEL_47:
            if ( !v55 )
              goto LABEL_48;
            *v75 = v55;
            v50 = BfRemoveBatchedVirtualizationMapping(a1, a2);
            if ( v50 < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_48;
              LODWORD(v54) = v50;
              LOBYTE(v51) = 2;
              WPP_RECORDER_SF_sDd(
                WPP_GLOBAL_Control->DeviceExtension,
                v51,
                6,
                157,
                (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                50,
                v54);
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v51) = 2;
              WPP_RECORDER_SF_sDdd(
                WPP_GLOBAL_Control->DeviceExtension,
                v51,
                6,
                158,
                (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                53,
                v55,
                v6);
            }
            goto LABEL_48;
          }
          v6 = BfValidateContainerRootId((unsigned __int16 *)P[1], *(unsigned __int16 *)P[1]);
          if ( v6 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v54) = v6;
              v45 = 149;
              v53 = 103;
              goto LABEL_111;
            }
            goto LABEL_47;
          }
          if ( v57 )
          {
            v42 = BfpInitializeContainerRootId((unsigned int)v76, (unsigned int)v59, 0, 0, (__int64)&v65);
            v6 = v42;
            if ( v42 < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LODWORD(v54) = v42;
                LOBYTE(v43) = 2;
                WPP_RECORDER_SF_sDd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v43,
                  6,
                  150,
                  (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                  (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                  117,
                  v54);
              }
              v2 = v65;
              goto LABEL_47;
            }
            v2 = v65;
            if ( *(_WORD *)Src == 92 && *((_WORD *)Src + 1) == 92 && *((_WORD *)Src + 2) == 63 )
              v65[1] = 96;
            v44 = BfValidateContainerRootId(v2, *v2);
            v6 = v44;
            if ( v44 < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LODWORD(v54) = v44;
                v45 = 151;
                v53 = -127;
                goto LABEL_111;
              }
              goto LABEL_47;
            }
          }
          v34 = FltObject;
          if ( FltObject )
          {
            if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
            {
              if ( *String1.Buffer == 92 && String1.Buffer[1] == 92 && String1.Buffer[2] != 63 )
                *((_WORD *)P[1] + 1) = 2;
              goto LABEL_29;
            }
            FltObjectDereference(v34);
            FltObject = 0;
          }
          if ( Context )
          {
            FltReleaseContext(Context);
            Context = 0;
          }
          BfFreeUnicodeString(&String2);
          if ( *String1.Buffer != 92 || String1.Buffer[1] != 92 )
            break;
          if ( String1.Buffer[2] == 63 )
          {
            InstanceFromFileObject = BfGetInstanceFromFileObject(&String1);
LABEL_88:
            v6 = InstanceFromFileObject;
            goto LABEL_89;
          }
          v6 = BfGetInstanceFromFileObject(&String1);
          *((_WORD *)P[1] + 1) = 2;
LABEL_89:
          if ( v6 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_47;
            LODWORD(v54) = v6;
            v45 = 152;
            v53 = -64;
            goto LABEL_102;
          }
          InstanceContext = FltGetInstanceContext((PFLT_INSTANCE)FltObject, &Context);
          v6 = InstanceContext;
          if ( InstanceContext < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_47;
            LODWORD(v54) = InstanceContext;
            v45 = 153;
            v53 = -56;
            goto LABEL_102;
          }
          v48 = BfAllocateUnicodeString(String1.MaximumLength, &String2);
          v6 = v48;
          if ( v48 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_47;
            LODWORD(v54) = v48;
            v45 = 154;
            v53 = -43;
LABEL_102:
            v49 = 8;
            goto LABEL_112;
          }
          RtlCopyUnicodeString(&String2, &String1);
LABEL_29:
          if ( !*(_QWORD *)v72 )
          {
            LOBYTE(v35) = 1;
            InstanceTierNode = BfpGetInstanceTierNode(
                                 (unsigned int)v59,
                                 *(_QWORD *)(a1 + 8),
                                 *(_QWORD *)(a1 + 16),
                                 v35,
                                 (__int64)&v74,
                                 (__int64)&v73,
                                 (__int64)v72);
            v6 = InstanceTierNode;
            if ( InstanceTierNode < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LODWORD(v54) = InstanceTierNode;
                v45 = 155;
                v53 = -8;
                goto LABEL_111;
              }
              goto LABEL_47;
            }
            FltAcquireResourceExclusive((PERESOURCE)(v73 + 16));
            v84 = 1;
          }
          v36 = *(_DWORD *)(a1 + 4);
          v37 = v36 | 0x20000000;
          if ( !(_WORD)v64 )
            v37 = v36;
          inserted = BfpMappingInsertIntoTable(
                       (__int64 *)P,
                       v37,
                       (PFLT_INSTANCE *)v74,
                       *(__int64 *)v72,
                       Context,
                       0,
                       0,
                       (__int64)v2);
          v6 = inserted;
          if ( inserted < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v54) = inserted;
              v45 = 156;
              v53 = 21;
              goto LABEL_111;
            }
            goto LABEL_47;
          }
          if ( v2 )
          {
            ExFreePoolWithTag(v2, 0x706D4642u);
            v2 = 0;
            v65 = 0;
          }
          ExFreePoolWithTag(P[0], 0x706D4642u);
          ExFreePoolWithTag(P[1], 0x706D4642u);
          v7 = v75;
          v8 = v55 + 1;
        }
        InstanceFromFileObject = BfGetInstanceFromVolumeName(&String1);
        goto LABEL_88;
      }
      ExReleaseFastMutex(&FastMutex);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sD(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          6,
          146,
          (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
          240);
      v6 = -1073741637;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        6,
        144,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        218);
    v6 = -1073741790;
  }
LABEL_48:
  if ( String2.Buffer )
  {
    ExFreePoolWithTag(String2.Buffer, 0x74734642u);
    String2.Buffer = 0;
  }
  *(_DWORD *)&String2.Length = 0;
  if ( v84 )
    FltReleaseResource((PERESOURCE)(v73 + 16));
  if ( v74 )
    FltReleaseContext(v74);
  if ( FltObject )
    FltObjectDereference(FltObject);
  if ( Context )
    FltReleaseContext(Context);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x706D4642u);
  if ( v82 )
    BfpCleanupMappingEntry(P);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001d974  mov     [rsp-8+arg_8], edx
0x14001d978  mov     [rsp-8+arg_0], rcx
0x14001d97d  push    rbp
0x14001d97e  push    rbx
0x14001d97f  push    rsi
0x14001d980  push    rdi
0x14001d981  push    r12
0x14001d983  push    r13
0x14001d985  push    r14
0x14001d987  push    r15
0x14001d989  lea     rbp, [rsp-18h]
0x14001d98e  sub     rsp, 118h
0x14001d995  xor     r15d, r15d
0x14001d998  xorps   xmm0, xmm0
0x14001d99b  xorps   xmm1, xmm1
0x14001d99e  mov     [rbp+50h+var_B0], r15
0x14001d9a2  mov     r13d, r15d
0x14001d9a5  mov     byte ptr [rbp+50h+arg_10], r15b
0x14001d9a9  movups  xmmword ptr [rbp+50h+P], xmm0
0x14001d9ad  mov     [rsp+150h+FltObject], r15
0x14001d9b2  mov     ebx, edx
0x14001d9b4  movups  xmmword ptr [rbp+50h+String2.Length], xmm1
0x14001d9b8  mov     [rbp+50h+Context], r15
0x14001d9bc  mov     rdi, rcx
0x14001d9bf  mov     [rbp+50h+arg_18], r15b
0x14001d9c3  mov     [rbp+50h+var_78], r15
0x14001d9c7  mov     [rbp+50h+var_70], r15
0x14001d9cb  mov     qword ptr [rbp+50h+var_80], r15
0x14001d9cf  call    cs:__imp_PsGetCurrentSilo
0x14001d9d6  nop     dword ptr [rax+rax+00h]
0x14001d9db  mov     rcx, rax
0x14001d9de  call    cs:__imp_PsIsHostSilo
0x14001d9e5  nop     dword ptr [rax+rax+00h]
0x14001d9ea  test    al, al
0x14001d9ec  jz      loc_14001DFDA
0x14001d9f2  mov     edx, ebx
0x14001d9f4  mov     rcx, rdi
0x14001d9f7  call    BfpValidateBatchedMappingConfig
0x14001d9fc  mov     ebx, eax
0x14001d9fe  test    eax, eax
0x14001da00  js      loc_14001E033
0x14001da06  lea     rsi, FastMutex
0x14001da0d  mov     rcx, rsi; FastMutex
0x14001da10  call    cs:__imp_ExAcquireFastMutex
0x14001da17  nop     dword ptr [rax+rax+00h]
0x14001da1c  cmp     cs:byte_14000B1C0, r15b
0x14001da23  mov     rcx, rsi; FastMutex
0x14001da26  jnz     loc_14001E08B
0x14001da2c  call    cs:__imp_ExReleaseFastMutex
0x14001da33  nop     dword ptr [rax+rax+00h]
0x14001da38  mov     r11d, [rdi+18h]
0x14001da3c  lea     esi, [r15+2]
0x14001da40  mov     r14d, [rdi+1Ch]
0x14001da44  lea     r12d, [r15+6]
0x14001da48  add     r11, 20h ; ' '
0x14001da4c  add     r14, 20h ; ' '
0x14001da50  add     r11, rdi
0x14001da53  mov     eax, r15d
0x14001da56  add     r14, rdi
0x14001da59  mov     [rbp+50h+var_68], r11
0x14001da5d  mov     [rbp+50h+var_50], r14
0x14001da61  mov     [rsp+150h+var_100], eax
0x14001da65  mov     byte ptr [rbp+50h+arg_10], r15b
0x14001da69  cmp     eax, [r11]
0x14001da6c  jnb     loc_14001DF5B
0x14001da72  mov     edx, eax
0x14001da74  shl     rdx, 5
0x14001da78  mov     [rbp+50h+var_5C], r15d
0x14001da7c  mov     [rsp+150h+var_D4], r15d
0x14001da81  mov     dword ptr [rsp+150h+String1+4], r15d
0x14001da86  mov     eax, [rdx+r11+8]
0x14001da8b  movzx   r8d, word ptr [rdx+r11+6]
0x14001da91  movzx   r9d, word ptr [rdx+r11+1Ch]
0x14001da97  movzx   r10d, word ptr [rdx+r11+14h]
0x14001da9d  mov     ecx, [rdx+r11+20h]
0x14001daa2  mov     [rbp+50h+var_90], eax
0x14001daa5  add     rcx, 20h ; ' '
0x14001daa9  movzx   eax, word ptr [rdx+r11+0Eh]
0x14001daaf  add     rcx, rdi
0x14001dab2  mov     [rbp+50h+arg_10], ax
0x14001dab6  mov     eax, [rdx+r11+10h]
0x14001dabb  mov     [rbp+50h+var_84], eax
0x14001dabe  mov     eax, [rdx+r11+18h]
0x14001dac3  mov     [rbp+50h+var_8C], eax
0x14001dac6  mov     [rbp+50h+var_58], rcx
0x14001daca  movzx   ecx, word ptr [rdx+r11+4]
0x14001dad0  mov     [rbp+50h+var_B8], r8d
0x14001dad4  mov     [rbp+50h+var_B4], r10d
0x14001dad8  mov     [rsp+150h+var_E8], r9w
0x14001dade  mov     rcx, [r14+rcx*8+4]
0x14001dae3  mov     rax, rcx
0x14001dae6  mov     [rsp+150h+var_D8], cx
0x14001daeb  shr     rax, 20h
0x14001daef  add     rax, 20h ; ' '
0x14001daf3  mov     [rsp+150h+var_D6], cx
0x14001daf8  add     rax, rdi
0x14001dafb  mov     [rbp+50h+var_60], r9w
0x14001db00  mov     [rbp+50h+Src], rax
0x14001db04  movzx   eax, word ptr [rdx+r11+0Ch]
0x14001db0a  lea     rdx, [rdi+20h]
0x14001db0e  mov     [rbp+50h+var_5E], r9w
0x14001db13  mov     rax, [r14+rax*8+4]
0x14001db18  mov     [rsp+150h+String1.Length], ax
0x14001db1d  mov     [rsp+150h+String1.MaximumLength], ax
0x14001db22  shr     rax, 20h
0x14001db26  add     rdx, rax
0x14001db29  lea     eax, [r10+8]
0x14001db2d  mov     [rsp+150h+String1.Buffer], rdx
0x14001db32  add     eax, r8d
0x14001db35  movzx   edx, cx
0x14001db38  mov     r8d, 706D4642h
0x14001db3e  add     edx, eax
0x14001db40  mov     ecx, 100h
0x14001db45  call    cs:__imp_ExAllocatePool2
0x14001db4c  nop     dword ptr [rax+rax+00h]
0x14001db51  mov     rbx, rax
0x14001db54  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001db5b  xor     eax, eax
0x14001db5d  lea     r15, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001db64  test    rbx, rbx
0x14001db67  jz      loc_14001DE3E
0x14001db6d  mov     [rbx], r12d
0x14001db70  mov     [rbx+4], ax
0x14001db74  movzx   ecx, [rsp+150h+var_D8]
0x14001db79  add     cx, r12w
0x14001db7d  mov     [rbx], cx
0x14001db80  lea     rcx, [rbx+6]; void *
0x14001db84  movzx   eax, [rsp+150h+var_D8]
0x14001db89  mov     [rbx+4], ax
0x14001db8d  movzx   eax, [rsp+150h+var_D8]
0x14001db92  mov     [rbx+2], ax
0x14001db96  movzx   r8d, [rsp+150h+var_D8]; Size
0x14001db9c  mov     rdx, [rbp+50h+Src]; Src
0x14001dba0  call    memmove
0x14001dba5  movzx   ecx, [rsp+150h+var_D8]
0x14001dbaa  mov     eax, [rbp+50h+var_B8]
0x14001dbad  add     ecx, r12d
0x14001dbb0  mov     edx, [rbp+50h+var_90]
0x14001dbb3  add     [rbx], ax
0x14001dbb6  add     rdx, 20h ; ' '
0x14001dbba  add     [rbx+4], ax
0x14001dbbe  add     rdx, rdi; Src
0x14001dbc1  mov     [rbp+50h+var_88], ecx
0x14001dbc4  add     rcx, rbx; void *
0x14001dbc7  movzx   r8d, ax; Size
0x14001dbcb  call    memmove
0x14001dbd0  mov     r10d, [rbp+50h+var_B4]
0x14001dbd4  test    r10w, r10w
0x14001dbd8  jz      short loc_14001DC2A
0x14001dbda  movzx   ecx, word ptr [rbx+4]
0x14001dbde  mov     r8d, 5Ch ; '\'
0x14001dbe4  mov     edx, [rbp+50h+var_B8]
0x14001dbe7  mov     eax, ecx
0x14001dbe9  add     edx, [rbp+50h+var_88]
0x14001dbec  mov     r9d, [rbp+50h+var_8C]
0x14001dbf0  shr     rax, 1
0x14001dbf3  cmp     [rbx+rax*2+4], r8w
0x14001dbf9  jz      short loc_14001DC0C
0x14001dbfb  add     [rbx], si
0x14001dbfe  add     cx, si
0x14001dc01  mov     [rbx+4], cx
0x14001dc05  mov     [rdx+rbx], r8w
0x14001dc0a  add     edx, esi
0x14001dc0c  add     [rbx+4], r10w
0x14001dc11  add     [rbx], r10w
0x14001dc15  mov     ecx, edx
0x14001dc17  lea     rdx, [r9+20h]
0x14001dc1b  add     rdx, rdi; Src
0x14001dc1e  movzx   r8d, r10w; Size
0x14001dc22  add     rcx, rbx; void *
0x14001dc25  call    memmove
0x14001dc2a  mov     [rbp+50h+P], rbx
0x14001dc2e  movzx   ecx, [rbp+50h+arg_10]
0x14001dc32  mov     r8d, 706D4642h
0x14001dc38  movzx   edx, [rsp+150h+String1.Length]
0x14001dc3d  add     ecx, r12d
0x14001dc40  add     edx, ecx
0x14001dc42  mov     ecx, 100h
0x14001dc47  call    cs:__imp_ExAllocatePool2
0x14001dc4e  nop     dword ptr [rax+rax+00h]
0x14001dc53  mov     rbx, rax
0x14001dc56  xor     eax, eax
0x14001dc58  test    rbx, rbx
0x14001dc5b  jz      loc_14001E438
0x14001dc61  mov     [rbx], r12d
0x14001dc64  mov     [rbx+4], ax
0x14001dc68  movzx   ecx, [rsp+150h+String1.Length]
0x14001dc6d  add     cx, r12w
0x14001dc71  mov     [rbx], cx
0x14001dc74  lea     rcx, [rbx+6]; void *
0x14001dc78  movzx   eax, [rsp+150h+String1.Length]
0x14001dc7d  mov     [rbx+4], ax
0x14001dc81  movzx   eax, [rsp+150h+String1.Length]
0x14001dc86  mov     [rbx+2], ax
0x14001dc8a  movzx   r8d, [rsp+150h+String1.Length]; Size
0x14001dc90  mov     rdx, [rsp+150h+String1.Buffer]; Src
0x14001dc95  call    memmove
0x14001dc9a  movzx   ecx, [rsp+150h+String1.Length]
0x14001dc9f  movzx   eax, [rbp+50h+arg_10]
0x14001dca3  add     rcx, r12
0x14001dca6  mov     edx, [rbp+50h+var_84]
0x14001dca9  add     rcx, rbx; void *
0x14001dcac  add     [rbx], ax
0x14001dcaf  add     rdx, 20h ; ' '
0x14001dcb3  add     [rbx+4], ax
0x14001dcb7  add     rdx, rdi; Src
0x14001dcba  mov     r8d, eax; Size
0x14001dcbd  call    memmove
0x14001dcc2  mov     [rbp+50h+P+8], rbx
0x14001dcc6  mov     rax, [rbp+50h+Src]
0x14001dcca  mov     ecx, 5Ch ; '\'
0x14001dccf  mov     byte ptr [rbp+50h+arg_10], 1
0x14001dcd3  cmp     [rax], cx
0x14001dcd6  jnz     loc_14001DE34
0x14001dcdc  cmp     [rax+2], cx
0x14001dce0  jnz     loc_14001DE34
0x14001dce6  cmp     word ptr [rax+4], 3Fh ; '?'
0x14001dceb  lea     edx, [rcx+4]
0x14001dcee  jnz     short loc_14001DCFC
0x14001dcf0  mov     rax, [rbp+50h+P]
0x14001dcf4  mov     [rax+2], dx
0x14001dcf8  mov     rbx, [rbp+50h+P+8]
0x14001dcfc  mov     rax, [rsp+150h+String1.Buffer]
0x14001dd01  cmp     [rax], cx
0x14001dd04  jnz     short loc_14001DD17
0x14001dd06  cmp     [rax+2], cx
0x14001dd0a  jnz     short loc_14001DD17
0x14001dd0c  cmp     word ptr [rax+4], 3Fh ; '?'
0x14001dd11  jnz     short loc_14001DD17
0x14001dd13  mov     [rbx+2], dx
0x14001dd17  mov     rcx, [rbp+50h+P]
0x14001dd1b  movzx   edx, word ptr [rcx]
0x14001dd1e  call    BfValidateContainerRootId
0x14001dd23  mov     ebx, eax
0x14001dd25  test    eax, eax
0x14001dd27  js      loc_14001E3ED
0x14001dd2d  mov     rcx, [rbp+50h+P+8]
0x14001dd31  movzx   edx, word ptr [rcx]
0x14001dd34  call    BfValidateContainerRootId
0x14001dd39  mov     ebx, eax
0x14001dd3b  xor     eax, eax
0x14001dd3d  test    ebx, ebx
0x14001dd3f  js      loc_14001E3C5
0x14001dd45  cmp     [rsp+150h+var_E8], ax
0x14001dd4a  ja      loc_14001E0F0
0x14001dd50  mov     rbx, [rsp+150h+FltObject]
0x14001dd55  test    rbx, rbx
0x14001dd58  jz      loc_14001E1A2
0x14001dd5e  mov     r8b, 1; CaseInSensitive
0x14001dd61  lea     rdx, [rbp+50h+String2]; String2
0x14001dd65  lea     rcx, [rsp+150h+String1]; String1
0x14001dd6a  call    cs:__imp_RtlCompareUnicodeString
0x14001dd71  nop     dword ptr [rax+rax+00h]
0x14001dd76  xor     ecx, ecx
0x14001dd78  test    eax, eax
0x14001dd7a  jnz     loc_14001E18C
0x14001dd80  mov     rax, [rsp+150h+String1.Buffer]
0x14001dd85  lea     edx, [rcx+5Ch]
0x14001dd88  cmp     [rax], dx
0x14001dd8b  jnz     short loc_14001DD9E
0x14001dd8d  cmp     [rax+2], dx
0x14001dd91  jnz     short loc_14001DD9E
0x14001dd93  cmp     word ptr [rax+4], 3Fh ; '?'
0x14001dd98  jnz     loc_14001E17F
0x14001dd9e  cmp     qword ptr [rbp+50h+var_80], rcx
0x14001dda2  jz      loc_14001DF01
0x14001dda8  mov     eax, [rdi+4]
0x14001ddab  mov     edx, eax
0x14001ddad  mov     r9, qword ptr [rbp+50h+var_80]; int
0x14001ddb1  bts     edx, 1Dh
0x14001ddb5  cmp     word ptr [rbp+50h+var_B4], 0
0x14001ddba  mov     r8, [rbp+50h+var_70]; int
0x14001ddbe  mov     [rsp+150h+var_118], r13; __int64
0x14001ddc3  cmovz   edx, eax; int
0x14001ddc6  mov     rax, [rbp+50h+Context]
0x14001ddca  mov     [rsp+150h+var_120], rcx; __int64
0x14001ddcf  mov     [rsp+150h+var_128], ecx; int
0x14001ddd3  lea     rcx, [rbp+50h+P]; int
0x14001ddd7  mov     [rsp+150h+var_130], rax; Context
0x14001dddc  call    BfpMappingInsertIntoTable
0x14001dde1  mov     ebx, eax
0x14001dde3  test    eax, eax
0x14001dde5  js      loc_14001E317
0x14001ddeb  xor     r15d, r15d
0x14001ddee  test    r13, r13
0x14001ddf1  jnz     loc_14001E295
0x14001ddf7  mov     rcx, [rbp+50h+P]; P
0x14001ddfb  mov     edx, 706D4642h; Tag
0x14001de00  call    cs:__imp_ExFreePoolWithTag
0x14001de07  nop     dword ptr [rax+rax+00h]
0x14001de0c  mov     rcx, [rbp+50h+P+8]; P
0x14001de10  mov     edx, 706D4642h; Tag
0x14001de15  call    cs:__imp_ExFreePoolWithTag
0x14001de1c  nop     dword ptr [rax+rax+00h]
0x14001de21  mov     eax, [rsp+150h+var_100]
0x14001de25  mov     r11, [rbp+50h+var_68]
0x14001de29  inc     eax
0x14001de2b  mov     r14, [rbp+50h+var_50]
0x14001de2f  jmp     loc_14001DA61
0x14001de34  mov     edx, 60h ; '`'
  ... truncated ...
```
