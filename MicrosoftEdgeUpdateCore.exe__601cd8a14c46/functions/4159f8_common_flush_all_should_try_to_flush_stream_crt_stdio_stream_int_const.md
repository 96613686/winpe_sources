# common_flush_all_should_try_to_flush_stream(__crt_stdio_stream,int * const)

- ea: `0x4159f8`
- end: `0x415a2b`
- name: `?common_flush_all_should_try_to_flush_stream@@YA_NV__crt_stdio_stream@@QAH@Z`
- size: `51`
- prototype: `char __cdecl(int, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x415873`
- `0x4158ff`

## callees

- `0x4159f8`
- `0x415a2b`

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
0x4159f8  mov     edi, edi
0x4159fa  push    ebp
0x4159fb  mov     ebp, esp
0x4159fd  mov     eax, [ebp+arg_0]
0x415a00  test    eax, eax
0x415a02  jz      short loc_415A23
0x415a04  mov     ecx, [eax+0Ch]
0x415a07  nop
0x415a08  mov     eax, ecx
0x415a0a  shr     eax, 0Dh
0x415a0d  test    al, 1
0x415a0f  jz      short loc_415A23
0x415a11  push    ecx; int
0x415a12  call    ?is_stream_flushable_or_commitable@@YA_NJ@Z
0x415a17  add     esp, 4
0x415a1a  test    al, al
0x415a1c  jnz     short loc_415A27
0x415a1e  mov     eax, [ebp+arg_4]
0x415a21  inc     dword ptr [eax]
0x415a23  xor     al, al
0x415a25  pop     ebp
0x415a26  retn
0x415a27  mov     al, 1
0x415a29  pop     ebp
0x415a2a  retn
```
