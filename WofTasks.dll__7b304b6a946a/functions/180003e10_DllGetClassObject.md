# DllGetClassObject

- ea: `0x180003e10`
- end: `0x180003ec0`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180003e10`
- `0x180006010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // ebx
  _DWORD *v6; // rax
  _DWORD *v7; // rdi

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_WofTasks != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CWofTasksHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x180003e10  mov     [rsp+arg_0], rbx
0x180003e15  mov     [rsp+arg_8], rsi
0x180003e1a  push    rdi
0x180003e1b  sub     rsp, 20h
0x180003e1f  mov     rbx, r8
0x180003e22  mov     rsi, rdx
0x180003e25  test    r8, r8
0x180003e28  jnz     short loc_180003E31
0x180003e2a  mov     ebx, 80070057h
0x180003e2f  jmp     short loc_180003EAE
0x180003e31  mov     qword ptr [r8], 0
0x180003e38  mov     rax, qword ptr cs:CLSID_WofTasks.Data1
0x180003e3f  cmp     rax, [rcx]
0x180003e42  jnz     short loc_180003EA9
0x180003e44  mov     rax, qword ptr cs:CLSID_WofTasks.Data4
0x180003e4b  cmp     rax, [rcx+8]
0x180003e4f  jnz     short loc_180003EA9
0x180003e51  mov     ecx, 10h; Size
0x180003e56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e5b  mov     rdi, rax
0x180003e5e  test    rax, rax
0x180003e61  jz      short loc_180003EA2
0x180003e63  lea     rax, ??_7?$CWinTaskClassFactoryT@VCWofTasksHandler@@$00@@6B@; const CWinTaskClassFactoryT<CWofTasksHandler,1>::`vftable'
0x180003e6a  mov     [rdi], rax
0x180003e6d  mov     dword ptr [rdi+8], 1
0x180003e74  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180003e7b  mov     rax, [rdi]
0x180003e7e  mov     r8, rbx
0x180003e81  mov     rdx, rsi
0x180003e84  mov     rcx, rdi
0x180003e87  mov     rax, [rax]
0x180003e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e8f  mov     ebx, eax
0x180003e91  mov     rax, [rdi]
0x180003e94  mov     rcx, rdi
0x180003e97  mov     rax, [rax+10h]
0x180003e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea0  jmp     short loc_180003EAE
0x180003ea2  mov     ebx, 8007000Eh
0x180003ea7  jmp     short loc_180003EAE
0x180003ea9  mov     ebx, 80040111h
0x180003eae  mov     rsi, [rsp+28h+arg_8]
0x180003eb3  mov     eax, ebx
0x180003eb5  mov     rbx, [rsp+28h+arg_0]
0x180003eba  add     rsp, 20h
0x180003ebe  pop     rdi
0x180003ebf  retn
```
