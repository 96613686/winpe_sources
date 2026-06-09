# MbbNdisLteAttachConfigHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x14002fb40`
- end: `0x1400300b1`
- name: `?MbbNdisLteAttachConfigHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `1393`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, struct _MBB_MS_LTE_ATTACH_CONFIG_INFO *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140005644`
- `0x14002fb40`
- `0x14003df70`
- `0x14003f028`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002fb9e`
- `ntoskrnl!ExAllocatePool2` at `0x14002fb9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003007a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003007a`

## pseudocode

```c
__int64 __fastcall MbbNdisLteAttachConfigHandler(
        __int64 a1,
        int a2,
        unsigned int a3,
        struct _MBB_MS_LTE_ATTACH_CONFIG_INFO *a4,
        unsigned int a5)
{
  _DWORD *Pool2; // rax
  int v9; // edx
  _DWORD *v10; // r13
  int v12; // edx
  __int64 v13; // rax
  unsigned int v14; // edx
  int v15; // ebx
  unsigned int v16; // eax
  int v17; // r9d
  unsigned int v18; // r15d
  __int64 v19; // rcx
  unsigned int v20; // r10d
  int v21; // r8d
  int v22; // edx
  int v23; // r9d
  __int64 v24; // rdx
  NDIS_HANDLE *v25; // rax
  char v26; // [rsp+30h] [rbp-A1h]
  unsigned int v27; // [rsp+38h] [rbp-99h]
  int IsVariableFieldValid; // [rsp+40h] [rbp-91h]
  unsigned int v29; // [rsp+44h] [rbp-8Dh]
  __int64 v31; // [rsp+50h] [rbp-81h]
  unsigned int v32; // [rsp+58h] [rbp-79h]
  unsigned int v33; // [rsp+60h] [rbp-71h]
  struct _NDIS_STATUS_INDICATION v34; // [rsp+70h] [rbp-61h] BYREF

  IsVariableFieldValid = a2;
  memset(&v34, 0, sizeof(v34));
  Pool2 = (_DWORD *)ExAllocatePool2(64, 3816, 1683505741);
  v10 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        344,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        232,
        *(_DWORD *)a4);
    }
    return 3221225626LL;
  }
  memset(Pool2, 0, 0xEE8u);
  v13 = *(_QWORD *)(a1 + 48);
  v34.Header = (NDIS_OBJECT_HEADER)7340440;
  v34.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v13 + 1144LL) + 16LL);
  v34.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v34.RequestId = *(PVOID *)(a1 + 432);
  v34.PortNumber = 0;
  *(_QWORD *)&v34.StatusCode = 1074008125;
  v34.Guid = 0;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        3,
        345,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
    goto LABEL_43;
  }
  v15 = MbbUtilMbbToWwanStatus(a3);
  if ( !v15 )
  {
    v16 = a5;
    if ( a4 && a5 >= 0xC )
    {
      if ( *(_DWORD *)a4 != 3 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v27 = 3;
          v17 = 347;
          v26 = *(_DWORD *)a4;
          goto LABEL_42;
        }
        goto LABEL_43;
      }
      if ( a5 >= 0x1C )
      {
        v19 = 0;
        v29 = 0;
        while ( 1 )
        {
          IsVariableFieldValid = MbbIsVariableFieldValid(
                                   v16,
                                   *((_DWORD *)a4 + 2 * v19 + 1),
                                   *((_DWORD *)a4 + 2 * v19 + 2),
                                   0x291u,
                                   1u,
                                   1);
          if ( IsVariableFieldValid < 0 )
            break;
          v20 = *((_DWORD *)a4 + 2 * v29 + 2);
          if ( v20 < 0x2C )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v27 = 44;
              v17 = 351;
              v26 = *((_DWORD *)a4 + 2 * v29 + 2);
              goto LABEL_42;
            }
            goto LABEL_43;
          }
          v31 = *((unsigned int *)a4 + 2 * v29 + 1);
          IsVariableFieldValid = MbbIsVariableFieldValid(
                                   v20,
                                   *(_DWORD *)((char *)a4 + v31 + 12),
                                   *(_DWORD *)((char *)a4 + v31 + 16),
                                   0x64u,
                                   2u,
                                   1);
          if ( IsVariableFieldValid < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_43;
            v23 = 352;
            goto LABEL_31;
          }
          v32 = (*(_DWORD *)((char *)a4 + v31 + 16) + 3) & 0xFFFFFFFC;
          IsVariableFieldValid = MbbIsVariableFieldValid(
                                   *((_DWORD *)a4 + 2 * v29 + 2),
                                   *(_DWORD *)((char *)a4 + v31 + 20),
                                   *(_DWORD *)((char *)a4 + v31 + 24),
                                   0xFFu,
                                   2u,
                                   1);
          if ( IsVariableFieldValid < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_43;
            v23 = 353;
            goto LABEL_31;
          }
          v33 = (*(_DWORD *)((char *)a4 + v31 + 24) + 3) & 0xFFFFFFFC;
          IsVariableFieldValid = MbbIsVariableFieldValid(
                                   *((_DWORD *)a4 + 2 * v29 + 2),
                                   *(_DWORD *)((char *)a4 + v31 + 28),
                                   *(_DWORD *)((char *)a4 + v31 + 32),
                                   0xFFu,
                                   2u,
                                   1);
          if ( IsVariableFieldValid < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_43;
            v23 = 354;
            goto LABEL_31;
          }
          v14 = v32 + ((*(_DWORD *)((char *)a4 + v31 + 32) + 3) & 0xFFFFFFFC) + v33 + 44;
          if ( *((_DWORD *)a4 + 2 * v29 + 2) != v14 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_43;
            v27 = v32 + ((*(_DWORD *)((char *)a4 + v31 + 32) + 3) & 0xFFFFFFFC) + v33 + 44;
            v17 = 355;
            v26 = *((_DWORD *)a4 + 2 * v29 + 2);
LABEL_42:
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_Ddd(
              WPP_GLOBAL_Control->DeviceExtension,
              v14,
              3,
              v17,
              (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
              *(_DWORD *)(a1 + 16),
              v26,
              v27);
            goto LABEL_43;
          }
          v21 = *(_DWORD *)a4;
          v19 = v29 + 1;
          v16 = a5;
          v29 = v19;
          if ( (unsigned int)v19 >= *(_DWORD *)a4 )
          {
            *v10 = 250085760;
            v10[2] = v21;
            MbbUtilMbbToWwanLteAttachConfigInfo(a4, (struct _WWAN_LTE_ATTACH_CONFIG *)(v10 + 2));
            v18 = IsVariableFieldValid;
            goto LABEL_47;
          }
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_43;
        v23 = 350;
LABEL_31:
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          3,
          v23,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *(_DWORD *)(a1 + 16));
        goto LABEL_43;
      }
      v18 = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_Ddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          3,
          349,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *(_DWORD *)(a1 + 16),
          a5,
          28);
      }
      v15 = -1073479677;
      goto LABEL_45;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v27 = 12;
      v17 = 346;
      v26 = a5;
      goto LABEL_42;
    }
LABEL_43:
    v15 = -1073479677;
  }
  v18 = IsVariableFieldValid;
LABEL_45:
  if ( (unsigned int)MbbUtilMbbToWwanStatus(a3) )
    v15 = MbbUtilMbbToWwanStatus(a3);
LABEL_47:
  v34.StatusBuffer = v10;
  v34.StatusBufferSize = 3816;
  v10[1] = v15;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v22) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      3,
      356,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v15);
  }
  v24 = *(_QWORD *)(a1 + 104);
  if ( v24 )
    v25 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                            WdfDriverGlobals,
                            v24,
                            off_14005DF38)
                        + 24);
  else
    v25 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v25, &v34);
  ExFreePoolWithTag(v10, 0);
  return v18;
}

```

## disassembly

```asm
0x14002fb40  mov     [rsp-8+arg_8], rbx
0x14002fb45  push    rbp
0x14002fb46  push    rsi
0x14002fb47  push    rdi
0x14002fb48  push    r12
0x14002fb4a  push    r13
0x14002fb4c  push    r14
0x14002fb4e  push    r15
0x14002fb50  lea     rbp, [rsp-1Fh]
0x14002fb55  sub     rsp, 0F0h
0x14002fb5c  mov     rax, cs:__security_cookie
0x14002fb63  xor     rax, rsp
0x14002fb66  mov     [rbp+4Fh+var_40], rax
0x14002fb6a  mov     ebx, edx
0x14002fb6c  mov     [rsp+120h+var_E0], edx
0x14002fb70  xor     edx, edx; Val
0x14002fb72  mov     [rsp+120h+var_D8], r8d
0x14002fb77  mov     rsi, rcx
0x14002fb7a  mov     r15, r9
0x14002fb7d  lea     rcx, [rbp+4Fh+var_B0]; void *
0x14002fb81  lea     r8d, [rdx+70h]; Size
0x14002fb85  call    memset
0x14002fb8a  mov     r14d, 0EE8h
0x14002fb90  mov     r8d, 6458424Dh
0x14002fb96  mov     edx, r14d
0x14002fb99  mov     ecx, 40h ; '@'
0x14002fb9e  call    cs:__imp_ExAllocatePool2
0x14002fba5  nop     dword ptr [rax+rax+00h]
0x14002fbaa  mov     r13, rax
0x14002fbad  test    rax, rax
0x14002fbb0  jnz     short loc_14002FC07
0x14002fbb2  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002fbb9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002fbc0  jz      short loc_14002FBFD
0x14002fbc2  mov     eax, [r15]
0x14002fbc5  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002fbcc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fbd3  lea     r8d, [r13+3]
0x14002fbd7  mov     dword ptr [rsp+120h+var_E8], eax
0x14002fbdb  mov     r9d, 158h
0x14002fbe1  mov     eax, [rsi+10h]
0x14002fbe4  mov     dl, 2
0x14002fbe6  mov     dword ptr [rsp+120h+var_F0], r14d
0x14002fbeb  mov     rcx, [rcx+40h]
0x14002fbef  mov     [rsp+120h+var_F8], eax
0x14002fbf3  mov     qword ptr [rsp+120h+var_100], r12
0x14002fbf8  call    WPP_RECORDER_SF_Ddd
0x14002fbfd  mov     eax, 0C000009Ah
0x14002fc02  jmp     loc_140030089
0x14002fc07  mov     r8, r14; Size
0x14002fc0a  xor     edx, edx; Val
0x14002fc0c  mov     rcx, r13; void *
0x14002fc0f  call    memset
0x14002fc14  mov     rax, [rsi+30h]
0x14002fc18  xorps   xmm0, xmm0
0x14002fc1b  mov     dword ptr [rbp+4Fh+var_B0.Header.Type], 700198h
0x14002fc22  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002fc29  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002fc30  mov     r14d, 3
0x14002fc36  mov     rcx, [rax]
0x14002fc39  mov     rax, [rcx+478h]
0x14002fc40  mov     rcx, [rax]
0x14002fc43  mov     rax, [rcx+10h]
0x14002fc47  mov     [rbp+4Fh+var_B0.SourceHandle], rax
0x14002fc4b  mov     rax, [rsi+1B8h]
0x14002fc52  mov     [rbp+4Fh+var_B0.DestinationHandle], rax
0x14002fc56  mov     rax, [rsi+1B0h]
0x14002fc5d  mov     [rbp+4Fh+var_B0.RequestId], rax
0x14002fc61  mov     [rbp+4Fh+var_B0.PortNumber], 0
0x14002fc68  mov     qword ptr [rbp+4Fh+var_B0.StatusCode], 4004103Dh
0x14002fc70  movups  xmmword ptr [rbp+4Fh+var_B0.Guid.Data1], xmm0
0x14002fc74  test    ebx, ebx
0x14002fc76  jz      short loc_14002FCB5
0x14002fc78  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002fc7f  jz      loc_14002FFC3
0x14002fc85  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fc8c  mov     r9d, 159h
0x14002fc92  mov     eax, [rsi+10h]
0x14002fc95  mov     r8d, r14d
0x14002fc98  mov     dword ptr [rsp+120h+var_F0], ebx
0x14002fc9c  mov     dl, 2
0x14002fc9e  mov     [rsp+120h+var_F8], eax
0x14002fca2  mov     rcx, [rcx+40h]
0x14002fca6  mov     qword ptr [rsp+120h+var_100], r12
0x14002fcab  call    WPP_RECORDER_SF_DD
0x14002fcb0  jmp     loc_14002FFC3
0x14002fcb5  mov     ecx, [rsp+120h+var_D8]
0x14002fcb9  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002fcbe  mov     ebx, eax
0x14002fcc0  test    eax, eax
0x14002fcc2  jnz     loc_14002FFC8
0x14002fcc8  mov     eax, [rbp+4Fh+arg_20]
0x14002fccb  test    r15, r15
0x14002fcce  jz      loc_14002FF87
0x14002fcd4  cmp     eax, 0Ch
0x14002fcd7  jb      loc_14002FF87
0x14002fcdd  mov     ecx, [r15]
0x14002fce0  cmp     ecx, r14d
0x14002fce3  jz      short loc_14002FD06
0x14002fce5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002fcec  jz      loc_14002FFC3
0x14002fcf2  mov     dword ptr [rsp+120h+var_E8], r14d
0x14002fcf7  mov     r9d, 15Bh
0x14002fcfd  mov     dword ptr [rsp+120h+var_F0], ecx
0x14002fd01  jmp     loc_14002FFA2
0x14002fd06  cmp     eax, 1Ch
0x14002fd09  jnb     short loc_14002FD54
0x14002fd0b  xor     r15d, r15d
0x14002fd0e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002fd15  jz      short loc_14002FD4A
0x14002fd17  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fd1e  mov     r9d, 15Dh
0x14002fd24  mov     dword ptr [rsp+120h+var_E8], 1Ch
0x14002fd2c  mov     r8d, r14d
0x14002fd2f  mov     dword ptr [rsp+120h+var_F0], eax
0x14002fd33  mov     dl, 2
0x14002fd35  mov     eax, [rsi+10h]
0x14002fd38  mov     rcx, [rcx+40h]
0x14002fd3c  mov     [rsp+120h+var_F8], eax
0x14002fd40  mov     qword ptr [rsp+120h+var_100], r12
0x14002fd45  call    WPP_RECORDER_SF_Ddd
0x14002fd4a  mov     ebx, 0C0040003h
0x14002fd4f  jmp     loc_14002FFCD
0x14002fd54  xor     ecx, ecx
0x14002fd56  mov     [rsp+120h+var_DC], ecx
0x14002fd5a  mov     r8d, [r15+rcx*8+8]; unsigned int
0x14002fd5f  mov     r9d, 291h; unsigned int
0x14002fd65  mov     edx, [r15+rcx*8+4]; unsigned int
0x14002fd6a  mov     ecx, eax; unsigned int
0x14002fd6c  mov     [rsp+120h+var_F8], 1; int
0x14002fd74  mov     [rsp+120h+var_100], 1; unsigned int
0x14002fd7c  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x14002fd81  mov     [rsp+120h+var_E0], eax
0x14002fd85  test    eax, eax
0x14002fd87  js      loc_14002FF76
0x14002fd8d  mov     ecx, [rsp+120h+var_DC]
0x14002fd91  mov     r10d, [r15+rcx*8+8]
0x14002fd96  cmp     r10d, 2Ch ; ','
0x14002fd9a  jb      loc_14002FF58
0x14002fda0  mov     eax, [r15+rcx*8+4]
0x14002fda5  mov     r9d, 64h ; 'd'; unsigned int
0x14002fdab  mov     [rsp+120h+var_F8], 1; int
0x14002fdb3  mov     ecx, r10d; unsigned int
0x14002fdb6  mov     [rsp+120h+var_D0], rax
0x14002fdbb  mov     [rsp+120h+var_100], 2; unsigned int
0x14002fdc3  mov     r8d, [rax+r15+10h]; unsigned int
0x14002fdc8  mov     edx, [rax+r15+0Ch]; unsigned int
0x14002fdcd  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x14002fdd2  mov     [rsp+120h+var_E0], eax
0x14002fdd6  test    eax, eax
0x14002fdd8  js      loc_14002FF47
0x14002fdde  mov     rcx, [rsp+120h+var_D0]
0x14002fde3  mov     r9d, 0FFh; unsigned int
0x14002fde9  mov     [rsp+120h+var_F8], 1; int
0x14002fdf1  mov     [rsp+120h+var_100], 2; unsigned int
0x14002fdf9  mov     eax, [rcx+r15+10h]
0x14002fdfe  mov     r8d, [rcx+r15+18h]; unsigned int
0x14002fe03  add     eax, r14d
0x14002fe06  mov     edx, [rcx+r15+14h]; unsigned int
0x14002fe0b  and     eax, 0FFFFFFFCh
0x14002fe0e  mov     [rbp+4Fh+var_C8], eax
0x14002fe11  mov     eax, [rsp+120h+var_DC]
0x14002fe15  mov     ecx, [r15+rax*8+8]; unsigned int
0x14002fe1a  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x14002fe1f  mov     [rsp+120h+var_E0], eax
0x14002fe23  test    eax, eax
0x14002fe25  js      loc_14002FF32
0x14002fe2b  mov     rcx, [rsp+120h+var_D0]
0x14002fe30  mov     r9d, 0FFh; unsigned int
0x14002fe36  mov     [rsp+120h+var_F8], 1; int
0x14002fe3e  mov     [rsp+120h+var_100], 2; unsigned int
0x14002fe46  mov     eax, [rcx+r15+18h]
0x14002fe4b  mov     r8d, [rcx+r15+20h]; unsigned int
0x14002fe50  add     eax, r14d
0x14002fe53  mov     edx, [rcx+r15+1Ch]; unsigned int
0x14002fe58  and     eax, 0FFFFFFFCh
0x14002fe5b  mov     ecx, [rsp+120h+var_DC]
0x14002fe5f  mov     [rbp+4Fh+var_C0], eax
0x14002fe62  mov     ecx, [r15+rcx*8+8]; unsigned int
0x14002fe67  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x14002fe6c  mov     [rsp+120h+var_E0], eax
0x14002fe70  test    eax, eax
0x14002fe72  js      loc_14002FEF9
0x14002fe78  mov     rcx, [rsp+120h+var_D0]
0x14002fe7d  mov     rdx, qword ptr [rbp+4Fh+var_C0]
0x14002fe81  add     edx, 2Ch ; ','
0x14002fe84  mov     eax, [rcx+r15+20h]
0x14002fe89  mov     ecx, [rsp+120h+var_DC]
0x14002fe8d  add     eax, r14d
0x14002fe90  and     eax, 0FFFFFFFCh
0x14002fe93  add     eax, [rbp+4Fh+var_C8]
0x14002fe96  add     edx, eax
0x14002fe98  mov     r8d, [r15+rcx*8+8]
0x14002fe9d  cmp     r8d, edx
0x14002fea0  jnz     short loc_14002FED8
0x14002fea2  mov     r8d, [r15]
0x14002fea5  inc     ecx
0x14002fea7  mov     eax, [rbp+4Fh+arg_20]
0x14002feaa  mov     [rsp+120h+var_DC], ecx
0x14002feae  cmp     ecx, r8d
0x14002feb1  jb      loc_14002FD5A
0x14002feb7  lea     rdx, [r13+8]; struct _WWAN_LTE_ATTACH_CONFIG *
0x14002febb  mov     dword ptr [r13+0], 0EE80180h
0x14002fec3  mov     rcx, r15; struct _MBB_MS_LTE_ATTACH_CONFIG_INFO *
0x14002fec6  mov     [rdx], r8d
0x14002fec9  call    ?MbbUtilMbbToWwanLteAttachConfigInfo@@YAXPEAU_MBB_MS_LTE_ATTACH_CONFIG_INFO@@PEAU_WWAN_LTE_ATTACH_CONFIG@@@Z; MbbUtilMbbToWwanLteAttachConfigInfo(_MBB_MS_LTE_ATTACH_CONFIG_INFO *,_WWAN_LTE_ATTACH_CONFIG *)
0x14002fece  mov     r15d, [rsp+120h+var_E0]
0x14002fed3  jmp     loc_14002FFE5
0x14002fed8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002fedf  jz      loc_14002FFC3
0x14002fee5  mov     dword ptr [rsp+120h+var_E8], edx
0x14002fee9  mov     r9d, 163h
0x14002feef  mov     dword ptr [rsp+120h+var_F0], r8d
0x14002fef4  jmp     loc_14002FFA2
0x14002fef9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002ff00  jz      loc_14002FFC3
0x14002ff06  mov     r9d, 162h
0x14002ff0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ff13  mov     r8d, r14d
0x14002ff16  mov     eax, [rsi+10h]
0x14002ff19  mov     dl, 2
0x14002ff1b  mov     [rsp+120h+var_F8], eax
0x14002ff1f  mov     qword ptr [rsp+120h+var_100], r12
0x14002ff24  mov     rcx, [rcx+40h]
0x14002ff28  call    WPP_RECORDER_SF_d
0x14002ff2d  jmp     loc_14002FFC3
0x14002ff32  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002ff39  jz      loc_14002FFC3
0x14002ff3f  mov     r9d, 161h
0x14002ff45  jmp     short loc_14002FF0C
0x14002ff47  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002ff4e  jz      short loc_14002FFC3
0x14002ff50  mov     r9d, 160h
0x14002ff56  jmp     short loc_14002FF0C
0x14002ff58  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002ff5f  jz      short loc_14002FFC3
0x14002ff61  mov     dword ptr [rsp+120h+var_E8], 2Ch ; ','
0x14002ff69  mov     r9d, 15Fh
0x14002ff6f  mov     dword ptr [rsp+120h+var_F0], r10d
0x14002ff74  jmp     short loc_14002FFA2
0x14002ff76  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002ff7d  jz      short loc_14002FFC3
0x14002ff7f  mov     r9d, 15Eh
0x14002ff85  jmp     short loc_14002FF0C
0x14002ff87  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002ff8e  jz      short loc_14002FFC3
0x14002ff90  mov     dword ptr [rsp+120h+var_E8], 0Ch
0x14002ff98  mov     r9d, 15Ah
0x14002ff9e  mov     dword ptr [rsp+120h+var_F0], eax
0x14002ffa2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ffa9  mov     r8d, r14d
0x14002ffac  mov     eax, [rsi+10h]
0x14002ffaf  mov     dl, 2
0x14002ffb1  mov     [rsp+120h+var_F8], eax
0x14002ffb5  mov     qword ptr [rsp+120h+var_100], r12
0x14002ffba  mov     rcx, [rcx+40h]
0x14002ffbe  call    WPP_RECORDER_SF_Ddd
0x14002ffc3  mov     ebx, 0C0040003h
0x14002ffc8  mov     r15d, [rsp+120h+var_E0]
0x14002ffcd  mov     ecx, [rsp+120h+var_D8]
0x14002ffd1  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002ffd6  test    eax, eax
0x14002ffd8  jz      short loc_14002FFE5
0x14002ffda  mov     ecx, [rsp+120h+var_D8]
0x14002ffde  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002ffe3  mov     ebx, eax
0x14002ffe5  mov     [rbp+4Fh+var_B0.StatusBuffer], r13
0x14002ffe9  mov     [rbp+4Fh+var_B0.StatusBufferSize], 0EE8h
0x14002fff0  mov     [r13+4], ebx
0x14002fff4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002fffb  jz      short loc_140030028
0x14002fffd  mov     rcx, cs:WPP_GLOBAL_Control
0x140030004  mov     r9d, 164h
0x14003000a  mov     eax, [rsi+10h]
0x14003000d  mov     r8d, r14d
0x140030010  mov     dword ptr [rsp+120h+var_F0], ebx
0x140030014  mov     dl, 4
0x140030016  mov     [rsp+120h+var_F8], eax
0x14003001a  mov     rcx, [rcx+40h]
0x14003001e  mov     qword ptr [rsp+120h+var_100], r12
0x140030023  call    WPP_RECORDER_SF_DD
0x140030028  mov     rdx, [rsi+68h]
0x14003002c  test    rdx, rdx
0x14003002f  jz      short loc_140030058
0x140030031  mov     rax, cs:WdfFunctions_01031
0x140030038  mov     r8, cs:off_14005DF38
0x14003003f  mov     rcx, cs:WdfDriverGlobals
0x140030046  mov     rax, [rax+650h]
0x14003004d  call    _guard_dispatch_icall
0x140030052  add     rax, 18h
0x140030056  jmp     short loc_140030069
0x140030058  mov     rax, [rsi+30h]
0x14003005c  mov     rdx, [rax]
0x14003005f  mov     rax, [rdx+478h]
0x140030066  mov     rax, [rax]
0x140030069  lea     rdx, [rbp+4Fh+var_B0]; struct _NDIS_STATUS_INDICATION *
0x14003006d  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x140030070  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x140030075  xor     edx, edx; Tag
0x140030077  mov     rcx, r13; P
  ... truncated ...
```
