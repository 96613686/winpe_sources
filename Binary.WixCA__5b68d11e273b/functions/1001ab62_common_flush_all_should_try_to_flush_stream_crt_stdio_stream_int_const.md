# common_flush_all_should_try_to_flush_stream(__crt_stdio_stream,int * const)

- ea: `0x1001ab62`
- end: `0x1001ab95`
- name: `?common_flush_all_should_try_to_flush_stream@@YA_NV__crt_stdio_stream@@QAH@Z`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1001a9ef`
- `0x1001aa71`

## callees

- `0x1001ab62`
- `0x1001ab95`

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
0x1001ab62  mov     edi, edi
0x1001ab64  push    ebp
0x1001ab65  mov     ebp, esp
0x1001ab67  mov     eax, [ebp+arg_0]
0x1001ab6a  test    eax, eax
0x1001ab6c  jz      short loc_1001AB8D
0x1001ab6e  mov     ecx, [eax+0Ch]
0x1001ab71  nop
0x1001ab72  mov     eax, ecx
0x1001ab74  shr     eax, 0Dh
0x1001ab77  test    al, 1
0x1001ab79  jz      short loc_1001AB8D
0x1001ab7b  push    ecx; int
0x1001ab7c  call    ?is_stream_flushable_or_commitable@@YA_NJ@Z
0x1001ab81  add     esp, 4
0x1001ab84  test    al, al
0x1001ab86  jnz     short loc_1001AB91
0x1001ab88  mov     eax, [ebp+arg_4]
0x1001ab8b  inc     dword ptr [eax]
0x1001ab8d  xor     al, al
0x1001ab8f  pop     ebp
0x1001ab90  retn
0x1001ab91  mov     al, 1
0x1001ab93  pop     ebp
0x1001ab94  retn
```
