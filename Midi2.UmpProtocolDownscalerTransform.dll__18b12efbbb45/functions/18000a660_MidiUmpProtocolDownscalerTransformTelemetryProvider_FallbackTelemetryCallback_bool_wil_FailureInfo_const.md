# MidiUmpProtocolDownscalerTransformTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x18000a660`
- end: `0x18000a694`
- name: `?FallbackTelemetryCallback@MidiUmpProtocolDownscalerTransformTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `52`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a798`
- `0x180013010`

## pseudocode

```c
void __fastcall MidiUmpProtocolDownscalerTransformTelemetryProvider::FallbackTelemetryCallback(
        char a1,
        const struct wil::FailureInfo *a2)
{
  struct MidiUmpProtocolDownscalerTransformTelemetryProvider *v4; // rax
  __int64 v5; // rdx

  v4 = MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance();
  LOBYTE(v5) = a1;
  (*(void (__fastcall **)(struct MidiUmpProtocolDownscalerTransformTelemetryProvider *, __int64, const struct wil::FailureInfo *))(*(_QWORD *)v4 + 16LL))(
    v4,
    v5,
    a2);
}

```

## disassembly

```asm
0x18000a660  mov     [rsp+arg_0], rbx
0x18000a665  push    rdi
0x18000a666  sub     rsp, 20h
0x18000a66a  mov     rbx, rdx
0x18000a66d  mov     dil, cl
0x18000a670  call    ?Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV1@XZ; MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)
0x18000a675  mov     rcx, rax
0x18000a678  mov     dl, dil
0x18000a67b  mov     r8, [rax]
0x18000a67e  mov     rax, [r8+10h]
0x18000a682  mov     r8, rbx
0x18000a685  mov     rbx, [rsp+28h+arg_0]
0x18000a68a  add     rsp, 20h
0x18000a68e  pop     rdi
0x18000a68f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
