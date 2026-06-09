# wil_details_RecordCachedUsage

- ea: `0x18000a8e0`
- end: `0x18000aa27`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007a44`

## callees

- `0x1800020c0`
- `0x180009994`
- `0x18000a8e0`

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
0x18000a8e0  sub     rsp, 68h
0x18000a8e4  mov     rax, cs:__security_cookie
0x18000a8eb  xor     rax, rsp
0x18000a8ee  mov     [rsp+68h+var_18], rax
0x18000a8f3  mov     r9, rdx
0x18000a8f6  mov     r10d, ecx
0x18000a8f9  prefetchw byte ptr [rdx]
0x18000a8fc  mov     eax, [rdx]
0x18000a8fe  mov     r8d, eax
0x18000a901  and     r8d, 0FFC0401Eh
0x18000a908  lock cmpxchg [rdx], r8d
0x18000a90d  jnz     short loc_18000A8FE
0x18000a90f  mov     ecx, eax
0x18000a911  mov     r8d, eax
0x18000a914  shr     r8d, 1
0x18000a917  and     r8d, 0Fh
0x18000a91b  jz      short loc_18000A938
0x18000a91d  prefetchw byte ptr [rdx+4]
0x18000a921  mov     eax, [rdx+4]
0x18000a924  mov     edx, eax
0x18000a926  or      edx, r8d
0x18000a929  lock cmpxchg [r9+4], edx
0x18000a92f  jnz     short loc_18000A924
0x18000a931  not     eax
0x18000a933  and     eax, r8d
0x18000a936  jmp     short loc_18000A93B
0x18000a938  mov     eax, r8d
0x18000a93b  mov     r8d, 2
0x18000a941  lea     r9d, [r8-1]
0x18000a945  test    r9b, al
0x18000a948  jz      short loc_18000A95E
0x18000a94a  mov     [rsp+68h+var_48], r10d
0x18000a94f  mov     [rsp+68h+var_44], 10002h
0x18000a957  lea     rdx, [rsp+68h+var_40]
0x18000a95c  jmp     short loc_18000A963
0x18000a95e  lea     rdx, [rsp+68h+var_48]
0x18000a963  test    r8b, al
0x18000a966  jz      short loc_18000A976
0x18000a968  mov     [rdx], r10d
0x18000a96b  mov     dword ptr [rdx+4], 10006h
0x18000a972  add     rdx, 8
0x18000a976  test    al, 4
0x18000a978  jz      short loc_18000A988
0x18000a97a  mov     [rdx], r10d
0x18000a97d  mov     dword ptr [rdx+4], 10003h
0x18000a984  add     rdx, 8
0x18000a988  cmp     eax, 8
0x18000a98b  jb      short loc_18000A99B
0x18000a98d  mov     [rdx], r10d
0x18000a990  mov     dword ptr [rdx+4], 10007h
0x18000a997  add     rdx, 8
0x18000a99b  mov     r8d, ecx
0x18000a99e  shr     r8d, 5
0x18000a9a2  mov     r11d, 1FFh
0x18000a9a8  test    r11d, r8d
0x18000a9ab  jz      short loc_18000A9CE
0x18000a9ad  mov     [rdx], r10d
0x18000a9b0  mov     eax, ecx
0x18000a9b2  shr     eax, 0Eh
0x18000a9b5  and     ax, r9w
0x18000a9b9  shl     ax, 2
0x18000a9bd  mov     [rdx+4], ax
0x18000a9c1  and     r8w, r11w; unsigned __int64
0x18000a9c5  mov     [rdx+6], r8w
0x18000a9ca  add     rdx, 8
0x18000a9ce  mov     eax, ecx
0x18000a9d0  shr     eax, 0Fh
0x18000a9d3  test    al, 7Fh
0x18000a9d5  jz      short loc_18000A9F9
0x18000a9d7  mov     [rdx], r10d
0x18000a9da  shr     ecx, 16h
0x18000a9dd  and     cx, r9w
0x18000a9e1  shl     cx, 2
0x18000a9e5  add     cx, r9w
0x18000a9e9  mov     [rdx+4], cx
0x18000a9ed  and     ax, 7Fh
0x18000a9f1  mov     [rdx+6], ax
0x18000a9f5  add     rdx, 8
0x18000a9f9  lea     rax, [rsp+68h+var_48]
0x18000a9fe  sub     rdx, rax
0x18000aa01  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000aa05  test    rdx, rdx
0x18000aa08  jle     short loc_18000AA15
0x18000aa0a  lea     rcx, [rsp+68h+var_48]; this
0x18000aa0f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000aa14  nop
0x18000aa15  mov     rcx, [rsp+68h+var_18]
0x18000aa1a  xor     rcx, rsp; StackCookie
0x18000aa1d  call    __security_check_cookie
0x18000aa22  add     rsp, 68h
0x18000aa26  retn
```
