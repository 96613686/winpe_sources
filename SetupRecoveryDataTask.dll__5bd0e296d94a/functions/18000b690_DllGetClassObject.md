# DllGetClassObject

- ea: `0x18000b690`
- end: `0x18000b740`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001404`
- `0x18000b690`
- `0x18000d010`

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
  if ( *(_OWORD *)&CLSID_SetupRecoveryDataTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x18000b690  mov     [rsp+arg_0], rbx
0x18000b695  mov     [rsp+arg_8], rsi
0x18000b69a  push    rdi
0x18000b69b  sub     rsp, 20h
0x18000b69f  mov     rbx, r8
0x18000b6a2  mov     rsi, rdx
0x18000b6a5  test    r8, r8
0x18000b6a8  jnz     short loc_18000B6B1
0x18000b6aa  mov     ebx, 80070057h
0x18000b6af  jmp     short loc_18000B72E
0x18000b6b1  mov     qword ptr [r8], 0
0x18000b6b8  mov     rax, qword ptr cs:CLSID_SetupRecoveryDataTask.Data1
0x18000b6bf  cmp     rax, [rcx]
0x18000b6c2  jnz     short loc_18000B729
0x18000b6c4  mov     rax, qword ptr cs:CLSID_SetupRecoveryDataTask.Data4
0x18000b6cb  cmp     rax, [rcx+8]
0x18000b6cf  jnz     short loc_18000B729
0x18000b6d1  mov     ecx, 10h; Size
0x18000b6d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b6db  mov     rdi, rax
0x18000b6de  test    rax, rax
0x18000b6e1  jz      short loc_18000B722
0x18000b6e3  lea     rax, ??_7?$CWinTaskClassFactoryT@VSetupRecoveryTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::`vftable'
0x18000b6ea  mov     [rdi], rax
0x18000b6ed  mov     dword ptr [rdi+8], 1
0x18000b6f4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000b6fb  mov     rax, [rdi]
0x18000b6fe  mov     r8, rbx
0x18000b701  mov     rdx, rsi
0x18000b704  mov     rcx, rdi
0x18000b707  mov     rax, [rax]
0x18000b70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b70f  mov     ebx, eax
0x18000b711  mov     rcx, rdi
0x18000b714  mov     rax, [rdi]
0x18000b717  mov     rax, [rax+10h]
0x18000b71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b720  jmp     short loc_18000B72E
0x18000b722  mov     ebx, 8007000Eh
0x18000b727  jmp     short loc_18000B72E
0x18000b729  mov     ebx, 80040111h
0x18000b72e  mov     rsi, [rsp+28h+arg_8]
0x18000b733  mov     eax, ebx
0x18000b735  mov     rbx, [rsp+28h+arg_0]
0x18000b73a  add     rsp, 20h
0x18000b73e  pop     rdi
0x18000b73f  retn
```
