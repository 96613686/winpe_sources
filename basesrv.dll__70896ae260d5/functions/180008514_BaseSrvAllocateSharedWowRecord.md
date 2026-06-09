# BaseSrvAllocateSharedWowRecord

- ea: `0x180008514`
- end: `0x1800085b5`
- name: `BaseSrvAllocateSharedWowRecord`
- size: `161`
- prototype: `struct _UNICODE_STRING *__fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008d80`

## callees

- `0x180008514`
- `0x18000d713`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180008546`
- `ntdll!RtlAllocateHeap` at `0x180008546`
- `ntdll!RtlCopyUnicodeString` at `0x180008582`
- `ntdll!RtlCopyUnicodeString` at `0x180008582`

## pseudocode

```c
struct _UNICODE_STRING *__fastcall BaseSrvAllocateSharedWowRecord(PCUNICODE_STRING SourceString)
{
  __int64 Length; // rsi
  struct _UNICODE_STRING *Heap; // rax
  struct _UNICODE_STRING *v4; // rbx

  Length = SourceString->Length;
  Heap = (struct _UNICODE_STRING *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, Length + 98);
  v4 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, Length + 98);
    v4[2].MaximumLength = SourceString->Length + 2;
    v4[2].Buffer = &v4[6].Length;
    RtlCopyUnicodeString(v4 + 2, SourceString);
    *(_QWORD *)&v4[4].Length = -1;
  }
  return v4;
}

```

## disassembly

```asm
0x180008514  mov     [rsp+arg_8], rbx
0x180008519  mov     [rsp+arg_10], rsi
0x18000851e  push    rdi
0x18000851f  sub     rsp, 20h
0x180008523  movzx   esi, word ptr [rcx]
0x180008526  mov     rdi, rcx
0x180008529  mov     rcx, gs:60h
0x180008532  mov     edx, cs:BaseSrvTag
0x180008538  add     edx, 40000h; Flags
0x18000853e  lea     r8, [rsi+62h]; Size
0x180008542  mov     rcx, [rcx+30h]; HeapHandle
0x180008546  call    cs:__imp_RtlAllocateHeap
0x18000854d  nop     dword ptr [rax+rax+00h]
0x180008552  mov     rbx, rax
0x180008555  test    rax, rax
0x180008558  jz      short loc_1800085A1
0x18000855a  lea     r8, [rsi+62h]; Size
0x18000855e  xor     edx, edx; Val
0x180008560  mov     rcx, rax; void *
0x180008563  call    memset_0
0x180008568  movzx   ecx, word ptr [rdi]
0x18000856b  mov     rdx, rdi; SourceString
0x18000856e  add     cx, 2
0x180008572  mov     [rbx+22h], cx
0x180008576  lea     rcx, [rbx+60h]
0x18000857a  mov     [rbx+28h], rcx
0x18000857e  lea     rcx, [rbx+20h]; DestinationString
0x180008582  call    cs:__imp_RtlCopyUnicodeString
0x180008589  nop     dword ptr [rax+rax+00h]
0x18000858e  or      dword ptr [rsp+28h+arg_0], 0FFFFFFFFh
0x180008593  or      dword ptr [rsp+28h+arg_0+4], 0FFFFFFFFh
0x180008598  mov     rax, [rsp+28h+arg_0]
0x18000859d  mov     [rbx+40h], rax
0x1800085a1  mov     rsi, [rsp+28h+arg_10]
0x1800085a6  mov     rax, rbx
0x1800085a9  mov     rbx, [rsp+28h+arg_8]
0x1800085ae  add     rsp, 20h
0x1800085b2  pop     rdi
0x1800085b3  retn
```
