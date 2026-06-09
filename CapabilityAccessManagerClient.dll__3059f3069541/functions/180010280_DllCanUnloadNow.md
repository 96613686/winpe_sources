# DllCanUnloadNow

- ea: `0x180010280`
- end: `0x1800102b0`
- name: `DllCanUnloadNow`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b2d4`
- `0x18000ee90`
- `0x180010280`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18001028b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18001028b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax
  Microsoft::WRL::Details *v1; // rax
  struct Microsoft::WRL::Details::ModuleBase *v2; // rdx
  bool v3; // r9

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
  {
    v1 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
    return !Microsoft::WRL::Details::TerminateMap(v1, v2, 0, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180010280  sub     rsp, 28h
0x180010284  lea     rcx, gPFactory; pPSFactoryBuffer
0x18001028b  call    cs:__imp_NdrDllCanUnloadNow
0x180010291  test    eax, eax
0x180010293  jnz     short loc_1800102AB
0x180010295  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18001029a  xor     r8d, r8d; unsigned __int16 *
0x18001029d  mov     rcx, rax; this
0x1800102a0  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x1800102a5  movzx   eax, al
0x1800102a8  xor     eax, 1
0x1800102ab  add     rsp, 28h
0x1800102af  retn
```
