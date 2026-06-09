# _TelemetrySession::CreateTelemetrySession_::_1_::dtor$0

- ea: `0x18001482b`
- end: `0x180014839`
- name: `_TelemetrySession::CreateTelemetrySession_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180014832`

## pseudocode

```c
void __fastcall TelemetrySession::CreateTelemetrySession_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x18001482b  mov     rcx, [rdx+20h]
0x180014832  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
