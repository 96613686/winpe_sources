# CAggregateTelemetryLazyUpdate<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::SetPeriod(unsigned __int64)

- ea: `0x18001eb80`
- end: `0x18001ebc0`
- name: `?SetPeriod@?$CAggregateTelemetryLazyUpdate@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@UEAAX_K@Z`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180024010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001ebab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001ebab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONGLONG __fastcall CAggregateTelemetryLazyUpdate<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::SetPeriod(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v2; // rbx
  ULONGLONG result; // rax

  v2 = a2;
  LOBYTE(a2) = 1;
  (*(void (__fastcall **)(_QWORD *, __int64))(*a1 + 48LL))(a1, a2);
  a1[4] = v2;
  result = GetTickCount64();
  a1[5] = result;
  return result;
}

```

## disassembly

```asm
0x18001eb80  mov     [rsp+arg_8], rbx
0x18001eb85  push    rdi
0x18001eb86  sub     rsp, 20h
0x18001eb8a  mov     rbx, rdx
0x18001eb8d  mov     rdi, rcx
0x18001eb90  mov     [rsp+28h+arg_0], 0
0x18001eb99  mov     rax, [rcx]
0x18001eb9c  mov     dl, 1
0x18001eb9e  mov     rax, [rax+30h]
0x18001eba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eba7  mov     [rdi+20h], rbx
0x18001ebab  call    cs:__imp_GetTickCount64
0x18001ebb1  mov     [rdi+28h], rax
0x18001ebb5  mov     rbx, [rsp+28h+arg_8]
0x18001ebba  add     rsp, 20h
0x18001ebbe  pop     rdi
0x18001ebbf  retn
```
