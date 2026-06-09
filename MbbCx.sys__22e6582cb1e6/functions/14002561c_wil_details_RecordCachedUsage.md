# wil_details_RecordCachedUsage

- ea: `0x14002561c`
- end: `0x140025763`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140065730`

## callees

- `0x14002561c`
- `0x140047e50`
- `0x1400657b0`

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
0x14002561c  sub     rsp, 68h
0x140025620  mov     rax, cs:__security_cookie
0x140025627  xor     rax, rsp
0x14002562a  mov     [rsp+68h+var_18], rax
0x14002562f  mov     r9, rdx
0x140025632  mov     r10d, ecx
0x140025635  prefetchw byte ptr [rdx]
0x140025638  mov     eax, [rdx]
0x14002563a  mov     r8d, eax
0x14002563d  and     r8d, 0FFC0401Eh
0x140025644  lock cmpxchg [rdx], r8d
0x140025649  jnz     short loc_14002563A
0x14002564b  mov     r8d, eax
0x14002564e  mov     ecx, eax
0x140025650  shr     r8d, 1
0x140025653  and     r8d, 0Fh
0x140025657  jz      short loc_140025674
0x140025659  prefetchw byte ptr [rdx+4]
0x14002565d  mov     eax, [rdx+4]
0x140025660  mov     edx, eax
0x140025662  or      edx, r8d
0x140025665  lock cmpxchg [r9+4], edx
0x14002566b  jnz     short loc_140025660
0x14002566d  not     eax
0x14002566f  and     eax, r8d
0x140025672  jmp     short loc_140025677
0x140025674  mov     eax, r8d
0x140025677  mov     r8d, 2
0x14002567d  lea     r9d, [r8-1]
0x140025681  test    r9b, al
0x140025684  jz      short loc_14002569A
0x140025686  mov     [rsp+68h+var_48], r10d
0x14002568b  lea     rdx, [rsp+68h+var_40]
0x140025690  mov     [rsp+68h+var_44], 10002h
0x140025698  jmp     short loc_14002569F
0x14002569a  lea     rdx, [rsp+68h+var_48]
0x14002569f  test    r8b, al
0x1400256a2  jz      short loc_1400256B2
0x1400256a4  mov     [rdx], r10d
0x1400256a7  mov     dword ptr [rdx+4], 10006h
0x1400256ae  add     rdx, 8
0x1400256b2  test    al, 4
0x1400256b4  jz      short loc_1400256C4
0x1400256b6  mov     [rdx], r10d
0x1400256b9  mov     dword ptr [rdx+4], 10003h
0x1400256c0  add     rdx, 8
0x1400256c4  cmp     eax, 8
0x1400256c7  jb      short loc_1400256D7
0x1400256c9  mov     [rdx], r10d
0x1400256cc  mov     dword ptr [rdx+4], 10007h
0x1400256d3  add     rdx, 8
0x1400256d7  mov     r8d, ecx
0x1400256da  mov     r11d, 1FFh
0x1400256e0  shr     r8d, 5
0x1400256e4  test    r11d, r8d
0x1400256e7  jz      short loc_14002570A
0x1400256e9  and     r8w, r11w
0x1400256ed  mov     [rdx], r10d
0x1400256f0  mov     eax, ecx
0x1400256f2  mov     [rdx+6], r8w
0x1400256f7  shr     eax, 0Eh
0x1400256fa  and     ax, r9w
0x1400256fe  shl     ax, 2
0x140025702  mov     [rdx+4], ax
0x140025706  add     rdx, 8
0x14002570a  mov     eax, ecx
0x14002570c  shr     eax, 0Fh
0x14002570f  test    al, 7Fh
0x140025711  jz      short loc_140025735
0x140025713  shr     ecx, 16h
0x140025716  and     ax, 7Fh
0x14002571a  and     cx, r9w
0x14002571e  mov     [rdx], r10d
0x140025721  shl     cx, 2
0x140025725  add     cx, r9w
0x140025729  mov     [rdx+6], ax
0x14002572d  mov     [rdx+4], cx
0x140025731  add     rdx, 8
0x140025735  lea     rax, [rsp+68h+var_48]
0x14002573a  sub     rdx, rax
0x14002573d  sar     rdx, 3
0x140025741  test    rdx, rdx
0x140025744  jle     short loc_140025750
0x140025746  lea     rcx, [rsp+68h+var_48]
0x14002574b  call    wil_details_RecordFeatureUsageCallback
0x140025750  mov     rcx, [rsp+68h+var_18]
0x140025755  xor     rcx, rsp; StackCookie
0x140025758  call    __security_check_cookie
0x14002575d  add     rsp, 68h
0x140025761  retn
```
