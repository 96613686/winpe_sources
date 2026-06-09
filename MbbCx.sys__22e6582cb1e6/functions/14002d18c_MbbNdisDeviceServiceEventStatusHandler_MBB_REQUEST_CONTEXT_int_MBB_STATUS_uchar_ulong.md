# MbbNdisDeviceServiceEventStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x14002d18c`
- end: `0x14002d452`
- name: `?MbbNdisDeviceServiceEventStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `710`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, const void *, unsigned int Size)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x14002ddd0`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140005644`
- `0x14002d18c`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002d2e2`
- `ntoskrnl!ExAllocatePool2` at `0x14002d2e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d40d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d40d`

## pseudocode

```c
__int64 __fastcall MbbNdisDeviceServiceEventStatusHandler(
        __int64 a1,
        int a2,
        unsigned int a3,
        const void *a4,
        unsigned int Size)
{
  int v9; // r15d
  int v10; // edx
  __int64 v11; // rax
  char *Pool2; // rbx
  int v13; // r9d
  int v14; // eax
  int v15; // edx
  int v16; // ecx
  __int64 v17; // rdx
  NDIS_HANDLE *v18; // rax
  __int64 result; // rax
  struct _NDIS_STATUS_INDICATION v20; // [rsp+40h] [rbp-61h] BYREF

  v9 = -1073479677;
  memset(&v20.Header + 1, 0, 0x6Cu);
  v11 = *(_QWORD *)(a1 + 48);
  Pool2 = 0;
  v20.Header = (NDIS_OBJECT_HEADER)7340440;
  v20.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v11 + 1144LL) + 16LL);
  v20.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v20.RequestId = *(PVOID *)(a1 + 432);
  v20.PortNumber = 0;
  *(_QWORD *)&v20.StatusCode = 1074008089;
  v20.Guid = 0;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_19;
    v13 = 189;
    goto LABEL_4;
  }
  LOBYTE(a2) = Size;
  if ( Size + 28 >= Size )
  {
    Pool2 = (char *)ExAllocatePool2(64, Size + 28, 1683505741);
    if ( Pool2 )
    {
      v14 = MbbUtilMbbToWwanStatus(a3);
      v16 = *(_DWORD *)(a1 + 720);
      v9 = v14;
      *(_DWORD *)Pool2 = 1835392;
      *((_DWORD *)Pool2 + 5) = v16;
      *((_DWORD *)Pool2 + 6) = Size;
      *(_OWORD *)(Pool2 + 4) = *(_OWORD *)(a1 + 704);
      if ( Size )
        memmove(Pool2 + 28, a4, Size);
      v20.StatusBuffer = Pool2;
      v20.StatusBufferSize = Size + 28;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 4;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          3,
          192,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *(_DWORD *)(a1 + 16));
      }
      v17 = *(_QWORD *)(a1 + 104);
      if ( v17 )
        v18 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031
                                                                                                 + 1616))(
                                WdfDriverGlobals,
                                v17,
                                off_14005DF38)
                            + 24);
      else
        v18 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
      MbbUtilNdisMiniportIndicateStatusEx(v18, &v20);
      if ( !v9 )
        goto LABEL_22;
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 191;
LABEL_4:
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        v13,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_Ddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      3,
      190,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      Size,
      28,
      *(_QWORD *)&v20.Header.Type,
      v20.SourceHandle,
      *(_QWORD *)&v20.PortNumber,
      *(_QWORD *)&v20.Flags,
      v20.DestinationHandle,
      v20.RequestId);
  }
LABEL_19:
  if ( (unsigned int)MbbUtilMbbToWwanStatus(a3) )
    v9 = MbbUtilMbbToWwanStatus(a3);
  if ( Pool2 )
LABEL_22:
    ExFreePoolWithTag(Pool2, 0);
  result = 259;
  if ( v9 != 1074004232 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14002d18c  mov     [rsp-8+arg_8], rbx
0x14002d191  push    rbp
0x14002d192  push    rsi
0x14002d193  push    rdi
0x14002d194  push    r12
0x14002d196  push    r13
0x14002d198  push    r14
0x14002d19a  push    r15
0x14002d19c  lea     rbp, [rsp-1Fh]
0x14002d1a1  sub     rsp, 0C0h
0x14002d1a8  mov     rax, cs:__security_cookie
0x14002d1af  xor     rax, rsp
0x14002d1b2  mov     [rbp+4Fh+var_40], rax
0x14002d1b6  mov     esi, edx
0x14002d1b8  mov     r12d, r8d
0x14002d1bb  xor     edx, edx; Val
0x14002d1bd  mov     rdi, rcx
0x14002d1c0  lea     rcx, [rbp+4Fh+var_B0+4]; void *
0x14002d1c4  mov     r13, r9
0x14002d1c7  mov     r15d, 0C0040003h
0x14002d1cd  lea     r8d, [rdx+6Ch]; Size
0x14002d1d1  call    memset
0x14002d1d6  mov     rax, [rdi+30h]
0x14002d1da  xor     ebx, ebx
0x14002d1dc  mov     dword ptr [rbp+4Fh+var_B0.Header.Type], 700198h
0x14002d1e3  xorps   xmm0, xmm0
0x14002d1e6  mov     rcx, [rax]
0x14002d1e9  mov     rax, [rcx+478h]
0x14002d1f0  mov     rcx, [rax]
0x14002d1f3  mov     rax, [rcx+10h]
0x14002d1f7  mov     [rbp+4Fh+var_B0.SourceHandle], rax
0x14002d1fb  mov     rax, [rdi+1B8h]
0x14002d202  mov     [rbp+4Fh+var_B0.DestinationHandle], rax
0x14002d206  mov     rax, [rdi+1B0h]
0x14002d20d  mov     [rbp+4Fh+var_B0.RequestId], rax
0x14002d211  mov     [rbp+4Fh+var_B0.PortNumber], ebx
0x14002d214  mov     qword ptr [rbp+4Fh+var_B0.StatusCode], 40041019h
0x14002d21c  movups  xmmword ptr [rbp+4Fh+var_B0.Guid.Data1], xmm0
0x14002d220  test    esi, esi
0x14002d222  jz      short loc_14002D272
0x14002d224  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d22b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d232  jz      loc_14002D3EC
0x14002d238  mov     r9d, 0BDh
0x14002d23e  mov     eax, [rdi+10h]
0x14002d241  mov     r8d, 3
0x14002d247  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d24e  mov     dl, 2
0x14002d250  mov     [rsp+0F0h+var_C0], esi
0x14002d254  mov     [rsp+0F0h+var_C8], eax
0x14002d258  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002d25f  mov     [rsp+0F0h+var_D0], rax
0x14002d264  mov     rcx, [rcx+40h]
0x14002d268  call    WPP_RECORDER_SF_DD
0x14002d26d  jmp     loc_14002D3EC
0x14002d272  mov     esi, dword ptr [rbp+4Fh+Size]
0x14002d275  lea     r14d, [rsi+1Ch]
0x14002d279  cmp     r14d, esi
0x14002d27c  jnb     short loc_14002D2D4
0x14002d27e  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d285  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d28c  jz      loc_14002D3EC
0x14002d292  mov     eax, [rdi+10h]
0x14002d295  mov     r9d, 0BEh
0x14002d29b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d2a2  mov     r8d, 3
0x14002d2a8  mov     [rsp+0F0h+var_B8], 1Ch
0x14002d2b0  mov     dl, 2
0x14002d2b2  mov     [rsp+0F0h+var_C0], esi
0x14002d2b6  mov     [rsp+0F0h+var_C8], eax
0x14002d2ba  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002d2c1  mov     rcx, [rcx+40h]
0x14002d2c5  mov     [rsp+0F0h+var_D0], rax
0x14002d2ca  call    WPP_RECORDER_SF_Ddd
0x14002d2cf  jmp     loc_14002D3EC
0x14002d2d4  mov     edx, r14d
0x14002d2d7  mov     ecx, 40h ; '@'
0x14002d2dc  mov     r8d, 6458424Dh
0x14002d2e2  call    cs:__imp_ExAllocatePool2
0x14002d2e9  nop     dword ptr [rax+rax+00h]
0x14002d2ee  mov     rbx, rax
0x14002d2f1  test    rax, rax
0x14002d2f4  jnz     short loc_14002D315
0x14002d2f6  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d2fd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d304  jz      loc_14002D3EC
0x14002d30a  mov     r9d, 0BFh
0x14002d310  jmp     loc_14002D23E
0x14002d315  mov     ecx, r12d
0x14002d318  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002d31d  mov     ecx, [rdi+2D0h]
0x14002d323  mov     r15d, eax
0x14002d326  mov     dword ptr [rbx], 1C0180h
0x14002d32c  mov     [rbx+14h], ecx
0x14002d32f  mov     [rbx+18h], esi
0x14002d332  movups  xmm0, xmmword ptr [rdi+2C0h]
0x14002d339  movdqu  xmmword ptr [rbx+4], xmm0
0x14002d33e  test    esi, esi
0x14002d340  jz      short loc_14002D351
0x14002d342  mov     r8, rsi; Size
0x14002d345  lea     rcx, [rbx+1Ch]; void *
0x14002d349  mov     rdx, r13; Src
0x14002d34c  call    memmove
0x14002d351  mov     [rbp+4Fh+var_B0.StatusBuffer], rbx
0x14002d355  mov     [rbp+4Fh+var_B0.StatusBufferSize], r14d
0x14002d359  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d360  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d367  jz      short loc_14002D39A
0x14002d369  mov     eax, [rdi+10h]
0x14002d36c  mov     r9d, 0C0h
0x14002d372  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d379  mov     r8d, 3
0x14002d37f  mov     [rsp+0F0h+var_C8], eax
0x14002d383  mov     dl, 4
0x14002d385  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002d38c  mov     [rsp+0F0h+var_D0], rax
0x14002d391  mov     rcx, [rcx+40h]
0x14002d395  call    WPP_RECORDER_SF_d
0x14002d39a  mov     rdx, [rdi+68h]
0x14002d39e  test    rdx, rdx
0x14002d3a1  jz      short loc_14002D3CA
0x14002d3a3  mov     rax, cs:WdfFunctions_01031
0x14002d3aa  mov     r8, cs:off_14005DF38
0x14002d3b1  mov     rcx, cs:WdfDriverGlobals
0x14002d3b8  mov     rax, [rax+650h]
0x14002d3bf  call    _guard_dispatch_icall
0x14002d3c4  add     rax, 18h
0x14002d3c8  jmp     short loc_14002D3DB
0x14002d3ca  mov     rax, [rdi+30h]
0x14002d3ce  mov     rcx, [rax]
0x14002d3d1  mov     rax, [rcx+478h]
0x14002d3d8  mov     rax, [rax]
0x14002d3db  lea     rdx, [rbp+4Fh+var_B0]; struct _NDIS_STATUS_INDICATION *
0x14002d3df  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x14002d3e2  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14002d3e7  test    r15d, r15d
0x14002d3ea  jz      short loc_14002D408
0x14002d3ec  mov     ecx, r12d
0x14002d3ef  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002d3f4  test    eax, eax
0x14002d3f6  jz      short loc_14002D403
0x14002d3f8  mov     ecx, r12d
0x14002d3fb  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002d400  mov     r15d, eax
0x14002d403  test    rbx, rbx
0x14002d406  jz      short loc_14002D419
0x14002d408  xor     edx, edx; Tag
0x14002d40a  mov     rcx, rbx; P
0x14002d40d  call    cs:__imp_ExFreePoolWithTag
0x14002d414  nop     dword ptr [rax+rax+00h]
0x14002d419  xor     ecx, ecx
0x14002d41b  mov     eax, 103h
0x14002d420  cmp     r15d, 40040108h
0x14002d427  cmovnz  eax, ecx
0x14002d42a  mov     rcx, [rbp+4Fh+var_40]
0x14002d42e  xor     rcx, rsp; StackCookie
0x14002d431  call    __security_check_cookie
0x14002d436  mov     rbx, [rsp+0F0h+arg_8]
0x14002d43e  add     rsp, 0C0h
0x14002d445  pop     r15
0x14002d447  pop     r14
0x14002d449  pop     r13
0x14002d44b  pop     r12
0x14002d44d  pop     rdi
0x14002d44e  pop     rsi
0x14002d44f  pop     rbp
0x14002d450  retn
```
