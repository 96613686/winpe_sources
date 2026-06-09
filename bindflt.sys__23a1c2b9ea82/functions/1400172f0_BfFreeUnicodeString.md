# BfFreeUnicodeString

- ea: `0x1400172f0`
- end: `0x140017326`
- name: `BfFreeUnicodeString`
- size: `54`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x140001dd0`
- `0x140001fd0`
- `0x14000fda0`
- `0x140013864`
- `0x1400152f0`
- `0x1400154b0`
- `0x1400157a0`
- `0x140018b60`
- `0x14001c904`
- `0x14001d974`
- `0x14001e854`
- `0x14001e998`
- `0x14001ea10`
- `0x140020ae0`
- `0x140022910`
- `0x140023330`

## callees

- `0x1400172f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140017307`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017307`

## pseudocode

```c
__int64 __fastcall BfFreeUnicodeString(__int64 a1)
{
  void *v2; // rcx
  __int64 result; // rax

  v2 = *(void **)(a1 + 8);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0x74734642u);
    *(_QWORD *)(a1 + 8) = 0;
  }
  result = 0;
  *(_DWORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1400172f0  push    rbx
0x1400172f2  sub     rsp, 20h
0x1400172f6  mov     rbx, rcx
0x1400172f9  mov     rcx, [rcx+8]; P
0x1400172fd  test    rcx, rcx
0x140017300  jz      short loc_14001731B
0x140017302  mov     edx, 74734642h; Tag
0x140017307  call    cs:__imp_ExFreePoolWithTag
0x14001730e  nop     dword ptr [rax+rax+00h]
0x140017313  mov     qword ptr [rbx+8], 0
0x14001731b  xor     eax, eax
0x14001731d  mov     [rbx], eax
0x14001731f  add     rsp, 20h
0x140017323  pop     rbx
0x140017324  retn
```
