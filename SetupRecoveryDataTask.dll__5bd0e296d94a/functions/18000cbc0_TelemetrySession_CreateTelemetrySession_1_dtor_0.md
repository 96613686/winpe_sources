# _TelemetrySession::CreateTelemetrySession_::_1_::dtor$0

- ea: `0x18000cbc0`
- end: `0x18000cbce`
- name: `_TelemetrySession::CreateTelemetrySession_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cbc7`

## pseudocode

```c
void __fastcall TelemetrySession::CreateTelemetrySession_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x18000cbc0  mov     rcx, [rdx+20h]
0x18000cbc7  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
