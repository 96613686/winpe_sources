# MbbNdisDssWriteCompleteStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x14002e100`
- end: `0x14002e2a3`
- name: `?MbbNdisDssWriteCompleteStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `419`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400051ac`
- `0x140019f78`
- `0x14002e100`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## pseudocode

```c
__int64 __fastcall MbbNdisDssWriteCompleteStatusHandler(__int64 a1, unsigned int a2)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  int v6; // edx
  unsigned int v7; // eax
  __int64 v8; // rdx
  NDIS_HANDLE *v9; // rax
  __int64 v11; // [rsp+40h] [rbp-51h] BYREF
  struct _NDIS_STATUS_INDICATION v12; // [rsp+50h] [rbp-41h] BYREF

  memset(&v12, 0, sizeof(v12));
  v4 = *(_QWORD *)(a1 + 480);
  v11 = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01031 + 2104))(WdfDriverGlobals, v4, a2);
  v5 = *(_QWORD *)(a1 + 48);
  v11 = 0;
  v6 = 8;
  v12.Header = (NDIS_OBJECT_HEADER)7340440;
  v12.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v5 + 1144LL) + 16LL);
  v12.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v12.RequestId = *(PVOID *)(a1 + 432);
  v12.PortNumber = 0;
  *(_QWORD *)&v12.StatusCode = 1074008099;
  LODWORD(v11) = 524672;
  v12.Guid = 0;
  if ( a2 )
    v7 = a2 != 259 ? 0xC0040003 : 0;
  else
    v7 = 0;
  HIDWORD(v11) = v7;
  v12.StatusBuffer = &v11;
  v12.StatusBufferSize = 8;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      3,
      214,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v7);
  }
  v8 = *(_QWORD *)(a1 + 104);
  if ( v8 )
    v9 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                           WdfDriverGlobals,
                           v8,
                           off_14005DF38)
                       + 24);
  else
    v9 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v9, &v12);
  MbbReqMgrDerefRequest((struct _MBB_REQUEST_CONTEXT *)a1);
  return 0;
}

```

## disassembly

```asm
0x14002e100  mov     [rsp-8+arg_10], rbx
0x14002e105  push    rbp
0x14002e106  push    rsi
0x14002e107  push    rdi
0x14002e108  lea     rbp, [rsp-3Fh]
0x14002e10d  sub     rsp, 0D0h
0x14002e114  mov     rax, cs:__security_cookie
0x14002e11b  xor     rax, rsp
0x14002e11e  mov     [rbp+4Fh+var_20], rax
0x14002e122  mov     ebx, edx
0x14002e124  mov     rdi, rcx
0x14002e127  xor     edx, edx; Val
0x14002e129  lea     rcx, [rbp+4Fh+var_90]; void *
0x14002e12d  lea     r8d, [rdx+70h]; Size
0x14002e131  call    memset
0x14002e136  mov     rax, cs:WdfFunctions_01031
0x14002e13d  mov     r8d, ebx
0x14002e140  mov     rdx, [rdi+1E0h]
0x14002e147  mov     rcx, cs:WdfDriverGlobals
0x14002e14e  mov     [rbp+4Fh+var_A0], 0
0x14002e156  mov     rax, [rax+838h]
0x14002e15d  call    _guard_dispatch_icall
0x14002e162  mov     rax, [rdi+30h]
0x14002e166  xorps   xmm0, xmm0
0x14002e169  mov     [rbp+4Fh+var_A0], 0
0x14002e171  mov     edx, 8
0x14002e176  mov     dword ptr [rbp+4Fh+var_90.Header.Type], 700198h
0x14002e17d  mov     rcx, [rax]
0x14002e180  mov     rax, [rcx+478h]
0x14002e187  mov     rcx, [rax]
0x14002e18a  mov     rax, [rcx+10h]
0x14002e18e  mov     [rbp+4Fh+var_90.SourceHandle], rax
0x14002e192  mov     rax, [rdi+1B8h]
0x14002e199  mov     [rbp+4Fh+var_90.DestinationHandle], rax
0x14002e19d  mov     rax, [rdi+1B0h]
0x14002e1a4  mov     [rbp+4Fh+var_90.RequestId], rax
0x14002e1a8  mov     [rbp+4Fh+var_90.PortNumber], 0
0x14002e1af  mov     qword ptr [rbp+4Fh+var_90.StatusCode], 40041023h
0x14002e1b7  mov     dword ptr [rbp+4Fh+var_A0], 80180h
0x14002e1be  movups  xmmword ptr [rbp+4Fh+var_90.Guid.Data1], xmm0
0x14002e1c2  test    ebx, ebx
0x14002e1c4  jz      short loc_14002E1D7
0x14002e1c6  sub     ebx, 103h
0x14002e1cc  neg     ebx
0x14002e1ce  sbb     eax, eax
0x14002e1d0  and     eax, 0C0040003h
0x14002e1d5  jmp     short loc_14002E1D9
0x14002e1d7  xor     eax, eax
0x14002e1d9  lea     rcx, [rbp+4Fh+var_A0]
0x14002e1dd  mov     dword ptr [rbp+4Fh+var_A0+4], eax
0x14002e1e0  mov     [rbp+4Fh+var_90.StatusBuffer], rcx
0x14002e1e4  mov     [rbp+4Fh+var_90.StatusBufferSize], edx
0x14002e1e7  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002e1ee  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002e1f5  jz      short loc_14002E22C
0x14002e1f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e1fe  mov     r9d, 0D6h
0x14002e204  mov     [rsp+0E0h+var_B0], eax
0x14002e208  mov     r8d, 3
0x14002e20e  mov     eax, [rdi+10h]
0x14002e211  mov     dl, 4
0x14002e213  mov     [rsp+0E0h+var_B8], eax
0x14002e217  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002e21e  mov     rcx, [rcx+40h]
0x14002e222  mov     [rsp+0E0h+var_C0], rax
0x14002e227  call    WPP_RECORDER_SF_DD
0x14002e22c  mov     rdx, [rdi+68h]
0x14002e230  test    rdx, rdx
0x14002e233  jz      short loc_14002E25C
0x14002e235  mov     rax, cs:WdfFunctions_01031
0x14002e23c  mov     r8, cs:off_14005DF38
0x14002e243  mov     rcx, cs:WdfDriverGlobals
0x14002e24a  mov     rax, [rax+650h]
0x14002e251  call    _guard_dispatch_icall
0x14002e256  add     rax, 18h
0x14002e25a  jmp     short loc_14002E26D
0x14002e25c  mov     rax, [rdi+30h]
0x14002e260  mov     rdx, [rax]
0x14002e263  mov     rax, [rdx+478h]
0x14002e26a  mov     rax, [rax]
0x14002e26d  lea     rdx, [rbp+4Fh+var_90]; struct _NDIS_STATUS_INDICATION *
0x14002e271  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x14002e274  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14002e279  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x14002e27c  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x14002e281  xor     eax, eax
0x14002e283  mov     rcx, [rbp+4Fh+var_20]
0x14002e287  xor     rcx, rsp; StackCookie
0x14002e28a  call    __security_check_cookie
0x14002e28f  mov     rbx, [rsp+0E0h+arg_10]
0x14002e297  add     rsp, 0D0h
0x14002e29e  pop     rdi
0x14002e29f  pop     rsi
0x14002e2a0  pop     rbp
0x14002e2a1  retn
```
