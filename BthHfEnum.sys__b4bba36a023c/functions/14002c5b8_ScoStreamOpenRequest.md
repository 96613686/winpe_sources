# ScoStreamOpenRequest

- ea: `0x14002c5b8`
- end: `0x14002c775`
- name: `ScoStreamOpenRequest`
- size: `445`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140009750`

## callees

- `0x1400041d0`
- `0x14001117c`
- `0x14001269c`
- `0x14001a258`
- `0x14001ae00`
- `0x14002c5b8`

## string_xrefs

- `0x14002c677`: `Received Sco stream open request while already streaming`

## pseudocode

```c
__int64 __fastcall ScoStreamOpenRequest(__int64 a1, __int64 a2)
{
  char v4; // di
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int64 v7; // r8
  __int32 v8; // esi
  int v9; // edx
  __int64 *v10; // r8
  __int64 result; // rax
  unsigned int v12; // edx
  __int64 v13; // rax
  __int64 v14; // rcx

  v4 = 1;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_140022150);
  v8 = _InterlockedExchange((volatile __int32 *)(v6 + 108), 1);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(v5) = 0;
  }
  LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      v7,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      74,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
  if ( v8 )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("Received Sco stream open request while already streaming", v5, v7);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v9) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      v4 = 0;
    if ( (_BYTE)v9 || v4 )
    {
      v10 = WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids;
      LOBYTE(v10) = v4;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        (_DWORD)v10,
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        5,
        75,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
    }
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
             WdfDriverGlobals,
             a2,
             3221225488LL);
  }
  else
  {
    v12 = 0;
    do
    {
      v13 = (int)v12++;
      v14 = 10 * v13;
      *(_QWORD *)(v6 + 8 * v14 + 144) = 0;
      *(_QWORD *)(v6 + 8 * v14 + 152) = 0;
      *(_QWORD *)(v6 + 8 * v14 + 168) = 0;
    }
    while ( v12 < 2 );
    *(_QWORD *)(v6 + 120) = 0;
    result = ScoConnectionRequest(a1, a2);
    if ( (int)result < 0 )
    {
      *(_DWORD *)(v6 + 108) = 0;
      return ScoUpdateAvdtpSuspension(v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002c5b8  push    rbx
0x14002c5ba  push    rbp
0x14002c5bb  push    rsi
0x14002c5bc  push    rdi
0x14002c5bd  push    r13
0x14002c5bf  push    r14
0x14002c5c1  push    r15
0x14002c5c3  sub     rsp, 40h
0x14002c5c7  mov     rax, cs:WdfFunctions_01015
0x14002c5ce  mov     rbp, rdx
0x14002c5d1  mov     r8, cs:off_140022150
0x14002c5d8  mov     r14, rcx
0x14002c5db  mov     rdx, rcx
0x14002c5de  mov     rcx, cs:WdfDriverGlobals
0x14002c5e5  mov     rax, [rax+650h]
0x14002c5ec  call    _guard_dispatch_icall
0x14002c5f1  mov     edi, 1
0x14002c5f6  mov     rbx, rax
0x14002c5f9  mov     esi, edi
0x14002c5fb  xchg    esi, [rax+6Ch]
0x14002c5fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c605  lea     rax, WPP_GLOBAL_Control
0x14002c60c  xor     r15d, r15d
0x14002c60f  cmp     rcx, rax
0x14002c612  jz      short loc_14002C624
0x14002c614  mov     eax, [rcx+2Ch]
0x14002c617  test    al, 10h
0x14002c619  jz      short loc_14002C624
0x14002c61b  cmp     byte ptr [rcx+29h], 4
0x14002c61f  mov     dl, dil
0x14002c622  jnb     short loc_14002C627
0x14002c624  mov     dl, r15b
0x14002c627  lea     r13, WPP_RECORDER_INITIALIZED
0x14002c62e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14002c635  lea     r9, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14002c63c  setnz   r8b
0x14002c640  test    dl, dl
0x14002c642  jnz     short loc_14002C649
0x14002c644  test    r8b, r8b
0x14002c647  jz      short loc_14002C66F
0x14002c649  mov     [rsp+78h+var_40], r9
0x14002c64e  mov     r9, [rcx+40h]
0x14002c652  mov     rcx, [rcx+18h]
0x14002c656  mov     [rsp+78h+var_48], 4Ah ; 'J'
0x14002c65d  mov     [rsp+78h+var_50], 5
0x14002c665  mov     [rsp+78h+var_58], 4
0x14002c66a  call    WPP_RECORDER_AND_TRACE_SF_
0x14002c66f  test    esi, esi
0x14002c671  jz      loc_14002C71A
0x14002c677  lea     rcx, aReceivedScoStr; "Received Sco stream open request while "...
0x14002c67e  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002c683  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c68a  lea     rax, WPP_GLOBAL_Control
0x14002c691  cmp     rcx, rax
0x14002c694  jz      short loc_14002C6A6
0x14002c696  mov     eax, [rcx+2Ch]
0x14002c699  test    al, 10h
0x14002c69b  jz      short loc_14002C6A6
0x14002c69d  cmp     byte ptr [rcx+29h], 5
0x14002c6a1  mov     dl, dil
0x14002c6a4  jnb     short loc_14002C6A9
0x14002c6a6  mov     dl, r15b
0x14002c6a9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14002c6b0  jz      short loc_14002C6B9
0x14002c6b2  cmp     [rcx+48h], r15w
0x14002c6b7  jnz     short loc_14002C6BC
0x14002c6b9  mov     dil, r15b
0x14002c6bc  test    dl, dl
0x14002c6be  jnz     short loc_14002C6C5
0x14002c6c0  test    dil, dil
0x14002c6c3  jz      short loc_14002C6F5
0x14002c6c5  mov     r9, [rcx+40h]
0x14002c6c9  lea     r8, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14002c6d0  mov     rcx, [rcx+18h]
0x14002c6d4  mov     [rsp+78h+var_40], r8
0x14002c6d9  mov     r8b, dil
0x14002c6dc  mov     [rsp+78h+var_48], 4Bh ; 'K'
0x14002c6e3  mov     [rsp+78h+var_50], 5
0x14002c6eb  mov     [rsp+78h+var_58], 5
0x14002c6f0  call    WPP_RECORDER_AND_TRACE_SF_
0x14002c6f5  mov     rax, cs:WdfFunctions_01015
0x14002c6fc  mov     r8d, 0C0000010h
0x14002c702  mov     rcx, cs:WdfDriverGlobals
0x14002c709  mov     rdx, rbp
0x14002c70c  mov     rax, [rax+838h]
0x14002c713  call    _guard_dispatch_icall
0x14002c718  jmp     short loc_14002C765
0x14002c71a  mov     edx, r15d
0x14002c71d  movsxd  rax, edx
0x14002c720  add     edx, edi
0x14002c722  lea     rcx, [rax+rax*4]
0x14002c726  add     rcx, rcx
0x14002c729  mov     [rbx+rcx*8+90h], r15
0x14002c731  mov     [rbx+rcx*8+98h], r15
0x14002c739  mov     [rbx+rcx*8+0A8h], r15
0x14002c741  cmp     edx, 2
0x14002c744  jb      short loc_14002C71D
0x14002c746  mov     rdx, rbp
0x14002c749  mov     [rbx+78h], r15
0x14002c74d  mov     rcx, r14
0x14002c750  call    ScoConnectionRequest
0x14002c755  test    eax, eax
0x14002c757  jns     short loc_14002C765
0x14002c759  mov     rcx, rbx
0x14002c75c  mov     [rbx+6Ch], r15d
0x14002c760  call    ScoUpdateAvdtpSuspension
0x14002c765  add     rsp, 40h
0x14002c769  pop     r15
0x14002c76b  pop     r14
0x14002c76d  pop     r13
0x14002c76f  pop     rdi
0x14002c770  pop     rsi
0x14002c771  pop     rbp
0x14002c772  pop     rbx
0x14002c773  retn
```
