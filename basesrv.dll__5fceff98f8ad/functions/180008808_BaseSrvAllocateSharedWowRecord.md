# BaseSrvAllocateSharedWowRecord

- ea: `0x180008808`
- end: `0x1800088a8`
- name: `BaseSrvAllocateSharedWowRecord`
- size: `160`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000905c`

## callees

- `0x180008808`
- `0x18000db1d`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000883a`
- `ntdll!RtlAllocateHeap` at `0x18000883a`
- `ntdll!RtlCopyUnicodeString` at `0x180008876`
- `ntdll!RtlCopyUnicodeString` at `0x180008876`

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
0x180008808  mov     [rsp+arg_8], rbx
0x18000880d  mov     [rsp+arg_10], rsi
0x180008812  push    rdi
0x180008813  sub     rsp, 20h
0x180008817  movzx   esi, word ptr [rcx]
0x18000881a  mov     rdi, rcx
0x18000881d  mov     rcx, gs:60h
0x180008826  mov     edx, cs:BaseSrvTag
0x18000882c  add     edx, 40000h; Flags
0x180008832  lea     r8, [rsi+62h]; Size
0x180008836  mov     rcx, [rcx+30h]; HeapHandle
0x18000883a  call    cs:__imp_RtlAllocateHeap
0x180008841  nop     dword ptr [rax+rax+00h]
0x180008846  mov     rbx, rax
0x180008849  test    rax, rax
0x18000884c  jz      short loc_180008894
0x18000884e  lea     r8, [rsi+62h]; Size
0x180008852  xor     edx, edx; Val
0x180008854  mov     rcx, rax; void *
0x180008857  call    memset_0
0x18000885c  movzx   ecx, word ptr [rdi]
0x18000885f  mov     rdx, rdi; SourceString
0x180008862  add     cx, 2
0x180008866  mov     [rbx+22h], cx
0x18000886a  lea     rcx, [rbx+60h]
0x18000886e  mov     [rbx+28h], rcx
0x180008872  lea     rcx, [rbx+20h]; DestinationString
0x180008876  call    cs:__imp_RtlCopyUnicodeString
0x18000887d  nop     dword ptr [rax+rax+00h]
0x180008882  mov     [rsp+28h+arg_0], 0FFFFFFFFFFFFFFFFh
0x18000888b  mov     rax, [rsp+28h+arg_0]
0x180008890  mov     [rbx+40h], rax
0x180008894  mov     rsi, [rsp+28h+arg_10]
0x180008899  mov     rax, rbx
0x18000889c  mov     rbx, [rsp+28h+arg_8]
0x1800088a1  add     rsp, 20h
0x1800088a5  pop     rdi
0x1800088a6  retn
```
