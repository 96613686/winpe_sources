# keywordCode

- ea: `0x180033d28`
- end: `0x180033e01`
- name: `keywordCode`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800857cc`

## callees

- `0x180033d28`

## string_xrefs

- `0x180033da5`: `REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXPLAINSTEADDATABASELECTABLEFTHENDEFERRABLELSEXCLUDELETEMPORARYISNULLSAVEPOINTERSECTIESNOTNULLIKEXCEPTRANSACTIONATURALTERAISEXCLUSIVEXISTSCONSTRAINTOFFSETRIGGERANGENERATEDETACHAVINGLOBEGINNEREFERENCESUNIQUERYWITHOUTERELEASEATTACHBETWEENOTHINGROUPSCASCADEFAULTCASECOLLATECREATECURRENT_DATEIMMEDIATEJOINSERTMATCHPLANALYZEPRAGMATERIALIZEDEFERREDISTINCTUPDATEVALUESVIRTUALWAYSWHENWHERECURSIVEABORTAFTERENAMEANDROPARTITIONAUTOINCREMENTCASTCOLUMNCOMMITCONFLICTCROSSCURRE`

## pseudocode

```c
__int64 __fastcall keywordCode(unsigned __int8 *a1, int a2, _DWORD *a3)
{
  __int64 v3; // rdi
  __int64 i; // rcx
  char *v7; // r9
  unsigned int v8; // edx

  v3 = *a1;
  for ( i = *((unsigned __int8 *)qword_1800BA7A0
            + (a2
             ^ (4 * *((unsigned __int8 *)qword_1800ADCF0 + v3))
             ^ (3 * *((unsigned __int8 *)qword_1800ADCF0 + a1[a2 - 1])))
            % 127); (_DWORD)i; i = *((unsigned __int8 *)qword_1800BA830 + (unsigned int)i) )
  {
    if ( *((unsigned __int8 *)qword_1800B6540 + i) == a2 )
    {
      v7 = &aReindexedescap[(unsigned __int16)word_1800B6C40[i]];
      if ( (v3 & 0xDF) == *v7 && (a1[1] & 0xDF) == v7[1] )
      {
        v8 = 2;
        if ( a2 <= 2 )
        {
LABEL_9:
          *a3 = *((unsigned __int8 *)&qword_1800B6DC0[52] + (unsigned int)i);
          return (unsigned int)a2;
        }
        while ( (a1[v8] & 0xDF) == v7[v8] )
        {
          if ( (int)++v8 >= a2 )
            goto LABEL_9;
        }
      }
    }
  }
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x180033d28  push    rbx
0x180033d2a  push    rsi
0x180033d2b  push    rdi
0x180033d2c  movzx   edi, byte ptr [rcx]
0x180033d2f  lea     rsi, __ImageBase
0x180033d36  movsxd  r10, edx
0x180033d39  mov     r11, rcx
0x180033d3c  mov     rbx, r8
0x180033d3f  movzx   r9d, byte ptr [r10+rcx-1]
0x180033d45  movzx   eax, byte ptr [r9+rsi+0ADCF0h]
0x180033d4e  lea     r9d, [rax+rax*2]
0x180033d52  movzx   eax, byte ptr [rdi+rsi+0ADCF0h]
0x180033d5a  shl     eax, 2
0x180033d5d  xor     r9d, eax
0x180033d60  mov     eax, 81020409h
0x180033d65  xor     r9d, r10d
0x180033d68  imul    r9d
0x180033d6b  add     edx, r9d
0x180033d6e  sar     edx, 6
0x180033d71  mov     eax, edx
0x180033d73  shr     eax, 1Fh
0x180033d76  add     edx, eax
0x180033d78  imul    eax, edx, 7Fh
0x180033d7b  sub     r9d, eax
0x180033d7e  movsxd  rax, r9d
0x180033d81  movzx   ecx, byte ptr [rax+rsi+0BA7A0h]
0x180033d89  test    ecx, ecx
0x180033d8b  jz      short loc_180033DEF
0x180033d8d  movzx   eax, byte ptr [rcx+rsi+0B6540h]
0x180033d95  mov     r8d, ecx
0x180033d98  cmp     eax, r10d
0x180033d9b  jnz     short loc_180033DF6
0x180033d9d  movzx   eax, ds:rva word_1800B6C40[rsi+rcx*2]
0x180033da5  lea     r9, rva aReindexedescap[rsi]; "REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXP"... ...
0x180033dac  add     r9, rax
0x180033daf  mov     al, dil
0x180033db2  and     al, 0DFh
0x180033db4  cmp     al, [r9]
0x180033db7  jnz     short loc_180033DF6
0x180033db9  mov     al, [r11+1]
0x180033dbd  and     al, 0DFh
0x180033dbf  cmp     al, [r9+1]
0x180033dc3  jnz     short loc_180033DF6
0x180033dc5  mov     edx, 2
0x180033dca  cmp     r10d, edx
0x180033dcd  jle     short loc_180033DE4
0x180033dcf  mov     ecx, edx
0x180033dd1  mov     al, [r11+rcx]
0x180033dd5  and     al, 0DFh
0x180033dd7  cmp     al, [r9+rcx]
0x180033ddb  jnz     short loc_180033DF6
0x180033ddd  inc     edx
0x180033ddf  cmp     edx, r10d
0x180033de2  jl      short loc_180033DCF
0x180033de4  movzx   eax, byte ptr [r8+rsi+0B6F60h]
0x180033ded  mov     [rbx], eax
0x180033def  mov     eax, r10d
0x180033df2  pop     rdi
0x180033df3  pop     rsi
0x180033df4  pop     rbx
0x180033df5  retn
0x180033df6  movzx   ecx, byte ptr [r8+rsi+0BA830h]
0x180033dff  jmp     short loc_180033D89
```
