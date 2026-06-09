# ScoStreamProcessDataQueue(WDFQUEUE__ *)

- ea: `0x140010eb0`
- end: `0x1400110b3`
- name: `?ScoStreamProcessDataQueue@@YAXPEAUWDFQUEUE__@@@Z`
- size: `515`
- prototype: `void __fastcall(struct WDFQUEUE__ *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000d090`
- `0x14000f2a0`
- `0x1400114c8`

## callees

- `0x14000e248`
- `0x140010c80`
- `0x140010eb0`
- `0x140014d20`
- `0x14001ae00`
- `0x14002ea08`

## pseudocode

```c
void __fastcall ScoStreamProcessDataQueue(struct WDFQUEUE__ *a1)
{
  __int64 v2; // rax
  __int64 v3; // rsi
  __int64 v4; // rdi
  bool v5; // bp
  bool v6; // r14
  int v7; // r8d
  int v8; // edx
  struct WDFREQUEST__ *v9; // [rsp+A8h] [rbp+10h] BYREF

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFQUEUE__ *))(WdfFunctions_01015 + 1256))(
         WdfDriverGlobals,
         a1);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v2,
         off_140022150);
  v4 = *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFQUEUE__ *, __int64 *))(WdfFunctions_01015
                                                                                                 + 1616))(
                    WdfDriverGlobals,
                    a1,
                    off_1400221A0);
  v9 = 0;
  v5 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 112))(
      WdfDriverGlobals,
      *(_QWORD *)(v4 + 48));
    LOBYTE(v7) = v6;
    LOBYTE(v8) = v5;
    WPP_RECORDER_AND_TRACE_SF_SCOSTATEdq(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v7,
      WPP_GLOBAL_Control->DeviceExtension);
  }
  while ( *(_DWORD *)(v3 + 376) == 7
       && !*(_QWORD *)(v4 + 56)
       && (unsigned __int8)AudioQueue_IsReadyToProcessNextRequest(a1)
       && (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFQUEUE__ *, struct WDFREQUEST__ **))(WdfFunctions_01015
                                                                                                  + 1264))(
            WdfDriverGlobals,
            a1,
            &v9) >= 0
       && v9 )
    ScoChannelTransfer((struct _SCO_TRANSFER_CONTEXT *)v4, v9);
  while ( *(_DWORD *)(v3 + 376) != 7
       && !(*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 112))(
             WdfDriverGlobals,
             *(_QWORD *)(v4 + 48))
       && !*(_QWORD *)(v4 + 56)
       && (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFQUEUE__ *, struct WDFREQUEST__ **))(WdfFunctions_01015
                                                                                                  + 1264))(
            WdfDriverGlobals,
            a1,
            &v9) >= 0
       && v9 )
    ScoSimulatedTransfer((struct _SCO_TRANSFER_CONTEXT *)v4, v9);
}

```

## disassembly

```asm
0x140010eb0  push    rbx
0x140010eb2  push    rbp
0x140010eb3  push    rsi
0x140010eb4  push    rdi
0x140010eb5  push    r14
0x140010eb7  push    r15
0x140010eb9  sub     rsp, 68h
0x140010ebd  mov     rax, cs:WdfFunctions_01015
0x140010ec4  mov     r15, rcx
0x140010ec7  mov     rdx, rcx
0x140010eca  mov     rcx, cs:WdfDriverGlobals
0x140010ed1  mov     rax, [rax+4E8h]
0x140010ed8  call    _guard_dispatch_icall
0x140010edd  mov     rdx, cs:WdfFunctions_01015
0x140010ee4  mov     r9, rax
0x140010ee7  mov     r8, cs:off_140022150
0x140010eee  mov     rcx, cs:WdfDriverGlobals
0x140010ef5  mov     rax, [rdx+650h]
0x140010efc  mov     rdx, r9
0x140010eff  call    _guard_dispatch_icall
0x140010f04  mov     rcx, cs:WdfFunctions_01015
0x140010f0b  mov     rsi, rax
0x140010f0e  mov     r8, cs:off_1400221A0
0x140010f15  mov     rdx, r15
0x140010f18  mov     rax, [rcx+650h]
0x140010f1f  mov     rcx, cs:WdfDriverGlobals
0x140010f26  call    _guard_dispatch_icall
0x140010f2b  mov     rdi, [rax]
0x140010f2e  mov     [rsp+98h+arg_8], 0
0x140010f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f41  lea     rax, WPP_GLOBAL_Control
0x140010f48  cmp     rcx, rax
0x140010f4b  jz      short loc_140010F5F
0x140010f4d  mov     eax, [rcx+2Ch]
0x140010f50  test    al, 10h
0x140010f52  jz      short loc_140010F5F
0x140010f54  cmp     byte ptr [rcx+29h], 4
0x140010f58  jb      short loc_140010F5F
0x140010f5a  mov     bpl, 1
0x140010f5d  jmp     short loc_140010F62
0x140010f5f  xor     bpl, bpl
0x140010f62  lea     rax, WPP_RECORDER_INITIALIZED
0x140010f69  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010f70  setnz   r14b
0x140010f74  test    bpl, bpl
0x140010f77  jnz     short loc_140010F82
0x140010f79  test    r14b, r14b
0x140010f7c  jz      loc_14001102D
0x140010f82  mov     rax, cs:WdfFunctions_01015
0x140010f89  mov     rdx, [rdi+30h]
0x140010f8d  mov     rcx, cs:WdfDriverGlobals
0x140010f94  mov     rbx, [rdi+38h]
0x140010f98  mov     rax, [rax+70h]
0x140010f9c  call    _guard_dispatch_icall
0x140010fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140010fa8  mov     r8b, r14b
0x140010fab  mov     [rsp+98h+var_48], rbx
0x140010fb0  mov     dl, bpl
0x140010fb3  mov     [rsp+98h+var_50], eax
0x140010fb7  mov     eax, [rsi+178h]
0x140010fbd  mov     r9, [rcx+40h]
0x140010fc1  mov     rcx, [rcx+18h]
0x140010fc5  mov     [rsp+98h+var_58], eax
0x140010fc9  call    WPP_RECORDER_AND_TRACE_SF_SCOSTATEdq
0x140010fce  jmp     short loc_14001102D
0x140010fd0  cmp     qword ptr [rdi+38h], 0
0x140010fd5  jnz     loc_14001109C
0x140010fdb  mov     rcx, r15
0x140010fde  call    AudioQueue_IsReadyToProcessNextRequest
0x140010fe3  test    al, al
0x140010fe5  jz      loc_14001109C
0x140010feb  mov     rax, cs:WdfFunctions_01015
0x140010ff2  lea     r8, [rsp+98h+arg_8]
0x140010ffa  mov     rcx, cs:WdfDriverGlobals
0x140011001  mov     rdx, r15
0x140011004  mov     rax, [rax+4F0h]
0x14001100b  call    _guard_dispatch_icall
0x140011010  test    eax, eax
0x140011012  js      loc_14001109C
0x140011018  mov     rdx, [rsp+98h+arg_8]; struct WDFREQUEST__ *
0x140011020  test    rdx, rdx
0x140011023  jz      short loc_14001109C
0x140011025  mov     rcx, rdi; struct _SCO_TRANSFER_CONTEXT *
0x140011028  call    ?ScoChannelTransfer@@YAXPEAU_SCO_TRANSFER_CONTEXT@@PEAUWDFREQUEST__@@@Z; ScoChannelTransfer(_SCO_TRANSFER_CONTEXT *,WDFREQUEST__ *)
0x14001102d  cmp     dword ptr [rsi+178h], 7
0x140011034  jz      short loc_140010FD0
0x140011036  jmp     short loc_14001109C
0x140011038  mov     rax, cs:WdfFunctions_01015
0x14001103f  mov     rdx, [rdi+30h]
0x140011043  mov     rcx, cs:WdfDriverGlobals
0x14001104a  mov     rax, [rax+70h]
0x14001104e  call    _guard_dispatch_icall
0x140011053  test    eax, eax
0x140011055  jnz     short loc_1400110A5
0x140011057  cmp     qword ptr [rdi+38h], 0
0x14001105c  jnz     short loc_1400110A5
0x14001105e  mov     rax, cs:WdfFunctions_01015
0x140011065  lea     r8, [rsp+98h+arg_8]
0x14001106d  mov     rcx, cs:WdfDriverGlobals
0x140011074  mov     rdx, r15
0x140011077  mov     rax, [rax+4F0h]
0x14001107e  call    _guard_dispatch_icall
0x140011083  test    eax, eax
0x140011085  js      short loc_1400110A5
0x140011087  mov     rdx, [rsp+98h+arg_8]; struct WDFREQUEST__ *
0x14001108f  test    rdx, rdx
0x140011092  jz      short loc_1400110A5
0x140011094  mov     rcx, rdi; struct _SCO_TRANSFER_CONTEXT *
0x140011097  call    ?ScoSimulatedTransfer@@YAJPEAU_SCO_TRANSFER_CONTEXT@@PEAUWDFREQUEST__@@@Z; ScoSimulatedTransfer(_SCO_TRANSFER_CONTEXT *,WDFREQUEST__ *)
0x14001109c  cmp     dword ptr [rsi+178h], 7
0x1400110a3  jnz     short loc_140011038
0x1400110a5  add     rsp, 68h
0x1400110a9  pop     r15
0x1400110ab  pop     r14
0x1400110ad  pop     rdi
0x1400110ae  pop     rsi
0x1400110af  pop     rbp
0x1400110b0  pop     rbx
0x1400110b1  retn
```
