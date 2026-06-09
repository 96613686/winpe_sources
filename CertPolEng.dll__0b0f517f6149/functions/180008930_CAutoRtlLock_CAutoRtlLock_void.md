# CAutoRtlLock::~CAutoRtlLock(void)

- ea: `0x180008930`
- end: `0x180008941`
- name: `??1CAutoRtlLock@@QEAA@XZ`
- size: `17`
- prototype: `void __fastcall(PRTL_RESOURCE *this)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001a4e0`
- `0x18001a520`
- `0x18001a560`
- `0x18001a5c0`
- `0x18001a5e0`
- `0x18001aa98`

## callees

- `0x180008930`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180008939`

## pseudocode

```c
void __fastcall CAutoRtlLock::~CAutoRtlLock(PRTL_RESOURCE *this)
{
  if ( *((_BYTE *)this + 8) )
    RtlReleaseResource(*this);
}

```

## disassembly

```asm
0x180008930  cmp     byte ptr [rcx+8], 0
0x180008934  jz      short locret_180008940
0x180008936  mov     rcx, [rcx]
0x180008939  jmp     cs:__imp_RtlReleaseResource
0x180008940  retn
```
