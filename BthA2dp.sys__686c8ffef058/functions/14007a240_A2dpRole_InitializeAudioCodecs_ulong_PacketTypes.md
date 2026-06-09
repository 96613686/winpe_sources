# A2dpRole::InitializeAudioCodecs(ulong,PacketTypes)

- ea: `0x14007a240`
- end: `0x14007a5c9`
- name: `?InitializeAudioCodecs@A2dpRole@@QEAAJKUPacketTypes@@@Z`
- size: `905`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140079014`

## callees

- `0x140010628`
- `0x1400126ac`
- `0x14001bd20`
- `0x14001c064`
- `0x14002d940`
- `0x1400784bc`
- `0x14007868c`
- `0x14007a240`
- `0x140089fc0`
- `0x14008a774`

## string_xrefs

- `0x14007a42e`: `Failed to create inband AAC codec`
- `0x14007a53d`: `Failed to create inband SBC codec`

## pseudocode

```c
__int64 __fastcall A2dpRole::InitializeAudioCodecs(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  unsigned __int16 v3; // bx
  int v5; // ecx
  bool v6; // dl
  __int64 *v7; // rsi
  __int64 result; // rax
  A2dpAudioCodecManager *v9; // rcx
  unsigned __int8 v10; // r8
  char v11; // al
  bool v12; // bl
  int RegistryDWord; // eax
  __int64 v14; // r8
  __int64 v15; // rcx
  bool v16; // al
  bool v17; // zf
  A2dpAudioCodecManager *v18; // rcx
  int v19; // eax
  __int16 v20; // r8
  bool v21; // dl
  char v22; // al
  bool v23; // bl
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rcx
  bool v27; // al
  A2dpAudioCodecManager *v28; // rcx
  int v29; // eax
  __int16 v30; // r8
  bool v31; // dl
  char v32; // al
  bool v33; // bl
  int v34; // eax
  __int64 v35; // rcx
  _BYTE v36[4]; // [rsp+50h] [rbp-18h] BYREF
  int v37; // [rsp+54h] [rbp-14h]
  __int16 v38; // [rsp+58h] [rbp-10h]

  v3 = a3;
  v5 = (int)WPP_GLOBAL_Control;
  v6 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      51,
      (__int64)WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids,
      20,
      a1);
  }
  v7 = (__int64 *)(a1 + 80);
  LOBYTE(v5) = *(_BYTE *)(a1 + 89) == 0;
  result = A2dpAudioCodecManager::MakeAndInitialize(v5, v6, v3, (int)a1 + 80, a1);
  if ( (int)result >= 0 )
  {
    v9 = *(A2dpAudioCodecManager **)a1;
    v36[0] = 0;
    v38 = 0;
    v37 = 0;
    result = A2dpAudioCodecManager::AddInbandCodec(v9, (const struct CodecId *)v36);
    if ( (int)result >= 0 )
    {
      A2dpRole::AddStreamEndpoint((A2dpRole *)a1, *(_BYTE *)(a1 + 89) != 0 ? 36 : 52, v10, *(_BYTE *)(a1 + 89) != 0);
      v11 = *(_BYTE *)(a1 + 89);
      v12 = v11 == 0;
      *(_BYTE *)(a1 + 16) = v11 == 0;
      if ( !v11 )
      {
        RegistryDWord = QueryRegistryDWord(&DriverParametersRegistryPathName, L"BluetoothAptxEnable", 1u);
        v14 = *(_QWORD *)(a1 + 72);
        v15 = *v7;
        *(_BYTE *)(a1 + 16) = v12 && RegistryDWord != 0;
        v16 = (BthQueryDeviceCompatFlags(v15, 7, *(_QWORD *)(v14 + 376)) & 1) == 0;
        v17 = (v16 & *(_BYTE *)(a1 + 16)) == 0;
        *(_BYTE *)(a1 + 16) &= v16;
        if ( !v17 )
        {
          v18 = *(A2dpAudioCodecManager **)a1;
          v36[0] = -1;
          v37 = 79;
          v38 = 1;
          v19 = A2dpAudioCodecManager::AddInbandCodec(v18, (const struct CodecId *)v36);
          if ( v19 >= 0 )
          {
            A2dpRole::AddStreamEndpoint((A2dpRole *)a1, 0x36u, v20, 0);
          }
          else
          {
            v21 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
            if ( v21 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_dq(
                WPP_GLOBAL_Control->AttachedDevice,
                v21,
                v20,
                WPP_GLOBAL_Control->DeviceExtension,
                2,
                5,
                52,
                (__int64)WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids,
                v19,
                a1);
            }
            MicrosoftTelemetryAssertTriggeredMsgKM("Failed to create inband AAC codec");
          }
        }
      }
      v22 = *(_BYTE *)(a1 + 89);
      v23 = v22 == 0;
      *(_BYTE *)(a1 + 17) = v22 == 0;
      if ( !v22 )
      {
        v24 = QueryRegistryDWord(&DriverParametersRegistryPathName, L"BluetoothAacEnable", 1u);
        v25 = *(_QWORD *)(a1 + 72);
        v26 = *v7;
        *(_BYTE *)(a1 + 17) = v23 && v24 != 0;
        v27 = (BthQueryDeviceCompatFlags(v26, 7, *(_QWORD *)(v25 + 376)) & 2) == 0;
        v17 = (v27 & *(_BYTE *)(a1 + 17)) == 0;
        *(_BYTE *)(a1 + 17) &= v27;
        if ( !v17 )
        {
          v28 = *(A2dpAudioCodecManager **)a1;
          v36[0] = 2;
          v38 = 0;
          v37 = 0;
          v29 = A2dpAudioCodecManager::AddInbandCodec(v28, (const struct CodecId *)v36);
          if ( v29 >= 0 )
          {
            A2dpRole::AddStreamEndpoint((A2dpRole *)a1, 0x37u, v30, 0);
          }
          else
          {
            v31 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
            if ( v31 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_dq(
                WPP_GLOBAL_Control->AttachedDevice,
                v31,
                v30,
                WPP_GLOBAL_Control->DeviceExtension,
                2,
                5,
                53,
                (__int64)WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids,
                v29,
                a1);
            }
            MicrosoftTelemetryAssertTriggeredMsgKM("Failed to create inband SBC codec");
          }
        }
      }
      Feature_A2dpAptxAdaptive__private_IsEnabledPreCheck();
      v32 = *(_BYTE *)(a1 + 89);
      v33 = v32 == 0;
      *(_BYTE *)(a1 + 18) = v32 == 0;
      if ( !v32 )
      {
        v34 = QueryRegistryDWord(&DriverParametersRegistryPathName, L"BluetoothAptXAdaptiveEnable", 1u);
        v35 = *v7;
        *(_BYTE *)(a1 + 18) = v34 != 0 && v33;
        *(_BYTE *)(a1 + 18) &= (BthQueryDeviceCompatFlags(v35, 7, *(_QWORD *)(*(_QWORD *)(a1 + 72) + 376LL)) & 4) == 0;
      }
      A2dpRole::ResetCodecs((A2dpRole *)a1);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14007a240  push    rbp
0x14007a242  push    rbx
0x14007a243  push    rsi
0x14007a244  push    rdi
0x14007a245  push    r13
0x14007a247  push    r15
0x14007a249  mov     rbp, rsp
0x14007a24c  sub     rsp, 68h
0x14007a250  movzx   ebx, r8w
0x14007a254  mov     rdi, rcx
0x14007a257  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a25e  lea     r13, WPP_GLOBAL_Control
0x14007a265  mov     r15d, 1
0x14007a26b  cmp     rcx, r13
0x14007a26e  jz      short loc_14007A282
0x14007a270  mov     eax, [rcx+2Ch]
0x14007a273  test    al, 10h
0x14007a275  jz      short loc_14007A282
0x14007a277  cmp     byte ptr [rcx+29h], 4
0x14007a27b  jb      short loc_14007A282
0x14007a27d  mov     dl, r15b
0x14007a280  jmp     short loc_14007A284
0x14007a282  xor     dl, dl
0x14007a284  lea     rax, WPP_RECORDER_INITIALIZED
0x14007a28b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007a292  lea     r9, WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids
0x14007a299  setnz   r8b
0x14007a29d  test    dl, dl
0x14007a29f  jnz     short loc_14007A2A6
0x14007a2a1  test    r8b, r8b
0x14007a2a4  jz      short loc_14007A2D9
0x14007a2a6  mov     [rsp+68h+var_20], rdi
0x14007a2ab  mov     [rsp+68h+var_28], 13F114h
0x14007a2b3  mov     [rsp+68h+var_30], r9
0x14007a2b8  mov     r9, [rcx+40h]
0x14007a2bc  mov     rcx, [rcx+18h]
0x14007a2c0  mov     [rsp+68h+var_38], 33h ; '3'
0x14007a2c7  mov     [rsp+68h+var_40], 5
0x14007a2cf  mov     byte ptr [rsp+68h+var_48], 4
0x14007a2d4  call    WPP_RECORDER_AND_TRACE_SF_dq
0x14007a2d9  cmp     byte ptr [rdi+59h], 0
0x14007a2dd  lea     rsi, [rdi+50h]
0x14007a2e1  mov     r9, rsi
0x14007a2e4  mov     [rsp+68h+var_48], rdi
0x14007a2e9  setz    cl
0x14007a2ec  movzx   r8d, bx
0x14007a2f0  call    ?MakeAndInitialize@A2dpAudioCodecManager@@SAJ_NIUPacketTypes@@AEB_KAEAV?$shared_ptr@VA2dpAudioCodecManager@@@utl@@@Z; A2dpAudioCodecManager::MakeAndInitialize(bool,uint,PacketTypes,unsigned __int64 const &,utl::shared_ptr<A2dpAudioCodecManager> &)
0x14007a2f5  test    eax, eax
0x14007a2f7  js      loc_14007A5BB
0x14007a2fd  mov     rcx, [rdi]; this
0x14007a300  lea     rdx, [rbp+var_18]; struct CodecId *
0x14007a304  xor     eax, eax
0x14007a306  mov     [rbp+var_18], 0
0x14007a30a  mov     [rbp+var_10], ax
0x14007a30e  mov     [rbp+var_14], 0
0x14007a315  call    ?AddInbandCodec@A2dpAudioCodecManager@@QEAAJAEBVCodecId@@@Z; A2dpAudioCodecManager::AddInbandCodec(CodecId const &)
0x14007a31a  test    eax, eax
0x14007a31c  js      loc_14007A5BB
0x14007a322  mov     al, [rdi+59h]
0x14007a325  mov     rcx, rdi; this
0x14007a328  test    al, al
0x14007a32a  setnz   r9b; unsigned __int8
0x14007a32e  neg     al
0x14007a330  sbb     dl, dl
0x14007a332  and     dl, 0F0h
0x14007a335  add     dl, 34h ; '4'; unsigned __int8
0x14007a338  call    ?AddStreamEndpoint@A2dpRole@@AEAAJEEE@Z; A2dpRole::AddStreamEndpoint(uchar,uchar,uchar)
0x14007a33d  mov     al, [rdi+59h]
0x14007a340  test    al, al
0x14007a342  setz    bl
0x14007a345  mov     [rdi+10h], bl
0x14007a348  test    al, al
0x14007a34a  jnz     loc_14007A449
0x14007a350  mov     r8d, r15d
0x14007a353  lea     rdx, aBluetoothaptxe; "BluetoothAptxEnable"
0x14007a35a  lea     rcx, DriverParametersRegistryPathName
0x14007a361  call    QueryRegistryDWord
0x14007a366  mov     r8, [rdi+48h]
0x14007a36a  test    eax, eax
0x14007a36c  mov     rcx, [rsi]
0x14007a36f  mov     edx, 7
0x14007a374  setnz   al
0x14007a377  and     al, bl
0x14007a379  mov     [rdi+10h], al
0x14007a37c  mov     r8, [r8+178h]
0x14007a383  call    BthQueryDeviceCompatFlags
0x14007a388  not     al
0x14007a38a  and     al, r15b
0x14007a38d  and     [rdi+10h], al
0x14007a390  jz      loc_14007A449
0x14007a396  mov     rcx, [rdi]; this
0x14007a399  lea     rdx, [rbp+var_18]; struct CodecId *
0x14007a39d  mov     [rbp+var_18], 0FFh
0x14007a3a1  mov     [rbp+var_14], 4Fh ; 'O'
0x14007a3a8  mov     [rbp+var_10], r15w
0x14007a3ad  call    ?AddInbandCodec@A2dpAudioCodecManager@@QEAAJAEBVCodecId@@@Z; A2dpAudioCodecManager::AddInbandCodec(CodecId const &)
0x14007a3b2  test    eax, eax
0x14007a3b4  jns     loc_14007A43C
0x14007a3ba  mov     r10, cs:WPP_GLOBAL_Control
0x14007a3c1  cmp     r10, r13
0x14007a3c4  jz      short loc_14007A3DB
0x14007a3c6  mov     ecx, [r10+2Ch]
0x14007a3ca  test    cl, 10h
0x14007a3cd  jz      short loc_14007A3DB
0x14007a3cf  cmp     byte ptr [r10+29h], 2
0x14007a3d4  jb      short loc_14007A3DB
0x14007a3d6  mov     dl, r15b
0x14007a3d9  jmp     short loc_14007A3DD
0x14007a3db  xor     dl, dl
0x14007a3dd  lea     rcx, WPP_RECORDER_INITIALIZED
0x14007a3e4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14007a3eb  setnz   r8b
0x14007a3ef  test    dl, dl
0x14007a3f1  jnz     short loc_14007A3F8
0x14007a3f3  test    r8b, r8b
0x14007a3f6  jz      short loc_14007A42E
0x14007a3f8  mov     r9, [r10+40h]
0x14007a3fc  mov     rcx, [r10+18h]
0x14007a400  mov     [rsp+68h+var_20], rdi
0x14007a405  mov     [rsp+68h+var_28], eax
0x14007a409  lea     rax, WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids
0x14007a410  mov     [rsp+68h+var_30], rax
0x14007a415  mov     [rsp+68h+var_38], 34h ; '4'
0x14007a41c  mov     [rsp+68h+var_40], 5
0x14007a424  mov     byte ptr [rsp+68h+var_48], 2
0x14007a429  call    WPP_RECORDER_AND_TRACE_SF_dq
0x14007a42e  lea     rcx, aFailedToCreate_0; "Failed to create inband AAC codec"
0x14007a435  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14007a43a  jmp     short loc_14007A449
0x14007a43c  xor     r9d, r9d; unsigned __int8
0x14007a43f  mov     dl, 36h ; '6'; unsigned __int8
0x14007a441  mov     rcx, rdi; this
0x14007a444  call    ?AddStreamEndpoint@A2dpRole@@AEAAJEEE@Z; A2dpRole::AddStreamEndpoint(uchar,uchar,uchar)
0x14007a449  mov     al, [rdi+59h]
0x14007a44c  test    al, al
0x14007a44e  setz    bl
0x14007a451  mov     [rdi+11h], bl
0x14007a454  test    al, al
0x14007a456  jnz     loc_14007A558
0x14007a45c  mov     r8d, r15d
0x14007a45f  lea     rdx, aBluetoothaacen; "BluetoothAacEnable"
0x14007a466  lea     rcx, DriverParametersRegistryPathName
0x14007a46d  call    QueryRegistryDWord
0x14007a472  mov     r8, [rdi+48h]
0x14007a476  test    eax, eax
0x14007a478  mov     rcx, [rsi]
0x14007a47b  mov     edx, 7
0x14007a480  setnz   al
0x14007a483  and     al, bl
0x14007a485  mov     [rdi+11h], al
0x14007a488  mov     r8, [r8+178h]
0x14007a48f  call    BthQueryDeviceCompatFlags
0x14007a494  shr     al, 1
0x14007a496  not     al
0x14007a498  and     al, r15b
0x14007a49b  and     [rdi+11h], al
0x14007a49e  jz      loc_14007A558
0x14007a4a4  mov     rcx, [rdi]; this
0x14007a4a7  lea     rdx, [rbp+var_18]; struct CodecId *
0x14007a4ab  xor     eax, eax
0x14007a4ad  mov     [rbp+var_18], 2
0x14007a4b1  mov     [rbp+var_10], ax
0x14007a4b5  mov     [rbp+var_14], 0
0x14007a4bc  call    ?AddInbandCodec@A2dpAudioCodecManager@@QEAAJAEBVCodecId@@@Z; A2dpAudioCodecManager::AddInbandCodec(CodecId const &)
0x14007a4c1  test    eax, eax
0x14007a4c3  jns     loc_14007A54B
0x14007a4c9  mov     r10, cs:WPP_GLOBAL_Control
0x14007a4d0  cmp     r10, r13
0x14007a4d3  jz      short loc_14007A4EA
0x14007a4d5  mov     ecx, [r10+2Ch]
0x14007a4d9  test    cl, 10h
0x14007a4dc  jz      short loc_14007A4EA
0x14007a4de  cmp     byte ptr [r10+29h], 2
0x14007a4e3  jb      short loc_14007A4EA
0x14007a4e5  mov     dl, r15b
0x14007a4e8  jmp     short loc_14007A4EC
0x14007a4ea  xor     dl, dl
0x14007a4ec  lea     rcx, WPP_RECORDER_INITIALIZED
0x14007a4f3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14007a4fa  setnz   r8b
0x14007a4fe  test    dl, dl
0x14007a500  jnz     short loc_14007A507
0x14007a502  test    r8b, r8b
0x14007a505  jz      short loc_14007A53D
0x14007a507  mov     r9, [r10+40h]
0x14007a50b  mov     rcx, [r10+18h]
0x14007a50f  mov     [rsp+68h+var_20], rdi
0x14007a514  mov     [rsp+68h+var_28], eax
0x14007a518  lea     rax, WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids
0x14007a51f  mov     [rsp+68h+var_30], rax
0x14007a524  mov     [rsp+68h+var_38], 35h ; '5'
0x14007a52b  mov     [rsp+68h+var_40], 5
0x14007a533  mov     byte ptr [rsp+68h+var_48], 2
0x14007a538  call    WPP_RECORDER_AND_TRACE_SF_dq
0x14007a53d  lea     rcx, aFailedToCreate; "Failed to create inband SBC codec"
0x14007a544  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14007a549  jmp     short loc_14007A558
0x14007a54b  xor     r9d, r9d; unsigned __int8
0x14007a54e  mov     dl, 37h ; '7'; unsigned __int8
0x14007a550  mov     rcx, rdi; this
0x14007a553  call    ?AddStreamEndpoint@A2dpRole@@AEAAJEEE@Z; A2dpRole::AddStreamEndpoint(uchar,uchar,uchar)
0x14007a558  call    Feature_A2dpAptxAdaptive__private_IsEnabledPreCheck
0x14007a55d  mov     al, [rdi+59h]
0x14007a560  test    al, al
0x14007a562  setz    bl
0x14007a565  mov     [rdi+12h], bl
0x14007a568  test    al, al
0x14007a56a  jnz     short loc_14007A5B1
0x14007a56c  mov     r8d, r15d
0x14007a56f  lea     rdx, aBluetoothaptxa; "BluetoothAptXAdaptiveEnable"
0x14007a576  lea     rcx, DriverParametersRegistryPathName
0x14007a57d  call    QueryRegistryDWord
0x14007a582  mov     rcx, [rsi]
0x14007a585  neg     eax
0x14007a587  mov     edx, 7
0x14007a58c  sbb     r8b, r8b
0x14007a58f  and     r8b, bl
0x14007a592  mov     [rdi+12h], r8b
0x14007a596  mov     r8, [rdi+48h]
0x14007a59a  mov     r8, [r8+178h]
0x14007a5a1  call    BthQueryDeviceCompatFlags
0x14007a5a6  shr     al, 2
0x14007a5a9  not     al
0x14007a5ab  and     al, r15b
0x14007a5ae  and     [rdi+12h], al
0x14007a5b1  mov     rcx, rdi; this
0x14007a5b4  call    ?ResetCodecs@A2dpRole@@QEAAXXZ; A2dpRole::ResetCodecs(void)
0x14007a5b9  xor     eax, eax
0x14007a5bb  add     rsp, 68h
0x14007a5bf  pop     r15
0x14007a5c1  pop     r13
0x14007a5c3  pop     rdi
0x14007a5c4  pop     rsi
0x14007a5c5  pop     rbx
0x14007a5c6  pop     rbp
0x14007a5c7  retn
```
