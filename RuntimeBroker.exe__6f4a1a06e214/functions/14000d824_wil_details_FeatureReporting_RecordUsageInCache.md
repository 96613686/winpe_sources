# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000d824`
- end: `0x14000d99b`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005238`

## callees

- `0x14000d678`
- `0x14000d748`
- `0x14000d824`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r11d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 v13; // edx
  int v14; // r9d
  signed __int32 v15; // r11d
  signed __int32 v16; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_35;
    case 1:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_34;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v5 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
      goto LABEL_16;
    v6 = *((_DWORD *)a2 + 1);
    do
    {
      v7 = (v6 & 0x10) != 0 && ((v6 >> 5) & 0x3F) == v5;
      *(_DWORD *)(a1 + 16) = v7;
      v8 = v6;
      v6 = _InterlockedCompareExchange(
             a2 + 1,
             v6 ^ ((unsigned __int16)v6 ^ (unsigned __int16)(32 * v5)) & 0x7E0 | 0x10,
             v6);
    }
    while ( v8 != v6 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
    }
    return a1;
  }
LABEL_17:
  v9 = 0;
  v10 = a3 - 2;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( v12 )
      {
        if ( v12 == 1 )
          v9 = 16;
      }
      else
      {
        v9 = 4;
      }
    }
    else
    {
      v9 = 8;
    }
  }
  else
  {
    v9 = 2;
  }
  v13 = *a2;
  v14 = 1;
  while ( 1 )
  {
    v15 = v13 | v9 | 1;
    *(_DWORD *)(a1 + 16) = (v13 | v9) == v13;
    if ( (v13 | v9) == v13 )
      v15 = v13 | v9;
    v16 = _InterlockedCompareExchange(a2, v15, v13);
    if ( v13 == v16 )
      break;
    v13 = v16;
  }
  if ( (v15 & 1) == 0 || (v13 & 1) != 0 )
    v14 = 0;
  *(_DWORD *)a1 = v14;
  return a1;
}

```

## disassembly

```asm
0x14000d824  mov     [rsp+arg_0], rbx
0x14000d829  push    rdi
0x14000d82a  sub     rsp, 20h
0x14000d82e  xor     eax, eax
0x14000d830  xorps   xmm0, xmm0
0x14000d833  mov     r10, rdx
0x14000d836  mov     rbx, rcx
0x14000d839  mov     r9d, r8d
0x14000d83c  movups  xmmword ptr [rcx], xmm0
0x14000d83f  mov     [rcx+10h], rax
0x14000d843  test    r8d, r8d
0x14000d846  jz      loc_14000D97F
0x14000d84c  sub     r9d, 1
0x14000d850  jz      loc_14000D96F
0x14000d856  sub     r9d, 1
0x14000d85a  jz      loc_14000D8F7
0x14000d860  sub     r9d, 1
0x14000d864  jz      loc_14000D8F7
0x14000d86a  sub     r9d, 1
0x14000d86e  jz      loc_14000D97F
0x14000d874  sub     r9d, 1
0x14000d878  jz      loc_14000D96F
0x14000d87e  sub     r9d, 1
0x14000d882  jz      short loc_14000D8F7
0x14000d884  cmp     r9d, 1
0x14000d888  jz      short loc_14000D8F7
0x14000d88a  lea     r11d, [r8-140h]
0x14000d891  lea     r9d, [rax+1]
0x14000d895  cmp     r11d, 40h ; '@'
0x14000d899  jge     short loc_14000D8E3
0x14000d89b  mov     eax, [rdx+4]
0x14000d89e  lea     ecx, [r9+0Fh]
0x14000d8a2  mov     edi, r11d
0x14000d8a5  shl     edi, 5
0x14000d8a8  test    cl, al
0x14000d8aa  jz      short loc_14000D8BE
0x14000d8ac  mov     edx, eax
0x14000d8ae  shr     edx, 5
0x14000d8b1  and     edx, 3Fh
0x14000d8b4  cmp     edx, r11d
0x14000d8b7  jnz     short loc_14000D8BE
0x14000d8b9  mov     edx, r9d
0x14000d8bc  jmp     short loc_14000D8C0
0x14000d8be  xor     edx, edx
0x14000d8c0  mov     [rbx+10h], edx
0x14000d8c3  mov     edx, edi
0x14000d8c5  xor     edx, eax
0x14000d8c7  and     edx, 7E0h
0x14000d8cd  xor     edx, eax
0x14000d8cf  or      edx, ecx
0x14000d8d1  lock cmpxchg [r10+4], edx
0x14000d8d7  jnz     short loc_14000D8A8
0x14000d8d9  cmp     dword ptr [rbx+10h], 0
0x14000d8dd  jnz     loc_14000D98D
0x14000d8e3  mov     [rbx+8], r8d
0x14000d8e7  mov     [rbx+4], r9d
0x14000d8eb  mov     dword ptr [rbx+0Ch], 0
0x14000d8f2  jmp     loc_14000D98D
0x14000d8f7  xor     ecx, ecx
0x14000d8f9  sub     r8d, 2
0x14000d8fd  jz      short loc_14000D925
0x14000d8ff  sub     r8d, 1
0x14000d903  jz      short loc_14000D91E
0x14000d905  sub     r8d, 3
0x14000d909  jz      short loc_14000D917
0x14000d90b  cmp     r8d, 1
0x14000d90f  jnz     short loc_14000D92A
0x14000d911  lea     ecx, [r8+0Fh]
0x14000d915  jmp     short loc_14000D92A
0x14000d917  mov     ecx, 4
0x14000d91c  jmp     short loc_14000D92A
0x14000d91e  mov     ecx, 8
0x14000d923  jmp     short loc_14000D92A
0x14000d925  mov     ecx, 2
0x14000d92a  mov     edx, [rdx]
0x14000d92c  mov     r9d, 1
0x14000d932  xor     eax, eax
0x14000d934  mov     r8d, ecx
0x14000d937  or      r8d, edx
0x14000d93a  cmp     r8d, edx
0x14000d93d  mov     r11d, r8d
0x14000d940  setz    al
0x14000d943  or      r11d, r9d
0x14000d946  cmp     r8d, edx
0x14000d949  mov     [rbx+10h], eax
0x14000d94c  mov     eax, edx
0x14000d94e  cmovz   r11d, r8d
0x14000d952  lock cmpxchg [r10], r11d
0x14000d957  jz      short loc_14000D95D
0x14000d959  mov     edx, eax
0x14000d95b  jmp     short loc_14000D932
0x14000d95d  test    r9b, r11b
0x14000d960  jz      short loc_14000D967
0x14000d962  test    r9b, dl
0x14000d965  jz      short loc_14000D96A
0x14000d967  xor     r9d, r9d
0x14000d96a  mov     [rbx], r9d
0x14000d96d  jmp     short loc_14000D98D
0x14000d96f  mov     r9, rbx
0x14000d972  mov     edx, r8d
0x14000d975  mov     rcx, r10
0x14000d978  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14000d97d  jmp     short loc_14000D98D
0x14000d97f  mov     r9, rbx
0x14000d982  mov     edx, r8d
0x14000d985  mov     rcx, r10
0x14000d988  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14000d98d  mov     rax, rbx
0x14000d990  mov     rbx, [rsp+28h+arg_0]
0x14000d995  add     rsp, 20h
0x14000d999  pop     rdi
0x14000d99a  retn
```
