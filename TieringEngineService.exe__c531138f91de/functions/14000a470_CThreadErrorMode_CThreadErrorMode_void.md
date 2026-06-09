# CThreadErrorMode::~CThreadErrorMode(void)

- ea: `0x14000a470`
- end: `0x14000a489`
- name: `??1CThreadErrorMode@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ULONG *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400405e9`

## callees

- `0x14000a470`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x14000a47e`
- `ntdll!RtlSetThreadErrorMode` at `0x14000a47e`

## pseudocode

```c
void __fastcall CThreadErrorMode::~CThreadErrorMode(ULONG *this)
{
  if ( *((_BYTE *)this + 4) )
    RtlSetThreadErrorMode(*this, 0);
}

```

## disassembly

```asm
0x14000a470  sub     rsp, 28h
0x14000a474  cmp     byte ptr [rcx+4], 0
0x14000a478  jz      short loc_14000A484
0x14000a47a  mov     ecx, [rcx]; NewMode
0x14000a47c  xor     edx, edx; OldMode
0x14000a47e  call    cs:__imp_RtlSetThreadErrorMode
0x14000a484  add     rsp, 28h
0x14000a488  retn
```
