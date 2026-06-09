# DllGetClassObject

- ea: `0x180002d60`
- end: `0x180002e10`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001028`
- `0x180002d60`
- `0x180004010`

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
  if ( *(_OWORD *)&CLSID_TimeSyncTask != *(_OWORD *)rclsid )
    return -2147221231;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return -2147024882;
  *(_QWORD *)v6 = &CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::`vftable';
  v6[2] = 1;
  _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
  v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x180002d60  mov     [rsp+arg_0], rbx
0x180002d65  mov     [rsp+arg_8], rsi
0x180002d6a  push    rdi
0x180002d6b  sub     rsp, 20h
0x180002d6f  mov     rbx, r8
0x180002d72  mov     rsi, rdx
0x180002d75  test    r8, r8
0x180002d78  jnz     short loc_180002D81
0x180002d7a  mov     ebx, 80070057h
0x180002d7f  jmp     short loc_180002DFE
0x180002d81  mov     qword ptr [r8], 0
0x180002d88  mov     rax, qword ptr cs:CLSID_TimeSyncTask.Data1
0x180002d8f  cmp     rax, [rcx]
0x180002d92  jnz     short loc_180002DF9
0x180002d94  mov     rax, qword ptr cs:CLSID_TimeSyncTask.Data4
0x180002d9b  cmp     rax, [rcx+8]
0x180002d9f  jnz     short loc_180002DF9
0x180002da1  mov     ecx, 10h; Size
0x180002da6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002dab  mov     rdi, rax
0x180002dae  test    rax, rax
0x180002db1  jz      short loc_180002DF2
0x180002db3  lea     rax, ??_7?$CWinTaskClassFactoryT@VCTimeSyncTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::`vftable'
0x180002dba  mov     [rdi], rax
0x180002dbd  mov     dword ptr [rdi+8], 1
0x180002dc4  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002dcb  mov     rax, [rdi]
0x180002dce  mov     r8, rbx
0x180002dd1  mov     rdx, rsi
0x180002dd4  mov     rcx, rdi
0x180002dd7  mov     rax, [rax]
0x180002dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ddf  mov     ebx, eax
0x180002de1  mov     rcx, rdi
0x180002de4  mov     rax, [rdi]
0x180002de7  mov     rax, [rax+10h]
0x180002deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df0  jmp     short loc_180002DFE
0x180002df2  mov     ebx, 8007000Eh
0x180002df7  jmp     short loc_180002DFE
0x180002df9  mov     ebx, 80040111h
0x180002dfe  mov     rsi, [rsp+28h+arg_8]
0x180002e03  mov     eax, ebx
0x180002e05  mov     rbx, [rsp+28h+arg_0]
0x180002e0a  add     rsp, 20h
0x180002e0e  pop     rdi
0x180002e0f  retn
```
