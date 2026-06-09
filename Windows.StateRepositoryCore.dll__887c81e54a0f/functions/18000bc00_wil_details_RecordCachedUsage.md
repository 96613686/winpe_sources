# wil_details_RecordCachedUsage

- ea: `0x18000bc00`
- end: `0x18000bd47`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000802c`

## callees

- `0x180001ed0`
- `0x18000a5a0`
- `0x18000bc00`

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
0x18000bc00  sub     rsp, 68h
0x18000bc04  mov     rax, cs:__security_cookie
0x18000bc0b  xor     rax, rsp
0x18000bc0e  mov     [rsp+68h+var_18], rax
0x18000bc13  mov     r9, rdx
0x18000bc16  mov     r10d, ecx
0x18000bc19  prefetchw byte ptr [rdx]
0x18000bc1c  mov     eax, [rdx]
0x18000bc1e  mov     r8d, eax
0x18000bc21  and     r8d, 0FFC0401Eh
0x18000bc28  lock cmpxchg [rdx], r8d
0x18000bc2d  jnz     short loc_18000BC1E
0x18000bc2f  mov     ecx, eax
0x18000bc31  mov     r8d, eax
0x18000bc34  shr     r8d, 1
0x18000bc37  and     r8d, 0Fh
0x18000bc3b  jz      short loc_18000BC58
0x18000bc3d  prefetchw byte ptr [rdx+4]
0x18000bc41  mov     eax, [rdx+4]
0x18000bc44  mov     edx, eax
0x18000bc46  or      edx, r8d
0x18000bc49  lock cmpxchg [r9+4], edx
0x18000bc4f  jnz     short loc_18000BC44
0x18000bc51  not     eax
0x18000bc53  and     eax, r8d
0x18000bc56  jmp     short loc_18000BC5B
0x18000bc58  mov     eax, r8d
0x18000bc5b  mov     r8d, 2
0x18000bc61  lea     r9d, [r8-1]
0x18000bc65  test    r9b, al
0x18000bc68  jz      short loc_18000BC7E
0x18000bc6a  mov     [rsp+68h+var_48], r10d
0x18000bc6f  mov     [rsp+68h+var_44], 10002h
0x18000bc77  lea     rdx, [rsp+68h+var_40]
0x18000bc7c  jmp     short loc_18000BC83
0x18000bc7e  lea     rdx, [rsp+68h+var_48]
0x18000bc83  test    r8b, al
0x18000bc86  jz      short loc_18000BC96
0x18000bc88  mov     [rdx], r10d
0x18000bc8b  mov     dword ptr [rdx+4], 10006h
0x18000bc92  add     rdx, 8
0x18000bc96  test    al, 4
0x18000bc98  jz      short loc_18000BCA8
0x18000bc9a  mov     [rdx], r10d
0x18000bc9d  mov     dword ptr [rdx+4], 10003h
0x18000bca4  add     rdx, 8
0x18000bca8  cmp     eax, 8
0x18000bcab  jb      short loc_18000BCBB
0x18000bcad  mov     [rdx], r10d
0x18000bcb0  mov     dword ptr [rdx+4], 10007h
0x18000bcb7  add     rdx, 8
0x18000bcbb  mov     r8d, ecx
0x18000bcbe  shr     r8d, 5
0x18000bcc2  mov     r11d, 1FFh
0x18000bcc8  test    r11d, r8d
0x18000bccb  jz      short loc_18000BCEE
0x18000bccd  mov     [rdx], r10d
0x18000bcd0  mov     eax, ecx
0x18000bcd2  shr     eax, 0Eh
0x18000bcd5  and     ax, r9w
0x18000bcd9  shl     ax, 2
0x18000bcdd  mov     [rdx+4], ax
0x18000bce1  and     r8w, r11w; unsigned __int64
0x18000bce5  mov     [rdx+6], r8w
0x18000bcea  add     rdx, 8
0x18000bcee  mov     eax, ecx
0x18000bcf0  shr     eax, 0Fh
0x18000bcf3  test    al, 7Fh
0x18000bcf5  jz      short loc_18000BD19
0x18000bcf7  mov     [rdx], r10d
0x18000bcfa  shr     ecx, 16h
0x18000bcfd  and     cx, r9w
0x18000bd01  shl     cx, 2
0x18000bd05  add     cx, r9w
0x18000bd09  mov     [rdx+4], cx
0x18000bd0d  and     ax, 7Fh
0x18000bd11  mov     [rdx+6], ax
0x18000bd15  add     rdx, 8
0x18000bd19  lea     rax, [rsp+68h+var_48]
0x18000bd1e  sub     rdx, rax
0x18000bd21  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000bd25  test    rdx, rdx
0x18000bd28  jle     short loc_18000BD35
0x18000bd2a  lea     rcx, [rsp+68h+var_48]; this
0x18000bd2f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000bd34  nop
0x18000bd35  mov     rcx, [rsp+68h+var_18]
0x18000bd3a  xor     rcx, rsp; StackCookie
0x18000bd3d  call    __security_check_cookie
0x18000bd42  add     rsp, 68h
0x18000bd46  retn
```
