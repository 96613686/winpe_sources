# MbbNdisIndicatePacketServiceFailure(_MBB_REQUEST_CONTEXT *,ulong)

- ea: `0x14002f0c8`
- end: `0x14002f21f`
- name: `?MbbNdisIndicatePacketServiceFailure@@YAXPEAU_MBB_REQUEST_CONTEXT@@K@Z`
- size: `343`
- prototype: `void __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x1400128b0`
- `0x14002ec90`

## callees

- `0x140001db8`
- `0x14002f0c8`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## pseudocode

```c
void __fastcall MbbNdisIndicatePacketServiceFailure(struct _MBB_REQUEST_CONTEXT *a1, int a2)
{
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rdx
  NDIS_HANDLE *v7; // rax
  struct _NDIS_STATUS_INDICATION v8; // [rsp+30h] [rbp-59h] BYREF
  _DWORD v9[2]; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v10; // [rsp+A8h] [rbp+1Fh]
  _BYTE v11[28]; // [rsp+B0h] [rbp+27h] BYREF

  memset(&v8.Header + 1, 0, 0x6Cu);
  v4 = *((_QWORD *)a1 + 6);
  v10 = 0;
  v9[0] = 2883968;
  v5 = 44;
  memset(v11, 0, sizeof(v11));
  v9[1] = a2;
  v8.Header = (NDIS_OBJECT_HEADER)7340440;
  v8.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v4 + 1144LL) + 16LL);
  v8.DestinationHandle = (NDIS_HANDLE)*((_QWORD *)a1 + 55);
  v8.RequestId = (PVOID)*((_QWORD *)a1 + 54);
  v8.StatusBuffer = v9;
  v8.PortNumber = 0;
  *(_QWORD *)&v8.StatusCode = 1074008073;
  v8.Guid = 0;
  v8.StatusBufferSize = 44;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      75,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *((_DWORD *)a1 + 4),
      *(_QWORD *)&v8.Header.Type,
      v8.SourceHandle,
      *(_QWORD *)&v8.PortNumber,
      *(_QWORD *)&v8.Flags,
      v8.DestinationHandle,
      v8.RequestId,
      v8.StatusBuffer,
      *(_QWORD *)&v8.StatusBufferSize,
      *(_QWORD *)&v8.Guid.Data2,
      *(_QWORD *)&v8.Guid.Data4[4]);
  }
  v6 = *((_QWORD *)a1 + 13);
  if ( v6 )
    v7 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                           WdfDriverGlobals,
                           v6,
                           off_14005DF38)
                       + 24);
  else
    v7 = **(NDIS_HANDLE ***)(**((_QWORD **)a1 + 6) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v7, &v8);
}

```

## disassembly

```asm
0x14002f0c8  mov     [rsp-8+arg_10], rbx
0x14002f0cd  mov     [rsp-8+arg_18], rdi
0x14002f0d2  push    rbp
0x14002f0d3  lea     rbp, [rsp-57h]
0x14002f0d8  sub     rsp, 0E0h
0x14002f0df  mov     rax, cs:__security_cookie
0x14002f0e6  xor     rax, rsp
0x14002f0e9  mov     [rbp+57h+var_10], rax
0x14002f0ed  mov     ebx, edx
0x14002f0ef  mov     rdi, rcx
0x14002f0f2  xor     edx, edx; Val
0x14002f0f4  lea     rcx, [rbp+57h+var_B0+4]; void *
0x14002f0f8  lea     r8d, [rdx+6Ch]; Size
0x14002f0fc  call    memset
0x14002f101  mov     rax, [rdi+30h]
0x14002f105  xorps   xmm0, xmm0
0x14002f108  movups  [rbp+57h+var_40], xmm0
0x14002f10c  mov     dword ptr [rbp+57h+var_40], 2C0180h
0x14002f113  mov     edx, 2Ch ; ','
0x14002f118  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x14002f11c  mov     dword ptr [rbp+57h+var_40+4], ebx
0x14002f11f  movups  xmmword ptr [rbp+57h+var_30+0Ch], xmm0
0x14002f123  mov     dword ptr [rbp+57h+var_B0.Header.Type], 700198h
0x14002f12a  mov     rcx, [rax]
0x14002f12d  mov     rax, [rcx+478h]
0x14002f134  mov     rcx, [rax]
0x14002f137  mov     rax, [rcx+10h]
0x14002f13b  mov     [rbp+57h+var_B0.SourceHandle], rax
0x14002f13f  mov     rax, [rdi+1B8h]
0x14002f146  mov     [rbp+57h+var_B0.DestinationHandle], rax
0x14002f14a  mov     rax, [rdi+1B0h]
0x14002f151  mov     [rbp+57h+var_B0.RequestId], rax
0x14002f155  lea     rax, [rbp+57h+var_40]
0x14002f159  mov     [rbp+57h+var_B0.StatusBuffer], rax
0x14002f15d  mov     [rbp+57h+var_B0.PortNumber], 0
0x14002f164  mov     qword ptr [rbp+57h+var_B0.StatusCode], 40041009h
0x14002f16c  movups  xmmword ptr [rbp+57h+var_B0.Guid.Data1], xmm0
0x14002f170  mov     [rbp+57h+var_B0.StatusBufferSize], edx
0x14002f173  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f17a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f181  jz      short loc_14002F1B0
0x14002f183  mov     eax, [rdi+10h]
0x14002f186  lea     r9d, [rdx+1Fh]
0x14002f18a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f191  lea     r8d, [rdx-29h]
0x14002f195  mov     [rsp+0E0h+var_B8], eax
0x14002f199  mov     dl, 2
0x14002f19b  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002f1a2  mov     [rsp+0E0h+var_C0], rax
0x14002f1a7  mov     rcx, [rcx+40h]
0x14002f1ab  call    WPP_RECORDER_SF_d
0x14002f1b0  mov     rdx, [rdi+68h]
0x14002f1b4  test    rdx, rdx
0x14002f1b7  jz      short loc_14002F1E0
0x14002f1b9  mov     rax, cs:WdfFunctions_01031
0x14002f1c0  mov     r8, cs:off_14005DF38
0x14002f1c7  mov     rcx, cs:WdfDriverGlobals
0x14002f1ce  mov     rax, [rax+650h]
0x14002f1d5  call    _guard_dispatch_icall
0x14002f1da  add     rax, 18h
0x14002f1de  jmp     short loc_14002F1F1
0x14002f1e0  mov     rax, [rdi+30h]
0x14002f1e4  mov     rcx, [rax]
0x14002f1e7  mov     rax, [rcx+478h]
0x14002f1ee  mov     rax, [rax]
0x14002f1f1  lea     rdx, [rbp+57h+var_B0]; struct _NDIS_STATUS_INDICATION *
0x14002f1f5  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x14002f1f8  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14002f1fd  mov     rcx, [rbp+57h+var_10]
0x14002f201  xor     rcx, rsp; StackCookie
0x14002f204  call    __security_check_cookie
0x14002f209  lea     r11, [rsp+0E0h+var_s0]
0x14002f211  mov     rbx, [r11+20h]
0x14002f215  mov     rdi, [r11+28h]
0x14002f219  mov     rsp, r11
0x14002f21c  pop     rbp
0x14002f21d  retn
```
