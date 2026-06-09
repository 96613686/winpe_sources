# _GetCreateKeyProc

- ea: `0x180015384`
- end: `0x180015405`
- name: `_GetCreateKeyProc`
- size: `129`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012838`

## callees

- `0x180009a10`
- `0x180015384`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800153d1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800153d1`

## pseudocode

```c
__int64 __fastcall GetCreateKeyProc(PCNZWCH lpString2)
{
  unsigned int v1; // ebx
  __int64 v3; // rdi

  v1 = 0;
  v3 = 0;
  if ( !dword_180022FC4 )
    LoadRegKeyvalueExtensions();
  while ( v1 < dword_180022FE0 )
  {
    if ( CompareStringW(0, 1u, *(PCNZWCH *)(*((_QWORD *)lpMem + v1) + 24LL), -1, lpString2, -1) == 2 )
    {
      _mm_lfence();
      return *(_QWORD *)(*((_QWORD *)lpMem + v1) + 40LL);
    }
    ++v1;
  }
  return v3;
}

```

## disassembly

```asm
0x180015384  push    rbx
0x180015386  push    rbp
0x180015387  push    rsi
0x180015388  push    rdi
0x180015389  sub     rsp, 38h
0x18001538d  xor     ebx, ebx
0x18001538f  mov     rbp, rcx
0x180015392  cmp     cs:dword_180022FC4, ebx
0x180015398  mov     edi, ebx
0x18001539a  jnz     short loc_1800153A1
0x18001539c  call    _LoadRegKeyvalueExtensions
0x1800153a1  cmp     ebx, cs:dword_180022FE0
0x1800153a7  jnb     short loc_1800153F8
0x1800153a9  mov     rax, cs:lpMem
0x1800153b0  or      r9d, 0FFFFFFFFh; cchCount1
0x1800153b4  mov     esi, ebx
0x1800153b6  xor     ecx, ecx; Locale
0x1800153b8  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800153c0  mov     [rsp+58h+lpString2], rbp; lpString2
0x1800153c5  lea     edx, [r9+2]; dwCmpFlags
0x1800153c9  mov     r8, [rax+rsi*8]
0x1800153cd  mov     r8, [r8+18h]; lpString1
0x1800153d1  call    cs:__imp_CompareStringW
0x1800153d8  nop     dword ptr [rax+rax+00h]
0x1800153dd  cmp     eax, 2
0x1800153e0  jz      short loc_1800153E6
0x1800153e2  inc     ebx
0x1800153e4  jmp     short loc_1800153A1
0x1800153e6  lfence
0x1800153e9  mov     rax, cs:lpMem
0x1800153f0  mov     rcx, [rax+rsi*8]
0x1800153f4  mov     rdi, [rcx+28h]
0x1800153f8  mov     rax, rdi
0x1800153fb  add     rsp, 38h
0x1800153ff  pop     rdi
0x180015400  pop     rsi
0x180015401  pop     rbp
0x180015402  pop     rbx
0x180015403  retn
```
