# SafeAllocaFreeToHeap

- ea: `0x140006720`
- end: `0x140006739`
- name: `SafeAllocaFreeToHeap`
- size: `25`
- prototype: `void(void *)`
- caller_count: `51`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140003af0`
- `0x140003e58`
- `0x1400041d0`
- `0x1400042d0`
- `0x1400043c0`
- `0x1400044d0`
- `0x140004b70`
- `0x140004e40`
- `0x140005280`
- `0x140005820`
- `0x140006390`
- `0x140008538`
- `0x14000e070`
- `0x14000f520`
- `0x1400145ac`
- `0x140014cd0`
- `0x140015b90`
- `0x140016ac0`
- `0x140017a40`
- `0x1400180d0`
- `0x140018880`
- `0x14001a69c`
- `0x14001a778`
- `0x14001a9a4`
- `0x14001aa00`
- `0x14001aa2c`
- `0x14001ab38`
- `0x14001b094`
- `0x14001b45c`
- `0x14001bad8`
- `0x14001d584`
- `0x14001d9ac`
- `0x14001de00`
- `0x14001e0e0`
- `0x14001efd0`
- `0x14001f1d4`
- `0x140034700`
- `0x1400348a0`
- `0x140034a40`
- `0x140034c60`
- `0x140034f00`
- `0x1400350e0`
- `0x1400353e0`
- `0x140035610`
- `0x140035770`
- `0x140035ec0`
- `0x14003623c`
- `0x140036330`
- `0x140036570`
- `0x140036b00`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140006732`

## pseudocode

```c
void __fastcall SafeAllocaFreeToHeap(void *a1)
{
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x140006720  mov     rax, gs:60h
0x140006729  mov     r8, rcx
0x14000672c  xor     edx, edx
0x14000672e  mov     rcx, [rax+30h]
0x140006732  jmp     cs:__imp_RtlFreeHeap
```
