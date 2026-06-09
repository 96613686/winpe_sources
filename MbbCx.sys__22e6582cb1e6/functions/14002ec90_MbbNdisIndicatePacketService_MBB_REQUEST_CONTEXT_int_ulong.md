# MbbNdisIndicatePacketService(_MBB_REQUEST_CONTEXT *,int,ulong)

- ea: `0x14002ec90`
- end: `0x14002f0c2`
- name: `?MbbNdisIndicatePacketService@@YAXPEAU_MBB_REQUEST_CONTEXT@@HK@Z`
- size: `1074`
- prototype: `void __fastcall(struct _MBB_REQUEST_CONTEXT *, int, unsigned int)`
- caller_count: `4`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140027eb8`
- `0x1400280f8`
- `0x140028340`
- `0x140034530`

## callees

- `0x1400051ac`
- `0x140005778`
- `0x140011278`
- `0x140019b6c`
- `0x140019f78`
- `0x14001a168`
- `0x14001b900`
- `0x1400245e0`
- `0x14002ec90`
- `0x14002f0c8`
- `0x14003b20c`
- `0x14003e100`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002f08e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f08e`

## pseudocode

```c
void __fastcall MbbNdisIndicatePacketService(struct _MBB_REQUEST_CONTEXT *a1, int a2, __int64 a3)
{
  _DWORD *v3; // rsi
  int v5; // ecx
  unsigned int v6; // r12d
  int v7; // eax
  ULONG v8; // edi
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rdx
  NDIS_HANDLE *v12; // rax
  struct _MBB_REQUEST_CONTEXT *Request; // rdi
  char (near **CommandString)[32]; // rax
  int v15; // edx
  char (near **v16)[32]; // rax
  int v17; // edx
  int v18; // r13d
  char (near **v19)[32]; // rax
  int v20; // edx
  int v21; // r8d
  __int64 v22; // [rsp+38h] [rbp-81h]
  int v23[4]; // [rsp+40h] [rbp-79h] BYREF
  struct _NDIS_STATUS_INDICATION v24; // [rsp+50h] [rbp-69h] BYREF
  __int128 v25; // [rsp+C0h] [rbp+7h] BYREF
  int v26; // [rsp+D0h] [rbp+17h]

  v3 = (_DWORD *)*((_QWORD *)a1 + 92);
  v23[0] = a2;
  v5 = *((_DWORD *)a1 + 182);
  v26 = 0;
  v6 = a3;
  v25 = 0;
  if ( (v5 & 4) == 0 )
  {
    v5 |= 4u;
    *((_DWORD *)a1 + 182) = v5;
    if ( *((_OWORD *)a1 + 44) == MBB_UUID_BASIC_CONNECT && *((_DWORD *)a1 + 180) == 10 && !*((_BYTE *)a1 + 576) )
    {
      v5 |= 2u;
      *((_DWORD *)a1 + 182) = v5;
    }
  }
  if ( a2 )
  {
    v6 = -1073479677;
    if ( (_DWORD)a3 )
      v6 = a3;
    goto LABEL_42;
  }
  v7 = v5 & 1;
  if ( v3 )
  {
    if ( (v5 & 1) != 0 )
    {
      v8 = *((_DWORD *)a1 + 183);
      memset(&v24.Header + 1, 0, 0x6Cu);
      v3[4] = *((_DWORD *)a1 + 186);
      v10 = *((_QWORD *)a1 + 6);
      v24.Header = (NDIS_OBJECT_HEADER)7340440;
      v24.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v10 + 1144LL) + 16LL);
      v24.DestinationHandle = (NDIS_HANDLE)*((_QWORD *)a1 + 55);
      v24.RequestId = (PVOID)*((_QWORD *)a1 + 54);
      v24.PortNumber = 0;
      *(_QWORD *)&v24.StatusCode = 1074008073;
      v24.Guid = 0;
      v24.StatusBuffer = v3;
      v24.StatusBufferSize = v8;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 4;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          3,
          76,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *((_DWORD *)a1 + 4),
          v8);
      }
      v11 = *((_QWORD *)a1 + 13);
      if ( v11 )
        v12 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031
                                                                                                 + 1616))(
                                WdfDriverGlobals,
                                v11,
                                off_14005DF38)
                            + 24);
      else
        v12 = **(NDIS_HANDLE ***)(**((_QWORD **)a1 + 6) + 1144LL);
      MbbUtilNdisMiniportIndicateStatusEx(v12, &v24);
LABEL_43:
      ExFreePoolWithTag(v3, 0);
      return;
    }
    v7 = 0;
  }
  else if ( (v5 & 1) == 0 )
  {
    if ( (v5 & 2) == 0 )
      return;
LABEL_42:
    MbbNdisIndicatePacketServiceFailure(a1, v6);
    if ( !v3 )
      return;
    goto LABEL_43;
  }
  if ( (_DWORD)a3 && *((_QWORD *)a1 + 54) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_DDd(WPP_GLOBAL_Control->DeviceExtension, a2, a3, 77);
    }
    goto LABEL_42;
  }
  if ( v3 )
  {
    if ( v7 )
      goto LABEL_31;
    v26 = 9;
  }
  else
  {
    v26 = 10;
  }
  v25 = MBB_UUID_BASIC_CONNECT;
LABEL_31:
  Request = MbbReqMgrCreateRequest(*((struct _MBB_REQUEST_MANAGER **)a1 + 6), 0, a3, v23, 1u);
  if ( !Request )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      CommandString = MbbUtilGetCommandString((struct _MBB_COMMAND *)&v25);
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_Ds(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        3,
        78,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4),
        (__int64)CommandString);
    }
    goto LABEL_42;
  }
  *((_QWORD *)Request + 10) = MbbNdisGetOidHandlerByCommand((struct _MBB_COMMAND *)&v25);
  if ( (*((_DWORD *)a1 + 182) & 2) != 0 )
  {
    *((_QWORD *)Request + 54) = *((_QWORD *)a1 + 54);
    *((_QWORD *)Request + 55) = *((_QWORD *)a1 + 55);
  }
  *(_OWORD *)((char *)Request + 728) = *(_OWORD *)((char *)a1 + 728);
  *((_QWORD *)Request + 93) = *((_QWORD *)a1 + 93);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v16 = MbbUtilGetCommandString((struct _MBB_COMMAND *)&v25);
    WPP_RECORDER_SF_DDs(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      3,
      79,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *((_DWORD *)a1 + 4),
      *((_DWORD *)Request + 4),
      (__int64)v16);
  }
  v18 = MbbReqMgrDispatchRequest(
          (union _LARGE_INTEGER *)Request,
          (*(_DWORD *)(*((_QWORD *)Request + 10) + 4LL) & 4) != 0,
          (int (*)(void *, struct _MBB_REQUEST_CONTEXT *))MbbUtilInternalCIDQuery,
          (void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int))MbbUtilInternalCIDCompletion,
          (void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int))MbbUtilInternalCIDResponse);
  if ( v18 != 259 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = MbbUtilGetCommandString((struct _MBB_COMMAND *)&v25);
      LODWORD(v22) = v18;
      WPP_RECORDER_SF_Dsd(
        WPP_GLOBAL_Control->DeviceExtension,
        v20,
        v21,
        80,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)Request + 4),
        (__int64)v19,
        v22,
        *(_QWORD *)v23);
    }
    MbbReqMgrDerefRequest(Request);
    goto LABEL_42;
  }
}

```

## disassembly

```asm
0x14002ec90  mov     [rsp-8+arg_18], rbx
0x14002ec95  push    rbp
0x14002ec96  push    rsi
0x14002ec97  push    rdi
0x14002ec98  push    r12
0x14002ec9a  push    r13
0x14002ec9c  push    r14
0x14002ec9e  push    r15
0x14002eca0  lea     rbp, [rsp-27h]
0x14002eca5  sub     rsp, 0E0h
0x14002ecac  mov     rax, cs:__security_cookie
0x14002ecb3  xor     rax, rsp
0x14002ecb6  mov     [rbp+57h+var_38], rax
0x14002ecba  mov     rsi, [rcx+2E0h]
0x14002ecc1  xor     eax, eax
0x14002ecc3  mov     rbx, rcx
0x14002ecc6  mov     [rbp+57h+var_D0], edx
0x14002ecc9  mov     ecx, [rcx+2D8h]
0x14002eccf  xorps   xmm0, xmm0
0x14002ecd2  mov     [rbp+57h+var_40], eax
0x14002ecd5  mov     r12d, r8d
0x14002ecd8  movups  [rbp+57h+var_50], xmm0
0x14002ecdc  test    cl, 4
0x14002ecdf  jnz     short loc_14002ED25
0x14002ece1  or      ecx, 4
0x14002ece4  mov     [rbx+2D8h], ecx
0x14002ecea  mov     rax, [rbx+2C0h]
0x14002ecf1  cmp     rax, qword ptr cs:MBB_UUID_BASIC_CONNECT
0x14002ecf8  jnz     short loc_14002ED25
0x14002ecfa  mov     rax, [rbx+2C8h]
0x14002ed01  cmp     rax, qword ptr cs:MBB_UUID_BASIC_CONNECT+8
0x14002ed08  jnz     short loc_14002ED25
0x14002ed0a  cmp     dword ptr [rbx+2D0h], 0Ah
0x14002ed11  jnz     short loc_14002ED25
0x14002ed13  cmp     byte ptr [rbx+240h], 0
0x14002ed1a  jnz     short loc_14002ED25
0x14002ed1c  or      ecx, 2
0x14002ed1f  mov     [rbx+2D8h], ecx
0x14002ed25  test    edx, edx
0x14002ed27  jz      short loc_14002ED3B
0x14002ed29  test    r8d, r8d
0x14002ed2c  mov     r12d, 0C0040003h
0x14002ed32  cmovnz  r12d, r8d
0x14002ed36  jmp     loc_14002F079
0x14002ed3b  mov     eax, ecx
0x14002ed3d  and     eax, 1
0x14002ed40  test    rsi, rsi
0x14002ed43  jz      loc_14002EEAF
0x14002ed49  test    eax, eax
0x14002ed4b  jz      loc_14002EE57
0x14002ed51  mov     edi, [rbx+2DCh]
0x14002ed57  lea     rcx, [rbp+57h+var_C0+4]; void *
0x14002ed5b  xor     edx, edx; Val
0x14002ed5d  lea     r8d, [rdx+6Ch]; Size
0x14002ed61  call    memset
0x14002ed66  mov     eax, [rbx+2E8h]
0x14002ed6c  xorps   xmm0, xmm0
0x14002ed6f  mov     [rsi+10h], eax
0x14002ed72  mov     rax, [rbx+30h]
0x14002ed76  mov     dword ptr [rbp+57h+var_C0.Header.Type], 700198h
0x14002ed7d  mov     rcx, [rax]
0x14002ed80  mov     rax, [rcx+478h]
0x14002ed87  mov     rcx, [rax]
0x14002ed8a  mov     rax, [rcx+10h]
0x14002ed8e  mov     [rbp+57h+var_C0.SourceHandle], rax
0x14002ed92  mov     rax, [rbx+1B8h]
0x14002ed99  mov     [rbp+57h+var_C0.DestinationHandle], rax
0x14002ed9d  mov     rax, [rbx+1B0h]
0x14002eda4  mov     [rbp+57h+var_C0.RequestId], rax
0x14002eda8  mov     [rbp+57h+var_C0.PortNumber], 0
0x14002edaf  mov     qword ptr [rbp+57h+var_C0.StatusCode], 40041009h
0x14002edb7  movups  xmmword ptr [rbp+57h+var_C0.Guid.Data1], xmm0
0x14002edbb  mov     [rbp+57h+var_C0.StatusBuffer], rsi
0x14002edbf  mov     [rbp+57h+var_C0.StatusBufferSize], edi
0x14002edc2  lea     r14, WPP_RECORDER_INITIALIZED
0x14002edc9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002edd0  jz      short loc_14002EE05
0x14002edd2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002edd9  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002ede0  mov     eax, [rbx+10h]
0x14002ede3  mov     r9d, 4Ch ; 'L'
0x14002ede9  mov     dword ptr [rsp+110h+var_E0], edi
0x14002eded  mov     dl, 4
0x14002edef  mov     [rsp+110h+var_E8], eax
0x14002edf3  mov     rcx, [rcx+40h]
0x14002edf7  lea     r8d, [r9-49h]
0x14002edfb  mov     [rsp+110h+var_F0], r15
0x14002ee00  call    WPP_RECORDER_SF_DD
0x14002ee05  mov     rdx, [rbx+68h]
0x14002ee09  test    rdx, rdx
0x14002ee0c  jz      short loc_14002EE35
0x14002ee0e  mov     rax, cs:WdfFunctions_01031
0x14002ee15  mov     r8, cs:off_14005DF38
0x14002ee1c  mov     rcx, cs:WdfDriverGlobals
0x14002ee23  mov     rax, [rax+650h]
0x14002ee2a  call    _guard_dispatch_icall
0x14002ee2f  add     rax, 18h
0x14002ee33  jmp     short loc_14002EE46
0x14002ee35  mov     rax, [rbx+30h]
0x14002ee39  mov     rcx, [rax]
0x14002ee3c  mov     rax, [rcx+478h]
0x14002ee43  mov     rax, [rax]
0x14002ee46  lea     rdx, [rbp+57h+var_C0]; struct _NDIS_STATUS_INDICATION *
0x14002ee4a  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x14002ee4d  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14002ee52  jmp     loc_14002F089
0x14002ee57  xor     eax, eax
0x14002ee59  test    r8d, r8d
0x14002ee5c  jz      short loc_14002EEC2
0x14002ee5e  cmp     qword ptr [rbx+1B0h], 0
0x14002ee66  jz      short loc_14002EEC2
0x14002ee68  lea     r14, WPP_RECORDER_INITIALIZED
0x14002ee6f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002ee76  jz      loc_14002F079
0x14002ee7c  mov     eax, [rbx+1B0h]
0x14002ee82  mov     r9d, 4Dh ; 'M'
0x14002ee88  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ee8f  mov     dl, 4
0x14002ee91  mov     dword ptr [rsp+110h+var_D8], r8d
0x14002ee96  mov     dword ptr [rsp+110h+var_E0], eax
0x14002ee9a  mov     eax, [rbx+10h]
0x14002ee9d  mov     rcx, [rcx+40h]
0x14002eea1  mov     [rsp+110h+var_E8], eax
0x14002eea5  call    WPP_RECORDER_SF_DDd
0x14002eeaa  jmp     loc_14002F079
0x14002eeaf  test    eax, eax
0x14002eeb1  jnz     short loc_14002EE59
0x14002eeb3  bt      ecx, 1
0x14002eeb7  jnb     loc_14002F09A
0x14002eebd  jmp     loc_14002F079
0x14002eec2  test    rsi, rsi
0x14002eec5  jnz     short loc_14002EED0
0x14002eec7  mov     [rbp+57h+var_40], 0Ah
0x14002eece  jmp     short loc_14002EEDB
0x14002eed0  test    eax, eax
0x14002eed2  jnz     short loc_14002EEE7
0x14002eed4  mov     [rbp+57h+var_40], 9
0x14002eedb  movups  xmm0, cs:MBB_UUID_BASIC_CONNECT
0x14002eee2  movdqu  [rbp+57h+var_50], xmm0
0x14002eee7  mov     rcx, [rbx+30h]; struct _MBB_REQUEST_MANAGER *
0x14002eeeb  lea     r9, [rbp+57h+var_D0]; int *
0x14002eeef  xor     edx, edx; struct _NDIS_OID_REQUEST *
0x14002eef1  mov     byte ptr [rsp+110h+var_F0], 1; unsigned __int8
0x14002eef6  call    ?MbbReqMgrCreateRequest@@YAPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@PEAU_NDIS_OID_REQUEST@@KPEAHE@Z; MbbReqMgrCreateRequest(_MBB_REQUEST_MANAGER *,_NDIS_OID_REQUEST *,ulong,int *,uchar)
0x14002eefb  mov     rdi, rax
0x14002eefe  test    rax, rax
0x14002ef01  jnz     short loc_14002EF57
0x14002ef03  lea     r14, WPP_RECORDER_INITIALIZED
0x14002ef0a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002ef11  jz      loc_14002F079
0x14002ef17  lea     rcx, [rbp+57h+var_50]; Source1
0x14002ef1b  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14002ef20  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ef27  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002ef2e  mov     [rsp+110h+var_E0], rax
0x14002ef33  lea     r9d, [rdi+4Eh]
0x14002ef37  mov     eax, [rbx+10h]
0x14002ef3a  lea     r8d, [rdi+3]
0x14002ef3e  mov     [rsp+110h+var_E8], eax
0x14002ef42  mov     dl, 2
0x14002ef44  mov     rcx, [rcx+40h]
0x14002ef48  mov     [rsp+110h+var_F0], r15
0x14002ef4d  call    WPP_RECORDER_SF_Ds
0x14002ef52  jmp     loc_14002F079
0x14002ef57  lea     rcx, [rbp+57h+var_50]; struct _MBB_COMMAND *
0x14002ef5b  call    ?MbbNdisGetOidHandlerByCommand@@YAPEAU_MBB_OID_HANDLER_ENTRY@@PEAU_MBB_COMMAND@@@Z; MbbNdisGetOidHandlerByCommand(_MBB_COMMAND *)
0x14002ef60  mov     [rdi+50h], rax
0x14002ef64  mov     eax, [rbx+2D8h]
0x14002ef6a  test    al, 2
0x14002ef6c  jz      short loc_14002EF8A
0x14002ef6e  mov     rax, [rbx+1B0h]
0x14002ef75  mov     [rdi+1B0h], rax
0x14002ef7c  mov     rax, [rbx+1B8h]
0x14002ef83  mov     [rdi+1B8h], rax
0x14002ef8a  movups  xmm0, xmmword ptr [rbx+2D8h]
0x14002ef91  movups  xmmword ptr [rdi+2D8h], xmm0
0x14002ef98  movsd   xmm1, qword ptr [rbx+2E8h]
0x14002efa0  movsd   qword ptr [rdi+2E8h], xmm1
0x14002efa8  lea     r14, WPP_RECORDER_INITIALIZED
0x14002efaf  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002efb6  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002efbd  jz      short loc_14002EFFA
0x14002efbf  lea     rcx, [rbp+57h+var_50]; Source1
0x14002efc3  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14002efc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002efcf  mov     r9d, 4Fh ; 'O'
0x14002efd5  mov     [rsp+110h+var_D8], rax
0x14002efda  mov     eax, [rdi+10h]
0x14002efdd  mov     dword ptr [rsp+110h+var_E0], eax
0x14002efe1  mov     eax, [rbx+10h]
0x14002efe4  lea     r8d, [r9-4Ch]
0x14002efe8  mov     rcx, [rcx+40h]
0x14002efec  mov     [rsp+110h+var_E8], eax
0x14002eff0  mov     [rsp+110h+var_F0], r15
0x14002eff5  call    WPP_RECORDER_SF_DDs
0x14002effa  mov     rax, [rdi+50h]
0x14002effe  lea     r9, ?MbbUtilInternalCIDCompletion@@YAXPEAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int)
0x14002f005  lea     r8, ?MbbUtilInternalCIDQuery@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z; int (*)(void *, struct _MBB_REQUEST_CONTEXT *)
0x14002f00c  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x14002f00f  mov     edx, [rax+4]
0x14002f012  lea     rax, ?MbbUtilInternalCIDResponse@@YAXPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbUtilInternalCIDResponse(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x14002f019  shr     edx, 2
0x14002f01c  and     dl, 1; unsigned __int8
0x14002f01f  mov     [rsp+110h+var_F0], rax; void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int)
0x14002f024  call    ?MbbReqMgrDispatchRequest@@YAHPEAU_MBB_REQUEST_CONTEXT@@EP6AHPEAX0@ZP6AX10H@ZP6AX0HW4_MBB_STATUS@@PEAEK@Z@Z; MbbReqMgrDispatchRequest(_MBB_REQUEST_CONTEXT *,uchar,int (*)(void *,_MBB_REQUEST_CONTEXT *),void (*)(void *,_MBB_REQUEST_CONTEXT *,int),void (*)(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong))
0x14002f029  mov     r13d, eax
0x14002f02c  cmp     eax, 103h
0x14002f031  jz      short loc_14002F09A
0x14002f033  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002f03a  jz      short loc_14002F071
0x14002f03c  lea     rcx, [rbp+57h+var_50]; Source1
0x14002f040  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14002f045  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f04c  mov     r9d, 50h ; 'P'
0x14002f052  mov     dword ptr [rsp+110h+var_D8], r13d
0x14002f057  mov     [rsp+110h+var_E0], rax
0x14002f05c  mov     eax, [rdi+10h]
0x14002f05f  mov     rcx, [rcx+40h]
0x14002f063  mov     [rsp+110h+var_E8], eax
0x14002f067  mov     [rsp+110h+var_F0], r15
0x14002f06c  call    WPP_RECORDER_SF_Dsd
0x14002f071  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x14002f074  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x14002f079  mov     edx, r12d; unsigned int
0x14002f07c  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x14002f07f  call    ?MbbNdisIndicatePacketServiceFailure@@YAXPEAU_MBB_REQUEST_CONTEXT@@K@Z; MbbNdisIndicatePacketServiceFailure(_MBB_REQUEST_CONTEXT *,ulong)
0x14002f084  test    rsi, rsi
0x14002f087  jz      short loc_14002F09A
0x14002f089  xor     edx, edx; Tag
0x14002f08b  mov     rcx, rsi; P
0x14002f08e  call    cs:__imp_ExFreePoolWithTag
0x14002f095  nop     dword ptr [rax+rax+00h]
0x14002f09a  mov     rcx, [rbp+57h+var_38]
0x14002f09e  xor     rcx, rsp; StackCookie
0x14002f0a1  call    __security_check_cookie
0x14002f0a6  mov     rbx, [rsp+110h+arg_18]
0x14002f0ae  add     rsp, 0E0h
0x14002f0b5  pop     r15
0x14002f0b7  pop     r14
0x14002f0b9  pop     r13
0x14002f0bb  pop     r12
0x14002f0bd  pop     rdi
0x14002f0be  pop     rsi
0x14002f0bf  pop     rbp
0x14002f0c0  retn
```
