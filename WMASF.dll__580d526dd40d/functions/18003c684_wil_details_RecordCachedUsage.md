# wil_details_RecordCachedUsage

- ea: `0x18003c684`
- end: `0x18003c7ca`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800397e8`

## callees

- `0x1800015d0`
- `0x18003bc9c`
- `0x18003c684`

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
0x18003c684  sub     rsp, 68h
0x18003c688  mov     rax, cs:__security_cookie
0x18003c68f  xor     rax, rsp
0x18003c692  mov     [rsp+68h+var_18], rax
0x18003c697  mov     r9, rdx
0x18003c69a  mov     r10d, ecx
0x18003c69d  prefetchw byte ptr [rdx]
0x18003c6a0  mov     eax, [rdx]
0x18003c6a2  mov     r8d, eax
0x18003c6a5  and     r8d, 0FFC0401Eh
0x18003c6ac  lock cmpxchg [rdx], r8d
0x18003c6b1  jnz     short loc_18003C6A2
0x18003c6b3  mov     r8d, eax
0x18003c6b6  mov     ecx, eax
0x18003c6b8  shr     r8d, 1
0x18003c6bb  and     r8d, 0Fh
0x18003c6bf  jz      short loc_18003C6DC
0x18003c6c1  prefetchw byte ptr [rdx+4]
0x18003c6c5  mov     eax, [rdx+4]
0x18003c6c8  mov     edx, eax
0x18003c6ca  or      edx, r8d
0x18003c6cd  lock cmpxchg [r9+4], edx
0x18003c6d3  jnz     short loc_18003C6C8
0x18003c6d5  not     eax
0x18003c6d7  and     eax, r8d
0x18003c6da  jmp     short loc_18003C6DF
0x18003c6dc  mov     eax, r8d
0x18003c6df  mov     r8d, 2
0x18003c6e5  lea     r9d, [r8-1]
0x18003c6e9  test    r9b, al
0x18003c6ec  jz      short loc_18003C702
0x18003c6ee  mov     [rsp+68h+var_48], r10d
0x18003c6f3  lea     rdx, [rsp+68h+var_40]
0x18003c6f8  mov     [rsp+68h+var_44], 10002h
0x18003c700  jmp     short loc_18003C707
0x18003c702  lea     rdx, [rsp+68h+var_48]
0x18003c707  test    r8b, al
0x18003c70a  jz      short loc_18003C71A
0x18003c70c  mov     [rdx], r10d
0x18003c70f  mov     dword ptr [rdx+4], 10006h
0x18003c716  add     rdx, 8
0x18003c71a  test    al, 4
0x18003c71c  jz      short loc_18003C72C
0x18003c71e  mov     [rdx], r10d
0x18003c721  mov     dword ptr [rdx+4], 10003h
0x18003c728  add     rdx, 8
0x18003c72c  cmp     eax, 8
0x18003c72f  jb      short loc_18003C73F
0x18003c731  mov     [rdx], r10d
0x18003c734  mov     dword ptr [rdx+4], 10007h
0x18003c73b  add     rdx, 8
0x18003c73f  mov     r8d, ecx
0x18003c742  mov     r11d, 1FFh
0x18003c748  shr     r8d, 5
0x18003c74c  test    r11d, r8d
0x18003c74f  jz      short loc_18003C772
0x18003c751  and     r8w, r11w; unsigned __int64
0x18003c755  mov     [rdx], r10d
0x18003c758  mov     eax, ecx
0x18003c75a  mov     [rdx+6], r8w
0x18003c75f  shr     eax, 0Eh
0x18003c762  and     ax, r9w
0x18003c766  shl     ax, 2
0x18003c76a  mov     [rdx+4], ax
0x18003c76e  add     rdx, 8
0x18003c772  mov     eax, ecx
0x18003c774  shr     eax, 0Fh
0x18003c777  test    al, 7Fh
0x18003c779  jz      short loc_18003C79D
0x18003c77b  shr     ecx, 16h
0x18003c77e  and     ax, 7Fh
0x18003c782  and     cx, r9w
0x18003c786  mov     [rdx], r10d
0x18003c789  shl     cx, 2
0x18003c78d  add     cx, r9w
0x18003c791  mov     [rdx+6], ax
0x18003c795  mov     [rdx+4], cx
0x18003c799  add     rdx, 8
0x18003c79d  lea     rax, [rsp+68h+var_48]
0x18003c7a2  sub     rdx, rax
0x18003c7a5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18003c7a9  test    rdx, rdx
0x18003c7ac  jle     short loc_18003C7B8
0x18003c7ae  lea     rcx, [rsp+68h+var_48]; this
0x18003c7b3  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18003c7b8  mov     rcx, [rsp+68h+var_18]
0x18003c7bd  xor     rcx, rsp; StackCookie
0x18003c7c0  call    __security_check_cookie
0x18003c7c5  add     rsp, 68h
0x18003c7c9  retn
```
