# MbbNdisDssStateStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong,_WWAN_DEVICE_SERVICE_SESSION_STATE)

- ea: `0x14002deb8`
- end: `0x14002e0eb`
- name: `?MbbNdisDssStateStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEKW4_WWAN_DEVICE_SERVICE_SESSION_STATE@@@Z`
- size: `563`
- prototype: `__int64 __fastcall(__int64, int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x14002dea0`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x14002deb8`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## pseudocode

```c
__int64 __fastcall MbbNdisDssStateStatusHandler(__int64 a1, int a2, unsigned int a3)
{
  int v6; // edx
  __int64 v8; // rax
  bool v9; // zf
  __int128 v10; // xmm0
  __int32 v11; // eax
  __int64 v12; // rdx
  NDIS_HANDLE *v13; // rax
  struct _NDIS_STATUS_INDICATION v14; // [rsp+40h] [rbp-79h] BYREF
  __m256i v15; // [rsp+B0h] [rbp-9h] BYREF

  memset(&v14.Header + 1, 0, 0x6Cu);
  if ( *(_BYTE *)(a1 + 576) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        3,
        211,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16));
    }
    return 65539;
  }
  else
  {
    v8 = *(_QWORD *)(a1 + 48);
    v14.Header = (NDIS_OBJECT_HEADER)7340440;
    *(_OWORD *)&v15.m256i_u64[2] = 0;
    *(_OWORD *)v15.m256i_i8 = 0;
    v14.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v8 + 1144LL) + 16LL);
    v14.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
    v14.RequestId = *(PVOID *)(a1 + 432);
    v9 = *(_DWORD *)(a1 + 748) == 1;
    v14.Guid = 0;
    v14.PortNumber = 0;
    v10 = *(_OWORD *)(a1 + 728);
    *(_QWORD *)&v14.StatusCode = 1074008098;
    v15.m256i_i32[0] = 2097536;
    v15.m256i_i32[6] = !v9 + 1;
    v15.m256i_i32[7] = *(_DWORD *)(a1 + 744);
    *(_OWORD *)&v15.m256i_u64[1] = v10;
    if ( a2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          3,
          212,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *(_DWORD *)(a1 + 16),
          a2);
      }
      v11 = -1073479677;
    }
    else
    {
      v11 = MbbUtilMbbToWwanStatus(a3);
    }
    v15.m256i_i32[1] = v11;
    v14.StatusBuffer = &v15;
    v14.StatusBufferSize = 32;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        3,
        213,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v11);
    }
    v12 = *(_QWORD *)(a1 + 104);
    if ( v12 )
      v13 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031
                                                                                               + 1616))(
                              WdfDriverGlobals,
                              v12,
                              off_14005DF38)
                          + 24);
    else
      v13 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
    MbbUtilNdisMiniportIndicateStatusEx(v13, &v14);
    return 0;
  }
}

```

## disassembly

```asm
0x14002deb8  mov     [rsp-8+arg_8], rbx
0x14002debd  mov     [rsp-8+arg_18], rsi
0x14002dec2  push    rbp
0x14002dec3  push    rdi
0x14002dec4  push    r13
0x14002dec6  push    r14
0x14002dec8  push    r15
0x14002deca  lea     rbp, [rsp-27h]
0x14002decf  sub     rsp, 0E0h
0x14002ded6  mov     rax, cs:__security_cookie
0x14002dedd  xor     rax, rsp
0x14002dee0  mov     [rbp+47h+var_30], rax
0x14002dee4  mov     r14d, edx
0x14002dee7  mov     r15d, r8d
0x14002deea  xor     edx, edx; Val
0x14002deec  mov     rbx, rcx
0x14002deef  lea     rcx, [rbp+47h+var_C0+4]; void *
0x14002def3  lea     r8d, [rdx+6Ch]; Size
0x14002def7  call    memset
0x14002defc  cmp     byte ptr [rbx+240h], 0
0x14002df03  jz      short loc_14002DF50
0x14002df05  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002df0c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002df13  jz      short loc_14002DF46
0x14002df15  mov     rcx, cs:WPP_GLOBAL_Control
0x14002df1c  lea     rsi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002df23  mov     eax, [rbx+10h]
0x14002df26  mov     r9d, 0D3h
0x14002df2c  mov     [rsp+100h+var_D8], eax
0x14002df30  mov     r8d, 3
0x14002df36  mov     dl, 2
0x14002df38  mov     [rsp+100h+var_E0], rsi
0x14002df3d  mov     rcx, [rcx+40h]
0x14002df41  call    WPP_RECORDER_SF_d
0x14002df46  mov     eax, 10003h
0x14002df4b  jmp     loc_14002E0C2
0x14002df50  mov     rax, [rbx+30h]
0x14002df54  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002df5b  xorps   xmm0, xmm0
0x14002df5e  mov     dword ptr [rbp+47h+var_C0.Header.Type], 700198h
0x14002df65  movups  [rbp+47h+var_40], xmm0
0x14002df69  lea     rsi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002df70  movups  [rbp+47h+var_50], xmm0
0x14002df74  mov     rcx, [rax]
0x14002df77  mov     rax, [rcx+478h]
0x14002df7e  mov     rcx, [rax]
0x14002df81  mov     rax, [rcx+10h]
0x14002df85  mov     [rbp+47h+var_C0.SourceHandle], rax
0x14002df89  mov     rax, [rbx+1B8h]
0x14002df90  mov     [rbp+47h+var_C0.DestinationHandle], rax
0x14002df94  mov     rax, [rbx+1B0h]
0x14002df9b  mov     [rbp+47h+var_C0.RequestId], rax
0x14002df9f  xor     eax, eax
0x14002dfa1  cmp     dword ptr [rbx+2ECh], 1
0x14002dfa8  movups  xmmword ptr [rbp+47h+var_C0.Guid.Data1], xmm0
0x14002dfac  mov     [rbp+47h+var_C0.PortNumber], 0
0x14002dfb3  movups  xmm0, xmmword ptr [rbx+2D8h]
0x14002dfba  lea     r13d, [rax+20h]
0x14002dfbe  mov     qword ptr [rbp+47h+var_C0.StatusCode], 40041022h
0x14002dfc6  setnz   al
0x14002dfc9  mov     dword ptr [rbp+47h+var_50], 200180h
0x14002dfd0  inc     eax
0x14002dfd2  mov     dword ptr [rbp+47h+var_40+8], eax
0x14002dfd5  mov     eax, [rbx+2E8h]
0x14002dfdb  mov     dword ptr [rbp+47h+var_40+0Ch], eax
0x14002dfde  movdqu  [rbp+47h+var_50+8], xmm0
0x14002dfe3  test    r14d, r14d
0x14002dfe6  jz      short loc_14002E025
0x14002dfe8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002dfef  jz      short loc_14002E01E
0x14002dff1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dff8  lea     r8d, [r13-1Dh]
0x14002dffc  mov     eax, [rbx+10h]
0x14002dfff  mov     r9d, 0D4h
0x14002e005  mov     [rsp+100h+var_D0], r14d
0x14002e00a  mov     dl, 2
0x14002e00c  mov     [rsp+100h+var_D8], eax
0x14002e010  mov     rcx, [rcx+40h]
0x14002e014  mov     [rsp+100h+var_E0], rsi
0x14002e019  call    WPP_RECORDER_SF_DD
0x14002e01e  mov     eax, 0C0040003h
0x14002e023  jmp     short loc_14002E02D
0x14002e025  mov     ecx, r15d
0x14002e028  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002e02d  lea     rcx, [rbp+47h+var_50]
0x14002e031  mov     dword ptr [rbp+47h+var_50+4], eax
0x14002e034  mov     [rbp+47h+var_C0.StatusBuffer], rcx
0x14002e038  mov     [rbp+47h+var_C0.StatusBufferSize], r13d
0x14002e03c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14002e043  jz      short loc_14002E073
0x14002e045  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e04c  mov     r9d, 0D5h
0x14002e052  mov     [rsp+100h+var_D0], eax
0x14002e056  mov     r8d, 3
0x14002e05c  mov     eax, [rbx+10h]
0x14002e05f  mov     dl, 4
0x14002e061  mov     [rsp+100h+var_D8], eax
0x14002e065  mov     rcx, [rcx+40h]
0x14002e069  mov     [rsp+100h+var_E0], rsi
0x14002e06e  call    WPP_RECORDER_SF_DD
0x14002e073  mov     rdx, [rbx+68h]
0x14002e077  test    rdx, rdx
0x14002e07a  jz      short loc_14002E0A3
0x14002e07c  mov     rax, cs:WdfFunctions_01031
0x14002e083  mov     r8, cs:off_14005DF38
0x14002e08a  mov     rcx, cs:WdfDriverGlobals
0x14002e091  mov     rax, [rax+650h]
0x14002e098  call    _guard_dispatch_icall
0x14002e09d  add     rax, 18h
0x14002e0a1  jmp     short loc_14002E0B4
0x14002e0a3  mov     rax, [rbx+30h]
0x14002e0a7  mov     rcx, [rax]
0x14002e0aa  mov     rax, [rcx+478h]
0x14002e0b1  mov     rax, [rax]
0x14002e0b4  lea     rdx, [rbp+47h+var_C0]; struct _NDIS_STATUS_INDICATION *
0x14002e0b8  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x14002e0bb  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14002e0c0  xor     eax, eax
0x14002e0c2  mov     rcx, [rbp+47h+var_30]
0x14002e0c6  xor     rcx, rsp; StackCookie
0x14002e0c9  call    __security_check_cookie
0x14002e0ce  lea     r11, [rsp+100h+var_20]
0x14002e0d6  mov     rbx, [r11+38h]
0x14002e0da  mov     rsi, [r11+48h]
0x14002e0de  mov     rsp, r11
0x14002e0e1  pop     r15
0x14002e0e3  pop     r14
0x14002e0e5  pop     r13
0x14002e0e7  pop     rdi
0x14002e0e8  pop     rbp
0x14002e0e9  retn
```
