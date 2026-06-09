# DllGetClassObject

- ea: `0x180007930`
- end: `0x1800079e0`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001a64`
- `0x180007930`
- `0x180009010`

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
  if ( *(_OWORD *)&CLSID_EcoScoreTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x180007930  mov     [rsp+arg_0], rbx
0x180007935  mov     [rsp+arg_8], rsi
0x18000793a  push    rdi
0x18000793b  sub     rsp, 20h
0x18000793f  mov     rbx, r8
0x180007942  mov     rsi, rdx
0x180007945  test    r8, r8
0x180007948  jnz     short loc_180007951
0x18000794a  mov     ebx, 80070057h
0x18000794f  jmp     short loc_1800079CE
0x180007951  mov     qword ptr [r8], 0
0x180007958  mov     rax, qword ptr cs:CLSID_EcoScoreTask.Data1
0x18000795f  cmp     rax, [rcx]
0x180007962  jnz     short loc_1800079C9
0x180007964  mov     rax, qword ptr cs:CLSID_EcoScoreTask.Data4
0x18000796b  cmp     rax, [rcx+8]
0x18000796f  jnz     short loc_1800079C9
0x180007971  mov     ecx, 10h; Size
0x180007976  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000797b  mov     rdi, rax
0x18000797e  test    rax, rax
0x180007981  jz      short loc_1800079C2
0x180007983  lea     rax, ??_7?$CWinTaskClassFactoryT@VCEcoScoreTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::`vftable'
0x18000798a  mov     [rdi], rax
0x18000798d  mov     dword ptr [rdi+8], 1
0x180007994  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000799b  mov     rax, [rdi]
0x18000799e  mov     r8, rbx
0x1800079a1  mov     rdx, rsi
0x1800079a4  mov     rcx, rdi
0x1800079a7  mov     rax, [rax]
0x1800079aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079af  mov     ebx, eax
0x1800079b1  mov     rax, [rdi]
0x1800079b4  mov     rcx, rdi
0x1800079b7  mov     rax, [rax+10h]
0x1800079bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079c0  jmp     short loc_1800079CE
0x1800079c2  mov     ebx, 8007000Eh
0x1800079c7  jmp     short loc_1800079CE
0x1800079c9  mov     ebx, 80040111h
0x1800079ce  mov     rsi, [rsp+28h+arg_8]
0x1800079d3  mov     eax, ebx
0x1800079d5  mov     rbx, [rsp+28h+arg_0]
0x1800079da  add     rsp, 20h
0x1800079de  pop     rdi
0x1800079df  retn
```
