# BypassIoctlGetNrecDisableStatusUpdate

- ea: `0x1400083b8`
- end: `0x1400084dc`
- name: `BypassIoctlGetNrecDisableStatusUpdate`
- size: `292`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x1400083b8`
- `0x14000b0ac`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall BypassIoctlGetNrecDisableStatusUpdate(__int64 a1, __int64 a2)
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
      39,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
  }
  return WdfRequestCompleteOrForwardStatusIoctlRequest(
           a2,
           *(_QWORD *)(v3 + 152),
           0x22003Bu,
           (_DWORD *)(v3 + 284),
           (_DWORD *)(v6 + 4));
}

```

## disassembly

```asm
0x1400083b8  mov     [rsp+arg_0], rbx
0x1400083bd  mov     [rsp+arg_8], rsi
0x1400083c2  push    rdi
0x1400083c3  sub     rsp, 40h
0x1400083c7  mov     rax, cs:WdfFunctions_01015
0x1400083ce  mov     rdi, rdx
0x1400083d1  mov     r8, cs:off_1400220B0
0x1400083d8  mov     rdx, rcx
0x1400083db  mov     rcx, cs:WdfDriverGlobals
0x1400083e2  mov     rax, [rax+650h]
0x1400083e9  call    _guard_dispatch_icall
0x1400083ee  mov     rcx, cs:WdfFunctions_01015
0x1400083f5  mov     rbx, rax
0x1400083f8  mov     rdx, rdi
0x1400083fb  mov     rax, [rcx+8A8h]
0x140008402  mov     rcx, cs:WdfDriverGlobals
0x140008409  call    _guard_dispatch_icall
0x14000840e  mov     rcx, cs:WdfFunctions_01015
0x140008415  mov     rdx, rax
0x140008418  mov     r8, cs:off_140022100
0x14000841f  mov     rax, [rcx+650h]
0x140008426  mov     rcx, cs:WdfDriverGlobals
0x14000842d  call    _guard_dispatch_icall
0x140008432  mov     rsi, rax
0x140008435  mov     r10, cs:WPP_GLOBAL_Control
0x14000843c  lea     rax, WPP_GLOBAL_Control
0x140008443  cmp     r10, rax
0x140008446  jz      short loc_14000845C
0x140008448  mov     ecx, [r10+2Ch]
0x14000844c  test    cl, 1
0x14000844f  jz      short loc_14000845C
0x140008451  cmp     byte ptr [r10+29h], 4
0x140008456  jb      short loc_14000845C
0x140008458  mov     dl, 1
0x14000845a  jmp     short loc_14000845E
0x14000845c  xor     dl, dl
0x14000845e  lea     rax, WPP_RECORDER_INITIALIZED
0x140008465  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000846c  setnz   r8b
0x140008470  test    dl, dl
0x140008472  jnz     short loc_140008479
0x140008474  test    r8b, r8b
0x140008477  jz      short loc_1400084A6
0x140008479  mov     r9, [r10+40h]
0x14000847d  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140008484  mov     rcx, [r10+18h]
0x140008488  mov     [rsp+48h+var_10], rax
0x14000848d  mov     [rsp+48h+var_18], 27h ; '''
0x140008494  mov     [rsp+48h+var_20], 1
0x14000849c  mov     byte ptr [rsp+48h+var_28], 4
0x1400084a1  call    WPP_RECORDER_AND_TRACE_SF_
0x1400084a6  mov     rdx, [rbx+98h]
0x1400084ad  lea     rax, [rsi+4]
0x1400084b1  lea     r9, [rbx+11Ch]
0x1400084b8  mov     [rsp+48h+var_28], rax
0x1400084bd  mov     r8d, 22003Bh
0x1400084c3  mov     rcx, rdi
0x1400084c6  call    WdfRequestCompleteOrForwardStatusIoctlRequest
0x1400084cb  mov     rbx, [rsp+48h+arg_0]
0x1400084d0  mov     rsi, [rsp+48h+arg_8]
0x1400084d5  add     rsp, 40h
0x1400084d9  pop     rdi
0x1400084da  retn
```
