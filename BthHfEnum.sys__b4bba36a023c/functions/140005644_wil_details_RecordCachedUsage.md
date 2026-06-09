# wil_details_RecordCachedUsage

- ea: `0x140005644`
- end: `0x14000578b`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002a380`

## callees

- `0x140005644`
- `0x14001adc0`
- `0x14002a3d4`

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
0x140005644  sub     rsp, 68h
0x140005648  mov     rax, cs:__security_cookie
0x14000564f  xor     rax, rsp
0x140005652  mov     [rsp+68h+var_18], rax
0x140005657  mov     r9, rdx
0x14000565a  mov     r10d, ecx
0x14000565d  prefetchw byte ptr [rdx]
0x140005660  mov     eax, [rdx]
0x140005662  mov     r8d, eax
0x140005665  and     r8d, 0FFC0401Eh
0x14000566c  lock cmpxchg [rdx], r8d
0x140005671  jnz     short loc_140005662
0x140005673  mov     r8d, eax
0x140005676  mov     ecx, eax
0x140005678  shr     r8d, 1
0x14000567b  and     r8d, 0Fh
0x14000567f  jz      short loc_14000569C
0x140005681  prefetchw byte ptr [rdx+4]
0x140005685  mov     eax, [rdx+4]
0x140005688  mov     edx, eax
0x14000568a  or      edx, r8d
0x14000568d  lock cmpxchg [r9+4], edx
0x140005693  jnz     short loc_140005688
0x140005695  not     eax
0x140005697  and     eax, r8d
0x14000569a  jmp     short loc_14000569F
0x14000569c  mov     eax, r8d
0x14000569f  mov     r8d, 2
0x1400056a5  lea     r9d, [r8-1]
0x1400056a9  test    r9b, al
0x1400056ac  jz      short loc_1400056C2
0x1400056ae  mov     [rsp+68h+var_48], r10d
0x1400056b3  lea     rdx, [rsp+68h+var_40]
0x1400056b8  mov     [rsp+68h+var_44], 10002h
0x1400056c0  jmp     short loc_1400056C7
0x1400056c2  lea     rdx, [rsp+68h+var_48]
0x1400056c7  test    r8b, al
0x1400056ca  jz      short loc_1400056DA
0x1400056cc  mov     [rdx], r10d
0x1400056cf  mov     dword ptr [rdx+4], 10006h
0x1400056d6  add     rdx, 8
0x1400056da  test    al, 4
0x1400056dc  jz      short loc_1400056EC
0x1400056de  mov     [rdx], r10d
0x1400056e1  mov     dword ptr [rdx+4], 10003h
0x1400056e8  add     rdx, 8
0x1400056ec  cmp     eax, 8
0x1400056ef  jb      short loc_1400056FF
0x1400056f1  mov     [rdx], r10d
0x1400056f4  mov     dword ptr [rdx+4], 10007h
0x1400056fb  add     rdx, 8
0x1400056ff  mov     r8d, ecx
0x140005702  mov     r11d, 1FFh
0x140005708  shr     r8d, 5
0x14000570c  test    r11d, r8d
0x14000570f  jz      short loc_140005732
0x140005711  and     r8w, r11w
0x140005715  mov     [rdx], r10d
0x140005718  mov     eax, ecx
0x14000571a  mov     [rdx+6], r8w
0x14000571f  shr     eax, 0Eh
0x140005722  and     ax, r9w
0x140005726  shl     ax, 2
0x14000572a  mov     [rdx+4], ax
0x14000572e  add     rdx, 8
0x140005732  mov     eax, ecx
0x140005734  shr     eax, 0Fh
0x140005737  test    al, 7Fh
0x140005739  jz      short loc_14000575D
0x14000573b  shr     ecx, 16h
0x14000573e  and     ax, 7Fh
0x140005742  and     cx, r9w
0x140005746  mov     [rdx], r10d
0x140005749  shl     cx, 2
0x14000574d  add     cx, r9w
0x140005751  mov     [rdx+6], ax
0x140005755  mov     [rdx+4], cx
0x140005759  add     rdx, 8
0x14000575d  lea     rax, [rsp+68h+var_48]
0x140005762  sub     rdx, rax
0x140005765  sar     rdx, 3
0x140005769  test    rdx, rdx
0x14000576c  jle     short loc_140005778
0x14000576e  lea     rcx, [rsp+68h+var_48]
0x140005773  call    wil_details_RecordFeatureUsageCallback
0x140005778  mov     rcx, [rsp+68h+var_18]
0x14000577d  xor     rcx, rsp; StackCookie
0x140005780  call    __security_check_cookie
0x140005785  add     rsp, 68h
0x140005789  retn
```
