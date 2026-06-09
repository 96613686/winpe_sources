# MbbNdisUiccOpenChannelInfoStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140039ee0`
- end: `0x14003a2b1`
- name: `?MbbNdisUiccOpenChannelInfoStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `977`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x1400051ac`
- `0x140005644`
- `0x140039ee0`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003a06d`
- `ntoskrnl!ExAllocatePool2` at `0x14003a06d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a27b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a27b`

## pseudocode

```c
__int64 __fastcall MbbNdisUiccOpenChannelInfoStatusHandler(
        __int64 a1,
        int a2,
        unsigned int a3,
        __int16 *a4,
        unsigned int a5)
{
  char v8; // r12
  __int64 v10; // rax
  _WORD *v11; // rdi
  unsigned int v12; // edx
  int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // ecx
  ULONG v16; // r15d
  _WORD *Pool2; // rax
  int v18; // edx
  int v19; // edx
  __int16 v20; // ax
  unsigned int v21; // eax
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
  v26.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v10 + 1144LL) + 16LL);
  v26.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v26.RequestId = *(PVOID *)(a1 + 432);
  v26.PortNumber = 0;
  *(_QWORD *)&v26.StatusCode = 1074008117;
  v26.Guid = 0;
  v13 = MbbUtilMbbToWwanStatus(a3);
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        3,
        311,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
    goto LABEL_25;
  }
  if ( !a4
    || a5 < 0x10
    || (v14 = *((_DWORD *)a4 + 3), v15 = *((_DWORD *)a4 + 2), v12 = v14 + v15, v14 + v15 < v14)
    || a5 < v12 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        3,
        312,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a5,
        16);
    }
    goto LABEL_24;
  }
  v16 = v15 + 20;
  if ( v15 >= 0xFFFFFFEC )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        3,
        313,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v15);
    }
LABEL_24:
    v8 = 1;
LABEL_25:
    v13 = -1073479677;
LABEL_26:
    if ( (unsigned int)MbbUtilMbbToWwanStatus(a3) )
      v13 = MbbUtilMbbToWwanStatus(a3);
    if ( v8 )
    {
      *(_DWORD *)v27 = 1573248;
      *(_DWORD *)&v27[4] = v13;
      *(_OWORD *)&v27[8] = 0;
      v26.StatusBuffer = v27;
      v26.StatusBufferSize = 24;
    }
    goto LABEL_18;
  }
  Pool2 = (_WORD *)ExAllocatePool2(64, v16, 1683505741);
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
        314,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v16);
    }
    v8 = 1;
    goto LABEL_25;
  }
  memset(Pool2, 0, v16);
  v20 = *a4;
  *v11 = 384;
  v11[1] = v16;
  *((_DWORD *)v11 + 1) = v13;
  v11[4] = v20;
  *((_DWORD *)v11 + 3) = *((_DWORD *)a4 + 1);
  v21 = *((_DWORD *)a4 + 2);
  *((_DWORD *)v11 + 4) = v21;
  v26.StatusBuffer = v11;
  v26.StatusBufferSize = v16;
  if ( a5 > 0x10 )
    memmove(v11 + 10, (char *)a4 + *((unsigned int *)a4 + 3), v21);
  v8 = 0;
  if ( v13 )
    goto LABEL_26;
LABEL_18:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      3,
      315,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v13);
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
0x140039ee0  mov     [rsp-8+arg_8], rbx
0x140039ee5  push    rbp
0x140039ee6  push    rsi
0x140039ee7  push    rdi
0x140039ee8  push    r12
0x140039eea  push    r13
0x140039eec  push    r14
0x140039eee  push    r15
0x140039ef0  lea     rbp, [rsp-1Fh]
0x140039ef5  sub     rsp, 0E0h
0x140039efc  mov     rax, cs:__security_cookie
0x140039f03  xor     rax, rsp
0x140039f06  mov     [rbp+4Fh+var_38], rax
0x140039f0a  mov     ebx, r8d
0x140039f0d  mov     r15d, edx
0x140039f10  xor     edx, edx; Val
0x140039f12  mov     [rbp+4Fh+var_CC], ebx
0x140039f15  mov     rsi, rcx
0x140039f18  mov     r12b, 1
0x140039f1b  lea     rcx, [rbp+4Fh+var_C0+4]; void *
0x140039f1f  mov     [rsp+110h+var_D0], r12b
0x140039f24  mov     r14, r9
0x140039f27  lea     r8d, [rdx+6Ch]; Size
0x140039f2b  call    memset
0x140039f30  xor     eax, eax
0x140039f32  mov     dword ptr [rbp+4Fh+var_C0.Header.Type], 700198h
0x140039f39  mov     [rbp+4Fh+var_40], rax
0x140039f3d  xorps   xmm0, xmm0
0x140039f40  mov     rax, [rsi+30h]
0x140039f44  xor     edi, edi
0x140039f46  movups  [rbp+4Fh+var_50], xmm0
0x140039f4a  mov     rcx, [rax]
0x140039f4d  mov     rax, [rcx+478h]
0x140039f54  mov     rcx, [rax]
0x140039f57  mov     rax, [rcx+10h]
0x140039f5b  mov     ecx, ebx
0x140039f5d  mov     [rbp+4Fh+var_C0.SourceHandle], rax
0x140039f61  mov     rax, [rsi+1B8h]
0x140039f68  mov     [rbp+4Fh+var_C0.DestinationHandle], rax
0x140039f6c  mov     rax, [rsi+1B0h]
0x140039f73  mov     [rbp+4Fh+var_C0.RequestId], rax
0x140039f77  mov     [rbp+4Fh+var_C0.PortNumber], edi
0x140039f7a  mov     qword ptr [rbp+4Fh+var_C0.StatusCode], 40041035h
0x140039f82  movups  xmmword ptr [rbp+4Fh+var_C0.Guid.Data1], xmm0
0x140039f86  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140039f8b  lea     r8, WPP_RECORDER_INITIALIZED
0x140039f92  mov     ebx, eax
0x140039f94  lea     r11, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140039f9b  lea     r10d, [rdi+3]
0x140039f9f  test    r15d, r15d
0x140039fa2  jz      short loc_140039FE2
0x140039fa4  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140039fab  jz      loc_14003A1F5
0x140039fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140039fb8  mov     r9d, 137h
0x140039fbe  mov     eax, [rsi+10h]
0x140039fc1  mov     r8d, r10d
0x140039fc4  mov     [rsp+110h+var_E0], r15d
0x140039fc9  mov     dl, 2
0x140039fcb  mov     [rsp+110h+var_E8], eax
0x140039fcf  mov     rcx, [rcx+40h]
0x140039fd3  mov     [rsp+110h+var_F0], r11
0x140039fd8  call    WPP_RECORDER_SF_DD
0x140039fdd  jmp     loc_14003A1F5
0x140039fe2  mov     r12d, [rbp+4Fh+arg_20]
0x140039fe6  test    r14, r14
0x140039fe9  jz      loc_14003A1B3
0x140039fef  cmp     r12d, 10h
0x140039ff3  jb      loc_14003A1B3
0x140039ff9  mov     eax, [r14+0Ch]
0x140039ffd  mov     ecx, [r14+8]
0x14003a001  lea     edx, [rax+rcx]
0x14003a004  cmp     edx, eax
0x14003a006  jb      loc_14003A1B3
0x14003a00c  cmp     r12d, edx
0x14003a00f  jb      loc_14003A1B3
0x14003a015  lea     r15d, [rcx+14h]
0x14003a019  cmp     r15d, 14h
0x14003a01d  jnb     short loc_14003A05C
0x14003a01f  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14003a026  jz      loc_14003A1F0
0x14003a02c  mov     eax, [rsi+10h]
0x14003a02f  mov     r9d, 139h
0x14003a035  mov     [rsp+110h+var_E0], ecx
0x14003a039  mov     r8d, r10d
0x14003a03c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a043  mov     dl, 2
0x14003a045  mov     [rsp+110h+var_E8], eax
0x14003a049  mov     [rsp+110h+var_F0], r11
0x14003a04e  mov     rcx, [rcx+40h]
0x14003a052  call    WPP_RECORDER_SF_DD
0x14003a057  jmp     loc_14003A1F0
0x14003a05c  mov     r8d, 6458424Dh
0x14003a062  mov     edx, r15d
0x14003a065  mov     ecx, 40h ; '@'
0x14003a06a  mov     r13d, r15d
0x14003a06d  call    cs:__imp_ExAllocatePool2
0x14003a074  nop     dword ptr [rax+rax+00h]
0x14003a079  mov     rdi, rax
0x14003a07c  test    rax, rax
0x14003a07f  jnz     short loc_14003A0D8
0x14003a081  lea     r13, WPP_RECORDER_INITIALIZED
0x14003a088  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003a08f  jz      short loc_14003A0C7
0x14003a091  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a098  lea     r8d, [rdi+3]
0x14003a09c  mov     eax, [rsi+10h]
0x14003a09f  mov     r9d, 13Ah
0x14003a0a5  mov     [rsp+110h+var_E0], r15d
0x14003a0aa  mov     dl, 2
0x14003a0ac  mov     [rsp+110h+var_E8], eax
0x14003a0b0  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003a0b7  mov     rcx, [rcx+40h]
0x14003a0bb  mov     [rsp+110h+var_F0], r15
0x14003a0c0  call    WPP_RECORDER_SF_DD
0x14003a0c5  jmp     short loc_14003A0CE
0x14003a0c7  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003a0ce  mov     r12b, [rsp+110h+var_D0]
0x14003a0d3  jmp     loc_14003A203
0x14003a0d8  mov     r8, r13; Size
0x14003a0db  xor     edx, edx; Val
0x14003a0dd  mov     rcx, rdi; void *
0x14003a0e0  call    memset
0x14003a0e5  movzx   eax, word ptr [r14]
0x14003a0e9  mov     word ptr [rdi], 180h
0x14003a0ee  mov     [rdi+2], r15w
0x14003a0f3  mov     [rdi+4], ebx
0x14003a0f6  mov     [rdi+8], ax
0x14003a0fa  mov     eax, [r14+4]
0x14003a0fe  mov     [rdi+0Ch], eax
0x14003a101  mov     eax, [r14+8]
0x14003a105  mov     [rdi+10h], eax
0x14003a108  mov     [rbp+4Fh+var_C0.StatusBuffer], rdi
0x14003a10c  mov     [rbp+4Fh+var_C0.StatusBufferSize], r15d
0x14003a110  cmp     r12d, 10h
0x14003a114  jbe     short loc_14003A129
0x14003a116  mov     edx, [r14+0Ch]
0x14003a11a  lea     rcx, [rdi+14h]; void *
0x14003a11e  add     rdx, r14; Src
0x14003a121  mov     r8d, eax; Size
0x14003a124  call    memmove
0x14003a129  xor     r12b, r12b
0x14003a12c  lea     r13, WPP_RECORDER_INITIALIZED
0x14003a133  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003a13a  test    ebx, ebx
0x14003a13c  jnz     loc_14003A208
0x14003a142  lea     r14d, [rbx+18h]
0x14003a146  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003a14d  jz      short loc_14003A17D
0x14003a14f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a156  mov     r9d, 13Bh
0x14003a15c  mov     eax, [rsi+10h]
0x14003a15f  mov     r8d, 3
0x14003a165  mov     [rsp+110h+var_E0], ebx
0x14003a169  mov     dl, 4
0x14003a16b  mov     [rsp+110h+var_E8], eax
0x14003a16f  mov     rcx, [rcx+40h]
0x14003a173  mov     [rsp+110h+var_F0], r15
0x14003a178  call    WPP_RECORDER_SF_DD
0x14003a17d  mov     rdx, [rsi+68h]
0x14003a181  test    rdx, rdx
0x14003a184  jz      loc_14003A254
0x14003a18a  mov     rax, cs:WdfFunctions_01031
0x14003a191  mov     r8, cs:off_14005DF38
0x14003a198  mov     rcx, cs:WdfDriverGlobals
0x14003a19f  mov     rax, [rax+650h]
0x14003a1a6  call    _guard_dispatch_icall
0x14003a1ab  add     rax, r14
0x14003a1ae  jmp     loc_14003A265
0x14003a1b3  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14003a1ba  jz      short loc_14003A1F0
0x14003a1bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a1c3  mov     r9d, 138h
0x14003a1c9  mov     eax, [rsi+10h]
0x14003a1cc  mov     r8d, r10d
0x14003a1cf  mov     [rsp+110h+var_D8], 10h
0x14003a1d7  mov     dl, 2
0x14003a1d9  mov     [rsp+110h+var_E0], r12d
0x14003a1de  mov     rcx, [rcx+40h]
0x14003a1e2  mov     [rsp+110h+var_E8], eax
0x14003a1e6  mov     [rsp+110h+var_F0], r11
0x14003a1eb  call    WPP_RECORDER_SF_Ddd
0x14003a1f0  mov     r12b, [rsp+110h+var_D0]
0x14003a1f5  lea     r13, WPP_RECORDER_INITIALIZED
0x14003a1fc  lea     r15, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003a203  mov     ebx, 0C0040003h
0x14003a208  mov     r14d, [rbp+4Fh+var_CC]
0x14003a20c  mov     ecx, r14d
0x14003a20f  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14003a214  test    eax, eax
0x14003a216  jz      short loc_14003A222
0x14003a218  mov     ecx, r14d
0x14003a21b  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14003a220  mov     ebx, eax
0x14003a222  mov     r14d, 18h
0x14003a228  test    r12b, r12b
0x14003a22b  jz      loc_14003A146
0x14003a231  xorps   xmm0, xmm0
0x14003a234  mov     dword ptr [rbp+4Fh+var_50], 180180h
0x14003a23b  lea     rax, [rbp+4Fh+var_50]
0x14003a23f  mov     dword ptr [rbp+4Fh+var_50+4], ebx
0x14003a242  movdqu  [rbp+4Fh+var_50+8], xmm0
0x14003a247  mov     [rbp+4Fh+var_C0.StatusBuffer], rax
0x14003a24b  mov     [rbp+4Fh+var_C0.StatusBufferSize], r14d
0x14003a24f  jmp     loc_14003A146
0x14003a254  mov     rax, [rsi+30h]
0x14003a258  mov     rdx, [rax]
0x14003a25b  mov     rax, [rdx+478h]
0x14003a262  mov     rax, [rax]
0x14003a265  lea     rdx, [rbp+4Fh+var_C0]; struct _NDIS_STATUS_INDICATION *
0x14003a269  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x14003a26c  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x14003a271  test    rdi, rdi
0x14003a274  jz      short loc_14003A287
0x14003a276  xor     edx, edx; Tag
0x14003a278  mov     rcx, rdi; P
0x14003a27b  call    cs:__imp_ExFreePoolWithTag
0x14003a282  nop     dword ptr [rax+rax+00h]
0x14003a287  xor     eax, eax
0x14003a289  mov     rcx, [rbp+4Fh+var_38]
0x14003a28d  xor     rcx, rsp; StackCookie
0x14003a290  call    __security_check_cookie
0x14003a295  mov     rbx, [rsp+110h+arg_8]
0x14003a29d  add     rsp, 0E0h
0x14003a2a4  pop     r15
0x14003a2a6  pop     r14
0x14003a2a8  pop     r13
0x14003a2aa  pop     r12
0x14003a2ac  pop     rdi
0x14003a2ad  pop     rsi
0x14003a2ae  pop     rbp
0x14003a2af  retn
```
