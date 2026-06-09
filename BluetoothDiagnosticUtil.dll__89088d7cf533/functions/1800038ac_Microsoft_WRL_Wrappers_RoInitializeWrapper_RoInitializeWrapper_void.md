# Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper(void)

- ea: `0x1800038ac`
- end: `0x1800038c7`
- name: `??1RoInitializeWrapper@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::RoInitializeWrapper *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a6a3`
- `0x18000a747`

## callees

- `0x1800038ac`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800038b5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800038b5`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper(
        Microsoft::WRL::Wrappers::RoInitializeWrapper *this)
{
  if ( *(int *)this >= 0 )
    RoUninitialize();
}

```

## disassembly

```asm
0x1800038ac  sub     rsp, 28h
0x1800038b0  cmp     dword ptr [rcx], 0
0x1800038b3  jl      short loc_1800038C1
0x1800038b5  call    cs:__imp_RoUninitialize
0x1800038bc  nop     dword ptr [rax+rax+00h]
0x1800038c1  add     rsp, 28h
0x1800038c5  retn
```
