# wil_details_RecordCachedUsage

- ea: `0x180011360`
- end: `0x1800114a6`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016dc4`

## callees

- `0x180011360`
- `0x1800173f4`
- `0x18001aec0`

## pseudocode

```c
void __fastcall wil_details_RecordCachedUsage(int a1, __int64 a2)
{
  unsigned __int32 v3; // ecx
  int v4; // r8d
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned int v7; // eax
  char *v8; // rdx
  unsigned __int64 v9; // r8
  __int64 v10; // rdx
  _DWORD v11[2]; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+28h] [rbp-40h] BYREF

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
    v11[0] = a1;
    v8 = &v12;
    v11[1] = 65538;
  }
  else
  {
    v8 = (char *)v11;
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
  v9 = v3 >> 5;
  if ( (v9 & 0x1FF) != 0 )
  {
    LOWORD(v9) = v9 & 0x1FF;
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = v9;
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
  v10 = (v8 - (char *)v11) >> 3;
  if ( v10 > 0 )
    wil::details::WilApi_RecordFeatureUsageReports((wil::details *)v11, (struct __WIL_RTL_FEATURE_USAGE_DATA *)v10, v9);
}

```

## disassembly

```asm
0x180011360  sub     rsp, 68h
0x180011364  mov     rax, cs:__security_cookie
0x18001136b  xor     rax, rsp
0x18001136e  mov     [rsp+68h+var_18], rax
0x180011373  mov     r9, rdx
0x180011376  mov     r10d, ecx
0x180011379  prefetchw byte ptr [rdx]
0x18001137c  mov     eax, [rdx]
0x18001137e  mov     r8d, eax
0x180011381  and     r8d, 0FFC0401Eh
0x180011388  lock cmpxchg [rdx], r8d
0x18001138d  jnz     short loc_18001137E
0x18001138f  mov     r8d, eax
0x180011392  mov     ecx, eax
0x180011394  shr     r8d, 1
0x180011397  and     r8d, 0Fh
0x18001139b  jz      short loc_1800113B8
0x18001139d  prefetchw byte ptr [rdx+4]
0x1800113a1  mov     eax, [rdx+4]
0x1800113a4  mov     edx, eax
0x1800113a6  or      edx, r8d
0x1800113a9  lock cmpxchg [r9+4], edx
0x1800113af  jnz     short loc_1800113A4
0x1800113b1  not     eax
0x1800113b3  and     eax, r8d
0x1800113b6  jmp     short loc_1800113BB
0x1800113b8  mov     eax, r8d
0x1800113bb  mov     r8d, 2
0x1800113c1  lea     r9d, [r8-1]
0x1800113c5  test    r9b, al
0x1800113c8  jz      short loc_1800113DE
0x1800113ca  mov     [rsp+68h+var_48], r10d
0x1800113cf  lea     rdx, [rsp+68h+var_40]
0x1800113d4  mov     [rsp+68h+var_44], 10002h
0x1800113dc  jmp     short loc_1800113E3
0x1800113de  lea     rdx, [rsp+68h+var_48]
0x1800113e3  test    r8b, al
0x1800113e6  jz      short loc_1800113F6
0x1800113e8  mov     [rdx], r10d
0x1800113eb  mov     dword ptr [rdx+4], 10006h
0x1800113f2  add     rdx, 8
0x1800113f6  test    al, 4
0x1800113f8  jz      short loc_180011408
0x1800113fa  mov     [rdx], r10d
0x1800113fd  mov     dword ptr [rdx+4], 10003h
0x180011404  add     rdx, 8
0x180011408  cmp     eax, 8
0x18001140b  jb      short loc_18001141B
0x18001140d  mov     [rdx], r10d
0x180011410  mov     dword ptr [rdx+4], 10007h
0x180011417  add     rdx, 8
0x18001141b  mov     r8d, ecx
0x18001141e  mov     r11d, 1FFh
0x180011424  shr     r8d, 5
0x180011428  test    r11d, r8d
0x18001142b  jz      short loc_18001144E
0x18001142d  and     r8w, r11w; unsigned __int64
0x180011431  mov     [rdx], r10d
0x180011434  mov     eax, ecx
0x180011436  mov     [rdx+6], r8w
0x18001143b  shr     eax, 0Eh
0x18001143e  and     ax, r9w
0x180011442  shl     ax, 2
0x180011446  mov     [rdx+4], ax
0x18001144a  add     rdx, 8
0x18001144e  mov     eax, ecx
0x180011450  shr     eax, 0Fh
0x180011453  test    al, 7Fh
0x180011455  jz      short loc_180011479
0x180011457  shr     ecx, 16h
0x18001145a  and     ax, 7Fh
0x18001145e  and     cx, r9w
0x180011462  mov     [rdx], r10d
0x180011465  shl     cx, 2
0x180011469  add     cx, r9w
0x18001146d  mov     [rdx+6], ax
0x180011471  mov     [rdx+4], cx
0x180011475  add     rdx, 8
0x180011479  lea     rax, [rsp+68h+var_48]
0x18001147e  sub     rdx, rax
0x180011481  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180011485  test    rdx, rdx
0x180011488  jle     short loc_180011494
0x18001148a  lea     rcx, [rsp+68h+var_48]; this
0x18001148f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180011494  mov     rcx, [rsp+68h+var_18]
0x180011499  xor     rcx, rsp; StackCookie
0x18001149c  call    __security_check_cookie
0x1800114a1  add     rsp, 68h
0x1800114a5  retn
```
