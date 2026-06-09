# CreateControlDevice(_UNICODE_STRING *)

- ea: `0x140024c60`
- end: `0x140024e4d`
- name: `?CreateControlDevice@@YAJPEAU_UNICODE_STRING@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14006703c`

## callees

- `0x140001db8`
- `0x140024c60`
- `0x140024e54`
- `0x1400254b8`
- `0x140047e90`

## pseudocode

```c
__int64 __fastcall CreateControlDevice(struct _UNICODE_STRING *a1)
{
  __int64 v2; // rax
  int v3; // edx
  int v4; // r8d
  unsigned int v6; // edi
  int v7; // edx
  int v8; // ebx
  int v9; // eax
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER, const UNICODE_STRING *))(WdfFunctions_01031 + 200))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         &SDDL_DEVOBJ_KERNEL_ONLY);
  v10 = v2;
  if ( v2 )
  {
    v6 = 0;
    while ( 1 )
    {
      v8 = RtlUnicodeStringPrintf(a1, L"%s%d", L"\\Device\\mbbcx", v6);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01031 + 536))(
             WdfDriverGlobals,
             v10,
             a1);
      if ( v8 < 0 )
        break;
      ++v6;
      v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, _QWORD, PDRIVER_CONTROL *))(WdfFunctions_01031
                                                                                                + 600))(
             WdfDriverGlobals,
             &v10,
             0,
             &WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      v8 = v9;
      if ( v9 != -1073741771 )
      {
        if ( v9 >= 0 )
        {
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, PDRIVER_CONTROL))(WdfFunctions_01031 + 216))(
            WdfDriverGlobals,
            WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
          if ( v10 )
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 432))(WdfDriverGlobals);
          return 0;
        }
        break;
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        11,
        24,
        (__int64)WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids,
        v8);
    }
    if ( v10 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 432))(WdfDriverGlobals);
    return (unsigned int)v8;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_s(WPP_GLOBAL_Control->DeviceExtension, v3, v4, 23);
      v2 = v10;
    }
    if ( v2 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 432))(WdfDriverGlobals, v2);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140024c60  mov     [rsp+arg_0], rbx
0x140024c65  mov     [rsp+arg_10], rsi
0x140024c6a  push    rdi
0x140024c6b  sub     rsp, 30h
0x140024c6f  mov     rax, cs:WdfFunctions_01031
0x140024c76  lea     r8, SDDL_DEVOBJ_KERNEL_ONLY
0x140024c7d  mov     rsi, rcx
0x140024c80  mov     rcx, cs:WdfDriverGlobals
0x140024c87  mov     rax, [rax+0C8h]
0x140024c8e  mov     rdx, [rcx]
0x140024c91  call    _guard_dispatch_icall
0x140024c96  mov     [rsp+38h+arg_8], rax
0x140024c9b  test    rax, rax
0x140024c9e  jnz     short loc_140024D04
0x140024ca0  lea     rcx, WPP_RECORDER_INITIALIZED
0x140024ca7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140024cae  jz      short loc_140024CD5
0x140024cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140024cb7  lea     r9d, [rax+17h]
0x140024cbb  lea     rax, aDeviceinitGet; "deviceInit.get()"
0x140024cc2  mov     [rsp+38h+var_10], rax
0x140024cc7  mov     rcx, [rcx+40h]
0x140024ccb  call    WPP_RECORDER_SF_s
0x140024cd0  mov     rax, [rsp+38h+arg_8]
0x140024cd5  test    rax, rax
0x140024cd8  jz      short loc_140024CFA
0x140024cda  mov     rcx, cs:WdfFunctions_01031
0x140024ce1  mov     rdx, rax
0x140024ce4  mov     r8, [rcx+1B0h]
0x140024ceb  mov     rcx, cs:WdfDriverGlobals
0x140024cf2  mov     rax, r8
0x140024cf5  call    _guard_dispatch_icall
0x140024cfa  mov     eax, 0C000009Ah
0x140024cff  jmp     loc_140024E3C
0x140024d04  xor     edi, edi
0x140024d06  mov     r9d, edi
0x140024d09  lea     r8, aDeviceMbbcx; "\\Device\\mbbcx"
0x140024d10  lea     rdx, aSD; "%s%d"
0x140024d17  mov     rcx, rsi; struct _UNICODE_STRING *
0x140024d1a  call    ?RtlUnicodeStringPrintf@@YAJPEAU_UNICODE_STRING@@PEBGZZ; RtlUnicodeStringPrintf(_UNICODE_STRING *,ushort const *,...)
0x140024d1f  mov     ebx, eax
0x140024d21  test    eax, eax
0x140024d23  js      loc_140024DDA
0x140024d29  mov     rax, cs:WdfFunctions_01031
0x140024d30  mov     r8, rsi
0x140024d33  mov     rdx, [rsp+38h+arg_8]
0x140024d38  mov     rcx, cs:WdfDriverGlobals
0x140024d3f  mov     rax, [rax+218h]
0x140024d46  call    _guard_dispatch_icall
0x140024d4b  mov     ebx, eax
0x140024d4d  test    eax, eax
0x140024d4f  js      loc_140024DDA
0x140024d55  mov     rax, cs:WdfFunctions_01031
0x140024d5c  lea     r9, WPP_MAIN_CB.Queue+18h
0x140024d63  mov     rcx, cs:WdfDriverGlobals
0x140024d6a  lea     rdx, [rsp+38h+arg_8]
0x140024d6f  xor     r8d, r8d
0x140024d72  inc     edi
0x140024d74  mov     rax, [rax+258h]
0x140024d7b  call    _guard_dispatch_icall
0x140024d80  mov     ebx, eax
0x140024d82  cmp     eax, 0C0000035h
0x140024d87  jz      loc_140024D06
0x140024d8d  test    eax, eax
0x140024d8f  js      short loc_140024DDA
0x140024d91  mov     rax, cs:WdfFunctions_01031
0x140024d98  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x140024d9f  mov     rcx, cs:WdfDriverGlobals
0x140024da6  mov     rax, [rax+0D8h]
0x140024dad  call    _guard_dispatch_icall
0x140024db2  mov     rdx, [rsp+38h+arg_8]
0x140024db7  test    rdx, rdx
0x140024dba  jz      short loc_140024DD6
0x140024dbc  mov     rax, cs:WdfFunctions_01031
0x140024dc3  mov     rcx, cs:WdfDriverGlobals
0x140024dca  mov     rax, [rax+1B0h]
0x140024dd1  call    _guard_dispatch_icall
0x140024dd6  xor     eax, eax
0x140024dd8  jmp     short loc_140024E3C
0x140024dda  lea     rcx, WPP_RECORDER_INITIALIZED
0x140024de1  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140024de8  jz      short loc_140024E16
0x140024dea  mov     rcx, cs:WPP_GLOBAL_Control
0x140024df1  lea     rax, WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids
0x140024df8  mov     r9d, 18h
0x140024dfe  mov     dword ptr [rsp+38h+var_10], ebx
0x140024e02  mov     dl, 2
0x140024e04  mov     [rsp+38h+var_18], rax
0x140024e09  mov     rcx, [rcx+40h]
0x140024e0d  lea     r8d, [r9-0Dh]
0x140024e11  call    WPP_RECORDER_SF_d
0x140024e16  mov     rdx, [rsp+38h+arg_8]
0x140024e1b  test    rdx, rdx
0x140024e1e  jz      short loc_140024E3A
0x140024e20  mov     rax, cs:WdfFunctions_01031
0x140024e27  mov     rcx, cs:WdfDriverGlobals
0x140024e2e  mov     rax, [rax+1B0h]
0x140024e35  call    _guard_dispatch_icall
0x140024e3a  mov     eax, ebx
0x140024e3c  mov     rbx, [rsp+38h+arg_0]
0x140024e41  mov     rsi, [rsp+38h+arg_10]
0x140024e46  add     rsp, 30h
0x140024e4a  pop     rdi
0x140024e4b  retn
```
