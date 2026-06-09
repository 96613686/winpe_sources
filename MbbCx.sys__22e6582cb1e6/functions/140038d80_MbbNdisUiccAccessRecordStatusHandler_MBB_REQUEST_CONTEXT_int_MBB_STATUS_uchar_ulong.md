# MbbNdisUiccAccessRecordStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140038d80`
- end: `0x140039135`
- name: `?MbbNdisUiccAccessRecordStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `949`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x1400051ac`
- `0x140005644`
- `0x140038d80`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140038f10`
- `ntoskrnl!ExAllocatePool2` at `0x140038f10`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400390ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400390ff`

## pseudocode

```c
__int64 __fastcall MbbNdisUiccAccessRecordStatusHandler(
        __int64 a1,
        int a2,
        unsigned int a3,
        _DWORD *a4,
        unsigned int a5)
{
  char v8; // r13
  __int64 v10; // rax
  _DWORD *v11; // rdi
  ULONG v12; // r14d
  unsigned int v13; // edx
  int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ecx
  _DWORD *Pool2; // rax
  int v18; // edx
  int v19; // edx
  size_t v20; // r8
  char *v21; // rdx
  __int64 v22; // rdx
  NDIS_HANDLE *v23; // rax
  struct _NDIS_STATUS_INDICATION v26; // [rsp+50h] [rbp-71h] BYREF
  _BYTE v27[24]; // [rsp+C0h] [rbp-1h] BYREF

  v8 = 1;
  memset(&v26.Header + 1, 0, 0x6Cu);
  v26.Header = (NDIS_OBJECT_HEADER)7340440;
  v10 = *(_QWORD *)(a1 + 48);
  v11 = 0;
  memset(v27, 0, sizeof(v27));
  v12 = 0;
  v26.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v10 + 1144LL) + 16LL);
  v26.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v26.RequestId = *(PVOID *)(a1 + 432);
  v26.PortNumber = 0;
  *(_QWORD *)&v26.StatusCode = 1074008137;
  v26.Guid = 0;
  v14 = MbbUtilMbbToWwanStatus(a3);
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        3,
        235,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
LABEL_23:
    v14 = -1073479677;
    goto LABEL_24;
  }
  if ( !a4 || a5 < 0x14 || (v15 = a4[3], v16 = a4[4], v13 = v15 + v16, v15 + v16 < v15) || a5 < v13 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        3,
        236,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a5,
        20);
    }
    goto LABEL_23;
  }
  v12 = v16 + 22;
  if ( v16 >= 0xFFFFFFEA )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        3,
        237,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v16);
    }
    v12 = -1;
    goto LABEL_23;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(64, v12, 1683505741);
  v11 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        3,
        238,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v12);
    }
    v8 = 1;
    goto LABEL_23;
  }
  memset(Pool2, 0, v12);
  v11[2] = *a4;
  v11[3] = a4[1];
  v11[4] = a4[2];
  *v11 = 1573248;
  if ( a5 <= 0x14 )
  {
    *((_WORD *)v11 + 10) = 0;
  }
  else
  {
    v20 = (unsigned int)a4[4];
    v21 = (char *)a4 + (unsigned int)a4[3];
    *((_WORD *)v11 + 10) = *((_WORD *)a4 + 8);
    memmove((char *)v11 + 22, v21, v20);
  }
  v8 = 0;
  if ( !v14 )
  {
LABEL_27:
    v11[1] = v14;
    v26.StatusBuffer = v11;
    v26.StatusBufferSize = v12;
    goto LABEL_29;
  }
LABEL_24:
  if ( (unsigned int)MbbUtilMbbToWwanStatus(a3) )
    v14 = MbbUtilMbbToWwanStatus(a3);
  if ( !v8 )
    goto LABEL_27;
  *(_DWORD *)v27 = 1573248;
  *(_DWORD *)&v27[4] = v14;
  v26.StatusBufferSize = 24;
  *(_OWORD *)&v27[8] = 0;
  v26.StatusBuffer = v27;
LABEL_29:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      3,
      239,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v14);
  }
  v22 = *(_QWORD *)(a1 + 104);
  if ( v22 )
    v23 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                            WdfDriverGlobals,
                            v22,
                            off_14005DF38)
                        + 24);
  else
    v23 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v23, &v26);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  return 0;
}

```

## disassembly

```asm
0x140038d80  mov     [rsp-8+arg_8], rbx
0x140038d85  push    rbp
0x140038d86  push    rsi
0x140038d87  push    rdi
0x140038d88  push    r12
0x140038d8a  push    r13
0x140038d8c  push    r14
0x140038d8e  push    r15
0x140038d90  lea     rbp, [rsp-1Fh]
0x140038d95  sub     rsp, 0E0h
0x140038d9c  mov     rax, cs:__security_cookie
0x140038da3  xor     rax, rsp
0x140038da6  mov     [rbp+4Fh+var_38], rax
0x140038daa  mov     ebx, r8d
0x140038dad  mov     r12d, edx
0x140038db0  xor     edx, edx; Val
0x140038db2  mov     [rbp+4Fh+var_CC], ebx
0x140038db5  mov     r15, rcx
0x140038db8  mov     r13b, 1
0x140038dbb  lea     rcx, [rbp+4Fh+var_C0+4]; void *
0x140038dbf  mov     [rsp+110h+var_D0], r13b
0x140038dc4  mov     rsi, r9
0x140038dc7  lea     r8d, [rdx+6Ch]; Size
0x140038dcb  call    memset
0x140038dd0  xor     eax, eax
0x140038dd2  mov     dword ptr [rbp+4Fh+var_C0.Header.Type], 700198h
0x140038dd9  mov     [rbp+4Fh+var_40], rax
0x140038ddd  xorps   xmm0, xmm0
0x140038de0  mov     rax, [r15+30h]
0x140038de4  xor     edi, edi
0x140038de6  movups  [rbp+4Fh+var_50], xmm0
0x140038dea  xor     r14d, r14d
0x140038ded  mov     rcx, [rax]
0x140038df0  mov     rax, [rcx+478h]
0x140038df7  mov     rcx, [rax]
0x140038dfa  mov     rax, [rcx+10h]
0x140038dfe  mov     ecx, ebx
0x140038e00  mov     [rbp+4Fh+var_C0.SourceHandle], rax
0x140038e04  mov     rax, [r15+1B8h]
0x140038e0b  mov     [rbp+4Fh+var_C0.DestinationHandle], rax
0x140038e0f  mov     rax, [r15+1B0h]
0x140038e16  mov     [rbp+4Fh+var_C0.RequestId], rax
0x140038e1a  mov     [rbp+4Fh+var_C0.PortNumber], edi
0x140038e1d  mov     qword ptr [rbp+4Fh+var_C0.StatusCode], 40041049h
0x140038e25  movups  xmmword ptr [rbp+4Fh+var_C0.Guid.Data1], xmm0
0x140038e29  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140038e2e  lea     r8, WPP_RECORDER_INITIALIZED
0x140038e35  mov     ebx, eax
0x140038e37  lea     r11, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140038e3e  lea     r10d, [r14+3]
0x140038e42  test    r12d, r12d
0x140038e45  jz      short loc_140038E86
0x140038e47  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140038e4e  jz      loc_14003900E
0x140038e54  mov     rcx, cs:WPP_GLOBAL_Control
0x140038e5b  mov     r9d, 0EBh
0x140038e61  mov     eax, [r15+10h]
0x140038e65  mov     r8d, r10d
0x140038e68  mov     [rsp+110h+var_E0], r12d
0x140038e6d  mov     dl, 2
0x140038e6f  mov     [rsp+110h+var_E8], eax
0x140038e73  mov     rcx, [rcx+40h]
0x140038e77  mov     [rsp+110h+var_F0], r11
0x140038e7c  call    WPP_RECORDER_SF_DD
0x140038e81  jmp     loc_14003900E
0x140038e86  mov     r12d, [rbp+4Fh+arg_20]
0x140038e8a  test    rsi, rsi
0x140038e8d  jz      loc_140038FD0
0x140038e93  cmp     r12d, 14h
0x140038e97  jb      loc_140038FD0
0x140038e9d  mov     eax, [rsi+0Ch]
0x140038ea0  mov     ecx, [rsi+10h]
0x140038ea3  lea     edx, [rax+rcx]
0x140038ea6  cmp     edx, eax
0x140038ea8  jb      loc_140038FD0
0x140038eae  cmp     r12d, edx
0x140038eb1  jb      loc_140038FD0
0x140038eb7  lea     r14d, [rcx+16h]
0x140038ebb  cmp     r14d, 16h
0x140038ebf  jnb     short loc_140038EFF
0x140038ec1  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140038ec8  jz      short loc_140038EF6
0x140038eca  mov     eax, [r15+10h]
0x140038ece  mov     r9d, 0EDh
0x140038ed4  mov     [rsp+110h+var_E0], ecx
0x140038ed8  mov     r8d, r10d
0x140038edb  mov     rcx, cs:WPP_GLOBAL_Control
0x140038ee2  mov     dl, 2
0x140038ee4  mov     [rsp+110h+var_E8], eax
0x140038ee8  mov     [rsp+110h+var_F0], r11
0x140038eed  mov     rcx, [rcx+40h]
0x140038ef1  call    WPP_RECORDER_SF_DD
0x140038ef6  or      r14d, 0FFFFFFFFh
0x140038efa  jmp     loc_14003900E
0x140038eff  mov     r8d, 6458424Dh
0x140038f05  mov     edx, r14d
0x140038f08  mov     ecx, 40h ; '@'
0x140038f0d  mov     r13d, r14d
0x140038f10  call    cs:__imp_ExAllocatePool2
0x140038f17  nop     dword ptr [rax+rax+00h]
0x140038f1c  mov     rdi, rax
0x140038f1f  test    rax, rax
0x140038f22  jnz     short loc_140038F73
0x140038f24  lea     r12, WPP_RECORDER_INITIALIZED
0x140038f2b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140038f32  jz      short loc_140038F69
0x140038f34  mov     eax, [r15+10h]
0x140038f38  lea     r8d, [rdi+3]
0x140038f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038f43  mov     r9d, 0EEh
0x140038f49  mov     [rsp+110h+var_E0], r14d
0x140038f4e  mov     dl, 2
0x140038f50  mov     [rsp+110h+var_E8], eax
0x140038f54  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140038f5b  mov     [rsp+110h+var_F0], rax
0x140038f60  mov     rcx, [rcx+40h]
0x140038f64  call    WPP_RECORDER_SF_DD
0x140038f69  mov     r13b, [rsp+110h+var_D0]
0x140038f6e  jmp     loc_140039015
0x140038f73  mov     r8, r13; Size
0x140038f76  xor     edx, edx; Val
0x140038f78  mov     rcx, rdi; void *
0x140038f7b  call    memset
0x140038f80  mov     eax, [rsi]
0x140038f82  mov     [rdi+8], eax
0x140038f85  mov     eax, [rsi+4]
0x140038f88  mov     [rdi+0Ch], eax
0x140038f8b  mov     eax, [rsi+8]
0x140038f8e  mov     [rdi+10h], eax
0x140038f91  mov     dword ptr [rdi], 180180h
0x140038f97  cmp     r12d, 14h
0x140038f9b  jbe     short loc_140038FBA
0x140038f9d  movzx   eax, word ptr [rsi+10h]
0x140038fa1  lea     rcx, [rdi+16h]; void *
0x140038fa5  mov     edx, [rsi+0Ch]
0x140038fa8  mov     r8d, [rsi+10h]; Size
0x140038fac  add     rdx, rsi; Src
0x140038faf  mov     [rdi+14h], ax
0x140038fb3  call    memmove
0x140038fb8  jmp     short loc_140038FC0
0x140038fba  xor     eax, eax
0x140038fbc  mov     [rdi+14h], ax
0x140038fc0  xor     r13b, r13b
0x140038fc3  lea     r12, WPP_RECORDER_INITIALIZED
0x140038fca  test    ebx, ebx
0x140038fcc  jz      short loc_140039036
0x140038fce  jmp     short loc_14003901A
0x140038fd0  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140038fd7  jz      short loc_14003900E
0x140038fd9  mov     rcx, cs:WPP_GLOBAL_Control
0x140038fe0  mov     r9d, 0ECh
0x140038fe6  mov     eax, [r15+10h]
0x140038fea  mov     r8d, r10d
0x140038fed  mov     [rsp+110h+var_D8], 14h
0x140038ff5  mov     dl, 2
0x140038ff7  mov     [rsp+110h+var_E0], r12d
0x140038ffc  mov     rcx, [rcx+40h]
0x140039000  mov     [rsp+110h+var_E8], eax
0x140039004  mov     [rsp+110h+var_F0], r11
0x140039009  call    WPP_RECORDER_SF_Ddd
0x14003900e  lea     r12, WPP_RECORDER_INITIALIZED
0x140039015  mov     ebx, 0C0040003h
0x14003901a  mov     esi, [rbp+4Fh+var_CC]
0x14003901d  mov     ecx, esi
0x14003901f  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140039024  test    eax, eax
0x140039026  jz      short loc_140039031
0x140039028  mov     ecx, esi
0x14003902a  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14003902f  mov     ebx, eax
0x140039031  test    r13b, r13b
0x140039034  jnz     short loc_140039048
0x140039036  mov     [rdi+4], ebx
0x140039039  mov     esi, 18h
0x14003903e  mov     [rbp+4Fh+var_C0.StatusBuffer], rdi
0x140039042  mov     [rbp+4Fh+var_C0.StatusBufferSize], r14d
0x140039046  jmp     short loc_14003906A
0x140039048  xorps   xmm0, xmm0
0x14003904b  mov     dword ptr [rbp+4Fh+var_50], 180180h
0x140039052  mov     esi, 18h
0x140039057  mov     dword ptr [rbp+4Fh+var_50+4], ebx
0x14003905a  lea     rax, [rbp+4Fh+var_50]
0x14003905e  mov     [rbp+4Fh+var_C0.StatusBufferSize], esi
0x140039061  movdqu  [rbp+4Fh+var_50+8], xmm0
0x140039066  mov     [rbp+4Fh+var_C0.StatusBuffer], rax
0x14003906a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140039071  jz      short loc_1400390A9
0x140039073  mov     eax, [r15+10h]
0x140039077  mov     r9d, 0EFh
0x14003907d  mov     rcx, cs:WPP_GLOBAL_Control
0x140039084  mov     r8d, 3
0x14003908a  mov     [rsp+110h+var_E0], ebx
0x14003908e  mov     dl, 4
0x140039090  mov     [rsp+110h+var_E8], eax
0x140039094  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003909b  mov     [rsp+110h+var_F0], rax
0x1400390a0  mov     rcx, [rcx+40h]
0x1400390a4  call    WPP_RECORDER_SF_DD
0x1400390a9  mov     rdx, [r15+68h]
0x1400390ad  test    rdx, rdx
0x1400390b0  jz      short loc_1400390D8
0x1400390b2  mov     rax, cs:WdfFunctions_01031
0x1400390b9  mov     r8, cs:off_14005DF38
0x1400390c0  mov     rcx, cs:WdfDriverGlobals
0x1400390c7  mov     rax, [rax+650h]
0x1400390ce  call    _guard_dispatch_icall
0x1400390d3  add     rax, rsi
0x1400390d6  jmp     short loc_1400390E9
0x1400390d8  mov     rax, [r15+30h]
0x1400390dc  mov     rdx, [rax]
0x1400390df  mov     rax, [rdx+478h]
0x1400390e6  mov     rax, [rax]
0x1400390e9  lea     rdx, [rbp+4Fh+var_C0]; struct _NDIS_STATUS_INDICATION *
0x1400390ed  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x1400390f0  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x1400390f5  test    rdi, rdi
0x1400390f8  jz      short loc_14003910B
0x1400390fa  xor     edx, edx; Tag
0x1400390fc  mov     rcx, rdi; P
0x1400390ff  call    cs:__imp_ExFreePoolWithTag
0x140039106  nop     dword ptr [rax+rax+00h]
0x14003910b  xor     eax, eax
0x14003910d  mov     rcx, [rbp+4Fh+var_38]
0x140039111  xor     rcx, rsp; StackCookie
0x140039114  call    __security_check_cookie
0x140039119  mov     rbx, [rsp+110h+arg_8]
0x140039121  add     rsp, 0E0h
0x140039128  pop     r15
0x14003912a  pop     r14
0x14003912c  pop     r13
0x14003912e  pop     r12
0x140039130  pop     rdi
0x140039131  pop     rsi
0x140039132  pop     rbp
0x140039133  retn
```
