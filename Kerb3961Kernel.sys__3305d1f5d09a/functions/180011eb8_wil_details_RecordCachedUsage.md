# wil_details_RecordCachedUsage

- ea: `0x180011eb8`
- end: `0x180011fff`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d300`

## callees

- `0x180011eb8`
- `0x180012200`
- `0x18001d380`

## pseudocode

```c
_DWORD *__fastcall wil_details_RecordCachedUsage(int a1, __int64 a2)
{
  unsigned __int32 v3; // ecx
  int v4; // r8d
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned int v7; // eax
  char *v8; // rdx
  _DWORD *result; // rax
  _DWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+28h] [rbp-40h] BYREF

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
    v10[0] = a1;
    v8 = &v11;
    v10[1] = 65538;
  }
  else
  {
    v8 = (char *)v10;
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
  if ( ((v3 >> 5) & 0x1FF) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = (v3 >> 5) & 0x1FF;
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
  result = v10;
  if ( (v8 - (char *)v10) >> 3 > 0 )
    return (_DWORD *)wil_details_RecordFeatureUsageCallback(v10);
  return result;
}

```

## disassembly

```asm
0x180011eb8  sub     rsp, 68h
0x180011ebc  mov     rax, cs:__security_cookie
0x180011ec3  xor     rax, rsp
0x180011ec6  mov     [rsp+68h+var_18], rax
0x180011ecb  mov     r9, rdx
0x180011ece  mov     r10d, ecx
0x180011ed1  prefetchw byte ptr [rdx]
0x180011ed4  mov     eax, [rdx]
0x180011ed6  mov     r8d, eax
0x180011ed9  and     r8d, 0FFC0401Eh
0x180011ee0  lock cmpxchg [rdx], r8d
0x180011ee5  jnz     short loc_180011ED6
0x180011ee7  mov     r8d, eax
0x180011eea  mov     ecx, eax
0x180011eec  shr     r8d, 1
0x180011eef  and     r8d, 0Fh
0x180011ef3  jz      short loc_180011F10
0x180011ef5  prefetchw byte ptr [rdx+4]
0x180011ef9  mov     eax, [rdx+4]
0x180011efc  mov     edx, eax
0x180011efe  or      edx, r8d
0x180011f01  lock cmpxchg [r9+4], edx
0x180011f07  jnz     short loc_180011EFC
0x180011f09  not     eax
0x180011f0b  and     eax, r8d
0x180011f0e  jmp     short loc_180011F13
0x180011f10  mov     eax, r8d
0x180011f13  mov     r8d, 2
0x180011f19  lea     r9d, [r8-1]
0x180011f1d  test    r9b, al
0x180011f20  jz      short loc_180011F36
0x180011f22  mov     [rsp+68h+var_48], r10d
0x180011f27  lea     rdx, [rsp+68h+var_40]
0x180011f2c  mov     [rsp+68h+var_44], 10002h
0x180011f34  jmp     short loc_180011F3B
0x180011f36  lea     rdx, [rsp+68h+var_48]
0x180011f3b  test    r8b, al
0x180011f3e  jz      short loc_180011F4E
0x180011f40  mov     [rdx], r10d
0x180011f43  mov     dword ptr [rdx+4], 10006h
0x180011f4a  add     rdx, 8
0x180011f4e  test    al, 4
0x180011f50  jz      short loc_180011F60
0x180011f52  mov     [rdx], r10d
0x180011f55  mov     dword ptr [rdx+4], 10003h
0x180011f5c  add     rdx, 8
0x180011f60  cmp     eax, 8
0x180011f63  jb      short loc_180011F73
0x180011f65  mov     [rdx], r10d
0x180011f68  mov     dword ptr [rdx+4], 10007h
0x180011f6f  add     rdx, 8
0x180011f73  mov     r8d, ecx
0x180011f76  mov     r11d, 1FFh
0x180011f7c  shr     r8d, 5
0x180011f80  test    r11d, r8d
0x180011f83  jz      short loc_180011FA6
0x180011f85  and     r8w, r11w
0x180011f89  mov     [rdx], r10d
0x180011f8c  mov     eax, ecx
0x180011f8e  mov     [rdx+6], r8w
0x180011f93  shr     eax, 0Eh
0x180011f96  and     ax, r9w
0x180011f9a  shl     ax, 2
0x180011f9e  mov     [rdx+4], ax
0x180011fa2  add     rdx, 8
0x180011fa6  mov     eax, ecx
0x180011fa8  shr     eax, 0Fh
0x180011fab  test    al, 7Fh
0x180011fad  jz      short loc_180011FD1
0x180011faf  shr     ecx, 16h
0x180011fb2  and     ax, 7Fh
0x180011fb6  and     cx, r9w
0x180011fba  mov     [rdx], r10d
0x180011fbd  shl     cx, 2
0x180011fc1  add     cx, r9w
0x180011fc5  mov     [rdx+6], ax
0x180011fc9  mov     [rdx+4], cx
0x180011fcd  add     rdx, 8
0x180011fd1  lea     rax, [rsp+68h+var_48]
0x180011fd6  sub     rdx, rax
0x180011fd9  sar     rdx, 3
0x180011fdd  test    rdx, rdx
0x180011fe0  jle     short loc_180011FEC
0x180011fe2  lea     rcx, [rsp+68h+var_48]
0x180011fe7  call    wil_details_RecordFeatureUsageCallback
0x180011fec  mov     rcx, [rsp+68h+var_18]
0x180011ff1  xor     rcx, rsp; StackCookie
0x180011ff4  call    __security_check_cookie
0x180011ff9  add     rsp, 68h
0x180011ffd  retn
```
