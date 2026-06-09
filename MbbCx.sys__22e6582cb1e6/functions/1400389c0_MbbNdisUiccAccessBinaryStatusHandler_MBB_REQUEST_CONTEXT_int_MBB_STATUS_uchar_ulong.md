# MbbNdisUiccAccessBinaryStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x1400389c0`
- end: `0x140038d75`
- name: `?MbbNdisUiccAccessBinaryStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `949`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x1400051ac`
- `0x140005644`
- `0x1400389c0`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047e50`
- `0x140047e90`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140038b50`
- `ntoskrnl!ExAllocatePool2` at `0x140038b50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d3f`

## pseudocode

```c
__int64 __fastcall MbbNdisUiccAccessBinaryStatusHandler(
        __int64 a1,
        int a2,
        unsigned int a3,
        _DWORD *a4,
        unsigned int a5)
{
  char v8; // r13
  __int64 v10; // rax
  _DWORD *v11; // rdi
  ULONG v12; // r14d
  unsigned int v13; // edx
  int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ecx
  _DWORD *Pool2; // rax
  int v18; // edx
  int v19; // edx
  size_t v20; // r8
  char *v21; // rdx
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
  v12 = 0;
  v26.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v10 + 1144LL) + 16LL);
  v26.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v26.RequestId = *(PVOID *)(a1 + 432);
  v26.PortNumber = 0;
  *(_QWORD *)&v26.StatusCode = 1074008138;
  v26.Guid = 0;
  v14 = MbbUtilMbbToWwanStatus(a3);
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        3,
        230,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
LABEL_23:
    v14 = -1073479677;
    goto LABEL_24;
  }
  if ( !a4 || a5 < 0x14 || (v15 = a4[3], v16 = a4[4], v13 = v15 + v16, v15 + v16 < v15) || a5 < v13 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        3,
        231,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a5,
        20);
    }
    goto LABEL_23;
  }
  v12 = v16 + 22;
  if ( v16 >= 0xFFFFFFEA )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        3,
        232,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v16);
    }
    v12 = -1;
    goto LABEL_23;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(64, v12, 1683505741);
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
        233,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v12);
    }
    v8 = 1;
    goto LABEL_23;
  }
  memset(Pool2, 0, v12);
  v11[2] = *a4;
  v11[3] = a4[1];
  v11[4] = a4[2];
  *v11 = 1573248;
  if ( a5 <= 0x14 )
  {
    *((_WORD *)v11 + 10) = 0;
  }
  else
  {
    v20 = (unsigned int)a4[4];
    v21 = (char *)a4 + (unsigned int)a4[3];
    *((_WORD *)v11 + 10) = *((_WORD *)a4 + 8);
    memmove((char *)v11 + 22, v21, v20);
  }
  v8 = 0;
  if ( !v14 )
  {
LABEL_27:
    v11[1] = v14;
    v26.StatusBuffer = v11;
    v26.StatusBufferSize = v12;
    goto LABEL_29;
  }
LABEL_24:
  if ( (unsigned int)MbbUtilMbbToWwanStatus(a3) )
    v14 = MbbUtilMbbToWwanStatus(a3);
  if ( !v8 )
    goto LABEL_27;
  *(_DWORD *)v27 = 1573248;
  *(_DWORD *)&v27[4] = v14;
  v26.StatusBufferSize = 24;
  *(_OWORD *)&v27[8] = 0;
  v26.StatusBuffer = v27;
LABEL_29:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      3,
      234,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v14);
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
0x1400389c0  mov     [rsp-8+arg_8], rbx
0x1400389c5  push    rbp
0x1400389c6  push    rsi
0x1400389c7  push    rdi
0x1400389c8  push    r12
0x1400389ca  push    r13
0x1400389cc  push    r14
0x1400389ce  push    r15
0x1400389d0  lea     rbp, [rsp-1Fh]
0x1400389d5  sub     rsp, 0E0h
0x1400389dc  mov     rax, cs:__security_cookie
0x1400389e3  xor     rax, rsp
0x1400389e6  mov     [rbp+4Fh+var_38], rax
0x1400389ea  mov     ebx, r8d
0x1400389ed  mov     r12d, edx
0x1400389f0  xor     edx, edx; Val
0x1400389f2  mov     [rbp+4Fh+var_CC], ebx
0x1400389f5  mov     r15, rcx
0x1400389f8  mov     r13b, 1
0x1400389fb  lea     rcx, [rbp+4Fh+var_C0+4]; void *
0x1400389ff  mov     [rsp+110h+var_D0], r13b
0x140038a04  mov     rsi, r9
0x140038a07  lea     r8d, [rdx+6Ch]; Size
0x140038a0b  call    memset
0x140038a10  xor     eax, eax
0x140038a12  mov     dword ptr [rbp+4Fh+var_C0.Header.Type], 700198h
0x140038a19  mov     [rbp+4Fh+var_40], rax
0x140038a1d  xorps   xmm0, xmm0
0x140038a20  mov     rax, [r15+30h]
0x140038a24  xor     edi, edi
0x140038a26  movups  [rbp+4Fh+var_50], xmm0
0x140038a2a  xor     r14d, r14d
0x140038a2d  mov     rcx, [rax]
0x140038a30  mov     rax, [rcx+478h]
0x140038a37  mov     rcx, [rax]
0x140038a3a  mov     rax, [rcx+10h]
0x140038a3e  mov     ecx, ebx
0x140038a40  mov     [rbp+4Fh+var_C0.SourceHandle], rax
0x140038a44  mov     rax, [r15+1B8h]
0x140038a4b  mov     [rbp+4Fh+var_C0.DestinationHandle], rax
0x140038a4f  mov     rax, [r15+1B0h]
0x140038a56  mov     [rbp+4Fh+var_C0.RequestId], rax
0x140038a5a  mov     [rbp+4Fh+var_C0.PortNumber], edi
0x140038a5d  mov     qword ptr [rbp+4Fh+var_C0.StatusCode], 4004104Ah
0x140038a65  movups  xmmword ptr [rbp+4Fh+var_C0.Guid.Data1], xmm0
0x140038a69  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140038a6e  lea     r8, WPP_RECORDER_INITIALIZED
0x140038a75  mov     ebx, eax
0x140038a77  lea     r11, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140038a7e  lea     r10d, [r14+3]
0x140038a82  test    r12d, r12d
0x140038a85  jz      short loc_140038AC6
0x140038a87  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140038a8e  jz      loc_140038C4E
0x140038a94  mov     rcx, cs:WPP_GLOBAL_Control
0x140038a9b  mov     r9d, 0E6h
0x140038aa1  mov     eax, [r15+10h]
0x140038aa5  mov     r8d, r10d
0x140038aa8  mov     [rsp+110h+var_E0], r12d
0x140038aad  mov     dl, 2
0x140038aaf  mov     [rsp+110h+var_E8], eax
0x140038ab3  mov     rcx, [rcx+40h]
0x140038ab7  mov     [rsp+110h+var_F0], r11
0x140038abc  call    WPP_RECORDER_SF_DD
0x140038ac1  jmp     loc_140038C4E
0x140038ac6  mov     r12d, [rbp+4Fh+arg_20]
0x140038aca  test    rsi, rsi
0x140038acd  jz      loc_140038C10
0x140038ad3  cmp     r12d, 14h
0x140038ad7  jb      loc_140038C10
0x140038add  mov     eax, [rsi+0Ch]
0x140038ae0  mov     ecx, [rsi+10h]
0x140038ae3  lea     edx, [rax+rcx]
0x140038ae6  cmp     edx, eax
0x140038ae8  jb      loc_140038C10
0x140038aee  cmp     r12d, edx
0x140038af1  jb      loc_140038C10
0x140038af7  lea     r14d, [rcx+16h]
0x140038afb  cmp     r14d, 16h
0x140038aff  jnb     short loc_140038B3F
0x140038b01  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140038b08  jz      short loc_140038B36
0x140038b0a  mov     eax, [r15+10h]
0x140038b0e  mov     r9d, 0E8h
0x140038b14  mov     [rsp+110h+var_E0], ecx
0x140038b18  mov     r8d, r10d
0x140038b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140038b22  mov     dl, 2
0x140038b24  mov     [rsp+110h+var_E8], eax
0x140038b28  mov     [rsp+110h+var_F0], r11
0x140038b2d  mov     rcx, [rcx+40h]
0x140038b31  call    WPP_RECORDER_SF_DD
0x140038b36  or      r14d, 0FFFFFFFFh
0x140038b3a  jmp     loc_140038C4E
0x140038b3f  mov     r8d, 6458424Dh
0x140038b45  mov     edx, r14d
0x140038b48  mov     ecx, 40h ; '@'
0x140038b4d  mov     r13d, r14d
0x140038b50  call    cs:__imp_ExAllocatePool2
0x140038b57  nop     dword ptr [rax+rax+00h]
0x140038b5c  mov     rdi, rax
0x140038b5f  test    rax, rax
0x140038b62  jnz     short loc_140038BB3
0x140038b64  lea     r12, WPP_RECORDER_INITIALIZED
0x140038b6b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140038b72  jz      short loc_140038BA9
0x140038b74  mov     eax, [r15+10h]
0x140038b78  lea     r8d, [rdi+3]
0x140038b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038b83  mov     r9d, 0E9h
0x140038b89  mov     [rsp+110h+var_E0], r14d
0x140038b8e  mov     dl, 2
0x140038b90  mov     [rsp+110h+var_E8], eax
0x140038b94  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140038b9b  mov     [rsp+110h+var_F0], rax
0x140038ba0  mov     rcx, [rcx+40h]
0x140038ba4  call    WPP_RECORDER_SF_DD
0x140038ba9  mov     r13b, [rsp+110h+var_D0]
0x140038bae  jmp     loc_140038C55
0x140038bb3  mov     r8, r13; Size
0x140038bb6  xor     edx, edx; Val
0x140038bb8  mov     rcx, rdi; void *
0x140038bbb  call    memset
0x140038bc0  mov     eax, [rsi]
0x140038bc2  mov     [rdi+8], eax
0x140038bc5  mov     eax, [rsi+4]
0x140038bc8  mov     [rdi+0Ch], eax
0x140038bcb  mov     eax, [rsi+8]
0x140038bce  mov     [rdi+10h], eax
0x140038bd1  mov     dword ptr [rdi], 180180h
0x140038bd7  cmp     r12d, 14h
0x140038bdb  jbe     short loc_140038BFA
0x140038bdd  movzx   eax, word ptr [rsi+10h]
0x140038be1  lea     rcx, [rdi+16h]; void *
0x140038be5  mov     edx, [rsi+0Ch]
0x140038be8  mov     r8d, [rsi+10h]; Size
0x140038bec  add     rdx, rsi; Src
0x140038bef  mov     [rdi+14h], ax
0x140038bf3  call    memmove
0x140038bf8  jmp     short loc_140038C00
0x140038bfa  xor     eax, eax
0x140038bfc  mov     [rdi+14h], ax
0x140038c00  xor     r13b, r13b
0x140038c03  lea     r12, WPP_RECORDER_INITIALIZED
0x140038c0a  test    ebx, ebx
0x140038c0c  jz      short loc_140038C76
0x140038c0e  jmp     short loc_140038C5A
0x140038c10  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140038c17  jz      short loc_140038C4E
0x140038c19  mov     rcx, cs:WPP_GLOBAL_Control
0x140038c20  mov     r9d, 0E7h
0x140038c26  mov     eax, [r15+10h]
0x140038c2a  mov     r8d, r10d
0x140038c2d  mov     [rsp+110h+var_D8], 14h
0x140038c35  mov     dl, 2
0x140038c37  mov     [rsp+110h+var_E0], r12d
0x140038c3c  mov     rcx, [rcx+40h]
0x140038c40  mov     [rsp+110h+var_E8], eax
0x140038c44  mov     [rsp+110h+var_F0], r11
0x140038c49  call    WPP_RECORDER_SF_Ddd
0x140038c4e  lea     r12, WPP_RECORDER_INITIALIZED
0x140038c55  mov     ebx, 0C0040003h
0x140038c5a  mov     esi, [rbp+4Fh+var_CC]
0x140038c5d  mov     ecx, esi
0x140038c5f  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140038c64  test    eax, eax
0x140038c66  jz      short loc_140038C71
0x140038c68  mov     ecx, esi
0x140038c6a  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140038c6f  mov     ebx, eax
0x140038c71  test    r13b, r13b
0x140038c74  jnz     short loc_140038C88
0x140038c76  mov     [rdi+4], ebx
0x140038c79  mov     esi, 18h
0x140038c7e  mov     [rbp+4Fh+var_C0.StatusBuffer], rdi
0x140038c82  mov     [rbp+4Fh+var_C0.StatusBufferSize], r14d
0x140038c86  jmp     short loc_140038CAA
0x140038c88  xorps   xmm0, xmm0
0x140038c8b  mov     dword ptr [rbp+4Fh+var_50], 180180h
0x140038c92  mov     esi, 18h
0x140038c97  mov     dword ptr [rbp+4Fh+var_50+4], ebx
0x140038c9a  lea     rax, [rbp+4Fh+var_50]
0x140038c9e  mov     [rbp+4Fh+var_C0.StatusBufferSize], esi
0x140038ca1  movdqu  [rbp+4Fh+var_50+8], xmm0
0x140038ca6  mov     [rbp+4Fh+var_C0.StatusBuffer], rax
0x140038caa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140038cb1  jz      short loc_140038CE9
0x140038cb3  mov     eax, [r15+10h]
0x140038cb7  mov     r9d, 0EAh
0x140038cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140038cc4  mov     r8d, 3
0x140038cca  mov     [rsp+110h+var_E0], ebx
0x140038cce  mov     dl, 4
0x140038cd0  mov     [rsp+110h+var_E8], eax
0x140038cd4  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140038cdb  mov     [rsp+110h+var_F0], rax
0x140038ce0  mov     rcx, [rcx+40h]
0x140038ce4  call    WPP_RECORDER_SF_DD
0x140038ce9  mov     rdx, [r15+68h]
0x140038ced  test    rdx, rdx
0x140038cf0  jz      short loc_140038D18
0x140038cf2  mov     rax, cs:WdfFunctions_01031
0x140038cf9  mov     r8, cs:off_14005DF38
0x140038d00  mov     rcx, cs:WdfDriverGlobals
0x140038d07  mov     rax, [rax+650h]
0x140038d0e  call    _guard_dispatch_icall
0x140038d13  add     rax, rsi
0x140038d16  jmp     short loc_140038D29
0x140038d18  mov     rax, [r15+30h]
0x140038d1c  mov     rdx, [rax]
0x140038d1f  mov     rax, [rdx+478h]
0x140038d26  mov     rax, [rax]
0x140038d29  lea     rdx, [rbp+4Fh+var_C0]; struct _NDIS_STATUS_INDICATION *
0x140038d2d  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x140038d30  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x140038d35  test    rdi, rdi
0x140038d38  jz      short loc_140038D4B
0x140038d3a  xor     edx, edx; Tag
0x140038d3c  mov     rcx, rdi; P
0x140038d3f  call    cs:__imp_ExFreePoolWithTag
0x140038d46  nop     dword ptr [rax+rax+00h]
0x140038d4b  xor     eax, eax
0x140038d4d  mov     rcx, [rbp+4Fh+var_38]
0x140038d51  xor     rcx, rsp; StackCookie
0x140038d54  call    __security_check_cookie
0x140038d59  mov     rbx, [rsp+110h+arg_8]
0x140038d61  add     rsp, 0E0h
0x140038d68  pop     r15
0x140038d6a  pop     r14
0x140038d6c  pop     r13
0x140038d6e  pop     r12
0x140038d70  pop     rdi
0x140038d71  pop     rsi
0x140038d72  pop     rbp
0x140038d73  retn
```
