# BypassIoctlGetConnectionStatusUpdate

- ea: `0x140007b28`
- end: `0x140007c62`
- name: `BypassIoctlGetConnectionStatusUpdate`
- size: `314`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x140007b28`
- `0x14000b0ac`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall BypassIoctlGetConnectionStatusUpdate(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  int v5; // edx
  _DWORD *v6; // rsi
  int v7; // r8d
  BOOL v9; // [rsp+60h] [rbp+18h] BYREF

  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2216))(WdfDriverGlobals, a2);
  v6 = (_DWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                   WdfDriverGlobals,
                   v4,
                   off_140022100);
  v9 = 0;
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
      38,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
  }
  v9 = (unsigned int)(*(_DWORD *)(v3 + 208) - 1) <= 1;
  return WdfRequestCompleteOrForwardStatusIoctlRequest(a2, *(_QWORD *)(v3 + 152), 0x220017u, &v9, v6);
}

```

## disassembly

```asm
0x140007b28  mov     [rsp+arg_0], rbx
0x140007b2d  mov     [rsp+arg_8], rsi
0x140007b32  push    rdi
0x140007b33  sub     rsp, 40h
0x140007b37  mov     rax, cs:WdfFunctions_01015
0x140007b3e  mov     rdi, rdx
0x140007b41  mov     r8, cs:off_1400220B0
0x140007b48  mov     rdx, rcx
0x140007b4b  mov     rcx, cs:WdfDriverGlobals
0x140007b52  mov     rax, [rax+650h]
0x140007b59  call    _guard_dispatch_icall
0x140007b5e  mov     rcx, cs:WdfFunctions_01015
0x140007b65  mov     rbx, rax
0x140007b68  mov     rdx, rdi
0x140007b6b  mov     rax, [rcx+8A8h]
0x140007b72  mov     rcx, cs:WdfDriverGlobals
0x140007b79  call    _guard_dispatch_icall
0x140007b7e  mov     rcx, cs:WdfFunctions_01015
0x140007b85  mov     rdx, rax
0x140007b88  mov     r8, cs:off_140022100
0x140007b8f  mov     rax, [rcx+650h]
0x140007b96  mov     rcx, cs:WdfDriverGlobals
0x140007b9d  call    _guard_dispatch_icall
0x140007ba2  mov     rsi, rax
0x140007ba5  mov     [rsp+48h+arg_10], 0
0x140007bad  mov     r10, cs:WPP_GLOBAL_Control
0x140007bb4  lea     rax, WPP_GLOBAL_Control
0x140007bbb  cmp     r10, rax
0x140007bbe  jz      short loc_140007BD4
0x140007bc0  mov     ecx, [r10+2Ch]
0x140007bc4  test    cl, 1
0x140007bc7  jz      short loc_140007BD4
0x140007bc9  cmp     byte ptr [r10+29h], 4
0x140007bce  jb      short loc_140007BD4
0x140007bd0  mov     dl, 1
0x140007bd2  jmp     short loc_140007BD6
0x140007bd4  xor     dl, dl
0x140007bd6  lea     rax, WPP_RECORDER_INITIALIZED
0x140007bdd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007be4  setnz   r8b
0x140007be8  test    dl, dl
0x140007bea  jnz     short loc_140007BF1
0x140007bec  test    r8b, r8b
0x140007bef  jz      short loc_140007C1E
0x140007bf1  mov     r9, [r10+40h]
0x140007bf5  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140007bfc  mov     rcx, [r10+18h]
0x140007c00  mov     [rsp+48h+var_10], rax
0x140007c05  mov     [rsp+48h+var_18], 26h ; '&'
0x140007c0c  mov     [rsp+48h+var_20], 1
0x140007c14  mov     byte ptr [rsp+48h+var_28], 4
0x140007c19  call    WPP_RECORDER_AND_TRACE_SF_
0x140007c1e  mov     eax, [rbx+0D0h]
0x140007c24  lea     r9, [rsp+48h+arg_10]
0x140007c29  xor     ecx, ecx
0x140007c2b  mov     [rsp+48h+var_28], rsi
0x140007c30  dec     eax
0x140007c32  mov     r8d, 220017h
0x140007c38  cmp     eax, 1
0x140007c3b  setbe   cl
0x140007c3e  mov     [rsp+48h+arg_10], ecx
0x140007c42  mov     rcx, rdi
0x140007c45  mov     rdx, [rbx+98h]
0x140007c4c  call    WdfRequestCompleteOrForwardStatusIoctlRequest
0x140007c51  mov     rbx, [rsp+48h+arg_0]
0x140007c56  mov     rsi, [rsp+48h+arg_8]
0x140007c5b  add     rsp, 40h
0x140007c5f  pop     rdi
0x140007c60  retn
```
