# LanguageComponentsInstallerTelemetryProvider::`vector deleting destructor'(uint)

- ea: `0x180014fd0`
- end: `0x180015025`
- name: `??_ELanguageComponentsInstallerTelemetryProvider@@UEAAPEAXI@Z`
- size: `85`
- prototype: `LanguageComponentsInstallerTelemetryProvider *__fastcall(LanguageComponentsInstallerTelemetryProvider *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180003a34`
- `0x180014fd0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180014ffe`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180014ffe`

## pseudocode

```c
LanguageComponentsInstallerTelemetryProvider *__fastcall LanguageComponentsInstallerTelemetryProvider::`vector deleting destructor'(
        LanguageComponentsInstallerTelemetryProvider *this,
        char a2)
{
  __int64 v4; // rax
  REGHANDLE v5; // rcx

  *(_QWORD *)this = &wil::TraceLoggingProvider::`vftable';
  if ( *((_BYTE *)this + 16) )
  {
    v4 = *((_QWORD *)this + 1);
    v5 = *(_QWORD *)(v4 + 32);
    *(_DWORD *)v4 = 0;
    *(_QWORD *)(v4 + 32) = 0;
    EventUnregister(v5);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180014fd0  mov     [rsp+arg_0], rbx
0x180014fd5  push    rdi
0x180014fd6  sub     rsp, 20h
0x180014fda  mov     edi, edx
0x180014fdc  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180014fe3  xor     edx, edx
0x180014fe5  mov     [rcx], rax
0x180014fe8  mov     rbx, rcx
0x180014feb  cmp     [rcx+10h], dl
0x180014fee  jz      short loc_180015004
0x180014ff0  mov     rax, [rcx+8]
0x180014ff4  mov     rcx, [rax+20h]; RegHandle
0x180014ff8  mov     [rax], edx
0x180014ffa  mov     [rax+20h], rdx
0x180014ffe  call    cs:__imp_EventUnregister
0x180015004  test    dil, 1
0x180015008  jz      short loc_180015017
0x18001500a  mov     edx, 20h ; ' '
0x18001500f  mov     rcx, rbx; Block
0x180015012  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015017  mov     rax, rbx
0x18001501a  mov     rbx, [rsp+28h+arg_0]
0x18001501f  add     rsp, 20h
0x180015023  pop     rdi
0x180015024  retn
```
