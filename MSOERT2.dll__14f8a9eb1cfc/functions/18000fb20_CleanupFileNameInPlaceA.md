# CleanupFileNameInPlaceA

- ea: `0x18000fb20`
- end: `0x18000fbb2`
- name: `CleanupFileNameInPlaceA`
- size: `146`
- prototype: `__int64 __fastcall(UINT CodePage, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000fb20`
- `0x18000fce0`

## import_xrefs

- `KERNEL32!RtlMoveMemory` at `0x18000fb92`
- `KERNEL32!RtlMoveMemory` at `0x18000fb92`
- `KERNEL32!IsDBCSLeadByteEx` at `0x18000fb62`
- `KERNEL32!IsDBCSLeadByteEx` at `0x18000fb62`

## pseudocode

```c
__int64 __fastcall CleanupFileNameInPlaceA(UINT CodePage, __int64 a2)
{
  unsigned int v2; // edi
  __int64 v4; // rbx
  UINT v5; // esi

  v2 = 0;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_BYTE *)(v4 + a2) );
  }
  else
  {
    LODWORD(v4) = 0;
  }
  v5 = 0;
  if ( CodePage != 1200 )
    v5 = CodePage;
  if ( (_DWORD)v4 )
  {
    do
    {
      if ( IsDBCSLeadByteEx(v5, *(_BYTE *)(a2 + v2)) )
      {
        v2 += 2;
      }
      else if ( (unsigned int)FIsValidFileNameCharA(v5) )
      {
        ++v2;
      }
      else
      {
        RtlMoveMemory(a2 + v2, a2 + v2 + 1, (unsigned int)v4 - v2);
        LODWORD(v4) = v4 - 1;
      }
    }
    while ( v2 < (unsigned int)v4 );
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000fb20  push    rbx
0x18000fb22  push    rbp
0x18000fb23  push    rsi
0x18000fb24  push    rdi
0x18000fb25  push    r14
0x18000fb27  push    r15
0x18000fb29  sub     rsp, 28h
0x18000fb2d  xor     edi, edi
0x18000fb2f  mov     rbp, rdx
0x18000fb32  test    rdx, rdx
0x18000fb35  jz      short loc_18000FB46
0x18000fb37  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000fb3b  inc     rbx
0x18000fb3e  cmp     [rbx+rdx], dil
0x18000fb42  jnz     short loc_18000FB3B
0x18000fb44  jmp     short loc_18000FB48
0x18000fb46  xor     ebx, ebx
0x18000fb48  xor     esi, esi
0x18000fb4a  cmp     ecx, 4B0h
0x18000fb50  cmovnz  esi, ecx
0x18000fb53  test    ebx, ebx
0x18000fb55  jz      short loc_18000FBA3
0x18000fb57  mov     r14d, edi
0x18000fb5a  mov     ecx, esi; CodePage
0x18000fb5c  add     r14, rbp
0x18000fb5f  mov     dl, [r14]; TestChar
0x18000fb62  call    cs:__imp_IsDBCSLeadByteEx
0x18000fb68  test    eax, eax
0x18000fb6a  jz      short loc_18000FB71
0x18000fb6c  add     edi, 2
0x18000fb6f  jmp     short loc_18000FB9F
0x18000fb71  mov     dl, [r14]
0x18000fb74  lea     r15d, [rdi+1]
0x18000fb78  mov     ecx, esi; CodePage
0x18000fb7a  call    FIsValidFileNameCharA
0x18000fb7f  test    eax, eax
0x18000fb81  jnz     short loc_18000FB9C
0x18000fb83  mov     r8d, ebx
0x18000fb86  mov     edx, r15d
0x18000fb89  sub     r8d, edi
0x18000fb8c  add     rdx, rbp
0x18000fb8f  mov     rcx, r14
0x18000fb92  call    cs:__imp_RtlMoveMemory
0x18000fb98  dec     ebx
0x18000fb9a  jmp     short loc_18000FB9F
0x18000fb9c  mov     edi, r15d
0x18000fb9f  cmp     edi, ebx
0x18000fba1  jb      short loc_18000FB57
0x18000fba3  mov     eax, ebx
0x18000fba5  add     rsp, 28h
0x18000fba9  pop     r15
0x18000fbab  pop     r14
0x18000fbad  pop     rdi
0x18000fbae  pop     rsi
0x18000fbaf  pop     rbp
0x18000fbb0  pop     rbx
0x18000fbb1  retn
```
