# wil_details_RecordCachedUsage

- ea: `0x18000b350`
- end: `0x18000b497`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008744`

## callees

- `0x180003ab0`
- `0x18000a3b4`
- `0x18000b350`

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
0x18000b350  sub     rsp, 68h
0x18000b354  mov     rax, cs:__security_cookie
0x18000b35b  xor     rax, rsp
0x18000b35e  mov     [rsp+68h+var_18], rax
0x18000b363  mov     r9, rdx
0x18000b366  mov     r10d, ecx
0x18000b369  prefetchw byte ptr [rdx]
0x18000b36c  mov     eax, [rdx]
0x18000b36e  mov     r8d, eax
0x18000b371  and     r8d, 0FFC0401Eh
0x18000b378  lock cmpxchg [rdx], r8d
0x18000b37d  jnz     short loc_18000B36E
0x18000b37f  mov     ecx, eax
0x18000b381  mov     r8d, eax
0x18000b384  shr     r8d, 1
0x18000b387  and     r8d, 0Fh
0x18000b38b  jz      short loc_18000B3A8
0x18000b38d  prefetchw byte ptr [rdx+4]
0x18000b391  mov     eax, [rdx+4]
0x18000b394  mov     edx, eax
0x18000b396  or      edx, r8d
0x18000b399  lock cmpxchg [r9+4], edx
0x18000b39f  jnz     short loc_18000B394
0x18000b3a1  not     eax
0x18000b3a3  and     eax, r8d
0x18000b3a6  jmp     short loc_18000B3AB
0x18000b3a8  mov     eax, r8d
0x18000b3ab  mov     r8d, 2
0x18000b3b1  lea     r9d, [r8-1]
0x18000b3b5  test    r9b, al
0x18000b3b8  jz      short loc_18000B3CE
0x18000b3ba  mov     [rsp+68h+var_48], r10d
0x18000b3bf  mov     [rsp+68h+var_44], 10002h
0x18000b3c7  lea     rdx, [rsp+68h+var_40]
0x18000b3cc  jmp     short loc_18000B3D3
0x18000b3ce  lea     rdx, [rsp+68h+var_48]
0x18000b3d3  test    r8b, al
0x18000b3d6  jz      short loc_18000B3E6
0x18000b3d8  mov     [rdx], r10d
0x18000b3db  mov     dword ptr [rdx+4], 10006h
0x18000b3e2  add     rdx, 8
0x18000b3e6  test    al, 4
0x18000b3e8  jz      short loc_18000B3F8
0x18000b3ea  mov     [rdx], r10d
0x18000b3ed  mov     dword ptr [rdx+4], 10003h
0x18000b3f4  add     rdx, 8
0x18000b3f8  cmp     eax, 8
0x18000b3fb  jb      short loc_18000B40B
0x18000b3fd  mov     [rdx], r10d
0x18000b400  mov     dword ptr [rdx+4], 10007h
0x18000b407  add     rdx, 8
0x18000b40b  mov     r8d, ecx
0x18000b40e  shr     r8d, 5
0x18000b412  mov     r11d, 1FFh
0x18000b418  test    r11d, r8d
0x18000b41b  jz      short loc_18000B43E
0x18000b41d  mov     [rdx], r10d
0x18000b420  mov     eax, ecx
0x18000b422  shr     eax, 0Eh
0x18000b425  and     ax, r9w
0x18000b429  shl     ax, 2
0x18000b42d  mov     [rdx+4], ax
0x18000b431  and     r8w, r11w; unsigned __int64
0x18000b435  mov     [rdx+6], r8w
0x18000b43a  add     rdx, 8
0x18000b43e  mov     eax, ecx
0x18000b440  shr     eax, 0Fh
0x18000b443  test    al, 7Fh
0x18000b445  jz      short loc_18000B469
0x18000b447  mov     [rdx], r10d
0x18000b44a  shr     ecx, 16h
0x18000b44d  and     cx, r9w
0x18000b451  shl     cx, 2
0x18000b455  add     cx, r9w
0x18000b459  mov     [rdx+4], cx
0x18000b45d  and     ax, 7Fh
0x18000b461  mov     [rdx+6], ax
0x18000b465  add     rdx, 8
0x18000b469  lea     rax, [rsp+68h+var_48]
0x18000b46e  sub     rdx, rax
0x18000b471  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000b475  test    rdx, rdx
0x18000b478  jle     short loc_18000B485
0x18000b47a  lea     rcx, [rsp+68h+var_48]; this
0x18000b47f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000b484  nop
0x18000b485  mov     rcx, [rsp+68h+var_18]
0x18000b48a  xor     rcx, rsp; StackCookie
0x18000b48d  call    __security_check_cookie
0x18000b492  add     rsp, 68h
0x18000b496  retn
```
