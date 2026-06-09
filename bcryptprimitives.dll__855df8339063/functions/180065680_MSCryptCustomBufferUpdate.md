# MSCryptCustomBufferUpdate

- ea: `0x180065680`
- end: `0x180065718`
- name: `MSCryptCustomBufferUpdate`
- size: `152`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013b70`
- `0x18004c440`
- `0x1800657e0`

## callees

- `0x18000ecb0`
- `0x18000ef28`
- `0x1800102a0`
- `0x180063170`
- `0x180065680`

## string_xrefs

- `0x1800656b5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptCustomBufferUpdate(__int64 a1, const void *a2, unsigned int a3)
{
  void *v3; // rbx
  size_t v4; // rdi
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rcx

  v3 = 0;
  v4 = a3;
  if ( !a3 )
    goto LABEL_7;
  if ( a2 )
  {
    if ( a3 > 0x40 )
    {
      v3 = (void *)SafeAllocaAllocateFromHeap(a3);
      if ( !v3 )
      {
        v7 = -1073741801;
        v8 = 735;
        v9 = 3221225495LL;
        goto LABEL_4;
      }
    }
    else
    {
      v3 = (void *)a1;
    }
LABEL_7:
    MSCryptCustomBufferReset(a1);
    memcpy_0(v3, a2, v4);
    *(_QWORD *)(a1 + 64) = v3;
    v7 = 0;
    *(_DWORD *)(a1 + 72) = v4;
    return v7;
  }
  v7 = -1073741811;
  v8 = 720;
  v9 = 3221225485LL;
LABEL_4:
  DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v8);
  return v7;
}

```

## disassembly

```asm
0x180065680  push    rbx
0x180065682  push    rbp
0x180065683  push    rsi
0x180065684  push    rdi
0x180065685  sub     rsp, 28h
0x180065689  xor     ebx, ebx
0x18006568b  mov     edi, r8d
0x18006568e  mov     rbp, rdx
0x180065691  mov     rsi, rcx
0x180065694  test    r8d, r8d
0x180065697  jz      short loc_1800656CB
0x180065699  test    rdx, rdx
0x18006569c  jnz     short loc_1800656C3
0x18006569e  mov     ebx, 0C000000Dh
0x1800656a3  mov     r9d, 2D0h
0x1800656a9  mov     ecx, 0C000000Dh
0x1800656ae  lea     rdx, aStatus; "Status"
0x1800656b5  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800656bc  call    DebugTraceError
0x1800656c1  jmp     short loc_1800656EA
0x1800656c3  cmp     edi, 40h ; '@'
0x1800656c6  ja      short loc_1800656F6
0x1800656c8  mov     rbx, rsi
0x1800656cb  mov     rcx, rsi
0x1800656ce  call    MSCryptCustomBufferReset
0x1800656d3  mov     r8, rdi; Size
0x1800656d6  mov     rdx, rbp; Src
0x1800656d9  mov     rcx, rbx; void *
0x1800656dc  call    memcpy_0
0x1800656e1  mov     [rsi+40h], rbx
0x1800656e5  xor     ebx, ebx
0x1800656e7  mov     [rsi+48h], edi
0x1800656ea  mov     eax, ebx
0x1800656ec  add     rsp, 28h
0x1800656f0  pop     rdi
0x1800656f1  pop     rsi
0x1800656f2  pop     rbp
0x1800656f3  pop     rbx
0x1800656f4  retn
0x1800656f6  mov     rcx, rdi
0x1800656f9  call    SafeAllocaAllocateFromHeap
0x1800656fe  mov     rbx, rax
0x180065701  test    rax, rax
0x180065704  jnz     short loc_1800656CB
0x180065706  mov     ebx, 0C0000017h
0x18006570b  mov     r9d, 2DFh
0x180065711  mov     ecx, 0C0000017h
0x180065716  jmp     short loc_1800656AE
```
