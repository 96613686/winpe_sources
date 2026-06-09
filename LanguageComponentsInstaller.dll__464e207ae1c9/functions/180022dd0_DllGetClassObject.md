# DllGetClassObject

- ea: `0x180022dd0`
- end: `0x180022e8a`
- name: `DllGetClassObject`
- size: `186`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003588`
- `0x180022dd0`
- `0x18002a010`

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
  if ( *(_OWORD *)&CLSID_LanguageComponentsInstaller != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x180022dd0  mov     [rsp+arg_0], rbx
0x180022dd5  mov     [rsp+arg_8], rsi
0x180022dda  push    rdi
0x180022ddb  sub     rsp, 20h
0x180022ddf  mov     rbx, r8
0x180022de2  mov     rsi, rdx
0x180022de5  test    r8, r8
0x180022de8  jnz     short loc_180022DF4
0x180022dea  mov     ebx, 80070057h
0x180022def  jmp     loc_180022E78
0x180022df4  mov     qword ptr [r8], 0
0x180022dfb  mov     rax, qword ptr cs:CLSID_LanguageComponentsInstaller.Data1
0x180022e02  cmp     rax, [rcx]
0x180022e05  jnz     short loc_180022E73
0x180022e07  mov     rax, qword ptr cs:CLSID_LanguageComponentsInstaller.Data4
0x180022e0e  cmp     rax, [rcx+8]
0x180022e12  jnz     short loc_180022E73
0x180022e14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022e1b  mov     ecx, 10h; unsigned __int64
0x180022e20  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022e25  mov     rdi, rax
0x180022e28  test    rax, rax
0x180022e2b  jz      short loc_180022E6C
0x180022e2d  lea     rax, ??_7?$CWinTaskClassFactoryT@VCLanguageComponentsInstallerHandler@@$00@@6B@; const CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::`vftable'
0x180022e34  mov     [rdi], rax
0x180022e37  mov     dword ptr [rdi+8], 1
0x180022e3e  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180022e45  mov     rax, [rdi]
0x180022e48  mov     r8, rbx
0x180022e4b  mov     rdx, rsi
0x180022e4e  mov     rcx, rdi
0x180022e51  mov     rax, [rax]
0x180022e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e59  mov     ebx, eax
0x180022e5b  mov     rcx, rdi
0x180022e5e  mov     rax, [rdi]
0x180022e61  mov     rax, [rax+10h]
0x180022e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e6a  jmp     short loc_180022E78
0x180022e6c  mov     ebx, 8007000Eh
0x180022e71  jmp     short loc_180022E78
0x180022e73  mov     ebx, 80040111h
0x180022e78  mov     rsi, [rsp+28h+arg_8]
0x180022e7d  mov     eax, ebx
0x180022e7f  mov     rbx, [rsp+28h+arg_0]
0x180022e84  add     rsp, 20h
0x180022e88  pop     rdi
0x180022e89  retn
```
