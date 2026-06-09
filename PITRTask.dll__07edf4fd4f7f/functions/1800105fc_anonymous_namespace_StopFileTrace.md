# _anonymous_namespace_::StopFileTrace

- ea: `0x1800105fc`
- end: `0x180010680`
- name: `_anonymous_namespace_::StopFileTrace`
- size: `132`
- prototype: `BOOL __fastcall(__int64, TRACEHANDLE)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a4f0`
- `0x18000fce4`
- `0x18000ff50`

## callees

- `0x18000fd2c`
- `0x1800105fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001065c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001065c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001066a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001066a`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180010648`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180010648`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x180010656`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x180010656`

## pseudocode

```c
BOOL __fastcall anonymous_namespace_::StopFileTrace(__int64 a1, TRACEHANDLE a2)
{
  struct _EVENT_TRACE_PROPERTIES *v4; // rsi
  BOOL result; // eax
  HANDLE ProcessHeap; // rax

  v4 = (struct _EVENT_TRACE_PROPERTIES *)anonymous_namespace_::AllocEventProperties(a1, 0);
  result = 0;
  if ( v4 )
  {
    if ( a2 != -1 )
      EnableTraceEx2(a2, (LPCGUID)(a1 + 8), 0, 0, 0, 0, 0, 0);
    StopTraceW(0, *(LPCWSTR *)a1, v4);
    ProcessHeap = GetProcessHeap();
    return HeapFree(ProcessHeap, 0, v4);
  }
  return result;
}

```

## disassembly

```asm
0x1800105fc  mov     [rsp+arg_0], rbx
0x180010601  mov     [rsp+arg_8], rsi
0x180010606  push    rdi
0x180010607  sub     rsp, 40h
0x18001060b  mov     rbx, rdx
0x18001060e  mov     rdi, rcx
0x180010611  xor     edx, edx
0x180010613  call    _anonymous_namespace___AllocEventProperties
0x180010618  mov     rsi, rax
0x18001061b  xor     eax, eax
0x18001061d  test    rsi, rsi
0x180010620  jz      short loc_180010670
0x180010622  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180010626  jz      short loc_18001064E
0x180010628  mov     [rsp+48h+EnableParameters], rax; EnableParameters
0x18001062d  lea     rdx, [rdi+8]; ProviderId
0x180010631  mov     [rsp+48h+Timeout], eax; Timeout
0x180010635  xor     r9d, r9d; Level
0x180010638  mov     [rsp+48h+MatchAllKeyword], rax; MatchAllKeyword
0x18001063d  xor     r8d, r8d; ControlCode
0x180010640  mov     rcx, rbx; TraceHandle
0x180010643  mov     [rsp+48h+MatchAnyKeyword], rax; MatchAnyKeyword
0x180010648  call    cs:__imp_EnableTraceEx2
0x18001064e  mov     rdx, [rdi]; InstanceName
0x180010651  mov     r8, rsi; Properties
0x180010654  xor     ecx, ecx; TraceHandle
0x180010656  call    cs:__imp_StopTraceW
0x18001065c  call    cs:__imp_GetProcessHeap
0x180010662  mov     r8, rsi; lpMem
0x180010665  xor     edx, edx; dwFlags
0x180010667  mov     rcx, rax; hHeap
0x18001066a  call    cs:__imp_HeapFree
0x180010670  mov     rbx, [rsp+48h+arg_0]
0x180010675  mov     rsi, [rsp+48h+arg_8]
0x18001067a  add     rsp, 40h
0x18001067e  pop     rdi
0x18001067f  retn
```
