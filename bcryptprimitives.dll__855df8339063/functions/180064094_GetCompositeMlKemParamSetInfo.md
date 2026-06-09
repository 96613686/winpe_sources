# GetCompositeMlKemParamSetInfo

- ea: `0x180064094`
- end: `0x18006412a`
- name: `GetCompositeMlKemParamSetInfo`
- size: `150`
- prototype: `__int64 __fastcall(void *Buf1, size_t Size, wchar_t ***)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800642d4`
- `0x180065260`

## callees

- `0x18000ecb0`
- `0x1800631a8`
- `0x180064094`

## string_xrefs

- `0x180064109`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall GetCompositeMlKemParamSetInfo(void *Buf1, size_t Size, wchar_t ***a3)
{
  size_t v3; // rsi
  unsigned int v6; // ebx
  wchar_t **v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx

  v3 = (unsigned int)Size;
  if ( Buf1 && (_DWORD)Size )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = &(&off_1800871F0)[4 * v6];
      if ( (_DWORD)v3 == *((_DWORD *)v7 + 2) && !memcmp_0(Buf1, *v7, v3) )
        break;
      if ( ++v6 >= 3 )
      {
        v8 = -1073741637;
        v9 = 683;
        v10 = 3221225659LL;
        goto LABEL_10;
      }
    }
    v8 = 0;
    *a3 = v7;
  }
  else
  {
    v8 = -1073741811;
    v9 = 660;
    v10 = 3221225485LL;
LABEL_10:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v9);
  }
  return v8;
}

```

## disassembly

```asm
0x180064094  push    rbx
0x180064096  push    rbp
0x180064097  push    rsi
0x180064098  push    rdi
0x180064099  push    r14
0x18006409b  sub     rsp, 20h
0x18006409f  mov     esi, edx
0x1800640a1  mov     r14, r8
0x1800640a4  mov     rbp, rcx
0x1800640a7  test    rcx, rcx
0x1800640aa  jz      short loc_1800640F9
0x1800640ac  test    edx, edx
0x1800640ae  jz      short loc_1800640F9
0x1800640b0  xor     ebx, ebx
0x1800640b2  mov     edi, ebx
0x1800640b4  lea     rcx, off_1800871F0; "768-P256"
0x1800640bb  shl     rdi, 5
0x1800640bf  add     rdi, rcx
0x1800640c2  cmp     esi, [rdi+8]
0x1800640c5  jnz     short loc_1800640D9
0x1800640c7  mov     rdx, [rdi]; Buf2
0x1800640ca  mov     r8, rsi; Size
0x1800640cd  mov     rcx, rbp; Buf1
0x1800640d0  call    memcmp_0
0x1800640d5  test    eax, eax
0x1800640d7  jz      short loc_1800640F2
0x1800640d9  inc     ebx
0x1800640db  cmp     ebx, 3
0x1800640de  jb      short loc_1800640B2
0x1800640e0  mov     ebx, 0C00000BBh
0x1800640e5  mov     r9d, 2ABh
0x1800640eb  mov     ecx, 0C00000BBh
0x1800640f0  jmp     short loc_180064109
0x1800640f2  xor     ebx, ebx
0x1800640f4  mov     [r14], rdi
0x1800640f7  jmp     short loc_18006411C
0x1800640f9  mov     ebx, 0C000000Dh
0x1800640fe  mov     r9d, 294h
0x180064104  mov     ecx, 0C000000Dh
0x180064109  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064110  lea     rdx, aStatus; "Status"
0x180064117  call    DebugTraceError
0x18006411c  mov     eax, ebx
0x18006411e  add     rsp, 20h
0x180064122  pop     r14
0x180064124  pop     rdi
0x180064125  pop     rsi
0x180064126  pop     rbp
0x180064127  pop     rbx
0x180064128  retn
```
