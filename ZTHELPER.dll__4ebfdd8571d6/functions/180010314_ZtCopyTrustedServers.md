# ZtCopyTrustedServers

- ea: `0x180010314`
- end: `0x180010364`
- name: `ZtCopyTrustedServers`
- size: `80`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001036c`
- `0x1800105c0`
- `0x180010790`
- `0x180010c18`

## callees

- `0x180010314`
- `0x180010898`

## pseudocode

```c
__int64 __fastcall ZtCopyTrustedServers(unsigned int a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  unsigned int i; // ebx

  if ( !a2 || !a3 )
    return 87;
  result = 0;
  for ( i = 0; i < a1; ++i )
  {
    result = ZtCopyTrustedServer(((unsigned __int64)i << 6) + a2, ((unsigned __int64)i << 6) + a3);
    if ( (_DWORD)result )
      break;
  }
  return result;
}

```

## disassembly

```asm
0x180010314  push    rbx
0x180010316  push    rbp
0x180010317  push    rsi
0x180010318  push    rdi
0x180010319  sub     rsp, 28h
0x18001031d  mov     rsi, r8
0x180010320  mov     rbp, rdx
0x180010323  mov     edi, ecx
0x180010325  test    rdx, rdx
0x180010328  jnz     short loc_180010331
0x18001032a  mov     eax, 57h ; 'W'
0x18001032f  jmp     short loc_18001035B
0x180010331  test    rsi, rsi
0x180010334  jz      short loc_18001032A
0x180010336  xor     eax, eax
0x180010338  xor     ebx, ebx
0x18001033a  test    edi, edi
0x18001033c  jz      short loc_18001035B
0x18001033e  mov     eax, ebx
0x180010340  shl     rax, 6
0x180010344  lea     rdx, [rax+rsi]
0x180010348  lea     rcx, [rax+rbp]
0x18001034c  call    ZtCopyTrustedServer
0x180010351  test    eax, eax
0x180010353  jnz     short loc_18001035B
0x180010355  inc     ebx
0x180010357  cmp     ebx, edi
0x180010359  jb      short loc_18001033E
0x18001035b  add     rsp, 28h
0x18001035f  pop     rdi
0x180010360  pop     rsi
0x180010361  pop     rbp
0x180010362  pop     rbx
0x180010363  retn
```
