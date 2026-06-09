# AERTAddMemoryToHeap(void *,unsigned __int64)

- ea: `0x140083ec0`
- end: `0x140083f47`
- name: `?AERTAddMemoryToHeap@@YAXPEAX_K@Z`
- size: `135`
- prototype: `void(void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000fff4`
- `0x140010660`
- `0x1400355a0`
- `0x1400771b0`

## callees

- `0x14000faf8`
- `0x140012ed8`
- `0x140083ec0`

## import_xrefs

- `ntdll!RtlExtendMemoryBlockLookaside` at `0x140083ed5`
- `ntdll!RtlExtendMemoryBlockLookaside` at `0x140083ef6`
- `ntdll!RtlExtendMemoryBlockLookaside` at `0x140083ed5`
- `ntdll!RtlExtendMemoryBlockLookaside` at `0x140083ef6`

## pseudocode

```c
void __fastcall AERTAddMemoryToHeap(void *a1, unsigned __int64 a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // r8d

  if ( (unsigned int)((__int64 (*)(void))RtlExtendMemoryBlockLookaside)() == -1073741663
    && (int)IncreaseProcessWorkingSet(a2) >= 0 )
  {
    RtlExtendMemoryBlockLookaside(a1, a2);
  }
  if ( (byte_1400E7E41 & 4) != 0 )
    McTemplateU0pqpqqqqqq_EventWriteTransfer(v5, v4, v6, 5, (char)a1, a2, 0, 0);
}

```

## disassembly

```asm
0x140083ec0  mov     [rsp+arg_0], rbx
0x140083ec5  mov     [rsp+arg_8], rsi
0x140083eca  push    rdi
0x140083ecb  sub     rsp, 60h
0x140083ecf  mov     rbx, rdx
0x140083ed2  mov     rdi, rcx
0x140083ed5  call    cs:__imp_RtlExtendMemoryBlockLookaside
0x140083edb  mov     esi, eax
0x140083edd  cmp     eax, 0C00000A1h
0x140083ee2  jnz     short loc_140083EFE
0x140083ee4  mov     rcx, rbx; unsigned __int64
0x140083ee7  call    ?IncreaseProcessWorkingSet@@YAJ_K@Z; IncreaseProcessWorkingSet(unsigned __int64)
0x140083eec  test    eax, eax
0x140083eee  js      short loc_140083EFE
0x140083ef0  mov     rdx, rbx
0x140083ef3  mov     rcx, rdi
0x140083ef6  call    cs:__imp_RtlExtendMemoryBlockLookaside
0x140083efc  mov     esi, eax
0x140083efe  test    cs:byte_1400E7E41, 4
0x140083f05  jz      short loc_140083F37
0x140083f07  mov     [rsp+68h+var_18], esi
0x140083f0b  mov     r9d, 5
0x140083f11  mov     [rsp+68h+var_20], 0
0x140083f19  mov     [rsp+68h+var_30], 0
0x140083f21  mov     [rsp+68h+var_38], 0
0x140083f29  mov     [rsp+68h+var_40], ebx
0x140083f2d  mov     [rsp+68h+var_48], rdi
0x140083f32  call    McTemplateU0pqpqqqqqq_EventWriteTransfer
0x140083f37  mov     rbx, [rsp+68h+arg_0]
0x140083f3c  mov     rsi, [rsp+68h+arg_8]
0x140083f41  add     rsp, 60h
0x140083f45  pop     rdi
0x140083f46  retn
```
