# BaseSrvSaveFileNameMapping

- ea: `0x180005b60`
- end: `0x180005bfd`
- name: `BaseSrvSaveFileNameMapping`
- size: `157`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004d70`
- `0x180006170`

## callees

- `0x180005b60`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005b94`
- `ntdll!RtlAllocateHeap` at `0x180005b94`
- `ntdll!RtlCopyUnicodeString` at `0x180005bdb`
- `ntdll!RtlCopyUnicodeString` at `0x180005bdb`

## pseudocode

```c
__int64 __fastcall BaseSrvSaveFileNameMapping(PCUNICODE_STRING SourceString, _QWORD *a2)
{
  char *Heap; // rax
  char *v5; // rbx

  Heap = (char *)RtlAllocateHeap(
                   BaseSrvSharedHeap,
                   (BaseSrvSharedTag + 0x40000) | 8,
                   SourceString->MaximumLength + 40LL);
  v5 = Heap;
  if ( !Heap )
    return 3221225495LL;
  if ( SourceString->Length )
  {
    *((_QWORD *)Heap + 2) = Heap + 40;
    *((_WORD *)Heap + 5) = SourceString->MaximumLength;
    RtlCopyUnicodeString((PUNICODE_STRING)(Heap + 8), SourceString);
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x180005b60  mov     [rsp+arg_0], rbx
0x180005b65  mov     [rsp+arg_8], rsi
0x180005b6a  push    rdi
0x180005b6b  sub     rsp, 20h
0x180005b6f  movzx   r8d, word ptr [rcx+2]
0x180005b74  mov     rsi, rdx
0x180005b77  mov     edx, cs:BaseSrvSharedTag
0x180005b7d  mov     rdi, rcx
0x180005b80  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005b87  add     edx, 40000h
0x180005b8d  or      edx, 8; Flags
0x180005b90  add     r8, 28h ; '('; Size
0x180005b94  call    cs:__imp_RtlAllocateHeap
0x180005b9b  nop     dword ptr [rax+rax+00h]
0x180005ba0  mov     rbx, rax
0x180005ba3  test    rax, rax
0x180005ba6  jnz     short loc_180005BBE
0x180005ba8  mov     eax, 0C0000017h
0x180005bad  mov     rbx, [rsp+28h+arg_0]
0x180005bb2  mov     rsi, [rsp+28h+arg_8]
0x180005bb7  add     rsp, 20h
0x180005bbb  pop     rdi
0x180005bbc  retn
0x180005bbe  cmp     word ptr [rdi], 0
0x180005bc2  jz      short loc_180005BE7
0x180005bc4  add     rax, 28h ; '('
0x180005bc8  lea     rcx, [rbx+8]; DestinationString
0x180005bcc  mov     [rbx+10h], rax
0x180005bd0  mov     rdx, rdi; SourceString
0x180005bd3  movzx   eax, word ptr [rdi+2]
0x180005bd7  mov     [rbx+0Ah], ax
0x180005bdb  call    cs:__imp_RtlCopyUnicodeString
0x180005be2  nop     dword ptr [rax+rax+00h]
0x180005be7  mov     [rsi], rbx
0x180005bea  xor     eax, eax
0x180005bec  mov     rbx, [rsp+28h+arg_0]
0x180005bf1  mov     rsi, [rsp+28h+arg_8]
0x180005bf6  add     rsp, 20h
0x180005bfa  pop     rdi
0x180005bfb  retn
```
