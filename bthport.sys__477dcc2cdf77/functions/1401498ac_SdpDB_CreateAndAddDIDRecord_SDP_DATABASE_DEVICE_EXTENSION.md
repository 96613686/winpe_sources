# SdpDB_CreateAndAddDIDRecord(_SDP_DATABASE *,DEVICE_EXTENSION *)

- ea: `0x1401498ac`
- end: `0x14014a5c8`
- name: `?SdpDB_CreateAndAddDIDRecord@@YAJPEAU_SDP_DATABASE@@PEAUDEVICE_EXTENSION@@@Z`
- size: `3356`
- prototype: `__int64 __fastcall(struct _SDP_DATABASE *, struct DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14002a5b8`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005c04`
- `0x14014968c`
- `0x1401498ac`
- `0x14014cc40`
- `0x1402098d0`
- `0x140209940`
- `0x140209b00`
- `0x140209b20`
- `0x140209b80`
- `0x140209c10`
- `0x140209c30`
- `0x140209d40`
- `0x140209e20`
- `0x14020a0c0`
- `0x14020a1a4`
- `0x14020a220`

## import_xrefs

- `ntoskrnl!RtlInitAnsiString` at `0x14014995c`
- `ntoskrnl!RtlInitAnsiString` at `0x14014995c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14014a4c7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14014a4c7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14014a544`
- `ntoskrnl!ExReleaseFastMutex` at `0x14014a544`
- `ntoskrnl!ExAllocatePool2` at `0x14014a458`
- `ntoskrnl!ExAllocatePool2` at `0x14014a458`
- `ntoskrnl!ExFreePool` at `0x14014a47e`
- `ntoskrnl!ExFreePool` at `0x14014a47e`

## string_xrefs

- `0x140149951`: `Device ID Service Record`

## pseudocode

```c
__int64 __fastcall SdpDB_CreateAndAddDIDRecord(struct _SDP_DATABASE *a1, struct DEVICE_EXTENSION *a2, __int16 a3)
{
  bool v3; // zf
  struct DEVICE_EXTENSION *v4; // rsi
  NTSTATUS appended; // ebx
  struct _SDP_NODE *NodeSequence; // r15
  struct _SDP_NODE *NodeUUID16; // r14
  int v9; // edx
  PDEVICE_OBJECT v10; // r9
  bool v11; // cl
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  PDEVICE_OBJECT v15; // rcx
  bool v16; // r10
  struct _SDP_NODE *NodeUInt16; // rax
  struct _SDP_NODE *v18; // rax
  struct _SDP_NODE *v19; // r12
  int v20; // edx
  int v21; // r8d
  PDEVICE_OBJECT v22; // rcx
  bool v23; // r10
  struct _SDP_NODE *v24; // rax
  struct _SDP_NODE *v25; // r14
  int v26; // edx
  int v27; // r8d
  PDEVICE_OBJECT v28; // rcx
  bool v29; // r10
  struct _SDP_NODE *NodeString; // rax
  struct _SDP_NODE *v31; // rax
  struct _SDP_NODE *v32; // rax
  struct _SDP_NODE *v33; // r14
  struct _SDP_NODE *v34; // rax
  struct _SDP_NODE *v35; // rax
  struct _SDP_NODE *v36; // rax
  struct _SDP_NODE *v37; // rax
  struct _SDP_NODE *v38; // rax
  struct _SDP_NODE *v39; // rax
  struct _SDP_TREE_ROOT_NODE *v40; // rsi
  struct _SDP_NODE *NodeBoolean; // rax
  struct _SDP_NODE *v42; // rcx
  ULONG v43; // r12d
  struct _SDP_NODE *NodeUInt32; // rax
  struct _SDP_NODE *v45; // r14
  int v46; // edx
  int v47; // r8d
  bool v48; // r10
  int v49; // edx
  int v50; // r8d
  bool v51; // r10
  unsigned int v52; // r15d
  __int64 Pool2; // rax
  __int64 v54; // r14
  struct _SECURITY_DATABASE *v55; // rcx
  struct _GUID v56; // xmm0
  PVOID v57; // rax
  _LIST_ENTRY *Blink; // rax
  int v59; // edx
  int v60; // r8d
  __int16 v62; // [rsp+30h] [rbp-49h]
  __int16 v63; // [rsp+30h] [rbp-49h]
  __int16 v64; // [rsp+30h] [rbp-49h]
  __int16 v65; // [rsp+30h] [rbp-49h]
  char v66; // [rsp+40h] [rbp-39h]
  char v67; // [rsp+40h] [rbp-39h]
  char v68; // [rsp+40h] [rbp-39h]
  struct _SDP_NODE *v69; // [rsp+58h] [rbp-21h]
  PVOID P; // [rsp+60h] [rbp-19h] BYREF
  struct _STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  struct _GUID v72; // [rsp+78h] [rbp-1h] BYREF
  unsigned int v74; // [rsp+E8h] [rbp+6Fh] BYREF
  PSDP_TREE_ROOT_NODE Tree; // [rsp+F0h] [rbp+77h]
  PSDP_NODE Parent; // [rsp+F8h] [rbp+7Fh]

  v3 = a2->SdpDidSupportLevel == 0;
  DestinationString = 0;
  v4 = a2;
  P = 0;
  v74 = 0;
  v72 = PnPInformationServiceClass_UUID;
  if ( !v3 )
  {
    RtlInitAnsiString(&DestinationString, "Device ID Service Record");
    Tree = SdpCreateNodeTree(0x44706453u);
    if ( !Tree )
      return (unsigned int)-1073741670;
    NodeSequence = SdpCreateNodeSequence(0x44706453u);
    if ( !NodeSequence )
      goto LABEL_10;
    Parent = 0;
    v69 = 0;
    NodeUUID16 = SdpCreateNodeUUID16(0x1200u, 0x44706453u);
    if ( !NodeUUID16 )
      goto LABEL_12;
    appended = SdpAppendNodeToContainerNode(NodeSequence, NodeUUID16);
    if ( appended < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      v12 = 11;
LABEL_168:
      v65 = v12;
      LOBYTE(v12) = 1;
      LOBYTE(v9) = v11;
      WPP_RECORDER_AND_TRACE_SF_d(
        v10->AttachedDevice,
        v9,
        v12,
        v10->DeviceExtension,
        2,
        8,
        v65,
        (__int64)WPP_2c573714d0f834c34b50df15b7970060_Traceguids,
        appended);
      SdpFreeOrphanedNode(NodeUUID16);
LABEL_169:
      if ( !NodeSequence )
      {
LABEL_171:
        if ( Parent )
          SdpFreeOrphanedNode(Parent);
        if ( !v69 )
          goto LABEL_191;
        v42 = v69;
LABEL_182:
        SdpFreeOrphanedNode(v42);
LABEL_191:
        if ( P )
          ExFreePool(P);
        goto LABEL_200;
      }
LABEL_170:
      SdpFreeOrphanedNode(NodeSequence);
      goto LABEL_171;
    }
    appended = SdpAddAttributeToTree(Tree, 1u, NodeSequence, 0x44706453u);
    if ( appended < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      v16 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      v66 = appended;
      v62 = 12;
LABEL_125:
      LOBYTE(v14) = 1;
      LOBYTE(v13) = v16;
      WPP_RECORDER_AND_TRACE_SF_d(
        v15->AttachedDevice,
        v13,
        v14,
        v15->DeviceExtension,
        2,
        8,
        v62,
        (__int64)WPP_2c573714d0f834c34b50df15b7970060_Traceguids,
        v66);
      goto LABEL_170;
    }
    NodeSequence = SdpCreateNodeSequence(0x44706453u);
    if ( NodeSequence )
    {
      NodeUInt16 = SdpCreateNodeUInt16(0x656Eu, 0x44706453u);
      NodeUUID16 = NodeUInt16;
      if ( !NodeUInt16 )
        goto LABEL_12;
      appended = SdpAppendNodeToContainerNode(NodeSequence, NodeUInt16);
      if ( appended < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v12 = 13;
        goto LABEL_168;
      }
      v18 = SdpCreateNodeUInt16(0x6Au, 0x44706453u);
      v19 = v18;
      if ( !v18 )
        goto LABEL_12;
      appended = SdpAppendNodeToContainerNode(NodeSequence, v18);
      if ( appended < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        v23 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v67 = appended;
        v63 = 14;
LABEL_84:
        LOBYTE(v21) = 1;
        LOBYTE(v20) = v23;
        WPP_RECORDER_AND_TRACE_SF_d(
          v22->AttachedDevice,
          v20,
          v21,
          v22->DeviceExtension,
          2,
          8,
          v63,
          (__int64)WPP_2c573714d0f834c34b50df15b7970060_Traceguids,
          v67);
        SdpFreeOrphanedNode(v19);
        goto LABEL_169;
      }
      v24 = SdpCreateNodeUInt16(0x100u, 0x44706453u);
      v25 = v24;
      if ( !v24 )
        goto LABEL_12;
      appended = SdpAppendNodeToContainerNode(NodeSequence, v24);
      if ( appended < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        v29 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v68 = appended;
        v64 = 15;
LABEL_47:
        LOBYTE(v27) = 1;
        LOBYTE(v26) = v29;
        WPP_RECORDER_AND_TRACE_SF_d(
          v28->AttachedDevice,
          v26,
          v27,
          v28->DeviceExtension,
          2,
          8,
          v64,
          (__int64)WPP_2c573714d0f834c34b50df15b7970060_Traceguids,
          v68);
        SdpFreeOrphanedNode(v25);
        goto LABEL_169;
      }
      appended = SdpAddAttributeToTree(Tree, 6u, NodeSequence, 0x44706453u);
      if ( appended < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        v16 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v66 = appended;
        v62 = 16;
        goto LABEL_125;
      }
      NodeUUID16 = SdpCreateNodeString(DestinationString.Buffer, DestinationString.Length, 0x44706453u);
      if ( NodeUUID16 )
      {
        NodeSequence = 0;
        appended = SdpAddAttributeToTree(Tree, 0x100u, NodeUUID16, 0x44706453u);
        if ( appended < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          v12 = 17;
          goto LABEL_168;
        }
        NodeString = SdpCreateNodeString(DestinationString.Buffer, DestinationString.Length, 0x44706453u);
        NodeUUID16 = NodeString;
        if ( NodeString )
        {
          appended = SdpAddAttributeToTree(Tree, 0x101u, NodeString, 0x44706453u);
          if ( appended < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
            v12 = 18;
            goto LABEL_168;
          }
          NodeSequence = SdpCreateNodeSequence(0x44706453u);
          if ( NodeSequence )
          {
            Parent = SdpCreateNodeSequence(0x44706453u);
            if ( !Parent )
              goto LABEL_12;
            v31 = SdpCreateNodeUUID16(0x100u, 0x44706453u);
            NodeUUID16 = v31;
            if ( !v31 )
              goto LABEL_12;
            appended = SdpAppendNodeToContainerNode(Parent, v31);
            if ( appended < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              v12 = 19;
              goto LABEL_168;
            }
            v32 = SdpCreateNodeUInt16(1u, 0x44706453u);
            v19 = v32;
            if ( !v32 )
              goto LABEL_12;
            v33 = Parent;
            appended = SdpAppendNodeToContainerNode(Parent, v32);
            if ( appended < 0 )
            {
              v22 = WPP_GLOBAL_Control;
              v23 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              v67 = appended;
              v63 = 20;
              goto LABEL_84;
            }
            appended = SdpAppendNodeToContainerNode(NodeSequence, v33);
            if ( appended < 0 )
            {
              v15 = WPP_GLOBAL_Control;
              v16 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              v66 = appended;
              v62 = 21;
              goto LABEL_125;
            }
            Parent = 0;
            v69 = SdpCreateNodeSequence(0x44706453u);
            if ( !v69 )
              goto LABEL_12;
            v34 = SdpCreateNodeUUID16(1u, 0x44706453u);
            v25 = v34;
            if ( !v34 )
              goto LABEL_12;
            appended = SdpAppendNodeToContainerNode(v69, v34);
            if ( appended < 0 )
            {
              v28 = WPP_GLOBAL_Control;
              v29 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              v68 = appended;
              v64 = 22;
              goto LABEL_47;
            }
            appended = SdpAppendNodeToContainerNode(NodeSequence, v69);
            if ( appended < 0 )
            {
              v15 = WPP_GLOBAL_Control;
              v16 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              v66 = appended;
              v62 = 23;
              goto LABEL_125;
            }
            v69 = 0;
            appended = SdpAddAttributeToTree(Tree, 4u, NodeSequence, 0x44706453u);
            if ( appended < 0 )
            {
              v15 = WPP_GLOBAL_Control;
              v16 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              v66 = appended;
              v62 = 24;
              goto LABEL_125;
            }
            NodeSequence = SdpCreateNodeSequence(0x44706453u);
            if ( NodeSequence )
            {
              NodeUUID16 = SdpCreateNodeUUID16(0x1002u, 0x44706453u);
              if ( NodeUUID16 )
              {
                appended = SdpAppendNodeToContainerNode(NodeSequence, NodeUUID16);
                if ( appended < 0 )
                {
                  v10 = WPP_GLOBAL_Control;
                  v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                  v12 = 25;
                  goto LABEL_168;
                }
                appended = SdpAddAttributeToTree(Tree, 5u, NodeSequence, 0x44706453u);
                if ( appended < 0 )
                {
                  v15 = WPP_GLOBAL_Control;
                  v16 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                  v66 = appended;
                  v62 = 26;
                  goto LABEL_125;
                }
                v35 = SdpCreateNodeUInt16(0x103u, 0x44706453u);
                NodeUUID16 = v35;
                if ( v35 )
                {
                  NodeSequence = 0;
                  appended = SdpAddAttributeToTree(Tree, 0x200u, v35, 0x44706453u);
                  if ( appended < 0 )
                  {
                    v10 = WPP_GLOBAL_Control;
                    v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                    v12 = 27;
                    goto LABEL_168;
                  }
                  v36 = SdpCreateNodeUInt16(v4->SdpDidInfo.VendorId, 0x44706453u);
                  NodeUUID16 = v36;
                  if ( v36 )
                  {
                    appended = SdpAddAttributeToTree(Tree, 0x201u, v36, 0x44706453u);
                    if ( appended < 0 )
                    {
                      v10 = WPP_GLOBAL_Control;
                      v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                      v12 = 28;
                      goto LABEL_168;
                    }
                    v37 = SdpCreateNodeUInt16(v4->SdpDidInfo.ProductId, 0x44706453u);
                    NodeUUID16 = v37;
                    if ( v37 )
                    {
                      appended = SdpAddAttributeToTree(Tree, 0x202u, v37, 0x44706453u);
                      if ( appended < 0 )
                      {
                        v10 = WPP_GLOBAL_Control;
                        v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                        v12 = 29;
                        goto LABEL_168;
                      }
                      v38 = SdpCreateNodeUInt16(v4->SdpDidInfo.Version, 0x44706453u);
                      NodeUUID16 = v38;
                      if ( v38 )
                      {
                        appended = SdpAddAttributeToTree(Tree, 0x203u, v38, 0x44706453u);
                        if ( appended < 0 )
                        {
                          v10 = WPP_GLOBAL_Control;
                          v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                          v12 = 30;
                          goto LABEL_168;
                        }
                        v39 = SdpCreateNodeUInt16(v4->SdpDidInfo.VendorIdSource, 0x44706453u);
                        NodeUUID16 = v39;
                        if ( v39 )
                        {
                          v40 = Tree;
                          appended = SdpAddAttributeToTree(Tree, 0x205u, v39, 0x44706453u);
                          if ( appended < 0 )
                          {
                            v10 = WPP_GLOBAL_Control;
                            v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                            v12 = 31;
                            goto LABEL_168;
                          }
                          NodeBoolean = SdpCreateNodeBoolean(1u, 0x44706453u);
                          NodeUUID16 = NodeBoolean;
                          if ( NodeBoolean )
                          {
                            appended = SdpAddAttributeToTree(v40, 0x204u, NodeBoolean, 0x44706453u);
                            if ( appended < 0 )
                            {
                              v10 = WPP_GLOBAL_Control;
                              v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                              v12 = 32;
                              goto LABEL_168;
                            }
                            v43 = (_InterlockedExchangeAdd(&a1->NextRecordHandle, 1u) - 0x10000 + 1) % 0xFFFF0000
                                + 0x10000;
                            NodeUInt32 = SdpCreateNodeUInt32(v43, 0x44706453u);
                            v45 = NodeUInt32;
                            if ( NodeUInt32 )
                            {
                              appended = SdpAddAttributeToTree(v40, 0, NodeUInt32, 0x44706453u);
                              if ( appended >= 0 )
                              {
                                appended = SdpStreamFromTree(v40, &P, &v74, 1148216403);
                                if ( appended >= 0 )
                                {
                                  v52 = v74;
                                  Pool2 = ExAllocatePool2(256, v74, 1346917442);
                                  v54 = Pool2;
                                  if ( Pool2 )
                                  {
                                    v55 = *(struct _SECURITY_DATABASE **)&Globals;
                                    *(_QWORD *)(Pool2 + 24) = 1;
                                    *(_QWORD *)(Pool2 + 32) = 1;
                                    *(_QWORD *)(Pool2 + 40) = 0;
                                    *(_QWORD *)(Pool2 + 8) = Pool2;
                                    *(_QWORD *)Pool2 = Pool2;
                                    *(_OWORD *)(Pool2 + 72) = 0;
                                    *(_QWORD *)(Pool2 + 88) = 0;
                                    SecDB_AddService(v55, &v72, 1);
                                    ExAcquireFastMutex(&a1->ServiceRecordListMutex);
                                    v56 = v72;
                                    v57 = P;
                                    *(_DWORD *)(v54 + 16) = 0;
                                    *(struct _GUID *)(v54 + 56) = v56;
                                    *(_DWORD *)(v54 + 36) = v52;
                                    *(_DWORD *)(v54 + 20) = 8;
                                    *(_DWORD *)(v54 + 32) = v43;
                                    *(_QWORD *)(v54 + 48) = 0;
                                    *(_QWORD *)(v54 + 40) = v57;
                                    *(_DWORD *)(v54 + 72) = 1;
                                    *(GUID *)(v54 + 76) = SDP_PROTOCOL_UUID;
                                    *(_WORD *)(v54 + 92) = 1;
                                    SdpDB_AlterDatabaseState(a1);
                                    Blink = a1->ServiceRecordList.Blink;
                                    if ( (struct _SDP_DATABASE *)Blink->Flink != a1 )
                                      __fastfail(3u);
                                    *(_QWORD *)v54 = a1;
                                    *(_QWORD *)(v54 + 8) = Blink;
                                    Blink->Flink = (_LIST_ENTRY *)v54;
                                    a1->ServiceRecordList.Blink = (_LIST_ENTRY *)v54;
                                    ExReleaseFastMutex(&a1->ServiceRecordListMutex);
                                    LOBYTE(v59) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                                               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
                                    LOBYTE(v60) = 1;
                                    WPP_RECORDER_AND_TRACE_SF_qL(
                                      WPP_GLOBAL_Control->AttachedDevice,
                                      v59,
                                      v60,
                                      WPP_GLOBAL_Control->DeviceExtension,
                                      4,
                                      8,
                                      35,
                                      (__int64)WPP_2c573714d0f834c34b50df15b7970060_Traceguids,
                                      *(_QWORD *)(v54 + 40),
                                      *(_DWORD *)(v54 + 36));
                                    goto LABEL_200;
                                  }
                                  appended = -1073741670;
                                }
                                else
                                {
                                  v51 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                                  LOBYTE(v50) = 1;
                                  LOBYTE(v49) = v51;
                                  WPP_RECORDER_AND_TRACE_SF_d(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    v49,
                                    v50,
                                    WPP_GLOBAL_Control->DeviceExtension,
                                    2,
                                    8,
                                    34,
                                    (__int64)WPP_2c573714d0f834c34b50df15b7970060_Traceguids,
                                    appended);
                                }
                                goto LABEL_191;
                              }
                              v48 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                              LOBYTE(v47) = 1;
                              LOBYTE(v46) = v48;
                              WPP_RECORDER_AND_TRACE_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                v46,
                                v47,
                                WPP_GLOBAL_Control->DeviceExtension,
                                2,
                                8,
                                33,
                                (__int64)WPP_2c573714d0f834c34b50df15b7970060_Traceguids,
                                appended);
                              v42 = v45;
                              goto LABEL_182;
                            }
                          }
                        }
                      }
                    }
                  }
                }
                goto LABEL_10;
              }
LABEL_12:
              appended = -1073741670;
              goto LABEL_170;
            }
          }
        }
      }
    }
LABEL_10:
    appended = -1073741670;
LABEL_200:
    SdpFreeTree(Tree);
    return (unsigned int)appended;
  }
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = 1;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    8,
    10,
    (__int64)WPP_2c573714d0f834c34b50df15b7970060_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1401498ac  mov     [rsp-8+arg_0], rcx
0x1401498b1  push    rbp
0x1401498b2  push    rbx
0x1401498b3  push    rsi
0x1401498b4  push    rdi
0x1401498b5  push    r12
0x1401498b7  push    r13
0x1401498b9  push    r14
0x1401498bb  push    r15
0x1401498bd  lea     rbp, [rsp-1Fh]
0x1401498c2  sub     rsp, 98h
0x1401498c9  cmp     dword ptr [rdx+1F0h], 0
0x1401498d0  xorps   xmm0, xmm0
0x1401498d3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1401498d7  mov     rsi, rdx
0x1401498da  mov     r13, rcx
0x1401498dd  movups  xmm0, xmmword ptr cs:PnPInformationServiceClass_UUID.Data1
0x1401498e4  mov     [rbp+57h+P], 0
0x1401498ec  mov     [rbp+57h+arg_8], 0
0x1401498f3  movdqu  xmmword ptr [rbp+57h+var_58.Data1], xmm0
0x1401498f8  jnz     short loc_140149951
0x1401498fa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140149901  mov     edi, 1
0x140149906  mov     eax, [rcx+2Ch]
0x140149909  test    al, al
0x14014990b  jns     short loc_140149918
0x14014990d  cmp     byte ptr [rcx+29h], 4
0x140149911  jb      short loc_140149918
0x140149913  mov     dl, dil
0x140149916  jmp     short loc_14014991A
0x140149918  xor     dl, dl
0x14014991a  mov     r9, [rcx+40h]
0x14014991e  lea     rax, WPP_2c573714d0f834c34b50df15b7970060_Traceguids
0x140149925  mov     rcx, [rcx+18h]
0x140149929  mov     r8b, dil
0x14014992c  mov     [rsp+0D0h+var_98], rax
0x140149931  mov     [rsp+0D0h+var_A0], 0Ah
0x140149938  mov     [rsp+0D0h+var_A8], 8
0x140149940  mov     [rsp+0D0h+var_B0], 4
0x140149945  call    WPP_RECORDER_AND_TRACE_SF_
0x14014994a  xor     ebx, ebx
0x14014994c  jmp     loc_14014A5B1
0x140149951  lea     rdx, aDeviceIdServic; "Device ID Service Record"
0x140149958  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14014995c  call    cs:__imp_RtlInitAnsiString
0x140149963  nop     dword ptr [rax+rax+00h]
0x140149968  mov     ebx, 44706453h
0x14014996d  mov     ecx, ebx; tag
0x14014996f  call    SdpCreateNodeTree
0x140149974  mov     [rbp+57h+Tree], rax
0x140149978  test    rax, rax
0x14014997b  jnz     short loc_140149987
0x14014997d  mov     ebx, 0C000009Ah
0x140149982  jmp     loc_14014A5B1
0x140149987  mov     ecx, ebx; tag
0x140149989  call    SdpCreateNodeSequence
0x14014998e  mov     r15, rax
0x140149991  test    rax, rax
0x140149994  jnz     short loc_1401499A0
0x140149996  mov     ebx, 0C000009Ah
0x14014999b  jmp     loc_14014A5A8
0x1401499a0  mov     ecx, 1200h; uuidVal2
0x1401499a5  mov     [rbp+57h+Parent], 0
0x1401499ad  mov     edx, ebx; tag
0x1401499af  mov     [rbp+57h+var_78], 0
0x1401499b7  call    SdpCreateNodeUUID16
0x1401499bc  mov     r14, rax
0x1401499bf  test    rax, rax
0x1401499c2  jnz     short loc_1401499CE
0x1401499c4  mov     ebx, 0C000009Ah
0x1401499c9  jmp     loc_14014A2F6
0x1401499ce  xor     eax, eax
0x1401499d0  mov     rdx, r14; Node
0x1401499d3  mov     rcx, r15; Parent
0x1401499d6  mov     [rbp+57h+var_80], rax
0x1401499da  xor     r12d, r12d
0x1401499dd  call    SdpAppendNodeToContainerNode
0x1401499e2  mov     ebx, eax
0x1401499e4  test    eax, eax
0x1401499e6  jns     short loc_140149A16
0x1401499e8  mov     r9, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401499ef  lea     edi, [r12+1]
0x1401499f4  mov     dl, 2
0x1401499f6  mov     ecx, [r9+2Ch]
0x1401499fa  test    cl, cl
0x1401499fc  jns     short loc_140149A09
0x1401499fe  cmp     [r9+29h], dl
0x140149a02  jb      short loc_140149A09
0x140149a04  mov     cl, dil
0x140149a07  jmp     short loc_140149A0B
0x140149a09  xor     cl, cl
0x140149a0b  mov     r8d, 0Bh
0x140149a11  jmp     loc_14014A290
0x140149a16  mov     rcx, [rbp+57h+Tree]; Tree
0x140149a1a  mov     edi, 1
0x140149a1f  mov     r14d, 44706453h
0x140149a25  mov     edx, edi; AttribId
0x140149a27  mov     r9d, r14d; tag
0x140149a2a  mov     r8, r15; AttribValue
0x140149a2d  call    SdpAddAttributeToTree
0x140149a32  mov     ebx, eax
0x140149a34  test    eax, eax
0x140149a36  jns     short loc_140149A71
0x140149a38  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140149a3f  mov     dl, 2
0x140149a41  mov     eax, [rcx+2Ch]
0x140149a44  test    al, al
0x140149a46  jns     short loc_140149A52
0x140149a48  cmp     [rcx+29h], dl
0x140149a4b  jb      short loc_140149A52
0x140149a4d  mov     r10b, dil
0x140149a50  jmp     short loc_140149A55
0x140149a52  xor     r10b, r10b
0x140149a55  mov     dword ptr [rsp+0D0h+var_90], ebx
0x140149a59  lea     rax, WPP_2c573714d0f834c34b50df15b7970060_Traceguids
0x140149a60  mov     [rsp+0D0h+var_98], rax
0x140149a65  mov     [rsp+0D0h+var_A0], 0Ch
0x140149a6c  jmp     loc_14014A025
0x140149a71  mov     ecx, r14d; tag
0x140149a74  call    SdpCreateNodeSequence
0x140149a79  mov     r15, rax
0x140149a7c  test    rax, rax
0x140149a7f  jz      loc_140149996
0x140149a85  mov     ecx, 656Eh; usVal
0x140149a8a  mov     edx, r14d; tag
0x140149a8d  call    SdpCreateNodeUInt16
0x140149a92  mov     r14, rax
0x140149a95  test    rax, rax
0x140149a98  jz      loc_1401499C4
0x140149a9e  mov     rdx, rax; Node
0x140149aa1  mov     rcx, r15; Parent
0x140149aa4  call    SdpAppendNodeToContainerNode
0x140149aa9  mov     ebx, eax
0x140149aab  test    eax, eax
0x140149aad  jns     short loc_140149AD8
0x140149aaf  mov     r9, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140149ab6  mov     dl, 2
0x140149ab8  mov     eax, [r9+2Ch]
0x140149abc  test    al, al
0x140149abe  jns     short loc_140149ACB
0x140149ac0  cmp     [r9+29h], dl
0x140149ac4  jb      short loc_140149ACB
0x140149ac6  mov     cl, dil
0x140149ac9  jmp     short loc_140149ACD
0x140149acb  xor     cl, cl
0x140149acd  mov     r8d, 0Dh
0x140149ad3  jmp     loc_14014A290
0x140149ad8  mov     ecx, 6Ah ; 'j'; usVal
0x140149add  mov     edx, 44706453h; tag
0x140149ae2  call    SdpCreateNodeUInt16
0x140149ae7  mov     r12, rax
0x140149aea  test    rax, rax
0x140149aed  jz      loc_1401499C4
0x140149af3  mov     rdx, rax; Node
0x140149af6  mov     rcx, r15; Parent
0x140149af9  call    SdpAppendNodeToContainerNode
0x140149afe  mov     ebx, eax
0x140149b00  test    eax, eax
0x140149b02  jns     short loc_140149B3D
0x140149b04  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140149b0b  mov     dl, 2
0x140149b0d  mov     eax, [rcx+2Ch]
0x140149b10  test    al, al
0x140149b12  jns     short loc_140149B1E
0x140149b14  cmp     [rcx+29h], dl
0x140149b17  jb      short loc_140149B1E
0x140149b19  mov     r10b, dil
0x140149b1c  jmp     short loc_140149B21
0x140149b1e  xor     r10b, r10b
0x140149b21  mov     dword ptr [rsp+0D0h+var_90], ebx
0x140149b25  lea     rax, WPP_2c573714d0f834c34b50df15b7970060_Traceguids
0x140149b2c  mov     [rsp+0D0h+var_98], rax
0x140149b31  mov     [rsp+0D0h+var_A0], 0Eh
0x140149b38  jmp     loc_140149DCA
0x140149b3d  mov     r12d, 44706453h
0x140149b43  mov     ecx, 100h; usVal
0x140149b48  mov     edx, r12d; tag
0x140149b4b  call    SdpCreateNodeUInt16
0x140149b50  mov     r14, rax
0x140149b53  test    rax, rax
0x140149b56  jz      loc_1401499C4
0x140149b5c  mov     rdx, rax; Node
0x140149b5f  mov     rcx, r15; Parent
0x140149b62  call    SdpAppendNodeToContainerNode
0x140149b67  mov     ebx, eax
0x140149b69  test    eax, eax
0x140149b6b  jns     short loc_140149BC5
0x140149b6d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140149b74  mov     dl, 2
0x140149b76  mov     eax, [rcx+2Ch]
0x140149b79  test    al, al
0x140149b7b  jns     short loc_140149B87
0x140149b7d  cmp     [rcx+29h], dl
0x140149b80  jb      short loc_140149B87
0x140149b82  mov     r10b, dil
0x140149b85  jmp     short loc_140149B8A
0x140149b87  xor     r10b, r10b
0x140149b8a  mov     dword ptr [rsp+0D0h+var_90], ebx
0x140149b8e  lea     rax, WPP_2c573714d0f834c34b50df15b7970060_Traceguids
0x140149b95  mov     [rsp+0D0h+var_98], rax
0x140149b9a  mov     [rsp+0D0h+var_A0], 0Fh
0x140149ba1  mov     r9, [rcx+40h]
0x140149ba5  mov     r8b, dil
0x140149ba8  mov     rcx, [rcx+18h]
0x140149bac  mov     [rsp+0D0h+var_A8], 8
0x140149bb4  mov     [rsp+0D0h+var_B0], dl
0x140149bb8  mov     dl, r10b
0x140149bbb  call    WPP_RECORDER_AND_TRACE_SF_d
0x140149bc0  jmp     loc_14014A2E9
0x140149bc5  mov     rcx, [rbp+57h+Tree]; Tree
0x140149bc9  mov     edx, 6; AttribId
0x140149bce  mov     r9d, r12d; tag
0x140149bd1  mov     r8, r15; AttribValue
0x140149bd4  call    SdpAddAttributeToTree
0x140149bd9  mov     ebx, eax
0x140149bdb  test    eax, eax
0x140149bdd  jns     short loc_140149C18
0x140149bdf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140149be6  mov     dl, 2
0x140149be8  mov     eax, [rcx+2Ch]
0x140149beb  test    al, al
0x140149bed  jns     short loc_140149BF9
0x140149bef  cmp     [rcx+29h], dl
0x140149bf2  jb      short loc_140149BF9
0x140149bf4  mov     r10b, dil
0x140149bf7  jmp     short loc_140149BFC
0x140149bf9  xor     r10b, r10b
0x140149bfc  mov     dword ptr [rsp+0D0h+var_90], ebx
0x140149c00  lea     rax, WPP_2c573714d0f834c34b50df15b7970060_Traceguids
0x140149c07  mov     [rsp+0D0h+var_98], rax
0x140149c0c  mov     [rsp+0D0h+var_A0], 10h
0x140149c13  jmp     loc_14014A025
0x140149c18  movzx   edx, [rbp+57h+DestinationString.Length]; stringLength
0x140149c1c  mov     r8d, r12d; tag
0x140149c1f  mov     rcx, [rbp+57h+DestinationString.Buffer]; string
0x140149c23  call    SdpCreateNodeString
0x140149c28  mov     r14, rax
0x140149c2b  test    rax, rax
0x140149c2e  jz      loc_140149996
0x140149c34  mov     rcx, [rbp+57h+Tree]; Tree
0x140149c38  xor     eax, eax
0x140149c3a  mov     edx, 100h; AttribId
0x140149c3f  mov     [rbp+57h+var_80], rax
0x140149c43  mov     r9d, 44706453h; tag
0x140149c49  mov     r8, r14; AttribValue
0x140149c4c  xor     r12d, r12d
0x140149c4f  xor     r15d, r15d
0x140149c52  call    SdpAddAttributeToTree
0x140149c57  mov     ebx, eax
0x140149c59  test    eax, eax
0x140149c5b  jns     short loc_140149C86
0x140149c5d  mov     r9, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140149c64  mov     dl, 2
0x140149c66  mov     eax, [r9+2Ch]
0x140149c6a  test    al, al
0x140149c6c  jns     short loc_140149C79
0x140149c6e  cmp     [r9+29h], dl
0x140149c72  jb      short loc_140149C79
0x140149c74  mov     cl, dil
0x140149c77  jmp     short loc_140149C7B
0x140149c79  xor     cl, cl
0x140149c7b  mov     r8d, 11h
0x140149c81  jmp     loc_14014A290
0x140149c86  movzx   edx, [rbp+57h+DestinationString.Length]; stringLength
0x140149c8a  mov     ebx, 44706453h
0x140149c8f  mov     rcx, [rbp+57h+DestinationString.Buffer]; string
0x140149c93  mov     r8d, ebx; tag
0x140149c96  call    SdpCreateNodeString
0x140149c9b  mov     r14, rax
0x140149c9e  test    rax, rax
0x140149ca1  jz      loc_140149996
0x140149ca7  mov     rcx, [rbp+57h+Tree]; Tree
0x140149cab  mov     edx, 101h; AttribId
0x140149cb0  mov     r9d, ebx; tag
0x140149cb3  mov     r8, rax; AttribValue
0x140149cb6  call    SdpAddAttributeToTree
0x140149cbb  mov     ebx, eax
0x140149cbd  test    eax, eax
0x140149cbf  jns     short loc_140149CEA
0x140149cc1  mov     r9, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140149cc8  mov     dl, 2
0x140149cca  mov     eax, [r9+2Ch]
0x140149cce  test    al, al
0x140149cd0  jns     short loc_140149CDD
0x140149cd2  cmp     [r9+29h], dl
0x140149cd6  jb      short loc_140149CDD
0x140149cd8  mov     cl, dil
0x140149cdb  jmp     short loc_140149CDF
0x140149cdd  xor     cl, cl
0x140149cdf  mov     r8d, 12h
0x140149ce5  jmp     loc_14014A290
0x140149cea  mov     ebx, 44706453h
0x140149cef  mov     ecx, ebx; tag
0x140149cf1  call    SdpCreateNodeSequence
0x140149cf6  mov     r15, rax
0x140149cf9  test    rax, rax
0x140149cfc  jz      loc_140149996
0x140149d02  mov     ecx, ebx; tag
0x140149d04  call    SdpCreateNodeSequence
0x140149d09  mov     [rbp+57h+Parent], rax
  ... truncated ...
```
