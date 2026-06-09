# DllCanUnloadNow

- ea: `0x18000aff0`
- end: `0x18000b02b`
- name: `DllCanUnloadNow`
- size: `59`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000832c`
- `0x18000aff0`
- `0x18001c010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000b024`

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
0x18000aff0  sub     rsp, 28h
0x18000aff4  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000aff9  mov     rdx, rax
0x18000affc  mov     rcx, [rax]
0x18000afff  mov     rax, [rcx+18h]
0x18000b003  mov     rcx, rdx
0x18000b006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b00b  test    eax, eax
0x18000b00d  jz      short loc_18000B019
0x18000b00f  mov     eax, 1
0x18000b014  add     rsp, 28h
0x18000b018  retn
0x18000b019  lea     rcx, gPFactory
0x18000b020  add     rsp, 28h
0x18000b024  jmp     cs:__imp_NdrDllCanUnloadNow
```
