# wil_details_RecordCachedUsage

- ea: `0x1400013f4`
- end: `0x140001542`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007b40`

## callees

- `0x1400013f4`
- `0x140001820`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140001523`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140001523`

## pseudocode

```c
_DWORD *__fastcall wil_details_RecordCachedUsage(int a1, __int64 a2)
{
  unsigned __int32 v3; // ecx
  int v4; // r8d
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned int v7; // eax
  char *v8; // rdx
  _DWORD *result; // rax
  _DWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+28h] [rbp-40h] BYREF

  _m_prefetchw((const void *)a2);
  v3 = _InterlockedAnd((volatile signed __int32 *)a2, 0xFFC0401E);
  v4 = (v3 >> 1) & 0xF;
  if ( v4 )
  {
    _m_prefetchw((const void *)(a2 + 4));
    v5 = *(_DWORD *)(a2 + 4);
    do
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 4), v4 | v5, v5);
    }
    while ( v6 != v5 );
    v7 = v4 & ~v5;
  }
  else
  {
    v7 = 0;
  }
  if ( (v7 & 1) != 0 )
  {
    v10[0] = a1;
    v8 = &v11;
    v10[1] = 65538;
  }
  else
  {
    v8 = (char *)v10;
  }
  if ( (v7 & 2) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65542;
    v8 += 8;
  }
  if ( (v7 & 4) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65539;
    v8 += 8;
  }
  if ( v7 >= 8 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65543;
    v8 += 8;
  }
  if ( ((v3 >> 5) & 0x1FF) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = (v3 >> 5) & 0x1FF;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 14) & 1);
    v8 += 8;
  }
  if ( ((v3 >> 15) & 0x7F) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = (v3 >> 15) & 0x7F;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 22) & 1) + 1;
    v8 += 8;
  }
  result = v10;
  if ( (v8 - (char *)v10) >> 3 > 0 )
    return (_DWORD *)RtlRecordFeatureUsage(v10);
  return result;
}

```

## disassembly

```asm
0x1400013f4  sub     rsp, 68h
0x1400013f8  mov     rax, cs:__security_cookie
0x1400013ff  xor     rax, rsp
0x140001402  mov     [rsp+68h+var_18], rax
0x140001407  mov     r9, rdx
0x14000140a  mov     r10d, ecx
0x14000140d  prefetchw byte ptr [rdx]
0x140001410  mov     eax, [rdx]
0x140001412  mov     r8d, eax
0x140001415  and     r8d, 0FFC0401Eh
0x14000141c  lock cmpxchg [rdx], r8d
0x140001421  jnz     short loc_140001412
0x140001423  mov     r8d, eax
0x140001426  mov     ecx, eax
0x140001428  shr     r8d, 1
0x14000142b  and     r8d, 0Fh
0x14000142f  jz      short loc_14000144C
0x140001431  prefetchw byte ptr [rdx+4]
0x140001435  mov     eax, [rdx+4]
0x140001438  mov     edx, eax
0x14000143a  or      edx, r8d
0x14000143d  lock cmpxchg [r9+4], edx
0x140001443  jnz     short loc_140001438
0x140001445  not     eax
0x140001447  and     eax, r8d
0x14000144a  jmp     short loc_14000144F
0x14000144c  mov     eax, r8d
0x14000144f  mov     r8d, 2
0x140001455  lea     r9d, [r8-1]
0x140001459  test    r9b, al
0x14000145c  jz      short loc_140001472
0x14000145e  mov     [rsp+68h+var_48], r10d
0x140001463  lea     rdx, [rsp+68h+var_40]
0x140001468  mov     [rsp+68h+var_44], 10002h
0x140001470  jmp     short loc_140001477
0x140001472  lea     rdx, [rsp+68h+var_48]
0x140001477  test    r8b, al
0x14000147a  jz      short loc_14000148A
0x14000147c  mov     [rdx], r10d
0x14000147f  mov     dword ptr [rdx+4], 10006h
0x140001486  add     rdx, 8
0x14000148a  test    al, 4
0x14000148c  jz      short loc_14000149C
0x14000148e  mov     [rdx], r10d
0x140001491  mov     dword ptr [rdx+4], 10003h
0x140001498  add     rdx, 8
0x14000149c  cmp     eax, 8
0x14000149f  jb      short loc_1400014AF
0x1400014a1  mov     [rdx], r10d
0x1400014a4  mov     dword ptr [rdx+4], 10007h
0x1400014ab  add     rdx, 8
0x1400014af  mov     r8d, ecx
0x1400014b2  mov     r11d, 1FFh
0x1400014b8  shr     r8d, 5
0x1400014bc  test    r11d, r8d
0x1400014bf  jz      short loc_1400014E2
0x1400014c1  and     r8w, r11w
0x1400014c5  mov     [rdx], r10d
0x1400014c8  mov     eax, ecx
0x1400014ca  mov     [rdx+6], r8w
0x1400014cf  shr     eax, 0Eh
0x1400014d2  and     ax, r9w
0x1400014d6  shl     ax, 2
0x1400014da  mov     [rdx+4], ax
0x1400014de  add     rdx, 8
0x1400014e2  mov     eax, ecx
0x1400014e4  shr     eax, 0Fh
0x1400014e7  test    al, 7Fh
0x1400014e9  jz      short loc_14000150D
0x1400014eb  shr     ecx, 16h
0x1400014ee  and     ax, 7Fh
0x1400014f2  and     cx, r9w
0x1400014f6  mov     [rdx], r10d
0x1400014f9  shl     cx, 2
0x1400014fd  add     cx, r9w
0x140001501  mov     [rdx+6], ax
0x140001505  mov     [rdx+4], cx
0x140001509  add     rdx, 8
0x14000150d  lea     rax, [rsp+68h+var_48]
0x140001512  sub     rdx, rax
0x140001515  sar     rdx, 3
0x140001519  test    rdx, rdx
0x14000151c  jle     short loc_14000152F
0x14000151e  lea     rcx, [rsp+68h+var_48]
0x140001523  call    cs:__imp_RtlRecordFeatureUsage
0x14000152a  nop     dword ptr [rax+rax+00h]
0x14000152f  mov     rcx, [rsp+68h+var_18]
0x140001534  xor     rcx, rsp; StackCookie
0x140001537  call    __security_check_cookie
0x14000153c  add     rsp, 68h
0x140001540  retn
```
