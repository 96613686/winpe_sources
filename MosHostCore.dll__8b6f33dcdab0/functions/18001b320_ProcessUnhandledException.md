# ProcessUnhandledException

- ea: `0x18001b320`
- end: `0x18001b38c`
- name: `ProcessUnhandledException`
- size: `108`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x180018008`
- `0x18001b320`
- `0x180025010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001b34c`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18001b34c`

## string_xrefs

- `0x18001b32d`: `[MosHost] Service crashed with exception code: 0x%08x`

## pseudocode

```c
__int64 (__fastcall *__fastcall ProcessUnhandledException(struct _EXCEPTION_POINTERS *ExceptionInfo))(_QWORD)
{
  PEXCEPTION_RECORD ExceptionRecord; // rdi
  OfflineMapsTelemetry *v3; // rax
  __int64 (__fastcall *result)(_QWORD); // rax

  ZTraceHelperNoThis(
    0,
    "ProcessUnhandledException",
    108,
    "[MosHost] Service crashed with exception code: 0x%08x",
    ExceptionInfo->ExceptionRecord->ExceptionCode);
  ExceptionRecord = ExceptionInfo->ExceptionRecord;
  if ( OfflineMapsTelemetry::IsEnabled() )
  {
    v3 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::MapsBrokerServiceCrash_(v3, ExceptionRecord->ExceptionCode);
  }
  result = qword_180035650;
  if ( qword_180035650 )
    return (__int64 (__fastcall *)(_QWORD))qword_180035650(ExceptionInfo);
  return result;
}

```

## disassembly

```asm
0x18001b320  mov     [rsp+arg_0], rbx
0x18001b325  push    rdi
0x18001b326  sub     rsp, 30h
0x18001b32a  mov     rax, [rcx]
0x18001b32d  lea     r9, aMoshostService; "[MosHost] Service crashed with exceptio"...
0x18001b334  mov     rbx, rcx
0x18001b337  mov     r8d, 6Ch ; 'l'
0x18001b33d  xor     ecx, ecx
0x18001b33f  mov     edx, [rax]
0x18001b341  mov     [rsp+38h+var_18], edx
0x18001b345  lea     rdx, aProcessunhandl; "ProcessUnhandledException"
0x18001b34c  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18001b352  mov     rdi, [rbx]
0x18001b355  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001b35a  test    al, al
0x18001b35c  jz      short loc_18001B36D
0x18001b35e  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18001b363  mov     edx, [rdi]; int
0x18001b365  mov     rcx, rax; this
0x18001b368  call    ?MapsBrokerServiceCrash_@OfflineMapsTelemetry@@QEAAXJ@Z; OfflineMapsTelemetry::MapsBrokerServiceCrash_(long)
0x18001b36d  mov     rax, cs:qword_180035650
0x18001b374  test    rax, rax
0x18001b377  jz      short loc_18001B381
0x18001b379  mov     rcx, rbx
0x18001b37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b381  mov     rbx, [rsp+38h+arg_0]
0x18001b386  add     rsp, 30h
0x18001b38a  pop     rdi
0x18001b38b  retn
```
