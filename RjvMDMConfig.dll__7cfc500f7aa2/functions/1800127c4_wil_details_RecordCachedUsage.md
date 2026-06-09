# wil_details_RecordCachedUsage

- ea: `0x1800127c4`
- end: `0x18001290b`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bdf8`

## callees

- `0x180001c60`
- `0x1800110f0`
- `0x1800127c4`

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
0x1800127c4  sub     rsp, 68h
0x1800127c8  mov     rax, cs:__security_cookie
0x1800127cf  xor     rax, rsp
0x1800127d2  mov     [rsp+68h+var_18], rax
0x1800127d7  mov     r9, rdx
0x1800127da  mov     r10d, ecx
0x1800127dd  prefetchw byte ptr [rdx]
0x1800127e0  mov     eax, [rdx]
0x1800127e2  mov     r8d, eax
0x1800127e5  and     r8d, 0FFC0401Eh
0x1800127ec  lock cmpxchg [rdx], r8d
0x1800127f1  jnz     short loc_1800127E2
0x1800127f3  mov     r8d, eax
0x1800127f6  mov     ecx, eax
0x1800127f8  shr     r8d, 1
0x1800127fb  and     r8d, 0Fh
0x1800127ff  jz      short loc_18001281C
0x180012801  prefetchw byte ptr [rdx+4]
0x180012805  mov     eax, [rdx+4]
0x180012808  mov     edx, eax
0x18001280a  or      edx, r8d
0x18001280d  lock cmpxchg [r9+4], edx
0x180012813  jnz     short loc_180012808
0x180012815  not     eax
0x180012817  and     eax, r8d
0x18001281a  jmp     short loc_18001281F
0x18001281c  mov     eax, r8d
0x18001281f  mov     r8d, 2
0x180012825  lea     r9d, [r8-1]
0x180012829  test    r9b, al
0x18001282c  jz      short loc_180012842
0x18001282e  mov     [rsp+68h+var_48], r10d
0x180012833  lea     rdx, [rsp+68h+var_40]
0x180012838  mov     [rsp+68h+var_44], 10002h
0x180012840  jmp     short loc_180012847
0x180012842  lea     rdx, [rsp+68h+var_48]
0x180012847  test    r8b, al
0x18001284a  jz      short loc_18001285A
0x18001284c  mov     [rdx], r10d
0x18001284f  mov     dword ptr [rdx+4], 10006h
0x180012856  add     rdx, 8
0x18001285a  test    al, 4
0x18001285c  jz      short loc_18001286C
0x18001285e  mov     [rdx], r10d
0x180012861  mov     dword ptr [rdx+4], 10003h
0x180012868  add     rdx, 8
0x18001286c  cmp     eax, 8
0x18001286f  jb      short loc_18001287F
0x180012871  mov     [rdx], r10d
0x180012874  mov     dword ptr [rdx+4], 10007h
0x18001287b  add     rdx, 8
0x18001287f  mov     r8d, ecx
0x180012882  mov     r11d, 1FFh
0x180012888  shr     r8d, 5
0x18001288c  test    r11d, r8d
0x18001288f  jz      short loc_1800128B2
0x180012891  and     r8w, r11w; unsigned __int64
0x180012895  mov     [rdx], r10d
0x180012898  mov     eax, ecx
0x18001289a  mov     [rdx+6], r8w
0x18001289f  shr     eax, 0Eh
0x1800128a2  and     ax, r9w
0x1800128a6  shl     ax, 2
0x1800128aa  mov     [rdx+4], ax
0x1800128ae  add     rdx, 8
0x1800128b2  mov     eax, ecx
0x1800128b4  shr     eax, 0Fh
0x1800128b7  test    al, 7Fh
0x1800128b9  jz      short loc_1800128DD
0x1800128bb  shr     ecx, 16h
0x1800128be  and     ax, 7Fh
0x1800128c2  and     cx, r9w
0x1800128c6  mov     [rdx], r10d
0x1800128c9  shl     cx, 2
0x1800128cd  add     cx, r9w
0x1800128d1  mov     [rdx+6], ax
0x1800128d5  mov     [rdx+4], cx
0x1800128d9  add     rdx, 8
0x1800128dd  lea     rax, [rsp+68h+var_48]
0x1800128e2  sub     rdx, rax
0x1800128e5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800128e9  test    rdx, rdx
0x1800128ec  jle     short loc_1800128F8
0x1800128ee  lea     rcx, [rsp+68h+var_48]; this
0x1800128f3  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1800128f8  mov     rcx, [rsp+68h+var_18]
0x1800128fd  xor     rcx, rsp; StackCookie
0x180012900  call    __security_check_cookie
0x180012905  add     rsp, 68h
0x180012909  retn
```
