# wil_details_RecordCachedUsage

- ea: `0x1800097cc`
- end: `0x180009913`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `void __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010dd4`

## callees

- `0x1800097cc`
- `0x180011ef4`
- `0x18001a380`

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
0x1800097cc  sub     rsp, 68h
0x1800097d0  mov     rax, cs:__security_cookie
0x1800097d7  xor     rax, rsp
0x1800097da  mov     [rsp+68h+var_18], rax
0x1800097df  mov     r9, rdx
0x1800097e2  mov     r10d, ecx
0x1800097e5  prefetchw byte ptr [rdx]
0x1800097e8  mov     eax, [rdx]
0x1800097ea  mov     r8d, eax
0x1800097ed  and     r8d, 0FFC0401Eh
0x1800097f4  lock cmpxchg [rdx], r8d
0x1800097f9  jnz     short loc_1800097EA
0x1800097fb  mov     ecx, eax
0x1800097fd  mov     r8d, eax
0x180009800  shr     r8d, 1
0x180009803  and     r8d, 0Fh
0x180009807  jz      short loc_180009824
0x180009809  prefetchw byte ptr [rdx+4]
0x18000980d  mov     eax, [rdx+4]
0x180009810  mov     edx, eax
0x180009812  or      edx, r8d
0x180009815  lock cmpxchg [r9+4], edx
0x18000981b  jnz     short loc_180009810
0x18000981d  not     eax
0x18000981f  and     eax, r8d
0x180009822  jmp     short loc_180009827
0x180009824  mov     eax, r8d
0x180009827  mov     r8d, 2
0x18000982d  lea     r9d, [r8-1]
0x180009831  test    r9b, al
0x180009834  jz      short loc_18000984A
0x180009836  mov     [rsp+68h+var_48], r10d
0x18000983b  mov     [rsp+68h+var_44], 10002h
0x180009843  lea     rdx, [rsp+68h+var_40]
0x180009848  jmp     short loc_18000984F
0x18000984a  lea     rdx, [rsp+68h+var_48]
0x18000984f  test    r8b, al
0x180009852  jz      short loc_180009862
0x180009854  mov     [rdx], r10d
0x180009857  mov     dword ptr [rdx+4], 10006h
0x18000985e  add     rdx, 8
0x180009862  test    al, 4
0x180009864  jz      short loc_180009874
0x180009866  mov     [rdx], r10d
0x180009869  mov     dword ptr [rdx+4], 10003h
0x180009870  add     rdx, 8
0x180009874  cmp     eax, 8
0x180009877  jb      short loc_180009887
0x180009879  mov     [rdx], r10d
0x18000987c  mov     dword ptr [rdx+4], 10007h
0x180009883  add     rdx, 8
0x180009887  mov     r8d, ecx
0x18000988a  shr     r8d, 5
0x18000988e  mov     r11d, 1FFh
0x180009894  test    r11d, r8d
0x180009897  jz      short loc_1800098BA
0x180009899  mov     [rdx], r10d
0x18000989c  mov     eax, ecx
0x18000989e  shr     eax, 0Eh
0x1800098a1  and     ax, r9w
0x1800098a5  shl     ax, 2
0x1800098a9  mov     [rdx+4], ax
0x1800098ad  and     r8w, r11w; unsigned __int64
0x1800098b1  mov     [rdx+6], r8w
0x1800098b6  add     rdx, 8
0x1800098ba  mov     eax, ecx
0x1800098bc  shr     eax, 0Fh
0x1800098bf  test    al, 7Fh
0x1800098c1  jz      short loc_1800098E5
0x1800098c3  mov     [rdx], r10d
0x1800098c6  shr     ecx, 16h
0x1800098c9  and     cx, r9w
0x1800098cd  shl     cx, 2
0x1800098d1  add     cx, r9w
0x1800098d5  mov     [rdx+4], cx
0x1800098d9  and     ax, 7Fh
0x1800098dd  mov     [rdx+6], ax
0x1800098e1  add     rdx, 8
0x1800098e5  lea     rax, [rsp+68h+var_48]
0x1800098ea  sub     rdx, rax
0x1800098ed  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800098f1  test    rdx, rdx
0x1800098f4  jle     short loc_180009901
0x1800098f6  lea     rcx, [rsp+68h+var_48]; this
0x1800098fb  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180009900  nop
0x180009901  mov     rcx, [rsp+68h+var_18]
0x180009906  xor     rcx, rsp; StackCookie
0x180009909  call    __security_check_cookie
0x18000990e  add     rsp, 68h
0x180009912  retn
```
