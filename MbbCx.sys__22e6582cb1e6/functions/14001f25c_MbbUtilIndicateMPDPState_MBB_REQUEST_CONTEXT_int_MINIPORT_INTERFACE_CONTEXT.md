# MbbUtilIndicateMPDPState(_MBB_REQUEST_CONTEXT *,int,_MINIPORT_INTERFACE_CONTEXT *)

- ea: `0x14001f25c`
- end: `0x14001f3de`
- name: `?MbbUtilIndicateMPDPState@@YAXPEAU_MBB_REQUEST_CONTEXT@@HPEAU_MINIPORT_INTERFACE_CONTEXT@@@Z`
- size: `386`
- prototype: `void __fastcall(struct _MBB_REQUEST_CONTEXT *, int, struct _MINIPORT_INTERFACE_CONTEXT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140020ed8`
- `0x1400212ec`

## callees

- `0x1400051ac`
- `0x14001f25c`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## pseudocode

```c
void __fastcall MbbUtilIndicateMPDPState(
        struct _MBB_REQUEST_CONTEXT *a1,
        int a2,
        struct _MINIPORT_INTERFACE_CONTEXT *a3)
{
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int128 v10; // xmm0
  __int16 v11; // ax
  __int64 v12; // rax
  struct _NDIS_STATUS_INDICATION v13; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v14[36]; // [rsp+B0h] [rbp+17h] BYREF

  memset(v14, 0, sizeof(v14));
  memset(&v13.Header + 1, 0, 0x6Cu);
  v6 = *((_QWORD *)a1 + 6);
  v13.Header = (NDIS_OBJECT_HEADER)7340440;
  v7 = 36;
  v13.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v6 + 1144LL) + 16LL);
  v13.DestinationHandle = (NDIS_HANDLE)*((_QWORD *)a1 + 55);
  v13.RequestId = (PVOID)*((_QWORD *)a1 + 54);
  v8 = *((_QWORD *)a1 + 53);
  v13.PortNumber = 0;
  *(_QWORD *)&v13.StatusCode = 1074008133;
  v13.Guid = 0;
  *(_DWORD *)v14 = 2359680;
  *(_DWORD *)&v14[4] = a2;
  v9 = *(_QWORD *)(v8 + 40);
  *(_DWORD *)&v14[8] = *(_DWORD *)(v9 + 4);
  *(_OWORD *)&v14[12] = *(_OWORD *)(v9 + 8);
  *(_QWORD *)&v14[28] = *(_QWORD *)(v9 + 24);
  if ( !*(_DWORD *)&v14[8] )
  {
    v10 = *(_OWORD *)((char *)a3 + 40);
    *(_DWORD *)&v14[28] = *((_DWORD *)a3 + 14);
    v11 = *((_WORD *)a3 + 30);
    *(_OWORD *)&v14[12] = v10;
    *(_WORD *)&v14[32] = v11;
  }
  v13.StatusBufferSize = 36;
  v13.StatusBuffer = v14;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      3,
      108,
      (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
      *((_DWORD *)a1 + 4),
      36);
  }
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
          WdfDriverGlobals,
          *((_QWORD *)a1 + 13),
          off_14005DF38);
  MbbUtilNdisMiniportIndicateStatusEx((NDIS_HANDLE *)(v12 + 24), &v13);
}

```

## disassembly

```asm
0x14001f25c  mov     [rsp-8+arg_18], rbx
0x14001f261  push    rbp
0x14001f262  push    rsi
0x14001f263  push    rdi
0x14001f264  lea     rbp, [rsp-47h]
0x14001f269  sub     rsp, 0E0h
0x14001f270  mov     rax, cs:__security_cookie
0x14001f277  xor     rax, rsp
0x14001f27a  mov     [rbp+57h+var_18], rax
0x14001f27e  xor     eax, eax
0x14001f280  xorps   xmm0, xmm0
0x14001f283  mov     rdi, r8
0x14001f286  mov     [rbp+57h+var_20], eax
0x14001f289  mov     ebx, edx
0x14001f28b  mov     rsi, rcx
0x14001f28e  xor     edx, edx; Val
0x14001f290  lea     rcx, [rbp+57h+var_B0+4]; void *
0x14001f294  lea     r8d, [rax+6Ch]; Size
0x14001f298  movups  [rbp+57h+var_40], xmm0
0x14001f29c  movups  [rbp+57h+var_30], xmm0
0x14001f2a0  call    memset
0x14001f2a5  mov     rax, [rsi+30h]
0x14001f2a9  xorps   xmm0, xmm0
0x14001f2ac  mov     dword ptr [rbp+57h+var_B0.Header.Type], 700198h
0x14001f2b3  mov     edx, 24h ; '$'
0x14001f2b8  mov     rcx, [rax]
0x14001f2bb  mov     rax, [rcx+478h]
0x14001f2c2  mov     rcx, [rax]
0x14001f2c5  mov     rax, [rcx+10h]
0x14001f2c9  mov     [rbp+57h+var_B0.SourceHandle], rax
0x14001f2cd  mov     rax, [rsi+1B8h]
0x14001f2d4  mov     [rbp+57h+var_B0.DestinationHandle], rax
0x14001f2d8  mov     rax, [rsi+1B0h]
0x14001f2df  mov     [rbp+57h+var_B0.RequestId], rax
0x14001f2e3  mov     rax, [rsi+1A8h]
0x14001f2ea  mov     [rbp+57h+var_B0.PortNumber], 0
0x14001f2f1  mov     qword ptr [rbp+57h+var_B0.StatusCode], 40041045h
0x14001f2f9  movups  xmmword ptr [rbp+57h+var_B0.Guid.Data1], xmm0
0x14001f2fd  mov     dword ptr [rbp+57h+var_40], 240180h
0x14001f304  mov     dword ptr [rbp+57h+var_40+4], ebx
0x14001f307  mov     rcx, [rax+28h]
0x14001f30b  mov     eax, [rcx+4]
0x14001f30e  mov     dword ptr [rbp+57h+var_40+8], eax
0x14001f311  movups  xmm0, xmmword ptr [rcx+8]
0x14001f315  movups  [rbp+57h+var_40+0Ch], xmm0
0x14001f319  movsd   xmm1, qword ptr [rcx+18h]
0x14001f31e  movsd   qword ptr [rbp+57h+var_30+0Ch], xmm1
0x14001f323  test    eax, eax
0x14001f325  jnz     short loc_14001F33E
0x14001f327  mov     eax, [rdi+38h]
0x14001f32a  movups  xmm0, xmmword ptr [rdi+28h]
0x14001f32e  mov     dword ptr [rbp+57h+var_30+0Ch], eax
0x14001f331  movzx   eax, word ptr [rdi+3Ch]
0x14001f335  movdqu  [rbp+57h+var_40+0Ch], xmm0
0x14001f33a  mov     word ptr [rbp+57h+var_20], ax
0x14001f33e  lea     rax, [rbp+57h+var_40]
0x14001f342  mov     [rbp+57h+var_B0.StatusBufferSize], edx
0x14001f345  mov     [rbp+57h+var_B0.StatusBuffer], rax
0x14001f349  lea     rax, WPP_RECORDER_INITIALIZED
0x14001f350  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f357  jz      short loc_14001F38C
0x14001f359  mov     eax, [rsi+10h]
0x14001f35c  mov     r9d, 6Ch ; 'l'
0x14001f362  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f369  mov     [rsp+0F0h+var_C0], edx
0x14001f36d  mov     dl, 4
0x14001f36f  mov     [rsp+0F0h+var_C8], eax
0x14001f373  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001f37a  lea     r8d, [r9-69h]
0x14001f37e  mov     [rsp+0F0h+var_D0], rax
0x14001f383  mov     rcx, [rcx+40h]
0x14001f387  call    WPP_RECORDER_SF_DD
0x14001f38c  mov     rax, cs:WdfFunctions_01031
0x14001f393  mov     r8, cs:off_14005DF38
0x14001f39a  mov     rdx, [rsi+68h]
0x14001f39e  mov     rcx, cs:WdfDriverGlobals
0x14001f3a5  mov     rax, [rax+650h]
0x14001f3ac  call    _guard_dispatch_icall
0x14001f3b1  lea     rdx, [rbp+57h+var_B0]; struct _NDIS_STATUS_INDICATION *
0x14001f3b5  lea     rcx, [rax+18h]; struct _MINIPORT_INTERFACE_CONTEXT *
0x14001f3b9  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14001f3be  mov     rcx, [rbp+57h+var_18]
0x14001f3c2  xor     rcx, rsp; StackCookie
0x14001f3c5  call    __security_check_cookie
0x14001f3ca  mov     rbx, [rsp+0F0h+arg_18]
0x14001f3d2  add     rsp, 0E0h
0x14001f3d9  pop     rdi
0x14001f3da  pop     rsi
0x14001f3db  pop     rbp
0x14001f3dc  retn
```
