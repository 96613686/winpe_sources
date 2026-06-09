# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::~CMemoryPriority<1>(void)

- ea: `0x180072d6c`
- end: `0x180072daf`
- name: `??1?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003f3e0`

## callees

- `0x180072d6c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072d8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072d8a`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::~CMemoryPriority<1>(
        __int64 a1)
{
  void (__fastcall *v1)(HANDLE, _QWORD, int *, __int64); // rbx
  HANDLE CurrentThread; // rcx
  int v3; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(void (__fastcall **)(HANDLE, _QWORD, int *, __int64))a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(_DWORD *)(a1 + 16);
    CurrentThread = GetCurrentThread();
    v1(CurrentThread, 0, &v3, 4);
  }
}

```

## disassembly

```asm
0x180072d6c  push    rbx
0x180072d6e  sub     rsp, 40h
0x180072d72  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x180072d7b  mov     rbx, [rcx]
0x180072d7e  test    rbx, rbx
0x180072d81  jz      short loc_180072DA9
0x180072d83  mov     ecx, [rcx+10h]
0x180072d86  mov     [rsp+48h+arg_0], ecx
0x180072d8a  call    cs:__imp_GetCurrentThread
0x180072d90  mov     rcx, rax
0x180072d93  mov     r9d, 4
0x180072d99  lea     r8, [rsp+48h+arg_0]
0x180072d9e  xor     edx, edx
0x180072da0  mov     rax, rbx
0x180072da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072da8  nop
0x180072da9  add     rsp, 40h
0x180072dad  pop     rbx
0x180072dae  retn
```
