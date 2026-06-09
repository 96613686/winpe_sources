# wil_details_RecordCachedUsage

- ea: `0x14000f4f8`
- end: `0x14000f646`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: `_DWORD *__fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140025af0`

## callees

- `0x14000f4f8`
- `0x140011560`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000f627`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000f627`

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
0x14000f4f8  sub     rsp, 68h
0x14000f4fc  mov     rax, cs:__security_cookie
0x14000f503  xor     rax, rsp
0x14000f506  mov     [rsp+68h+var_18], rax
0x14000f50b  mov     r9, rdx
0x14000f50e  mov     r10d, ecx
0x14000f511  prefetchw byte ptr [rdx]
0x14000f514  mov     eax, [rdx]
0x14000f516  mov     r8d, eax
0x14000f519  and     r8d, 0FFC0401Eh
0x14000f520  lock cmpxchg [rdx], r8d
0x14000f525  jnz     short loc_14000F516
0x14000f527  mov     r8d, eax
0x14000f52a  mov     ecx, eax
0x14000f52c  shr     r8d, 1
0x14000f52f  and     r8d, 0Fh
0x14000f533  jz      short loc_14000F550
0x14000f535  prefetchw byte ptr [rdx+4]
0x14000f539  mov     eax, [rdx+4]
0x14000f53c  mov     edx, eax
0x14000f53e  or      edx, r8d
0x14000f541  lock cmpxchg [r9+4], edx
0x14000f547  jnz     short loc_14000F53C
0x14000f549  not     eax
0x14000f54b  and     eax, r8d
0x14000f54e  jmp     short loc_14000F553
0x14000f550  mov     eax, r8d
0x14000f553  mov     r8d, 2
0x14000f559  lea     r9d, [r8-1]
0x14000f55d  test    r9b, al
0x14000f560  jz      short loc_14000F576
0x14000f562  mov     [rsp+68h+var_48], r10d
0x14000f567  lea     rdx, [rsp+68h+var_40]
0x14000f56c  mov     [rsp+68h+var_44], 10002h
0x14000f574  jmp     short loc_14000F57B
0x14000f576  lea     rdx, [rsp+68h+var_48]
0x14000f57b  test    r8b, al
0x14000f57e  jz      short loc_14000F58E
0x14000f580  mov     [rdx], r10d
0x14000f583  mov     dword ptr [rdx+4], 10006h
0x14000f58a  add     rdx, 8
0x14000f58e  test    al, 4
0x14000f590  jz      short loc_14000F5A0
0x14000f592  mov     [rdx], r10d
0x14000f595  mov     dword ptr [rdx+4], 10003h
0x14000f59c  add     rdx, 8
0x14000f5a0  cmp     eax, 8
0x14000f5a3  jb      short loc_14000F5B3
0x14000f5a5  mov     [rdx], r10d
0x14000f5a8  mov     dword ptr [rdx+4], 10007h
0x14000f5af  add     rdx, 8
0x14000f5b3  mov     r8d, ecx
0x14000f5b6  mov     r11d, 1FFh
0x14000f5bc  shr     r8d, 5
0x14000f5c0  test    r11d, r8d
0x14000f5c3  jz      short loc_14000F5E6
0x14000f5c5  and     r8w, r11w
0x14000f5c9  mov     [rdx], r10d
0x14000f5cc  mov     eax, ecx
0x14000f5ce  mov     [rdx+6], r8w
0x14000f5d3  shr     eax, 0Eh
0x14000f5d6  and     ax, r9w
0x14000f5da  shl     ax, 2
0x14000f5de  mov     [rdx+4], ax
0x14000f5e2  add     rdx, 8
0x14000f5e6  mov     eax, ecx
0x14000f5e8  shr     eax, 0Fh
0x14000f5eb  test    al, 7Fh
0x14000f5ed  jz      short loc_14000F611
0x14000f5ef  shr     ecx, 16h
0x14000f5f2  and     ax, 7Fh
0x14000f5f6  and     cx, r9w
0x14000f5fa  mov     [rdx], r10d
0x14000f5fd  shl     cx, 2
0x14000f601  add     cx, r9w
0x14000f605  mov     [rdx+6], ax
0x14000f609  mov     [rdx+4], cx
0x14000f60d  add     rdx, 8
0x14000f611  lea     rax, [rsp+68h+var_48]
0x14000f616  sub     rdx, rax
0x14000f619  sar     rdx, 3
0x14000f61d  test    rdx, rdx
0x14000f620  jle     short loc_14000F633
0x14000f622  lea     rcx, [rsp+68h+var_48]
0x14000f627  call    cs:__imp_RtlRecordFeatureUsage
0x14000f62e  nop     dword ptr [rax+rax+00h]
0x14000f633  mov     rcx, [rsp+68h+var_18]
0x14000f638  xor     rcx, rsp; StackCookie
0x14000f63b  call    __security_check_cookie
0x14000f640  add     rsp, 68h
0x14000f644  retn
```
