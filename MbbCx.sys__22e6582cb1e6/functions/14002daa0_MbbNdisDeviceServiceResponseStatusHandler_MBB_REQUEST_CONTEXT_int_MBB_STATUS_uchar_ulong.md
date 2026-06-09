# MbbNdisDeviceServiceResponseStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x14002daa0`
- end: `0x14002ddc8`
- name: `?MbbNdisDeviceServiceResponseStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `808`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, const void *, unsigned int Size)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x14002ddd0`

## callees

- `0x1400051ac`
- `0x14002daa0`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002dce0`
- `ntoskrnl!ExAllocatePool2` at `0x14002dce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dd84`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dd84`

## pseudocode

```c
__int64 __fastcall MbbNdisDeviceServiceResponseStatusHandler(
        __int64 a1,
        int a2,
        unsigned int a3,
        const void *a4,
        unsigned int Size)
{
  int v9; // edx
  __int64 v10; // rax
  _DWORD *v11; // rdi
  int v12; // ebx
  int v13; // edx
  __int128 v14; // xmm0
  _DWORD *v15; // rax
  __int64 v16; // rdx
  NDIS_HANDLE *v17; // rax
  int v18; // r9d
  __int64 Pool2; // rax
  __int64 result; // rax
  struct _NDIS_STATUS_INDICATION v21; // [rsp+40h] [rbp-81h] BYREF
  _OWORD v22[2]; // [rsp+B0h] [rbp-11h] BYREF

  memset(&v21.Header + 1, 0, 0x6Cu);
  v10 = *(_QWORD *)(a1 + 48);
  memset(v22, 0, sizeof(v22));
  v21.Header = (NDIS_OBJECT_HEADER)7340440;
  v11 = 0;
  v21.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v10 + 1144LL) + 16LL);
  v21.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v21.RequestId = *(PVOID *)(a1 + 432);
  v21.PortNumber = 0;
  *(_QWORD *)&v21.StatusCode = 1074008088;
  v21.Guid = 0;
  if ( a2 )
  {
    v12 = -1073479677;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        185,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
    goto LABEL_4;
  }
  v12 = MbbUtilMbbToWwanStatus(a3);
  if ( v12 )
  {
LABEL_4:
    if ( (unsigned int)MbbUtilMbbToWwanStatus(a3) )
      v12 = MbbUtilMbbToWwanStatus(a3);
    v14 = *(_OWORD *)(a1 + 704);
    *((_QWORD *)&v22[1] + 1) = *(unsigned int *)(a1 + 720);
    v15 = v22;
    LODWORD(v22[0]) = 2097536;
    *(_OWORD *)((char *)v22 + 8) = v14;
    v21.StatusBufferSize = 32;
    goto LABEL_7;
  }
  if ( Size > 0xFFFFFFDF )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_16:
      v12 = -1073479677;
      goto LABEL_4;
    }
    v18 = 186;
LABEL_15:
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      3,
      v18,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      Size);
    goto LABEL_16;
  }
  Pool2 = ExAllocatePool2(64, Size + 32, 1683505741);
  v11 = (_DWORD *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_16;
    v18 = 187;
    goto LABEL_15;
  }
  *(_DWORD *)Pool2 = 2097536;
  *(_DWORD *)(Pool2 + 28) = Size;
  *(_OWORD *)(Pool2 + 8) = *(_OWORD *)(a1 + 704);
  *(_DWORD *)(Pool2 + 24) = *(_DWORD *)(a1 + 720);
  if ( Size )
    memmove((void *)(Pool2 + 32), a4, Size);
  v15 = v11;
  v21.StatusBufferSize = Size + 32;
LABEL_7:
  v21.StatusBuffer = v15;
  v15[1] = v12;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      3,
      188,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v12);
  }
  v16 = *(_QWORD *)(a1 + 104);
  if ( v16 )
    v17 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                            WdfDriverGlobals,
                            v16,
                            off_14005DF38)
                        + 24);
  else
    v17 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v17, &v21);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  result = 259;
  if ( v12 != 1074004232 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14002daa0  mov     [rsp-8+arg_8], rbx
0x14002daa5  push    rbp
0x14002daa6  push    rsi
0x14002daa7  push    rdi
0x14002daa8  push    r12
0x14002daaa  push    r13
0x14002daac  push    r14
0x14002daae  push    r15
0x14002dab0  lea     rbp, [rsp-1Fh]
0x14002dab5  sub     rsp, 0E0h
0x14002dabc  mov     rax, cs:__security_cookie
0x14002dac3  xor     rax, rsp
0x14002dac6  mov     [rbp+4Fh+var_40], rax
0x14002daca  mov     r14d, edx
0x14002dacd  mov     r15d, r8d
0x14002dad0  xor     edx, edx; Val
0x14002dad2  mov     rsi, rcx
0x14002dad5  lea     rcx, [rbp+4Fh+var_D0+4]; void *
0x14002dad9  mov     r13, r9
0x14002dadc  lea     r8d, [rdx+6Ch]; Size
0x14002dae0  call    memset
0x14002dae5  mov     rax, [rsi+30h]
0x14002dae9  xorps   xmm0, xmm0
0x14002daec  movups  [rbp+4Fh+var_60], xmm0
0x14002daf0  mov     dword ptr [rsp+110h+var_D0.Header.Type], 700198h
0x14002daf8  xor     edi, edi
0x14002dafa  movups  [rbp+4Fh+var_50], xmm0
0x14002dafe  mov     rcx, [rax]
0x14002db01  xor     r12d, r12d
0x14002db04  mov     rax, [rcx+478h]
0x14002db0b  mov     rcx, [rax]
0x14002db0e  mov     rax, [rcx+10h]
0x14002db12  lea     rcx, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002db19  mov     [rbp+4Fh+var_D0.SourceHandle], rax
0x14002db1d  mov     rax, [rsi+1B8h]
0x14002db24  mov     [rbp+4Fh+var_D0.DestinationHandle], rax
0x14002db28  mov     rax, [rsi+1B0h]
0x14002db2f  mov     [rbp+4Fh+var_D0.RequestId], rax
0x14002db33  lea     rax, WPP_RECORDER_INITIALIZED
0x14002db3a  mov     [rbp+4Fh+var_D0.PortNumber], edi
0x14002db3d  mov     qword ptr [rbp+4Fh+var_D0.StatusCode], 40041018h
0x14002db45  movups  xmmword ptr [rbp+4Fh+var_D0.Guid.Data1], xmm0
0x14002db49  test    r14d, r14d
0x14002db4c  jz      loc_14002DC59
0x14002db52  mov     ebx, 0C0040003h
0x14002db57  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002db5e  jz      short loc_14002DB8E
0x14002db60  mov     eax, [rsi+10h]
0x14002db63  lea     r8d, [r12+3]
0x14002db68  mov     [rsp+110h+var_E0], r14d
0x14002db6d  mov     r9d, 0B9h
0x14002db73  mov     [rsp+110h+var_E8], eax
0x14002db77  mov     dl, 2
0x14002db79  mov     [rsp+110h+var_F0], rcx
0x14002db7e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002db85  mov     rcx, [rcx+40h]
0x14002db89  call    WPP_RECORDER_SF_DD
0x14002db8e  lea     r13, WPP_RECORDER_INITIALIZED
0x14002db95  lea     r14, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002db9c  mov     ecx, r15d
0x14002db9f  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002dba4  test    eax, eax
0x14002dba6  jz      short loc_14002DBB2
0x14002dba8  mov     ecx, r15d
0x14002dbab  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002dbb0  mov     ebx, eax
0x14002dbb2  test    rdi, rdi
0x14002dbb5  jnz     loc_14002DD50
0x14002dbbb  mov     eax, [rsi+2D0h]
0x14002dbc1  lea     ecx, [rdi+20h]
0x14002dbc4  movups  xmm0, xmmword ptr [rsi+2C0h]
0x14002dbcb  mov     dword ptr [rbp+4Fh+var_50+8], eax
0x14002dbce  lea     rax, [rbp+4Fh+var_60]
0x14002dbd2  mov     dword ptr [rbp+4Fh+var_60], 200180h
0x14002dbd9  movdqu  [rbp+4Fh+var_60+8], xmm0
0x14002dbde  mov     dword ptr [rbp+4Fh+var_50+0Ch], edi
0x14002dbe1  mov     [rbp+4Fh+var_D0.StatusBufferSize], ecx
0x14002dbe4  mov     [rbp+4Fh+var_D0.StatusBuffer], rax
0x14002dbe8  mov     [rax+4], ebx
0x14002dbeb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14002dbf2  jz      short loc_14002DC22
0x14002dbf4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dbfb  mov     r9d, 0BCh
0x14002dc01  mov     eax, [rsi+10h]
0x14002dc04  mov     r8d, 3
0x14002dc0a  mov     [rsp+110h+var_E0], ebx
0x14002dc0e  mov     dl, 4
0x14002dc10  mov     [rsp+110h+var_E8], eax
0x14002dc14  mov     rcx, [rcx+40h]
0x14002dc18  mov     [rsp+110h+var_F0], r14
0x14002dc1d  call    WPP_RECORDER_SF_DD
0x14002dc22  mov     rdx, [rsi+68h]
0x14002dc26  test    rdx, rdx
0x14002dc29  jz      loc_14002DD5C
0x14002dc2f  mov     rax, cs:WdfFunctions_01031
0x14002dc36  mov     r8, cs:off_14005DF38
0x14002dc3d  mov     rcx, cs:WdfDriverGlobals
0x14002dc44  mov     rax, [rax+650h]
0x14002dc4b  call    _guard_dispatch_icall
0x14002dc50  add     rax, 18h
0x14002dc54  jmp     loc_14002DD6D
0x14002dc59  mov     ecx, r15d
0x14002dc5c  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002dc61  mov     ebx, eax
0x14002dc63  test    eax, eax
0x14002dc65  jnz     loc_14002DB8E
0x14002dc6b  mov     r14d, dword ptr [rbp+4Fh+Size]
0x14002dc6f  cmp     r14d, 0FFFFFFDFh
0x14002dc73  jbe     short loc_14002DCCE
0x14002dc75  lea     r13, WPP_RECORDER_INITIALIZED
0x14002dc7c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14002dc83  jz      short loc_14002DCBD
0x14002dc85  mov     r9d, 0BAh
0x14002dc8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dc92  mov     r8d, 3
0x14002dc98  mov     eax, [rsi+10h]
0x14002dc9b  mov     dl, 2
0x14002dc9d  mov     [rsp+110h+var_E0], r14d
0x14002dca2  lea     r14, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002dca9  mov     [rsp+110h+var_E8], eax
0x14002dcad  mov     rcx, [rcx+40h]
0x14002dcb1  mov     [rsp+110h+var_F0], r14
0x14002dcb6  call    WPP_RECORDER_SF_DD
0x14002dcbb  jmp     short loc_14002DCC4
0x14002dcbd  lea     r14, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002dcc4  mov     ebx, 0C0040003h
0x14002dcc9  jmp     loc_14002DB9C
0x14002dcce  lea     r12d, [r14+20h]
0x14002dcd2  mov     ecx, 40h ; '@'
0x14002dcd7  mov     edx, r12d
0x14002dcda  mov     r8d, 6458424Dh
0x14002dce0  call    cs:__imp_ExAllocatePool2
0x14002dce7  nop     dword ptr [rax+rax+00h]
0x14002dcec  mov     rdi, rax
0x14002dcef  test    rax, rax
0x14002dcf2  jnz     short loc_14002DD0F
0x14002dcf4  lea     r13, WPP_RECORDER_INITIALIZED
0x14002dcfb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14002dd02  jz      short loc_14002DCBD
0x14002dd04  mov     r9d, 0BBh
0x14002dd0a  jmp     loc_14002DC8B
0x14002dd0f  mov     dword ptr [rax], 200180h
0x14002dd15  mov     [rdi+1Ch], r14d
0x14002dd19  movups  xmm0, xmmword ptr [rsi+2C0h]
0x14002dd20  movdqu  xmmword ptr [rax+8], xmm0
0x14002dd25  mov     eax, [rsi+2D0h]
0x14002dd2b  mov     [rdi+18h], eax
0x14002dd2e  test    r14d, r14d
0x14002dd31  jz      short loc_14002DD42
0x14002dd33  mov     r8, r14; Size
0x14002dd36  lea     rcx, [rdi+20h]; void *
0x14002dd3a  mov     rdx, r13; Src
0x14002dd3d  call    memmove
0x14002dd42  lea     r14, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002dd49  lea     r13, WPP_RECORDER_INITIALIZED
0x14002dd50  mov     rax, rdi
0x14002dd53  mov     [rbp+4Fh+var_D0.StatusBufferSize], r12d
0x14002dd57  jmp     loc_14002DBE4
0x14002dd5c  mov     rax, [rsi+30h]
0x14002dd60  mov     rdx, [rax]
0x14002dd63  mov     rax, [rdx+478h]
0x14002dd6a  mov     rax, [rax]
0x14002dd6d  lea     rdx, [rsp+110h+var_D0]; struct _NDIS_STATUS_INDICATION *
0x14002dd72  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x14002dd75  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14002dd7a  test    rdi, rdi
0x14002dd7d  jz      short loc_14002DD90
0x14002dd7f  xor     edx, edx; Tag
0x14002dd81  mov     rcx, rdi; P
0x14002dd84  call    cs:__imp_ExFreePoolWithTag
0x14002dd8b  nop     dword ptr [rax+rax+00h]
0x14002dd90  xor     ecx, ecx
0x14002dd92  mov     eax, 103h
0x14002dd97  cmp     ebx, 40040108h
0x14002dd9d  cmovnz  eax, ecx
0x14002dda0  mov     rcx, [rbp+4Fh+var_40]
0x14002dda4  xor     rcx, rsp; StackCookie
0x14002dda7  call    __security_check_cookie
0x14002ddac  mov     rbx, [rsp+110h+arg_8]
0x14002ddb4  add     rsp, 0E0h
0x14002ddbb  pop     r15
0x14002ddbd  pop     r14
0x14002ddbf  pop     r13
0x14002ddc1  pop     r12
0x14002ddc3  pop     rdi
0x14002ddc4  pop     rsi
0x14002ddc5  pop     rbp
0x14002ddc6  retn
```
