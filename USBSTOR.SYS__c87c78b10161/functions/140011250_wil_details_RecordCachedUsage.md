# wil_details_RecordCachedUsage

- ea: `0x140011250`
- end: `0x14001139e`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140021610`

## callees

- `0x140011250`
- `0x140013950`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14001137f`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14001137f`

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
0x140011250  sub     rsp, 68h
0x140011254  mov     rax, cs:__security_cookie
0x14001125b  xor     rax, rsp
0x14001125e  mov     [rsp+68h+var_18], rax
0x140011263  mov     r9, rdx
0x140011266  mov     r10d, ecx
0x140011269  prefetchw byte ptr [rdx]
0x14001126c  mov     eax, [rdx]
0x14001126e  mov     r8d, eax
0x140011271  and     r8d, 0FFC0401Eh
0x140011278  lock cmpxchg [rdx], r8d
0x14001127d  jnz     short loc_14001126E
0x14001127f  mov     r8d, eax
0x140011282  mov     ecx, eax
0x140011284  shr     r8d, 1
0x140011287  and     r8d, 0Fh
0x14001128b  jz      short loc_1400112A8
0x14001128d  prefetchw byte ptr [rdx+4]
0x140011291  mov     eax, [rdx+4]
0x140011294  mov     edx, eax
0x140011296  or      edx, r8d
0x140011299  lock cmpxchg [r9+4], edx
0x14001129f  jnz     short loc_140011294
0x1400112a1  not     eax
0x1400112a3  and     eax, r8d
0x1400112a6  jmp     short loc_1400112AB
0x1400112a8  mov     eax, r8d
0x1400112ab  mov     r8d, 2
0x1400112b1  lea     r9d, [r8-1]
0x1400112b5  test    r9b, al
0x1400112b8  jz      short loc_1400112CE
0x1400112ba  mov     [rsp+68h+var_48], r10d
0x1400112bf  lea     rdx, [rsp+68h+var_40]
0x1400112c4  mov     [rsp+68h+var_44], 10002h
0x1400112cc  jmp     short loc_1400112D3
0x1400112ce  lea     rdx, [rsp+68h+var_48]
0x1400112d3  test    r8b, al
0x1400112d6  jz      short loc_1400112E6
0x1400112d8  mov     [rdx], r10d
0x1400112db  mov     dword ptr [rdx+4], 10006h
0x1400112e2  add     rdx, 8
0x1400112e6  test    al, 4
0x1400112e8  jz      short loc_1400112F8
0x1400112ea  mov     [rdx], r10d
0x1400112ed  mov     dword ptr [rdx+4], 10003h
0x1400112f4  add     rdx, 8
0x1400112f8  cmp     eax, 8
0x1400112fb  jb      short loc_14001130B
0x1400112fd  mov     [rdx], r10d
0x140011300  mov     dword ptr [rdx+4], 10007h
0x140011307  add     rdx, 8
0x14001130b  mov     r8d, ecx
0x14001130e  mov     r11d, 1FFh
0x140011314  shr     r8d, 5
0x140011318  test    r11d, r8d
0x14001131b  jz      short loc_14001133E
0x14001131d  and     r8w, r11w
0x140011321  mov     [rdx], r10d
0x140011324  mov     eax, ecx
0x140011326  mov     [rdx+6], r8w
0x14001132b  shr     eax, 0Eh
0x14001132e  and     ax, r9w
0x140011332  shl     ax, 2
0x140011336  mov     [rdx+4], ax
0x14001133a  add     rdx, 8
0x14001133e  mov     eax, ecx
0x140011340  shr     eax, 0Fh
0x140011343  test    al, 7Fh
0x140011345  jz      short loc_140011369
0x140011347  shr     ecx, 16h
0x14001134a  and     ax, 7Fh
0x14001134e  and     cx, r9w
0x140011352  mov     [rdx], r10d
0x140011355  shl     cx, 2
0x140011359  add     cx, r9w
0x14001135d  mov     [rdx+6], ax
0x140011361  mov     [rdx+4], cx
0x140011365  add     rdx, 8
0x140011369  lea     rax, [rsp+68h+var_48]
0x14001136e  sub     rdx, rax
0x140011371  sar     rdx, 3
0x140011375  test    rdx, rdx
0x140011378  jle     short loc_14001138B
0x14001137a  lea     rcx, [rsp+68h+var_48]
0x14001137f  call    cs:__imp_RtlRecordFeatureUsage
0x140011386  nop     dword ptr [rax+rax+00h]
0x14001138b  mov     rcx, [rsp+68h+var_18]
0x140011390  xor     rcx, rsp; StackCookie
0x140011393  call    __security_check_cookie
0x140011398  add     rsp, 68h
0x14001139c  retn
```
