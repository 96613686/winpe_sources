# CUpdateConnectionQualityJob::StartConnectionQualityUpdateOnPort(ushort,_WDI_CONNECTION_QUALITY_HINT,bool *)

- ea: `0x14007f07c`
- end: `0x14007f3b5`
- name: `?StartConnectionQualityUpdateOnPort@CUpdateConnectionQualityJob@@AEAAHGW4_WDI_CONNECTION_QUALITY_HINT@@PEA_N@Z`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007bff0`

## callees

- `0x140016d00`
- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x1400400b4`
- `0x140063a48`
- `0x14007f07c`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CUpdateConnectionQualityJob::StartConnectionQualityUpdateOnPort(
        __int64 a1,
        int a2,
        int a3,
        _BYTE *a4)
{
  int v5; // r14d
  CPropertyCache *v8; // rax
  unsigned int WdiSetConnectionQualityToIhv; // edi
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  __int64 v14; // [rsp+38h] [rbp-30h]
  __int64 v15; // [rsp+50h] [rbp-18h] BYREF
  int v16; // [rsp+58h] [rbp-10h]
  unsigned int v17; // [rsp+B0h] [rbp+48h] BYREF

  v15 = (unsigned int)v15 & 0xFFFFFFFE;
  v5 = (unsigned __int16)a2;
  LOWORD(v16) = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_WORD)a2,
      a3,
      184,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      a1,
      *(_DWORD *)(a1 + 16));
  }
  *a4 = 0;
  if ( *(_BYTE *)(a1 + 552)
    || (v8 = (CPropertyCache *)(**(__int64 (__fastcall ***)(__int64, _QWORD))(*(_QWORD *)(a1 + 536) + 8LL))(
                                 *(_QWORD *)(a1 + 536) + 8LL,
                                 (unsigned __int16)v5),
        v17 = 0,
        (WdiSetConnectionQualityToIhv = CPropertyCache::GetPropertyULong(v8, 0x33u, &v17)) != 0)
    || v17 != a3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_WORD)a2,
        a3,
        186,
        (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
        a1,
        *(_DWORD *)(a1 + 16),
        a3,
        v5);
    }
    *(_WORD *)(a1 + 760) = v5;
    LODWORD(v15) = 0;
    HIDWORD(v15) = a3;
    *(_DWORD *)(a1 + 764) = a3;
    v16 = 0;
    if ( a3 == 2 )
    {
      BYTE1(v16) = byte_140110334;
      LOBYTE(v16) = 20;
      LODWORD(v15) = 1;
    }
    WdiSetConnectionQualityToIhv = GenerateWdiSetConnectionQualityToIhv(
                                     (unsigned int)&v15,
                                     48,
                                     (unsigned int)*(_QWORD *)(a1 + 536) + 5384,
                                     (int)a1 + 744,
                                     a1 + 752);
    if ( WdiSetConnectionQualityToIhv )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return WdiSetConnectionQualityToIhv;
      LODWORD(v14) = WdiSetConnectionQualityToIhv;
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        187,
        (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
        a1,
        *(_DWORD *)(a1 + 16),
        v14);
      goto LABEL_29;
    }
    WdiSetConnectionQualityToIhv = DeviceCommand::Initialize(
                                     (DeviceCommand *)(a1 + 560),
                                     v5,
                                     32,
                                     *(_DWORD *)(a1 + 744),
                                     *(unsigned __int8 **)(a1 + 752));
    if ( WdiSetConnectionQualityToIhv )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return WdiSetConnectionQualityToIhv;
      v12 = 188;
    }
    else
    {
      WdiSetConnectionQualityToIhv = CJobBase::QueueDeviceCommand(
                                       (CJobBase *)a1,
                                       (struct DeviceCommand *)(a1 + 560),
                                       a3);
      if ( !WdiSetConnectionQualityToIhv )
      {
        *a4 = 1;
        goto LABEL_29;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return WdiSetConnectionQualityToIhv;
      v12 = 189;
    }
    LOBYTE(a2) = 2;
    LODWORD(v14) = WdiSetConnectionQualityToIhv;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      v12,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      a1,
      *(_DWORD *)(a1 + 16),
      v14);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return WdiSetConnectionQualityToIhv;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_WORD)a2,
        a3,
        185,
        (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
        a1,
        *(_DWORD *)(a1 + 16),
        a3,
        v5);
    }
  }
LABEL_29:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v14) = WdiSetConnectionQualityToIhv;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      190,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      a1,
      *(_DWORD *)(a1 + 16),
      v14);
  }
  return WdiSetConnectionQualityToIhv;
}

```

## disassembly

```asm
0x14007f07c  push    rbp
0x14007f07e  push    rbx
0x14007f07f  push    rsi
0x14007f080  push    rdi
0x14007f081  push    r12
0x14007f083  push    r13
0x14007f085  push    r14
0x14007f087  push    r15
0x14007f089  mov     rbp, rsp
0x14007f08c  sub     rsp, 68h
0x14007f090  and     dword ptr [rbp+var_18], 0FFFFFFFEh
0x14007f094  mov     r15, r9
0x14007f097  xor     r12d, r12d
0x14007f09a  movzx   r14d, dx
0x14007f09e  mov     dword ptr [rbp+var_18+4], r12d
0x14007f0a2  mov     esi, r8d
0x14007f0a5  mov     word ptr [rbp+var_10], r12w
0x14007f0aa  mov     rbx, rcx
0x14007f0ad  lea     rax, WPP_RECORDER_INITIALIZED
0x14007f0b4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007f0bb  lea     r13, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x14007f0c2  jz      short loc_14007F0FA
0x14007f0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f0cb  cmp     byte ptr [rcx+29h], 5
0x14007f0cf  jnb     short loc_14007F0D8
0x14007f0d1  cmp     [rcx+48h], r12w
0x14007f0d6  jz      short loc_14007F0FA
0x14007f0d8  mov     eax, [rbx+10h]
0x14007f0db  mov     r9d, 0B8h
0x14007f0e1  mov     rcx, [rcx+40h]
0x14007f0e5  mov     dl, 5
0x14007f0e7  mov     [rsp+68h+var_38], eax
0x14007f0eb  mov     [rsp+68h+var_40], rbx
0x14007f0f0  mov     [rsp+68h+var_48], r13
0x14007f0f5  call    WPP_RECORDER_SF_qD
0x14007f0fa  mov     [r15], r12b
0x14007f0fd  cmp     [rbx+228h], r12b
0x14007f104  jnz     loc_14007F1A0
0x14007f10a  mov     rcx, [rbx+218h]
0x14007f111  movzx   edx, r14w
0x14007f115  add     rcx, 8
0x14007f119  mov     rax, [rcx]
0x14007f11c  mov     rax, [rax]
0x14007f11f  call    _guard_dispatch_icall
0x14007f124  lea     r8, [rbp+arg_0]; unsigned int *
0x14007f128  mov     [rbp+arg_0], r12d
0x14007f12c  mov     edx, 33h ; '3'; unsigned int
0x14007f131  mov     rcx, rax; this
0x14007f134  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x14007f139  mov     edi, eax
0x14007f13b  test    eax, eax
0x14007f13d  jnz     short loc_14007F1A0
0x14007f13f  cmp     [rbp+arg_0], esi
0x14007f142  jnz     short loc_14007F1A0
0x14007f144  lea     r15, WPP_RECORDER_INITIALIZED
0x14007f14b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14007f152  jz      loc_14007F3A1
0x14007f158  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f15f  cmp     byte ptr [rcx+29h], 5
0x14007f163  jnb     short loc_14007F170
0x14007f165  cmp     [rcx+48h], r12w
0x14007f16a  jz      loc_14007F35E
0x14007f170  mov     eax, [rbx+10h]
0x14007f173  mov     r9d, 0B9h
0x14007f179  mov     rcx, [rcx+40h]
0x14007f17d  mov     dl, 5
0x14007f17f  mov     [rsp+68h+var_28], r14d
0x14007f184  mov     dword ptr [rsp+68h+var_30], esi
0x14007f188  mov     [rsp+68h+var_38], eax
0x14007f18c  mov     [rsp+68h+var_40], rbx
0x14007f191  mov     [rsp+68h+var_48], r13
0x14007f196  call    WPP_RECORDER_SF_qDdd
0x14007f19b  jmp     loc_14007F35E
0x14007f1a0  lea     rax, WPP_RECORDER_INITIALIZED
0x14007f1a7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007f1ae  jz      short loc_14007F1EF
0x14007f1b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f1b7  cmp     byte ptr [rcx+29h], 5
0x14007f1bb  jnb     short loc_14007F1C4
0x14007f1bd  cmp     [rcx+48h], r12w
0x14007f1c2  jz      short loc_14007F1EF
0x14007f1c4  mov     eax, [rbx+10h]
0x14007f1c7  mov     r9d, 0BAh
0x14007f1cd  mov     rcx, [rcx+40h]
0x14007f1d1  mov     dl, 5
0x14007f1d3  mov     [rsp+68h+var_28], r14d
0x14007f1d8  mov     dword ptr [rsp+68h+var_30], esi
0x14007f1dc  mov     [rsp+68h+var_38], eax
0x14007f1e0  mov     [rsp+68h+var_40], rbx
0x14007f1e5  mov     [rsp+68h+var_48], r13
0x14007f1ea  call    WPP_RECORDER_SF_qDdd
0x14007f1ef  xor     eax, eax
0x14007f1f1  mov     [rbx+2F8h], r14w
0x14007f1f9  mov     [rbp+var_18], rax
0x14007f1fd  mov     dword ptr [rbp+var_18+4], esi
0x14007f200  mov     [rbx+2FCh], esi
0x14007f206  mov     [rbp+var_10], eax
0x14007f209  cmp     esi, 2
0x14007f20c  jnz     short loc_14007F222
0x14007f20e  mov     al, cs:byte_140110334
0x14007f214  mov     byte ptr [rbp+var_10+1], al
0x14007f217  mov     byte ptr [rbp+var_10], 14h
0x14007f21b  mov     dword ptr [rbp+var_18], 1
0x14007f222  mov     r8, [rbx+218h]
0x14007f229  lea     r13, [rbx+2E8h]
0x14007f230  lea     r12, [rbx+2F0h]
0x14007f237  add     r8, 1508h
0x14007f23e  mov     r9, r13
0x14007f241  mov     [rsp+68h+var_48], r12
0x14007f246  mov     edx, 30h ; '0'
0x14007f24b  lea     rcx, [rbp+var_18]
0x14007f24f  call    GenerateWdiSetConnectionQualityToIhv
0x14007f254  mov     edi, eax
0x14007f256  test    eax, eax
0x14007f258  jz      short loc_14007F2AA
0x14007f25a  lea     rax, WPP_RECORDER_INITIALIZED
0x14007f261  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007f268  jz      loc_14007F3A1
0x14007f26e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f275  lea     r13, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x14007f27c  mov     eax, [rbx+10h]
0x14007f27f  mov     r9d, 0BBh
0x14007f285  mov     dword ptr [rsp+68h+var_30], edi
0x14007f289  mov     dl, 2
0x14007f28b  mov     [rsp+68h+var_38], eax
0x14007f28f  mov     rcx, [rcx+40h]
0x14007f293  mov     [rsp+68h+var_40], rbx
0x14007f298  mov     [rsp+68h+var_48], r13
0x14007f29d  call    WPP_RECORDER_SF_qDD
0x14007f2a2  xor     r12d, r12d
0x14007f2a5  jmp     loc_14007F357
0x14007f2aa  mov     rax, [r12]
0x14007f2ae  lea     rsi, [rbx+230h]
0x14007f2b5  mov     r9d, [r13+0]; unsigned int
0x14007f2b9  mov     rcx, rsi; this
0x14007f2bc  mov     r8d, 20h ; ' '; unsigned int
0x14007f2c2  mov     [rsp+68h+var_48], rax; unsigned __int8 *
0x14007f2c7  movzx   edx, r14w; unsigned __int16
0x14007f2cb  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x14007f2d0  xor     r12d, r12d
0x14007f2d3  mov     edi, eax
0x14007f2d5  test    eax, eax
0x14007f2d7  jz      short loc_14007F323
0x14007f2d9  lea     rax, WPP_RECORDER_INITIALIZED
0x14007f2e0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007f2e7  jz      loc_14007F3A1
0x14007f2ed  mov     r9d, 0BCh
0x14007f2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f2fa  lea     r13, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x14007f301  mov     eax, [rbx+10h]
0x14007f304  mov     dl, 2
0x14007f306  mov     dword ptr [rsp+68h+var_30], edi
0x14007f30a  mov     [rsp+68h+var_38], eax
0x14007f30e  mov     rcx, [rcx+40h]
0x14007f312  mov     [rsp+68h+var_40], rbx
0x14007f317  mov     [rsp+68h+var_48], r13
0x14007f31c  call    WPP_RECORDER_SF_qDD
0x14007f321  jmp     short loc_14007F357
0x14007f323  mov     rdx, rsi; struct DeviceCommand *
0x14007f326  mov     rcx, rbx; this
0x14007f329  call    ?QueueDeviceCommand@CJobBase@@IEAAHPEAVDeviceCommand@@@Z; CJobBase::QueueDeviceCommand(DeviceCommand *)
0x14007f32e  mov     edi, eax
0x14007f330  test    eax, eax
0x14007f332  jz      short loc_14007F34C
0x14007f334  lea     rax, WPP_RECORDER_INITIALIZED
0x14007f33b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007f342  jz      short loc_14007F3A1
0x14007f344  mov     r9d, 0BDh
0x14007f34a  jmp     short loc_14007F2F3
0x14007f34c  mov     byte ptr [r15], 1
0x14007f350  lea     r13, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x14007f357  lea     r15, WPP_RECORDER_INITIALIZED
0x14007f35e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14007f365  jz      short loc_14007F3A1
0x14007f367  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f36e  cmp     byte ptr [rcx+29h], 5
0x14007f372  jnb     short loc_14007F37B
0x14007f374  cmp     [rcx+48h], r12w
0x14007f379  jz      short loc_14007F3A1
0x14007f37b  mov     eax, [rbx+10h]
0x14007f37e  mov     r9d, 0BEh
0x14007f384  mov     rcx, [rcx+40h]
0x14007f388  mov     dl, 5
0x14007f38a  mov     dword ptr [rsp+68h+var_30], edi
0x14007f38e  mov     [rsp+68h+var_38], eax
0x14007f392  mov     [rsp+68h+var_40], rbx
0x14007f397  mov     [rsp+68h+var_48], r13
0x14007f39c  call    WPP_RECORDER_SF_qDD
0x14007f3a1  mov     eax, edi
0x14007f3a3  add     rsp, 68h
0x14007f3a7  pop     r15
0x14007f3a9  pop     r14
0x14007f3ab  pop     r13
0x14007f3ad  pop     r12
0x14007f3af  pop     rdi
0x14007f3b0  pop     rsi
0x14007f3b1  pop     rbx
0x14007f3b2  pop     rbp
0x14007f3b3  retn
```
