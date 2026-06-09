# EapFreeSimpleEventParameters

- ea: `0x180009b58`
- end: `0x180009be3`
- name: `EapFreeSimpleEventParameters`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009300`
- `0x180009b20`

## callees

- `0x180002e30`
- `0x180009b58`

## pseudocode

```c
BOOLEAN __fastcall EapFreeSimpleEventParameters(__int64 a1)
{
  unsigned __int16 v2; // si
  __int64 v3; // rdx
  __int64 v4; // rdi
  void *v5; // rcx
  void *v6; // rcx
  BOOLEAN result; // al

  if ( *(_QWORD *)(a1 + 24) )
  {
    v2 = 0;
    if ( *(_WORD *)(a1 + 16) )
    {
      while ( 1 )
      {
        v3 = *(_QWORD *)(a1 + 24);
        v4 = 32LL * v2;
        if ( *(_DWORD *)(v3 + v4 + 8) == 2 )
          break;
        if ( (unsigned int)(*(_DWORD *)(v3 + v4 + 8) - 3) <= 1 )
        {
          v5 = *(void **)(v3 + v4 + 24);
          goto LABEL_7;
        }
LABEL_9:
        v6 = *(void **)(v4 + *(_QWORD *)(a1 + 24));
        if ( v6 )
          EaLibFree(v6);
        if ( ++v2 >= *(_WORD *)(a1 + 16) )
          return EaLibFree(*(void **)(a1 + 24));
      }
      v5 = *(void **)(v3 + v4 + 16);
LABEL_7:
      if ( v5 )
        EaLibFree(v5);
      goto LABEL_9;
    }
    return EaLibFree(*(void **)(a1 + 24));
  }
  return result;
}

```

## disassembly

```asm
0x180009b58  mov     [rsp+arg_0], rbx
0x180009b5d  mov     [rsp+arg_8], rsi
0x180009b62  push    rdi
0x180009b63  sub     rsp, 20h
0x180009b67  cmp     qword ptr [rcx+18h], 0
0x180009b6c  mov     rbx, rcx
0x180009b6f  jz      short loc_180009BD3
0x180009b71  xor     esi, esi
0x180009b73  xor     eax, eax
0x180009b75  cmp     ax, [rcx+10h]
0x180009b79  jnb     short loc_180009BCA
0x180009b7b  mov     rdx, [rbx+18h]
0x180009b7f  movzx   edi, si
0x180009b82  shl     rdi, 5
0x180009b86  mov     ecx, [rdx+rdi+8]
0x180009b8a  sub     ecx, 2
0x180009b8d  jz      short loc_180009BA0
0x180009b8f  sub     ecx, 1
0x180009b92  jz      short loc_180009B99
0x180009b94  cmp     ecx, 1
0x180009b97  jnz     short loc_180009BAF
0x180009b99  mov     rcx, [rdx+rdi+18h]
0x180009b9e  jmp     short loc_180009BA5
0x180009ba0  mov     rcx, [rdx+rdi+10h]
0x180009ba5  test    rcx, rcx
0x180009ba8  jz      short loc_180009BAF
0x180009baa  call    EaLibFree
0x180009baf  mov     rax, [rbx+18h]
0x180009bb3  mov     rcx, [rdi+rax]
0x180009bb7  test    rcx, rcx
0x180009bba  jz      short loc_180009BC1
0x180009bbc  call    EaLibFree
0x180009bc1  inc     si
0x180009bc4  cmp     si, [rbx+10h]
0x180009bc8  jb      short loc_180009B7B
0x180009bca  mov     rcx, [rbx+18h]
0x180009bce  call    EaLibFree
0x180009bd3  mov     rbx, [rsp+28h+arg_0]
0x180009bd8  mov     rsi, [rsp+28h+arg_8]
0x180009bdd  add     rsp, 20h
0x180009be1  pop     rdi
0x180009be2  retn
```
