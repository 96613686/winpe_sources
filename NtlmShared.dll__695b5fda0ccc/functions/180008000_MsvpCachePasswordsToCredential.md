# MsvpCachePasswordsToCredential

- ea: `0x180008000`
- end: `0x18000803f`
- name: `MsvpCachePasswordsToCredential`
- size: `63`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008000`
- `0x18000c4a4`

## pseudocode

```c
char __fastcall MsvpCachePasswordsToCredential(__int64 a1, __int64 a2)
{
  char result; // al

  memset_0((void *)a2, 0, 0x160u);
  result = *(_BYTE *)(a1 + 32);
  *(_BYTE *)(a2 + 9) = result;
  if ( *(_BYTE *)(a1 + 32) )
    *(_OWORD *)(a2 + 38) = *(_OWORD *)a1;
  return result;
}

```

## disassembly

```asm
0x180008000  mov     [rsp+arg_0], rbx
0x180008005  push    rdi
0x180008006  sub     rsp, 20h
0x18000800a  mov     rbx, rdx
0x18000800d  mov     rdi, rcx
0x180008010  mov     rcx, rbx; void *
0x180008013  xor     edx, edx; Val
0x180008015  mov     r8d, 160h; Size
0x18000801b  call    memset_0
0x180008020  mov     al, [rdi+20h]
0x180008023  mov     [rbx+9], al
0x180008026  cmp     byte ptr [rdi+20h], 0
0x18000802a  jz      short loc_180008034
0x18000802c  movups  xmm0, xmmword ptr [rdi]
0x18000802f  movdqu  xmmword ptr [rbx+26h], xmm0
0x180008034  mov     rbx, [rsp+28h+arg_0]
0x180008039  add     rsp, 20h
0x18000803d  pop     rdi
0x18000803e  retn
```
