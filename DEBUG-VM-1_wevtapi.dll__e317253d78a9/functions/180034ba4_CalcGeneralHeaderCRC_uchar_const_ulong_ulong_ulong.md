# CalcGeneralHeaderCRC(uchar const *,ulong,ulong,ulong)

- ea: `0x180034ba4`
- end: `0x180034be3`
- name: `?CalcGeneralHeaderCRC@@YAKPEBEKKK@Z`
- size: `63`
- prototype: `unsigned int __fastcall(PUCHAR Buffer, unsigned int, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033b9c`
- `0x180033fa8`
- `0x180034d34`
- `0x180034e38`
- `0x180035884`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x180034bbf`
- `ntdll!RtlComputeCrc32` at `0x180034bbf`
- `ntdll!RtlComputeCrc32` at `0x180034bdc`

## pseudocode

```c
ULONG __fastcall CalcGeneralHeaderCRC(PUCHAR Buffer, __int64 a2, __int64 a3, int a4)
{
  ULONG v6; // eax

  v6 = RtlComputeCrc32(0, Buffer, 0x78u);
  return RtlComputeCrc32(v6, Buffer + 128, a4 - 128);
}

```

## disassembly

```asm
0x180034ba4  mov     [rsp+arg_0], rbx
0x180034ba9  push    rdi
0x180034baa  sub     rsp, 20h
0x180034bae  mov     rbx, rcx
0x180034bb1  mov     rdx, rcx; Buffer
0x180034bb4  xor     ecx, ecx; InitialCrc
0x180034bb6  mov     r8d, 78h ; 'x'; Length
0x180034bbc  mov     edi, r9d
0x180034bbf  call    cs:__imp_RtlComputeCrc32
0x180034bc5  mov     ecx, eax
0x180034bc7  lea     r8d, [rdi-80h]
0x180034bcb  lea     rdx, [rbx+80h]
0x180034bd2  mov     rbx, [rsp+28h+arg_0]
0x180034bd7  add     rsp, 20h
0x180034bdb  pop     rdi
0x180034bdc  jmp     cs:__imp_RtlComputeCrc32
```
