# MbbNdisIndicateReadyInfoFailure(_MBB_REQUEST_CONTEXT *)

- ea: `0x14002f75c`
- end: `0x14002f8d0`
- name: `?MbbNdisIndicateReadyInfoFailure@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `372`
- prototype: `void __fastcall(struct _MBB_REQUEST_CONTEXT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140013880`
- `0x14002f228`

## callees

- `0x140001db8`
- `0x14002f75c`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`

## pseudocode

```c
void __fastcall MbbNdisIndicateReadyInfoFailure(struct _MBB_REQUEST_CONTEXT *a1)
{
  int v2; // edx
  __int64 v3; // rax
  __int64 v4; // rdx
  NDIS_HANDLE *v5; // rax
  struct _NDIS_STATUS_INDICATION v6; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v7[28]; // [rsp+A0h] [rbp-60h] BYREF

  memset(&v6, 0, sizeof(v6));
  memset(v7, 0, 0x68u);
  *(_DWORD *)(**((_QWORD **)a1 + 6) + 1088LL) &= ~0x20u;
  memset(&v7[2], 0, 0x60u);
  v3 = *((_QWORD *)a1 + 6);
  v7[0] = 6816384;
  v7[1] = 4;
  v6.Header = (NDIS_OBJECT_HEADER)7340440;
  v6.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v3 + 1144LL) + 16LL);
  v6.DestinationHandle = (NDIS_HANDLE)*((_QWORD *)a1 + 55);
  v6.RequestId = (PVOID)*((_QWORD *)a1 + 54);
  v6.StatusBuffer = v7;
  v6.PortNumber = 0;
  *(_QWORD *)&v6.StatusCode = 1074008065;
  v6.Guid = 0;
  v6.StatusBufferSize = 104;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      3,
      20,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *((_DWORD *)a1 + 4),
      *(_QWORD *)&v6.Header.Type,
      v6.SourceHandle,
      *(_QWORD *)&v6.PortNumber,
      *(_QWORD *)&v6.Flags,
      v6.DestinationHandle,
      v6.RequestId,
      v6.StatusBuffer,
      *(_QWORD *)&v6.StatusBufferSize,
      *(_QWORD *)&v6.Guid.Data2,
      *(_QWORD *)&v6.Guid.Data4[4]);
  }
  v4 = *((_QWORD *)a1 + 13);
  if ( v4 )
    v5 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                           WdfDriverGlobals,
                           v4,
                           off_14005DF38)
                       + 24);
  else
    v5 = **(NDIS_HANDLE ***)(**((_QWORD **)a1 + 6) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v5, &v6);
}

```

## disassembly

```asm
0x14002f75c  push    rbp
0x14002f75e  push    rbx
0x14002f75f  push    rsi
0x14002f760  push    rdi
0x14002f761  lea     rbp, [rsp-28h]
0x14002f766  sub     rsp, 128h
0x14002f76d  mov     rax, cs:__security_cookie
0x14002f774  xor     rax, rsp
0x14002f777  mov     [rbp+40h+var_30], rax
0x14002f77b  xor     edx, edx; Val
0x14002f77d  mov     rbx, rcx
0x14002f780  lea     rcx, [rsp+140h+var_110]; void *
0x14002f785  lea     r8d, [rdx+70h]; Size
0x14002f789  call    memset
0x14002f78e  mov     esi, 68h ; 'h'
0x14002f793  lea     rcx, [rbp+40h+var_A0]; void *
0x14002f797  mov     r8d, esi; Size
0x14002f79a  xor     edx, edx; Val
0x14002f79c  call    memset
0x14002f7a1  mov     rax, [rbx+30h]
0x14002f7a5  lea     r8d, [rsi-8]; Size
0x14002f7a9  xor     edx, edx; Val
0x14002f7ab  mov     rcx, [rax]
0x14002f7ae  and     dword ptr [rcx+440h], 0FFFFFFDFh
0x14002f7b5  lea     rcx, [rbp+40h+var_98]; void *
0x14002f7b9  call    memset
0x14002f7be  mov     rax, [rbx+30h]
0x14002f7c2  xorps   xmm0, xmm0
0x14002f7c5  mov     [rbp+40h+var_A0], 680280h
0x14002f7cc  mov     [rbp+40h+var_9C], 4
0x14002f7d3  mov     dword ptr [rsp+140h+var_110.Header.Type], 700198h
0x14002f7db  mov     rcx, [rax]
0x14002f7de  mov     rax, [rcx+478h]
0x14002f7e5  mov     rcx, [rax]
0x14002f7e8  mov     rax, [rcx+10h]
0x14002f7ec  mov     [rsp+140h+var_110.SourceHandle], rax
0x14002f7f1  mov     rax, [rbx+1B8h]
0x14002f7f8  mov     [rsp+140h+var_110.DestinationHandle], rax
0x14002f7fd  mov     rax, [rbx+1B0h]
0x14002f804  mov     [rsp+140h+var_110.RequestId], rax
0x14002f809  lea     rax, [rbp+40h+var_A0]
0x14002f80d  mov     [rsp+140h+var_110.StatusBuffer], rax
0x14002f812  mov     [rsp+140h+var_110.PortNumber], 0
0x14002f81a  mov     qword ptr [rsp+140h+var_110.StatusCode], 40041001h
0x14002f823  movups  xmmword ptr [rsp+140h+var_110.Guid.Data1], xmm0
0x14002f828  mov     [rsp+140h+var_110.StatusBufferSize], esi
0x14002f82c  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f833  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f83a  jz      short loc_14002F869
0x14002f83c  mov     eax, [rbx+10h]
0x14002f83f  lea     r9d, [rsi-54h]
0x14002f843  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f84a  lea     r8d, [rsi-65h]
0x14002f84e  mov     [rsp+140h+var_118], eax
0x14002f852  mov     dl, 2
0x14002f854  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002f85b  mov     [rsp+140h+var_120], rax
0x14002f860  mov     rcx, [rcx+40h]
0x14002f864  call    WPP_RECORDER_SF_d
0x14002f869  mov     rdx, [rbx+68h]
0x14002f86d  test    rdx, rdx
0x14002f870  jz      short loc_14002F899
0x14002f872  mov     rax, cs:WdfFunctions_01031
0x14002f879  mov     r8, cs:off_14005DF38
0x14002f880  mov     rcx, cs:WdfDriverGlobals
0x14002f887  mov     rax, [rax+650h]
0x14002f88e  call    _guard_dispatch_icall
0x14002f893  add     rax, 18h
0x14002f897  jmp     short loc_14002F8AA
0x14002f899  mov     rax, [rbx+30h]
0x14002f89d  mov     rcx, [rax]
0x14002f8a0  mov     rax, [rcx+478h]
0x14002f8a7  mov     rax, [rax]
0x14002f8aa  lea     rdx, [rsp+140h+var_110]; struct _NDIS_STATUS_INDICATION *
0x14002f8af  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x14002f8b2  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14002f8b7  mov     rcx, [rbp+40h+var_30]
0x14002f8bb  xor     rcx, rsp; StackCookie
0x14002f8be  call    __security_check_cookie
0x14002f8c3  add     rsp, 128h
0x14002f8ca  pop     rdi
0x14002f8cb  pop     rsi
0x14002f8cc  pop     rbx
0x14002f8cd  pop     rbp
0x14002f8ce  retn
```
