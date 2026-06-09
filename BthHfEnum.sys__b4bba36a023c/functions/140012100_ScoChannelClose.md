# ScoChannelClose

- ea: `0x140012100`
- end: `0x14001239a`
- name: `ScoChannelClose`
- size: `666`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400016d4`
- `0x140001790`
- `0x140006e8c`
- `0x14000f890`
- `0x14000fa40`
- `0x1400123a0`
- `0x140013148`
- `0x140013df8`
- `0x140014258`

## callees

- `0x140004810`
- `0x14000affc`
- `0x14000cb04`
- `0x1400112c4`
- `0x140012100`
- `0x1400153fc`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall ScoChannelClose(__int64 a1, int a2)
{
  __int64 v4; // rax
  _QWORD *v5; // rbx
  int v6; // edx
  int ScoState; // edi
  __int64 v8; // r8
  char v9; // r14
  struct _BRB *v10; // rax
  struct _BRB *v11; // rbp
  int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  struct WDFREQUEST__ *v16; // rsi
  struct WDFREQUEST__ *v18; // [rsp+B0h] [rbp+18h] BYREF

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_140022150);
  v18 = 0;
  v5 = (_QWORD *)v4;
  ScoState = GetScoState(v4);
  v9 = 1;
  LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qSCOSTATE(WPP_GLOBAL_Control->AttachedDevice, v6, v8, WPP_GLOBAL_Control->DeviceExtension);
  if ( ((ScoState - 4) & 0xFFFFFFFC) != 0 || ScoState == 5 )
  {
    return (unsigned int)-1073741808;
  }
  else
  {
    v10 = (struct _BRB *)(*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v5[1] + 32LL))(
                           516,
                           *((unsigned int *)v5 + 6),
                           v8);
    v11 = v10;
    if ( v10 )
    {
      v10->BrbL2caUnregisterServer.ServerHandle = (PVOID)v5[16];
      v10->BrbL2caRegisterServer.BtAddress = v5[2];
      v12 = WdfIoTargetCreateAndFormatRequestForBrb(
              0,
              (struct WDFIOTARGET__ *)*v5,
              (struct _BTH_PROFILE_DRIVER_INTERFACE *)v5[1],
              v10,
              &v18);
      if ( v12 < 0 )
      {
        v16 = v18;
      }
      else
      {
        v11 = 0;
        SetScoState(v5, (unsigned int)(a2 != 0) + 8);
        v15 = a1;
        v16 = v18;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, _QWORD, __int64))(WdfFunctions_01015 + 2080))(
          WdfDriverGlobals,
          v18,
          ScoCloseCompletionRoutine,
          v15);
        if ( (*(unsigned __int8 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, _QWORD, _QWORD))(WdfFunctions_01015 + 2024))(
               WdfDriverGlobals,
               v16,
               *v5,
               0) )
        {
          v16 = 0;
          v12 = 0;
        }
        else
        {
          SetScoState(v5, 0);
          v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01015 + 2032))(
                  WdfDriverGlobals,
                  v16);
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            v9 = 0;
          }
          LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v13) = v9;
            WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
              WPP_GLOBAL_Control->AttachedDevice,
              v13,
              v14,
              WPP_GLOBAL_Control->DeviceExtension,
              2,
              5,
              52,
              (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
              v12);
          }
        }
      }
      if ( v16 )
      {
        SetScoState(v5, 0);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01015 + 1664))(
          WdfDriverGlobals,
          v16);
      }
      if ( v11 )
        (*(void (__fastcall **)(struct _BRB *, __int64, __int64))(v5[1] + 40LL))(v11, v13, v14);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140012100  push    rbx
0x140012102  push    rbp
0x140012103  push    rsi
0x140012104  push    rdi
0x140012105  push    r12
0x140012107  push    r13
0x140012109  push    r14
0x14001210b  push    r15
0x14001210d  sub     rsp, 58h
0x140012111  mov     rax, cs:WdfFunctions_01015
0x140012118  mov     r15d, edx
0x14001211b  mov     r8, cs:off_140022150
0x140012122  mov     rsi, rcx
0x140012125  mov     rdx, rcx
0x140012128  mov     rcx, cs:WdfDriverGlobals
0x14001212f  mov     rax, [rax+650h]
0x140012136  call    _guard_dispatch_icall
0x14001213b  mov     rcx, rax
0x14001213e  mov     [rsp+98h+arg_10], 0
0x14001214a  mov     rbx, rax
0x14001214d  call    ?GetScoState@@YA?AW4SCOSTATE@@PEAU_SCOCONTEXT@@@Z; GetScoState(_SCOCONTEXT *)
0x140012152  mov     edi, eax
0x140012154  mov     r10, cs:WPP_GLOBAL_Control
0x14001215b  lea     r13, WPP_GLOBAL_Control
0x140012162  mov     r14b, 1
0x140012165  cmp     r10, r13
0x140012168  jz      short loc_14001217F
0x14001216a  mov     ecx, [r10+2Ch]
0x14001216e  test    cl, 10h
0x140012171  jz      short loc_14001217F
0x140012173  cmp     byte ptr [r10+29h], 4
0x140012178  jb      short loc_14001217F
0x14001217a  mov     dl, r14b
0x14001217d  jmp     short loc_140012181
0x14001217f  xor     dl, dl
0x140012181  lea     r12, WPP_RECORDER_INITIALIZED
0x140012188  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001218f  setnz   r8b
0x140012193  test    dl, dl
0x140012195  jnz     short loc_14001219C
0x140012197  test    r8b, r8b
0x14001219a  jz      short loc_1400121B9
0x14001219c  mov     rax, [rbx+80h]
0x1400121a3  mov     r9, [r10+40h]
0x1400121a7  mov     rcx, [r10+18h]
0x1400121ab  mov     [rsp+98h+var_50], edi
0x1400121af  mov     [rsp+98h+var_58], rax
0x1400121b4  call    WPP_RECORDER_AND_TRACE_SF_qSCOSTATE
0x1400121b9  lea     eax, [rdi-4]
0x1400121bc  test    eax, 0FFFFFFFCh
0x1400121c1  jnz     loc_140012381
0x1400121c7  cmp     edi, 5
0x1400121ca  jz      loc_140012381
0x1400121d0  mov     rax, [rbx+8]
0x1400121d4  mov     ecx, 204h
0x1400121d9  mov     edx, [rbx+18h]
0x1400121dc  mov     rax, [rax+20h]
0x1400121e0  call    _guard_dispatch_icall
0x1400121e5  mov     rbp, rax
0x1400121e8  test    rax, rax
0x1400121eb  jnz     short loc_1400121F7
0x1400121ed  mov     edi, 0C000009Ah
0x1400121f2  jmp     loc_140012386
0x1400121f7  mov     rax, [rbx+80h]
0x1400121fe  mov     r9, rbp
0x140012201  mov     [rbp+78h], rax
0x140012205  xor     ecx, ecx
0x140012207  mov     rax, [rbx+10h]
0x14001220b  mov     [rbp+70h], rax
0x14001220f  lea     rax, [rsp+98h+arg_10]
0x140012217  mov     r8, [rbx+8]
0x14001221b  mov     rdx, [rbx]
0x14001221e  mov     [rsp+98h+var_78], rax
0x140012223  call    WdfIoTargetCreateAndFormatRequestForBrb
0x140012228  mov     edi, eax
0x14001222a  test    eax, eax
0x14001222c  js      loc_140012336
0x140012232  xor     ebp, ebp
0x140012234  mov     rcx, rbx
0x140012237  neg     r15d
0x14001223a  sbb     edx, edx
0x14001223c  neg     edx
0x14001223e  add     edx, 8
0x140012241  call    SetScoState
0x140012246  mov     rax, cs:WdfFunctions_01015
0x14001224d  lea     r8, ?ScoCloseCompletionRoutine@@YAXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z; ScoCloseCompletionRoutine(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)
0x140012254  mov     rcx, cs:WdfDriverGlobals
0x14001225b  mov     r9, rsi
0x14001225e  mov     rsi, [rsp+98h+arg_10]
0x140012266  mov     rdx, rsi
0x140012269  mov     rax, [rax+820h]
0x140012270  call    _guard_dispatch_icall
0x140012275  mov     rax, cs:WdfFunctions_01015
0x14001227c  xor     r9d, r9d
0x14001227f  mov     r8, [rbx]
0x140012282  mov     rdx, rsi
0x140012285  mov     rcx, cs:WdfDriverGlobals
0x14001228c  mov     rax, [rax+7E8h]
0x140012293  call    _guard_dispatch_icall
0x140012298  test    al, al
0x14001229a  jnz     loc_140012330
0x1400122a0  xor     edx, edx
0x1400122a2  mov     rcx, rbx
0x1400122a5  call    SetScoState
0x1400122aa  mov     rax, cs:WdfFunctions_01015
0x1400122b1  mov     rdx, rsi
0x1400122b4  mov     rcx, cs:WdfDriverGlobals
0x1400122bb  mov     rax, [rax+7F0h]
0x1400122c2  call    _guard_dispatch_icall
0x1400122c7  mov     edi, eax
0x1400122c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122d0  cmp     rcx, r13
0x1400122d3  jz      short loc_1400122E2
0x1400122d5  mov     eax, [rcx+2Ch]
0x1400122d8  test    al, 10h
0x1400122da  jz      short loc_1400122E2
0x1400122dc  cmp     byte ptr [rcx+29h], 2
0x1400122e0  jnb     short loc_1400122E5
0x1400122e2  xor     r14b, r14b
0x1400122e5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400122ec  setnz   r8b
0x1400122f0  test    r14b, r14b
0x1400122f3  jnz     short loc_1400122FA
0x1400122f5  test    r8b, r8b
0x1400122f8  jz      short loc_14001233E
0x1400122fa  mov     r9, [rcx+40h]
0x1400122fe  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140012305  mov     rcx, [rcx+18h]
0x140012309  mov     dl, r14b
0x14001230c  mov     dword ptr [rsp+98h+var_58], edi
0x140012310  mov     [rsp+98h+var_60], rax
0x140012315  mov     [rsp+98h+var_68], 34h ; '4'
0x14001231c  mov     [rsp+98h+var_70], 5
0x140012324  mov     byte ptr [rsp+98h+var_78], 2
0x140012329  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14001232e  jmp     short loc_14001233E
0x140012330  xor     esi, esi
0x140012332  xor     edi, edi
0x140012334  jmp     short loc_14001233E
0x140012336  mov     rsi, [rsp+98h+arg_10]
0x14001233e  test    rsi, rsi
0x140012341  jz      short loc_14001236A
0x140012343  xor     edx, edx
0x140012345  mov     rcx, rbx
0x140012348  call    SetScoState
0x14001234d  mov     rax, cs:WdfFunctions_01015
0x140012354  mov     rdx, rsi
0x140012357  mov     rcx, cs:WdfDriverGlobals
0x14001235e  mov     rax, [rax+680h]
0x140012365  call    _guard_dispatch_icall
0x14001236a  test    rbp, rbp
0x14001236d  jz      short loc_140012386
0x14001236f  mov     rax, [rbx+8]
0x140012373  mov     rcx, rbp
0x140012376  mov     rax, [rax+28h]
0x14001237a  call    _guard_dispatch_icall
0x14001237f  jmp     short loc_140012386
0x140012381  mov     edi, 0C0000010h
0x140012386  mov     eax, edi
0x140012388  add     rsp, 58h
0x14001238c  pop     r15
0x14001238e  pop     r14
0x140012390  pop     r13
0x140012392  pop     r12
0x140012394  pop     rdi
0x140012395  pop     rsi
0x140012396  pop     rbp
0x140012397  pop     rbx
0x140012398  retn
```
