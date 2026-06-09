# Tracker::DeleteManagedRuntime(void)

- ea: `0x140002d6c`
- end: `0x140002dfb`
- name: `?DeleteManagedRuntime@Tracker@@CAJXZ`
- size: `143`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140004e38`

## callees

- `0x140002d6c`
- `0x1400052d0`
- `0x140005374`
- `0x14000556c`
- `0x140005594`
- `0x140006590`

## import_xrefs

- `ole32!CoUninitialize` at `0x140002dd8`
- `ole32!CoUninitialize` at `0x140002dd8`

## pseudocode

```c
__int64 Tracker::DeleteManagedRuntime(void)
{
  unsigned int v0; // ebx
  int v1; // edi
  int v3; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  v1 = 0;
  v3 = 0;
  if ( *(_QWORD *)&Tracker::s_pManagedRuntime.Data1 )
  {
    CReadWriteSpinLock::AcquireWriterLock((CReadWriteSpinLock *)&Tracker::s_lockManagedRuntime);
    v1 = 1;
    if ( *(_QWORD *)&Tracker::s_pManagedRuntime.Data1 )
    {
      v0 = EnsureCoInitialized(&v3);
      if ( !v0 )
        v0 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&Tracker::s_pManagedRuntime.Data1 + 24LL))(*(_QWORD *)&Tracker::s_pManagedRuntime.Data1);
    }
  }
  ClearInterfaceFn((struct IUnknown **)&Tracker::s_pManagedRuntime);
  if ( v3 )
    CoUninitialize();
  if ( v1 )
    CReadWriteSpinLock::ReleaseWriterLock((CReadWriteSpinLock *)&Tracker::s_lockManagedRuntime);
  return v0;
}

```

## disassembly

```asm
0x140002d6c  mov     [rsp+arg_8], rbx
0x140002d71  push    rdi
0x140002d72  sub     rsp, 20h
0x140002d76  xor     ebx, ebx
0x140002d78  xor     edi, edi
0x140002d7a  and     [rsp+28h+arg_0], ebx
0x140002d7e  cmp     qword ptr cs:?s_pManagedRuntime@Tracker@@0PEAU_StateRuntime@xspmrt@@EA.Data1, rbx; xspmrt::_StateRuntime * Tracker::s_pManagedRuntime ...
0x140002d85  jz      short loc_140002DC5
0x140002d87  lea     rcx, ?s_lockManagedRuntime@Tracker@@0VCReadWriteSpinLock@@A; this
0x140002d8e  call    ?AcquireWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::AcquireWriterLock(void)
0x140002d93  cmp     qword ptr cs:?s_pManagedRuntime@Tracker@@0PEAU_StateRuntime@xspmrt@@EA.Data1, rbx; xspmrt::_StateRuntime * Tracker::s_pManagedRuntime ...
0x140002d9a  lea     edi, [rbx+1]
0x140002d9d  jz      short loc_140002DC5
0x140002d9f  lea     rcx, [rsp+28h+arg_0]; int *
0x140002da4  call    ?EnsureCoInitialized@@YAJPEAH@Z; EnsureCoInitialized(int *)
0x140002da9  mov     ebx, eax
0x140002dab  test    eax, eax
0x140002dad  jnz     short loc_140002DC5
0x140002daf  mov     rcx, qword ptr cs:?s_pManagedRuntime@Tracker@@0PEAU_StateRuntime@xspmrt@@EA.Data1; xspmrt::_StateRuntime * Tracker::s_pManagedRuntime ...
0x140002db6  mov     rax, [rcx]
0x140002db9  mov     rax, [rax+18h]
0x140002dbd  call    cs:__guard_dispatch_icall_fptr
0x140002dc3  mov     ebx, eax
0x140002dc5  lea     rcx, ?s_pManagedRuntime@Tracker@@0PEAU_StateRuntime@xspmrt@@EA; struct IUnknown **
0x140002dcc  call    ?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z; ClearInterfaceFn(IUnknown * *)
0x140002dd1  cmp     [rsp+28h+arg_0], 0
0x140002dd6  jz      short loc_140002DDE
0x140002dd8  call    cs:__imp_CoUninitialize
0x140002dde  test    edi, edi
0x140002de0  jz      short loc_140002DEE
0x140002de2  lea     rcx, ?s_lockManagedRuntime@Tracker@@0VCReadWriteSpinLock@@A; this
0x140002de9  call    ?ReleaseWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseWriterLock(void)
0x140002dee  mov     eax, ebx
0x140002df0  mov     rbx, [rsp+28h+arg_8]
0x140002df5  add     rsp, 20h
0x140002df9  pop     rdi
0x140002dfa  retn
```
