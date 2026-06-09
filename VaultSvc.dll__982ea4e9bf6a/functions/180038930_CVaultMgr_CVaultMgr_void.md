# CVaultMgr::~CVaultMgr(void)

- ea: `0x180038930`
- end: `0x180038955`
- name: `??1CVaultMgr@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(struct _RTL_RESOURCE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004cce0`

## callees

- `0x180038930`
- `0x18003895c`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180038948`
- `ntdll!RtlDeleteResource` at `0x180038948`

## pseudocode

```c
void __fastcall CVaultMgr::~CVaultMgr(struct _RTL_RESOURCE *this)
{
  CVaultMgr::Uninitialize((CVaultMgr *)this);
  if ( LOBYTE(this->DebugInfo) )
    RtlDeleteResource(this + 1);
}

```

## disassembly

```asm
0x180038930  push    rbx
0x180038932  sub     rsp, 20h
0x180038936  mov     rbx, rcx
0x180038939  call    ?Uninitialize@CVaultMgr@@QEAAXXZ; CVaultMgr::Uninitialize(void)
0x18003893e  cmp     byte ptr [rbx+58h], 0
0x180038942  jz      short loc_18003894F
0x180038944  lea     rcx, [rbx+60h]; Resource
0x180038948  call    cs:__imp_RtlDeleteResource
0x18003894e  nop
0x18003894f  add     rsp, 20h
0x180038953  pop     rbx
0x180038954  retn
```
