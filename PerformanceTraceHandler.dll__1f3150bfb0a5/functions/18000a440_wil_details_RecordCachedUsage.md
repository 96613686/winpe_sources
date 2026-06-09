# wil_details_RecordCachedUsage

- ea: `0x18000a440`
- end: `0x18000a587`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007418`

## callees

- `0x180002c00`
- `0x180009074`
- `0x18000a440`

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
    v11[1] = 65538;
    v8 = &v12;
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
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 14) & 1);
    LOWORD(v9) = v9 & 0x1FF;
    *((_WORD *)v8 + 3) = v9;
    v8 += 8;
  }
  if ( ((v3 >> 15) & 0x7F) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 22) & 1) + 1;
    *((_WORD *)v8 + 3) = (v3 >> 15) & 0x7F;
    v8 += 8;
  }
  v10 = (v8 - (char *)v11) >> 3;
  if ( v10 > 0 )
    wil::details::WilApi_RecordFeatureUsageReports((wil::details *)v11, (struct __WIL_RTL_FEATURE_USAGE_DATA *)v10, v9);
}

```

## disassembly

```asm
0x18000a440  sub     rsp, 68h
0x18000a444  mov     rax, cs:__security_cookie
0x18000a44b  xor     rax, rsp
0x18000a44e  mov     [rsp+68h+var_18], rax
0x18000a453  mov     r9, rdx
0x18000a456  mov     r10d, ecx
0x18000a459  prefetchw byte ptr [rdx]
0x18000a45c  mov     eax, [rdx]
0x18000a45e  mov     r8d, eax
0x18000a461  and     r8d, 0FFC0401Eh
0x18000a468  lock cmpxchg [rdx], r8d
0x18000a46d  jnz     short loc_18000A45E
0x18000a46f  mov     ecx, eax
0x18000a471  mov     r8d, eax
0x18000a474  shr     r8d, 1
0x18000a477  and     r8d, 0Fh
0x18000a47b  jz      short loc_18000A498
0x18000a47d  prefetchw byte ptr [rdx+4]
0x18000a481  mov     eax, [rdx+4]
0x18000a484  mov     edx, eax
0x18000a486  or      edx, r8d
0x18000a489  lock cmpxchg [r9+4], edx
0x18000a48f  jnz     short loc_18000A484
0x18000a491  not     eax
0x18000a493  and     eax, r8d
0x18000a496  jmp     short loc_18000A49B
0x18000a498  mov     eax, r8d
0x18000a49b  mov     r8d, 2
0x18000a4a1  lea     r9d, [r8-1]
0x18000a4a5  test    r9b, al
0x18000a4a8  jz      short loc_18000A4BE
0x18000a4aa  mov     [rsp+68h+var_48], r10d
0x18000a4af  mov     [rsp+68h+var_44], 10002h
0x18000a4b7  lea     rdx, [rsp+68h+var_40]
0x18000a4bc  jmp     short loc_18000A4C3
0x18000a4be  lea     rdx, [rsp+68h+var_48]
0x18000a4c3  test    r8b, al
0x18000a4c6  jz      short loc_18000A4D6
0x18000a4c8  mov     [rdx], r10d
0x18000a4cb  mov     dword ptr [rdx+4], 10006h
0x18000a4d2  add     rdx, 8
0x18000a4d6  test    al, 4
0x18000a4d8  jz      short loc_18000A4E8
0x18000a4da  mov     [rdx], r10d
0x18000a4dd  mov     dword ptr [rdx+4], 10003h
0x18000a4e4  add     rdx, 8
0x18000a4e8  cmp     eax, 8
0x18000a4eb  jb      short loc_18000A4FB
0x18000a4ed  mov     [rdx], r10d
0x18000a4f0  mov     dword ptr [rdx+4], 10007h
0x18000a4f7  add     rdx, 8
0x18000a4fb  mov     r8d, ecx
0x18000a4fe  shr     r8d, 5
0x18000a502  mov     r11d, 1FFh
0x18000a508  test    r11d, r8d
0x18000a50b  jz      short loc_18000A52E
0x18000a50d  mov     [rdx], r10d
0x18000a510  mov     eax, ecx
0x18000a512  shr     eax, 0Eh
0x18000a515  and     ax, r9w
0x18000a519  shl     ax, 2
0x18000a51d  mov     [rdx+4], ax
0x18000a521  and     r8w, r11w; unsigned __int64
0x18000a525  mov     [rdx+6], r8w
0x18000a52a  add     rdx, 8
0x18000a52e  mov     eax, ecx
0x18000a530  shr     eax, 0Fh
0x18000a533  test    al, 7Fh
0x18000a535  jz      short loc_18000A559
0x18000a537  mov     [rdx], r10d
0x18000a53a  shr     ecx, 16h
0x18000a53d  and     cx, r9w
0x18000a541  shl     cx, 2
0x18000a545  add     cx, r9w
0x18000a549  mov     [rdx+4], cx
0x18000a54d  and     ax, 7Fh
0x18000a551  mov     [rdx+6], ax
0x18000a555  add     rdx, 8
0x18000a559  lea     rax, [rsp+68h+var_48]
0x18000a55e  sub     rdx, rax
0x18000a561  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000a565  test    rdx, rdx
0x18000a568  jle     short loc_18000A575
0x18000a56a  lea     rcx, [rsp+68h+var_48]; this
0x18000a56f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000a574  nop
0x18000a575  mov     rcx, [rsp+68h+var_18]
0x18000a57a  xor     rcx, rsp; StackCookie
0x18000a57d  call    __security_check_cookie
0x18000a582  add     rsp, 68h
0x18000a586  retn
```
