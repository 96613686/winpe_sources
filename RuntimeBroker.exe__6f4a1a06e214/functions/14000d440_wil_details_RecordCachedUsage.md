# wil_details_RecordCachedUsage

- ea: `0x14000d440`
- end: `0x14000d586`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000c21c`

## callees

- `0x140008c80`
- `0x14000cbc4`
- `0x14000d440`

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
0x14000d440  sub     rsp, 68h
0x14000d444  mov     rax, cs:__security_cookie
0x14000d44b  xor     rax, rsp
0x14000d44e  mov     [rsp+68h+var_18], rax
0x14000d453  mov     r9, rdx
0x14000d456  mov     r10d, ecx
0x14000d459  prefetchw byte ptr [rdx]
0x14000d45c  mov     eax, [rdx]
0x14000d45e  mov     r8d, eax
0x14000d461  and     r8d, 0FFC0401Eh
0x14000d468  lock cmpxchg [rdx], r8d
0x14000d46d  jnz     short loc_14000D45E
0x14000d46f  mov     r8d, eax
0x14000d472  mov     ecx, eax
0x14000d474  shr     r8d, 1
0x14000d477  and     r8d, 0Fh
0x14000d47b  jz      short loc_14000D498
0x14000d47d  prefetchw byte ptr [rdx+4]
0x14000d481  mov     eax, [rdx+4]
0x14000d484  mov     edx, eax
0x14000d486  or      edx, r8d
0x14000d489  lock cmpxchg [r9+4], edx
0x14000d48f  jnz     short loc_14000D484
0x14000d491  not     eax
0x14000d493  and     eax, r8d
0x14000d496  jmp     short loc_14000D49B
0x14000d498  mov     eax, r8d
0x14000d49b  mov     r8d, 2
0x14000d4a1  lea     r9d, [r8-1]
0x14000d4a5  test    r9b, al
0x14000d4a8  jz      short loc_14000D4BE
0x14000d4aa  mov     [rsp+68h+var_48], r10d
0x14000d4af  lea     rdx, [rsp+68h+var_40]
0x14000d4b4  mov     [rsp+68h+var_44], 10002h
0x14000d4bc  jmp     short loc_14000D4C3
0x14000d4be  lea     rdx, [rsp+68h+var_48]
0x14000d4c3  test    r8b, al
0x14000d4c6  jz      short loc_14000D4D6
0x14000d4c8  mov     [rdx], r10d
0x14000d4cb  mov     dword ptr [rdx+4], 10006h
0x14000d4d2  add     rdx, 8
0x14000d4d6  test    al, 4
0x14000d4d8  jz      short loc_14000D4E8
0x14000d4da  mov     [rdx], r10d
0x14000d4dd  mov     dword ptr [rdx+4], 10003h
0x14000d4e4  add     rdx, 8
0x14000d4e8  cmp     eax, 8
0x14000d4eb  jb      short loc_14000D4FB
0x14000d4ed  mov     [rdx], r10d
0x14000d4f0  mov     dword ptr [rdx+4], 10007h
0x14000d4f7  add     rdx, 8
0x14000d4fb  mov     r8d, ecx
0x14000d4fe  mov     r11d, 1FFh
0x14000d504  shr     r8d, 5
0x14000d508  test    r11d, r8d
0x14000d50b  jz      short loc_14000D52E
0x14000d50d  and     r8w, r11w; unsigned __int64
0x14000d511  mov     [rdx], r10d
0x14000d514  mov     eax, ecx
0x14000d516  mov     [rdx+6], r8w
0x14000d51b  shr     eax, 0Eh
0x14000d51e  and     ax, r9w
0x14000d522  shl     ax, 2
0x14000d526  mov     [rdx+4], ax
0x14000d52a  add     rdx, 8
0x14000d52e  mov     eax, ecx
0x14000d530  shr     eax, 0Fh
0x14000d533  test    al, 7Fh
0x14000d535  jz      short loc_14000D559
0x14000d537  shr     ecx, 16h
0x14000d53a  and     ax, 7Fh
0x14000d53e  and     cx, r9w
0x14000d542  mov     [rdx], r10d
0x14000d545  shl     cx, 2
0x14000d549  add     cx, r9w
0x14000d54d  mov     [rdx+6], ax
0x14000d551  mov     [rdx+4], cx
0x14000d555  add     rdx, 8
0x14000d559  lea     rax, [rsp+68h+var_48]
0x14000d55e  sub     rdx, rax
0x14000d561  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x14000d565  test    rdx, rdx
0x14000d568  jle     short loc_14000D574
0x14000d56a  lea     rcx, [rsp+68h+var_48]; this
0x14000d56f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x14000d574  mov     rcx, [rsp+68h+var_18]
0x14000d579  xor     rcx, rsp; StackCookie
0x14000d57c  call    __security_check_cookie
0x14000d581  add     rsp, 68h
0x14000d585  retn
```
