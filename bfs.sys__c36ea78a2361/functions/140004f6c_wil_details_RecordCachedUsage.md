# wil_details_RecordCachedUsage

- ea: `0x140004f6c`
- end: `0x1400050ba`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: `_DWORD *__fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001eb70`

## callees

- `0x140004f6c`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000509b`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000509b`

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
0x140004f6c  sub     rsp, 68h
0x140004f70  mov     rax, cs:__security_cookie
0x140004f77  xor     rax, rsp
0x140004f7a  mov     [rsp+68h+var_18], rax
0x140004f7f  mov     r9, rdx
0x140004f82  mov     r10d, ecx
0x140004f85  prefetchw byte ptr [rdx]
0x140004f88  mov     eax, [rdx]
0x140004f8a  mov     r8d, eax
0x140004f8d  and     r8d, 0FFC0401Eh
0x140004f94  lock cmpxchg [rdx], r8d
0x140004f99  jnz     short loc_140004F8A
0x140004f9b  mov     r8d, eax
0x140004f9e  mov     ecx, eax
0x140004fa0  shr     r8d, 1
0x140004fa3  and     r8d, 0Fh
0x140004fa7  jz      short loc_140004FC4
0x140004fa9  prefetchw byte ptr [rdx+4]
0x140004fad  mov     eax, [rdx+4]
0x140004fb0  mov     edx, eax
0x140004fb2  or      edx, r8d
0x140004fb5  lock cmpxchg [r9+4], edx
0x140004fbb  jnz     short loc_140004FB0
0x140004fbd  not     eax
0x140004fbf  and     eax, r8d
0x140004fc2  jmp     short loc_140004FC7
0x140004fc4  mov     eax, r8d
0x140004fc7  mov     r8d, 2
0x140004fcd  lea     r9d, [r8-1]
0x140004fd1  test    r9b, al
0x140004fd4  jz      short loc_140004FEA
0x140004fd6  mov     [rsp+68h+var_48], r10d
0x140004fdb  lea     rdx, [rsp+68h+var_40]
0x140004fe0  mov     [rsp+68h+var_44], 10002h
0x140004fe8  jmp     short loc_140004FEF
0x140004fea  lea     rdx, [rsp+68h+var_48]
0x140004fef  test    r8b, al
0x140004ff2  jz      short loc_140005002
0x140004ff4  mov     [rdx], r10d
0x140004ff7  mov     dword ptr [rdx+4], 10006h
0x140004ffe  add     rdx, 8
0x140005002  test    al, 4
0x140005004  jz      short loc_140005014
0x140005006  mov     [rdx], r10d
0x140005009  mov     dword ptr [rdx+4], 10003h
0x140005010  add     rdx, 8
0x140005014  cmp     eax, 8
0x140005017  jb      short loc_140005027
0x140005019  mov     [rdx], r10d
0x14000501c  mov     dword ptr [rdx+4], 10007h
0x140005023  add     rdx, 8
0x140005027  mov     r8d, ecx
0x14000502a  mov     r11d, 1FFh
0x140005030  shr     r8d, 5
0x140005034  test    r11d, r8d
0x140005037  jz      short loc_14000505A
0x140005039  and     r8w, r11w
0x14000503d  mov     [rdx], r10d
0x140005040  mov     eax, ecx
0x140005042  mov     [rdx+6], r8w
0x140005047  shr     eax, 0Eh
0x14000504a  and     ax, r9w
0x14000504e  shl     ax, 2
0x140005052  mov     [rdx+4], ax
0x140005056  add     rdx, 8
0x14000505a  mov     eax, ecx
0x14000505c  shr     eax, 0Fh
0x14000505f  test    al, 7Fh
0x140005061  jz      short loc_140005085
0x140005063  shr     ecx, 16h
0x140005066  and     ax, 7Fh
0x14000506a  and     cx, r9w
0x14000506e  mov     [rdx], r10d
0x140005071  shl     cx, 2
0x140005075  add     cx, r9w
0x140005079  mov     [rdx+6], ax
0x14000507d  mov     [rdx+4], cx
0x140005081  add     rdx, 8
0x140005085  lea     rax, [rsp+68h+var_48]
0x14000508a  sub     rdx, rax
0x14000508d  sar     rdx, 3
0x140005091  test    rdx, rdx
0x140005094  jle     short loc_1400050A7
0x140005096  lea     rcx, [rsp+68h+var_48]
0x14000509b  call    cs:__imp_RtlRecordFeatureUsage
0x1400050a2  nop     dword ptr [rax+rax+00h]
0x1400050a7  mov     rcx, [rsp+68h+var_18]
0x1400050ac  xor     rcx, rsp; StackCookie
0x1400050af  call    __security_check_cookie
0x1400050b4  add     rsp, 68h
0x1400050b8  retn
```
