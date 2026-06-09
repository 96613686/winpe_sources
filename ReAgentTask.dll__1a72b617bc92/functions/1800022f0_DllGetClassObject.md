# DllGetClassObject

- ea: `0x1800022f0`
- end: `0x1800023a0`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x1800022f0`
- `0x180003010`

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
  if ( *(_OWORD *)&CLSID_ReAgentTaskHandler != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CReAgentTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x1800022f0  mov     [rsp+arg_0], rbx
0x1800022f5  mov     [rsp+arg_8], rsi
0x1800022fa  push    rdi
0x1800022fb  sub     rsp, 20h
0x1800022ff  mov     rbx, r8
0x180002302  mov     rsi, rdx
0x180002305  test    r8, r8
0x180002308  jnz     short loc_180002311
0x18000230a  mov     ebx, 80070057h
0x18000230f  jmp     short loc_18000238E
0x180002311  mov     qword ptr [r8], 0
0x180002318  mov     rax, qword ptr cs:CLSID_ReAgentTaskHandler.Data1
0x18000231f  cmp     rax, [rcx]
0x180002322  jnz     short loc_180002389
0x180002324  mov     rax, qword ptr cs:CLSID_ReAgentTaskHandler.Data4
0x18000232b  cmp     rax, [rcx+8]
0x18000232f  jnz     short loc_180002389
0x180002331  mov     ecx, 10h; Size
0x180002336  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000233b  mov     rdi, rax
0x18000233e  test    rax, rax
0x180002341  jz      short loc_180002382
0x180002343  lea     rax, ??_7?$CWinTaskClassFactoryT@VCReAgentTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CReAgentTaskHandler,1>::`vftable'
0x18000234a  mov     [rdi], rax
0x18000234d  mov     dword ptr [rdi+8], 1
0x180002354  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000235b  mov     rax, [rdi]
0x18000235e  mov     r8, rbx
0x180002361  mov     rdx, rsi
0x180002364  mov     rcx, rdi
0x180002367  mov     rax, [rax]
0x18000236a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000236f  mov     ebx, eax
0x180002371  mov     rax, [rdi]
0x180002374  mov     rcx, rdi
0x180002377  mov     rax, [rax+10h]
0x18000237b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002380  jmp     short loc_18000238E
0x180002382  mov     ebx, 8007000Eh
0x180002387  jmp     short loc_18000238E
0x180002389  mov     ebx, 80040111h
0x18000238e  mov     rsi, [rsp+28h+arg_8]
0x180002393  mov     eax, ebx
0x180002395  mov     rbx, [rsp+28h+arg_0]
0x18000239a  add     rsp, 20h
0x18000239e  pop     rdi
0x18000239f  retn
```
