# DllGetClassObject

- ea: `0x18000c4c0`
- end: `0x18000c564`
- name: `DllGetClassObject`
- size: `164`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001430`
- `0x18000c4c0`
- `0x18000d010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // edi
  _DWORD *v6; // rbx

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_TempSignedLicenseExchangeTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return v5;
}

```

## disassembly

```asm
0x18000c4c0  mov     [rsp+arg_0], rbx
0x18000c4c5  mov     [rsp+arg_8], rsi
0x18000c4ca  push    rdi
0x18000c4cb  sub     rsp, 20h
0x18000c4cf  mov     rdi, r8
0x18000c4d2  mov     rsi, rdx
0x18000c4d5  test    r8, r8
0x18000c4d8  jnz     short loc_18000C4E1
0x18000c4da  mov     edi, 80070057h
0x18000c4df  jmp     short loc_18000C552
0x18000c4e1  mov     qword ptr [r8], 0
0x18000c4e8  mov     rax, qword ptr cs:CLSID_TempSignedLicenseExchangeTask.Data1
0x18000c4ef  cmp     rax, [rcx]
0x18000c4f2  jnz     short loc_18000C54D
0x18000c4f4  mov     rax, qword ptr cs:CLSID_TempSignedLicenseExchangeTask.Data4
0x18000c4fb  cmp     rax, [rcx+8]
0x18000c4ff  jnz     short loc_18000C54D
0x18000c501  mov     ecx, 10h; Size
0x18000c506  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c50b  mov     rbx, rax
0x18000c50e  lea     rax, ??_7?$CWinTaskClassFactoryT@VCTempSignedLicenseExchangeTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::`vftable'
0x18000c515  mov     [rbx], rax
0x18000c518  mov     dword ptr [rbx+8], 1
0x18000c51f  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000c526  mov     rax, [rbx]
0x18000c529  mov     r8, rdi
0x18000c52c  mov     rdx, rsi
0x18000c52f  mov     rcx, rbx
0x18000c532  mov     rax, [rax]
0x18000c535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c53a  mov     edi, eax
0x18000c53c  mov     rax, [rbx]
0x18000c53f  mov     rcx, rbx
0x18000c542  mov     rax, [rax+10h]
0x18000c546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c54b  jmp     short loc_18000C552
0x18000c54d  mov     edi, 80040111h
0x18000c552  mov     rbx, [rsp+28h+arg_0]
0x18000c557  mov     eax, edi
0x18000c559  mov     rsi, [rsp+28h+arg_8]
0x18000c55e  add     rsp, 20h
0x18000c562  pop     rdi
0x18000c563  retn
```
