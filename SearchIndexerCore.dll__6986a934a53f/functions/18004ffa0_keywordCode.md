# keywordCode

- ea: `0x18004ffa0`
- end: `0x180050088`
- name: `keywordCode`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004f7c8`
- `0x180092dc4`

## callees

- `0x18004ffa0`

## string_xrefs

- `0x18005001d`: `REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXPLAINSTEADDATABASELECTABLEFTHENDEFERRABLELSEXCLUDELETEMPORARYISNULLSAVEPOINTERSECTIESNOTNULLIKEXCEPTRANSACTIONATURALTERAISEXCLUSIVEXISTSCONSTRAINTOFFSETRIGGERANGENERATEDETACHAVINGLOBEGINNEREFERENCESUNIQUERYWITHOUTERELEASEATTACHBETWEENOTHINGROUPSCASCADEFAULTCASECOLLATECREATECURRENT_DATEIMMEDIATEJOINSERTMATCHPLANALYZEPRAGMATERIALIZEDEFERREDISTINCTUPDATEVALUESVIRTUALWAYSWHENWHERECURSIVEABORTAFTERENAMEANDROPARTITIONAUTOINCREMENTCASTCOLUMNCOMMITCONFLICTCROSSCURRE`

## pseudocode

```c
__int64 __fastcall keywordCode(unsigned __int8 *a1, int a2, _DWORD *a3)
{
  __int64 v3; // rdi
  __int64 i; // rcx
  char *v7; // r8
  int v8; // eax

  v3 = *a1;
  for ( i = *((unsigned __int8 *)qword_1800C1360
            + (a2
             ^ (4 * *((unsigned __int8 *)qword_1800B4ED0 + v3))
             ^ (3 * *((unsigned __int8 *)qword_1800B4ED0 + a1[a2 - 1])))
            % 127); (_DWORD)i; i = *((unsigned __int8 *)qword_1800C13F0 + (unsigned int)i) )
  {
    if ( *((unsigned __int8 *)qword_1800BD5F0 + i) == a2 )
    {
      v7 = &aReindexedescap[(unsigned __int16)word_1800BDCE0[i]];
      if ( (v3 & 0xDF) == *v7 && (a1[1] & 0xDF) == v7[1] )
      {
        v8 = 2;
        if ( a2 <= 2 )
        {
LABEL_9:
          *a3 = *((unsigned __int8 *)qword_1800BDE70 + (unsigned int)i);
          return (unsigned int)a2;
        }
        while ( (a1[v8] & 0xDF) == v7[v8] )
        {
          if ( ++v8 >= a2 )
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
0x18004ffa0  push    rbx
0x18004ffa2  push    rsi
0x18004ffa3  push    rdi
0x18004ffa4  movzx   edi, byte ptr [rcx]
0x18004ffa7  lea     rsi, __ImageBase
0x18004ffae  movsxd  r10, edx
0x18004ffb1  mov     r11, rcx
0x18004ffb4  mov     rbx, r8
0x18004ffb7  movzx   r9d, byte ptr [r10+rcx-1]
0x18004ffbd  movzx   eax, byte ptr [r9+rsi+0B4ED0h]
0x18004ffc6  lea     r9d, [rax+rax*2]
0x18004ffca  movzx   eax, byte ptr [rdi+rsi+0B4ED0h]
0x18004ffd2  shl     eax, 2
0x18004ffd5  xor     r9d, eax
0x18004ffd8  mov     eax, 81020409h
0x18004ffdd  xor     r9d, r10d
0x18004ffe0  imul    r9d
0x18004ffe3  add     edx, r9d
0x18004ffe6  sar     edx, 6
0x18004ffe9  mov     eax, edx
0x18004ffeb  shr     eax, 1Fh
0x18004ffee  add     edx, eax
0x18004fff0  imul    eax, edx, 7Fh
0x18004fff3  sub     r9d, eax
0x18004fff6  movsxd  rax, r9d
0x18004fff9  movzx   ecx, byte ptr [rax+rsi+0C1360h]
0x180050001  test    ecx, ecx
0x180050003  jz      short loc_180050073
0x180050005  movzx   eax, byte ptr [rcx+rsi+0BD5F0h]
0x18005000d  mov     r9d, ecx
0x180050010  cmp     eax, r10d
0x180050013  jnz     short loc_18005007A
0x180050015  movzx   eax, ds:rva word_1800BDCE0[rsi+rcx*2]
0x18005001d  lea     r8, rva aReindexedescap[rsi]; "REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXP"... ...
0x180050024  add     r8, rax
0x180050027  movzx   eax, dil
0x18005002b  and     al, 0DFh
0x18005002d  cmp     al, [r8]
0x180050030  jnz     short loc_18005007A
0x180050032  movzx   eax, byte ptr [r11+1]
0x180050037  and     al, 0DFh
0x180050039  cmp     al, [r8+1]
0x18005003d  jnz     short loc_18005007A
0x18005003f  mov     eax, 2
0x180050044  cmp     r10d, eax
0x180050047  jle     short loc_180050068
0x180050049  nop     dword ptr [rax+00000000h]
0x180050050  movsxd  rdx, eax
0x180050053  movzx   ecx, byte ptr [rdx+r11]
0x180050058  and     cl, 0DFh
0x18005005b  cmp     cl, [rdx+r8]
0x18005005f  jnz     short loc_18005007A
0x180050061  inc     eax
0x180050063  cmp     eax, r10d
0x180050066  jl      short loc_180050050
0x180050068  movzx   eax, byte ptr [r9+rsi+0BDE70h]
0x180050071  mov     [rbx], eax
0x180050073  mov     eax, r10d
0x180050076  pop     rdi
0x180050077  pop     rsi
0x180050078  pop     rbx
0x180050079  retn
0x18005007a  movzx   ecx, byte ptr [r9+rsi+0C13F0h]
0x180050083  jmp     loc_180050001
```
