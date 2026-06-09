# BfReleaseMappingInformation

- ea: `0x14001732c`
- end: `0x140017358`
- name: `BfReleaseMappingInformation`
- size: `44`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400157a0`
- `0x14001e854`
- `0x140020cec`
- `0x140022910`

## callees

- `0x14001732c`
- `0x14001e998`

## pseudocode

```c
void __fastcall BfReleaseMappingInformation(volatile signed __int64 *a1)
{
  signed __int64 v1; // rax
  bool v2; // cc
  signed __int64 v3; // rax

  v1 = _InterlockedExchangeAdd64(a1, 0xFFFFFFFFFFFFFFFFuLL);
  v2 = v1 <= 1;
  v3 = v1 - 1;
  if ( v2 )
  {
    if ( v3 )
      __fastfail(0xEu);
    BfpDeleteMappingInformation((char *)a1);
  }
}

```

## disassembly

```asm
0x14001732c  sub     rsp, 28h
0x140017330  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017334  lock xadd [rcx], rax
0x140017339  sub     rax, 1
0x14001733d  jg      short loc_14001734B
0x14001733f  test    rax, rax
0x140017342  jz      short loc_140017351
0x140017344  mov     ecx, 0Eh; P
0x140017349  int     29h; Win8: RtlFailFast(ecx)
0x14001734b  add     rsp, 28h
0x14001734f  retn
0x140017351  call    BfpDeleteMappingInformation
0x140017356  jmp     short loc_14001734B
```
