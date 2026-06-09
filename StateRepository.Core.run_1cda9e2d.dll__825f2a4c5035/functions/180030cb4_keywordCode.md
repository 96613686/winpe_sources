# keywordCode

- ea: `0x180030cb4`
- end: `0x180030d8f`
- name: `keywordCode`
- size: `219`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003114c`
- `0x1800849a4`

## callees

- `0x180030cb4`

## string_xrefs

- `0x180030d31`: `REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXPLAINSTEADDATABASELECTABLEFTHENDEFERRABLELSEXCLUDELETEMPORARYISNULLSAVEPOINTERSECTIESNOTNULLIKEXCEPTRANSACTIONATURALTERAISEXCLUSIVEXISTSCONSTRAINTOFFSETRIGGERANGENERATEDETACHAVINGLOBEGINNEREFERENCESUNIQUERYWITHOUTERELEASEATTACHBETWEENOTHINGROUPSCASCADEFAULTCASECOLLATECREATECURRENT_DATEIMMEDIATEJOINSERTMATCHPLANALYZEPRAGMATERIALIZEDEFERREDISTINCTUPDATEVALUESVIRTUALWAYSWHENWHERECURSIVEABORTAFTERENAMEANDROPARTITIONAUTOINCREMENTCASTCOLUMNCOMMITCONFLICTCROSSCURRE`

## pseudocode

```c
__int64 __fastcall keywordCode(unsigned __int8 *a1, int a2, _DWORD *a3)
{
  __int64 v3; // rdi
  __int64 i; // rcx
  char *v7; // r9
  unsigned int v8; // edx

  v3 = *a1;
  for ( i = byte_1800AA9A0[(a2 ^ (4 * byte_18009E760[v3]) ^ (3 * byte_18009E760[a1[a2 - 1]])) % 127];
        (_DWORD)i;
        i = byte_1800AAA30[(unsigned int)i] )
  {
    if ( byte_1800A6880[i] == a2 )
    {
      v7 = &aReindexedescap[(unsigned __int16)word_1800A6F70[i]];
      if ( (v3 & 0xDF) == *v7 && (a1[1] & 0xDF) == v7[1] )
      {
        v8 = 2;
        if ( a2 <= 2 )
        {
LABEL_7:
          *a3 = byte_1800A7290[(unsigned int)i];
          return (unsigned int)a2;
        }
        while ( (a1[v8] & 0xDF) == v7[v8] )
        {
          if ( (int)++v8 >= a2 )
            goto LABEL_7;
        }
      }
    }
  }
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x180030cb4  push    rbx
0x180030cb6  push    rsi
0x180030cb7  push    rdi
0x180030cb8  movzx   edi, byte ptr [rcx]
0x180030cbb  lea     rsi, cs:180000000h
0x180030cc2  movsxd  r10, edx
0x180030cc5  mov     r11, rcx
0x180030cc8  mov     rbx, r8
0x180030ccb  movzx   r9d, byte ptr [r10+rcx-1]
0x180030cd1  movzx   eax, byte ptr [r9+rsi+9E760h]
0x180030cda  lea     r9d, [rax+rax*2]
0x180030cde  movzx   eax, byte ptr [rdi+rsi+9E760h]
0x180030ce6  shl     eax, 2
0x180030ce9  xor     r9d, eax
0x180030cec  mov     eax, 81020409h
0x180030cf1  xor     r9d, r10d
0x180030cf4  imul    r9d
0x180030cf7  add     edx, r9d
0x180030cfa  sar     edx, 6
0x180030cfd  mov     eax, edx
0x180030cff  shr     eax, 1Fh
0x180030d02  add     edx, eax
0x180030d04  imul    eax, edx, 7Fh
0x180030d07  sub     r9d, eax
0x180030d0a  movsxd  rax, r9d
0x180030d0d  movzx   ecx, byte ptr [rax+rsi+0AA9A0h]
0x180030d15  test    ecx, ecx
0x180030d17  jz      short loc_180030D66
0x180030d19  movzx   eax, byte ptr [rcx+rsi+0A6880h]
0x180030d21  mov     r8d, ecx
0x180030d24  cmp     eax, r10d
0x180030d27  jnz     short loc_180030D7B
0x180030d29  movzx   eax, ds:rva word_1800A6F70[rsi+rcx*2]
0x180030d31  lea     r9, rva aReindexedescap[rsi]; "REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXP"... ...
0x180030d38  add     r9, rax
0x180030d3b  mov     al, dil
0x180030d3e  and     al, 0DFh
0x180030d40  cmp     al, [r9]
0x180030d43  jnz     short loc_180030D7B
0x180030d45  mov     al, [r11+1]
0x180030d49  and     al, 0DFh
0x180030d4b  cmp     al, [r9+1]
0x180030d4f  jnz     short loc_180030D7B
0x180030d51  mov     edx, 2
0x180030d56  cmp     r10d, edx
0x180030d59  jg      short loc_180030D6D
0x180030d5b  movzx   eax, byte ptr [r8+rsi+0A7290h]
0x180030d64  mov     [rbx], eax
0x180030d66  mov     eax, r10d
0x180030d69  pop     rdi
0x180030d6a  pop     rsi
0x180030d6b  pop     rbx
0x180030d6c  retn
0x180030d6d  mov     ecx, edx
0x180030d6f  mov     al, [r11+rcx]
0x180030d73  and     al, 0DFh
0x180030d75  cmp     al, [r9+rcx]
0x180030d79  jz      short loc_180030D86
0x180030d7b  movzx   ecx, byte ptr [r8+rsi+0AAA30h]
0x180030d84  jmp     short loc_180030D15
0x180030d86  inc     edx
0x180030d88  cmp     edx, r10d
0x180030d8b  jge     short loc_180030D5B
0x180030d8d  jmp     short loc_180030D6D
```
