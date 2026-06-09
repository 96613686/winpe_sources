# DllCanUnloadNow

- ea: `0x1800087d0`
- end: `0x18000880b`
- name: `DllCanUnloadNow`
- size: `59`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800059f8`
- `0x1800087d0`
- `0x180027010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800087fa`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v0 + 24LL))(v0) )
    return 1;
  else
    return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x1800087d0  sub     rsp, 28h
0x1800087d4  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800087d9  mov     rdx, rax
0x1800087dc  mov     rcx, [rax]
0x1800087df  mov     rax, [rcx+18h]
0x1800087e3  mov     rcx, rdx
0x1800087e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087eb  test    eax, eax
0x1800087ed  jnz     short loc_180008801
0x1800087ef  lea     rcx, gPFactory
0x1800087f6  add     rsp, 28h
0x1800087fa  jmp     cs:__imp_NdrDllCanUnloadNow
0x180008801  mov     eax, 1
0x180008806  add     rsp, 28h
0x18000880a  retn
```
