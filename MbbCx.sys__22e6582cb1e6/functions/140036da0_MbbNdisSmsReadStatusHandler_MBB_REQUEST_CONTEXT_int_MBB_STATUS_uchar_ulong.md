# MbbNdisSmsReadStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140036da0`
- end: `0x140037211`
- name: `?MbbNdisSmsReadStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `1137`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x140001db8`
- `0x1400034e4`
- `0x1400051ac`
- `0x140005644`
- `0x140036da0`
- `0x14003b20c`
- `0x14003f458`
- `0x14003f7e4`
- `0x14003f994`
- `0x1400411d4`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140036fe2`
- `ntoskrnl!ExAllocatePool2` at `0x140036fe2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400371cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400371cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036e17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036e17`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140036dfc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140036dfc`

## pseudocode

```c
__int64 __fastcall MbbNdisSmsReadStatusHandler(__int64 a1, int a2, unsigned int a3, _DWORD *a4, unsigned int a5)
{
  ULONG v7; // r14d
  PKSPIN_LOCK *v9; // rax
  __int128 *v10; // rsi
  PKSPIN_LOCK v11; // rbx
  KIRQL v12; // al
  int v13; // r13d
  bool v14; // zf
  __int64 v15; // rax
  __int64 *v16; // rdx
  int v17; // ebx
  int v18; // edx
  __int128 *v19; // rax
  int v20; // r9d
  int v21; // edx
  unsigned int v22; // edx
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  __int128 *Pool2; // rax
  __int64 v26; // rdx
  int v27; // r8d
  int v28; // eax
  int v29; // r9d
  __int64 v30; // rdx
  NDIS_HANDLE *v31; // rax
  __int64 result; // rax
  int v33; // [rsp+38h] [rbp-89h]
  struct _NDIS_STATUS_INDICATION v35; // [rsp+50h] [rbp-71h] BYREF
  __int128 v36; // [rsp+C0h] [rbp-1h] BYREF

  v7 = 0;
  memset(&v35, 0, sizeof(v35));
  v9 = *(PKSPIN_LOCK **)(a1 + 48);
  v36 = 0;
  v10 = 0;
  v11 = *v9;
  v12 = KeAcquireSpinLockRaiseToDpc(*v9);
  v13 = *((_DWORD *)v11 + 274);
  *((_BYTE *)v11 + 8) = v12;
  KeReleaseSpinLock(v11, v12);
  v14 = MbbAdapterIsMultimodeCapable(**(PKSPIN_LOCK **)(a1 + 48)) == 0;
  v35.Header = (NDIS_OBJECT_HEADER)7340440;
  v15 = *(_QWORD *)(a1 + 48);
  if ( !v14 )
    v13 = 1;
  v16 = WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids;
  v36 = 0;
  v35.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v15 + 1144LL) + 16LL);
  v35.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v35.RequestId = *(PVOID *)(a1 + 432);
  v35.PortNumber = 0;
  *(_QWORD *)&v35.StatusCode = 1074008079;
  v35.Guid = 0;
  if ( a2 )
  {
    v17 = -1073479677;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v16,
        3,
        157,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
    goto LABEL_6;
  }
  v17 = MbbUtilMbbToWwanStatus(a3);
  if ( v17 )
    goto LABEL_6;
  if ( (unsigned int)MbbUtilValidateMbbSmsReceive(v13, a5, a4, v20) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v21) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        v17 + 3,
        158,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16));
    }
    goto LABEL_15;
  }
  v22 = *a4 != 0 ? 252 : 376;
  v23 = (unsigned int)a4[1];
  v24 = v23 * v22;
  if ( v24 > 0xFFFFFFFF )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_15;
    v29 = 159;
    v33 = *a4 != 0 ? 252 : 376;
    goto LABEL_27;
  }
  v7 = v24 + 16;
  LOBYTE(v23) = 16;
  if ( (unsigned int)v24 >= 0xFFFFFFF0 )
  {
    v7 = -1;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_15:
      v17 = -1073479677;
      goto LABEL_6;
    }
    v29 = 160;
    v33 = v24;
LABEL_27:
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_Ddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      3,
      v29,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v23,
      v33);
    goto LABEL_15;
  }
  Pool2 = (__int128 *)ExAllocatePool2(64, v7, 1683505741);
  v10 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 1048960;
    v28 = MbbUtilMbbToWwanSmsReceive(a4, v26, v13, (_DWORD *)Pool2 + 2);
    if ( !v28 )
      goto LABEL_30;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        3,
        162,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v28);
    }
    goto LABEL_15;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v26) = 2;
    WPP_RECORDER_SF_DDd(WPP_GLOBAL_Control->DeviceExtension, v26, v27, 161);
  }
  v17 = -1073479677;
LABEL_6:
  if ( (unsigned int)MbbUtilMbbToWwanStatus(a3) )
    v17 = MbbUtilMbbToWwanStatus(a3);
  if ( v17 && v17 != 1074004232 )
  {
    LODWORD(v36) = 1048960;
    v35.StatusBufferSize = 16;
    v19 = &v36;
    *((_QWORD *)&v36 + 1) = 3;
    goto LABEL_31;
  }
LABEL_30:
  v19 = v10;
  v35.StatusBufferSize = v7;
LABEL_31:
  v35.StatusBuffer = v19;
  *((_DWORD *)v19 + 1) = v17;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v18) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      3,
      163,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v17);
  }
  v30 = *(_QWORD *)(a1 + 104);
  if ( v30 )
    v31 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                            WdfDriverGlobals,
                            v30,
                            off_14005DF38)
                        + 24);
  else
    v31 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v31, &v35);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  result = 259;
  if ( v17 != 1074004232 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140036da0  mov     [rsp-8+arg_8], rbx
0x140036da5  push    rbp
0x140036da6  push    rsi
0x140036da7  push    rdi
0x140036da8  push    r12
0x140036daa  push    r13
0x140036dac  push    r14
0x140036dae  push    r15
0x140036db0  lea     rbp, [rsp-1Fh]
0x140036db5  sub     rsp, 0E0h
0x140036dbc  mov     rax, cs:__security_cookie
0x140036dc3  xor     rax, rsp
0x140036dc6  mov     [rbp+4Fh+var_40], rax
0x140036dca  mov     r12d, r8d
0x140036dcd  mov     [rsp+110h+var_D0], edx
0x140036dd1  mov     rdi, rcx
0x140036dd4  xor     r14d, r14d
0x140036dd7  xor     edx, edx; Val
0x140036dd9  lea     rcx, [rbp+4Fh+var_C0]; void *
0x140036ddd  mov     r15, r9
0x140036de0  lea     r8d, [r14+70h]; Size
0x140036de4  call    memset
0x140036de9  mov     rax, [rdi+30h]
0x140036ded  xorps   xmm0, xmm0
0x140036df0  movups  [rbp+4Fh+var_50], xmm0
0x140036df4  xor     esi, esi
0x140036df6  mov     rbx, [rax]
0x140036df9  mov     rcx, rbx; SpinLock
0x140036dfc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140036e03  nop     dword ptr [rax+rax+00h]
0x140036e08  mov     r13d, [rbx+448h]
0x140036e0f  mov     rcx, rbx; SpinLock
0x140036e12  mov     dl, al; NewIrql
0x140036e14  mov     [rbx+8], al
0x140036e17  call    cs:__imp_KeReleaseSpinLock
0x140036e1e  nop     dword ptr [rax+rax+00h]
0x140036e23  mov     rcx, [rdi+30h]
0x140036e27  mov     rcx, [rcx]; SpinLock
0x140036e2a  call    ?MbbAdapterIsMultimodeCapable@@YAEPEAU_MINIPORT_ADAPTER_CONTEXT@@@Z; MbbAdapterIsMultimodeCapable(_MINIPORT_ADAPTER_CONTEXT *)
0x140036e2f  test    al, al
0x140036e31  mov     dword ptr [rbp+4Fh+var_C0.Header.Type], 700198h
0x140036e38  mov     rax, [rdi+30h]
0x140036e3c  lea     ecx, [rsi+1]
0x140036e3f  cmovnz  r13d, ecx
0x140036e43  lea     rdx, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140036e4a  xorps   xmm0, xmm0
0x140036e4d  movups  [rbp+4Fh+var_50], xmm0
0x140036e51  mov     rcx, [rax]
0x140036e54  mov     rax, [rcx+478h]
0x140036e5b  mov     rcx, [rax]
0x140036e5e  mov     rax, [rcx+10h]
0x140036e62  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036e69  mov     [rbp+4Fh+var_C0.SourceHandle], rax
0x140036e6d  mov     rax, [rdi+1B8h]
0x140036e74  mov     [rbp+4Fh+var_C0.DestinationHandle], rax
0x140036e78  mov     rax, [rdi+1B0h]
0x140036e7f  mov     [rbp+4Fh+var_C0.RequestId], rax
0x140036e83  mov     eax, [rsp+110h+var_D0]
0x140036e87  mov     [rbp+4Fh+var_C0.PortNumber], esi
0x140036e8a  mov     qword ptr [rbp+4Fh+var_C0.StatusCode], 4004100Fh
0x140036e92  movups  xmmword ptr [rbp+4Fh+var_C0.Guid.Data1], xmm0
0x140036e96  test    eax, eax
0x140036e98  jz      loc_140036F30
0x140036e9e  mov     ebx, 0C0040003h
0x140036ea3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140036eaa  jz      short loc_140036ED8
0x140036eac  mov     rcx, cs:WPP_GLOBAL_Control
0x140036eb3  lea     r8d, [r14+3]
0x140036eb7  mov     [rsp+110h+var_E0], eax
0x140036ebb  mov     r9d, 9Dh
0x140036ec1  mov     eax, [rdi+10h]
0x140036ec4  mov     [rsp+110h+var_E8], eax
0x140036ec8  mov     rcx, [rcx+40h]
0x140036ecc  mov     [rsp+110h+var_F0], rdx
0x140036ed1  mov     dl, 2
0x140036ed3  call    WPP_RECORDER_SF_DD
0x140036ed8  lea     r13, WPP_RECORDER_INITIALIZED
0x140036edf  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140036ee6  mov     ecx, r12d
0x140036ee9  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140036eee  test    eax, eax
0x140036ef0  jz      short loc_140036EFC
0x140036ef2  mov     ecx, r12d
0x140036ef5  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140036efa  mov     ebx, eax
0x140036efc  test    ebx, ebx
0x140036efe  jz      loc_140037131
0x140036f04  cmp     ebx, 40040108h
0x140036f0a  jz      loc_140037131
0x140036f10  mov     ecx, 10h
0x140036f15  mov     dword ptr [rbp+4Fh+var_50], 100180h
0x140036f1c  mov     [rbp+4Fh+var_C0.StatusBufferSize], ecx
0x140036f1f  lea     rax, [rbp+4Fh+var_50]
0x140036f23  mov     qword ptr [rbp+4Fh+var_50+8], 3
0x140036f2b  jmp     loc_140037138
0x140036f30  mov     ecx, r12d
0x140036f33  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140036f38  mov     ebx, eax
0x140036f3a  test    eax, eax
0x140036f3c  jnz     short loc_140036ED8
0x140036f3e  mov     edx, [rbp+4Fh+arg_20]
0x140036f41  mov     r8, r15
0x140036f44  mov     ecx, r13d
0x140036f47  call    ?MbbUtilValidateMbbSmsReceive@@YAHW4_MBB_CELLULAR_CLASS@@KPEAU_MBB_SMS_RECEIVE@@@Z; MbbUtilValidateMbbSmsReceive(_MBB_CELLULAR_CLASS,ulong,_MBB_SMS_RECEIVE *)
0x140036f4c  test    eax, eax
0x140036f4e  jz      short loc_140036F99
0x140036f50  lea     r13, WPP_RECORDER_INITIALIZED
0x140036f57  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140036f5e  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140036f65  jz      short loc_140036F8F
0x140036f67  mov     rcx, cs:WPP_GLOBAL_Control
0x140036f6e  lea     r8d, [rbx+3]
0x140036f72  mov     eax, [rdi+10h]
0x140036f75  mov     r9d, 9Eh
0x140036f7b  mov     [rsp+110h+var_E8], eax
0x140036f7f  mov     dl, 2
0x140036f81  mov     [rsp+110h+var_F0], r15
0x140036f86  mov     rcx, [rcx+40h]
0x140036f8a  call    WPP_RECORDER_SF_d
0x140036f8f  mov     ebx, 0C0040003h
0x140036f94  jmp     loc_140036EE6
0x140036f99  mov     eax, [r15]
0x140036f9c  mov     r8d, 0FFFFFFFFh
0x140036fa2  neg     eax
0x140036fa4  sbb     ecx, ecx
0x140036fa6  and     ecx, 0FFFFFF84h
0x140036fa9  lea     edx, [rcx+178h]
0x140036faf  mov     ecx, [r15+4]
0x140036fb3  mov     eax, edx
0x140036fb5  imul    rax, rcx
0x140036fb9  cmp     rax, r8
0x140036fbc  ja      loc_1400370FC
0x140036fc2  lea     r14d, [rax+10h]
0x140036fc6  mov     ecx, 10h
0x140036fcb  cmp     r14d, ecx
0x140036fce  jb      loc_1400370A7
0x140036fd4  mov     edx, r14d
0x140036fd7  mov     ecx, 40h ; '@'
0x140036fdc  mov     r8d, 6458424Dh
0x140036fe2  call    cs:__imp_ExAllocatePool2
0x140036fe9  nop     dword ptr [rax+rax+00h]
0x140036fee  mov     rsi, rax
0x140036ff1  test    rax, rax
0x140036ff4  jnz     short loc_14003703C
0x140036ff6  lea     r13, WPP_RECORDER_INITIALIZED
0x140036ffd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140037004  jz      short loc_140037032
0x140037006  mov     eax, [r15+4]
0x14003700a  mov     r9d, 0A1h
0x140037010  mov     rcx, cs:WPP_GLOBAL_Control
0x140037017  mov     dl, 2
0x140037019  mov     dword ptr [rsp+110h+var_D8], eax
0x14003701d  mov     eax, [rdi+10h]
0x140037020  mov     [rsp+110h+var_E0], r14d
0x140037025  mov     rcx, [rcx+40h]
0x140037029  mov     [rsp+110h+var_E8], eax
0x14003702d  call    WPP_RECORDER_SF_DDd
0x140037032  mov     ebx, 0C0040003h
0x140037037  jmp     loc_140036EDF
0x14003703c  lea     r9, [rax+8]
0x140037040  mov     dword ptr [rax], 100180h
0x140037046  mov     r8d, r13d
0x140037049  mov     rcx, r15
0x14003704c  call    ?MbbUtilMbbToWwanSmsReceive@@YAHPEAU_MBB_SMS_RECEIVE@@KW4_MBB_CELLULAR_CLASS@@PEAU_WWAN_LIST_HEADER@@@Z; MbbUtilMbbToWwanSmsReceive(_MBB_SMS_RECEIVE *,ulong,_MBB_CELLULAR_CLASS,_WWAN_LIST_HEADER *)
0x140037051  test    eax, eax
0x140037053  jz      loc_140037123
0x140037059  lea     r13, WPP_RECORDER_INITIALIZED
0x140037060  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140037067  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003706e  jz      loc_140036F8F
0x140037074  mov     rcx, cs:WPP_GLOBAL_Control
0x14003707b  mov     r9d, 0A2h
0x140037081  mov     [rsp+110h+var_E0], eax
0x140037085  mov     r8d, 3
0x14003708b  mov     eax, [rdi+10h]
0x14003708e  mov     dl, 2
0x140037090  mov     [rsp+110h+var_E8], eax
0x140037094  mov     rcx, [rcx+40h]
0x140037098  mov     [rsp+110h+var_F0], r15
0x14003709d  call    WPP_RECORDER_SF_DD
0x1400370a2  jmp     loc_140036F8F
0x1400370a7  mov     r14d, r8d
0x1400370aa  lea     r13, WPP_RECORDER_INITIALIZED
0x1400370b1  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400370b8  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400370bf  jz      loc_140036F8F
0x1400370c5  mov     r9d, 0A0h
0x1400370cb  mov     dword ptr [rsp+110h+var_D8], eax
0x1400370cf  mov     eax, [rdi+10h]
0x1400370d2  mov     r8d, 3
0x1400370d8  mov     [rsp+110h+var_E0], ecx
0x1400370dc  mov     dl, 2
0x1400370de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400370e5  mov     [rsp+110h+var_E8], eax
0x1400370e9  mov     [rsp+110h+var_F0], r15
0x1400370ee  mov     rcx, [rcx+40h]
0x1400370f2  call    WPP_RECORDER_SF_Ddd
0x1400370f7  jmp     loc_140036F8F
0x1400370fc  lea     r13, WPP_RECORDER_INITIALIZED
0x140037103  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003710a  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140037111  jz      loc_140036F8F
0x140037117  mov     r9d, 9Fh
0x14003711d  mov     dword ptr [rsp+110h+var_D8], edx
0x140037121  jmp     short loc_1400370CF
0x140037123  lea     r13, WPP_RECORDER_INITIALIZED
0x14003712a  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140037131  mov     rax, rsi
0x140037134  mov     [rbp+4Fh+var_C0.StatusBufferSize], r14d
0x140037138  mov     [rbp+4Fh+var_C0.StatusBuffer], rax
0x14003713c  mov     [rax+4], ebx
0x14003713f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140037146  jz      short loc_140037176
0x140037148  mov     rcx, cs:WPP_GLOBAL_Control
0x14003714f  mov     r9d, 0A3h
0x140037155  mov     eax, [rdi+10h]
0x140037158  mov     r8d, 3
0x14003715e  mov     [rsp+110h+var_E0], ebx
0x140037162  mov     dl, 4
0x140037164  mov     [rsp+110h+var_E8], eax
0x140037168  mov     rcx, [rcx+40h]
0x14003716c  mov     [rsp+110h+var_F0], r15
0x140037171  call    WPP_RECORDER_SF_DD
0x140037176  mov     rdx, [rdi+68h]
0x14003717a  test    rdx, rdx
0x14003717d  jz      short loc_1400371A6
0x14003717f  mov     rax, cs:WdfFunctions_01031
0x140037186  mov     r8, cs:off_14005DF38
0x14003718d  mov     rcx, cs:WdfDriverGlobals
0x140037194  mov     rax, [rax+650h]
0x14003719b  call    _guard_dispatch_icall
0x1400371a0  add     rax, 18h
0x1400371a4  jmp     short loc_1400371B7
0x1400371a6  mov     rax, [rdi+30h]
0x1400371aa  mov     rdx, [rax]
0x1400371ad  mov     rax, [rdx+478h]
0x1400371b4  mov     rax, [rax]
0x1400371b7  lea     rdx, [rbp+4Fh+var_C0]; struct _NDIS_STATUS_INDICATION *
0x1400371bb  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x1400371be  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x1400371c3  test    rsi, rsi
0x1400371c6  jz      short loc_1400371D9
0x1400371c8  xor     edx, edx; Tag
0x1400371ca  mov     rcx, rsi; P
0x1400371cd  call    cs:__imp_ExFreePoolWithTag
0x1400371d4  nop     dword ptr [rax+rax+00h]
0x1400371d9  xor     ecx, ecx
0x1400371db  mov     eax, 103h
0x1400371e0  cmp     ebx, 40040108h
0x1400371e6  cmovnz  eax, ecx
0x1400371e9  mov     rcx, [rbp+4Fh+var_40]
0x1400371ed  xor     rcx, rsp; StackCookie
0x1400371f0  call    __security_check_cookie
0x1400371f5  mov     rbx, [rsp+110h+arg_8]
0x1400371fd  add     rsp, 0E0h
0x140037204  pop     r15
0x140037206  pop     r14
0x140037208  pop     r13
0x14003720a  pop     r12
0x14003720c  pop     rdi
0x14003720d  pop     rsi
0x14003720e  pop     rbp
0x14003720f  retn
```
