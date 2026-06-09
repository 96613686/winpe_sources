# Endpoint_OnCancelSetDequeuePointerCompletion

- ea: `0x140039880`
- end: `0x140039b5e`
- name: `Endpoint_OnCancelSetDequeuePointerCompletion`
- size: `734`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1400038c0`
- `0x14000c264`
- `0x1400270d0`
- `0x14002792c`
- `0x14002b2c0`
- `0x14002b300`
- `0x14003107c`
- `0x140039880`
- `0x14003e79c`
- `0x1400492a0`
- `0x140057db0`

## string_xrefs

- `0x1400399d1`: `Set Dequeue Pointer command following a Stop Endpoint command failed`
- `0x140039a9d`: `Feature_RetryOnContextStateErrorDuringSetDequeuePointer was effective`

## pseudocode

```c
__int64 __fastcall Endpoint_OnCancelSetDequeuePointerCompletion(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rbp
  _BYTE *v7; // rsi
  int v8; // edx
  __int64 v9; // rdx
  int v10; // edx
  int v11; // edx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v13; // rcx
  __int64 result; // rax
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v19; // ecx
  unsigned __int16 *v20; // rdi
  int v21; // edx

  v3 = *(_QWORD *)(a1 + 48);
  v5 = a2;
  v7 = (_BYTE *)(a1 + 60);
  if ( (unsigned int)Feature_ROCSEDSDP__private_IsEnabledDeviceUsageNoInline() && *v7 == 19 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = *(unsigned __int16 *)(a1 + 34);
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_dddL(*(_QWORD *)(v3 + 80), v8, *(unsigned __int8 *)(*(_QWORD *)(v3 + 16) + 143LL), 65);
    }
    v9 = 40;
    return ESM_AddEsmEvent(v3, v9);
  }
  if ( (_DWORD)v5 == 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = *(unsigned __int8 *)(*(_QWORD *)(v3 + 16) + 143LL);
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_ddd(
        *(_QWORD *)(v3 + 80),
        v10,
        13,
        66,
        (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
        *(_BYTE *)(*(_QWORD *)(v3 + 16) + 143LL),
        *(_DWORD *)(v3 + 152),
        *(_WORD *)(a1 + 34));
    }
LABEL_15:
    _m_prefetchw((const void *)(v3 + 32));
    result = (unsigned int)_InterlockedOr((volatile signed __int32 *)(v3 + 32), 2u);
    if ( (result & 2) != 0 )
      return result;
    v9 = 12;
    return ESM_AddEsmEvent(v3, v9);
  }
  if ( *v7 != 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = *(unsigned __int16 *)(a1 + 34);
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_dddL(*(_QWORD *)(v3 + 80), v11, *(unsigned __int8 *)(*(_QWORD *)(v3 + 16) + 143LL), 67);
    }
    Controller_HwVerifierBreakIfEnabled(
      *(_QWORD *)v3,
      *(_QWORD *)(v3 + 8),
      *(_QWORD *)(v3 + 24),
      512,
      (__int64)"Set Dequeue Pointer command following a Stop Endpoint command failed",
      a1 + 24,
      a3);
    IsEnabledDeviceUsageNoInline = Feature_ATFUR__private_IsEnabledDeviceUsageNoInline();
    v13 = *(_QWORD *)(v3 + 16);
    if ( IsEnabledDeviceUsageNoInline )
      Controller_ReportFatalErrorEx(*(_QWORD *)v3, 2, 4106, *(unsigned __int8 *)(a1 + 60), v5, v13, v3, 0);
    else
      Controller_ReportFatalError(*(_QWORD *)v3, 2, 4106, 0, v13, v3, 0);
    goto LABEL_15;
  }
  if ( (unsigned int)Feature_ROCSEDSDP__private_IsEnabledDeviceUsageNoInline() )
  {
    v15 = *(unsigned int *)(v3 + 168);
    if ( (_DWORD)v15 != 1 )
    {
      v16 = *(_DWORD *)(*(_QWORD *)v3 + 644LL) == 1
          ? *(unsigned __int16 *)(*(_QWORD *)v3 + 652LL) | (*(unsigned __int16 *)(*(_QWORD *)v3 + 648LL) << 16)
          : 0LL;
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        "USBXHCI.SYS",
        v16,
        v15,
        "Feature_RetryOnContextStateErrorDuringSetDequeuePointer was effective");
      v17 = *(_QWORD *)v3;
      ++*(_DWORD *)(v17 + 928);
      ++*(_DWORD *)(v17 + 992);
      *(_BYTE *)(v17 + 872) = 1;
      v18 = *(_QWORD *)v3;
      v19 = *(_DWORD *)(v3 + 168);
      if ( v19 > *(_DWORD *)(*(_QWORD *)v3 + 940LL) )
      {
        *(_DWORD *)(v18 + 940) = v19;
        *(_BYTE *)(v18 + 872) = 1;
      }
    }
  }
  v20 = (unsigned __int16 *)(a1 + 34);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v21 = *v20;
    LOBYTE(v21) = 4;
    WPP_RECORDER_SF_dddL(*(_QWORD *)(v3 + 80), v21, *(unsigned __int8 *)(*(_QWORD *)(v3 + 16) + 143LL), 68);
  }
  if ( *(_BYTE *)(v3 + 37) )
    return Endpoint_StreamsOnCancelSetDequeuePointerComplete(v3, *v20);
  v9 = 16;
  return ESM_AddEsmEvent(v3, v9);
}

```

## disassembly

```asm
0x140039880  push    rbx
0x140039882  push    rbp
0x140039883  push    rsi
0x140039884  push    rdi
0x140039885  push    r14
0x140039887  sub     rsp, 50h
0x14003988b  mov     rbx, [rcx+30h]
0x14003988f  mov     r14, r8
0x140039892  movsxd  rbp, edx
0x140039895  mov     rdi, rcx
0x140039898  lea     rsi, [rcx+3Ch]
0x14003989c  call    Feature_ROCSEDSDP__private_IsEnabledDeviceUsageNoInline
0x1400398a1  test    eax, eax
0x1400398a3  jz      short loc_140039900
0x1400398a5  cmp     byte ptr [rsi], 13h
0x1400398a8  jnz     short loc_140039900
0x1400398aa  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400398b1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400398b8  jz      short loc_1400398F6
0x1400398ba  mov     rax, [rbx+10h]
0x1400398be  mov     r9d, 41h ; 'A'
0x1400398c4  movzx   edx, word ptr [rdi+22h]
0x1400398c8  mov     rcx, [rbx+50h]
0x1400398cc  mov     [rsp+78h+var_38], 13h
0x1400398d4  movzx   r8d, byte ptr [rax+8Fh]
0x1400398dc  mov     eax, [rbx+98h]
0x1400398e2  mov     dword ptr [rsp+78h+var_40], edx
0x1400398e6  mov     dl, 2
0x1400398e8  mov     dword ptr [rsp+78h+var_48], eax
0x1400398ec  mov     dword ptr [rsp+78h+var_50], r8d
0x1400398f1  call    WPP_RECORDER_SF_dddL
0x1400398f6  mov     edx, 28h ; '('
0x1400398fb  jmp     loc_140039B4A
0x140039900  cmp     ebp, 3
0x140039903  jnz     short loc_14003995E
0x140039905  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003990c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140039913  jz      loc_140039A3F
0x140039919  mov     rax, [rbx+10h]
0x14003991d  lea     r9d, [rbp+3Fh]
0x140039921  movzx   ecx, word ptr [rdi+22h]
0x140039925  lea     r8d, [rbp+0Ah]
0x140039929  mov     dword ptr [rsp+78h+var_40], ecx
0x14003992d  mov     rcx, [rbx+50h]
0x140039931  movzx   edx, byte ptr [rax+8Fh]
0x140039938  mov     eax, [rbx+98h]
0x14003993e  mov     dword ptr [rsp+78h+var_48], eax
0x140039942  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140039949  mov     dword ptr [rsp+78h+var_50], edx
0x14003994d  mov     dl, 4
0x14003994f  mov     [rsp+78h+var_58], rax
0x140039954  call    WPP_RECORDER_SF_ddd
0x140039959  jmp     loc_140039A3F
0x14003995e  movzx   ecx, byte ptr [rsi]
0x140039961  cmp     cl, 1
0x140039964  jz      loc_140039A64
0x14003996a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140039971  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140039978  jz      short loc_1400399B2
0x14003997a  mov     rax, [rbx+10h]
0x14003997e  mov     r9d, 43h ; 'C'
0x140039984  movzx   edx, word ptr [rdi+22h]
0x140039988  mov     [rsp+78h+var_38], ecx
0x14003998c  mov     rcx, [rbx+50h]
0x140039990  movzx   r8d, byte ptr [rax+8Fh]
0x140039998  mov     eax, [rbx+98h]
0x14003999e  mov     dword ptr [rsp+78h+var_40], edx
0x1400399a2  mov     dl, 2
0x1400399a4  mov     dword ptr [rsp+78h+var_48], eax
0x1400399a8  mov     dword ptr [rsp+78h+var_50], r8d
0x1400399ad  call    WPP_RECORDER_SF_dddL
0x1400399b2  mov     r8, [rbx+18h]
0x1400399b6  lea     rax, [rdi+18h]
0x1400399ba  mov     rdx, [rbx+8]
0x1400399be  mov     r9d, 200h
0x1400399c4  mov     rcx, [rbx]
0x1400399c7  mov     [rsp+78h+var_48], r14
0x1400399cc  mov     [rsp+78h+var_50], rax
0x1400399d1  lea     rax, aSetDequeuePoin_1; "Set Dequeue Pointer command following a"...
0x1400399d8  mov     [rsp+78h+var_58], rax
0x1400399dd  call    Controller_HwVerifierBreakIfEnabled
0x1400399e2  call    Feature_ATFUR__private_IsEnabledDeviceUsageNoInline
0x1400399e7  mov     rcx, [rbx+10h]
0x1400399eb  mov     edx, 2
0x1400399f0  mov     r8d, 100Ah
0x1400399f6  test    eax, eax
0x1400399f8  jz      short loc_140039A21
0x1400399fa  movzx   r9d, byte ptr [rdi+3Ch]
0x1400399ff  mov     [rsp+78h+var_40], 0
0x140039a08  mov     [rsp+78h+var_48], rbx
0x140039a0d  mov     [rsp+78h+var_50], rcx
0x140039a12  mov     rcx, [rbx]
0x140039a15  mov     [rsp+78h+var_58], rbp
0x140039a1a  call    Controller_ReportFatalErrorEx
0x140039a1f  jmp     short loc_140039A3F
0x140039a21  mov     [rsp+78h+var_48], 0
0x140039a2a  xor     r9d, r9d
0x140039a2d  mov     [rsp+78h+var_50], rbx
0x140039a32  mov     [rsp+78h+var_58], rcx
0x140039a37  mov     rcx, [rbx]
0x140039a3a  call    Controller_ReportFatalError
0x140039a3f  prefetchw byte ptr [rbx+20h]
0x140039a43  mov     eax, [rbx+20h]
0x140039a46  mov     ecx, eax
0x140039a48  or      ecx, 2
0x140039a4b  lock cmpxchg [rbx+20h], ecx
0x140039a50  jnz     short loc_140039A46
0x140039a52  test    al, 2
0x140039a54  jnz     loc_140039B52
0x140039a5a  mov     edx, 0Ch
0x140039a5f  jmp     loc_140039B4A
0x140039a64  call    Feature_ROCSEDSDP__private_IsEnabledDeviceUsageNoInline
0x140039a69  test    eax, eax
0x140039a6b  jz      short loc_140039AE4
0x140039a6d  mov     r8d, [rbx+0A8h]
0x140039a74  cmp     r8d, 1
0x140039a78  jz      short loc_140039AE4
0x140039a7a  mov     rax, [rbx]; __annotation("Debug", "TelemetryAssert", "FALSE", "Feature_RetryOnContextStateErrorDuringSetDequeuePointer was effective")
0x140039a7d  cmp     dword ptr [rax+284h], 1
0x140039a84  jnz     short loc_140039A9B
0x140039a86  movzx   edx, word ptr [rax+288h]
0x140039a8d  movzx   eax, word ptr [rax+28Ch]
0x140039a94  shl     edx, 10h
0x140039a97  or      edx, eax
0x140039a99  jmp     short loc_140039A9D
0x140039a9b  xor     edx, edx
0x140039a9d  lea     r9, aFeatureRetryon_0; "Feature_RetryOnContextStateErrorDuringS"...
0x140039aa4  lea     rcx, aUsbxhciSys_0; "USBXHCI.SYS"
0x140039aab  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140039ab0  mov     rax, [rbx]
0x140039ab3  inc     dword ptr [rax+3A0h]
0x140039ab9  inc     dword ptr [rax+3E0h]
0x140039abf  mov     byte ptr [rax+368h], 1
0x140039ac6  mov     rax, [rbx]
0x140039ac9  mov     ecx, [rbx+0A8h]
0x140039acf  cmp     ecx, [rax+3ACh]
0x140039ad5  jbe     short loc_140039AE4
0x140039ad7  mov     [rax+3ACh], ecx
0x140039add  mov     byte ptr [rax+368h], 1
0x140039ae4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140039aeb  add     rdi, 22h ; '"'
0x140039aef  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140039af6  jz      short loc_140039B32
0x140039af8  mov     rax, [rbx+10h]
0x140039afc  mov     r9d, 44h ; 'D'
0x140039b02  movzx   ecx, byte ptr [rsi]
0x140039b05  movzx   edx, word ptr [rdi]
0x140039b08  mov     [rsp+78h+var_38], ecx
0x140039b0c  movzx   r8d, byte ptr [rax+8Fh]
0x140039b14  mov     eax, [rbx+98h]
0x140039b1a  mov     rcx, [rbx+50h]
0x140039b1e  mov     dword ptr [rsp+78h+var_40], edx
0x140039b22  mov     dl, 4
0x140039b24  mov     dword ptr [rsp+78h+var_48], eax
0x140039b28  mov     dword ptr [rsp+78h+var_50], r8d
0x140039b2d  call    WPP_RECORDER_SF_dddL
0x140039b32  cmp     byte ptr [rbx+25h], 0
0x140039b36  jz      short loc_140039B45
0x140039b38  movzx   edx, word ptr [rdi]
0x140039b3b  mov     rcx, rbx
0x140039b3e  call    Endpoint_StreamsOnCancelSetDequeuePointerComplete
0x140039b43  jmp     short loc_140039B52
0x140039b45  mov     edx, 10h
0x140039b4a  mov     rcx, rbx
0x140039b4d  call    ESM_AddEsmEvent
0x140039b52  add     rsp, 50h
0x140039b56  pop     r14
0x140039b58  pop     rdi
0x140039b59  pop     rsi
0x140039b5a  pop     rbp
0x140039b5b  pop     rbx
0x140039b5c  retn
```
