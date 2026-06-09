# `MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(void)

- ea: `0x180009db0`
- end: `0x180009e03`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV3@XZ@SA@XZ`
- size: `83`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009db0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009dda`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009dda`

## pseudocode

```c
void __fastcall `MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_()
{
  BOOL v0; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v1; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v0 = 0;
  if ( InitOnceBeginInitialize(
         &`MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance'::`2'::wrapper,
         1u,
         &v0,
         &v1) )
  {
    if ( !v0 )
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v1 + 24LL))(v1, 0);
  }
}

```

## disassembly

```asm
0x180009db0  mov     rax, rsp
0x180009db3  sub     rsp, 28h
0x180009db7  lea     r9, [rax+10h]; lpContext
0x180009dbb  mov     qword ptr [rax+10h], 0
0x180009dc3  lea     r8, [rax+8]; fPending
0x180009dc7  mov     dword ptr [rax+8], 0
0x180009dce  mov     edx, 1; dwFlags
0x180009dd3  lea     rcx, ?wrapper@?1??Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiUmpProtocolDownscalerTransformTelemetryProvider@@@details@wil@@A; lpInitOnce
0x180009dda  call    cs:__imp_InitOnceBeginInitialize
0x180009de0  test    eax, eax
0x180009de2  jz      short loc_180009DFE
0x180009de4  cmp     [rsp+28h+arg_0], 0
0x180009de9  jnz     short loc_180009DFE
0x180009deb  mov     rcx, [rsp+28h+arg_8]
0x180009df0  xor     edx, edx
0x180009df2  mov     rax, [rcx]
0x180009df5  mov     rax, [rax+18h]
0x180009df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dfe  add     rsp, 28h
0x180009e02  retn
```
