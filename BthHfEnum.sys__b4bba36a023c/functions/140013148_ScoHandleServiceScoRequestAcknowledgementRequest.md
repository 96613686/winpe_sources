# ScoHandleServiceScoRequestAcknowledgementRequest

- ea: `0x140013148`
- end: `0x1400136a9`
- name: `ScoHandleServiceScoRequestAcknowledgementRequest`
- size: `1377`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x140004810`
- `0x14000a914`
- `0x14000cb04`
- `0x14000dcf0`
- `0x14000f700`
- `0x1400112c4`
- `0x140012100`
- `0x140013148`
- `0x140014438`
- `0x140014510`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall ScoHandleServiceScoRequestAcknowledgementRequest(struct WDFDEVICE__ *a1, __int64 a2)
{
  __int64 v3; // r14
  char v4; // bl
  __int64 v5; // r8
  char v6; // di
  int v7; // edx
  int v8; // r8d
  unsigned int v9; // r12d
  int v10; // edx
  int v11; // r8d
  int ScoState; // r13d
  int v13; // edx
  int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // edx
  int v18; // r8d
  __int64 v19; // r8
  struct WDFDEVICE__ *v20; // rsi
  void (__fastcall *v21)(_QWORD, struct WDFDEVICE__ *); // rax
  int v23; // [rsp+20h] [rbp-98h]
  _QWORD v24[11]; // [rsp+60h] [rbp-58h] BYREF
  char v27; // [rsp+D8h] [rbp+20h]

  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_140022150);
  v24[0] = 0;
  v4 = 1;
  LOBYTE(v5) = 1;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2560))(
         WdfDriverGlobals,
         *(_QWORD *)(v3 + 480),
         v5);
  v27 = v6;
  v23 = 0;
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _QWORD *))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         a2,
         8,
         v24);
  if ( (v9 & 0x80000000) == 0 )
  {
    ScoState = GetScoState(v3);
    LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_BTHHF_SCO_STATUS_INDICATIONlSCOSTATEl(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        0);
    }
    v13 = *(_DWORD *)v24[0];
    if ( (unsigned int)(*(_DWORD *)v24[0] - 4) <= 1 )
    {
      if ( *(_BYTE *)(v24[0] + 4LL) )
      {
        if ( ScoState == 5 )
        {
          if ( v6 )
          {
            v20 = a1;
            v9 = ScoChannelOpenAsync(a1);
            v14 = v9;
            goto LABEL_75;
          }
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          {
            v4 = 0;
          }
          if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v13) = v4;
            LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_(
              WPP_GLOBAL_Control->AttachedDevice,
              v13,
              v11,
              WPP_GLOBAL_Control->DeviceExtension,
              3,
              5,
              122,
              (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
          }
          v14 = -1073741643;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v4 = 0;
          }
          if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v13) = v4;
            LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_BTHHF_SCO_STATUS_INDICATIONSCOSTATEd(
              WPP_GLOBAL_Control->AttachedDevice,
              v13,
              v11,
              WPP_GLOBAL_Control->DeviceExtension,
              v23);
          }
          v14 = -1073741436;
        }
      }
      else
      {
        v14 = -1073741790;
      }
      v20 = a1;
LABEL_79:
      v21 = *(void (__fastcall **)(_QWORD, struct WDFDEVICE__ *))(v3 + 408);
      if ( v21 )
        v21((unsigned int)v14, v20);
      return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
               WdfDriverGlobals,
               a2,
               v9);
    }
    if ( v13 != 6 )
      return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
               WdfDriverGlobals,
               a2,
               v9);
    v14 = 0;
    if ( ScoState != 6 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v4 = 0;
      }
      if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = v4;
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v13,
          v11,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          125,
          (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
      }
      if ( *(_DWORD *)(v3 + 108) )
      {
        v20 = a1;
        ScoHandleStreamFailure(-1073741667, a1);
        v4 = 0;
        goto LABEL_30;
      }
      goto LABEL_28;
    }
    if ( !*(_BYTE *)(v24[0] + 4LL) || !v27 )
    {
      v14 = -1073741790;
      goto LABEL_29;
    }
    SetScoState(v3, 7);
    WdfIoQueueFindAndCompleteIoctlRequest(*(_QWORD *)(v3 + 96), v15, 2228267, 0);
    WdfIoQueueFindAndCompleteIoctlRequest(*(_QWORD *)(v3 + 96), v16, 2752536, v9);
    if ( *(_QWORD *)(v3 + 112) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || (LOBYTE(v17) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      {
        LOBYTE(v17) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        v4 = 0;
      if ( (_BYTE)v17 || v4 )
      {
        LOBYTE(v18) = v4;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v17,
          v18,
          WPP_GLOBAL_Control->DeviceExtension,
          5,
          5,
          123,
          (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
      }
      v19 = -100000000;
    }
    else
    {
      if ( *(_DWORD *)(v3 + 108) )
        goto LABEL_28;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || (LOBYTE(v17) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      {
        LOBYTE(v17) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        v4 = 0;
      if ( (_BYTE)v17 || v4 )
      {
        LOBYTE(v18) = v4;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v17,
          v18,
          WPP_GLOBAL_Control->DeviceExtension,
          5,
          5,
          124,
          (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
      }
      v19 = -50000000;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2552))(
      WdfDriverGlobals,
      *(_QWORD *)(v3 + 360),
      v19);
LABEL_28:
    v4 = 0;
LABEL_29:
    v20 = a1;
LABEL_30:
    if ( v4 )
      ScoChannelClose(v20, 0);
    v9 = 0;
LABEL_75:
    if ( v14 >= 0 )
      return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
               WdfDriverGlobals,
               a2,
               v9);
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    v4 = 0;
  }
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = v4;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      5,
      126,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
      v9);
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
           WdfDriverGlobals,
           a2,
           v9);
}

```

## disassembly

```asm
0x140013148  mov     [rsp+arg_8], rdx
0x14001314d  mov     [rsp+arg_0], rcx
0x140013152  push    rbx
0x140013153  push    rbp
0x140013154  push    rsi
0x140013155  push    rdi
0x140013156  push    r12
0x140013158  push    r13
0x14001315a  push    r14
0x14001315c  push    r15
0x14001315e  sub     rsp, 78h
0x140013162  mov     rax, cs:WdfFunctions_01015
0x140013169  mov     rsi, rdx
0x14001316c  mov     r8, cs:off_140022150
0x140013173  mov     rdx, rcx
0x140013176  mov     rcx, cs:WdfDriverGlobals
0x14001317d  mov     rax, [rax+650h]
0x140013184  call    _guard_dispatch_icall
0x140013189  mov     rdx, cs:WdfFunctions_01015
0x140013190  mov     r14, rax
0x140013193  mov     rcx, cs:WdfDriverGlobals
0x14001319a  xor     r13d, r13d
0x14001319d  mov     [rsp+0B8h+var_58], r13
0x1400131a2  mov     rax, [rdx+0A00h]
0x1400131a9  mov     rdx, [r14+1E0h]
0x1400131b0  lea     ebx, [r13+1]
0x1400131b4  mov     r8b, bl
0x1400131b7  call    _guard_dispatch_icall
0x1400131bc  mov     rcx, cs:WdfFunctions_01015
0x1400131c3  lea     r9, [rsp+0B8h+var_58]
0x1400131c8  mov     dil, al
0x1400131cb  mov     [rsp+0B8h+arg_18], al
0x1400131d2  lea     r8d, [r13+8]
0x1400131d6  mov     [rsp+0B8h+var_98], r13
0x1400131db  mov     rdx, rsi
0x1400131de  mov     rax, [rcx+868h]
0x1400131e5  mov     rcx, cs:WdfDriverGlobals
0x1400131ec  call    _guard_dispatch_icall
0x1400131f1  mov     r12d, eax
0x1400131f4  test    eax, eax
0x1400131f6  js      loc_1400135FC
0x1400131fc  mov     rcx, r14
0x1400131ff  call    ?GetScoState@@YA?AW4SCOSTATE@@PEAU_SCOCONTEXT@@@Z; GetScoState(_SCOCONTEXT *)
0x140013204  mov     r13d, eax
0x140013207  mov     r11, cs:WPP_GLOBAL_Control
0x14001320e  lea     rbp, WPP_GLOBAL_Control
0x140013215  mov     sil, 10h
0x140013218  cmp     r11, rbp
0x14001321b  jz      short loc_140013234
0x14001321d  mov     ecx, [r11+2Ch]
0x140013221  test    sil, cl
0x140013224  jz      short loc_140013234
0x140013226  cmp     byte ptr [r11+29h], 4
0x14001322b  jb      short loc_140013234
0x14001322d  mov     dl, bl
0x14001322f  xor     r10d, r10d
0x140013232  jmp     short loc_14001323A
0x140013234  xor     r10d, r10d
0x140013237  mov     dl, r10b
0x14001323a  lea     r15, WPP_RECORDER_INITIALIZED
0x140013241  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013248  setnz   r8b
0x14001324c  test    dl, dl
0x14001324e  jnz     short loc_140013255
0x140013250  test    r8b, r8b
0x140013253  jz      short loc_14001328E
0x140013255  mov     rcx, [r11+18h]
0x140013259  mov     r9d, r10d
0x14001325c  mov     r10, [rsp+0B8h+var_58]
0x140013261  test    dil, dil
0x140013264  setz    r9b
0x140013268  mov     [rsp+0B8h+var_60], r9d
0x14001326d  movzx   eax, byte ptr [r10+4]
0x140013272  mov     r9, [r11+40h]
0x140013276  mov     [rsp+0B8h+var_68], r13d
0x14001327b  mov     [rsp+0B8h+var_70], eax
0x14001327f  mov     eax, [r10]
0x140013282  mov     [rsp+0B8h+var_78], eax
0x140013286  call    WPP_RECORDER_AND_TRACE_SF_BTHHF_SCO_STATUS_INDICATIONlSCOSTATEl
0x14001328b  xor     r10d, r10d
0x14001328e  mov     rcx, [rsp+0B8h+var_58]
0x140013293  mov     edx, [rcx]
0x140013295  lea     eax, [rdx-4]
0x140013298  cmp     eax, ebx
0x14001329a  jbe     loc_1400134D7
0x1400132a0  cmp     edx, 6
0x1400132a3  jnz     loc_140013672
0x1400132a9  mov     edi, r10d
0x1400132ac  cmp     r13d, edx
0x1400132af  jnz     loc_14001344A
0x1400132b5  cmp     [rcx+4], r10b
0x1400132b9  jz      loc_140013440
0x1400132bf  cmp     [rsp+0B8h+arg_18], r10b
0x1400132c7  jz      loc_140013440
0x1400132cd  mov     edx, 7
0x1400132d2  mov     rcx, r14
0x1400132d5  call    SetScoState
0x1400132da  mov     rcx, [r14+60h]
0x1400132de  xor     r9d, r9d
0x1400132e1  mov     r8d, 22002Bh
0x1400132e7  call    WdfIoQueueFindAndCompleteIoctlRequest
0x1400132ec  mov     rcx, [r14+60h]
0x1400132f0  mov     r9d, r12d
0x1400132f3  mov     r8d, 2A0018h
0x1400132f9  call    WdfIoQueueFindAndCompleteIoctlRequest
0x1400132fe  xor     r10d, r10d
0x140013301  cmp     [r14+70h], r10
0x140013305  jz      loc_1400133C4
0x14001330b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013312  cmp     rcx, rbp
0x140013315  jz      short loc_140013327
0x140013317  mov     eax, [rcx+2Ch]
0x14001331a  test    sil, al
0x14001331d  jz      short loc_140013327
0x14001331f  cmp     byte ptr [rcx+29h], 5
0x140013323  mov     dl, bl
0x140013325  jnb     short loc_14001332A
0x140013327  mov     dl, r10b
0x14001332a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013331  jz      short loc_14001333A
0x140013333  cmp     [rcx+48h], r10w
0x140013338  jnz     short loc_14001333D
0x14001333a  mov     bl, r10b
0x14001333d  test    dl, dl
0x14001333f  jnz     short loc_140013345
0x140013341  test    bl, bl
0x140013343  jz      short loc_140013375
0x140013345  mov     r9, [rcx+40h]
0x140013349  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140013350  mov     rcx, [rcx+18h]
0x140013354  mov     r8b, bl
0x140013357  mov     [rsp+0B8h+var_80], rax
0x14001335c  mov     [rsp+0B8h+var_88], 7Bh ; '{'
0x140013363  mov     [rsp+0B8h+var_90], 5
0x14001336b  mov     byte ptr [rsp+0B8h+var_98], 5
0x140013370  call    WPP_RECORDER_AND_TRACE_SF_
0x140013375  mov     r8, 0FFFFFFFFFA0A1F00h
0x14001337c  mov     rax, cs:WdfFunctions_01015
0x140013383  mov     rdx, [r14+168h]
0x14001338a  mov     rcx, cs:WdfDriverGlobals
0x140013391  mov     rax, [rax+9F8h]
0x140013398  call    _guard_dispatch_icall
0x14001339d  xor     r10d, r10d
0x1400133a0  mov     bl, dil
0x1400133a3  mov     rsi, [rsp+0B8h+arg_0]
0x1400133ab  test    bl, bl
0x1400133ad  jz      short loc_1400133BC
0x1400133af  xor     edx, edx
0x1400133b1  mov     rcx, rsi
0x1400133b4  call    ScoChannelClose
0x1400133b9  xor     r10d, r10d
0x1400133bc  mov     r12d, r10d
0x1400133bf  jmp     loc_1400135C9
0x1400133c4  cmp     [r14+6Ch], r10d
0x1400133c8  jnz     short loc_1400133A0
0x1400133ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400133d1  cmp     rcx, rbp
0x1400133d4  jz      short loc_1400133E6
0x1400133d6  mov     eax, [rcx+2Ch]
0x1400133d9  test    sil, al
0x1400133dc  jz      short loc_1400133E6
0x1400133de  cmp     byte ptr [rcx+29h], 5
0x1400133e2  mov     dl, bl
0x1400133e4  jnb     short loc_1400133E9
0x1400133e6  mov     dl, r10b
0x1400133e9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400133f0  jz      short loc_1400133F9
0x1400133f2  cmp     [rcx+48h], r10w
0x1400133f7  jnz     short loc_1400133FC
0x1400133f9  mov     bl, r10b
0x1400133fc  test    dl, dl
0x1400133fe  jnz     short loc_140013404
0x140013400  test    bl, bl
0x140013402  jz      short loc_140013434
0x140013404  mov     r9, [rcx+40h]
0x140013408  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14001340f  mov     rcx, [rcx+18h]
0x140013413  mov     r8b, bl
0x140013416  mov     [rsp+0B8h+var_80], rax
0x14001341b  mov     [rsp+0B8h+var_88], 7Ch ; '|'
0x140013422  mov     [rsp+0B8h+var_90], 5
0x14001342a  mov     byte ptr [rsp+0B8h+var_98], 5
0x14001342f  call    WPP_RECORDER_AND_TRACE_SF_
0x140013434  mov     r8, 0FFFFFFFFFD050F80h
0x14001343b  jmp     loc_14001337C
0x140013440  mov     edi, 0C0000022h
0x140013445  jmp     loc_1400133A3
0x14001344a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013451  cmp     rcx, rbp
0x140013454  jz      short loc_140013464
0x140013456  mov     eax, [rcx+2Ch]
0x140013459  test    sil, al
0x14001345c  jz      short loc_140013464
0x14001345e  cmp     byte ptr [rcx+29h], 4
0x140013462  jnb     short loc_140013467
0x140013464  mov     bl, r10b
0x140013467  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001346e  setnz   r8b
0x140013472  test    bl, bl
0x140013474  jnz     short loc_14001347B
0x140013476  test    r8b, r8b
0x140013479  jz      short loc_1400134AD
0x14001347b  mov     r9, [rcx+40h]
0x14001347f  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140013486  mov     rcx, [rcx+18h]
0x14001348a  mov     dl, bl
0x14001348c  mov     [rsp+0B8h+var_80], rax
0x140013491  mov     [rsp+0B8h+var_88], 7Dh ; '}'
0x140013498  mov     [rsp+0B8h+var_90], 5
0x1400134a0  mov     byte ptr [rsp+0B8h+var_98], 4
0x1400134a5  call    WPP_RECORDER_AND_TRACE_SF_
0x1400134aa  xor     r10d, r10d
0x1400134ad  cmp     [r14+6Ch], r10d
0x1400134b1  jz      loc_1400133A0
0x1400134b7  mov     rsi, [rsp+0B8h+arg_0]
0x1400134bf  mov     ecx, 0C000009Dh; int
0x1400134c4  mov     rdx, rsi; struct WDFDEVICE__ *
0x1400134c7  call    ?ScoHandleStreamFailure@@YAXJPEAUWDFDEVICE__@@@Z; ScoHandleStreamFailure(long,WDFDEVICE__ *)
0x1400134cc  xor     r10d, r10d
0x1400134cf  mov     bl, dil
0x1400134d2  jmp     loc_1400133AB
0x1400134d7  cmp     [rcx+4], r10b
0x1400134db  jz      loc_1400135D3
0x1400134e1  cmp     r13d, 5
0x1400134e5  jz      short loc_140013548
0x1400134e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400134ee  cmp     rcx, rbp
0x1400134f1  jz      short loc_140013501
0x1400134f3  mov     eax, [rcx+2Ch]
0x1400134f6  test    sil, al
0x1400134f9  jz      short loc_140013501
0x1400134fb  cmp     byte ptr [rcx+29h], 4
0x1400134ff  jnb     short loc_140013504
0x140013501  mov     bl, r10b
0x140013504  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001350b  setnz   r8b
0x14001350f  test    bl, bl
0x140013511  jnz     short loc_140013518
0x140013513  test    r8b, r8b
0x140013516  jz      short loc_14001353E
0x140013518  mov     eax, [r14+6Ch]
0x14001351c  mov     r9, [rcx+40h]
0x140013520  mov     rcx, [rcx+18h]
0x140013524  mov     [rsp+0B8h+var_68], eax
0x140013528  mov     eax, [r14+178h]
0x14001352f  mov     [rsp+0B8h+var_70], eax
0x140013533  mov     [rsp+0B8h+var_78], edx
0x140013537  mov     dl, bl
0x140013539  call    WPP_RECORDER_AND_TRACE_SF_BTHHF_SCO_STATUS_INDICATIONSCOSTATEd
0x14001353e  mov     edi, 0C0000184h
0x140013543  jmp     loc_1400135D8
0x140013548  test    dil, dil
0x14001354b  jnz     short loc_1400135B4
0x14001354d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013554  cmp     rcx, rbp
0x140013557  jz      short loc_140013567
0x140013559  mov     eax, [rcx+2Ch]
0x14001355c  test    sil, al
0x14001355f  jz      short loc_140013567
0x140013561  cmp     byte ptr [rcx+29h], 3
0x140013565  jnb     short loc_14001356A
0x140013567  mov     bl, r10b
0x14001356a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013571  setnz   r8b
0x140013575  test    bl, bl
0x140013577  jnz     short loc_14001357E
0x140013579  test    r8b, r8b
0x14001357c  jz      short loc_1400135AD
0x14001357e  mov     r9, [rcx+40h]
0x140013582  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140013589  mov     rcx, [rcx+18h]
0x14001358d  mov     dl, bl
0x14001358f  mov     [rsp+0B8h+var_80], rax
0x140013594  mov     [rsp+0B8h+var_88], 7Ah ; 'z'
0x14001359b  mov     [rsp+0B8h+var_90], 5
0x1400135a3  mov     byte ptr [rsp+0B8h+var_98], 3
0x1400135a8  call    WPP_RECORDER_AND_TRACE_SF_
0x1400135ad  mov     edi, 0C00000B5h
0x1400135b2  jmp     short loc_1400135D8
0x1400135b4  mov     rsi, [rsp+0B8h+arg_0]
0x1400135bc  mov     rcx, rsi; struct WDFDEVICE__ *
0x1400135bf  call    ?ScoChannelOpenAsync@@YAJPEAUWDFDEVICE__@@@Z; ScoChannelOpenAsync(WDFDEVICE__ *)
0x1400135c4  mov     r12d, eax
0x1400135c7  mov     edi, eax
0x1400135c9  test    edi, edi
0x1400135cb  jns     loc_140013672
0x1400135d1  jmp     short loc_1400135E0
0x1400135d3  mov     edi, 0C0000022h
0x1400135d8  mov     rsi, [rsp+0B8h+arg_0]
0x1400135e0  mov     rax, [r14+198h]
0x1400135e7  test    rax, rax
0x1400135ea  jz      loc_140013672
0x1400135f0  mov     rdx, rsi
0x1400135f3  mov     ecx, edi
0x1400135f5  call    _guard_dispatch_icall
0x1400135fa  jmp     short loc_140013672
0x1400135fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140013603  lea     rbp, WPP_GLOBAL_Control
0x14001360a  cmp     rcx, rbp
0x14001360d  jz      short loc_140013620
  ... truncated ...
```
