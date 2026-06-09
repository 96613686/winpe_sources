# CWinTaskModuleT<PrintJobCleanupTask,&_GUID const CLSID_PrintJobCleanupTask>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180003e44`
- end: `0x180003ef0`
- name: `?DllGetClassObject@?$CWinTaskModuleT@VPrintJobCleanupTask@@$1?CLSID_PrintJobCleanupTask@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005860`

## callees

- `0x180002044`
- `0x180003e44`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CWinTaskModuleT<PrintJobCleanupTask,&_GUID const CLSID_PrintJobCleanupTask>::DllGetClassObject(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v7; // rax
  unsigned int v8; // edi
  _DWORD *v9; // [rsp+30h] [rbp+8h]

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v7 = *(_QWORD *)&CLSID_PrintJobCleanupTask.Data1 - *a2;
  if ( *(_QWORD *)&CLSID_PrintJobCleanupTask.Data1 == *a2 )
    v7 = *(_QWORD *)CLSID_PrintJobCleanupTask.Data4 - a2[1];
  if ( v7 )
  {
    return (unsigned int)-2147221231;
  }
  else
  {
    v9 = operator new(0x10u);
    *(_QWORD *)v9 = &CWinTaskClassFactoryT<PrintJobCleanupTask,1>::`vftable';
    v9[2] = 1;
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
    v8 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, a3, a4);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x180003e44  mov     [rsp+arg_8], rbx
0x180003e49  mov     [rsp+arg_10], rsi
0x180003e4e  push    rdi
0x180003e4f  sub     rsp, 20h
0x180003e53  mov     rdi, r9
0x180003e56  mov     rsi, r8
0x180003e59  test    r9, r9
0x180003e5c  jnz     short loc_180003E65
0x180003e5e  mov     eax, 80070057h
0x180003e63  jmp     short loc_180003EE0
0x180003e65  mov     qword ptr [r9], 0
0x180003e6c  mov     rax, qword ptr cs:CLSID_PrintJobCleanupTask.Data1
0x180003e73  sub     rax, [rdx]
0x180003e76  jnz     short loc_180003E83
0x180003e78  mov     rax, qword ptr cs:CLSID_PrintJobCleanupTask.Data4
0x180003e7f  sub     rax, [rdx+8]
0x180003e83  test    rax, rax
0x180003e86  jz      short loc_180003E8F
0x180003e88  mov     edi, 80040111h
0x180003e8d  jmp     short loc_180003EDE
0x180003e8f  mov     ecx, 10h; Size
0x180003e94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e99  mov     rbx, rax
0x180003e9c  mov     [rsp+28h+arg_0], rax
0x180003ea1  lea     rax, ??_7?$CWinTaskClassFactoryT@VPrintJobCleanupTask@@$00@@6B@; const CWinTaskClassFactoryT<PrintJobCleanupTask,1>::`vftable'
0x180003ea8  mov     [rbx], rax
0x180003eab  mov     dword ptr [rbx+8], 1
0x180003eb2  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180003eb9  mov     rax, [rbx]
0x180003ebc  mov     r8, rdi
0x180003ebf  mov     rdx, rsi
0x180003ec2  mov     rcx, rbx
0x180003ec5  mov     rax, [rax]
0x180003ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ecd  mov     edi, eax
0x180003ecf  mov     rcx, [rbx]
0x180003ed2  mov     rax, [rcx+10h]
0x180003ed6  mov     rcx, rbx
0x180003ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ede  mov     eax, edi
0x180003ee0  mov     rbx, [rsp+28h+arg_8]
0x180003ee5  mov     rsi, [rsp+28h+arg_10]
0x180003eea  add     rsp, 20h
0x180003eee  pop     rdi
0x180003eef  retn
```
