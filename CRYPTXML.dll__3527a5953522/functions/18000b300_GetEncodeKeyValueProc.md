# _GetEncodeKeyValueProc

- ea: `0x18000b300`
- end: `0x18000b3a2`
- name: `_GetEncodeKeyValueProc`
- size: `162`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a310`
- `0x18000b1e0`

## callees

- `0x180009a10`
- `0x18000b300`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b360`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b360`

## pseudocode

```c
__int64 __fastcall GetEncodeKeyValueProc(PCNZWCH lpString2)
{
  __int64 i; // rdi

  if ( !dword_180022FC4 )
    LoadRegKeyvalueExtensions();
  for ( i = 0; (unsigned int)i < dword_180022FE0; i = (unsigned int)(i + 1) )
  {
    if ( CompareStringW(0, 1u, **((PCNZWCH **)lpMem + i), -1, lpString2, -1) == 2 )
    {
      _mm_lfence();
      return *(_QWORD *)(*((_QWORD *)lpMem + i) + 32LL);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b300  mov     [rsp+arg_8], rbx
0x18000b305  mov     [rsp+arg_10], rsi
0x18000b30a  push    rdi
0x18000b30b  sub     rsp, 30h
0x18000b30f  xor     ebx, ebx
0x18000b311  mov     rsi, rcx
0x18000b314  cmp     cs:dword_180022FC4, ebx
0x18000b31a  jnz     short loc_18000B321
0x18000b31c  call    _LoadRegKeyvalueExtensions
0x18000b321  xor     edi, edi
0x18000b323  mov     [rsp+38h+arg_0], r14
0x18000b328  cmp     edi, cs:dword_180022FE0
0x18000b32e  jnb     short loc_18000B389
0x18000b330  mov     rax, cs:lpMem
0x18000b337  lea     r14, ds:0[rdi*8]
0x18000b33f  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000b347  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000b34d  mov     edx, 1; dwCmpFlags
0x18000b352  mov     [rsp+38h+lpString2], rsi; lpString2
0x18000b357  xor     ecx, ecx; Locale
0x18000b359  mov     r8, [r14+rax]
0x18000b35d  mov     r8, [r8]; lpString1
0x18000b360  call    cs:__imp_CompareStringW
0x18000b367  nop     dword ptr [rax+rax+00h]
0x18000b36c  cmp     eax, 2
0x18000b36f  jz      short loc_18000B375
0x18000b371  inc     edi
0x18000b373  jmp     short loc_18000B328
0x18000b375  lfence
0x18000b378  mov     rax, cs:lpMem
0x18000b37f  mov     rcx, [r14+rax]
0x18000b383  mov     rax, [rcx+20h]
0x18000b387  jmp     short loc_18000B38C
0x18000b389  mov     rax, rbx
0x18000b38c  mov     r14, [rsp+38h+arg_0]
0x18000b391  mov     rbx, [rsp+38h+arg_8]
0x18000b396  mov     rsi, [rsp+38h+arg_10]
0x18000b39b  add     rsp, 30h
0x18000b39f  pop     rdi
0x18000b3a0  retn
```
