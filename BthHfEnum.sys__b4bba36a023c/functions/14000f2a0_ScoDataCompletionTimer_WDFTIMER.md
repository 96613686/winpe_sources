# ScoDataCompletionTimer(WDFTIMER__ *)

- ea: `0x14000f2a0`
- end: `0x14000f399`
- name: `?ScoDataCompletionTimer@@YAXPEAUWDFTIMER__@@@Z`
- size: `249`
- prototype: `void __fastcall(struct WDFTIMER__ *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400041d0`
- `0x14000f2a0`
- `0x140010eb0`
- `0x14001ae00`

## pseudocode

```c
void __fastcall ScoDataCompletionTimer(struct WDFTIMER__ *a1)
{
  __int64 v1; // rax
  int v2; // edx
  int v3; // r8d
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rsi

  v1 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFTIMER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400221A0);
  v4 = *(_QWORD *)v1;
  v5 = *(_QWORD *)(*(_QWORD *)v1 + 56LL);
  v6 = *(_QWORD *)(*(_QWORD *)v1 + 64LL);
  LOBYTE(v2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      v3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      31,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
  }
  *(_QWORD *)(v4 + 56) = 0;
  *(_QWORD *)(v4 + 64) = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01015 + 2120))(
    WdfDriverGlobals,
    v5,
    0,
    v6);
  ScoStreamProcessDataQueue(*(struct WDFQUEUE__ **)(v4 + 24));
}

```

## disassembly

```asm
0x14000f2a0  mov     [rsp+arg_0], rbx
0x14000f2a5  mov     [rsp+arg_8], rsi
0x14000f2aa  push    rdi
0x14000f2ab  sub     rsp, 40h
0x14000f2af  mov     rax, cs:WdfFunctions_01015
0x14000f2b6  mov     rdx, rcx
0x14000f2b9  mov     r8, cs:off_1400221A0
0x14000f2c0  mov     rcx, cs:WdfDriverGlobals
0x14000f2c7  mov     rax, [rax+650h]
0x14000f2ce  call    _guard_dispatch_icall
0x14000f2d3  mov     rbx, [rax]
0x14000f2d6  mov     rdi, [rbx+38h]
0x14000f2da  mov     rsi, [rbx+40h]
0x14000f2de  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f2e5  lea     rax, WPP_GLOBAL_Control
0x14000f2ec  cmp     rcx, rax
0x14000f2ef  jz      short loc_14000F302
0x14000f2f1  mov     eax, [rcx+2Ch]
0x14000f2f4  test    al, 10h
0x14000f2f6  jz      short loc_14000F302
0x14000f2f8  cmp     byte ptr [rcx+29h], 4
0x14000f2fc  jb      short loc_14000F302
0x14000f2fe  mov     dl, 1
0x14000f300  jmp     short loc_14000F304
0x14000f302  xor     dl, dl
0x14000f304  lea     rax, WPP_RECORDER_INITIALIZED
0x14000f30b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f312  setnz   r8b
0x14000f316  test    dl, dl
0x14000f318  jnz     short loc_14000F31F
0x14000f31a  test    r8b, r8b
0x14000f31d  jz      short loc_14000F34C
0x14000f31f  mov     r9, [rcx+40h]
0x14000f323  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000f32a  mov     rcx, [rcx+18h]
0x14000f32e  mov     [rsp+48h+var_10], rax
0x14000f333  mov     [rsp+48h+var_18], 1Fh
0x14000f33a  mov     [rsp+48h+var_20], 5
0x14000f342  mov     [rsp+48h+var_28], 4
0x14000f347  call    WPP_RECORDER_AND_TRACE_SF_
0x14000f34c  mov     qword ptr [rbx+38h], 0
0x14000f354  mov     r9, rsi
0x14000f357  mov     qword ptr [rbx+40h], 0
0x14000f35f  xor     r8d, r8d
0x14000f362  mov     rax, cs:WdfFunctions_01015
0x14000f369  mov     rdx, rdi
0x14000f36c  mov     rcx, cs:WdfDriverGlobals
0x14000f373  mov     rax, [rax+848h]
0x14000f37a  call    _guard_dispatch_icall
0x14000f37f  mov     rcx, [rbx+18h]; struct WDFQUEUE__ *
0x14000f383  call    ?ScoStreamProcessDataQueue@@YAXPEAUWDFQUEUE__@@@Z; ScoStreamProcessDataQueue(WDFQUEUE__ *)
0x14000f388  mov     rbx, [rsp+48h+arg_0]
0x14000f38d  mov     rsi, [rsp+48h+arg_8]
0x14000f392  add     rsp, 40h
0x14000f396  pop     rdi
0x14000f397  retn
```
