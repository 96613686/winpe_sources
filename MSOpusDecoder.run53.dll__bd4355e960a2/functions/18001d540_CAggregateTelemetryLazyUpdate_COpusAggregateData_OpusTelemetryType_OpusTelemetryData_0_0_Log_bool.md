# CAggregateTelemetryLazyUpdate<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::Log(bool)

- ea: `0x18001d540`
- end: `0x18001d591`
- name: `?Log@?$CAggregateTelemetryLazyUpdate@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@UEAAX_N@Z`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18001d540`
- `0x18001d5a0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001d57c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001d57c`

## pseudocode

```c
ULONGLONG __fastcall CAggregateTelemetryLazyUpdate<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::Log(
        _QWORD *a1,
        char a2)
{
  COpusAggregateData *v4; // rcx
  ULONGLONG result; // rax

  v4 = (COpusAggregateData *)a1[1];
  if ( v4 )
    COpusAggregateData::LogTelemetry(v4);
  if ( a2 )
    (*(void (__fastcall **)(_QWORD *))(*a1 + 24LL))(a1);
  result = GetTickCount64();
  a1[5] = result;
  return result;
}

```

## disassembly

```asm
0x18001d540  mov     [rsp+arg_8], rbx
0x18001d545  push    rdi
0x18001d546  sub     rsp, 20h
0x18001d54a  mov     dil, dl
0x18001d54d  mov     rbx, rcx
0x18001d550  mov     [rsp+28h+arg_0], 0
0x18001d559  mov     rcx, [rcx+8]; this
0x18001d55d  test    rcx, rcx
0x18001d560  jz      short loc_18001D568
0x18001d562  call    ?LogTelemetry@COpusAggregateData@@UEAAXXZ; COpusAggregateData::LogTelemetry(void)
0x18001d567  nop
0x18001d568  test    dil, dil
0x18001d56b  jz      short loc_18001D57C
0x18001d56d  mov     rax, [rbx]
0x18001d570  mov     rcx, rbx
0x18001d573  mov     rax, [rax+18h]
0x18001d577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d57c  call    cs:__imp_GetTickCount64
0x18001d582  mov     [rbx+28h], rax
0x18001d586  mov     rbx, [rsp+28h+arg_8]
0x18001d58b  add     rsp, 20h
0x18001d58f  pop     rdi
0x18001d590  retn
```
