# common_flush_all_should_try_to_flush_stream(__crt_stdio_stream,int * const)

- ea: `0x41256e`
- end: `0x4125a1`
- name: `?common_flush_all_should_try_to_flush_stream@@YA_NV__crt_stdio_stream@@QAH@Z`
- size: `51`
- prototype: `char __cdecl(int, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4123e9`
- `0x412475`

## callees

- `0x41256e`
- `0x4125a1`

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
0x41256e  mov     edi, edi
0x412570  push    ebp
0x412571  mov     ebp, esp
0x412573  mov     eax, [ebp+arg_0]
0x412576  test    eax, eax
0x412578  jz      short loc_412599
0x41257a  mov     ecx, [eax+0Ch]
0x41257d  nop
0x41257e  mov     eax, ecx
0x412580  shr     eax, 0Dh
0x412583  test    al, 1
0x412585  jz      short loc_412599
0x412587  push    ecx; int
0x412588  call    ?is_stream_flushable_or_commitable@@YA_NJ@Z
0x41258d  add     esp, 4
0x412590  test    al, al
0x412592  jnz     short loc_41259D
0x412594  mov     eax, [ebp+arg_4]
0x412597  inc     dword ptr [eax]
0x412599  xor     al, al
0x41259b  pop     ebp
0x41259c  retn
0x41259d  mov     al, 1
0x41259f  pop     ebp
0x4125a0  retn
```
