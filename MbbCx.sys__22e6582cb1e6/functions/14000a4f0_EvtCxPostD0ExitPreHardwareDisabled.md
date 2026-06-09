# EvtCxPostD0ExitPreHardwareDisabled

- ea: `0x14000a4f0`
- end: `0x14000a5fe`
- name: `EvtCxPostD0ExitPreHardwareDisabled`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001cf8`
- `0x14000a4f0`
- `0x14000df54`
- `0x14000e3b4`
- `0x14000f478`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14000a5d6`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14000a5d6`
- `ntoskrnl!ExRundownCompleted` at `0x14000a5e6`
- `ntoskrnl!ExRundownCompleted` at `0x14000a5e6`

## pseudocode

```c
__int64 __fastcall EvtCxPostD0ExitPreHardwareDisabled(__int64 a1)
{
  int v1; // edx
  __int64 v2; // rbx
  int v3; // r8d
  int v4; // r9d

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14005DF70);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dc(WPP_GLOBAL_Control->DeviceExtension, v1, v3, v4);
  _InterlockedAdd((volatile signed __int32 *)(v2 + 1708), _InterlockedExchange((volatile __int32 *)(v2 + 1720), 0));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_l(WPP_GLOBAL_Control->DeviceExtension, v1, v3, 127);
  if ( !*(_BYTE *)(v2 + 1554) )
  {
    *(_BYTE *)(v2 + 1552) = 0;
    MbbClose((PKSPIN_LOCK)(v2 + 64));
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v1) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v1,
      8,
      133,
      (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids);
  }
  *(_BYTE *)(v2 + 1556) = 0;
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v2 + 88));
  ExRundownCompleted((PEX_RUNDOWN_REF)(v2 + 88));
  return 0;
}

```

## disassembly

```asm
0x14000a4f0  push    rbx
0x14000a4f2  push    rbp
0x14000a4f3  push    rsi
0x14000a4f4  push    rdi
0x14000a4f5  sub     rsp, 48h
0x14000a4f9  mov     rax, cs:WdfFunctions_01031
0x14000a500  mov     esi, edx
0x14000a502  mov     r8, cs:off_14005DF70
0x14000a509  mov     rdx, rcx
0x14000a50c  mov     rcx, cs:WdfDriverGlobals
0x14000a513  mov     rax, [rax+650h]
0x14000a51a  call    _guard_dispatch_icall
0x14000a51f  mov     rbx, rax
0x14000a522  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000a529  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a530  lea     rdi, [rax+612h]
0x14000a537  jz      short loc_14000A553
0x14000a539  mov     cl, [rdi]
0x14000a53b  mov     [rsp+68h+var_38], cl
0x14000a53f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a546  mov     [rsp+68h+var_40], esi
0x14000a54a  mov     rcx, [rcx+40h]
0x14000a54e  call    WPP_RECORDER_SF_dc
0x14000a553  xor     esi, esi
0x14000a555  mov     eax, esi
0x14000a557  xchg    eax, [rbx+6B8h]
0x14000a55d  lock add [rbx+6ACh], eax
0x14000a564  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a56b  jz      short loc_14000A585
0x14000a56d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a574  lea     r9d, [rsi+7Fh]
0x14000a578  mov     [rsp+68h+var_40], eax
0x14000a57c  mov     rcx, [rcx+40h]
0x14000a580  call    WPP_RECORDER_SF_l
0x14000a585  cmp     [rdi], sil
0x14000a588  jnz     short loc_14000A59A
0x14000a58a  lea     rcx, [rbx+40h]; SpinLock
0x14000a58e  mov     [rbx+610h], sil
0x14000a595  call    ?MbbClose@@YAXPEAU_MINIPORT_ADAPTER_CONTEXT@@@Z; MbbClose(_MINIPORT_ADAPTER_CONTEXT *)
0x14000a59a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a5a1  jz      short loc_14000A5CB
0x14000a5a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5aa  lea     rax, WPP_87eee639879b3392f87380bbab0baecf_Traceguids
0x14000a5b1  mov     r9d, 85h
0x14000a5b7  mov     [rsp+68h+var_48], rax
0x14000a5bc  mov     dl, 4
0x14000a5be  mov     rcx, [rcx+40h]
0x14000a5c2  lea     r8d, [r9-7Dh]
0x14000a5c6  call    WPP_RECORDER_SF_
0x14000a5cb  lea     rcx, [rbx+58h]; RunRef
0x14000a5cf  mov     [rbx+614h], sil
0x14000a5d6  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14000a5dd  nop     dword ptr [rax+rax+00h]
0x14000a5e2  lea     rcx, [rbx+58h]; RunRef
0x14000a5e6  call    cs:__imp_ExRundownCompleted
0x14000a5ed  nop     dword ptr [rax+rax+00h]
0x14000a5f2  xor     eax, eax
0x14000a5f4  add     rsp, 48h
0x14000a5f8  pop     rdi
0x14000a5f9  pop     rsi
0x14000a5fa  pop     rbp
0x14000a5fb  pop     rbx
0x14000a5fc  retn
```
