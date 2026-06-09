# CFileStream::Write(void const *,ulong,ulong *)

- ea: `0x180022f20`
- end: `0x180022f69`
- name: `?Write@CFileStream@@UEAAJPEBXKPEAK@Z`
- size: `73`
- prototype: `int(CFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180015fb4`
- `0x180022f20`

## import_xrefs

- `msvcrt!fwrite` at `0x180022f42`
- `msvcrt!fwrite` at `0x180022f42`

## pseudocode

```c
__int64 __fastcall CFileStream::Write(FILE **this, const void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v6; // eax

  v6 = fwrite(a2, 1u, a3, this[3]);
  *a4 = v6;
  if ( v6 == a3 )
    return 0;
  else
    return Exit(-2147467259, 0);
}

```

## disassembly

```asm
0x180022f20  mov     [rsp+arg_0], rbx
0x180022f25  push    rdi
0x180022f26  sub     rsp, 20h
0x180022f2a  mov     rax, rdx
0x180022f2d  mov     edi, r8d
0x180022f30  mov     rbx, r9
0x180022f33  mov     r8d, r8d; ElementCount
0x180022f36  mov     r9, [rcx+18h]; Stream
0x180022f3a  mov     edx, 1; ElementSize
0x180022f3f  mov     rcx, rax; Buffer
0x180022f42  call    cs:__imp_fwrite
0x180022f48  mov     [rbx], eax
0x180022f4a  cmp     eax, edi
0x180022f4c  jnz     short loc_180022F52
0x180022f4e  xor     eax, eax
0x180022f50  jmp     short loc_180022F5E
0x180022f52  xor     edx, edx; unsigned int
0x180022f54  mov     ecx, 80004005h; int
0x180022f59  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180022f5e  mov     rbx, [rsp+28h+arg_0]
0x180022f63  add     rsp, 20h
0x180022f67  pop     rdi
0x180022f68  retn
```
