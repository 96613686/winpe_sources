# DllCanUnloadNow

- ea: `0x180006b00`
- end: `0x180006b3b`
- name: `DllCanUnloadNow`
- size: `59`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004620`
- `0x180006b00`
- `0x18000b010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180006b2a`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 *v0; // rax

  v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  if ( (*(unsigned int (__fastcall **)(__int64 *))(*v0 + 24))(v0) )
    return 1;
  else
    return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x180006b00  sub     rsp, 28h
0x180006b04  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180006b09  mov     rdx, rax
0x180006b0c  mov     rcx, [rax]
0x180006b0f  mov     rax, [rcx+18h]
0x180006b13  mov     rcx, rdx
0x180006b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b1b  test    eax, eax
0x180006b1d  jnz     short loc_180006B31
0x180006b1f  lea     rcx, gPFactory
0x180006b26  add     rsp, 28h
0x180006b2a  jmp     cs:__imp_NdrDllCanUnloadNow
0x180006b31  mov     eax, 1
0x180006b36  add     rsp, 28h
0x180006b3a  retn
```
