# MbbNdisSmsDeleteStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140036be0`
- end: `0x140036d8d`
- name: `?MbbNdisSmsDeleteStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `429`
- prototype: `__int64 __fastcall(__int64, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400051ac`
- `0x140036be0`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## pseudocode

```c
__int64 __fastcall MbbNdisSmsDeleteStatusHandler(__int64 a1, int a2, unsigned int a3)
{
  int v6; // edx
  __int64 v7; // rax
  int v8; // edi
  __int64 v9; // rdx
  NDIS_HANDLE *v10; // rax
  __int64 v12; // [rsp+40h] [rbp-61h] BYREF
  struct _NDIS_STATUS_INDICATION v13; // [rsp+50h] [rbp-51h] BYREF

  memset(&v13.Header + 1, 0, 0x6Cu);
  v7 = *(_QWORD *)(a1 + 48);
  v12 = 0;
  v13.Header = (NDIS_OBJECT_HEADER)7340440;
  v13.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v7 + 1144LL) + 16LL);
  v13.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v13.RequestId = *(PVOID *)(a1 + 432);
  v13.PortNumber = 0;
  *(_QWORD *)&v13.StatusCode = 1074008081;
  LODWORD(v12) = 524672;
  v13.Guid = 0;
  if ( a2 )
  {
    v8 = -1073479677;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        3,
        167,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
  }
  else
  {
    v8 = MbbUtilMbbToWwanStatus(a3);
  }
  HIDWORD(v12) = v8;
  v13.StatusBuffer = &v12;
  v13.StatusBufferSize = 8;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      3,
      168,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v8);
  }
  v9 = *(_QWORD *)(a1 + 104);
  if ( v9 )
    v10 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                            WdfDriverGlobals,
                            v9,
                            off_14005DF38)
                        + 24);
  else
    v10 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v10, &v13);
  return 0;
}

```

## disassembly

```asm
0x140036be0  mov     [rsp-8+arg_8], rbx
0x140036be5  push    rbp
0x140036be6  push    rsi
0x140036be7  push    rdi
0x140036be8  push    r13
0x140036bea  push    r14
0x140036bec  lea     rbp, [rsp-2Fh]
0x140036bf1  sub     rsp, 0D0h
0x140036bf8  mov     rax, cs:__security_cookie
0x140036bff  xor     rax, rsp
0x140036c02  mov     [rbp+4Fh+var_30], rax
0x140036c06  mov     esi, edx
0x140036c08  mov     edi, r8d
0x140036c0b  xor     edx, edx; Val
0x140036c0d  mov     rbx, rcx
0x140036c10  lea     rcx, [rbp+4Fh+var_A0+4]; void *
0x140036c14  lea     r8d, [rdx+6Ch]; Size
0x140036c18  call    memset
0x140036c1d  mov     rax, [rbx+30h]
0x140036c21  xorps   xmm0, xmm0
0x140036c24  mov     [rbp+4Fh+var_B0], 0
0x140036c2c  lea     r13, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140036c33  mov     dword ptr [rbp+4Fh+var_A0.Header.Type], 700198h
0x140036c3a  lea     r14, WPP_RECORDER_INITIALIZED
0x140036c41  mov     rcx, [rax]
0x140036c44  mov     rax, [rcx+478h]
0x140036c4b  mov     rcx, [rax]
0x140036c4e  mov     rax, [rcx+10h]
0x140036c52  mov     [rbp+4Fh+var_A0.SourceHandle], rax
0x140036c56  mov     rax, [rbx+1B8h]
0x140036c5d  mov     [rbp+4Fh+var_A0.DestinationHandle], rax
0x140036c61  mov     rax, [rbx+1B0h]
0x140036c68  mov     [rbp+4Fh+var_A0.RequestId], rax
0x140036c6c  mov     [rbp+4Fh+var_A0.PortNumber], 0
0x140036c73  mov     qword ptr [rbp+4Fh+var_A0.StatusCode], 40041011h
0x140036c7b  mov     dword ptr [rbp+4Fh+var_B0], 80180h
0x140036c82  movups  xmmword ptr [rbp+4Fh+var_A0.Guid.Data1], xmm0
0x140036c86  test    esi, esi
0x140036c88  jz      short loc_140036CC8
0x140036c8a  mov     edi, 0C0040003h
0x140036c8f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140036c96  jz      short loc_140036CD1
0x140036c98  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c9f  mov     r9d, 0A7h
0x140036ca5  mov     eax, [rbx+10h]
0x140036ca8  mov     r8d, 3
0x140036cae  mov     [rsp+0F0h+var_C0], esi
0x140036cb2  mov     dl, 2
0x140036cb4  mov     [rsp+0F0h+var_C8], eax
0x140036cb8  mov     rcx, [rcx+40h]
0x140036cbc  mov     [rsp+0F0h+var_D0], r13
0x140036cc1  call    WPP_RECORDER_SF_DD
0x140036cc6  jmp     short loc_140036CD1
0x140036cc8  mov     ecx, edi
0x140036cca  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140036ccf  mov     edi, eax
0x140036cd1  lea     rax, [rbp+4Fh+var_B0]
0x140036cd5  mov     dword ptr [rbp+4Fh+var_B0+4], edi
0x140036cd8  mov     [rbp+4Fh+var_A0.StatusBuffer], rax
0x140036cdc  mov     [rbp+4Fh+var_A0.StatusBufferSize], 8
0x140036ce3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140036cea  jz      short loc_140036D1A
0x140036cec  mov     rcx, cs:WPP_GLOBAL_Control
0x140036cf3  mov     r9d, 0A8h
0x140036cf9  mov     eax, [rbx+10h]
0x140036cfc  mov     r8d, 3
0x140036d02  mov     [rsp+0F0h+var_C0], edi
0x140036d06  mov     dl, 4
0x140036d08  mov     [rsp+0F0h+var_C8], eax
0x140036d0c  mov     rcx, [rcx+40h]
0x140036d10  mov     [rsp+0F0h+var_D0], r13
0x140036d15  call    WPP_RECORDER_SF_DD
0x140036d1a  mov     rdx, [rbx+68h]
0x140036d1e  test    rdx, rdx
0x140036d21  jz      short loc_140036D4A
0x140036d23  mov     rax, cs:WdfFunctions_01031
0x140036d2a  mov     r8, cs:off_14005DF38
0x140036d31  mov     rcx, cs:WdfDriverGlobals
0x140036d38  mov     rax, [rax+650h]
0x140036d3f  call    _guard_dispatch_icall
0x140036d44  add     rax, 18h
0x140036d48  jmp     short loc_140036D5B
0x140036d4a  mov     rax, [rbx+30h]
0x140036d4e  mov     rcx, [rax]
0x140036d51  mov     rax, [rcx+478h]
0x140036d58  mov     rax, [rax]
0x140036d5b  lea     rdx, [rbp+4Fh+var_A0]; struct _NDIS_STATUS_INDICATION *
0x140036d5f  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x140036d62  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x140036d67  xor     eax, eax
0x140036d69  mov     rcx, [rbp+4Fh+var_30]
0x140036d6d  xor     rcx, rsp; StackCookie
0x140036d70  call    __security_check_cookie
0x140036d75  mov     rbx, [rsp+0F0h+arg_8]
0x140036d7d  add     rsp, 0D0h
0x140036d84  pop     r14
0x140036d86  pop     r13
0x140036d88  pop     rdi
0x140036d89  pop     rsi
0x140036d8a  pop     rbp
0x140036d8b  retn
```
