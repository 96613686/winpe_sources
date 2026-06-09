# DllGetClassObject

- ea: `0x18000c660`
- end: `0x18000c710`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800014b4`
- `0x18000c660`
- `0x180012010`

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
  if ( *(_OWORD *)&CLSID_PITRTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CPITRTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x18000c660  mov     [rsp+arg_0], rbx
0x18000c665  mov     [rsp+arg_8], rsi
0x18000c66a  push    rdi
0x18000c66b  sub     rsp, 20h
0x18000c66f  mov     rbx, r8
0x18000c672  mov     rsi, rdx
0x18000c675  test    r8, r8
0x18000c678  jnz     short loc_18000C681
0x18000c67a  mov     ebx, 80070057h
0x18000c67f  jmp     short loc_18000C6FE
0x18000c681  mov     qword ptr [r8], 0
0x18000c688  mov     rax, qword ptr cs:CLSID_PITRTask.Data1
0x18000c68f  cmp     rax, [rcx]
0x18000c692  jnz     short loc_18000C6F9
0x18000c694  mov     rax, qword ptr cs:CLSID_PITRTask.Data4
0x18000c69b  cmp     rax, [rcx+8]
0x18000c69f  jnz     short loc_18000C6F9
0x18000c6a1  mov     ecx, 10h; Size
0x18000c6a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c6ab  mov     rdi, rax
0x18000c6ae  test    rax, rax
0x18000c6b1  jz      short loc_18000C6F2
0x18000c6b3  lea     rax, ??_7?$CWinTaskClassFactoryT@VCPITRTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CPITRTaskHandler,1>::`vftable'
0x18000c6ba  mov     [rdi], rax
0x18000c6bd  mov     dword ptr [rdi+8], 1
0x18000c6c4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000c6cb  mov     rax, [rdi]
0x18000c6ce  mov     r8, rbx
0x18000c6d1  mov     rdx, rsi
0x18000c6d4  mov     rcx, rdi
0x18000c6d7  mov     rax, [rax]
0x18000c6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6df  mov     ebx, eax
0x18000c6e1  mov     rcx, rdi
0x18000c6e4  mov     rax, [rdi]
0x18000c6e7  mov     rax, [rax+10h]
0x18000c6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6f0  jmp     short loc_18000C6FE
0x18000c6f2  mov     ebx, 8007000Eh
0x18000c6f7  jmp     short loc_18000C6FE
0x18000c6f9  mov     ebx, 80040111h
0x18000c6fe  mov     rsi, [rsp+28h+arg_8]
0x18000c703  mov     eax, ebx
0x18000c705  mov     rbx, [rsp+28h+arg_0]
0x18000c70a  add     rsp, 20h
0x18000c70e  pop     rdi
0x18000c70f  retn
```
