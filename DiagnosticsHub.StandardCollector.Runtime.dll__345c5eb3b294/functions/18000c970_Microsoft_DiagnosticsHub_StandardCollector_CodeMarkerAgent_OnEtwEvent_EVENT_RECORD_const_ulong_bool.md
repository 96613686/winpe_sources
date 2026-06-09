# Microsoft::DiagnosticsHub::StandardCollector::CodeMarkerAgent::OnEtwEvent(_EVENT_RECORD const *,ulong,bool *)

- ea: `0x18000c970`
- end: `0x18000ca16`
- name: `?OnEtwEvent@CodeMarkerAgent@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEBU_EVENT_RECORD@@KPEA_N@Z`
- size: `166`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::CodeMarkerAgent *__hidden this, const struct _EVENT_RECORD *, unsigned int, bool *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000c970`
- `0x18000ca18`
- `0x18000cb68`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x18000c9a2`
- `VCRUNTIME140!memcmp` at `0x18000c9d7`
- `VCRUNTIME140!memcmp` at `0x18000c9a2`
- `VCRUNTIME140!memcmp` at `0x18000c9d7`
- `KERNEL32!GetCurrentProcessId` at `0x18000c9af`
- `KERNEL32!GetCurrentProcessId` at `0x18000c9af`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::CodeMarkerAgent::OnEtwEvent(
        Microsoft::DiagnosticsHub::StandardCollector::CodeMarkerAgent *this,
        const struct _EVENT_RECORD *a2,
        __int64 a3,
        bool *a4)
{
  ULONG ProcessId; // ebx
  __int64 result; // rax

  *a4 = 0;
  if ( !memcmp(&a2->EventHeader.ProviderId, &xmmword_180056550, 0x10u) )
  {
    ProcessId = a2->EventHeader.ProcessId;
    if ( ProcessId == GetCurrentProcessId() )
      return 0;
    result = Microsoft::DiagnosticsHub::StandardCollector::CodeMarkerAgent::TryAddTargetProcess(
               (Microsoft::DiagnosticsHub::StandardCollector::CodeMarkerAgent *)((char *)this - 8),
               ProcessId);
  }
  else
  {
    if ( memcmp(&a2->EventHeader.ProviderId, qword_180056560, 0x10u) )
      return 0;
    *a4 = 1;
    if ( a2->EventHeader.EventDescriptor.Opcode != 2 )
      return 0;
    result = Microsoft::DiagnosticsHub::StandardCollector::CodeMarkerAgent::TryRemoveTargetProcess(
               (Microsoft::DiagnosticsHub::StandardCollector::CodeMarkerAgent *)((char *)this - 8),
               a2->EventHeader.ProcessId);
  }
  if ( (int)result < 0 )
  {
    _mm_lfence();
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c970  mov     [rsp+arg_0], rbx
0x18000c975  mov     [rsp+arg_8], rbp
0x18000c97a  mov     [rsp+arg_10], rsi
0x18000c97f  push    rdi
0x18000c980  sub     rsp, 20h
0x18000c984  mov     rbx, rdx
0x18000c987  mov     byte ptr [r9], 0
0x18000c98b  mov     rdi, rcx
0x18000c98e  lea     rdx, xmmword_180056550; Buf2
0x18000c995  mov     r8d, 10h; Size
0x18000c99b  mov     rsi, r9
0x18000c99e  lea     rcx, [rbx+18h]; Buf1
0x18000c9a2  call    cs:__imp_memcmp
0x18000c9a8  test    eax, eax
0x18000c9aa  jnz     short loc_18000C9C6
0x18000c9ac  mov     ebx, [rbx+0Ch]
0x18000c9af  call    cs:__imp_GetCurrentProcessId
0x18000c9b5  cmp     ebx, eax
0x18000c9b7  jz      short loc_18000C9FF
0x18000c9b9  lea     rcx, [rdi-8]; this
0x18000c9bd  mov     edx, ebx; unsigned int
0x18000c9bf  call    ?TryAddTargetProcess@CodeMarkerAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJK@Z; Microsoft::DiagnosticsHub::StandardCollector::CodeMarkerAgent::TryAddTargetProcess(ulong)
0x18000c9c4  jmp     short loc_18000C9F6
0x18000c9c6  mov     r8d, 10h; Size
0x18000c9cc  lea     rdx, qword_180056560; Buf2
0x18000c9d3  lea     rcx, [rbx+18h]; Buf1
0x18000c9d7  call    cs:__imp_memcmp
0x18000c9dd  test    eax, eax
0x18000c9df  jnz     short loc_18000C9FF
0x18000c9e1  mov     byte ptr [rsi], 1
0x18000c9e4  cmp     byte ptr [rbx+2Dh], 2
0x18000c9e8  jnz     short loc_18000C9FF
0x18000c9ea  mov     edx, [rbx+0Ch]; unsigned int
0x18000c9ed  lea     rcx, [rdi-8]; this
0x18000c9f1  call    ?TryRemoveTargetProcess@CodeMarkerAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJK@Z; Microsoft::DiagnosticsHub::StandardCollector::CodeMarkerAgent::TryRemoveTargetProcess(ulong)
0x18000c9f6  test    eax, eax
0x18000c9f8  jns     short loc_18000C9FF
0x18000c9fa  lfence
0x18000c9fd  jmp     short loc_18000CA01
0x18000c9ff  xor     eax, eax
0x18000ca01  mov     rbx, [rsp+28h+arg_0]
0x18000ca06  mov     rbp, [rsp+28h+arg_8]
0x18000ca0b  mov     rsi, [rsp+28h+arg_10]
0x18000ca10  add     rsp, 20h
0x18000ca14  pop     rdi
0x18000ca15  retn
```
