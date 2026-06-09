# CWinTaskModuleT<PrinterCleanupTask,&_GUID const CLSID_PrinterCleanupTask>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180003ef8`
- end: `0x180003fa4`
- name: `?DllGetClassObject@?$CWinTaskModuleT@VPrinterCleanupTask@@$1?CLSID_PrinterCleanupTask@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005860`

## callees

- `0x180002044`
- `0x180003ef8`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CWinTaskModuleT<PrinterCleanupTask,&_GUID const CLSID_PrinterCleanupTask>::DllGetClassObject(
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
  v7 = *(_QWORD *)&CLSID_PrinterCleanupTask.Data1 - *a2;
  if ( *(_QWORD *)&CLSID_PrinterCleanupTask.Data1 == *a2 )
    v7 = *(_QWORD *)CLSID_PrinterCleanupTask.Data4 - a2[1];
  if ( v7 )
  {
    return (unsigned int)-2147221231;
  }
  else
  {
    v9 = operator new(0x10u);
    *(_QWORD *)v9 = &CWinTaskClassFactoryT<PrinterCleanupTask,1>::`vftable';
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
0x180003ef8  mov     [rsp+arg_8], rbx
0x180003efd  mov     [rsp+arg_10], rsi
0x180003f02  push    rdi
0x180003f03  sub     rsp, 20h
0x180003f07  mov     rdi, r9
0x180003f0a  mov     rsi, r8
0x180003f0d  test    r9, r9
0x180003f10  jnz     short loc_180003F19
0x180003f12  mov     eax, 80070057h
0x180003f17  jmp     short loc_180003F94
0x180003f19  mov     qword ptr [r9], 0
0x180003f20  mov     rax, qword ptr cs:CLSID_PrinterCleanupTask.Data1
0x180003f27  sub     rax, [rdx]
0x180003f2a  jnz     short loc_180003F37
0x180003f2c  mov     rax, qword ptr cs:CLSID_PrinterCleanupTask.Data4
0x180003f33  sub     rax, [rdx+8]
0x180003f37  test    rax, rax
0x180003f3a  jz      short loc_180003F43
0x180003f3c  mov     edi, 80040111h
0x180003f41  jmp     short loc_180003F92
0x180003f43  mov     ecx, 10h; Size
0x180003f48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003f4d  mov     rbx, rax
0x180003f50  mov     [rsp+28h+arg_0], rax
0x180003f55  lea     rax, ??_7?$CWinTaskClassFactoryT@VPrinterCleanupTask@@$00@@6B@; const CWinTaskClassFactoryT<PrinterCleanupTask,1>::`vftable'
0x180003f5c  mov     [rbx], rax
0x180003f5f  mov     dword ptr [rbx+8], 1
0x180003f66  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180003f6d  mov     rax, [rbx]
0x180003f70  mov     r8, rdi
0x180003f73  mov     rdx, rsi
0x180003f76  mov     rcx, rbx
0x180003f79  mov     rax, [rax]
0x180003f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f81  mov     edi, eax
0x180003f83  mov     rcx, [rbx]
0x180003f86  mov     rax, [rcx+10h]
0x180003f8a  mov     rcx, rbx
0x180003f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f92  mov     eax, edi
0x180003f94  mov     rbx, [rsp+28h+arg_8]
0x180003f99  mov     rsi, [rsp+28h+arg_10]
0x180003f9e  add     rsp, 20h
0x180003fa2  pop     rdi
0x180003fa3  retn
```
