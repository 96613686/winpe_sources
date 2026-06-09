# SPTelemetry::ModelUpdate::StopSession(long,bool)

- ea: `0x140008c20`
- end: `0x140008c8c`
- name: `?StopSession@ModelUpdate@SPTelemetry@@UEAAXJ_N@Z`
- size: `108`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *__hidden this, int, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140004d90`

## callees

- `0x1400077b0`
- `0x140008c20`
- `0x140008c94`

## string_xrefs

- `0x140008c6a`: `ModelUpdate_Stop`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::StopSession(SPTelemetry::ModelUpdate *this, int a2, bool a3)
{
  const struct _tlgProvider_t *v6; // rax

  v6 = SPTraceLoggingClass::Provider();
  if ( *(_DWORD *)v6 > 5u
    && (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v6 + 3) & 0x400000000000LL) == *((_QWORD *)v6 + 3) )
  {
    Windows::Speech::Session::FlightDataRecorder::StopSessionInternal(this, "ModelUpdate_Stop", a2, a3);
  }
}

```

## disassembly

```asm
0x140008c20  mov     [rsp+arg_0], rbx
0x140008c25  mov     [rsp+arg_8], rsi
0x140008c2a  push    rdi
0x140008c2b  sub     rsp, 20h
0x140008c2f  mov     bl, r8b
0x140008c32  mov     edi, edx
0x140008c34  mov     rsi, rcx
0x140008c37  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x140008c3c  mov     r9d, [rax]
0x140008c3f  cmp     r9d, 5
0x140008c43  jbe     short loc_140008C7C
0x140008c45  mov     r9, [rax+18h]
0x140008c49  mov     rcx, 400000000000h
0x140008c53  mov     rax, [rax+10h]
0x140008c57  test    rcx, rax
0x140008c5a  jz      short loc_140008C7C
0x140008c5c  mov     rax, r9
0x140008c5f  and     rax, rcx
0x140008c62  cmp     rax, r9
0x140008c65  jnz     short loc_140008C7C
0x140008c67  mov     r9b, bl; bool
0x140008c6a  lea     rdx, aModelupdateSto; "ModelUpdate_Stop"
0x140008c71  mov     r8d, edi; int
0x140008c74  mov     rcx, rsi; this
0x140008c77  call    ?StopSessionInternal@FlightDataRecorder@Session@Speech@Windows@@IEAAXPEBDJ_N@Z; Windows::Speech::Session::FlightDataRecorder::StopSessionInternal(char const *,long,bool)
0x140008c7c  mov     rbx, [rsp+28h+arg_0]
0x140008c81  mov     rsi, [rsp+28h+arg_8]
0x140008c86  add     rsp, 20h
0x140008c8a  pop     rdi
0x140008c8b  retn
```
