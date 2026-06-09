# wil_details_RecordCachedUsage

- ea: `0x1400020d8`
- end: `0x140002226`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001c850`

## callees

- `0x1400020d8`
- `0x140007d00`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140002207`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140002207`

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
0x1400020d8  sub     rsp, 68h
0x1400020dc  mov     rax, cs:__security_cookie
0x1400020e3  xor     rax, rsp
0x1400020e6  mov     [rsp+68h+var_18], rax
0x1400020eb  mov     r9, rdx
0x1400020ee  mov     r10d, ecx
0x1400020f1  prefetchw byte ptr [rdx]
0x1400020f4  mov     eax, [rdx]
0x1400020f6  mov     r8d, eax
0x1400020f9  and     r8d, 0FFC0401Eh
0x140002100  lock cmpxchg [rdx], r8d
0x140002105  jnz     short loc_1400020F6
0x140002107  mov     r8d, eax
0x14000210a  mov     ecx, eax
0x14000210c  shr     r8d, 1
0x14000210f  and     r8d, 0Fh
0x140002113  jz      short loc_140002130
0x140002115  prefetchw byte ptr [rdx+4]
0x140002119  mov     eax, [rdx+4]
0x14000211c  mov     edx, eax
0x14000211e  or      edx, r8d
0x140002121  lock cmpxchg [r9+4], edx
0x140002127  jnz     short loc_14000211C
0x140002129  not     eax
0x14000212b  and     eax, r8d
0x14000212e  jmp     short loc_140002133
0x140002130  mov     eax, r8d
0x140002133  mov     r8d, 2
0x140002139  lea     r9d, [r8-1]
0x14000213d  test    r9b, al
0x140002140  jz      short loc_140002156
0x140002142  mov     [rsp+68h+var_48], r10d
0x140002147  lea     rdx, [rsp+68h+var_40]
0x14000214c  mov     [rsp+68h+var_44], 10002h
0x140002154  jmp     short loc_14000215B
0x140002156  lea     rdx, [rsp+68h+var_48]
0x14000215b  test    r8b, al
0x14000215e  jz      short loc_14000216E
0x140002160  mov     [rdx], r10d
0x140002163  mov     dword ptr [rdx+4], 10006h
0x14000216a  add     rdx, 8
0x14000216e  test    al, 4
0x140002170  jz      short loc_140002180
0x140002172  mov     [rdx], r10d
0x140002175  mov     dword ptr [rdx+4], 10003h
0x14000217c  add     rdx, 8
0x140002180  cmp     eax, 8
0x140002183  jb      short loc_140002193
0x140002185  mov     [rdx], r10d
0x140002188  mov     dword ptr [rdx+4], 10007h
0x14000218f  add     rdx, 8
0x140002193  mov     r8d, ecx
0x140002196  mov     r11d, 1FFh
0x14000219c  shr     r8d, 5
0x1400021a0  test    r11d, r8d
0x1400021a3  jz      short loc_1400021C6
0x1400021a5  and     r8w, r11w
0x1400021a9  mov     [rdx], r10d
0x1400021ac  mov     eax, ecx
0x1400021ae  mov     [rdx+6], r8w
0x1400021b3  shr     eax, 0Eh
0x1400021b6  and     ax, r9w
0x1400021ba  shl     ax, 2
0x1400021be  mov     [rdx+4], ax
0x1400021c2  add     rdx, 8
0x1400021c6  mov     eax, ecx
0x1400021c8  shr     eax, 0Fh
0x1400021cb  test    al, 7Fh
0x1400021cd  jz      short loc_1400021F1
0x1400021cf  shr     ecx, 16h
0x1400021d2  and     ax, 7Fh
0x1400021d6  and     cx, r9w
0x1400021da  mov     [rdx], r10d
0x1400021dd  shl     cx, 2
0x1400021e1  add     cx, r9w
0x1400021e5  mov     [rdx+6], ax
0x1400021e9  mov     [rdx+4], cx
0x1400021ed  add     rdx, 8
0x1400021f1  lea     rax, [rsp+68h+var_48]
0x1400021f6  sub     rdx, rax
0x1400021f9  sar     rdx, 3
0x1400021fd  test    rdx, rdx
0x140002200  jle     short loc_140002213
0x140002202  lea     rcx, [rsp+68h+var_48]
0x140002207  call    cs:__imp_RtlRecordFeatureUsage
0x14000220e  nop     dword ptr [rax+rax+00h]
0x140002213  mov     rcx, [rsp+68h+var_18]
0x140002218  xor     rcx, rsp; StackCookie
0x14000221b  call    __security_check_cookie
0x140002220  add     rsp, 68h
0x140002224  retn
```
