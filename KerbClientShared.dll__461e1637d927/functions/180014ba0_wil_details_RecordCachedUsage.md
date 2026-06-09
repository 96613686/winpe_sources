# wil_details_RecordCachedUsage

- ea: `0x180014ba0`
- end: `0x180014ce6`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012a7c`

## callees

- `0x18000eb70`
- `0x180013f44`
- `0x180014ba0`

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
0x180014ba0  sub     rsp, 68h
0x180014ba4  mov     rax, cs:__security_cookie
0x180014bab  xor     rax, rsp
0x180014bae  mov     [rsp+68h+var_18], rax
0x180014bb3  mov     r9, rdx
0x180014bb6  mov     r10d, ecx
0x180014bb9  prefetchw byte ptr [rdx]
0x180014bbc  mov     eax, [rdx]
0x180014bbe  mov     r8d, eax
0x180014bc1  and     r8d, 0FFC0401Eh
0x180014bc8  lock cmpxchg [rdx], r8d
0x180014bcd  jnz     short loc_180014BBE
0x180014bcf  mov     r8d, eax
0x180014bd2  mov     ecx, eax
0x180014bd4  shr     r8d, 1
0x180014bd7  and     r8d, 0Fh
0x180014bdb  jz      short loc_180014BF8
0x180014bdd  prefetchw byte ptr [rdx+4]
0x180014be1  mov     eax, [rdx+4]
0x180014be4  mov     edx, eax
0x180014be6  or      edx, r8d
0x180014be9  lock cmpxchg [r9+4], edx
0x180014bef  jnz     short loc_180014BE4
0x180014bf1  not     eax
0x180014bf3  and     eax, r8d
0x180014bf6  jmp     short loc_180014BFB
0x180014bf8  mov     eax, r8d
0x180014bfb  mov     r8d, 2
0x180014c01  lea     r9d, [r8-1]
0x180014c05  test    r9b, al
0x180014c08  jz      short loc_180014C1E
0x180014c0a  mov     [rsp+68h+var_48], r10d
0x180014c0f  lea     rdx, [rsp+68h+var_40]
0x180014c14  mov     [rsp+68h+var_44], 10002h
0x180014c1c  jmp     short loc_180014C23
0x180014c1e  lea     rdx, [rsp+68h+var_48]
0x180014c23  test    r8b, al
0x180014c26  jz      short loc_180014C36
0x180014c28  mov     [rdx], r10d
0x180014c2b  mov     dword ptr [rdx+4], 10006h
0x180014c32  add     rdx, 8
0x180014c36  test    al, 4
0x180014c38  jz      short loc_180014C48
0x180014c3a  mov     [rdx], r10d
0x180014c3d  mov     dword ptr [rdx+4], 10003h
0x180014c44  add     rdx, 8
0x180014c48  cmp     eax, 8
0x180014c4b  jb      short loc_180014C5B
0x180014c4d  mov     [rdx], r10d
0x180014c50  mov     dword ptr [rdx+4], 10007h
0x180014c57  add     rdx, 8
0x180014c5b  mov     r8d, ecx
0x180014c5e  mov     r11d, 1FFh
0x180014c64  shr     r8d, 5
0x180014c68  test    r11d, r8d
0x180014c6b  jz      short loc_180014C8E
0x180014c6d  and     r8w, r11w; unsigned __int64
0x180014c71  mov     [rdx], r10d
0x180014c74  mov     eax, ecx
0x180014c76  mov     [rdx+6], r8w
0x180014c7b  shr     eax, 0Eh
0x180014c7e  and     ax, r9w
0x180014c82  shl     ax, 2
0x180014c86  mov     [rdx+4], ax
0x180014c8a  add     rdx, 8
0x180014c8e  mov     eax, ecx
0x180014c90  shr     eax, 0Fh
0x180014c93  test    al, 7Fh
0x180014c95  jz      short loc_180014CB9
0x180014c97  shr     ecx, 16h
0x180014c9a  and     ax, 7Fh
0x180014c9e  and     cx, r9w
0x180014ca2  mov     [rdx], r10d
0x180014ca5  shl     cx, 2
0x180014ca9  add     cx, r9w
0x180014cad  mov     [rdx+6], ax
0x180014cb1  mov     [rdx+4], cx
0x180014cb5  add     rdx, 8
0x180014cb9  lea     rax, [rsp+68h+var_48]
0x180014cbe  sub     rdx, rax
0x180014cc1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180014cc5  test    rdx, rdx
0x180014cc8  jle     short loc_180014CD4
0x180014cca  lea     rcx, [rsp+68h+var_48]; this
0x180014ccf  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180014cd4  mov     rcx, [rsp+68h+var_18]
0x180014cd9  xor     rcx, rsp; StackCookie
0x180014cdc  call    __security_check_cookie
0x180014ce1  add     rsp, 68h
0x180014ce5  retn
```
