# TR_Create

- ea: `0x140082ab4`
- end: `0x140083189`
- name: `TR_Create`
- size: `1749`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140048ae0`
- `0x140081c68`

## callees

- `0x14002bad0`
- `0x1400339b4`
- `0x140035738`
- `0x1400360ec`
- `0x1400389a4`
- `0x14003c6e4`
- `0x14004bc20`
- `0x1400599b0`
- `0x140059d80`
- `0x140082ab4`
- `0x140083190`
- `0x1400832b8`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140082f4f`
- `ntoskrnl!KeInitializeSpinLock` at `0x140082f4f`

## pseudocode

```c
__int64 __fastcall TR_Create(__int64 *a1, __int64 a2, __int64 a3, int a4, __int64 *a5)
{
  int v9; // ecx
  int v10; // edx
  __int64 v11; // rax
  bool v12; // zf
  int v13; // eax
  int v14; // eax
  int SecureObject; // ebx
  int v16; // r10d
  int v17; // r11d
  int v18; // edx
  __int64 (__fastcall **v19)(); // r15
  unsigned int v20; // r8d
  int v21; // r9d
  char IsSecureDevice; // al
  int v23; // eax
  char IsProxyEndpoint; // al
  __int64 v25; // rdx
  int v26; // r10d
  int v27; // ecx
  int v28; // edx
  __int64 v29; // rax
  __int128 v30; // xmm0
  __int64 v31; // rdi
  __int128 v32; // xmm1
  char IsSecureUsbDevice; // al
  __int64 (__fastcall *v34)(); // r8
  int v35; // edx
  int v36; // r8d
  int v37; // r9d
  __int64 v38; // rax
  __int64 (__fastcall *v39)(); // r8
  __int64 (__fastcall *v40)(); // r8
  __int128 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v43; // [rsp+60h] [rbp-A0h]
  __int128 v44; // [rsp+70h] [rbp-90h]
  __int64 *v45; // [rsp+80h] [rbp-80h]
  __int128 v46; // [rsp+88h] [rbp-78h] BYREF
  __int128 v47; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall **v48)(); // [rsp+A8h] [rbp-58h]
  __int128 v49; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h]
  __int128 v51; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v52; // [rsp+D8h] [rbp-28h]
  _QWORD v53[12]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v54; // [rsp+178h] [rbp+78h] BYREF

  LODWORD(v52) = 0;
  LODWORD(v50) = 0;
  LODWORD(v45) = 0;
  v51 = 0;
  v49 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  memset(v53, 0, sizeof(v53));
  v54 = 0;
  v46 = 0;
  v48 = 0;
  v47 = 0;
  if ( (unsigned __int8)Endpoint_IsProxyEndpoint(a2) )
  {
    v9 = 16776704;
    v10 = -1;
  }
  else
  {
    v11 = a1[12];
    v9 = *(_DWORD *)(v11 + 16);
    v10 = *(_DWORD *)(v11 + 20);
  }
  DWORD2(v46) = v10;
  DWORD1(v46) = v9 - 4096;
  v12 = (*(_BYTE *)(a2 + 99) & 3) == 0;
  v13 = *(_BYTE *)(a2 + 99) & 3;
  LODWORD(v46) = v13;
  if ( v12 )
  {
    v19 = ControlFunctionTable;
    HIDWORD(v46) = 1;
    LODWORD(v47) = 400;
    IsSecureDevice = Controller_IsSecureDevice(a1);
    v12 = (a1[92] & 8) == 0;
    DWORD2(v47) = IsSecureDevice == 0 ? v21 : 0;
    if ( v12 )
      goto LABEL_10;
    goto LABEL_15;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    HIDWORD(v46) = 3;
    LODWORD(v47) = 448;
    DWORD2(v47) = 0;
    v19 = IsochFunctionTable;
    if ( !(unsigned __int8)Endpoint_IsProxyEndpoint(a2) )
    {
LABEL_10:
      DWORD1(v47) = v21;
      goto LABEL_11;
    }
LABEL_15:
    DWORD1(v47) = 4096;
    goto LABEL_11;
  }
  if ( (unsigned int)(v14 - 1) >= 2 )
    return (unsigned int)-1073741823;
  Bulk_GetConfiguration(a1, 3, &v46, 512);
  v18 = HIDWORD(v46);
  v19 = v48;
  v20 = v47;
LABEL_11:
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x21 )
      LODWORD(v53[0]) = v17;
    else
      LODWORD(v53[0]) = *(_DWORD *)(WdfStructures + 264);
  }
  else
  {
    LODWORD(v53[0]) = 96;
  }
  v23 = v53[10];
  LODWORD(v53[1]) = 2;
  HIDWORD(v53[0]) = v18;
  if ( v18 == 2 )
    v23 = v17;
  LODWORD(v53[10]) = v23;
  v53[2] = v19[20];
  v53[9] = v19[21];
  v45 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v42) = v17;
    else
      LODWORD(v42) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v42) = 56;
  }
  v45 = off_14006C270;
  *((_QWORD *)&v44 + 1) = v20;
  *((_QWORD *)&v42 + 1) = TR_WdfEvtCleanupCallback;
  DWORD2(v43) = v16;
  HIDWORD(v43) = v16;
  *(_QWORD *)&v44 = a3;
  IsProxyEndpoint = Endpoint_IsProxyEndpoint(a2);
  v25 = *a1;
  v27 = v26;
  if ( IsProxyEndpoint )
    v27 = 2;
  DWORD2(v43) = v27;
  SecureObject = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *, __int128 *, __int64 *))(WdfFunctions_01033 + 1216))(
                   WdfDriverGlobals,
                   v25,
                   v53,
                   &v42,
                   &v54);
  if ( SecureObject < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v28) = 2;
      WPP_RECORDER_SF_DDDd(
        a1[9],
        v28,
        *(unsigned __int8 *)(*(_QWORD *)(a2 + 16) + 143LL),
        10,
        (__int64)WPP_dd12c690235e31d2d4306bcf93bb1f34_Traceguids,
        *(_BYTE *)(*(_QWORD *)(a2 + 16) + 143LL),
        *(_DWORD *)(a2 + 152),
        a4,
        SecureObject);
    }
    return (unsigned int)SecureObject;
  }
  v29 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
          WdfDriverGlobals,
          v54,
          off_14006C270);
  v30 = v46;
  v31 = v29;
  v32 = v47;
  *(_QWORD *)(v29 + 40) = a1;
  *(_OWORD *)v29 = v30;
  *(_OWORD *)(v29 + 16) = v32;
  *(_QWORD *)(v29 + 32) = v19;
  *(_QWORD *)(v29 + 48) = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(v29 + 56) = a2;
  *(_DWORD *)(v29 + 64) = a4;
  *(_QWORD *)(v29 + 72) = v54;
  *(_QWORD *)(v29 + 312) = 0;
  *(_DWORD *)(v29 + 320) = 0;
  if ( (unsigned __int8)Controller_IsSecureDevice(a1) )
  {
    if ( *((_DWORD *)a1 + 263) == 2 )
      IsSecureUsbDevice = XilUsbDevice_IsSecureUsbDevice(*(_QWORD *)(a2 + 16));
    else
      IsSecureUsbDevice = 1;
    *(_BYTE *)(v31 + 288) = IsSecureUsbDevice;
    v34 = v19[24];
    v50 = 0;
    v49 = 0;
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x43 )
        LODWORD(v49) = -1;
      else
        LODWORD(v49) = *(_DWORD *)(WdfStructures + 536);
    }
    else
    {
      LODWORD(v49) = 24;
    }
    *((_QWORD *)&v49 + 1) = v34;
    LOBYTE(v50) = 1;
    v45 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x26 )
        LODWORD(v42) = -1;
      else
        LODWORD(v42) = *(_DWORD *)(WdfStructures + 304);
    }
    else
    {
      LODWORD(v42) = 56;
    }
    *(_QWORD *)&v44 = v54;
    *((_QWORD *)&v43 + 1) = 0x100000001LL;
    SecureObject = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033 + 3032))(
                     WdfDriverGlobals,
                     &v49,
                     &v42,
                     v31 + 88);
    if ( SecureObject < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)SecureObject;
      v37 = 11;
      goto LABEL_47;
    }
  }
  else
  {
    *(_BYTE *)(v31 + 288) = 0;
  }
  KeInitializeSpinLock((PKSPIN_LOCK)(v31 + 96));
  *(_QWORD *)(v31 + 216) = v31 + 208;
  *(_QWORD *)(v31 + 208) = v31 + 208;
  *(_QWORD *)(v31 + 232) = v31 + 224;
  *(_QWORD *)(v31 + 224) = v31 + 224;
  if ( *(_BYTE *)(v31 + 288) )
  {
    SecureObject = TR_CreateSecureObject(v31);
    if ( SecureObject < 0 )
      return (unsigned int)SecureObject;
  }
  else
  {
    SecureObject = TR_EnsureSegments(v31);
    if ( SecureObject < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)SecureObject;
      v38 = *(_QWORD *)(v31 + 48);
      v37 = 12;
      goto LABEL_48;
    }
  }
  v39 = v19[22];
  if ( v39 )
  {
    SecureObject = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(), __int64))(WdfFunctions_01033 + 1328))(
                     WdfDriverGlobals,
                     v54,
                     v39,
                     v31);
    if ( SecureObject < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)SecureObject;
      v37 = 13;
      goto LABEL_47;
    }
  }
  v40 = v19[23];
  v52 = 0;
  v51 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x17 )
      LODWORD(v51) = -1;
    else
      LODWORD(v51) = *(_DWORD *)(WdfStructures + 184);
  }
  else
  {
    LODWORD(v51) = 24;
  }
  *((_QWORD *)&v51 + 1) = v40;
  v45 = 0;
  LOBYTE(v52) = 1;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v42) = -1;
    else
      LODWORD(v42) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v42) = 56;
  }
  *(_QWORD *)&v44 = v54;
  *((_QWORD *)&v43 + 1) = 0x100000001LL;
  SecureObject = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033
                                                                                                 + 888))(
                   WdfDriverGlobals,
                   &v51,
                   &v42,
                   v31 + 80);
  if ( SecureObject < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)SecureObject;
    v37 = 14;
    goto LABEL_47;
  }
  *(_QWORD *)(v31 + 176) = TR_AcquireSegment(v31);
  SecureObject = ((__int64 (__fastcall *)(__int64))*v19)(v31);
  if ( SecureObject >= 0 )
  {
    Counter_CreateTransferRingInstance(*(__int64 **)(v31 + 56), *(_DWORD *)(v31 + 64), (PPCW_INSTANCE *)(v31 + 248));
    *a5 = v31;
    return (unsigned int)SecureObject;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v37 = 15;
LABEL_47:
    v38 = *(_QWORD *)(a2 + 16);
LABEL_48:
    LOBYTE(v35) = 2;
    WPP_RECORDER_SF_DDDd(
      a1[9],
      v35,
      v36,
      v37,
      (__int64)WPP_dd12c690235e31d2d4306bcf93bb1f34_Traceguids,
      *(_BYTE *)(v38 + 143),
      *(_DWORD *)(a2 + 152),
      a4,
      SecureObject);
  }
  return (unsigned int)SecureObject;
}

```

## disassembly

```asm
0x140082ab4  mov     [rsp-8+arg_0], rbx
0x140082ab9  mov     [rsp-8+arg_10], rsi
0x140082abe  push    rbp
0x140082abf  push    rdi
0x140082ac0  push    r12
0x140082ac2  push    r14
0x140082ac4  push    r15
0x140082ac6  lea     rbp, [rsp-40h]
0x140082acb  sub     rsp, 140h
0x140082ad2  xorps   xmm0, xmm0
0x140082ad5  xor     eax, eax
0x140082ad7  mov     rbx, r8
0x140082ada  mov     dword ptr [rbp+60h+var_88], eax
0x140082add  mov     rsi, rdx
0x140082ae0  mov     dword ptr [rbp+60h+var_A0], eax
0x140082ae3  mov     r14, rcx
0x140082ae6  mov     dword ptr [rbp+60h+var_E0], eax
0x140082ae9  lea     edi, [rax+60h]
0x140082aec  xor     edx, edx; Val
0x140082aee  mov     r8d, edi; Size
0x140082af1  lea     rcx, [rbp+60h+var_80]; void *
0x140082af5  mov     r12d, r9d
0x140082af8  movups  [rbp+60h+var_98], xmm0
0x140082afc  movups  [rbp+60h+var_B0], xmm0
0x140082b00  movups  [rsp+160h+var_110], xmm0
0x140082b05  movups  [rsp+160h+var_100], xmm0
0x140082b0a  movups  [rsp+160h+var_F0], xmm0
0x140082b0f  call    memset
0x140082b14  xorps   xmm0, xmm0
0x140082b17  mov     [rbp+60h+arg_8], 0
0x140082b1f  xor     eax, eax
0x140082b21  mov     rcx, rsi
0x140082b24  movups  [rbp+60h+var_D8], xmm0
0x140082b28  mov     [rbp+60h+var_B8], rax
0x140082b2c  movups  [rbp+60h+var_C8], xmm0
0x140082b30  call    Endpoint_IsProxyEndpoint
0x140082b35  or      r11d, 0FFFFFFFFh
0x140082b39  test    al, al
0x140082b3b  jz      short loc_140082B47
0x140082b3d  mov     ecx, 0FFFE00h
0x140082b42  mov     edx, r11d
0x140082b45  jmp     short loc_140082B51
0x140082b47  mov     rax, [r14+60h]
0x140082b4b  mov     ecx, [rax+10h]
0x140082b4e  mov     edx, [rax+14h]
0x140082b51  lea     eax, [rcx-1000h]
0x140082b57  mov     dword ptr [rbp+60h+var_D8+8], edx
0x140082b5a  mov     dword ptr [rbp+60h+var_D8+4], eax
0x140082b5d  mov     edx, 3
0x140082b62  movzx   eax, byte ptr [rsi+63h]
0x140082b66  mov     r9d, 200h
0x140082b6c  and     eax, edx
0x140082b6e  mov     dword ptr [rbp+60h+var_D8], eax
0x140082b71  lea     r10d, [rdx-2]
0x140082b75  jz      loc_140082BFF
0x140082b7b  sub     eax, r10d
0x140082b7e  jz      short loc_140082BAD
0x140082b80  sub     eax, r10d
0x140082b83  jz      short loc_140082B94
0x140082b85  cmp     eax, r10d
0x140082b88  jz      short loc_140082B94
0x140082b8a  mov     ebx, 0C0000001h
0x140082b8f  jmp     loc_14008316A
0x140082b94  lea     r8, [rbp+60h+var_D8]
0x140082b98  mov     rcx, r14
0x140082b9b  call    Bulk_GetConfiguration
0x140082ba0  mov     edx, dword ptr [rbp+60h+var_D8+0Ch]
0x140082ba3  mov     r15, [rbp+60h+var_B8]
0x140082ba7  mov     r8d, dword ptr [rbp+60h+var_C8]
0x140082bab  jmp     short loc_140082BD8
0x140082bad  mov     r8d, 1C0h
0x140082bb3  mov     dword ptr [rbp+60h+var_D8+0Ch], edx
0x140082bb6  mov     rcx, rsi
0x140082bb9  mov     dword ptr [rbp+60h+var_C8], r8d
0x140082bbd  mov     dword ptr [rbp+60h+var_C8+8], 0
0x140082bc4  lea     r15, IsochFunctionTable
0x140082bcb  call    Endpoint_IsProxyEndpoint
0x140082bd0  test    al, al
0x140082bd2  jnz     short loc_140082C34
0x140082bd4  mov     dword ptr [rbp+60h+var_C8+4], r9d
0x140082bd8  mov     r9b, cs:WdfClientVersionHigherThanFramework
0x140082bdf  test    r9b, r9b
0x140082be2  jz      short loc_140082C43
0x140082be4  cmp     cs:WdfStructureCount, 21h ; '!'
0x140082beb  jbe     short loc_140082C3D
0x140082bed  mov     rax, cs:WdfStructures
0x140082bf4  mov     ecx, [rax+108h]
0x140082bfa  mov     [rbp+60h+var_80], ecx
0x140082bfd  jmp     short loc_140082C46
0x140082bff  mov     edx, r10d
0x140082c02  lea     r15, ControlFunctionTable
0x140082c09  mov     r8d, 190h
0x140082c0f  mov     dword ptr [rbp+60h+var_D8+0Ch], edx
0x140082c12  mov     rcx, r14
0x140082c15  mov     dword ptr [rbp+60h+var_C8], r8d
0x140082c19  call    Controller_IsSecureDevice
0x140082c1e  neg     al
0x140082c20  sbb     ecx, ecx
0x140082c22  not     ecx
0x140082c24  and     ecx, r9d
0x140082c27  test    byte ptr [r14+2E0h], 8
0x140082c2f  mov     dword ptr [rbp+60h+var_C8+8], ecx
0x140082c32  jz      short loc_140082BD4
0x140082c34  mov     dword ptr [rbp+60h+var_C8+4], 1000h
0x140082c3b  jmp     short loc_140082BD8
0x140082c3d  mov     [rbp+60h+var_80], r11d
0x140082c41  jmp     short loc_140082C46
0x140082c43  mov     [rbp+60h+var_80], edi
0x140082c46  mov     eax, [rbp+60h+var_30]
0x140082c49  mov     edi, 2
0x140082c4e  cmp     edx, edi
0x140082c50  mov     [rbp+60h+var_78], edi
0x140082c53  mov     [rbp+60h+var_7C], edx
0x140082c56  cmovz   eax, r11d
0x140082c5a  mov     [rbp+60h+var_30], eax
0x140082c5d  mov     rax, [r15+0A0h]
0x140082c64  mov     [rbp+60h+var_70], rax
0x140082c68  mov     rax, [r15+0A8h]
0x140082c6f  mov     [rbp+60h+var_38], rax
0x140082c73  xor     eax, eax
0x140082c75  mov     [rbp+60h+var_E0], rax
0x140082c79  movups  [rsp+160h+var_110], xmm0
0x140082c7e  movups  [rsp+160h+var_100], xmm0
0x140082c83  movups  [rsp+160h+var_F0], xmm0
0x140082c88  test    r9b, r9b
0x140082c8b  jz      short loc_140082CB0
0x140082c8d  cmp     cs:WdfStructureCount, 26h ; '&'
0x140082c94  jbe     short loc_140082CA9
0x140082c96  mov     rax, cs:WdfStructures
0x140082c9d  mov     ecx, [rax+130h]
0x140082ca3  mov     dword ptr [rsp+160h+var_110], ecx
0x140082ca7  jmp     short loc_140082CB8
0x140082ca9  mov     dword ptr [rsp+160h+var_110], r11d
0x140082cae  jmp     short loc_140082CB8
0x140082cb0  mov     dword ptr [rsp+160h+var_110], 38h ; '8'
0x140082cb8  mov     rax, cs:off_14006C270
0x140082cbf  mov     rcx, rsi
0x140082cc2  mov     [rbp+60h+var_E0], rax
0x140082cc6  mov     eax, r8d
0x140082cc9  mov     qword ptr [rsp+160h+var_F0+8], rax
0x140082cce  lea     rax, TR_WdfEvtCleanupCallback
0x140082cd5  mov     qword ptr [rsp+160h+var_110+8], rax
0x140082cda  mov     dword ptr [rsp+160h+var_100+8], r10d
0x140082cdf  mov     dword ptr [rsp+160h+var_100+0Ch], r10d
0x140082ce4  mov     qword ptr [rsp+160h+var_F0], rbx
0x140082ce9  call    Endpoint_IsProxyEndpoint
0x140082cee  mov     rdx, [r14]
0x140082cf1  lea     r9, [rsp+160h+var_110]
0x140082cf6  test    al, al
0x140082cf8  lea     r8, [rbp+60h+var_80]
0x140082cfc  mov     rax, cs:WdfFunctions_01033
0x140082d03  mov     ecx, r10d
0x140082d06  cmovnz  ecx, edi
0x140082d09  mov     dword ptr [rsp+160h+var_100+8], ecx
0x140082d0d  lea     rcx, [rbp+60h+arg_8]
0x140082d11  mov     [rsp+160h+var_140], rcx
0x140082d16  mov     rcx, cs:WdfDriverGlobals
0x140082d1d  mov     rax, [rax+4C0h]
0x140082d24  call    _guard_dispatch_icall
0x140082d29  mov     ebx, eax
0x140082d2b  test    eax, eax
0x140082d2d  jns     short loc_140082D8A
0x140082d2f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140082d36  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140082d3d  jz      loc_14008316A
0x140082d43  mov     rcx, [rsi+10h]
0x140082d47  mov     r9d, 0Ah
0x140082d4d  mov     eax, [rsi+98h]
0x140082d53  mov     dl, dil
0x140082d56  mov     [rsp+160h+var_120], ebx
0x140082d5a  mov     [rsp+160h+var_128], r12d
0x140082d5f  movzx   r8d, byte ptr [rcx+8Fh]
0x140082d67  mov     [rsp+160h+var_130], eax
0x140082d6b  mov     [rsp+160h+var_138], r8d
0x140082d70  mov     rcx, [r14+48h]
0x140082d74  lea     rax, WPP_dd12c690235e31d2d4306bcf93bb1f34_Traceguids
0x140082d7b  mov     [rsp+160h+var_140], rax
0x140082d80  call    WPP_RECORDER_SF_DDDd
0x140082d85  jmp     loc_14008316A
0x140082d8a  mov     rax, cs:WdfFunctions_01033
0x140082d91  mov     r8, cs:off_14006C270
0x140082d98  mov     rdx, [rbp+60h+arg_8]
0x140082d9c  mov     rcx, cs:WdfDriverGlobals
0x140082da3  mov     rax, [rax+650h]
0x140082daa  call    _guard_dispatch_icall
0x140082daf  movups  xmm0, [rbp+60h+var_D8]
0x140082db3  mov     rdi, rax
0x140082db6  movups  xmm1, [rbp+60h+var_C8]
0x140082dba  mov     [rax+28h], r14
0x140082dbe  movups  xmmword ptr [rax], xmm0
0x140082dc1  movups  xmmword ptr [rax+10h], xmm1
0x140082dc5  mov     [rax+20h], r15
0x140082dc9  mov     rcx, [rsi+10h]
0x140082dcd  mov     [rax+30h], rcx
0x140082dd1  mov     rcx, r14
0x140082dd4  mov     [rax+38h], rsi
0x140082dd8  mov     [rax+40h], r12d
0x140082ddc  mov     rax, [rbp+60h+arg_8]
0x140082de0  mov     [rdi+48h], rax
0x140082de4  mov     qword ptr [rdi+138h], 0
0x140082def  mov     dword ptr [rdi+140h], 0
0x140082df9  call    Controller_IsSecureDevice
0x140082dfe  test    al, al
0x140082e00  jz      loc_140082F44
0x140082e06  cmp     dword ptr [r14+41Ch], 2
0x140082e0e  jnz     short loc_140082E1B
0x140082e10  mov     rcx, [rsi+10h]
0x140082e14  call    XilUsbDevice_IsSecureUsbDevice
0x140082e19  jmp     short loc_140082E1D
0x140082e1b  mov     al, 1
0x140082e1d  mov     [rdi+120h], al
0x140082e23  xorps   xmm0, xmm0
0x140082e26  mov     r8, [r15+0C0h]
0x140082e2d  xor     eax, eax
0x140082e2f  mov     dl, cs:WdfClientVersionHigherThanFramework
0x140082e35  mov     [rbp+60h+var_A0], rax
0x140082e39  movups  [rbp+60h+var_B0], xmm0
0x140082e3d  test    dl, dl
0x140082e3f  jz      short loc_140082E65
0x140082e41  cmp     cs:WdfStructureCount, 43h ; 'C'
0x140082e48  jbe     short loc_140082E5C
0x140082e4a  mov     rax, cs:WdfStructures
0x140082e51  mov     ecx, [rax+218h]
0x140082e57  mov     dword ptr [rbp+60h+var_B0], ecx
0x140082e5a  jmp     short loc_140082E6C
0x140082e5c  mov     dword ptr [rbp+60h+var_B0], 0FFFFFFFFh
0x140082e63  jmp     short loc_140082E6C
0x140082e65  mov     dword ptr [rbp+60h+var_B0], 18h
0x140082e6c  xor     eax, eax
0x140082e6e  mov     qword ptr [rbp+60h+var_B0+8], r8
0x140082e72  mov     byte ptr [rbp+60h+var_A0], 1
0x140082e76  mov     [rbp+60h+var_E0], rax
0x140082e7a  movups  [rsp+160h+var_110], xmm0
0x140082e7f  movups  [rsp+160h+var_100], xmm0
0x140082e84  movups  [rsp+160h+var_F0], xmm0
0x140082e89  test    dl, dl
0x140082e8b  jz      short loc_140082EB3
0x140082e8d  cmp     cs:WdfStructureCount, 26h ; '&'
0x140082e94  jbe     short loc_140082EA9
0x140082e96  mov     rax, cs:WdfStructures
0x140082e9d  mov     ecx, [rax+130h]
0x140082ea3  mov     dword ptr [rsp+160h+var_110], ecx
0x140082ea7  jmp     short loc_140082EBB
0x140082ea9  mov     dword ptr [rsp+160h+var_110], 0FFFFFFFFh
0x140082eb1  jmp     short loc_140082EBB
0x140082eb3  mov     dword ptr [rsp+160h+var_110], 38h ; '8'
0x140082ebb  mov     rax, [rbp+60h+arg_8]
0x140082ebf  lea     r9, [rdi+58h]
0x140082ec3  mov     rcx, cs:WdfDriverGlobals
0x140082eca  lea     r8, [rsp+160h+var_110]
0x140082ecf  mov     qword ptr [rsp+160h+var_F0], rax
0x140082ed4  lea     rdx, [rbp+60h+var_B0]
0x140082ed8  mov     rax, cs:WdfFunctions_01033
0x140082edf  mov     dword ptr [rsp+160h+var_100+8], 1
0x140082ee7  mov     dword ptr [rsp+160h+var_100+0Ch], 1
0x140082eef  mov     rax, [rax+0BD8h]
0x140082ef6  call    _guard_dispatch_icall
0x140082efb  mov     ebx, eax
0x140082efd  test    eax, eax
0x140082eff  jns     short loc_140082F4B
0x140082f01  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140082f08  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140082f0f  jz      loc_14008316A
0x140082f15  mov     r9d, 0Bh
0x140082f1b  mov     rax, [rsi+10h]
0x140082f1f  movzx   ecx, byte ptr [rax+8Fh]
0x140082f26  mov     dl, 2
0x140082f28  mov     eax, [rsi+98h]
0x140082f2e  mov     [rsp+160h+var_120], ebx
0x140082f32  mov     [rsp+160h+var_128], r12d
0x140082f37  mov     [rsp+160h+var_130], eax
0x140082f3b  mov     [rsp+160h+var_138], ecx
0x140082f3f  jmp     loc_140082D70
0x140082f44  mov     byte ptr [rdi+120h], 0
0x140082f4b  lea     rcx, [rdi+60h]; SpinLock
0x140082f4f  call    cs:__imp_KeInitializeSpinLock
0x140082f56  nop     dword ptr [rax+rax+00h]
0x140082f5b  lea     rax, [rdi+0D0h]
0x140082f62  mov     rcx, rdi
0x140082f65  mov     [rax+8], rax
0x140082f69  mov     [rax], rax
0x140082f6c  lea     rax, [rdi+0E0h]
0x140082f73  mov     [rax+8], rax
0x140082f77  mov     [rax], rax
0x140082f7a  cmp     byte ptr [rdi+120h], 0
0x140082f81  jz      short loc_140082FE4
0x140082f83  call    TR_CreateSecureObject
0x140082f88  mov     ebx, eax
0x140082f8a  test    eax, eax
0x140082f8c  js      loc_14008316A
0x140082f92  mov     r8, [r15+0B0h]
0x140082f99  test    r8, r8
0x140082f9c  jz      short loc_140083019
0x140082f9e  mov     rax, cs:WdfFunctions_01033
0x140082fa5  mov     r9, rdi
0x140082fa8  mov     rdx, [rbp+60h+arg_8]
0x140082fac  mov     rcx, cs:WdfDriverGlobals
0x140082fb3  mov     rax, [rax+530h]
0x140082fba  call    _guard_dispatch_icall
0x140082fbf  mov     ebx, eax
  ... truncated ...
```
