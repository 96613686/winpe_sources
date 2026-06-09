# BypassIoctlGetSpeakerVolumeStatusUpdate

- ea: `0x1400084e4`
- end: `0x140008619`
- name: `BypassIoctlGetSpeakerVolumeStatusUpdate`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140029170`

## callees

- `0x1400084e4`
- `0x14000a594`
- `0x14000b0ac`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall BypassIoctlGetSpeakerVolumeStatusUpdate(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rdi
  int v7; // r8d

  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2216))(WdfDriverGlobals, a2);
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v4,
         off_140022100);
  LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      v7,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      43,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
      *(_DWORD *)(v6 + 8),
      *(_DWORD *)(v3 + 276));
  }
  return WdfRequestCompleteOrForwardStatusIoctlRequest(
           a2,
           *(_QWORD *)(v3 + 152),
           0x22001Fu,
           (_DWORD *)(v3 + 276),
           (_DWORD *)(v6 + 8));
}

```

## disassembly

```asm
0x1400084e4  mov     [rsp+arg_0], rbx
0x1400084e9  mov     [rsp+arg_8], rsi
0x1400084ee  push    rdi
0x1400084ef  sub     rsp, 50h
0x1400084f3  mov     rax, cs:WdfFunctions_01015
0x1400084fa  mov     rsi, rdx
0x1400084fd  mov     r8, cs:off_1400220B0
0x140008504  mov     rdx, rcx
0x140008507  mov     rcx, cs:WdfDriverGlobals
0x14000850e  mov     rax, [rax+650h]
0x140008515  call    _guard_dispatch_icall
0x14000851a  mov     rcx, cs:WdfFunctions_01015
0x140008521  mov     rbx, rax
0x140008524  mov     rdx, rsi
0x140008527  mov     rax, [rcx+8A8h]
0x14000852e  mov     rcx, cs:WdfDriverGlobals
0x140008535  call    _guard_dispatch_icall
0x14000853a  mov     rcx, cs:WdfFunctions_01015
0x140008541  mov     rdx, rax
0x140008544  mov     r8, cs:off_140022100
0x14000854b  mov     rax, [rcx+650h]
0x140008552  mov     rcx, cs:WdfDriverGlobals
0x140008559  call    _guard_dispatch_icall
0x14000855e  mov     rdi, rax
0x140008561  mov     r10, cs:WPP_GLOBAL_Control
0x140008568  lea     rax, WPP_GLOBAL_Control
0x14000856f  cmp     r10, rax
0x140008572  jz      short loc_140008588
0x140008574  mov     ecx, [r10+2Ch]
0x140008578  test    cl, 1
0x14000857b  jz      short loc_140008588
0x14000857d  cmp     byte ptr [r10+29h], 4
0x140008582  jb      short loc_140008588
0x140008584  mov     dl, 1
0x140008586  jmp     short loc_14000858A
0x140008588  xor     dl, dl
0x14000858a  lea     rax, WPP_RECORDER_INITIALIZED
0x140008591  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008598  setnz   r8b
0x14000859c  test    dl, dl
0x14000859e  jnz     short loc_1400085A5
0x1400085a0  test    r8b, r8b
0x1400085a3  jz      short loc_1400085E3
0x1400085a5  mov     eax, [rbx+114h]
0x1400085ab  mov     r9, [r10+40h]
0x1400085af  mov     rcx, [r10+18h]
0x1400085b3  mov     [rsp+58h+var_10], eax
0x1400085b7  mov     eax, [rdi+8]
0x1400085ba  mov     [rsp+58h+var_18], eax
0x1400085be  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x1400085c5  mov     [rsp+58h+var_20], rax
0x1400085ca  mov     [rsp+58h+var_28], 2Bh ; '+'
0x1400085d1  mov     [rsp+58h+var_30], 1
0x1400085d9  mov     byte ptr [rsp+58h+var_38], 4
0x1400085de  call    WPP_RECORDER_AND_TRACE_SF_dd
0x1400085e3  mov     rdx, [rbx+98h]
0x1400085ea  lea     rax, [rdi+8]
0x1400085ee  lea     r9, [rbx+114h]
0x1400085f5  mov     [rsp+58h+var_38], rax
0x1400085fa  mov     r8d, 22001Fh
0x140008600  mov     rcx, rsi
0x140008603  call    WdfRequestCompleteOrForwardStatusIoctlRequest
0x140008608  mov     rbx, [rsp+58h+arg_0]
0x14000860d  mov     rsi, [rsp+58h+arg_8]
0x140008612  add     rsp, 50h
0x140008616  pop     rdi
0x140008617  retn
```
