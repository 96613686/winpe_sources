# std::array<Mso::LoadMso::DllData,6>::~array<Mso::LoadMso::DllData,6>(void)

- ea: `0x140001670`
- end: `0x140001691`
- name: `??1?$array@UDllData@LoadMso@Mso@@$05@std@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140003290`

## callees

- `0x140001fc0`

## pseudocode

```c
void __fastcall std::array<Mso::LoadMso::DllData,6>::~array<Mso::LoadMso::DllData,6>(void *a1)
{
  `eh vector destructor iterator'(a1, 0x88u, 6u, (void (*)(void *))Mso::LoadMso::DllData::~DllData);
}

```

## disassembly

```asm
0x140001670  sub     rsp, 28h
0x140001674  lea     r9, ??1DllData@LoadMso@Mso@@QEAA@XZ; void (*)(void *)
0x14000167b  mov     edx, 88h; unsigned __int64
0x140001680  mov     r8d, 6; unsigned __int64
0x140001686  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14000168b  nop
0x14000168c  add     rsp, 28h
0x140001690  retn
```
