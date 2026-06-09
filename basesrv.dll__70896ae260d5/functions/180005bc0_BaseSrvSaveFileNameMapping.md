# BaseSrvSaveFileNameMapping

- ea: `0x180005bc0`
- end: `0x180005c5d`
- name: `BaseSrvSaveFileNameMapping`
- size: `157`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004d80`
- `0x180005f10`

## callees

- `0x180005bc0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005bf4`
- `ntdll!RtlAllocateHeap` at `0x180005bf4`
- `ntdll!RtlCopyUnicodeString` at `0x180005c3b`
- `ntdll!RtlCopyUnicodeString` at `0x180005c3b`

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
0x180005bc0  mov     [rsp+arg_0], rbx
0x180005bc5  mov     [rsp+arg_8], rsi
0x180005bca  push    rdi
0x180005bcb  sub     rsp, 20h
0x180005bcf  movzx   r8d, word ptr [rcx+2]
0x180005bd4  mov     rsi, rdx
0x180005bd7  mov     edx, cs:BaseSrvSharedTag
0x180005bdd  mov     rdi, rcx
0x180005be0  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005be7  add     edx, 40000h
0x180005bed  or      edx, 8; Flags
0x180005bf0  add     r8, 28h ; '('; Size
0x180005bf4  call    cs:__imp_RtlAllocateHeap
0x180005bfb  nop     dword ptr [rax+rax+00h]
0x180005c00  mov     rbx, rax
0x180005c03  test    rax, rax
0x180005c06  jnz     short loc_180005C1E
0x180005c08  mov     eax, 0C0000017h
0x180005c0d  mov     rbx, [rsp+28h+arg_0]
0x180005c12  mov     rsi, [rsp+28h+arg_8]
0x180005c17  add     rsp, 20h
0x180005c1b  pop     rdi
0x180005c1c  retn
0x180005c1e  cmp     word ptr [rdi], 0
0x180005c22  jz      short loc_180005C47
0x180005c24  add     rax, 28h ; '('
0x180005c28  lea     rcx, [rbx+8]; DestinationString
0x180005c2c  mov     [rbx+10h], rax
0x180005c30  mov     rdx, rdi; SourceString
0x180005c33  movzx   eax, word ptr [rdi+2]
0x180005c37  mov     [rbx+0Ah], ax
0x180005c3b  call    cs:__imp_RtlCopyUnicodeString
0x180005c42  nop     dword ptr [rax+rax+00h]
0x180005c47  mov     [rsi], rbx
0x180005c4a  xor     eax, eax
0x180005c4c  mov     rbx, [rsp+28h+arg_0]
0x180005c51  mov     rsi, [rsp+28h+arg_8]
0x180005c56  add     rsp, 20h
0x180005c5a  pop     rdi
0x180005c5b  retn
```
