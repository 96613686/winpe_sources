# wil_details_RecordCachedUsage

- ea: `0x140013a90`
- end: `0x140013bd7`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000f394`

## callees

- `0x1400114a8`
- `0x140013a90`
- `0x14001a8d0`

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
0x140013a90  sub     rsp, 68h
0x140013a94  mov     rax, cs:__security_cookie
0x140013a9b  xor     rax, rsp
0x140013a9e  mov     [rsp+68h+var_18], rax
0x140013aa3  mov     r9, rdx
0x140013aa6  mov     r10d, ecx
0x140013aa9  prefetchw byte ptr [rdx]
0x140013aac  mov     eax, [rdx]
0x140013aae  mov     r8d, eax
0x140013ab1  and     r8d, 0FFC0401Eh
0x140013ab8  lock cmpxchg [rdx], r8d
0x140013abd  jnz     short loc_140013AAE
0x140013abf  mov     ecx, eax
0x140013ac1  mov     r8d, eax
0x140013ac4  shr     r8d, 1
0x140013ac7  and     r8d, 0Fh
0x140013acb  jz      short loc_140013AE8
0x140013acd  prefetchw byte ptr [rdx+4]
0x140013ad1  mov     eax, [rdx+4]
0x140013ad4  mov     edx, eax
0x140013ad6  or      edx, r8d
0x140013ad9  lock cmpxchg [r9+4], edx
0x140013adf  jnz     short loc_140013AD4
0x140013ae1  not     eax
0x140013ae3  and     eax, r8d
0x140013ae6  jmp     short loc_140013AEB
0x140013ae8  mov     eax, r8d
0x140013aeb  mov     r8d, 2
0x140013af1  lea     r9d, [r8-1]
0x140013af5  test    r9b, al
0x140013af8  jz      short loc_140013B0E
0x140013afa  mov     [rsp+68h+var_48], r10d
0x140013aff  mov     [rsp+68h+var_44], 10002h
0x140013b07  lea     rdx, [rsp+68h+var_40]
0x140013b0c  jmp     short loc_140013B13
0x140013b0e  lea     rdx, [rsp+68h+var_48]
0x140013b13  test    r8b, al
0x140013b16  jz      short loc_140013B26
0x140013b18  mov     [rdx], r10d
0x140013b1b  mov     dword ptr [rdx+4], 10006h
0x140013b22  add     rdx, 8
0x140013b26  test    al, 4
0x140013b28  jz      short loc_140013B38
0x140013b2a  mov     [rdx], r10d
0x140013b2d  mov     dword ptr [rdx+4], 10003h
0x140013b34  add     rdx, 8
0x140013b38  cmp     eax, 8
0x140013b3b  jb      short loc_140013B4B
0x140013b3d  mov     [rdx], r10d
0x140013b40  mov     dword ptr [rdx+4], 10007h
0x140013b47  add     rdx, 8
0x140013b4b  mov     r8d, ecx
0x140013b4e  shr     r8d, 5
0x140013b52  mov     r11d, 1FFh
0x140013b58  test    r11d, r8d
0x140013b5b  jz      short loc_140013B7E
0x140013b5d  mov     [rdx], r10d
0x140013b60  mov     eax, ecx
0x140013b62  shr     eax, 0Eh
0x140013b65  and     ax, r9w
0x140013b69  shl     ax, 2
0x140013b6d  mov     [rdx+4], ax
0x140013b71  and     r8w, r11w; unsigned __int64
0x140013b75  mov     [rdx+6], r8w
0x140013b7a  add     rdx, 8
0x140013b7e  mov     eax, ecx
0x140013b80  shr     eax, 0Fh
0x140013b83  test    al, 7Fh
0x140013b85  jz      short loc_140013BA9
0x140013b87  mov     [rdx], r10d
0x140013b8a  shr     ecx, 16h
0x140013b8d  and     cx, r9w
0x140013b91  shl     cx, 2
0x140013b95  add     cx, r9w
0x140013b99  mov     [rdx+4], cx
0x140013b9d  and     ax, 7Fh
0x140013ba1  mov     [rdx+6], ax
0x140013ba5  add     rdx, 8
0x140013ba9  lea     rax, [rsp+68h+var_48]
0x140013bae  sub     rdx, rax
0x140013bb1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x140013bb5  test    rdx, rdx
0x140013bb8  jle     short loc_140013BC5
0x140013bba  lea     rcx, [rsp+68h+var_48]; this
0x140013bbf  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x140013bc4  nop
0x140013bc5  mov     rcx, [rsp+68h+var_18]
0x140013bca  xor     rcx, rsp; StackCookie
0x140013bcd  call    __security_check_cookie
0x140013bd2  add     rsp, 68h
0x140013bd6  retn
```
