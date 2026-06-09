# MbbNdisIndicateReadyInfo(_MBB_REQUEST_CONTEXT *,int)

- ea: `0x14002f228`
- end: `0x14002f754`
- name: `?MbbNdisIndicateReadyInfo@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z`
- size: `1324`
- prototype: `void __fastcall(struct _MBB_REQUEST_CONTEXT *, int, unsigned int, int)`
- caller_count: `5`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400287b0`
- `0x140028cb8`
- `0x1400291c0`
- `0x14002e2b0`
- `0x1400367e0`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140005778`
- `0x140011278`
- `0x140019b6c`
- `0x140019f78`
- `0x14001a168`
- `0x14001b900`
- `0x1400245e0`
- `0x14002f228`
- `0x14002f75c`
- `0x14003b994`
- `0x14003e100`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002f720`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f720`

## pseudocode

```c
void __fastcall MbbNdisIndicateReadyInfo(struct _MBB_REQUEST_CONTEXT *a1, int a2, __int64 a3, int a4)
{
  __int64 v4; // rdi
  int v6; // ecx
  int v7; // eax
  __int128 v8; // xmm0
  ULONG v9; // r14d
  int v10; // edx
  __int64 v11; // r13
  char v12; // al
  int v13; // edx
  __int64 v14; // rax
  __int64 v15; // rdx
  NDIS_HANDLE *v16; // rax
  struct _MBB_REQUEST_MANAGER *v17; // rcx
  struct _MBB_REQUEST_CONTEXT *Request; // r14
  char (near **v19)[32]; // rax
  int v20; // edx
  char (near **CommandString)[32]; // rax
  int v22; // edx
  int v23; // r15d
  char (near **v24)[32]; // rax
  int v25; // edx
  int v26; // r8d
  __int64 v27; // [rsp+38h] [rbp-91h]
  int v28[4]; // [rsp+50h] [rbp-79h] BYREF
  struct _NDIS_STATUS_INDICATION v29; // [rsp+60h] [rbp-69h] BYREF
  __int128 v30; // [rsp+D0h] [rbp+7h] BYREF
  int v31; // [rsp+E0h] [rbp+17h]

  v4 = *((_QWORD *)a1 + 92);
  v28[0] = a2;
  v6 = *((_DWORD *)a1 + 182);
  v31 = 0;
  v30 = 0;
  if ( (v6 & 8) == 0 )
  {
    v6 |= 8u;
    *((_DWORD *)a1 + 182) = v6;
    if ( *((_OWORD *)a1 + 44) == MBB_UUID_BASIC_CONNECT && *((_DWORD *)a1 + 180) == 2 && !*((_BYTE *)a1 + 576) )
    {
      v6 |= 4u;
      *((_DWORD *)a1 + 182) = v6;
    }
  }
  if ( a2 )
    goto LABEL_45;
  if ( v4 )
  {
    if ( !*(_DWORD *)(v4 + 4) )
    {
      if ( (v6 & 1) == 0 )
      {
        v6 |= 1u;
        *((_DWORD *)a1 + 186) = 0;
        *((_DWORD *)a1 + 182) = v6;
      }
      if ( (v6 & 2) == 0 )
      {
        v6 |= 2u;
        *((_BYTE *)a1 + 748) = 0;
        *((_DWORD *)a1 + 182) = v6;
      }
    }
    if ( (v6 & 3) == 3 || (v7 = *(_DWORD *)(v4 + 88), (v7 & 8) == 0) )
    {
      v9 = *((_DWORD *)a1 + 183);
      v28[0] = 0;
      memset(&v29, 0, sizeof(v29));
      v11 = **((_QWORD **)a1 + 6);
      v12 = ~(unsigned __int8)(*(_DWORD *)(v11 + 1088) >> 1);
      v29.Header = (NDIS_OBJECT_HEADER)7340440;
      v28[0] = v12 & 0x10;
      v29.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(v11 + 1144) + 16LL);
      v29.StatusBuffer = v28;
      v29.PortNumber = 0;
      *(_QWORD *)&v29.StatusCode = 1074008103;
      v29.Guid = 0;
      v29.StatusBufferSize = 4;
      *(_OWORD *)&v29.DestinationHandle = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          3,
          21,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *((_DWORD *)a1 + 4));
      }
      MbbUtilNdisMiniportIndicateStatusEx(**(NDIS_HANDLE ***)(v11 + 1144), &v29);
      *(_DWORD *)(v4 + 8) = *((_DWORD *)a1 + 186);
      *(_BYTE *)(v4 + 86) = *((_BYTE *)a1 + 748);
      v14 = *((_QWORD *)a1 + 6);
      v29.Header = (NDIS_OBJECT_HEADER)7340440;
      v29.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v14 + 1144LL) + 16LL);
      v29.DestinationHandle = (NDIS_HANDLE)*((_QWORD *)a1 + 55);
      v29.RequestId = (PVOID)*((_QWORD *)a1 + 54);
      v29.PortNumber = 0;
      *(_QWORD *)&v29.StatusCode = 1074008065;
      v29.Guid = 0;
      v29.StatusBuffer = (PVOID)v4;
      v29.StatusBufferSize = v9;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 4;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          3,
          22,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *((_DWORD *)a1 + 4),
          v9);
      }
      v15 = *((_QWORD *)a1 + 13);
      if ( v15 )
        v16 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031
                                                                                                 + 1616))(
                                WdfDriverGlobals,
                                v15,
                                off_14005DF38)
                            + 24);
      else
        v16 = **(NDIS_HANDLE ***)(**((_QWORD **)a1 + 6) + 1144LL);
      MbbUtilNdisMiniportIndicateStatusEx(v16, &v29);
      goto LABEL_48;
    }
    if ( (v6 & 1) != 0 || (v7 & 8) == 0 )
    {
      if ( (v6 & 2) != 0 || (v7 & 8) == 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_DddDd(WPP_GLOBAL_Control->DeviceExtension, 0, a3, a4);
        goto LABEL_45;
      }
      v8 = MBB_UUID_SMS;
      v31 = 1;
      goto LABEL_36;
    }
    v31 = 22;
  }
  else
  {
    if ( (v6 & 3) == 0 )
    {
      if ( (v6 & 4) == 0 )
        return;
      goto LABEL_45;
    }
    v31 = 2;
  }
  v8 = MBB_UUID_BASIC_CONNECT;
LABEL_36:
  v17 = (struct _MBB_REQUEST_MANAGER *)*((_QWORD *)a1 + 6);
  v30 = v8;
  Request = MbbReqMgrCreateRequest(v17, 0, a3, v28, 1u);
  if ( Request )
  {
    *((_QWORD *)Request + 10) = MbbNdisGetOidHandlerByCommand((struct _MBB_COMMAND *)&v30);
    *((_QWORD *)Request + 54) = *((_QWORD *)a1 + 54);
    *((_QWORD *)Request + 55) = *((_QWORD *)a1 + 55);
    *(_OWORD *)((char *)Request + 728) = *(_OWORD *)((char *)a1 + 728);
    *((_QWORD *)Request + 93) = *((_QWORD *)a1 + 93);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      CommandString = MbbUtilGetCommandString((struct _MBB_COMMAND *)&v30);
      WPP_RECORDER_SF_DDs(
        WPP_GLOBAL_Control->DeviceExtension,
        v22,
        3,
        25,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4),
        *((_DWORD *)Request + 4),
        (__int64)CommandString);
    }
    v23 = MbbReqMgrDispatchRequest(
            (union _LARGE_INTEGER *)Request,
            (*(_DWORD *)(*((_QWORD *)Request + 10) + 4LL) & 4) != 0,
            (int (*)(void *, struct _MBB_REQUEST_CONTEXT *))MbbUtilInternalCIDQuery,
            (void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int))MbbUtilInternalCIDCompletion,
            (void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int))MbbUtilInternalCIDResponse);
    if ( v23 == 259 )
      return;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v24 = MbbUtilGetCommandString((struct _MBB_COMMAND *)&v30);
      LODWORD(v27) = v23;
      WPP_RECORDER_SF_Dsd(
        WPP_GLOBAL_Control->DeviceExtension,
        v25,
        v26,
        26,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)Request + 4),
        (__int64)v24,
        v27);
    }
    MbbReqMgrDerefRequest(Request);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v19 = MbbUtilGetCommandString((struct _MBB_COMMAND *)&v30);
    LOBYTE(v20) = 2;
    WPP_RECORDER_SF_Ds(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      3,
      24,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *((_DWORD *)a1 + 4),
      (__int64)v19);
  }
LABEL_45:
  if ( (*((_DWORD *)a1 + 182) & 4) != 0 )
    MbbNdisIndicateReadyInfoFailure(a1);
  if ( v4 )
LABEL_48:
    ExFreePoolWithTag((PVOID)v4, 0);
}

```

## disassembly

```asm
0x14002f228  mov     [rsp-8+arg_10], rbx
0x14002f22d  push    rbp
0x14002f22e  push    rsi
0x14002f22f  push    rdi
0x14002f230  push    r12
0x14002f232  push    r13
0x14002f234  push    r14
0x14002f236  push    r15
0x14002f238  lea     rbp, [rsp-27h]
0x14002f23d  sub     rsp, 0F0h
0x14002f244  mov     rax, cs:__security_cookie
0x14002f24b  xor     rax, rsp
0x14002f24e  mov     [rbp+57h+var_38], rax
0x14002f252  mov     rdi, [rcx+2E0h]
0x14002f259  xor     eax, eax
0x14002f25b  mov     rbx, rcx
0x14002f25e  mov     [rbp+57h+var_D0], edx
0x14002f261  mov     ecx, [rcx+2D8h]
0x14002f267  xorps   xmm0, xmm0
0x14002f26a  mov     [rbp+57h+var_40], eax
0x14002f26d  lea     r13d, [rax+2]
0x14002f271  movups  [rbp+57h+var_50], xmm0
0x14002f275  test    cl, 8
0x14002f278  jnz     short loc_14002F2BE
0x14002f27a  or      ecx, 8
0x14002f27d  mov     [rbx+2D8h], ecx
0x14002f283  mov     rax, [rbx+2C0h]
0x14002f28a  cmp     rax, qword ptr cs:MBB_UUID_BASIC_CONNECT
0x14002f291  jnz     short loc_14002F2BE
0x14002f293  mov     rax, [rbx+2C8h]
0x14002f29a  cmp     rax, qword ptr cs:MBB_UUID_BASIC_CONNECT+8
0x14002f2a1  jnz     short loc_14002F2BE
0x14002f2a3  cmp     [rbx+2D0h], r13d
0x14002f2aa  jnz     short loc_14002F2BE
0x14002f2ac  cmp     byte ptr [rbx+240h], 0
0x14002f2b3  jnz     short loc_14002F2BE
0x14002f2b5  or      ecx, 4
0x14002f2b8  mov     [rbx+2D8h], ecx
0x14002f2be  test    edx, edx
0x14002f2c0  jnz     loc_14002F704
0x14002f2c6  lea     esi, [rdx+1]
0x14002f2c9  test    rdi, rdi
0x14002f2cc  jz      loc_14002F54F
0x14002f2d2  cmp     [rdi+4], edx
0x14002f2d5  jnz     short loc_14002F302
0x14002f2d7  mov     eax, ecx
0x14002f2d9  and     eax, esi
0x14002f2db  test    al, al
0x14002f2dd  jnz     short loc_14002F2ED
0x14002f2df  or      ecx, esi
0x14002f2e1  mov     [rbx+2E8h], edx
0x14002f2e7  mov     [rbx+2D8h], ecx
0x14002f2ed  test    r13b, cl
0x14002f2f0  jnz     short loc_14002F302
0x14002f2f2  or      ecx, r13d
0x14002f2f5  mov     byte ptr [rbx+2ECh], 0
0x14002f2fc  mov     [rbx+2D8h], ecx
0x14002f302  mov     r15d, 3
0x14002f308  mov     eax, ecx
0x14002f30a  and     eax, r15d
0x14002f30d  cmp     al, r15b
0x14002f310  jz      loc_14002F396
0x14002f316  mov     eax, [rdi+58h]
0x14002f319  test    al, 8
0x14002f31b  jz      short loc_14002F396
0x14002f31d  test    sil, cl
0x14002f320  jnz     short loc_14002F332
0x14002f322  test    al, 8
0x14002f324  jz      short loc_14002F332
0x14002f326  mov     [rbp+57h+var_40], 16h
0x14002f32d  jmp     loc_14002F56D
0x14002f332  test    r13b, cl
0x14002f335  jnz     short loc_14002F34A
0x14002f337  test    al, 8
0x14002f339  jz      short loc_14002F34A
0x14002f33b  movups  xmm0, cs:MBB_UUID_SMS
0x14002f342  mov     [rbp+57h+var_40], esi
0x14002f345  jmp     loc_14002F574
0x14002f34a  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002f351  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002f358  jz      loc_14002F704
0x14002f35e  mov     eax, [rdi+8]
0x14002f361  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f368  mov     [rsp+120h+var_D8], eax
0x14002f36c  mov     eax, [rdi+58h]
0x14002f36f  mov     [rsp+120h+var_E0], eax
0x14002f373  mov     eax, [rdi+5Ch]
0x14002f376  mov     rcx, [rcx+40h]
0x14002f37a  mov     dword ptr [rsp+120h+var_E8], eax
0x14002f37e  mov     eax, [rdi+4]
0x14002f381  mov     dword ptr [rsp+120h+var_F0], eax
0x14002f385  mov     eax, [rbx+10h]
0x14002f388  mov     [rsp+120h+var_F8], eax
0x14002f38c  call    WPP_RECORDER_SF_DddDd
0x14002f391  jmp     loc_14002F704
0x14002f396  mov     r14d, [rbx+2DCh]
0x14002f39d  lea     rcx, [rbp+57h+var_C0]; void *
0x14002f3a1  xor     edx, edx; Val
0x14002f3a3  mov     [rbp+57h+var_D0], 0
0x14002f3aa  lea     r8d, [rdx+70h]; Size
0x14002f3ae  call    memset
0x14002f3b3  mov     rax, [rbx+30h]
0x14002f3b7  xorps   xmm0, xmm0
0x14002f3ba  xorps   xmm1, xmm1
0x14002f3bd  mov     r13, [rax]
0x14002f3c0  mov     eax, [r13+440h]
0x14002f3c7  shr     eax, 1
0x14002f3c9  not     eax
0x14002f3cb  mov     dword ptr [rbp+57h+var_C0.Header.Type], 700198h
0x14002f3d2  and     eax, 10h
0x14002f3d5  mov     [rbp+57h+var_D0], eax
0x14002f3d8  mov     rax, [r13+478h]
0x14002f3df  mov     rcx, [rax]
0x14002f3e2  mov     rax, [rcx+10h]
0x14002f3e6  mov     [rbp+57h+var_C0.SourceHandle], rax
0x14002f3ea  lea     rax, [rbp+57h+var_D0]
0x14002f3ee  mov     [rbp+57h+var_C0.StatusBuffer], rax
0x14002f3f2  mov     [rbp+57h+var_C0.PortNumber], 0
0x14002f3f9  mov     qword ptr [rbp+57h+var_C0.StatusCode], 40041027h
0x14002f401  movups  xmmword ptr [rbp+57h+var_C0.Guid.Data1], xmm0
0x14002f405  mov     [rbp+57h+var_C0.StatusBufferSize], 4
0x14002f40c  movdqa  xmmword ptr [rbp+57h+var_C0.DestinationHandle], xmm1
0x14002f411  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002f418  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002f41f  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002f426  jz      short loc_14002F44F
0x14002f428  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f42f  mov     r9d, 15h
0x14002f435  mov     eax, [rbx+10h]
0x14002f438  mov     r8d, r15d
0x14002f43b  mov     [rsp+120h+var_F8], eax
0x14002f43f  mov     dl, 4
0x14002f441  mov     [rsp+120h+var_100], r12
0x14002f446  mov     rcx, [rcx+40h]
0x14002f44a  call    WPP_RECORDER_SF_d
0x14002f44f  mov     rcx, [r13+478h]
0x14002f456  lea     rdx, [rbp+57h+var_C0]; struct _NDIS_STATUS_INDICATION *
0x14002f45a  mov     rcx, [rcx]; struct _MINIPORT_INTERFACE_CONTEXT *
0x14002f45d  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14002f462  mov     eax, [rbx+2E8h]
0x14002f468  xorps   xmm0, xmm0
0x14002f46b  mov     [rdi+8], eax
0x14002f46e  mov     al, [rbx+2ECh]
0x14002f474  mov     [rdi+56h], al
0x14002f477  mov     rax, [rbx+30h]
0x14002f47b  mov     dword ptr [rbp+57h+var_C0.Header.Type], 700198h
0x14002f482  mov     rcx, [rax]
0x14002f485  mov     rax, [rcx+478h]
0x14002f48c  mov     rcx, [rax]
0x14002f48f  mov     rax, [rcx+10h]
0x14002f493  mov     [rbp+57h+var_C0.SourceHandle], rax
0x14002f497  mov     rax, [rbx+1B8h]
0x14002f49e  mov     [rbp+57h+var_C0.DestinationHandle], rax
0x14002f4a2  mov     rax, [rbx+1B0h]
0x14002f4a9  mov     [rbp+57h+var_C0.RequestId], rax
0x14002f4ad  mov     [rbp+57h+var_C0.PortNumber], 0
0x14002f4b4  mov     qword ptr [rbp+57h+var_C0.StatusCode], 40041001h
0x14002f4bc  movups  xmmword ptr [rbp+57h+var_C0.Guid.Data1], xmm0
0x14002f4c0  mov     [rbp+57h+var_C0.StatusBuffer], rdi
0x14002f4c4  mov     [rbp+57h+var_C0.StatusBufferSize], r14d
0x14002f4c8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002f4cf  jz      short loc_14002F4FD
0x14002f4d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f4d8  mov     r9d, 16h
0x14002f4de  mov     eax, [rbx+10h]
0x14002f4e1  mov     r8d, r15d
0x14002f4e4  mov     dword ptr [rsp+120h+var_F0], r14d
0x14002f4e9  mov     dl, 4
0x14002f4eb  mov     [rsp+120h+var_F8], eax
0x14002f4ef  mov     rcx, [rcx+40h]
0x14002f4f3  mov     [rsp+120h+var_100], r12
0x14002f4f8  call    WPP_RECORDER_SF_DD
0x14002f4fd  mov     rdx, [rbx+68h]
0x14002f501  test    rdx, rdx
0x14002f504  jz      short loc_14002F52D
0x14002f506  mov     rax, cs:WdfFunctions_01031
0x14002f50d  mov     r8, cs:off_14005DF38
0x14002f514  mov     rcx, cs:WdfDriverGlobals
0x14002f51b  mov     rax, [rax+650h]
0x14002f522  call    _guard_dispatch_icall
0x14002f527  add     rax, 18h
0x14002f52b  jmp     short loc_14002F53E
0x14002f52d  mov     rax, [rbx+30h]
0x14002f531  mov     rcx, [rax]
0x14002f534  mov     rax, [rcx+478h]
0x14002f53b  mov     rax, [rax]
0x14002f53e  lea     rdx, [rbp+57h+var_C0]; struct _NDIS_STATUS_INDICATION *
0x14002f542  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x14002f545  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14002f54a  jmp     loc_14002F71B
0x14002f54f  mov     r15d, 3
0x14002f555  test    r15d, ecx
0x14002f558  jnz     short loc_14002F569
0x14002f55a  bt      ecx, 2
0x14002f55e  jnb     loc_14002F72C
0x14002f564  jmp     loc_14002F704
0x14002f569  mov     [rbp+57h+var_40], r13d
0x14002f56d  movups  xmm0, cs:MBB_UUID_BASIC_CONNECT
0x14002f574  mov     rcx, [rbx+30h]; struct _MBB_REQUEST_MANAGER *
0x14002f578  lea     r9, [rbp+57h+var_D0]; int *
0x14002f57c  xor     edx, edx; struct _NDIS_OID_REQUEST *
0x14002f57e  mov     byte ptr [rsp+120h+var_100], sil; unsigned __int8
0x14002f583  movdqu  [rbp+57h+var_50], xmm0
0x14002f588  call    ?MbbReqMgrCreateRequest@@YAPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@PEAU_NDIS_OID_REQUEST@@KPEAHE@Z; MbbReqMgrCreateRequest(_MBB_REQUEST_MANAGER *,_NDIS_OID_REQUEST *,ulong,int *,uchar)
0x14002f58d  mov     r14, rax
0x14002f590  test    rax, rax
0x14002f593  jnz     short loc_14002F5E9
0x14002f595  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002f59c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002f5a3  jz      loc_14002F704
0x14002f5a9  lea     rcx, [rbp+57h+var_50]; Source1
0x14002f5ad  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14002f5b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f5b9  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002f5c0  mov     [rsp+120h+var_F0], rax
0x14002f5c5  lea     r9d, [r14+18h]
0x14002f5c9  mov     eax, [rbx+10h]
0x14002f5cc  mov     r8d, r15d
0x14002f5cf  mov     [rsp+120h+var_F8], eax
0x14002f5d3  mov     dl, r13b
0x14002f5d6  mov     rcx, [rcx+40h]
0x14002f5da  mov     [rsp+120h+var_100], r12
0x14002f5df  call    WPP_RECORDER_SF_Ds
0x14002f5e4  jmp     loc_14002F704
0x14002f5e9  lea     rcx, [rbp+57h+var_50]; struct _MBB_COMMAND *
0x14002f5ed  call    ?MbbNdisGetOidHandlerByCommand@@YAPEAU_MBB_OID_HANDLER_ENTRY@@PEAU_MBB_COMMAND@@@Z; MbbNdisGetOidHandlerByCommand(_MBB_COMMAND *)
0x14002f5f2  mov     [r14+50h], rax
0x14002f5f6  mov     rax, [rbx+1B0h]
0x14002f5fd  mov     [r14+1B0h], rax
0x14002f604  mov     rax, [rbx+1B8h]
0x14002f60b  mov     [r14+1B8h], rax
0x14002f612  movups  xmm0, xmmword ptr [rbx+2D8h]
0x14002f619  movups  xmmword ptr [r14+2D8h], xmm0
0x14002f621  movsd   xmm1, qword ptr [rbx+2E8h]
0x14002f629  movsd   qword ptr [r14+2E8h], xmm1
0x14002f632  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002f639  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002f640  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002f647  jz      short loc_14002F684
0x14002f649  lea     rcx, [rbp+57h+var_50]; Source1
0x14002f64d  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14002f652  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f659  mov     r9d, 19h
0x14002f65f  mov     [rsp+120h+var_E8], rax
0x14002f664  mov     r8d, r15d
0x14002f667  mov     eax, [r14+10h]
0x14002f66b  mov     dword ptr [rsp+120h+var_F0], eax
0x14002f66f  mov     eax, [rbx+10h]
0x14002f672  mov     rcx, [rcx+40h]
0x14002f676  mov     [rsp+120h+var_F8], eax
0x14002f67a  mov     [rsp+120h+var_100], r12
0x14002f67f  call    WPP_RECORDER_SF_DDs
0x14002f684  mov     rax, [r14+50h]
0x14002f688  lea     r9, ?MbbUtilInternalCIDCompletion@@YAXPEAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; void (*)(void *, struct _MBB_REQUEST_CONTEXT *, int)
0x14002f68f  lea     r8, ?MbbUtilInternalCIDQuery@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z; int (*)(void *, struct _MBB_REQUEST_CONTEXT *)
0x14002f696  mov     rcx, r14; struct _MBB_REQUEST_CONTEXT *
0x14002f699  mov     edx, [rax+4]
0x14002f69c  lea     rax, ?MbbUtilInternalCIDResponse@@YAXPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbUtilInternalCIDResponse(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x14002f6a3  shr     edx, 2
0x14002f6a6  and     dl, 1; unsigned __int8
0x14002f6a9  mov     [rsp+120h+var_100], rax; void (__high *)(struct _MBB_REQUEST_CONTEXT *, int, enum _MBB_STATUS, unsigned __int8 *, unsigned int)
0x14002f6ae  call    ?MbbReqMgrDispatchRequest@@YAHPEAU_MBB_REQUEST_CONTEXT@@EP6AHPEAX0@ZP6AX10H@ZP6AX0HW4_MBB_STATUS@@PEAEK@Z@Z; MbbReqMgrDispatchRequest(_MBB_REQUEST_CONTEXT *,uchar,int (*)(void *,_MBB_REQUEST_CONTEXT *),void (*)(void *,_MBB_REQUEST_CONTEXT *,int),void (*)(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong))
0x14002f6b3  mov     r15d, eax
0x14002f6b6  cmp     eax, 103h
0x14002f6bb  jz      short loc_14002F72C
0x14002f6bd  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002f6c4  jz      short loc_14002F6FC
0x14002f6c6  lea     rcx, [rbp+57h+var_50]; Source1
0x14002f6ca  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14002f6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f6d6  mov     r9d, 1Ah
0x14002f6dc  mov     dword ptr [rsp+120h+var_E8], r15d
0x14002f6e1  mov     [rsp+120h+var_F0], rax
0x14002f6e6  mov     eax, [r14+10h]
0x14002f6ea  mov     rcx, [rcx+40h]
0x14002f6ee  mov     [rsp+120h+var_F8], eax
0x14002f6f2  mov     [rsp+120h+var_100], r12
0x14002f6f7  call    WPP_RECORDER_SF_Dsd
0x14002f6fc  mov     rcx, r14; struct _MBB_REQUEST_CONTEXT *
0x14002f6ff  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x14002f704  mov     eax, [rbx+2D8h]
0x14002f70a  test    al, 4
0x14002f70c  jz      short loc_14002F716
0x14002f70e  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x14002f711  call    ?MbbNdisIndicateReadyInfoFailure@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbNdisIndicateReadyInfoFailure(_MBB_REQUEST_CONTEXT *)
0x14002f716  test    rdi, rdi
0x14002f719  jz      short loc_14002F72C
0x14002f71b  xor     edx, edx; Tag
0x14002f71d  mov     rcx, rdi; P
0x14002f720  call    cs:__imp_ExFreePoolWithTag
0x14002f727  nop     dword ptr [rax+rax+00h]
0x14002f72c  mov     rcx, [rbp+57h+var_38]
0x14002f730  xor     rcx, rsp; StackCookie
0x14002f733  call    __security_check_cookie
0x14002f738  mov     rbx, [rsp+120h+arg_10]
0x14002f740  add     rsp, 0F0h
0x14002f747  pop     r15
0x14002f749  pop     r14
0x14002f74b  pop     r13
0x14002f74d  pop     r12
  ... truncated ...
```
