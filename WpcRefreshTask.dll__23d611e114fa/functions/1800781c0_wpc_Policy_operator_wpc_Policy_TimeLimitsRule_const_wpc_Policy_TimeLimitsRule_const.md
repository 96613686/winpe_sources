# wpc::Policy::operator==(wpc::Policy::TimeLimitsRule const &,wpc::Policy::TimeLimitsRule const &)

- ea: `0x1800781c0`
- end: `0x1800782a7`
- name: `??8Policy@wpc@@YA_NAEBUTimeLimitsRule@01@0@Z`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800777a8`
- `0x1800782b0`

## callees

- `0x1800778ec`
- `0x1800781c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180078236`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180078251`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180078236`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180078251`

## pseudocode

```c
char __fastcall wpc::Policy::operator==(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  char v5; // r14
  __int64 v6; // rdi
  int v7; // eax

  if ( *(_BYTE *)a1 != *(_BYTE *)a2 || *(_BYTE *)(a1 + 1) != *(_BYTE *)(a2 + 1) )
    return 0;
  v4 = *(_QWORD *)(a2 + 48);
  v5 = 1;
  v6 = *(_QWORD *)(((a1 + 8) & -(__int64)(a1 != -9)) + 0x28);
  if ( v6 != v4 )
  {
    if ( v6 )
    {
      if ( !v4 )
        return 0;
      if ( *(_BYTE *)v6 < *(_BYTE *)v4
        || *(_BYTE *)v6 == *(_BYTE *)v4 && CompareFileTime((const FILETIME *)(v6 + 4), (const FILETIME *)(v4 + 4)) < 0 )
      {
        v7 = -1;
      }
      else
      {
        v7 = *(_BYTE *)v4 < *(_BYTE *)v6
          || *(_BYTE *)v4 == *(_BYTE *)v6 && CompareFileTime((const FILETIME *)(v4 + 4), (const FILETIME *)(v6 + 4)) < 0;
      }
    }
    else
    {
      v7 = -(v4 != 0);
    }
    if ( !v7 )
      goto LABEL_17;
    return 0;
  }
LABEL_17:
  if ( *(_QWORD *)(a1 + 64) != *(_QWORD *)(a2 + 64)
    || !(unsigned __int8)std::equal<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Day const,wpc::Policy::TimeRestriction>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Day const,wpc::Policy::TimeRestriction>>>,std::_Iterator_base0>>(
                           **(_QWORD **)(a1 + 56),
                           *(_QWORD *)(a1 + 56),
                           **(_QWORD **)(a2 + 56)) )
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800781c0  push    rbx
0x1800781c2  push    rbp
0x1800781c3  push    rsi
0x1800781c4  push    rdi
0x1800781c5  push    r12
0x1800781c7  push    r14
0x1800781c9  push    r15
0x1800781cb  sub     rsp, 20h
0x1800781cf  mov     al, [rdx]
0x1800781d1  mov     rsi, rdx
0x1800781d4  mov     rbp, rcx
0x1800781d7  cmp     [rcx], al
0x1800781d9  jnz     loc_180078292
0x1800781df  mov     al, [rdx+1]
0x1800781e2  cmp     [rcx+1], al
0x1800781e5  jnz     loc_180078292
0x1800781eb  mov     rbx, [rdx+30h]
0x1800781ef  lea     r8, [rcx+8]
0x1800781f3  lea     rax, [r8+1]
0x1800781f7  mov     r14d, 1
0x1800781fd  neg     rax
0x180078200  sbb     rcx, rcx
0x180078203  and     rcx, r8
0x180078206  mov     rdi, [rcx+28h]
0x18007820a  cmp     rdi, rbx
0x18007820d  jz      short loc_18007826E
0x18007820f  test    rdi, rdi
0x180078212  jnz     short loc_18007821B
0x180078214  neg     rbx
0x180078217  sbb     eax, eax
0x180078219  jmp     short loc_18007826A
0x18007821b  test    rbx, rbx
0x18007821e  jz      short loc_180078292
0x180078220  mov     al, [rdi]
0x180078222  cmp     al, [rbx]
0x180078224  jb      short loc_180078267
0x180078226  lea     r15, [rbx+4]
0x18007822a  lea     r12, [rdi+4]
0x18007822e  jnz     short loc_180078243
0x180078230  mov     rdx, r15; lpFileTime2
0x180078233  mov     rcx, r12; lpFileTime1
0x180078236  call    cs:__imp_CompareFileTime
0x18007823c  shr     eax, 1Fh
0x18007823f  test    al, al
0x180078241  jnz     short loc_180078267
0x180078243  mov     al, [rbx]
0x180078245  cmp     al, [rdi]
0x180078247  jb      short loc_180078262
0x180078249  jnz     short loc_18007825E
0x18007824b  mov     rdx, r12; lpFileTime2
0x18007824e  mov     rcx, r15; lpFileTime1
0x180078251  call    cs:__imp_CompareFileTime
0x180078257  shr     eax, 1Fh
0x18007825a  test    al, al
0x18007825c  jnz     short loc_180078262
0x18007825e  xor     eax, eax
0x180078260  jmp     short loc_18007826A
0x180078262  mov     eax, r14d
0x180078265  jmp     short loc_18007826A
0x180078267  or      eax, 0FFFFFFFFh
0x18007826a  test    eax, eax
0x18007826c  jnz     short loc_180078292
0x18007826e  mov     rax, [rsi+40h]
0x180078272  cmp     [rbp+40h], rax
0x180078276  jnz     short loc_180078292
0x180078278  mov     rcx, [rbp+38h]
0x18007827c  mov     r8, [rsi+38h]
0x180078280  mov     rdx, rcx
0x180078283  mov     rcx, [rcx]
0x180078286  mov     r8, [r8]
0x180078289  call    ??$equal@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVDay@@UTimeRestriction@Policy@wpc@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@std@@YA_NV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVDay@@UTimeRestriction@Policy@wpc@@@std@@@std@@@std@@U_Iterator_base0@2@@0@00@Z; std::equal<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Day const,wpc::Policy::TimeRestriction>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Day const,wpc::Policy::TimeRestriction>>>,std::_Iterator_base0>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Day const,wpc::Policy::TimeRestriction>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Day const,wpc::Policy::TimeRestriction>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Day const,wpc::Policy::TimeRestriction>>>,std::_Iterator_base0>)
0x18007828e  test    al, al
0x180078290  jnz     short loc_180078295
0x180078292  xor     r14b, r14b
0x180078295  mov     al, r14b
0x180078298  add     rsp, 20h
0x18007829c  pop     r15
0x18007829e  pop     r14
0x1800782a0  pop     r12
0x1800782a2  pop     rdi
0x1800782a3  pop     rsi
0x1800782a4  pop     rbp
0x1800782a5  pop     rbx
0x1800782a6  retn
```
