# wil_details_RecordCachedUsage

- ea: `0x14000178c`
- end: `0x1400018da`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022910`

## callees

- `0x14000178c`
- `0x140006a20`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400018bb`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400018bb`

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
    return (_DWORD *)RtlRecordFeatureUsage(v10);
  return result;
}

```

## disassembly

```asm
0x14000178c  sub     rsp, 68h
0x140001790  mov     rax, cs:__security_cookie
0x140001797  xor     rax, rsp
0x14000179a  mov     [rsp+68h+var_18], rax
0x14000179f  mov     r9, rdx
0x1400017a2  mov     r10d, ecx
0x1400017a5  prefetchw byte ptr [rdx]
0x1400017a8  mov     eax, [rdx]
0x1400017aa  mov     r8d, eax
0x1400017ad  and     r8d, 0FFC0401Eh
0x1400017b4  lock cmpxchg [rdx], r8d
0x1400017b9  jnz     short loc_1400017AA
0x1400017bb  mov     r8d, eax
0x1400017be  mov     ecx, eax
0x1400017c0  shr     r8d, 1
0x1400017c3  and     r8d, 0Fh
0x1400017c7  jz      short loc_1400017E4
0x1400017c9  prefetchw byte ptr [rdx+4]
0x1400017cd  mov     eax, [rdx+4]
0x1400017d0  mov     edx, eax
0x1400017d2  or      edx, r8d
0x1400017d5  lock cmpxchg [r9+4], edx
0x1400017db  jnz     short loc_1400017D0
0x1400017dd  not     eax
0x1400017df  and     eax, r8d
0x1400017e2  jmp     short loc_1400017E7
0x1400017e4  mov     eax, r8d
0x1400017e7  mov     r8d, 2
0x1400017ed  lea     r9d, [r8-1]
0x1400017f1  test    r9b, al
0x1400017f4  jz      short loc_14000180A
0x1400017f6  mov     [rsp+68h+var_48], r10d
0x1400017fb  lea     rdx, [rsp+68h+var_40]
0x140001800  mov     [rsp+68h+var_44], 10002h
0x140001808  jmp     short loc_14000180F
0x14000180a  lea     rdx, [rsp+68h+var_48]
0x14000180f  test    r8b, al
0x140001812  jz      short loc_140001822
0x140001814  mov     [rdx], r10d
0x140001817  mov     dword ptr [rdx+4], 10006h
0x14000181e  add     rdx, 8
0x140001822  test    al, 4
0x140001824  jz      short loc_140001834
0x140001826  mov     [rdx], r10d
0x140001829  mov     dword ptr [rdx+4], 10003h
0x140001830  add     rdx, 8
0x140001834  cmp     eax, 8
0x140001837  jb      short loc_140001847
0x140001839  mov     [rdx], r10d
0x14000183c  mov     dword ptr [rdx+4], 10007h
0x140001843  add     rdx, 8
0x140001847  mov     r8d, ecx
0x14000184a  mov     r11d, 1FFh
0x140001850  shr     r8d, 5
0x140001854  test    r11d, r8d
0x140001857  jz      short loc_14000187A
0x140001859  and     r8w, r11w
0x14000185d  mov     [rdx], r10d
0x140001860  mov     eax, ecx
0x140001862  mov     [rdx+6], r8w
0x140001867  shr     eax, 0Eh
0x14000186a  and     ax, r9w
0x14000186e  shl     ax, 2
0x140001872  mov     [rdx+4], ax
0x140001876  add     rdx, 8
0x14000187a  mov     eax, ecx
0x14000187c  shr     eax, 0Fh
0x14000187f  test    al, 7Fh
0x140001881  jz      short loc_1400018A5
0x140001883  shr     ecx, 16h
0x140001886  and     ax, 7Fh
0x14000188a  and     cx, r9w
0x14000188e  mov     [rdx], r10d
0x140001891  shl     cx, 2
0x140001895  add     cx, r9w
0x140001899  mov     [rdx+6], ax
0x14000189d  mov     [rdx+4], cx
0x1400018a1  add     rdx, 8
0x1400018a5  lea     rax, [rsp+68h+var_48]
0x1400018aa  sub     rdx, rax
0x1400018ad  sar     rdx, 3
0x1400018b1  test    rdx, rdx
0x1400018b4  jle     short loc_1400018C7
0x1400018b6  lea     rcx, [rsp+68h+var_48]
0x1400018bb  call    cs:__imp_RtlRecordFeatureUsage
0x1400018c2  nop     dword ptr [rax+rax+00h]
0x1400018c7  mov     rcx, [rsp+68h+var_18]
0x1400018cc  xor     rcx, rsp; StackCookie
0x1400018cf  call    __security_check_cookie
0x1400018d4  add     rsp, 68h
0x1400018d8  retn
```
