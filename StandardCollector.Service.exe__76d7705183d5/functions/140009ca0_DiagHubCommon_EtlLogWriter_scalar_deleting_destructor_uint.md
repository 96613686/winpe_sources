# DiagHubCommon::EtlLogWriter::`scalar deleting destructor'(uint)

- ea: `0x140009ca0`
- end: `0x140009ce3`
- name: `??_GEtlLogWriter@DiagHubCommon@@UEAAPEAXI@Z`
- size: `67`
- prototype: `void *__fastcall(DiagHubCommon::EtlLogWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140009ca0`
- `0x14001382c`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x140009cbd`
- `ADVAPI32!EventUnregister` at `0x140009cbd`

## pseudocode

```c
DiagHubCommon::EtlLogWriter *__fastcall DiagHubCommon::EtlLogWriter::`scalar deleting destructor'(
        DiagHubCommon::EtlLogWriter *this,
        char a2)
{
  *(_QWORD *)this = &DiagHubCommon::EtlLogWriter::`vftable';
  EventUnregister(*((_QWORD *)this + 1));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140009ca0  mov     [rsp+arg_0], rbx
0x140009ca5  push    rdi
0x140009ca6  sub     rsp, 20h
0x140009caa  lea     rax, ??_7EtlLogWriter@DiagHubCommon@@6B@; const DiagHubCommon::EtlLogWriter::`vftable'
0x140009cb1  mov     rdi, rcx
0x140009cb4  mov     [rcx], rax
0x140009cb7  mov     ebx, edx
0x140009cb9  mov     rcx, [rcx+8]; RegHandle
0x140009cbd  call    cs:__imp_EventUnregister
0x140009cc3  test    bl, 1
0x140009cc6  jz      short loc_140009CD5
0x140009cc8  mov     edx, 10h
0x140009ccd  mov     rcx, rdi; Block
0x140009cd0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009cd5  mov     rbx, [rsp+28h+arg_0]
0x140009cda  mov     rax, rdi
0x140009cdd  add     rsp, 20h
0x140009ce1  pop     rdi
0x140009ce2  retn
```
