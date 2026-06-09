# SPTelemetry::ModelUpdate::`scalar deleting destructor'(uint)

- ea: `0x140004d90`
- end: `0x140004de4`
- name: `??_GModelUpdate@SPTelemetry@@UEAAPEAXI@Z`
- size: `84`
- prototype: `SPTelemetry::ModelUpdate *__fastcall(SPTelemetry::ModelUpdate *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x1400028d8`
- `0x140004aec`
- `0x140004d90`
- `0x140008c20`

## pseudocode

```c
SPTelemetry::ModelUpdate *__fastcall SPTelemetry::ModelUpdate::`scalar deleting destructor'(
        SPTelemetry::ModelUpdate *this,
        char a2)
{
  *(_QWORD *)this = &SPTelemetry::ModelUpdate::`vftable';
  if ( *((_BYTE *)this + 8) )
    SPTelemetry::ModelUpdate::StopSession(this, *((_DWORD *)this + 4), 1);
  Windows::Speech::Session::FlightDataRecorder::~FlightDataRecorder(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140004d90  mov     [rsp+arg_0], rbx
0x140004d95  push    rdi
0x140004d96  sub     rsp, 20h
0x140004d9a  mov     edi, edx
0x140004d9c  mov     rbx, rcx
0x140004d9f  lea     rax, ??_7ModelUpdate@SPTelemetry@@6B@; const SPTelemetry::ModelUpdate::`vftable'
0x140004da6  mov     [rcx], rax
0x140004da9  cmp     byte ptr [rcx+8], 0
0x140004dad  jz      short loc_140004DBA
0x140004daf  mov     r8b, 1; bool
0x140004db2  mov     edx, [rcx+10h]; int
0x140004db5  call    ?StopSession@ModelUpdate@SPTelemetry@@UEAAXJ_N@Z; SPTelemetry::ModelUpdate::StopSession(long,bool)
0x140004dba  mov     rcx, rbx; this
0x140004dbd  call    ??1FlightDataRecorder@Session@Speech@Windows@@MEAA@XZ; Windows::Speech::Session::FlightDataRecorder::~FlightDataRecorder(void)
0x140004dc2  nop
0x140004dc3  test    dil, 1
0x140004dc7  jz      short loc_140004DD6
0x140004dc9  mov     edx, 98h
0x140004dce  mov     rcx, rbx; Block
0x140004dd1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004dd6  mov     rax, rbx
0x140004dd9  mov     rbx, [rsp+28h+arg_0]
0x140004dde  add     rsp, 20h
0x140004de2  pop     rdi
0x140004de3  retn
```
