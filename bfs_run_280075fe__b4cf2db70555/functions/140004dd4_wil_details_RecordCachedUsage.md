# wil_details_RecordCachedUsage

- ea: `0x140004dd4`
- end: `0x140004f22`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001eb10`

## callees

- `0x140004dd4`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140004f03`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140004f03`

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
0x140004dd4  sub     rsp, 68h
0x140004dd8  mov     rax, cs:__security_cookie
0x140004ddf  xor     rax, rsp
0x140004de2  mov     [rsp+68h+var_18], rax
0x140004de7  mov     r9, rdx
0x140004dea  mov     r10d, ecx
0x140004ded  prefetchw byte ptr [rdx]
0x140004df0  mov     eax, [rdx]
0x140004df2  mov     r8d, eax
0x140004df5  and     r8d, 0FFC0401Eh
0x140004dfc  lock cmpxchg [rdx], r8d
0x140004e01  jnz     short loc_140004DF2
0x140004e03  mov     r8d, eax
0x140004e06  mov     ecx, eax
0x140004e08  shr     r8d, 1
0x140004e0b  and     r8d, 0Fh
0x140004e0f  jz      short loc_140004E2C
0x140004e11  prefetchw byte ptr [rdx+4]
0x140004e15  mov     eax, [rdx+4]
0x140004e18  mov     edx, eax
0x140004e1a  or      edx, r8d
0x140004e1d  lock cmpxchg [r9+4], edx
0x140004e23  jnz     short loc_140004E18
0x140004e25  not     eax
0x140004e27  and     eax, r8d
0x140004e2a  jmp     short loc_140004E2F
0x140004e2c  mov     eax, r8d
0x140004e2f  mov     r8d, 2
0x140004e35  lea     r9d, [r8-1]
0x140004e39  test    r9b, al
0x140004e3c  jz      short loc_140004E52
0x140004e3e  mov     [rsp+68h+var_48], r10d
0x140004e43  lea     rdx, [rsp+68h+var_40]
0x140004e48  mov     [rsp+68h+var_44], 10002h
0x140004e50  jmp     short loc_140004E57
0x140004e52  lea     rdx, [rsp+68h+var_48]
0x140004e57  test    r8b, al
0x140004e5a  jz      short loc_140004E6A
0x140004e5c  mov     [rdx], r10d
0x140004e5f  mov     dword ptr [rdx+4], 10006h
0x140004e66  add     rdx, 8
0x140004e6a  test    al, 4
0x140004e6c  jz      short loc_140004E7C
0x140004e6e  mov     [rdx], r10d
0x140004e71  mov     dword ptr [rdx+4], 10003h
0x140004e78  add     rdx, 8
0x140004e7c  cmp     eax, 8
0x140004e7f  jb      short loc_140004E8F
0x140004e81  mov     [rdx], r10d
0x140004e84  mov     dword ptr [rdx+4], 10007h
0x140004e8b  add     rdx, 8
0x140004e8f  mov     r8d, ecx
0x140004e92  mov     r11d, 1FFh
0x140004e98  shr     r8d, 5
0x140004e9c  test    r11d, r8d
0x140004e9f  jz      short loc_140004EC2
0x140004ea1  and     r8w, r11w
0x140004ea5  mov     [rdx], r10d
0x140004ea8  mov     eax, ecx
0x140004eaa  mov     [rdx+6], r8w
0x140004eaf  shr     eax, 0Eh
0x140004eb2  and     ax, r9w
0x140004eb6  shl     ax, 2
0x140004eba  mov     [rdx+4], ax
0x140004ebe  add     rdx, 8
0x140004ec2  mov     eax, ecx
0x140004ec4  shr     eax, 0Fh
0x140004ec7  test    al, 7Fh
0x140004ec9  jz      short loc_140004EED
0x140004ecb  shr     ecx, 16h
0x140004ece  and     ax, 7Fh
0x140004ed2  and     cx, r9w
0x140004ed6  mov     [rdx], r10d
0x140004ed9  shl     cx, 2
0x140004edd  add     cx, r9w
0x140004ee1  mov     [rdx+6], ax
0x140004ee5  mov     [rdx+4], cx
0x140004ee9  add     rdx, 8
0x140004eed  lea     rax, [rsp+68h+var_48]
0x140004ef2  sub     rdx, rax
0x140004ef5  sar     rdx, 3
0x140004ef9  test    rdx, rdx
0x140004efc  jle     short loc_140004F0F
0x140004efe  lea     rcx, [rsp+68h+var_48]
0x140004f03  call    cs:__imp_RtlRecordFeatureUsage
0x140004f0a  nop     dword ptr [rax+rax+00h]
0x140004f0f  mov     rcx, [rsp+68h+var_18]
0x140004f14  xor     rcx, rsp; StackCookie
0x140004f17  call    __security_check_cookie
0x140004f1c  add     rsp, 68h
0x140004f20  retn
```
