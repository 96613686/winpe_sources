# MbbNdisModemConfigInfoHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140030100`
- end: `0x140030584`
- name: `?MbbNdisModemConfigInfoHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `1156`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x140005644`
- `0x140030100`
- `0x14003f7e4`
- `0x14003f994`
- `0x140047458`
- `0x140047530`
- `0x140047814`
- `0x140047e50`
- `0x140047e90`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140030368`
- `ntoskrnl!ExAllocatePool2` at `0x140030368`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400304f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400304f9`

## pseudocode

```c
__int64 __fastcall MbbNdisModemConfigInfoHandler(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        _DWORD *a4,
        unsigned int a5)
{
  int v9; // edx
  int v10; // edx
  int v11; // eax
  int v12; // r9d
  unsigned int v13; // r15d
  mbbcx_p *v14; // r13
  struct _MBB_TLV_IE *v15; // rax
  int v16; // ecx
  int v17; // r9d
  char *Pool2; // r12
  unsigned int v20; // eax
  _DWORD *v21; // rdx
  unsigned int v22; // ecx
  int v23; // edx
  bool v24; // zf
  __int64 v25; // rax
  __int64 v26; // rdx
  NDIS_HANDLE *v27; // rax
  char v28; // [rsp+30h] [rbp-A1h]
  int v29; // [rsp+38h] [rbp-99h]
  unsigned int v30; // [rsp+40h] [rbp-91h] BYREF
  unsigned __int8 *v31; // [rsp+44h] [rbp-8Dh] BYREF
  unsigned int v32; // [rsp+4Ch] [rbp-85h]
  _DWORD *v33; // [rsp+50h] [rbp-81h] BYREF
  struct _MBB_TLV_IE *v34; // [rsp+58h] [rbp-79h] BYREF
  _DWORD *v35; // [rsp+60h] [rbp-71h]
  struct _NDIS_STATUS_INDICATION v36; // [rsp+70h] [rbp-61h] BYREF

  v32 = a3;
  v35 = a4;
  memset(&v36, 0, sizeof(v36));
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        413,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a2);
    }
    return a2;
  }
  if ( !a4 || a5 < 0xC )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741823;
    v29 = 12;
    v17 = 414;
    v28 = a5;
LABEL_42:
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_Ddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      3,
      v17,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v28,
      v29);
    return (unsigned int)-1073741823;
  }
  v30 = 0;
  v33 = a4 + 1;
  LODWORD(v31) = a5 - 4;
  if ( !mbbcx_p::ExtractValidateNextTlv((mbbcx_p *)&v33, &v31, &v30, (enum mbbcx_p::MbbTlvError *)0xA) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = v30;
      v12 = 415;
LABEL_9:
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        v12,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v11);
    }
    return (unsigned int)-1073741823;
  }
  v13 = 0;
  v14 = 0;
  HIDWORD(v31) = 0;
  v34 = 0;
  if ( !a3 && (_DWORD)v31 )
  {
    do
    {
      v15 = mbbcx_p::ExtractValidateNextTlv((mbbcx_p *)&v33, &v31, &v30, 0);
      if ( !v15 )
        break;
      v9 = 6;
      if ( *(_WORD *)v15 == 6 )
      {
        v11 = mbbcx_p::CalculateSNssaiCntFromTlvPrecfgDfltCfgNssai((__int64)v15, (_DWORD *)&v31 + 1, &v34);
        if ( !v11 )
        {
          v13 = HIDWORD(v31);
          v14 = v34;
          goto LABEL_27;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return (unsigned int)-1073741823;
        v12 = 416;
        goto LABEL_9;
      }
    }
    while ( (_DWORD)v31 );
    if ( !(_DWORD)v31 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 4;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          3,
          418,
          (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
          *(_DWORD *)(a1 + 16));
      }
      goto LABEL_27;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741823;
    if ( v15 )
      v16 = *(unsigned __int16 *)v15;
    else
      v16 = 0;
    v17 = 417;
    v29 = v16;
    v28 = v30;
    goto LABEL_42;
  }
LABEL_27:
  HIDWORD(v31) = 16 * v13 + 236;
  Pool2 = (char *)ExAllocatePool2(64, HIDWORD(v31), 1683505741);
  if ( !Pool2 )
    return 3221225626LL;
  v20 = MbbUtilMbbToWwanStatus(v32);
  v30 = v20;
  *(_DWORD *)Pool2 = 15467136;
  *((_DWORD *)Pool2 + 1) = v20;
  memset(Pool2 + 8, 0, 0xE4u);
  v21 = v35;
  *((_DWORD *)Pool2 + 3) = *v35;
  v22 = v21[2] >> 1;
  if ( v22 >= 0x41 )
    v22 = 64;
  memmove(Pool2 + 96, v21 + 3, 2LL * v22);
  v24 = v32 == 0;
  *((_DWORD *)Pool2 + 57) = 24;
  if ( v24 && v13 )
  {
    *((_DWORD *)Pool2 + 58) = v13;
    mbbcx_p::ParseTlvNSSAI(v14, (struct _MBB_TLV_IE *const)(Pool2 + 236), (struct _WWAN_SINGLE_NSSAI *)v13);
  }
  v25 = *(_QWORD *)(a1 + 48);
  v36.Header = (NDIS_OBJECT_HEADER)7340440;
  v36.SourceHandle = *(NDIS_HANDLE *)(**(_QWORD **)(*(_QWORD *)v25 + 1144LL) + 16LL);
  v36.DestinationHandle = *(NDIS_HANDLE *)(a1 + 440);
  v36.RequestId = *(PVOID *)(a1 + 432);
  v36.StatusBufferSize = HIDWORD(v31);
  v36.PortNumber = 0;
  *(_QWORD *)&v36.StatusCode = 1074008128;
  v36.Guid = 0;
  v36.StatusBuffer = Pool2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v23) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      3,
      419,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v30);
  }
  v26 = *(_QWORD *)(a1 + 104);
  if ( v26 )
    v27 = (NDIS_HANDLE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                            WdfDriverGlobals,
                            v26,
                            off_14005DF38)
                        + 24);
  else
    v27 = **(NDIS_HANDLE ***)(**(_QWORD **)(a1 + 48) + 1144LL);
  MbbUtilNdisMiniportIndicateStatusEx(v27, &v36);
  ExFreePoolWithTag(Pool2, 0);
  return a2;
}

```

## disassembly

```asm
0x140030100  mov     [rsp-8+arg_8], rbx
0x140030105  push    rbp
0x140030106  push    rsi
0x140030107  push    rdi
0x140030108  push    r12
0x14003010a  push    r13
0x14003010c  push    r14
0x14003010e  push    r15
0x140030110  lea     rbp, [rsp-1Fh]
0x140030115  sub     rsp, 0F0h
0x14003011c  mov     rax, cs:__security_cookie
0x140030123  xor     rax, rsp
0x140030126  mov     [rbp+4Fh+var_40], rax
0x14003012a  mov     ebx, edx
0x14003012c  mov     [rsp+120h+var_D4], r8d
0x140030131  xor     edx, edx; Val
0x140030133  mov     [rbp+4Fh+var_C0], r9
0x140030137  mov     r12d, r8d
0x14003013a  mov     r14, rcx
0x14003013d  lea     rcx, [rbp+4Fh+var_B0]; void *
0x140030141  mov     rdi, r9
0x140030144  lea     r8d, [rdx+70h]; Size
0x140030148  call    memset
0x14003014d  test    ebx, ebx
0x14003014f  jz      short loc_1400301A0
0x140030151  lea     rdi, WPP_RECORDER_INITIALIZED
0x140030158  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003015f  jz      loc_14003055A
0x140030165  mov     rcx, cs:WPP_GLOBAL_Control
0x14003016c  lea     rsi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140030173  mov     eax, [r14+10h]
0x140030177  mov     r9d, 19Dh
0x14003017d  mov     dword ptr [rsp+120h+var_F0], ebx
0x140030181  mov     r8d, 3
0x140030187  mov     [rsp+120h+var_F8], eax
0x14003018b  mov     dl, 2
0x14003018d  mov     rcx, [rcx+40h]
0x140030191  mov     [rsp+120h+var_100], rsi
0x140030196  call    WPP_RECORDER_SF_DD
0x14003019b  jmp     loc_14003055A
0x1400301a0  mov     ecx, [rbp+4Fh+arg_20]
0x1400301a3  test    rdi, rdi
0x1400301a6  jz      loc_140030507
0x1400301ac  cmp     ecx, 0Ch
0x1400301af  jb      loc_140030507
0x1400301b5  lea     rax, [rdi+4]
0x1400301b9  mov     [rsp+120h+var_E0], 0
0x1400301c1  mov     [rsp+120h+var_D0], rax
0x1400301c6  lea     r8, [rsp+120h+var_E0]; unsigned int *
0x1400301cb  lea     eax, [rcx-4]
0x1400301ce  mov     r9d, 0Ah; enum mbbcx_p::MbbTlvError *
0x1400301d4  lea     rcx, [rsp+120h+var_D0]; this
0x1400301d9  mov     dword ptr [rsp+120h+var_DC], eax
0x1400301dd  lea     rdx, [rsp+120h+var_DC]; unsigned __int8 **
0x1400301e2  call    ?ExtractValidateNextTlv@mbbcx_p@@YAPEAU_MBB_TLV_IE@@AEAPEAEAEAKAEAW4MbbTlvError@1@G@Z; mbbcx_p::ExtractValidateNextTlv(uchar * &,ulong &,mbbcx_p::MbbTlvError &,ushort)
0x1400301e7  test    rax, rax
0x1400301ea  jnz     short loc_14003023F
0x1400301ec  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400301f3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400301fa  jz      loc_140030555
0x140030200  mov     eax, [rsp+120h+var_E0]
0x140030204  mov     r9d, 19Fh
0x14003020a  mov     rcx, cs:WPP_GLOBAL_Control
0x140030211  lea     rsi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140030218  mov     dword ptr [rsp+120h+var_F0], eax
0x14003021c  mov     r8d, 3
0x140030222  mov     eax, [r14+10h]
0x140030226  mov     dl, 2
0x140030228  mov     [rsp+120h+var_F8], eax
0x14003022c  mov     rcx, [rcx+40h]
0x140030230  mov     [rsp+120h+var_100], rsi
0x140030235  call    WPP_RECORDER_SF_DD
0x14003023a  jmp     loc_140030555
0x14003023f  xor     r15d, r15d
0x140030242  lea     rsi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140030249  xor     r13d, r13d
0x14003024c  mov     dword ptr [rsp+120h+var_DC+4], r15d
0x140030251  mov     [rbp+4Fh+var_C8], r13
0x140030255  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003025c  test    r12d, r12d
0x14003025f  jnz     loc_14003034C
0x140030265  cmp     dword ptr [rsp+120h+var_DC], r13d
0x14003026a  jz      loc_14003034C
0x140030270  xor     r9d, r9d; enum mbbcx_p::MbbTlvError *
0x140030273  lea     r8, [rsp+120h+var_E0]; unsigned int *
0x140030278  lea     rdx, [rsp+120h+var_DC]; unsigned __int8 **
0x14003027d  lea     rcx, [rsp+120h+var_D0]; this
0x140030282  call    ?ExtractValidateNextTlv@mbbcx_p@@YAPEAU_MBB_TLV_IE@@AEAPEAEAEAKAEAW4MbbTlvError@1@G@Z; mbbcx_p::ExtractValidateNextTlv(uchar * &,ulong &,mbbcx_p::MbbTlvError &,ushort)
0x140030287  mov     ecx, dword ptr [rsp+120h+var_DC]
0x14003028b  test    rax, rax
0x14003028e  jz      short loc_14003029E
0x140030290  mov     edx, 6
0x140030295  cmp     dx, [rax]
0x140030298  jz      short loc_1400302C0
0x14003029a  test    ecx, ecx
0x14003029c  jnz     short loc_140030270
0x14003029e  test    ecx, ecx
0x1400302a0  jz      short loc_140030318
0x1400302a2  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400302a9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400302b0  jz      loc_140030555
0x1400302b6  test    rax, rax
0x1400302b9  jz      short loc_1400302FF
0x1400302bb  movzx   ecx, word ptr [rax]
0x1400302be  jmp     short loc_140030301
0x1400302c0  lea     r8, [rbp+4Fh+var_C8]
0x1400302c4  mov     rcx, rax
0x1400302c7  lea     rdx, [rsp+120h+var_DC+4]
0x1400302cc  call    ?CalculateSNssaiCntFromTlvPrecfgDfltCfgNssai@mbbcx_p@@YA?AW4MbbTlvError@1@QEAU_MBB_TLV_IE@@AEAKAEAPEAU3@@Z; mbbcx_p::CalculateSNssaiCntFromTlvPrecfgDfltCfgNssai(_MBB_TLV_IE * const,ulong &,_MBB_TLV_IE * &)
0x1400302d1  test    eax, eax
0x1400302d3  jz      short loc_1400302F4
0x1400302d5  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400302dc  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400302e3  jz      loc_140030555
0x1400302e9  mov     r9d, 1A0h
0x1400302ef  jmp     loc_14003020A
0x1400302f4  mov     r15d, dword ptr [rsp+120h+var_DC+4]
0x1400302f9  mov     r13, [rbp+4Fh+var_C8]
0x1400302fd  jmp     short loc_14003034C
0x1400302ff  xor     ecx, ecx
0x140030301  mov     eax, [rsp+120h+var_E0]
0x140030305  mov     r9d, 1A1h
0x14003030b  mov     dword ptr [rsp+120h+var_E8], ecx
0x14003030f  mov     dword ptr [rsp+120h+var_F0], eax
0x140030313  jmp     loc_140030529
0x140030318  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003031f  jz      short loc_14003034C
0x140030321  mov     rcx, cs:WPP_GLOBAL_Control
0x140030328  mov     r9d, 1A2h
0x14003032e  mov     eax, [r14+10h]
0x140030332  mov     r8d, 3
0x140030338  mov     [rsp+120h+var_F8], eax
0x14003033c  mov     dl, 4
0x14003033e  mov     [rsp+120h+var_100], rsi
0x140030343  mov     rcx, [rcx+40h]
0x140030347  call    WPP_RECORDER_SF_d
0x14003034c  mov     eax, r15d
0x14003034f  mov     ecx, 40h ; '@'
0x140030354  shl     eax, 4
0x140030357  mov     r8d, 6458424Dh
0x14003035d  add     eax, 0ECh
0x140030362  mov     edx, eax
0x140030364  mov     dword ptr [rsp+120h+var_DC+4], eax
0x140030368  call    cs:__imp_ExAllocatePool2
0x14003036f  nop     dword ptr [rax+rax+00h]
0x140030374  mov     r12, rax
0x140030377  test    rax, rax
0x14003037a  jnz     short loc_140030386
0x14003037c  mov     eax, 0C000009Ah
0x140030381  jmp     loc_14003055C
0x140030386  mov     ecx, [rsp+120h+var_D4]
0x14003038a  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14003038f  lea     rcx, [r12+8]; void *
0x140030394  mov     [rsp+120h+var_E0], eax
0x140030398  xor     edx, edx; Val
0x14003039a  mov     dword ptr [r12], 0EC0280h
0x1400303a2  mov     r8d, 0E4h; Size
0x1400303a8  mov     [r12+4], eax
0x1400303ad  call    memset
0x1400303b2  mov     rdx, [rbp+4Fh+var_C0]
0x1400303b6  mov     eax, 40h ; '@'
0x1400303bb  mov     ecx, [rdx]
0x1400303bd  mov     [r12+0Ch], ecx
0x1400303c2  mov     ecx, [rdx+8]
0x1400303c5  shr     ecx, 1
0x1400303c7  cmp     ecx, 41h ; 'A'
0x1400303ca  cmovnb  ecx, eax
0x1400303cd  add     rdx, 0Ch; Src
0x1400303d1  mov     r8d, ecx
0x1400303d4  lea     rcx, [r12+60h]; void *
0x1400303d9  add     r8, r8; Size
0x1400303dc  call    memmove
0x1400303e1  cmp     [rsp+120h+var_D4], 0
0x1400303e6  mov     dword ptr [r12+0E4h], 18h
0x1400303f2  jnz     short loc_140030414
0x1400303f4  test    r15d, r15d
0x1400303f7  jz      short loc_140030414
0x1400303f9  lea     rdx, [r12+0ECh]; struct _MBB_TLV_IE *
0x140030401  mov     [r12+0E8h], r15d
0x140030409  mov     r8d, r15d; struct _WWAN_SINGLE_NSSAI *
0x14003040c  mov     rcx, r13; this
0x14003040f  call    ?ParseTlvNSSAI@mbbcx_p@@YAXQEAU_MBB_TLV_IE@@PEAU_WWAN_SINGLE_NSSAI@@K@Z; mbbcx_p::ParseTlvNSSAI(_MBB_TLV_IE * const,_WWAN_SINGLE_NSSAI *,ulong)
0x140030414  mov     rax, [r14+30h]
0x140030418  xorps   xmm0, xmm0
0x14003041b  mov     dword ptr [rbp+4Fh+var_B0.Header.Type], 700198h
0x140030422  mov     rcx, [rax]
0x140030425  mov     rax, [rcx+478h]
0x14003042c  mov     rcx, [rax]
0x14003042f  mov     rax, [rcx+10h]
0x140030433  mov     [rbp+4Fh+var_B0.SourceHandle], rax
0x140030437  mov     rax, [r14+1B8h]
0x14003043e  mov     [rbp+4Fh+var_B0.DestinationHandle], rax
0x140030442  mov     rax, [r14+1B0h]
0x140030449  mov     [rbp+4Fh+var_B0.RequestId], rax
0x14003044d  mov     eax, dword ptr [rsp+120h+var_DC+4]
0x140030451  mov     [rbp+4Fh+var_B0.StatusBufferSize], eax
0x140030454  mov     [rbp+4Fh+var_B0.PortNumber], 0
0x14003045b  mov     qword ptr [rbp+4Fh+var_B0.StatusCode], 40041040h
0x140030463  movups  xmmword ptr [rbp+4Fh+var_B0.Guid.Data1], xmm0
0x140030467  mov     [rbp+4Fh+var_B0.StatusBuffer], r12
0x14003046b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140030472  jz      short loc_1400304A7
0x140030474  mov     eax, [rsp+120h+var_E0]
0x140030478  mov     r9d, 1A3h
0x14003047e  mov     rcx, cs:WPP_GLOBAL_Control
0x140030485  mov     r8d, 3
0x14003048b  mov     dword ptr [rsp+120h+var_F0], eax
0x14003048f  mov     dl, 4
0x140030491  mov     eax, [r14+10h]
0x140030495  mov     [rsp+120h+var_F8], eax
0x140030499  mov     rcx, [rcx+40h]
0x14003049d  mov     [rsp+120h+var_100], rsi
0x1400304a2  call    WPP_RECORDER_SF_DD
0x1400304a7  mov     rdx, [r14+68h]
0x1400304ab  test    rdx, rdx
0x1400304ae  jz      short loc_1400304D7
0x1400304b0  mov     rax, cs:WdfFunctions_01031
0x1400304b7  mov     r8, cs:off_14005DF38
0x1400304be  mov     rcx, cs:WdfDriverGlobals
0x1400304c5  mov     rax, [rax+650h]
0x1400304cc  call    _guard_dispatch_icall
0x1400304d1  add     rax, 18h
0x1400304d5  jmp     short loc_1400304E8
0x1400304d7  mov     rax, [r14+30h]
0x1400304db  mov     rcx, [rax]
0x1400304de  mov     rax, [rcx+478h]
0x1400304e5  mov     rax, [rax]
0x1400304e8  lea     rdx, [rbp+4Fh+var_B0]; struct _NDIS_STATUS_INDICATION *
0x1400304ec  mov     rcx, rax; struct _MINIPORT_INTERFACE_CONTEXT *
0x1400304ef  call    ?MbbUtilNdisMiniportIndicateStatusEx@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_NDIS_STATUS_INDICATION@@@Z; MbbUtilNdisMiniportIndicateStatusEx(_MINIPORT_INTERFACE_CONTEXT *,_NDIS_STATUS_INDICATION *)
0x1400304f4  xor     edx, edx; Tag
0x1400304f6  mov     rcx, r12; P
0x1400304f9  call    cs:__imp_ExFreePoolWithTag
0x140030500  nop     dword ptr [rax+rax+00h]
0x140030505  jmp     short loc_14003055A
0x140030507  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003050e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140030515  jz      short loc_140030555
0x140030517  mov     dword ptr [rsp+120h+var_E8], 0Ch
0x14003051f  mov     r9d, 19Eh
0x140030525  mov     dword ptr [rsp+120h+var_F0], ecx
0x140030529  mov     rcx, cs:WPP_GLOBAL_Control
0x140030530  lea     rsi, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140030537  mov     eax, [r14+10h]
0x14003053b  mov     r8d, 3
0x140030541  mov     [rsp+120h+var_F8], eax
0x140030545  mov     dl, 2
0x140030547  mov     [rsp+120h+var_100], rsi
0x14003054c  mov     rcx, [rcx+40h]
0x140030550  call    WPP_RECORDER_SF_Ddd
0x140030555  mov     ebx, 0C0000001h
0x14003055a  mov     eax, ebx
0x14003055c  mov     rcx, [rbp+4Fh+var_40]
0x140030560  xor     rcx, rsp; StackCookie
0x140030563  call    __security_check_cookie
0x140030568  mov     rbx, [rsp+120h+arg_8]
0x140030570  add     rsp, 0F0h
0x140030577  pop     r15
0x140030579  pop     r14
0x14003057b  pop     r13
0x14003057d  pop     r12
0x14003057f  pop     rdi
0x140030580  pop     rsi
0x140030581  pop     rbp
0x140030582  retn
```
