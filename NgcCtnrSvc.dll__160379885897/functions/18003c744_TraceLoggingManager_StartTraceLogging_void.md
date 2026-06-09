# TraceLoggingManager::StartTraceLogging(void)

- ea: `0x18003c744`
- end: `0x18003c873`
- name: `?StartTraceLogging@TraceLoggingManager@@QEAAJXZ`
- size: `303`
- prototype: `__int64 __fastcall(TraceLoggingManager *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003ad70`

## callees

- `0x180023278`
- `0x18003c6c4`
- `0x18003c744`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c81f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c81f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003c80f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003c80f`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18003c782`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18003c7ee`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18003c782`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18003c7ee`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003c7c1`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003c7c1`

## string_xrefs

- `0x18003c843`: `onecore\ds\security\ngc\ctnrsvc\service\traceloggingmanager.cpp`

## pseudocode

```c
__int64 __fastcall TraceLoggingManager::StartTraceLogging(TraceLoggingManager *this)
{
  const WCHAR *v2; // rbx
  const WCHAR *v3; // rdx
  signed int started; // eax
  TraceLoggingManager *v5; // rcx
  const WCHAR *v6; // rdx
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( byte_1800C0D88 )
    return 0;
  v2 = (const WCHAR *)&g_NgcTraceLoggingManager;
  v3 = (const WCHAR *)&g_NgcTraceLoggingManager;
  if ( (unsigned __int64)qword_1800C0D48 > 7 )
    v3 = g_NgcTraceLoggingManager;
  started = StartTraceW(&TraceHandle, v3, &Properties);
  if ( started == 112 || started == 87 )
  {
    if ( !DeleteFileW(&FileName) )
    {
      started = GetLastError();
      goto LABEL_19;
    }
LABEL_11:
    if ( (unsigned __int64)qword_1800C0D48 > 7 )
      v2 = g_NgcTraceLoggingManager;
    started = StartTraceW(&TraceHandle, v2, &Properties);
LABEL_19:
    v7 = started;
    if ( started <= 0 )
      goto LABEL_21;
    goto LABEL_20;
  }
  if ( started == 183 )
  {
    v6 = (const WCHAR *)&g_NgcTraceLoggingManager;
    if ( (unsigned __int64)qword_1800C0D48 > 7 )
      v6 = g_NgcTraceLoggingManager;
    ControlTraceW(0, v6, &Properties, 1u);
    goto LABEL_11;
  }
  v7 = 0;
  if ( !started )
  {
LABEL_23:
    TraceLoggingManager::SetTraceLoggingProvidersState(v5, 1u);
    byte_1800C0D88 = 1;
    return v7;
  }
  if ( started <= 0 )
  {
    v7 = started;
    goto LABEL_21;
  }
LABEL_20:
  v7 = (unsigned __int16)started | 0x80070000;
LABEL_21:
  if ( (v7 & 0x80000000) == 0 )
    goto LABEL_23;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3C,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\traceloggingmanager.cpp",
    (const char *)v7,
    v8);
  return v7;
}

```

## disassembly

```asm
0x18003c744  push    rbx; int
0x18003c746  sub     rsp, 20h
0x18003c74a  cmp     cs:byte_1800C0D88, 0
0x18003c751  jz      short loc_18003C75A
0x18003c753  xor     eax, eax
0x18003c755  jmp     loc_18003C86C
0x18003c75a  cmp     cs:qword_1800C0D48, 7
0x18003c762  lea     rbx, ?g_NgcTraceLoggingManager@@3VTraceLoggingManager@@A; TraceLoggingManager g_NgcTraceLoggingManager
0x18003c769  mov     rdx, rbx
0x18003c76c  lea     r8, Properties; Properties
0x18003c773  cmova   rdx, cs:?g_NgcTraceLoggingManager@@3VTraceLoggingManager@@A; InstanceName
0x18003c77b  lea     rcx, TraceHandle; TraceHandle
0x18003c782  call    cs:__imp_StartTraceW
0x18003c789  nop     dword ptr [rax+rax+00h]
0x18003c78e  cmp     eax, 70h ; 'p'
0x18003c791  jz      short loc_18003C808
0x18003c793  cmp     eax, 57h ; 'W'
0x18003c796  jz      short loc_18003C808
0x18003c798  cmp     eax, 0B7h
0x18003c79d  jnz     short loc_18003C7FC
0x18003c79f  cmp     cs:qword_1800C0D48, 7
0x18003c7a7  lea     r8, Properties; Properties
0x18003c7ae  mov     rdx, rbx
0x18003c7b1  mov     r9d, 1; ControlCode
0x18003c7b7  cmova   rdx, cs:?g_NgcTraceLoggingManager@@3VTraceLoggingManager@@A; InstanceName
0x18003c7bf  xor     ecx, ecx; TraceHandle
0x18003c7c1  call    cs:__imp_ControlTraceW
0x18003c7c8  nop     dword ptr [rax+rax+00h]
0x18003c7cd  cmp     cs:qword_1800C0D48, 7
0x18003c7d5  lea     r8, Properties; Properties
0x18003c7dc  lea     rcx, TraceHandle; TraceHandle
0x18003c7e3  cmova   rbx, cs:?g_NgcTraceLoggingManager@@3VTraceLoggingManager@@A; TraceLoggingManager g_NgcTraceLoggingManager
0x18003c7eb  mov     rdx, rbx; InstanceName
0x18003c7ee  call    cs:__imp_StartTraceW
0x18003c7f5  nop     dword ptr [rax+rax+00h]
0x18003c7fa  jmp     short loc_18003C82B
0x18003c7fc  xor     ebx, ebx
0x18003c7fe  test    eax, eax
0x18003c800  jz      short loc_18003C859
0x18003c802  jg      short loc_18003C831
0x18003c804  mov     ebx, eax
0x18003c806  jmp     short loc_18003C83A
0x18003c808  lea     rcx, FileName; lpFileName
0x18003c80f  call    cs:__imp_DeleteFileW
0x18003c816  nop     dword ptr [rax+rax+00h]
0x18003c81b  test    eax, eax
0x18003c81d  jnz     short loc_18003C7CD
0x18003c81f  call    cs:__imp_GetLastError
0x18003c826  nop     dword ptr [rax+rax+00h]
0x18003c82b  mov     ebx, eax
0x18003c82d  test    eax, eax
0x18003c82f  jle     short loc_18003C83A
0x18003c831  movzx   ebx, ax
0x18003c834  or      ebx, 80070000h
0x18003c83a  test    ebx, ebx
0x18003c83c  jns     short loc_18003C859
0x18003c83e  mov     rcx, [rsp+28h]; this
0x18003c843  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x18003c84a  mov     r9d, ebx; char *
0x18003c84d  mov     edx, 3Ch ; '<'; void *
0x18003c852  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c857  jmp     short loc_18003C86A
0x18003c859  mov     edx, 1; unsigned int
0x18003c85e  call    ?SetTraceLoggingProvidersState@TraceLoggingManager@@AEAAXK@Z; TraceLoggingManager::SetTraceLoggingProvidersState(ulong)
0x18003c863  mov     cs:byte_1800C0D88, 1
0x18003c86a  mov     eax, ebx
0x18003c86c  add     rsp, 20h
0x18003c870  pop     rbx
0x18003c871  retn
```
