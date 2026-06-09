# SPTelemetry::ModelUpdate::StartSession(bool)

- ea: `0x140008860`
- end: `0x1400088bc`
- name: `?StartSession@ModelUpdate@SPTelemetry@@UEAAX_N@Z`
- size: `92`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *__hidden this, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1400077b0`
- `0x140008860`
- `0x1400088c4`

## string_xrefs

- `0x1400088a2`: `ModelUpdate_Start`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::StartSession(SPTelemetry::ModelUpdate *this, bool a2)
{
  const struct _tlgProvider_t *v4; // rax

  v4 = SPTraceLoggingClass::Provider();
  if ( *(_DWORD *)v4 > 5u
    && (*((_QWORD *)v4 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v4 + 3) & 0x400000000000LL) == *((_QWORD *)v4 + 3) )
  {
    Windows::Speech::Session::FlightDataRecorder::StartSessionInternal(this, "ModelUpdate_Start", a2);
  }
}

```

## disassembly

```asm
0x140008860  mov     [rsp+arg_0], rbx
0x140008865  push    rdi
0x140008866  sub     rsp, 20h
0x14000886a  mov     bl, dl
0x14000886c  mov     rdi, rcx
0x14000886f  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x140008874  mov     r8d, [rax]
0x140008877  cmp     r8d, 5
0x14000887b  jbe     short loc_1400088B1
0x14000887d  mov     r8, [rax+18h]
0x140008881  mov     rcx, 400000000000h
0x14000888b  mov     rax, [rax+10h]
0x14000888f  test    rcx, rax
0x140008892  jz      short loc_1400088B1
0x140008894  mov     rax, r8
0x140008897  and     rax, rcx
0x14000889a  cmp     rax, r8
0x14000889d  jnz     short loc_1400088B1
0x14000889f  mov     r8b, bl; bool
0x1400088a2  lea     rdx, aModelupdateSta; "ModelUpdate_Start"
0x1400088a9  mov     rcx, rdi; this
0x1400088ac  call    ?StartSessionInternal@FlightDataRecorder@Session@Speech@Windows@@IEAAXPEBD_N@Z; Windows::Speech::Session::FlightDataRecorder::StartSessionInternal(char const *,bool)
0x1400088b1  mov     rbx, [rsp+28h+arg_0]
0x1400088b6  add     rsp, 20h
0x1400088ba  pop     rdi
0x1400088bb  retn
```
