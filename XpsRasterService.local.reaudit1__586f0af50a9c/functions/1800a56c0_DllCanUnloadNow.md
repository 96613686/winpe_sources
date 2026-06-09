# DllCanUnloadNow

- ea: `0x1800a56c0`
- end: `0x1800a5703`
- name: `DllCanUnloadNow`
- size: `67`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800a0a18`
- `0x1800a56c0`
- `0x1800c3010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800a56f2`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v0 + 24LL))(v0) || g_nObjects )
    return 1;
  else
    return NdrDllCanUnloadNow((CStdPSFactoryBuffer *)gPFactory);
}

```

## disassembly

```asm
0x1800a56c0  sub     rsp, 28h
0x1800a56c4  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800a56c9  mov     rdx, rax
0x1800a56cc  mov     rcx, [rax]
0x1800a56cf  mov     rax, [rcx+18h]
0x1800a56d3  mov     rcx, rdx
0x1800a56d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a56db  test    eax, eax
0x1800a56dd  jnz     short loc_1800A56F9
0x1800a56df  cmp     cs:?g_nObjects@@3JA, eax; long g_nObjects
0x1800a56e5  jnz     short loc_1800A56F9
0x1800a56e7  lea     rcx, gPFactory
0x1800a56ee  add     rsp, 28h
0x1800a56f2  jmp     cs:__imp_NdrDllCanUnloadNow
0x1800a56f9  mov     eax, 1
0x1800a56fe  add     rsp, 28h
0x1800a5702  retn
```
