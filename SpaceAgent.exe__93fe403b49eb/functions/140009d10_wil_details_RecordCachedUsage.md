# wil_details_RecordCachedUsage

- ea: `0x140009d10`
- end: `0x140009e56`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400070d8`

## callees

- `0x140009004`
- `0x140009d10`
- `0x14001edc0`

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
0x140009d10  sub     rsp, 68h
0x140009d14  mov     rax, cs:__security_cookie
0x140009d1b  xor     rax, rsp
0x140009d1e  mov     [rsp+68h+var_18], rax
0x140009d23  mov     r9, rdx
0x140009d26  mov     r10d, ecx
0x140009d29  prefetchw byte ptr [rdx]
0x140009d2c  mov     eax, [rdx]
0x140009d2e  mov     r8d, eax
0x140009d31  and     r8d, 0FFC0401Eh
0x140009d38  lock cmpxchg [rdx], r8d
0x140009d3d  jnz     short loc_140009D2E
0x140009d3f  mov     r8d, eax
0x140009d42  mov     ecx, eax
0x140009d44  shr     r8d, 1
0x140009d47  and     r8d, 0Fh
0x140009d4b  jz      short loc_140009D68
0x140009d4d  prefetchw byte ptr [rdx+4]
0x140009d51  mov     eax, [rdx+4]
0x140009d54  mov     edx, eax
0x140009d56  or      edx, r8d
0x140009d59  lock cmpxchg [r9+4], edx
0x140009d5f  jnz     short loc_140009D54
0x140009d61  not     eax
0x140009d63  and     eax, r8d
0x140009d66  jmp     short loc_140009D6B
0x140009d68  mov     eax, r8d
0x140009d6b  mov     r8d, 2
0x140009d71  lea     r9d, [r8-1]
0x140009d75  test    r9b, al
0x140009d78  jz      short loc_140009D8E
0x140009d7a  mov     [rsp+68h+var_48], r10d
0x140009d7f  lea     rdx, [rsp+68h+var_40]
0x140009d84  mov     [rsp+68h+var_44], 10002h
0x140009d8c  jmp     short loc_140009D93
0x140009d8e  lea     rdx, [rsp+68h+var_48]
0x140009d93  test    r8b, al
0x140009d96  jz      short loc_140009DA6
0x140009d98  mov     [rdx], r10d
0x140009d9b  mov     dword ptr [rdx+4], 10006h
0x140009da2  add     rdx, 8
0x140009da6  test    al, 4
0x140009da8  jz      short loc_140009DB8
0x140009daa  mov     [rdx], r10d
0x140009dad  mov     dword ptr [rdx+4], 10003h
0x140009db4  add     rdx, 8
0x140009db8  cmp     eax, 8
0x140009dbb  jb      short loc_140009DCB
0x140009dbd  mov     [rdx], r10d
0x140009dc0  mov     dword ptr [rdx+4], 10007h
0x140009dc7  add     rdx, 8
0x140009dcb  mov     r8d, ecx
0x140009dce  mov     r11d, 1FFh
0x140009dd4  shr     r8d, 5
0x140009dd8  test    r11d, r8d
0x140009ddb  jz      short loc_140009DFE
0x140009ddd  and     r8w, r11w; unsigned __int64
0x140009de1  mov     [rdx], r10d
0x140009de4  mov     eax, ecx
0x140009de6  mov     [rdx+6], r8w
0x140009deb  shr     eax, 0Eh
0x140009dee  and     ax, r9w
0x140009df2  shl     ax, 2
0x140009df6  mov     [rdx+4], ax
0x140009dfa  add     rdx, 8
0x140009dfe  mov     eax, ecx
0x140009e00  shr     eax, 0Fh
0x140009e03  test    al, 7Fh
0x140009e05  jz      short loc_140009E29
0x140009e07  shr     ecx, 16h
0x140009e0a  and     ax, 7Fh
0x140009e0e  and     cx, r9w
0x140009e12  mov     [rdx], r10d
0x140009e15  shl     cx, 2
0x140009e19  add     cx, r9w
0x140009e1d  mov     [rdx+6], ax
0x140009e21  mov     [rdx+4], cx
0x140009e25  add     rdx, 8
0x140009e29  lea     rax, [rsp+68h+var_48]
0x140009e2e  sub     rdx, rax
0x140009e31  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x140009e35  test    rdx, rdx
0x140009e38  jle     short loc_140009E44
0x140009e3a  lea     rcx, [rsp+68h+var_48]; this
0x140009e3f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x140009e44  mov     rcx, [rsp+68h+var_18]
0x140009e49  xor     rcx, rsp; StackCookie
0x140009e4c  call    __security_check_cookie
0x140009e51  add     rsp, 68h
0x140009e55  retn
```
