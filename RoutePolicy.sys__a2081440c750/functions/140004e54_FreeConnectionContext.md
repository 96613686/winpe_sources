# FreeConnectionContext

- ea: `0x140004e54`
- end: `0x140004f1a`
- name: `FreeConnectionContext`
- size: `198`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400037a4`
- `0x140003f18`
- `0x140006afc`
- `0x140007110`
- `0x140007280`

## callees

- `0x140004e54`
- `0x14000935c`
- `0x14000a6c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004e7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004f07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004f07`

## pseudocode

```c
void __fastcall FreeConnectionContext(_QWORD *P, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  void *v5; // rcx

  if ( P )
  {
    v4 = (void *)P[3];
    if ( v4 )
      ExFreePoolWithTag(v4, 0x64667072u);
    v5 = (void *)P[4];
    if ( v5 )
      ExFreePoolWithTag(v5, 0x64667072u);
    if ( *((_BYTE *)P + 128) )
    {
      if ( *((_BYTE *)P + 129) )
      {
        LOBYTE(a3) = 1;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2560))(
          WdfDriverGlobals,
          P[15],
          a3);
        *((_BYTE *)P + 129) = 0;
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, P[15]);
      *((_BYTE *)P + 128) = 0;
    }
    ExFreePoolWithTag(P, 0x64667072u);
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
}

```

## disassembly

```asm
0x140004e54  push    rbx
0x140004e56  sub     rsp, 20h
0x140004e5a  mov     rbx, rcx
0x140004e5d  test    rcx, rcx
0x140004e60  jnz     short loc_140004E6C
0x140004e62  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140004e67  jmp     loc_140004F13
0x140004e6c  mov     rcx, [rcx+18h]; P
0x140004e70  test    rcx, rcx
0x140004e73  jz      short loc_140004E86
0x140004e75  mov     edx, 64667072h; Tag
0x140004e7a  call    cs:__imp_ExFreePoolWithTag
0x140004e81  nop     dword ptr [rax+rax+00h]
0x140004e86  mov     rcx, [rbx+20h]; P
0x140004e8a  test    rcx, rcx
0x140004e8d  jz      short loc_140004EA0
0x140004e8f  mov     edx, 64667072h; Tag
0x140004e94  call    cs:__imp_ExFreePoolWithTag
0x140004e9b  nop     dword ptr [rax+rax+00h]
0x140004ea0  cmp     byte ptr [rbx+80h], 0
0x140004ea7  jz      short loc_140004EFF
0x140004ea9  cmp     byte ptr [rbx+81h], 0
0x140004eb0  jz      short loc_140004EDA
0x140004eb2  mov     rax, cs:WdfFunctions_01015
0x140004eb9  mov     r8b, 1
0x140004ebc  mov     rdx, [rbx+78h]
0x140004ec0  mov     rcx, cs:WdfDriverGlobals
0x140004ec7  mov     rax, [rax+0A00h]
0x140004ece  call    _guard_dispatch_icall
0x140004ed3  mov     byte ptr [rbx+81h], 0
0x140004eda  mov     rax, cs:WdfFunctions_01015
0x140004ee1  mov     rdx, [rbx+78h]
0x140004ee5  mov     rcx, cs:WdfDriverGlobals
0x140004eec  mov     rax, [rax+680h]
0x140004ef3  call    _guard_dispatch_icall
0x140004ef8  mov     byte ptr [rbx+80h], 0
0x140004eff  mov     edx, 64667072h; Tag
0x140004f04  mov     rcx, rbx; P
0x140004f07  call    cs:__imp_ExFreePoolWithTag
0x140004f0e  nop     dword ptr [rax+rax+00h]
0x140004f13  add     rsp, 20h
0x140004f17  pop     rbx
0x140004f18  retn
```
