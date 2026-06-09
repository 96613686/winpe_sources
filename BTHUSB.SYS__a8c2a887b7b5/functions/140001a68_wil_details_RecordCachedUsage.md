# wil_details_RecordCachedUsage

- ea: `0x140001a68`
- end: `0x140001baf`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400184c0`

## callees

- `0x140001a68`
- `0x14000ddc0`
- `0x140018540`

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
0x140001a68  sub     rsp, 68h
0x140001a6c  mov     rax, cs:__security_cookie
0x140001a73  xor     rax, rsp
0x140001a76  mov     [rsp+68h+var_18], rax
0x140001a7b  mov     r9, rdx
0x140001a7e  mov     r10d, ecx
0x140001a81  prefetchw byte ptr [rdx]
0x140001a84  mov     eax, [rdx]
0x140001a86  mov     r8d, eax
0x140001a89  and     r8d, 0FFC0401Eh
0x140001a90  lock cmpxchg [rdx], r8d
0x140001a95  jnz     short loc_140001A86
0x140001a97  mov     r8d, eax
0x140001a9a  mov     ecx, eax
0x140001a9c  shr     r8d, 1
0x140001a9f  and     r8d, 0Fh
0x140001aa3  jz      short loc_140001AC0
0x140001aa5  prefetchw byte ptr [rdx+4]
0x140001aa9  mov     eax, [rdx+4]
0x140001aac  mov     edx, eax
0x140001aae  or      edx, r8d
0x140001ab1  lock cmpxchg [r9+4], edx
0x140001ab7  jnz     short loc_140001AAC
0x140001ab9  not     eax
0x140001abb  and     eax, r8d
0x140001abe  jmp     short loc_140001AC3
0x140001ac0  mov     eax, r8d
0x140001ac3  mov     r8d, 2
0x140001ac9  lea     r9d, [r8-1]
0x140001acd  test    r9b, al
0x140001ad0  jz      short loc_140001AE6
0x140001ad2  mov     [rsp+68h+var_48], r10d
0x140001ad7  lea     rdx, [rsp+68h+var_40]
0x140001adc  mov     [rsp+68h+var_44], 10002h
0x140001ae4  jmp     short loc_140001AEB
0x140001ae6  lea     rdx, [rsp+68h+var_48]
0x140001aeb  test    r8b, al
0x140001aee  jz      short loc_140001AFE
0x140001af0  mov     [rdx], r10d
0x140001af3  mov     dword ptr [rdx+4], 10006h
0x140001afa  add     rdx, 8
0x140001afe  test    al, 4
0x140001b00  jz      short loc_140001B10
0x140001b02  mov     [rdx], r10d
0x140001b05  mov     dword ptr [rdx+4], 10003h
0x140001b0c  add     rdx, 8
0x140001b10  cmp     eax, 8
0x140001b13  jb      short loc_140001B23
0x140001b15  mov     [rdx], r10d
0x140001b18  mov     dword ptr [rdx+4], 10007h
0x140001b1f  add     rdx, 8
0x140001b23  mov     r8d, ecx
0x140001b26  mov     r11d, 1FFh
0x140001b2c  shr     r8d, 5
0x140001b30  test    r11d, r8d
0x140001b33  jz      short loc_140001B56
0x140001b35  and     r8w, r11w
0x140001b39  mov     [rdx], r10d
0x140001b3c  mov     eax, ecx
0x140001b3e  mov     [rdx+6], r8w
0x140001b43  shr     eax, 0Eh
0x140001b46  and     ax, r9w
0x140001b4a  shl     ax, 2
0x140001b4e  mov     [rdx+4], ax
0x140001b52  add     rdx, 8
0x140001b56  mov     eax, ecx
0x140001b58  shr     eax, 0Fh
0x140001b5b  test    al, 7Fh
0x140001b5d  jz      short loc_140001B81
0x140001b5f  shr     ecx, 16h
0x140001b62  and     ax, 7Fh
0x140001b66  and     cx, r9w
0x140001b6a  mov     [rdx], r10d
0x140001b6d  shl     cx, 2
0x140001b71  add     cx, r9w
0x140001b75  mov     [rdx+6], ax
0x140001b79  mov     [rdx+4], cx
0x140001b7d  add     rdx, 8
0x140001b81  lea     rax, [rsp+68h+var_48]
0x140001b86  sub     rdx, rax
0x140001b89  sar     rdx, 3
0x140001b8d  test    rdx, rdx
0x140001b90  jle     short loc_140001B9C
0x140001b92  lea     rcx, [rsp+68h+var_48]
0x140001b97  call    wil_details_RecordFeatureUsageCallback
0x140001b9c  mov     rcx, [rsp+68h+var_18]
0x140001ba1  xor     rcx, rsp; StackCookie
0x140001ba4  call    __security_check_cookie
0x140001ba9  add     rsp, 68h
0x140001bad  retn
```
