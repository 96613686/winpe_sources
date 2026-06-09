# GetEnabledRemoteService(WDFDEVICE__ *)

- ea: `0x1400281d0`
- end: `0x1400285cd`
- name: `?GetEnabledRemoteService@@YA?AU_GUID@@PEAUWDFDEVICE__@@@Z`
- size: `1021`
- prototype: `struct _GUID *__fastcall(struct _GUID *__return_ptr __struct_ptr retstr, struct WDFDEVICE__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x140028008`

## callees

- `0x1400044dc`
- `0x14000458c`
- `0x14001ae00`
- `0x1400281d0`

## import_xrefs

- `btampm!BtaMpmGetRemoteDeviceProfileVersionAndAttribute` at `0x140028312`
- `btampm!BtaMpmGetRemoteDeviceProfileVersionAndAttribute` at `0x140028312`

## pseudocode

```c
struct _GUID *__fastcall GetEnabledRemoteService(struct _GUID *__return_ptr retstr, struct WDFDEVICE__ *a2)
{
  char v3; // si
  __int64 v4; // r14
  char v5; // r13
  char v6; // r12
  __int64 v7; // rax
  __int64 v8; // rbx
  char v9; // di
  GUID *v10; // r15
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int16 v15; // cx
  __int64 v16; // rax
  int v17; // edx
  int v18; // r8d
  int RemoteDeviceProfileVersionAndAttribute; // r9d
  bool v20; // r10
  __int16 v21; // ax
  bool v22; // r11
  __int16 v23; // ax
  GUID v24; // xmm0
  __int64 *v25; // r8
  int v27; // [rsp+20h] [rbp-88h]
  int v28; // [rsp+38h] [rbp-70h]
  __int16 v29; // [rsp+50h] [rbp-58h] BYREF
  __int16 v30; // [rsp+54h] [rbp-54h] BYREF
  bool v33; // [rsp+C0h] [rbp+18h]
  bool v34; // [rsp+C8h] [rbp+20h]

  *retstr = GUID_00000000_0000_0000_0000_000000000000;
  v3 = 0;
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a2,
         off_1400220B0);
  v33 = 0;
  v34 = 0;
  v5 = 0;
  v6 = 0;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *))(WdfFunctions_01015 + 312))(
         WdfDriverGlobals,
         a2);
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v7,
         off_140022050);
  v9 = 1;
  v10 = (GUID *)(v8 + 48);
  v11 = *(_QWORD *)HandsfreeServiceClass_UUID.Data4;
  v12 = *(_QWORD *)&HandsfreeServiceClass_UUID.Data1;
  v13 = *(_QWORD *)HandsfreeAudioGatewayServiceClass_UUID.Data4;
  v14 = *(_QWORD *)&HandsfreeAudioGatewayServiceClass_UUID.Data1;
  do
  {
    v15 = 0;
    v29 = 0;
    if ( !*(_BYTE *)(v8 + 20) )
    {
      v20 = 0;
      goto LABEL_26;
    }
    v30 = 0;
    v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64, __int64))(WdfFunctions_01015
                                                                                                 + 264))(
            WdfDriverGlobals,
            a2,
            v13,
            v14);
    LOWORD(v27) = 785;
    RemoteDeviceProfileVersionAndAttribute = BtaMpmGetRemoteDeviceProfileVersionAndAttribute(
                                               v16,
                                               v4 + 432,
                                               v8,
                                               &HandsfreeServiceClass_UUID);
    if ( RemoteDeviceProfileVersionAndAttribute < 0 )
    {
      if ( RemoteDeviceProfileVersionAndAttribute == -1073740532 )
      {
        LOBYTE(v17) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        if ( (_BYTE)v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF__guid_(
            WPP_GLOBAL_Control->AttachedDevice,
            v17,
            v18,
            WPP_GLOBAL_Control->DeviceExtension,
            3,
            4,
            10,
            (__int64)WPP_9739fd3d85a33a980818697074cd9c28_Traceguids,
            v8);
        }
        v3 = 1;
        v15 = 0;
        goto LABEL_24;
      }
      LOBYTE(v17) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF__guid_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v17,
          v18,
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          (unsigned int)&v30,
          (unsigned int)&v29,
          v28,
          v8,
          RemoteDeviceProfileVersionAndAttribute);
      }
    }
    else
    {
      v3 = 1;
    }
    v15 = v29;
LABEL_24:
    v12 = *(_QWORD *)&HandsfreeServiceClass_UUID.Data1;
    v13 = *(_QWORD *)HandsfreeAudioGatewayServiceClass_UUID.Data4;
    v14 = *(_QWORD *)&HandsfreeAudioGatewayServiceClass_UUID.Data1;
    v11 = *(_QWORD *)HandsfreeServiceClass_UUID.Data4;
    v20 = *(_DWORD *)(v8 + 16) == ((*(_DWORD *)(v4 + 440) >> 8) & 0x1F);
LABEL_26:
    if ( v12 == *(_QWORD *)v8 && v11 == *(_QWORD *)(v8 + 8) )
    {
      v33 = v20;
      v6 = v3;
      if ( v3 )
        v21 = v15;
      else
        v21 = 0;
      *(_WORD *)(v4 + 698) = v21;
      v11 = *(_QWORD *)HandsfreeServiceClass_UUID.Data4;
      v12 = *(_QWORD *)&HandsfreeServiceClass_UUID.Data1;
      v13 = *(_QWORD *)HandsfreeAudioGatewayServiceClass_UUID.Data4;
      v14 = *(_QWORD *)&HandsfreeAudioGatewayServiceClass_UUID.Data1;
      goto LABEL_39;
    }
    if ( v14 != *(_QWORD *)v8 || v13 != *(_QWORD *)(v8 + 8) )
    {
      v20 = v33;
LABEL_39:
      v22 = v34;
      goto LABEL_40;
    }
    v34 = v20;
    v5 = v3;
    v22 = v20;
    if ( v3 )
      v23 = v15;
    else
      v23 = 0;
    v20 = v33;
    *(_WORD *)(v4 + 696) = v23;
    v11 = *(_QWORD *)HandsfreeServiceClass_UUID.Data4;
    v12 = *(_QWORD *)&HandsfreeServiceClass_UUID.Data1;
    v13 = *(_QWORD *)HandsfreeAudioGatewayServiceClass_UUID.Data4;
    v14 = *(_QWORD *)&HandsfreeAudioGatewayServiceClass_UUID.Data1;
LABEL_40:
    v8 += 24;
    v3 = 0;
  }
  while ( (GUID *)v8 != v10 );
  if ( !v6 )
    goto LABEL_47;
  if ( !v5 || v20 )
  {
    v24 = HandsfreeServiceClass_UUID;
    goto LABEL_48;
  }
  if ( v22 )
  {
LABEL_47:
    v24 = HandsfreeAudioGatewayServiceClass_UUID;
    goto LABEL_48;
  }
  v24 = *v10;
LABEL_48:
  *retstr = v24;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
    || (LOBYTE(v12) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
  {
    LOBYTE(v12) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
    v9 = 0;
  if ( (_BYTE)v12 || v9 )
  {
    v25 = WPP_9739fd3d85a33a980818697074cd9c28_Traceguids;
    LOBYTE(v25) = v9;
    WPP_RECORDER_AND_TRACE_SF__guid_(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      (_DWORD)v25,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      4,
      12,
      (__int64)WPP_9739fd3d85a33a980818697074cd9c28_Traceguids,
      (__int64)retstr);
  }
  return retstr;
}

```

## disassembly

```asm
0x1400281d0  mov     [rsp+arg_8], rdx
0x1400281d5  mov     [rsp+arg_0], rcx
0x1400281da  push    rbx
0x1400281db  push    rbp
0x1400281dc  push    rsi
0x1400281dd  push    rdi
0x1400281de  push    r12
0x1400281e0  push    r13
0x1400281e2  push    r14
0x1400281e4  push    r15
0x1400281e6  sub     rsp, 68h
0x1400281ea  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1400281f1  mov     rbp, rcx
0x1400281f4  mov     rbx, rdx
0x1400281f7  movdqu  xmmword ptr [rcx], xmm0
0x1400281fb  mov     rax, cs:WdfFunctions_01015
0x140028202  mov     r8, cs:off_1400220B0
0x140028209  mov     rcx, cs:WdfDriverGlobals
0x140028210  mov     rax, [rax+650h]
0x140028217  call    _guard_dispatch_icall
0x14002821c  mov     rcx, cs:WdfFunctions_01015
0x140028223  xor     esi, esi
0x140028225  mov     r14, rax
0x140028228  mov     [rsp+0A8h+arg_10], sil
0x140028230  mov     rdx, rbx
0x140028233  mov     [rsp+0A8h+arg_18], sil
0x14002823b  mov     r13b, sil
0x14002823e  mov     r12b, sil
0x140028241  mov     rax, [rcx+138h]
0x140028248  mov     rcx, cs:WdfDriverGlobals
0x14002824f  call    _guard_dispatch_icall
0x140028254  mov     rcx, cs:WdfFunctions_01015
0x14002825b  mov     rdx, rax
0x14002825e  mov     r8, cs:off_140022050
0x140028265  mov     rax, [rcx+650h]
0x14002826c  mov     rcx, cs:WdfDriverGlobals
0x140028273  call    _guard_dispatch_icall
0x140028278  mov     rbx, rax
0x14002827b  mov     dil, 1
0x14002827e  lea     r15, [rax+30h]
0x140028282  cmp     rax, r15
0x140028285  jz      loc_14002852F
0x14002828b  mov     rax, qword ptr cs:HandsfreeServiceClass_UUID.Data4
0x140028292  mov     rdx, qword ptr cs:HandsfreeServiceClass_UUID.Data1
0x140028299  mov     r8, qword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data4
0x1400282a0  mov     r9, qword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data1
0x1400282a7  mov     rbp, [rsp+0A8h+arg_8]
0x1400282af  xor     ecx, ecx
0x1400282b1  mov     [rsp+0A8h+var_58], cx
0x1400282b6  cmp     [rbx+14h], cl
0x1400282b9  jz      loc_140028444
0x1400282bf  mov     rcx, cs:WdfDriverGlobals
0x1400282c6  xor     eax, eax
0x1400282c8  mov     [rsp+0A8h+var_54], ax
0x1400282cd  mov     rdx, rbp
0x1400282d0  mov     rax, cs:WdfFunctions_01015
0x1400282d7  mov     rax, [rax+108h]
0x1400282de  call    _guard_dispatch_icall
0x1400282e3  lea     rcx, [rsp+0A8h+var_58]
0x1400282e8  mov     r8, rbx
0x1400282eb  mov     [rsp+0A8h+var_78], rcx
0x1400282f0  lea     rdx, [r14+1B0h]
0x1400282f7  lea     rcx, [rsp+0A8h+var_54]
0x1400282fc  mov     [rsp+0A8h+var_80], rcx
0x140028301  lea     r9, HandsfreeServiceClass_UUID
0x140028308  mov     rcx, rax
0x14002830b  mov     [rsp+0A8h+var_88], 311h
0x140028312  call    cs:__imp_BtaMpmGetRemoteDeviceProfileVersionAndAttribute
0x140028319  nop     dword ptr [rax+rax+00h]
0x14002831e  mov     r9d, eax
0x140028321  test    eax, eax
0x140028323  js      short loc_14002832D
0x140028325  mov     sil, dil
0x140028328  jmp     loc_14002840D
0x14002832d  cmp     r9d, 0C000050Ch
0x140028334  jnz     short loc_1400283B4
0x140028336  mov     rcx, cs:WPP_GLOBAL_Control
0x14002833d  lea     rax, WPP_GLOBAL_Control
0x140028344  cmp     rcx, rax
0x140028347  jz      short loc_14002835B
0x140028349  mov     eax, [rcx+2Ch]
0x14002834c  test    al, 8
0x14002834e  jz      short loc_14002835B
0x140028350  cmp     byte ptr [rcx+29h], 3
0x140028354  jb      short loc_14002835B
0x140028356  mov     dl, dil
0x140028359  jmp     short loc_14002835D
0x14002835b  xor     dl, dl
0x14002835d  lea     rax, WPP_RECORDER_INITIALIZED
0x140028364  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002836b  setnz   r8b
0x14002836f  test    dl, dl
0x140028371  jnz     short loc_140028378
0x140028373  test    r8b, r8b
0x140028376  jz      short loc_1400283AA
0x140028378  mov     [rsp+0A8h+var_68], rbx
0x14002837d  lea     r9, WPP_9739fd3d85a33a980818697074cd9c28_Traceguids
0x140028384  mov     [rsp+0A8h+var_70], r9
0x140028389  mov     r9, [rcx+40h]
0x14002838d  mov     rcx, [rcx+18h]
0x140028391  mov     word ptr [rsp+0A8h+var_78], 0Ah
0x140028398  mov     dword ptr [rsp+0A8h+var_80], 4
0x1400283a0  mov     byte ptr [rsp+0A8h+var_88], 3
0x1400283a5  call    WPP_RECORDER_AND_TRACE_SF__guid_
0x1400283aa  xor     eax, eax
0x1400283ac  mov     sil, dil
0x1400283af  movzx   ecx, ax
0x1400283b2  jmp     short loc_140028412
0x1400283b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400283bb  lea     rax, WPP_GLOBAL_Control
0x1400283c2  cmp     rcx, rax
0x1400283c5  jz      short loc_1400283D9
0x1400283c7  mov     eax, [rcx+2Ch]
0x1400283ca  test    al, 8
0x1400283cc  jz      short loc_1400283D9
0x1400283ce  cmp     byte ptr [rcx+29h], 4
0x1400283d2  jb      short loc_1400283D9
0x1400283d4  mov     dl, dil
0x1400283d7  jmp     short loc_1400283DB
0x1400283d9  xor     dl, dl
0x1400283db  lea     rax, WPP_RECORDER_INITIALIZED
0x1400283e2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400283e9  setnz   r8b
0x1400283ed  test    dl, dl
0x1400283ef  jnz     short loc_1400283F6
0x1400283f1  test    r8b, r8b
0x1400283f4  jz      short loc_14002840D
0x1400283f6  mov     [rsp+0A8h+var_60], r9d
0x1400283fb  mov     r9, [rcx+40h]
0x1400283ff  mov     rcx, [rcx+18h]
0x140028403  mov     [rsp+0A8h+var_68], rbx
0x140028408  call    WPP_RECORDER_AND_TRACE_SF__guid_d
0x14002840d  movzx   ecx, [rsp+0A8h+var_58]
0x140028412  mov     eax, [r14+1B8h]
0x140028419  mov     rdx, qword ptr cs:HandsfreeServiceClass_UUID.Data1
0x140028420  mov     r8, qword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data4
0x140028427  mov     r9, qword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data1
0x14002842e  shr     eax, 8
0x140028431  and     eax, 1Fh
0x140028434  cmp     [rbx+10h], eax
0x140028437  mov     rax, qword ptr cs:HandsfreeServiceClass_UUID.Data4
0x14002843e  setz    r10b
0x140028442  jmp     short loc_140028447
0x140028444  xor     r10b, r10b
0x140028447  cmp     rdx, [rbx]
0x14002844a  jnz     short loc_14002848F
0x14002844c  cmp     rax, [rbx+8]
0x140028450  jnz     short loc_14002848F
0x140028452  mov     [rsp+0A8h+arg_10], r10b
0x14002845a  mov     r12b, sil
0x14002845d  test    sil, sil
0x140028460  jz      short loc_140028467
0x140028462  movzx   eax, cx
0x140028465  jmp     short loc_140028469
0x140028467  xor     eax, eax
0x140028469  mov     [r14+2BAh], ax
0x140028471  mov     rax, qword ptr cs:HandsfreeServiceClass_UUID.Data4
0x140028478  mov     rdx, qword ptr cs:HandsfreeServiceClass_UUID.Data1
0x14002847f  mov     r8, qword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data4
0x140028486  mov     r9, qword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data1
0x14002848d  jmp     short loc_1400284EA
0x14002848f  cmp     r9, [rbx]
0x140028492  jnz     short loc_1400284E2
0x140028494  cmp     r8, [rbx+8]
0x140028498  jnz     short loc_1400284E2
0x14002849a  mov     [rsp+0A8h+arg_18], r10b
0x1400284a2  mov     r13b, sil
0x1400284a5  mov     r11b, r10b
0x1400284a8  test    sil, sil
0x1400284ab  jz      short loc_1400284B2
0x1400284ad  movzx   eax, cx
0x1400284b0  jmp     short loc_1400284B4
0x1400284b2  xor     eax, eax
0x1400284b4  mov     r10b, [rsp+0A8h+arg_10]
0x1400284bc  mov     [r14+2B8h], ax
0x1400284c4  mov     rax, qword ptr cs:HandsfreeServiceClass_UUID.Data4
0x1400284cb  mov     rdx, qword ptr cs:HandsfreeServiceClass_UUID.Data1
0x1400284d2  mov     r8, qword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data4
0x1400284d9  mov     r9, qword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data1
0x1400284e0  jmp     short loc_1400284F2
0x1400284e2  mov     r10b, [rsp+0A8h+arg_10]
0x1400284ea  mov     r11b, [rsp+0A8h+arg_18]
0x1400284f2  add     rbx, 18h
0x1400284f6  mov     esi, 0
0x1400284fb  cmp     rbx, r15
0x1400284fe  jnz     loc_1400282AF
0x140028504  mov     rbp, [rsp+0A8h+arg_0]
0x14002850c  test    r12b, r12b
0x14002850f  jz      short loc_14002852F
0x140028511  test    r13b, r13b
0x140028514  jz      short loc_140028526
0x140028516  test    r10b, r10b
0x140028519  jnz     short loc_140028526
0x14002851b  test    r11b, r11b
0x14002851e  jnz     short loc_14002852F
0x140028520  movups  xmm0, xmmword ptr [r15]
0x140028524  jmp     short loc_140028536
0x140028526  movups  xmm0, xmmword ptr cs:HandsfreeServiceClass_UUID.Data1
0x14002852d  jmp     short loc_140028536
0x14002852f  movups  xmm0, xmmword ptr cs:HandsfreeAudioGatewayServiceClass_UUID.Data1
0x140028536  movdqu  xmmword ptr [rbp+0], xmm0
0x14002853b  mov     rcx, cs:WPP_GLOBAL_Control
0x140028542  lea     rax, WPP_GLOBAL_Control
0x140028549  cmp     rcx, rax
0x14002854c  jz      short loc_14002855E
0x14002854e  mov     eax, [rcx+2Ch]
0x140028551  test    al, 8
0x140028553  jz      short loc_14002855E
0x140028555  cmp     byte ptr [rcx+29h], 5
0x140028559  mov     dl, dil
0x14002855c  jnb     short loc_140028561
0x14002855e  mov     dl, sil
0x140028561  lea     rax, WPP_RECORDER_INITIALIZED
0x140028568  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002856f  jz      short loc_140028577
0x140028571  cmp     [rcx+48h], si
0x140028575  jnz     short loc_14002857A
0x140028577  mov     dil, sil
0x14002857a  test    dl, dl
0x14002857c  jnz     short loc_140028583
0x14002857e  test    dil, dil
0x140028581  jz      short loc_1400285B8
0x140028583  mov     r9, [rcx+40h]
0x140028587  lea     r8, WPP_9739fd3d85a33a980818697074cd9c28_Traceguids
0x14002858e  mov     rcx, [rcx+18h]
0x140028592  mov     [rsp+0A8h+var_68], rbp
0x140028597  mov     [rsp+0A8h+var_70], r8
0x14002859c  mov     r8b, dil
0x14002859f  mov     word ptr [rsp+0A8h+var_78], 0Ch
0x1400285a6  mov     dword ptr [rsp+0A8h+var_80], 4
0x1400285ae  mov     byte ptr [rsp+0A8h+var_88], 5
0x1400285b3  call    WPP_RECORDER_AND_TRACE_SF__guid_
0x1400285b8  mov     rax, rbp
0x1400285bb  add     rsp, 68h
0x1400285bf  pop     r15
0x1400285c1  pop     r14
0x1400285c3  pop     r13
0x1400285c5  pop     r12
0x1400285c7  pop     rdi
0x1400285c8  pop     rsi
0x1400285c9  pop     rbp
0x1400285ca  pop     rbx
0x1400285cb  retn
```
