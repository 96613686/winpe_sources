# BfsAllocateBlock

- ea: `0x1400105ac`
- end: `0x140010612`
- name: `BfsAllocateBlock`
- size: `102`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140010b30`
- `0x140011458`
- `0x140011d18`

## callees

- `0x1400105ac`

## import_xrefs

- `ntoskrnl!RtlFindClearBits` at `0x1400105cc`
- `ntoskrnl!RtlFindClearBits` at `0x1400105cc`
- `ntoskrnl!RtlSetBits` at `0x1400105f1`
- `ntoskrnl!RtlSetBits` at `0x1400105f1`

## pseudocode

```c
__int64 __fastcall BfsAllocateBlock(__int64 a1, ULONG *a2)
{
  struct _RTL_BITMAP *v2; // rdi
  ULONG ClearBits; // eax
  ULONG v5; // ebx
  __int64 result; // rax

  v2 = (struct _RTL_BITMAP *)(a1 + 24);
  ClearBits = RtlFindClearBits((PRTL_BITMAP)(a1 + 24), 1u, 0);
  v5 = ClearBits;
  if ( ClearBits == -1 )
    return 2147483674LL;
  RtlSetBits(v2, ClearBits, 1u);
  result = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x1400105ac  mov     [rsp+arg_0], rbx
0x1400105b1  mov     [rsp+arg_8], rsi
0x1400105b6  push    rdi
0x1400105b7  sub     rsp, 20h
0x1400105bb  xor     r8d, r8d; HintIndex
0x1400105be  lea     rdi, [rcx+18h]
0x1400105c2  mov     rsi, rdx
0x1400105c5  mov     rcx, rdi; BitMapHeader
0x1400105c8  lea     edx, [r8+1]; NumberToFind
0x1400105cc  call    cs:__imp_RtlFindClearBits
0x1400105d3  nop     dword ptr [rax+rax+00h]
0x1400105d8  mov     ebx, eax
0x1400105da  cmp     eax, 0FFFFFFFFh
0x1400105dd  jnz     short loc_1400105E6
0x1400105df  mov     eax, 8000001Ah
0x1400105e4  jmp     short loc_140010601
0x1400105e6  mov     r8d, 1; NumberToSet
0x1400105ec  mov     edx, ebx; StartingIndex
0x1400105ee  mov     rcx, rdi; BitMapHeader
0x1400105f1  call    cs:__imp_RtlSetBits
0x1400105f8  nop     dword ptr [rax+rax+00h]
0x1400105fd  xor     eax, eax
0x1400105ff  mov     [rsi], ebx
0x140010601  mov     rbx, [rsp+28h+arg_0]
0x140010606  mov     rsi, [rsp+28h+arg_8]
0x14001060b  add     rsp, 20h
0x14001060f  pop     rdi
0x140010610  retn
```
