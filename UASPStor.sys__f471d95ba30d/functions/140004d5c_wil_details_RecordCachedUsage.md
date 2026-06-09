# wil_details_RecordCachedUsage

- ea: `0x140004d5c`
- end: `0x140004eaa`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400157d0`

## callees

- `0x140004d5c`
- `0x14000d7f0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140004e8b`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140004e8b`

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
0x140004d5c  sub     rsp, 68h
0x140004d60  mov     rax, cs:__security_cookie
0x140004d67  xor     rax, rsp
0x140004d6a  mov     [rsp+68h+var_18], rax
0x140004d6f  mov     r9, rdx
0x140004d72  mov     r10d, ecx
0x140004d75  prefetchw byte ptr [rdx]
0x140004d78  mov     eax, [rdx]
0x140004d7a  mov     r8d, eax
0x140004d7d  and     r8d, 0FFC0401Eh
0x140004d84  lock cmpxchg [rdx], r8d
0x140004d89  jnz     short loc_140004D7A
0x140004d8b  mov     r8d, eax
0x140004d8e  mov     ecx, eax
0x140004d90  shr     r8d, 1
0x140004d93  and     r8d, 0Fh
0x140004d97  jz      short loc_140004DB4
0x140004d99  prefetchw byte ptr [rdx+4]
0x140004d9d  mov     eax, [rdx+4]
0x140004da0  mov     edx, eax
0x140004da2  or      edx, r8d
0x140004da5  lock cmpxchg [r9+4], edx
0x140004dab  jnz     short loc_140004DA0
0x140004dad  not     eax
0x140004daf  and     eax, r8d
0x140004db2  jmp     short loc_140004DB7
0x140004db4  mov     eax, r8d
0x140004db7  mov     r8d, 2
0x140004dbd  lea     r9d, [r8-1]
0x140004dc1  test    r9b, al
0x140004dc4  jz      short loc_140004DDA
0x140004dc6  mov     [rsp+68h+var_48], r10d
0x140004dcb  lea     rdx, [rsp+68h+var_40]
0x140004dd0  mov     [rsp+68h+var_44], 10002h
0x140004dd8  jmp     short loc_140004DDF
0x140004dda  lea     rdx, [rsp+68h+var_48]
0x140004ddf  test    r8b, al
0x140004de2  jz      short loc_140004DF2
0x140004de4  mov     [rdx], r10d
0x140004de7  mov     dword ptr [rdx+4], 10006h
0x140004dee  add     rdx, 8
0x140004df2  test    al, 4
0x140004df4  jz      short loc_140004E04
0x140004df6  mov     [rdx], r10d
0x140004df9  mov     dword ptr [rdx+4], 10003h
0x140004e00  add     rdx, 8
0x140004e04  cmp     eax, 8
0x140004e07  jb      short loc_140004E17
0x140004e09  mov     [rdx], r10d
0x140004e0c  mov     dword ptr [rdx+4], 10007h
0x140004e13  add     rdx, 8
0x140004e17  mov     r8d, ecx
0x140004e1a  mov     r11d, 1FFh
0x140004e20  shr     r8d, 5
0x140004e24  test    r11d, r8d
0x140004e27  jz      short loc_140004E4A
0x140004e29  and     r8w, r11w
0x140004e2d  mov     [rdx], r10d
0x140004e30  mov     eax, ecx
0x140004e32  mov     [rdx+6], r8w
0x140004e37  shr     eax, 0Eh
0x140004e3a  and     ax, r9w
0x140004e3e  shl     ax, 2
0x140004e42  mov     [rdx+4], ax
0x140004e46  add     rdx, 8
0x140004e4a  mov     eax, ecx
0x140004e4c  shr     eax, 0Fh
0x140004e4f  test    al, 7Fh
0x140004e51  jz      short loc_140004E75
0x140004e53  shr     ecx, 16h
0x140004e56  and     ax, 7Fh
0x140004e5a  and     cx, r9w
0x140004e5e  mov     [rdx], r10d
0x140004e61  shl     cx, 2
0x140004e65  add     cx, r9w
0x140004e69  mov     [rdx+6], ax
0x140004e6d  mov     [rdx+4], cx
0x140004e71  add     rdx, 8
0x140004e75  lea     rax, [rsp+68h+var_48]
0x140004e7a  sub     rdx, rax
0x140004e7d  sar     rdx, 3
0x140004e81  test    rdx, rdx
0x140004e84  jle     short loc_140004E97
0x140004e86  lea     rcx, [rsp+68h+var_48]
0x140004e8b  call    cs:__imp_RtlRecordFeatureUsage
0x140004e92  nop     dword ptr [rax+rax+00h]
0x140004e97  mov     rcx, [rsp+68h+var_18]
0x140004e9c  xor     rcx, rsp; StackCookie
0x140004e9f  call    __security_check_cookie
0x140004ea4  add     rsp, 68h
0x140004ea8  retn
```
