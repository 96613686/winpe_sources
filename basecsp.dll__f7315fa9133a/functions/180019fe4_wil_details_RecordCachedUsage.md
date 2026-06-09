# wil_details_RecordCachedUsage

- ea: `0x180019fe4`
- end: `0x18001a12b`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001517c`

## callees

- `0x1800179e8`
- `0x180019fe4`
- `0x18002cfa0`

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
0x180019fe4  sub     rsp, 68h
0x180019fe8  mov     rax, cs:__security_cookie
0x180019fef  xor     rax, rsp
0x180019ff2  mov     [rsp+68h+var_18], rax
0x180019ff7  mov     r9, rdx
0x180019ffa  mov     r10d, ecx
0x180019ffd  prefetchw byte ptr [rdx]
0x18001a000  mov     eax, [rdx]
0x18001a002  mov     r8d, eax
0x18001a005  and     r8d, 0FFC0401Eh
0x18001a00c  lock cmpxchg [rdx], r8d
0x18001a011  jnz     short loc_18001A002
0x18001a013  mov     ecx, eax
0x18001a015  mov     r8d, eax
0x18001a018  shr     r8d, 1
0x18001a01b  and     r8d, 0Fh
0x18001a01f  jz      short loc_18001A03C
0x18001a021  prefetchw byte ptr [rdx+4]
0x18001a025  mov     eax, [rdx+4]
0x18001a028  mov     edx, eax
0x18001a02a  or      edx, r8d
0x18001a02d  lock cmpxchg [r9+4], edx
0x18001a033  jnz     short loc_18001A028
0x18001a035  not     eax
0x18001a037  and     eax, r8d
0x18001a03a  jmp     short loc_18001A03F
0x18001a03c  mov     eax, r8d
0x18001a03f  mov     r8d, 2
0x18001a045  lea     r9d, [r8-1]
0x18001a049  test    r9b, al
0x18001a04c  jz      short loc_18001A062
0x18001a04e  mov     [rsp+68h+var_48], r10d
0x18001a053  mov     [rsp+68h+var_44], 10002h
0x18001a05b  lea     rdx, [rsp+68h+var_40]
0x18001a060  jmp     short loc_18001A067
0x18001a062  lea     rdx, [rsp+68h+var_48]
0x18001a067  test    r8b, al
0x18001a06a  jz      short loc_18001A07A
0x18001a06c  mov     [rdx], r10d
0x18001a06f  mov     dword ptr [rdx+4], 10006h
0x18001a076  add     rdx, 8
0x18001a07a  test    al, 4
0x18001a07c  jz      short loc_18001A08C
0x18001a07e  mov     [rdx], r10d
0x18001a081  mov     dword ptr [rdx+4], 10003h
0x18001a088  add     rdx, 8
0x18001a08c  cmp     eax, 8
0x18001a08f  jb      short loc_18001A09F
0x18001a091  mov     [rdx], r10d
0x18001a094  mov     dword ptr [rdx+4], 10007h
0x18001a09b  add     rdx, 8
0x18001a09f  mov     r8d, ecx
0x18001a0a2  shr     r8d, 5
0x18001a0a6  mov     r11d, 1FFh
0x18001a0ac  test    r11d, r8d
0x18001a0af  jz      short loc_18001A0D2
0x18001a0b1  mov     [rdx], r10d
0x18001a0b4  mov     eax, ecx
0x18001a0b6  shr     eax, 0Eh
0x18001a0b9  and     ax, r9w
0x18001a0bd  shl     ax, 2
0x18001a0c1  mov     [rdx+4], ax
0x18001a0c5  and     r8w, r11w; unsigned __int64
0x18001a0c9  mov     [rdx+6], r8w
0x18001a0ce  add     rdx, 8
0x18001a0d2  mov     eax, ecx
0x18001a0d4  shr     eax, 0Fh
0x18001a0d7  test    al, 7Fh
0x18001a0d9  jz      short loc_18001A0FD
0x18001a0db  mov     [rdx], r10d
0x18001a0de  shr     ecx, 16h
0x18001a0e1  and     cx, r9w
0x18001a0e5  shl     cx, 2
0x18001a0e9  add     cx, r9w
0x18001a0ed  mov     [rdx+4], cx
0x18001a0f1  and     ax, 7Fh
0x18001a0f5  mov     [rdx+6], ax
0x18001a0f9  add     rdx, 8
0x18001a0fd  lea     rax, [rsp+68h+var_48]
0x18001a102  sub     rdx, rax
0x18001a105  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18001a109  test    rdx, rdx
0x18001a10c  jle     short loc_18001A119
0x18001a10e  lea     rcx, [rsp+68h+var_48]; this
0x18001a113  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18001a118  nop
0x18001a119  mov     rcx, [rsp+68h+var_18]
0x18001a11e  xor     rcx, rsp; StackCookie
0x18001a121  call    __security_check_cookie
0x18001a126  add     rsp, 68h
0x18001a12a  retn
```
