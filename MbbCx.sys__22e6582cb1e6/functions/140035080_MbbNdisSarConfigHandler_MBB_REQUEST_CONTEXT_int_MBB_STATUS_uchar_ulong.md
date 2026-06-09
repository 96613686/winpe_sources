# MbbNdisSarConfigHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140035080`
- end: `0x14003551c`
- name: `?MbbNdisSarConfigHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `1180`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callees

- `0x1400051ac`
- `0x140005644`
- `0x140017fb4`
- `0x140035080`
- `0x14003b3f4`
- `0x14003b670`
- `0x14003bc04`
- `0x14003df70`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140035282`
- `ntoskrnl!ExAllocatePool2` at `0x140035282`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400354ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400354ed`

## pseudocode

```c
__int64 __fastcall MbbNdisSarConfigHandler(__int64 a1, int a2, unsigned int a3, _DWORD *a4, unsigned int a5)
{
  int v9; // edx
  __int64 v10; // rax
  _DWORD *v11; // r15
  int v12; // eax
  int v13; // r8d
  int v14; // r9d
  unsigned int v15; // edi
  unsigned __int64 v16; // rax
  ULONG v17; // ebx
  __int64 v18; // r12
  unsigned int v19; // r12d
  _DWORD *Pool2; // rax
  __int64 v21; // r8
  void *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rdx
  NDIS_HANDLE *v26; // rax
  int v28; // [rsp+20h] [rbp-E0h]
  struct _NDIS_STATUS_INDICATION v29; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v30[8]; // [rsp+E0h] [rbp-20h] BYREF

  memset(&v29.Header + 1, 0, 0x6Cu);
  v10 = *(_QWORD *)(a1 + 48);
  v29.Header = (NDIS_OBJECT_HEADER)7340440;
  memset(v30, 0, 28);
  v11 = 0;
  v29.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v10 + 1144LL) + 16LL);
  v29.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v29.RequestId = *(PVOID *)(a1 + 432);
  v29.PortNumber = 0;
  *(_QWORD *)&v29.StatusCode = 1074008122;
  v29.Guid = 0;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        333,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
    goto LABEL_24;
  }
  v12 = MbbUtilMbbToWwanStatus(a3);
  a2 = v12;
  if ( v12 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_DDL(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v13,
        334,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v12,
        a3);
    }
    goto LABEL_24;
  }
  if ( !a4 || a5 < 0x18 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        335,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a5,
        16);
    }
    goto LABEL_23;
  }
  v15 = a4[3];
  v16 = 8LL * v15;
  v9 = -1;
  if ( v16 > 0xFFFFFFFF
    || (v17 = v16 + 28, (int)v16 + 28 < (unsigned int)v16)
    || (int)v16 + 16 < (unsigned int)v16
    || a5 < (int)v16 + 16 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_DdId(WPP_GLOBAL_Control->DeviceExtension, -1, v13, 336);
LABEL_23:
    a2 = -1073676267;
    goto LABEL_24;
  }
  v18 = 0;
  if ( v15 )
  {
    while ( !(unsigned int)MbbIsVariableFieldValid(a5, a4[2 * v18 + 4], a4[2 * v18 + 5], 2u, 4u, 0) )
    {
      v18 = (unsigned int)(v18 + 1);
      if ( (unsigned int)v18 >= v15 )
      {
        v9 = -1;
        goto LABEL_17;
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Dddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v13,
        337,
        v28,
        *(_DWORD *)(a1 + 16),
        v18,
        a4[2 * v18 + 4],
        a5,
        a4[2 * v18 + 5],
        8);
    goto LABEL_23;
  }
LABEL_17:
  v19 = 8 * v15 + a4[4];
  if ( v19 < 8 * v15 )
  {
    LOBYTE(v19) = -1;
  }
  else if ( a5 >= v19 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(64, v17, 1683505741);
    v11 = Pool2;
    if ( Pool2 )
    {
      v21 = (unsigned int)a4[3];
      v22 = Pool2 + 7;
      v23 = (unsigned int)a4[4];
      *(_QWORD *)Pool2 = 1835392;
      v29.StatusBuffer = Pool2;
      Pool2[2] = *a4;
      Pool2[3] = a4[1];
      v24 = a4[2];
      v11[6] = v21;
      v11[4] = v24;
      v29.StatusBufferSize = v17;
      v11[5] = 20;
      memmove(v22, (char *)a4 + v23, 8 * v21);
      goto LABEL_26;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_DIddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      v13,
      v14,
      v28,
      *(_DWORD *)(a1 + 16),
      v17,
      a4[3],
      v19,
      a5);
  a2 = -1073741670;
LABEL_24:
  v30[0] = 1835392;
  v29.StatusBufferSize = 28;
  v29.StatusBuffer = v30;
  v30[1] = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      3,
      339,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      a2);
  }
LABEL_26:
  v25 = *(_QWORD *)(a1 + 104);
  if ( v25 )
    v26 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                            WdfDriverGlobals,
                            v25,
                            off_14005DF38)
                        + 24);
  else
    v26 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v26, &v29);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  return 0;
}

```

## disassembly

```asm
0x140035080  push    rbp
0x140035082  push    rbx
0x140035083  push    rsi
0x140035084  push    rdi
0x140035085  push    r12
0x140035087  push    r13
0x140035089  push    r14
0x14003508b  push    r15
0x14003508d  lea     rbp, [rsp-18h]
0x140035092  sub     rsp, 118h
0x140035099  mov     rax, cs:__security_cookie
0x1400350a0  xor     rax, rsp
0x1400350a3  mov     [rbp+50h+var_50], rax
0x1400350a7  mov     ebx, edx
0x1400350a9  mov     r12d, r8d
0x1400350ac  xor     edx, edx; Val
0x1400350ae  mov     rsi, rcx
0x1400350b1  lea     rcx, [rsp+150h+var_E0+4]; void *
0x1400350b6  mov     r14, r9
0x1400350b9  lea     r8d, [rdx+6Ch]; Size
0x1400350bd  call    memset
0x1400350c2  mov     rax, [rsi+30h]
0x1400350c6  lea     r13, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400350cd  mov     dword ptr [rsp+150h+var_E0.Header.Type], 700198h
0x1400350d5  xorps   xmm0, xmm0
0x1400350d8  movups  xmmword ptr [rbp+50h+var_70], xmm0
0x1400350dc  xor     r15d, r15d
0x1400350df  movups  xmmword ptr [rbp+50h+var_70+0Ch], xmm0
0x1400350e3  mov     rcx, [rax]
0x1400350e6  mov     rax, [rcx+478h]
0x1400350ed  mov     rcx, [rax]
0x1400350f0  mov     rax, [rcx+10h]
0x1400350f4  mov     [rsp+150h+var_E0.SourceHandle], rax
0x1400350f9  mov     rax, [rsi+1B8h]
0x140035100  mov     [rbp+50h+var_E0.DestinationHandle], rax
0x140035104  mov     rax, [rsi+1B0h]
0x14003510b  mov     [rbp+50h+var_E0.RequestId], rax
0x14003510f  mov     [rbp+50h+var_E0.PortNumber], r15d
0x140035113  mov     qword ptr [rbp+50h+var_E0.StatusCode], 4004103Ah
0x14003511b  movups  xmmword ptr [rbp+50h+var_E0.Guid.Data1], xmm0
0x14003511f  test    ebx, ebx
0x140035121  jz      short loc_140035168
0x140035123  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003512a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140035131  jz      loc_140035345
0x140035137  mov     rcx, cs:WPP_GLOBAL_Control
0x14003513e  lea     r8d, [r15+3]
0x140035142  mov     eax, [rsi+10h]
0x140035145  mov     r9d, 14Dh
0x14003514b  mov     dword ptr [rsp+150h+var_120], ebx
0x14003514f  mov     dl, 2
0x140035151  mov     [rsp+150h+var_128], eax
0x140035155  mov     rcx, [rcx+40h]
0x140035159  mov     qword ptr [rsp+150h+var_130], r13
0x14003515e  call    WPP_RECORDER_SF_DD
0x140035163  jmp     loc_140035345
0x140035168  mov     ecx, r12d
0x14003516b  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140035170  mov     ebx, eax
0x140035172  test    eax, eax
0x140035174  jz      short loc_1400351BC
0x140035176  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003517d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140035184  jz      loc_140035345
0x14003518a  mov     rcx, cs:WPP_GLOBAL_Control
0x140035191  mov     r9d, 14Eh
0x140035197  mov     dword ptr [rsp+150h+var_118], r12d
0x14003519c  mov     dl, 2
0x14003519e  mov     dword ptr [rsp+150h+var_120], eax
0x1400351a2  mov     eax, [rsi+10h]
0x1400351a5  mov     rcx, [rcx+40h]
0x1400351a9  mov     [rsp+150h+var_128], eax
0x1400351ad  mov     qword ptr [rsp+150h+var_130], r13
0x1400351b2  call    WPP_RECORDER_SF_DDL
0x1400351b7  jmp     loc_140035345
0x1400351bc  mov     r13d, [rbp+50h+arg_20]
0x1400351c3  test    r14, r14
0x1400351c6  jz      loc_14003546E
0x1400351cc  cmp     r13d, 18h
0x1400351d0  jb      loc_14003546E
0x1400351d6  mov     edi, [r14+0Ch]
0x1400351da  xor     ecx, ecx
0x1400351dc  mov     eax, edi
0x1400351de  mov     [rsp+150h+var_F0], rdi
0x1400351e3  shl     rax, 3
0x1400351e7  mov     edx, 0FFFFFFFFh
0x1400351ec  cmp     rax, rdx
0x1400351ef  ja      loc_140035423
0x1400351f5  lea     ebx, [rax+1Ch]
0x1400351f8  cmp     ebx, eax
0x1400351fa  jb      loc_140035423
0x140035200  lea     ecx, [rax+10h]
0x140035203  cmp     ecx, eax
0x140035205  jb      loc_140035421
0x14003520b  cmp     r13d, ecx
0x14003520e  jb      loc_140035423
0x140035214  xor     r12d, r12d
0x140035217  test    edi, edi
0x140035219  jz      short loc_140035255
0x14003521b  mov     r8d, [r14+r12*8+14h]; unsigned int
0x140035220  mov     r9d, 2; unsigned int
0x140035226  mov     edx, [r14+r12*8+10h]; unsigned int
0x14003522b  mov     ecx, r13d; unsigned int
0x14003522e  mov     [rsp+150h+var_128], r15d; int
0x140035233  mov     [rsp+150h+var_130], 4; unsigned int
0x14003523b  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x140035240  test    eax, eax
0x140035242  jnz     loc_1400352E8
0x140035248  inc     r12d
0x14003524b  cmp     r12d, edi
0x14003524e  jb      short loc_14003521B
0x140035250  mov     edx, 0FFFFFFFFh
0x140035255  mov     r12d, [r14+10h]
0x140035259  lea     ecx, ds:0[rdi*8]
0x140035260  add     r12d, ecx
0x140035263  cmp     r12d, ecx
0x140035266  jb      loc_1400353CD
0x14003526c  cmp     r13d, r12d
0x14003526f  jb      loc_1400353D0
0x140035275  mov     edx, ebx
0x140035277  mov     ecx, 40h ; '@'
0x14003527c  mov     r8d, 6458424Dh
0x140035282  call    cs:__imp_ExAllocatePool2
0x140035289  nop     dword ptr [rax+rax+00h]
0x14003528e  mov     r15, rax
0x140035291  test    rax, rax
0x140035294  jz      loc_1400353D0
0x14003529a  mov     r8d, [r14+0Ch]
0x14003529e  lea     rcx, [r15+1Ch]; void *
0x1400352a2  mov     edx, [r14+10h]
0x1400352a6  mov     qword ptr [rax], 1C0180h
0x1400352ad  add     rdx, r14; Src
0x1400352b0  mov     [rbp+50h+var_E0.StatusBuffer], rax
0x1400352b4  mov     eax, [r14]
0x1400352b7  mov     [r15+8], eax
0x1400352bb  mov     eax, [r14+4]
0x1400352bf  mov     [r15+0Ch], eax
0x1400352c3  mov     eax, [r14+8]
0x1400352c7  mov     [r15+18h], r8d
0x1400352cb  shl     r8, 3; Size
0x1400352cf  mov     [r15+10h], eax
0x1400352d3  mov     [rbp+50h+var_E0.StatusBufferSize], ebx
0x1400352d6  mov     dword ptr [r15+14h], 14h
0x1400352de  call    memmove
0x1400352e3  jmp     loc_140035396
0x1400352e8  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400352ef  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400352f6  jz      short loc_140035339
0x1400352f8  mov     eax, [r14+r12*8+14h]
0x1400352fd  mov     r9d, 151h
0x140035303  mov     rcx, cs:WPP_GLOBAL_Control
0x14003530a  mov     [rsp+150h+var_100], 8
0x140035312  mov     [rsp+150h+var_108], eax
0x140035316  mov     eax, [r14+r12*8+10h]
0x14003531b  mov     rcx, [rcx+40h]
0x14003531f  mov     [rsp+150h+var_110], r13d
0x140035324  mov     dword ptr [rsp+150h+var_118], eax
0x140035328  mov     eax, [rsi+10h]
0x14003532b  mov     dword ptr [rsp+150h+var_120], r12d
0x140035330  mov     [rsp+150h+var_128], eax
0x140035334  call    WPP_RECORDER_SF_Dddddd
0x140035339  lea     r13, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140035340  mov     ebx, 0C0010015h
0x140035345  mov     eax, 1Ch
0x14003534a  mov     [rbp+50h+var_70], 1C0180h
0x140035351  lea     rcx, [rbp+50h+var_70]
0x140035355  mov     [rbp+50h+var_E0.StatusBufferSize], eax
0x140035358  mov     [rbp+50h+var_E0.StatusBuffer], rcx
0x14003535c  mov     [rbp+50h+var_70+4], ebx
0x14003535f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140035366  jz      short loc_140035396
0x140035368  mov     rcx, cs:WPP_GLOBAL_Control
0x14003536f  mov     r9d, 153h
0x140035375  mov     eax, [rsi+10h]
0x140035378  mov     r8d, 3
0x14003537e  mov     dword ptr [rsp+150h+var_120], ebx
0x140035382  mov     dl, 4
0x140035384  mov     [rsp+150h+var_128], eax
0x140035388  mov     rcx, [rcx+40h]
0x14003538c  mov     qword ptr [rsp+150h+var_130], r13
0x140035391  call    WPP_RECORDER_SF_DD
0x140035396  mov     rdx, [rsi+68h]
0x14003539a  test    rdx, rdx
0x14003539d  jz      loc_1400354C5
0x1400353a3  mov     rax, cs:WdfFunctions_01031
0x1400353aa  mov     r8, cs:off_14005DF38
0x1400353b1  mov     rcx, cs:WdfDriverGlobals
0x1400353b8  mov     rax, [rax+650h]
0x1400353bf  call    _guard_dispatch_icall
0x1400353c4  add     rax, 18h
0x1400353c8  jmp     loc_1400354D6
0x1400353cd  mov     r12d, edx
0x1400353d0  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400353d7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400353de  jz      short loc_140035410
0x1400353e0  mov     eax, [r14+0Ch]
0x1400353e4  mov     [rsp+150h+var_108], r13d
0x1400353e9  mov     [rsp+150h+var_110], r12d
0x1400353ee  mov     dword ptr [rsp+150h+var_118], eax
0x1400353f2  mov     eax, [rsi+10h]
0x1400353f5  mov     ecx, ebx
0x1400353f7  mov     [rsp+150h+var_120], rcx
0x1400353fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140035403  mov     [rsp+150h+var_128], eax
0x140035407  mov     rcx, [rcx+40h]
0x14003540b  call    WPP_RECORDER_SF_DIddd
0x140035410  mov     ebx, 0C000009Ah
0x140035415  lea     r13, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003541c  jmp     loc_140035345
0x140035421  mov     ecx, edx
0x140035423  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003542a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140035431  jz      loc_140035339
0x140035437  mov     eax, ecx
0x140035439  mov     r9d, 150h
0x14003543f  mov     rcx, [rsp+150h+var_F0]
0x140035444  mov     [rsp+150h+var_110], ecx
0x140035448  mov     rcx, cs:WPP_GLOBAL_Control
0x14003544f  mov     [rsp+150h+var_118], rax
0x140035454  mov     eax, [rsi+10h]
0x140035457  mov     dword ptr [rsp+150h+var_120], r13d
0x14003545c  mov     rcx, [rcx+40h]
0x140035460  mov     [rsp+150h+var_128], eax
0x140035464  call    WPP_RECORDER_SF_DdId
0x140035469  jmp     loc_140035339
0x14003546e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140035475  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003547c  jz      loc_140035339
0x140035482  mov     rcx, cs:WPP_GLOBAL_Control
0x140035489  mov     r9d, 14Fh
0x14003548f  mov     eax, [rsi+10h]
0x140035492  mov     r8d, 3
0x140035498  mov     dword ptr [rsp+150h+var_118], 10h
0x1400354a0  mov     dl, 2
0x1400354a2  mov     dword ptr [rsp+150h+var_120], r13d
0x1400354a7  lea     r13, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400354ae  mov     rcx, [rcx+40h]
0x1400354b2  mov     [rsp+150h+var_128], eax
0x1400354b6  mov     qword ptr [rsp+150h+var_130], r13
0x1400354bb  call    WPP_RECORDER_SF_Ddd
0x1400354c0  jmp     loc_140035340
0x1400354c5  mov     rax, [rsi+30h]
0x1400354c9  mov     rcx, [rax]
0x1400354cc  mov     rax, [rcx+478h]
0x1400354d3  mov     rax, [rax]
0x1400354d6  lea     rdx, [rsp+150h+var_E0]; struct _NDIS_STATUS_INDICATION *
0x1400354db  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x1400354de  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x1400354e3  test    r15, r15
0x1400354e6  jz      short loc_1400354F9
0x1400354e8  xor     edx, edx; Tag
0x1400354ea  mov     rcx, r15; P
0x1400354ed  call    cs:__imp_ExFreePoolWithTag
0x1400354f4  nop     dword ptr [rax+rax+00h]
0x1400354f9  xor     eax, eax
0x1400354fb  mov     rcx, [rbp+50h+var_50]
0x1400354ff  xor     rcx, rsp; StackCookie
0x140035502  call    __security_check_cookie
0x140035507  add     rsp, 118h
0x14003550e  pop     r15
0x140035510  pop     r14
0x140035512  pop     r13
0x140035514  pop     r12
0x140035516  pop     rdi
0x140035517  pop     rsi
0x140035518  pop     rbx
0x140035519  pop     rbp
0x14003551a  retn
```
