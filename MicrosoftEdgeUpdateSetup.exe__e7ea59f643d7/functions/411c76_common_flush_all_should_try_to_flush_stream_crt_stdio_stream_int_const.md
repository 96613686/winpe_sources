# common_flush_all_should_try_to_flush_stream(__crt_stdio_stream,int * const)

- ea: `0x411c76`
- end: `0x411ca9`
- name: `?common_flush_all_should_try_to_flush_stream@@YA_NV__crt_stdio_stream@@QAH@Z`
- size: `51`
- prototype: `char __cdecl(int, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x411af1`
- `0x411b7d`

## callees

- `0x411c76`
- `0x411ca9`

## pseudocode

```c
char __cdecl common_flush_all_should_try_to_flush_stream(int a1, _DWORD *a2)
{
  if ( !a1 || (*(_DWORD *)(a1 + 12) & 0x2000) == 0 )
    return 0;
  if ( !is_stream_flushable_or_commitable(*(_DWORD *)(a1 + 12)) )
  {
    ++*a2;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x411c76  mov     edi, edi
0x411c78  push    ebp
0x411c79  mov     ebp, esp
0x411c7b  mov     eax, [ebp+arg_0]
0x411c7e  test    eax, eax
0x411c80  jz      short loc_411CA1
0x411c82  mov     ecx, [eax+0Ch]
0x411c85  nop
0x411c86  mov     eax, ecx
0x411c88  shr     eax, 0Dh
0x411c8b  test    al, 1
0x411c8d  jz      short loc_411CA1
0x411c8f  push    ecx; int
0x411c90  call    ?is_stream_flushable_or_commitable@@YA_NJ@Z
0x411c95  add     esp, 4
0x411c98  test    al, al
0x411c9a  jnz     short loc_411CA5
0x411c9c  mov     eax, [ebp+arg_4]
0x411c9f  inc     dword ptr [eax]
0x411ca1  xor     al, al
0x411ca3  pop     ebp
0x411ca4  retn
0x411ca5  mov     al, 1
0x411ca7  pop     ebp
0x411ca8  retn
```
