# MbbNdisServiceActivationStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x1400357c0`
- end: `0x140035b50`
- name: `?MbbNdisServiceActivationStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `912`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callees

- `0x1400051ac`
- `0x140005644`
- `0x1400357c0`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003598e`
- `ntoskrnl!ExAllocatePool2` at `0x14003598e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035b1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035b1a`

## pseudocode

```c
__int64 __fastcall MbbNdisServiceActivationStatusHandler(
        __int64 a1,
        int a2,
        unsigned int a3,
        _DWORD *a4,
        unsigned int a5)
{
  unsigned int v8; // r14d
  int v10; // edx
  __int64 v11; // rax
  __int128 *v12; // rdi
  int v13; // ebx
  int v14; // edx
  __int128 *v15; // rax
  int v16; // edx
  unsigned int v17; // r15d
  __int128 *Pool2; // rax
  int v19; // edx
  __int64 v20; // rdx
  NDIS_HANDLE *v21; // rax
  struct _NDIS_STATUS_INDICATION v23; // [rsp+40h] [rbp-71h] BYREF
  __int128 v24; // [rsp+B0h] [rbp-1h] BYREF

  v8 = 0;
  memset(&v23.Header + 1, 0, 0x6Cu);
  v11 = *(_QWORD *)(a1 + 48);
  v24 = 0;
  v23.Header = (NDIS_OBJECT_HEADER)7340440;
  v12 = 0;
  v23.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v11 + 1144LL) + 16LL);
  v23.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v23.RequestId = *(PVOID *)(a1 + 432);
  v23.PortNumber = 0;
  *(_QWORD *)&v23.StatusCode = 1074008077;
  v23.Guid = 0;
  if ( a2 )
  {
    v13 = -1073479677;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        148,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
    goto LABEL_4;
  }
  v13 = MbbUtilMbbToWwanStatus(a3);
  if ( !a4 || a5 < 4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        3,
        149,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a5,
        4,
        *(_QWORD *)&v23.Header.Type,
        v23.SourceHandle,
        *(_QWORD *)&v23.PortNumber,
        *(_QWORD *)&v23.Flags,
        v23.DestinationHandle,
        v23.RequestId);
    }
LABEL_17:
    v13 = -1073479677;
    goto LABEL_4;
  }
  v17 = a5 - 4;
  v8 = a5 - 4 + 16;
  if ( v8 >= a5 - 4 )
  {
    Pool2 = (__int128 *)ExAllocatePool2(64, v8, 1683505741);
    v12 = Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = 1048960;
      *((_DWORD *)Pool2 + 2) = *a4;
      *((_DWORD *)Pool2 + 3) = v17;
      memmove(Pool2 + 1, a4 + 1, v17);
      if ( !v13 )
        goto LABEL_19;
      goto LABEL_4;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        3,
        151,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v8);
    }
    goto LABEL_17;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = 2;
    WPP_RECORDER_SF_Ddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      3,
      150,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v17,
      16,
      *(_QWORD *)&v23.Header.Type,
      v23.SourceHandle,
      *(_QWORD *)&v23.PortNumber,
      *(_QWORD *)&v23.Flags,
      v23.DestinationHandle,
      v23.RequestId);
  }
  v13 = -1073479677;
  v8 = -1;
LABEL_4:
  if ( (unsigned int)MbbUtilMbbToWwanStatus(a3) )
    v13 = MbbUtilMbbToWwanStatus(a3);
  if ( !v12 )
  {
    LODWORD(v24) = 1048960;
    v23.StatusBufferSize = 16;
    v15 = &v24;
    *((_QWORD *)&v24 + 1) = 0;
    goto LABEL_20;
  }
LABEL_19:
  v15 = v12;
  v23.StatusBufferSize = v8;
LABEL_20:
  v23.StatusBuffer = v15;
  *((_DWORD *)v15 + 1) = v13;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      3,
      152,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v13);
  }
  v20 = *(_QWORD *)(a1 + 104);
  if ( v20 )
    v21 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                            WdfDriverGlobals,
                            v20,
                            off_14005DF38)
                        + 24);
  else
    v21 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v21, &v23);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  return 0;
}

```

## disassembly

```asm
0x1400357c0  mov     [rsp-8+arg_8], rbx
0x1400357c5  push    rbp
0x1400357c6  push    rsi
0x1400357c7  push    rdi
0x1400357c8  push    r12
0x1400357ca  push    r13
0x1400357cc  push    r14
0x1400357ce  push    r15
0x1400357d0  lea     rbp, [rsp-1Fh]
0x1400357d5  sub     rsp, 0D0h
0x1400357dc  mov     rax, cs:__security_cookie
0x1400357e3  xor     rax, rsp
0x1400357e6  mov     [rbp+4Fh+var_40], rax
0x1400357ea  mov     r13d, r8d
0x1400357ed  mov     r15d, edx
0x1400357f0  mov     rsi, rcx
0x1400357f3  xor     r14d, r14d
0x1400357f6  xor     edx, edx; Val
0x1400357f8  lea     rcx, [rbp+4Fh+var_C0+4]; void *
0x1400357fc  mov     r12, r9
0x1400357ff  lea     r8d, [r14+6Ch]; Size
0x140035803  call    memset
0x140035808  mov     rax, [rsi+30h]
0x14003580c  xorps   xmm0, xmm0
0x14003580f  movups  [rbp+4Fh+var_50], xmm0
0x140035813  mov     dword ptr [rbp+4Fh+var_C0.Header.Type], 700198h
0x14003581a  xor     edi, edi
0x14003581c  mov     rcx, [rax]
0x14003581f  mov     rax, [rcx+478h]
0x140035826  mov     rcx, [rax]
0x140035829  mov     rax, [rcx+10h]
0x14003582d  lea     rcx, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140035834  mov     [rbp+4Fh+var_C0.SourceHandle], rax
0x140035838  mov     rax, [rsi+1B8h]
0x14003583f  mov     [rbp+4Fh+var_C0.DestinationHandle], rax
0x140035843  mov     rax, [rsi+1B0h]
0x14003584a  mov     [rbp+4Fh+var_C0.RequestId], rax
0x14003584e  lea     rax, WPP_RECORDER_INITIALIZED
0x140035855  mov     [rbp+4Fh+var_C0.PortNumber], edi
0x140035858  mov     qword ptr [rbp+4Fh+var_C0.StatusCode], 4004100Dh
0x140035860  movups  xmmword ptr [rbp+4Fh+var_C0.Guid.Data1], xmm0
0x140035864  test    r15d, r15d
0x140035867  jz      loc_1400358EF
0x14003586d  mov     ebx, 0C0040003h
0x140035872  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035879  jz      short loc_1400358A8
0x14003587b  mov     eax, [rsi+10h]
0x14003587e  lea     r8d, [r14+3]
0x140035882  mov     [rsp+100h+var_D0], r15d
0x140035887  mov     r9d, 94h
0x14003588d  mov     [rsp+100h+var_D8], eax
0x140035891  mov     dl, 2
0x140035893  mov     [rsp+100h+var_E0], rcx
0x140035898  mov     rcx, cs:WPP_GLOBAL_Control
0x14003589f  mov     rcx, [rcx+40h]
0x1400358a3  call    WPP_RECORDER_SF_DD
0x1400358a8  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400358af  lea     r12, WPP_RECORDER_INITIALIZED
0x1400358b6  mov     ecx, r13d
0x1400358b9  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x1400358be  test    eax, eax
0x1400358c0  jz      short loc_1400358CC
0x1400358c2  mov     ecx, r13d
0x1400358c5  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x1400358ca  mov     ebx, eax
0x1400358cc  test    rdi, rdi
0x1400358cf  jnz     loc_140035A28
0x1400358d5  lea     ecx, [rdi+10h]
0x1400358d8  mov     dword ptr [rbp+4Fh+var_50], 100180h
0x1400358df  mov     [rbp+4Fh+var_C0.StatusBufferSize], ecx
0x1400358e2  lea     rax, [rbp+4Fh+var_50]
0x1400358e6  mov     qword ptr [rbp+4Fh+var_50+8], rdi
0x1400358ea  jmp     loc_140035A2F
0x1400358ef  mov     ecx, r13d
0x1400358f2  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x1400358f7  mov     ebx, eax
0x1400358f9  mov     eax, [rbp+4Fh+arg_20]
0x1400358fc  test    r12, r12
0x1400358ff  jz      loc_140035A9D
0x140035905  cmp     eax, 4
0x140035908  jb      loc_140035A9D
0x14003590e  lea     r15d, [rax-4]
0x140035912  lea     r14d, [r15+10h]
0x140035916  cmp     r14d, r15d
0x140035919  jnb     short loc_140035980
0x14003591b  lea     r12, WPP_RECORDER_INITIALIZED
0x140035922  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140035929  jz      short loc_14003596B
0x14003592b  mov     rcx, cs:WPP_GLOBAL_Control
0x140035932  mov     r9d, 96h
0x140035938  mov     eax, [rsi+10h]
0x14003593b  mov     r8d, 3
0x140035941  mov     [rsp+100h+var_C8], 10h
0x140035949  mov     dl, 2
0x14003594b  mov     [rsp+100h+var_D0], r15d
0x140035950  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140035957  mov     rcx, [rcx+40h]
0x14003595b  mov     [rsp+100h+var_D8], eax
0x14003595f  mov     [rsp+100h+var_E0], r15
0x140035964  call    WPP_RECORDER_SF_Ddd
0x140035969  jmp     short loc_140035972
0x14003596b  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140035972  mov     ebx, 0C0040003h
0x140035977  or      r14d, 0FFFFFFFFh
0x14003597b  jmp     loc_1400358B6
0x140035980  mov     edx, r14d
0x140035983  mov     ecx, 40h ; '@'
0x140035988  mov     r8d, 6458424Dh
0x14003598e  call    cs:__imp_ExAllocatePool2
0x140035995  nop     dword ptr [rax+rax+00h]
0x14003599a  mov     rdi, rax
0x14003599d  test    rax, rax
0x1400359a0  jnz     short loc_1400359F0
0x1400359a2  lea     r12, WPP_RECORDER_INITIALIZED
0x1400359a9  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400359b0  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400359b7  jz      short loc_1400359E6
0x1400359b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400359c0  lea     r8d, [rdi+3]
0x1400359c4  mov     eax, [rsi+10h]
0x1400359c7  mov     r9d, 97h
0x1400359cd  mov     [rsp+100h+var_D0], r14d
0x1400359d2  mov     dl, 2
0x1400359d4  mov     [rsp+100h+var_D8], eax
0x1400359d8  mov     rcx, [rcx+40h]
0x1400359dc  mov     [rsp+100h+var_E0], r15
0x1400359e1  call    WPP_RECORDER_SF_DD
0x1400359e6  mov     ebx, 0C0040003h
0x1400359eb  jmp     loc_1400358B6
0x1400359f0  mov     dword ptr [rax], 100180h
0x1400359f6  lea     rdx, [r12+4]; Src
0x1400359fb  mov     eax, [r12]
0x1400359ff  lea     rcx, [rdi+10h]; void *
0x140035a03  mov     r8d, r15d; Size
0x140035a06  mov     [rdi+8], eax
0x140035a09  mov     [rdi+0Ch], r15d
0x140035a0d  call    memmove
0x140035a12  lea     r12, WPP_RECORDER_INITIALIZED
0x140035a19  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140035a20  test    ebx, ebx
0x140035a22  jnz     loc_1400358B6
0x140035a28  mov     rax, rdi
0x140035a2b  mov     [rbp+4Fh+var_C0.StatusBufferSize], r14d
0x140035a2f  mov     [rbp+4Fh+var_C0.StatusBuffer], rax
0x140035a33  mov     [rax+4], ebx
0x140035a36  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140035a3d  jz      short loc_140035A6D
0x140035a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140035a46  mov     r9d, 98h
0x140035a4c  mov     eax, [rsi+10h]
0x140035a4f  mov     r8d, 3
0x140035a55  mov     [rsp+100h+var_D0], ebx
0x140035a59  mov     dl, 4
0x140035a5b  mov     [rsp+100h+var_D8], eax
0x140035a5f  mov     rcx, [rcx+40h]
0x140035a63  mov     [rsp+100h+var_E0], r15
0x140035a68  call    WPP_RECORDER_SF_DD
0x140035a6d  mov     rdx, [rsi+68h]
0x140035a71  test    rdx, rdx
0x140035a74  jz      short loc_140035AF3
0x140035a76  mov     rax, cs:WdfFunctions_01031
0x140035a7d  mov     r8, cs:off_14005DF38
0x140035a84  mov     rcx, cs:WdfDriverGlobals
0x140035a8b  mov     rax, [rax+650h]
0x140035a92  call    _guard_dispatch_icall
0x140035a97  add     rax, 18h
0x140035a9b  jmp     short loc_140035B04
0x140035a9d  lea     r12, WPP_RECORDER_INITIALIZED
0x140035aa4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140035aab  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140035ab2  jz      loc_1400359E6
0x140035ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x140035abf  mov     r9d, 95h
0x140035ac5  mov     [rsp+100h+var_C8], 4
0x140035acd  mov     r8d, 3
0x140035ad3  mov     [rsp+100h+var_D0], eax
0x140035ad7  mov     dl, 2
0x140035ad9  mov     eax, [rsi+10h]
0x140035adc  mov     rcx, [rcx+40h]
0x140035ae0  mov     [rsp+100h+var_D8], eax
0x140035ae4  mov     [rsp+100h+var_E0], r15
0x140035ae9  call    WPP_RECORDER_SF_Ddd
0x140035aee  jmp     loc_1400359E6
0x140035af3  mov     rax, [rsi+30h]
0x140035af7  mov     rdx, [rax]
0x140035afa  mov     rax, [rdx+478h]
0x140035b01  mov     rax, [rax]
0x140035b04  lea     rdx, [rbp+4Fh+var_C0]; struct _NDIS_STATUS_INDICATION *
0x140035b08  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x140035b0b  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x140035b10  test    rdi, rdi
0x140035b13  jz      short loc_140035B26
0x140035b15  xor     edx, edx; Tag
0x140035b17  mov     rcx, rdi; P
0x140035b1a  call    cs:__imp_ExFreePoolWithTag
0x140035b21  nop     dword ptr [rax+rax+00h]
0x140035b26  xor     eax, eax
0x140035b28  mov     rcx, [rbp+4Fh+var_40]
0x140035b2c  xor     rcx, rsp; StackCookie
0x140035b2f  call    __security_check_cookie
0x140035b34  mov     rbx, [rsp+100h+arg_8]
0x140035b3c  add     rsp, 0D0h
0x140035b43  pop     r15
0x140035b45  pop     r14
0x140035b47  pop     r13
0x140035b49  pop     r12
0x140035b4b  pop     rdi
0x140035b4c  pop     rsi
0x140035b4d  pop     rbp
0x140035b4e  retn
```
