# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14000b610`
- end: `0x14000b71d`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b5d4`

## callees

- `0x14000b5d4`
- `0x14000b610`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        unsigned __int32 a2,
        __int64 a3)
{
  int v4; // esi
  signed __int32 v5; // ebx
  BOOL v6; // edi
  BOOL v7; // ebp
  _QWORD *v8; // r14
  __int64 v9; // rax
  char CachedFeatureEnabledState; // al
  unsigned int v11; // edx
  unsigned int v12; // ecx
  signed __int32 v13; // eax
  __int64 v15; // [rsp+50h] [rbp+8h]

  HIDWORD(v15) = 0;
  v4 = (a2 >> 6) & 1;
  v5 = a2;
  v6 = 1;
  if ( (a2 & 0xC00) == 0xC00 || v4 )
  {
    v8 = *(_QWORD **)(a3 + 32);
    v7 = (a2 & 0xC00) == 3072;
    if ( v8 )
    {
      while ( 1 )
      {
        v9 = *v8;
        if ( !*v8 )
          break;
        if ( *(_BYTE *)(v9 + 30) || *(_BYTE *)(v9 + 29) )
        {
          if ( !*(_BYTE *)(v9 + 31) )
          {
            v6 = 0;
            break;
          }
          v6 = 1;
          ++v8;
        }
        else
        {
          CachedFeatureEnabledState = wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
                                        *(_QWORD *)v9,
                                        *v8);
          v6 = (CachedFeatureEnabledState & 1) != 0;
          ++v8;
          if ( (CachedFeatureEnabledState & 1) == 0 )
            break;
        }
      }
      v4 = v4 && v6;
    }
  }
  else
  {
    v7 = 0;
  }
  while ( 1 )
  {
    v11 = v4 | v5 & 0xFFFFFFFE;
    if ( v7 && !v6 )
      v11 = v4 & 0xFFFFFBFF | v5 & 0xFFFFFBFE;
    v12 = v11 & 0xFFFFFFCF;
    if ( (v5 & 1) == v4 )
      v12 = v11;
    v13 = _InterlockedCompareExchange(a1, v12 & 0xFFFFFDFF, v5);
    if ( v5 == v13 )
      break;
    v5 = v13;
  }
  LODWORD(v15) = v12 & 0xFFFFFDFF;
  return v15;
}

```

## disassembly

```asm
0x14000b610  mov     [rsp+arg_8], rbx
0x14000b615  mov     [rsp+arg_10], rbp
0x14000b61a  push    rsi
0x14000b61b  push    rdi
0x14000b61c  push    r13
0x14000b61e  push    r14
0x14000b620  push    r15
0x14000b622  sub     rsp, 20h
0x14000b626  mov     r13d, 1
0x14000b62c  mov     [rsp+48h+arg_0], 0
0x14000b635  mov     esi, edx
0x14000b637  mov     r15, rcx
0x14000b63a  shr     esi, 6
0x14000b63d  mov     ecx, 0C00h
0x14000b642  mov     eax, edx
0x14000b644  and     esi, r13d
0x14000b647  and     eax, ecx
0x14000b649  mov     rbx, rdx
0x14000b64c  mov     edi, r13d
0x14000b64f  cmp     eax, ecx
0x14000b651  jz      short loc_14000B65B
0x14000b653  test    esi, esi
0x14000b655  jnz     short loc_14000B65B
0x14000b657  xor     ebp, ebp
0x14000b659  jmp     short loc_14000B6C9
0x14000b65b  mov     r14, [r8+20h]
0x14000b65f  xor     ebp, ebp
0x14000b661  cmp     eax, ecx
0x14000b663  setz    bpl
0x14000b667  test    r14, r14
0x14000b66a  jz      short loc_14000B6C9
0x14000b66c  mov     rax, [r14]
0x14000b66f  test    rax, rax
0x14000b672  jz      short loc_14000B6BA
0x14000b674  cmp     byte ptr [rax+1Eh], 0
0x14000b678  jnz     short loc_14000B6A5
0x14000b67a  cmp     byte ptr [rax+1Dh], 0
0x14000b67e  jnz     short loc_14000B6A5
0x14000b680  mov     rcx, [rax]
0x14000b683  mov     rdx, rax
0x14000b686  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000b68b  test    edi, edi
0x14000b68d  jz      short loc_14000B699
0x14000b68f  test    r13b, al
0x14000b692  jz      short loc_14000B699
0x14000b694  mov     edi, r13d
0x14000b697  jmp     short loc_14000B69B
0x14000b699  xor     edi, edi
0x14000b69b  add     r14, 8
0x14000b69f  test    edi, edi
0x14000b6a1  jnz     short loc_14000B66C
0x14000b6a3  jmp     short loc_14000B6BA
0x14000b6a5  test    edi, edi
0x14000b6a7  jz      short loc_14000B6B8
0x14000b6a9  cmp     byte ptr [rax+1Fh], 0
0x14000b6ad  jz      short loc_14000B6B8
0x14000b6af  mov     edi, r13d
0x14000b6b2  add     r14, 8
0x14000b6b6  jmp     short loc_14000B66C
0x14000b6b8  xor     edi, edi
0x14000b6ba  test    esi, esi
0x14000b6bc  jz      short loc_14000B6C7
0x14000b6be  test    edi, edi
0x14000b6c0  jz      short loc_14000B6C7
0x14000b6c2  mov     esi, r13d
0x14000b6c5  jmp     short loc_14000B6C9
0x14000b6c7  xor     esi, esi
0x14000b6c9  mov     edx, ebx
0x14000b6cb  and     edx, 0FFFFFFFEh
0x14000b6ce  or      edx, esi
0x14000b6d0  test    ebp, ebp
0x14000b6d2  jz      short loc_14000B6DC
0x14000b6d4  test    edi, edi
0x14000b6d6  jnz     short loc_14000B6DC
0x14000b6d8  btr     edx, 0Ah
0x14000b6dc  mov     eax, ebx
0x14000b6de  mov     ecx, edx
0x14000b6e0  and     eax, r13d
0x14000b6e3  and     ecx, 0FFFFFFCFh
0x14000b6e6  cmp     eax, esi
0x14000b6e8  mov     eax, ebx
0x14000b6ea  cmovz   ecx, edx
0x14000b6ed  btr     ecx, 9
0x14000b6f1  mov     dword ptr [rsp+48h+arg_0], ecx
0x14000b6f5  lock cmpxchg [r15], ecx
0x14000b6fa  jz      short loc_14000B700
0x14000b6fc  mov     ebx, eax
0x14000b6fe  jmp     short loc_14000B6C9
0x14000b700  mov     rax, [rsp+48h+arg_0]
0x14000b705  mov     rbx, [rsp+48h+arg_8]
0x14000b70a  mov     rbp, [rsp+48h+arg_10]
0x14000b70f  add     rsp, 20h
0x14000b713  pop     r15
0x14000b715  pop     r14
0x14000b717  pop     r13
0x14000b719  pop     rdi
0x14000b71a  pop     rsi
0x14000b71b  retn
```
