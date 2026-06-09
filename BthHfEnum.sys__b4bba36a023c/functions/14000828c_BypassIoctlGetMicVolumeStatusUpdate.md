# BypassIoctlGetMicVolumeStatusUpdate

- ea: `0x14000828c`
- end: `0x1400083b0`
- name: `BypassIoctlGetMicVolumeStatusUpdate`
- size: `292`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x14000828c`
- `0x14000b0ac`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall BypassIoctlGetMicVolumeStatusUpdate(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rsi
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
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      v7,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      44,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
  }
  return WdfRequestCompleteOrForwardStatusIoctlRequest(
           a2,
           *(_QWORD *)(v3 + 152),
           0x220027u,
           (_DWORD *)(v3 + 280),
           (_DWORD *)(v6 + 12));
}

```

## disassembly

```asm
0x14000828c  mov     [rsp+arg_0], rbx
0x140008291  mov     [rsp+arg_8], rsi
0x140008296  push    rdi
0x140008297  sub     rsp, 40h
0x14000829b  mov     rax, cs:WdfFunctions_01015
0x1400082a2  mov     rdi, rdx
0x1400082a5  mov     r8, cs:off_1400220B0
0x1400082ac  mov     rdx, rcx
0x1400082af  mov     rcx, cs:WdfDriverGlobals
0x1400082b6  mov     rax, [rax+650h]
0x1400082bd  call    _guard_dispatch_icall
0x1400082c2  mov     rcx, cs:WdfFunctions_01015
0x1400082c9  mov     rbx, rax
0x1400082cc  mov     rdx, rdi
0x1400082cf  mov     rax, [rcx+8A8h]
0x1400082d6  mov     rcx, cs:WdfDriverGlobals
0x1400082dd  call    _guard_dispatch_icall
0x1400082e2  mov     rcx, cs:WdfFunctions_01015
0x1400082e9  mov     rdx, rax
0x1400082ec  mov     r8, cs:off_140022100
0x1400082f3  mov     rax, [rcx+650h]
0x1400082fa  mov     rcx, cs:WdfDriverGlobals
0x140008301  call    _guard_dispatch_icall
0x140008306  mov     rsi, rax
0x140008309  mov     r10, cs:WPP_GLOBAL_Control
0x140008310  lea     rax, WPP_GLOBAL_Control
0x140008317  cmp     r10, rax
0x14000831a  jz      short loc_140008330
0x14000831c  mov     ecx, [r10+2Ch]
0x140008320  test    cl, 1
0x140008323  jz      short loc_140008330
0x140008325  cmp     byte ptr [r10+29h], 4
0x14000832a  jb      short loc_140008330
0x14000832c  mov     dl, 1
0x14000832e  jmp     short loc_140008332
0x140008330  xor     dl, dl
0x140008332  lea     rax, WPP_RECORDER_INITIALIZED
0x140008339  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008340  setnz   r8b
0x140008344  test    dl, dl
0x140008346  jnz     short loc_14000834D
0x140008348  test    r8b, r8b
0x14000834b  jz      short loc_14000837A
0x14000834d  mov     r9, [r10+40h]
0x140008351  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140008358  mov     rcx, [r10+18h]
0x14000835c  mov     [rsp+48h+var_10], rax
0x140008361  mov     [rsp+48h+var_18], 2Ch ; ','
0x140008368  mov     [rsp+48h+var_20], 1
0x140008370  mov     byte ptr [rsp+48h+var_28], 4
0x140008375  call    WPP_RECORDER_AND_TRACE_SF_
0x14000837a  mov     rdx, [rbx+98h]
0x140008381  lea     rax, [rsi+0Ch]
0x140008385  lea     r9, [rbx+118h]
0x14000838c  mov     [rsp+48h+var_28], rax
0x140008391  mov     r8d, 220027h
0x140008397  mov     rcx, rdi
0x14000839a  call    WdfRequestCompleteOrForwardStatusIoctlRequest
0x14000839f  mov     rbx, [rsp+48h+arg_0]
0x1400083a4  mov     rsi, [rsp+48h+arg_8]
0x1400083a9  add     rsp, 40h
0x1400083ad  pop     rdi
0x1400083ae  retn
```
