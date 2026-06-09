# DllCanUnloadNow

- ea: `0x18000e030`
- end: `0x18000e07d`
- name: `DllCanUnloadNow`
- size: `77`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000e030`
- `0x18000f010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000e04e`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000e04e`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  if ( _InterlockedCompareExchange(&CWinTaskHandler::s_cInstances, 0, 0) )
    return 1;
  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
  return result;
}

```

## disassembly

```asm
0x18000e030  sub     rsp, 28h
0x18000e034  xor     ecx, ecx
0x18000e036  xor     eax, eax
0x18000e038  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000e040  jz      short loc_18000E047
0x18000e042  lea     eax, [rcx+1]
0x18000e045  jmp     short loc_18000E078
0x18000e047  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000e04e  call    cs:__imp_NdrDllCanUnloadNow
0x18000e054  test    eax, eax
0x18000e056  jnz     short loc_18000E078
0x18000e058  mov     rax, cs:?_AtlModule@@3VCDsmApiModule@@A; CDsmApiModule _AtlModule
0x18000e05f  lea     rcx, ?_AtlModule@@3VCDsmApiModule@@A; CDsmApiModule _AtlModule
0x18000e066  mov     rax, [rax+18h]
0x18000e06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e06f  xor     ecx, ecx
0x18000e071  test    eax, eax
0x18000e073  setnz   cl
0x18000e076  mov     eax, ecx
0x18000e078  add     rsp, 28h
0x18000e07c  retn
```
