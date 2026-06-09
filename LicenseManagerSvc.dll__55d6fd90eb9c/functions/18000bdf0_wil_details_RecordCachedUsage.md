# wil_details_RecordCachedUsage

- ea: `0x18000bdf0`
- end: `0x18000bf37`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009bac`

## callees

- `0x1800033d0`
- `0x18000b100`
- `0x18000bdf0`

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
0x18000bdf0  sub     rsp, 68h
0x18000bdf4  mov     rax, cs:__security_cookie
0x18000bdfb  xor     rax, rsp
0x18000bdfe  mov     [rsp+68h+var_18], rax
0x18000be03  mov     r9, rdx
0x18000be06  mov     r10d, ecx
0x18000be09  prefetchw byte ptr [rdx]
0x18000be0c  mov     eax, [rdx]
0x18000be0e  mov     r8d, eax
0x18000be11  and     r8d, 0FFC0401Eh
0x18000be18  lock cmpxchg [rdx], r8d
0x18000be1d  jnz     short loc_18000BE0E
0x18000be1f  mov     ecx, eax
0x18000be21  mov     r8d, eax
0x18000be24  shr     r8d, 1
0x18000be27  and     r8d, 0Fh
0x18000be2b  jz      short loc_18000BE48
0x18000be2d  prefetchw byte ptr [rdx+4]
0x18000be31  mov     eax, [rdx+4]
0x18000be34  mov     edx, eax
0x18000be36  or      edx, r8d
0x18000be39  lock cmpxchg [r9+4], edx
0x18000be3f  jnz     short loc_18000BE34
0x18000be41  not     eax
0x18000be43  and     eax, r8d
0x18000be46  jmp     short loc_18000BE4B
0x18000be48  mov     eax, r8d
0x18000be4b  mov     r8d, 2
0x18000be51  lea     r9d, [r8-1]
0x18000be55  test    r9b, al
0x18000be58  jz      short loc_18000BE6E
0x18000be5a  mov     [rsp+68h+var_48], r10d
0x18000be5f  mov     [rsp+68h+var_44], 10002h
0x18000be67  lea     rdx, [rsp+68h+var_40]
0x18000be6c  jmp     short loc_18000BE73
0x18000be6e  lea     rdx, [rsp+68h+var_48]
0x18000be73  test    r8b, al
0x18000be76  jz      short loc_18000BE86
0x18000be78  mov     [rdx], r10d
0x18000be7b  mov     dword ptr [rdx+4], 10006h
0x18000be82  add     rdx, 8
0x18000be86  test    al, 4
0x18000be88  jz      short loc_18000BE98
0x18000be8a  mov     [rdx], r10d
0x18000be8d  mov     dword ptr [rdx+4], 10003h
0x18000be94  add     rdx, 8
0x18000be98  cmp     eax, 8
0x18000be9b  jb      short loc_18000BEAB
0x18000be9d  mov     [rdx], r10d
0x18000bea0  mov     dword ptr [rdx+4], 10007h
0x18000bea7  add     rdx, 8
0x18000beab  mov     r8d, ecx
0x18000beae  shr     r8d, 5
0x18000beb2  mov     r11d, 1FFh
0x18000beb8  test    r11d, r8d
0x18000bebb  jz      short loc_18000BEDE
0x18000bebd  mov     [rdx], r10d
0x18000bec0  mov     eax, ecx
0x18000bec2  shr     eax, 0Eh
0x18000bec5  and     ax, r9w
0x18000bec9  shl     ax, 2
0x18000becd  mov     [rdx+4], ax
0x18000bed1  and     r8w, r11w; unsigned __int64
0x18000bed5  mov     [rdx+6], r8w
0x18000beda  add     rdx, 8
0x18000bede  mov     eax, ecx
0x18000bee0  shr     eax, 0Fh
0x18000bee3  test    al, 7Fh
0x18000bee5  jz      short loc_18000BF09
0x18000bee7  mov     [rdx], r10d
0x18000beea  shr     ecx, 16h
0x18000beed  and     cx, r9w
0x18000bef1  shl     cx, 2
0x18000bef5  add     cx, r9w
0x18000bef9  mov     [rdx+4], cx
0x18000befd  and     ax, 7Fh
0x18000bf01  mov     [rdx+6], ax
0x18000bf05  add     rdx, 8
0x18000bf09  lea     rax, [rsp+68h+var_48]
0x18000bf0e  sub     rdx, rax
0x18000bf11  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000bf15  test    rdx, rdx
0x18000bf18  jle     short loc_18000BF25
0x18000bf1a  lea     rcx, [rsp+68h+var_48]; this
0x18000bf1f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000bf24  nop
0x18000bf25  mov     rcx, [rsp+68h+var_18]
0x18000bf2a  xor     rcx, rsp; StackCookie
0x18000bf2d  call    __security_check_cookie
0x18000bf32  add     rsp, 68h
0x18000bf36  retn
```
