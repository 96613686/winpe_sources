# DllGetClassObject

- ea: `0x18000f970`
- end: `0x18000fa14`
- name: `DllGetClassObject`
- size: `164`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002324`
- `0x18000f970`
- `0x180012010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // edi
  _DWORD *v6; // rbx

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_AppListBackupLauncher != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CAppListBackupLauncher,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return v5;
}

```

## disassembly

```asm
0x18000f970  mov     [rsp+arg_0], rbx
0x18000f975  mov     [rsp+arg_8], rsi
0x18000f97a  push    rdi
0x18000f97b  sub     rsp, 20h
0x18000f97f  mov     rdi, r8
0x18000f982  mov     rsi, rdx
0x18000f985  test    r8, r8
0x18000f988  jnz     short loc_18000F991
0x18000f98a  mov     edi, 80070057h
0x18000f98f  jmp     short loc_18000FA02
0x18000f991  mov     qword ptr [r8], 0
0x18000f998  mov     rax, qword ptr cs:CLSID_AppListBackupLauncher.Data1
0x18000f99f  cmp     rax, [rcx]
0x18000f9a2  jnz     short loc_18000F9FD
0x18000f9a4  mov     rax, qword ptr cs:CLSID_AppListBackupLauncher.Data4
0x18000f9ab  cmp     rax, [rcx+8]
0x18000f9af  jnz     short loc_18000F9FD
0x18000f9b1  mov     ecx, 10h; Size
0x18000f9b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f9bb  mov     rbx, rax
0x18000f9be  lea     rax, ??_7?$CWinTaskClassFactoryT@VCAppListBackupLauncher@@$00@@6B@; const CWinTaskClassFactoryT<CAppListBackupLauncher,1>::`vftable'
0x18000f9c5  mov     [rbx], rax
0x18000f9c8  mov     dword ptr [rbx+8], 1
0x18000f9cf  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000f9d6  mov     rax, [rbx]
0x18000f9d9  mov     r8, rdi
0x18000f9dc  mov     rdx, rsi
0x18000f9df  mov     rcx, rbx
0x18000f9e2  mov     rax, [rax]
0x18000f9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9ea  mov     edi, eax
0x18000f9ec  mov     rax, [rbx]
0x18000f9ef  mov     rcx, rbx
0x18000f9f2  mov     rax, [rax+10h]
0x18000f9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9fb  jmp     short loc_18000FA02
0x18000f9fd  mov     edi, 80040111h
0x18000fa02  mov     rbx, [rsp+28h+arg_0]
0x18000fa07  mov     eax, edi
0x18000fa09  mov     rsi, [rsp+28h+arg_8]
0x18000fa0e  add     rsp, 20h
0x18000fa12  pop     rdi
0x18000fa13  retn
```
