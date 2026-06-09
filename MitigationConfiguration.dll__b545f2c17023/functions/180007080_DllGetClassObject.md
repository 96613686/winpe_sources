# DllGetClassObject

- ea: `0x180007080`
- end: `0x180007124`
- name: `DllGetClassObject`
- size: `164`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001c24`
- `0x180007080`
- `0x180015010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // edi
  _DWORD *v6; // rbx

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_ExploitGuardNotificationTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<ExploitGuardNotificationTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return v5;
}

```

## disassembly

```asm
0x180007080  mov     [rsp+arg_0], rbx
0x180007085  mov     [rsp+arg_8], rsi
0x18000708a  push    rdi
0x18000708b  sub     rsp, 20h
0x18000708f  mov     rdi, r8
0x180007092  mov     rsi, rdx
0x180007095  test    r8, r8
0x180007098  jnz     short loc_1800070A1
0x18000709a  mov     edi, 80070057h
0x18000709f  jmp     short loc_180007112
0x1800070a1  mov     qword ptr [r8], 0
0x1800070a8  mov     rax, qword ptr cs:CLSID_ExploitGuardNotificationTask.Data1
0x1800070af  cmp     rax, [rcx]
0x1800070b2  jnz     short loc_18000710D
0x1800070b4  mov     rax, qword ptr cs:CLSID_ExploitGuardNotificationTask.Data4
0x1800070bb  cmp     rax, [rcx+8]
0x1800070bf  jnz     short loc_18000710D
0x1800070c1  mov     ecx, 10h; Size
0x1800070c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800070cb  mov     rbx, rax
0x1800070ce  lea     rax, ??_7?$CWinTaskClassFactoryT@VExploitGuardNotificationTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<ExploitGuardNotificationTaskHandler,1>::`vftable'
0x1800070d5  mov     [rbx], rax
0x1800070d8  mov     dword ptr [rbx+8], 1
0x1800070df  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800070e6  mov     rax, [rbx]
0x1800070e9  mov     r8, rdi
0x1800070ec  mov     rdx, rsi
0x1800070ef  mov     rcx, rbx
0x1800070f2  mov     rax, [rax]
0x1800070f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070fa  mov     edi, eax
0x1800070fc  mov     rax, [rbx]
0x1800070ff  mov     rcx, rbx
0x180007102  mov     rax, [rax+10h]
0x180007106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000710b  jmp     short loc_180007112
0x18000710d  mov     edi, 80040111h
0x180007112  mov     rbx, [rsp+28h+arg_0]
0x180007117  mov     eax, edi
0x180007119  mov     rsi, [rsp+28h+arg_8]
0x18000711e  add     rsp, 20h
0x180007122  pop     rdi
0x180007123  retn
```
