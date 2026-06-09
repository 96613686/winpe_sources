# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14001c734`
- end: `0x14001c841`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001c5e0`
- `0x14001c6f8`

## callees

- `0x14001c6f8`
- `0x14001c734`

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
0x14001c734  mov     [rsp+arg_8], rbx
0x14001c739  mov     [rsp+arg_10], rbp
0x14001c73e  push    rsi
0x14001c73f  push    rdi
0x14001c740  push    r13
0x14001c742  push    r14
0x14001c744  push    r15
0x14001c746  sub     rsp, 20h
0x14001c74a  mov     r13d, 1
0x14001c750  mov     [rsp+48h+arg_0], 0
0x14001c759  mov     esi, edx
0x14001c75b  mov     r15, rcx
0x14001c75e  shr     esi, 6
0x14001c761  mov     ecx, 0C00h
0x14001c766  mov     eax, edx
0x14001c768  and     esi, r13d
0x14001c76b  and     eax, ecx
0x14001c76d  mov     rbx, rdx
0x14001c770  mov     edi, r13d
0x14001c773  cmp     eax, ecx
0x14001c775  jz      short loc_14001C77F
0x14001c777  test    esi, esi
0x14001c779  jnz     short loc_14001C77F
0x14001c77b  xor     ebp, ebp
0x14001c77d  jmp     short loc_14001C7ED
0x14001c77f  mov     r14, [r8+20h]
0x14001c783  xor     ebp, ebp
0x14001c785  cmp     eax, ecx
0x14001c787  setz    bpl
0x14001c78b  test    r14, r14
0x14001c78e  jz      short loc_14001C7ED
0x14001c790  mov     rax, [r14]
0x14001c793  test    rax, rax
0x14001c796  jz      short loc_14001C7DE
0x14001c798  cmp     byte ptr [rax+1Eh], 0
0x14001c79c  jnz     short loc_14001C7C9
0x14001c79e  cmp     byte ptr [rax+1Dh], 0
0x14001c7a2  jnz     short loc_14001C7C9
0x14001c7a4  mov     rcx, [rax]
0x14001c7a7  mov     rdx, rax
0x14001c7aa  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14001c7af  test    edi, edi
0x14001c7b1  jz      short loc_14001C7BD
0x14001c7b3  test    r13b, al
0x14001c7b6  jz      short loc_14001C7BD
0x14001c7b8  mov     edi, r13d
0x14001c7bb  jmp     short loc_14001C7BF
0x14001c7bd  xor     edi, edi
0x14001c7bf  add     r14, 8
0x14001c7c3  test    edi, edi
0x14001c7c5  jnz     short loc_14001C790
0x14001c7c7  jmp     short loc_14001C7DE
0x14001c7c9  test    edi, edi
0x14001c7cb  jz      short loc_14001C7DC
0x14001c7cd  cmp     byte ptr [rax+1Fh], 0
0x14001c7d1  jz      short loc_14001C7DC
0x14001c7d3  mov     edi, r13d
0x14001c7d6  add     r14, 8
0x14001c7da  jmp     short loc_14001C790
0x14001c7dc  xor     edi, edi
0x14001c7de  test    esi, esi
0x14001c7e0  jz      short loc_14001C7EB
0x14001c7e2  test    edi, edi
0x14001c7e4  jz      short loc_14001C7EB
0x14001c7e6  mov     esi, r13d
0x14001c7e9  jmp     short loc_14001C7ED
0x14001c7eb  xor     esi, esi
0x14001c7ed  mov     edx, ebx
0x14001c7ef  and     edx, 0FFFFFFFEh
0x14001c7f2  or      edx, esi
0x14001c7f4  test    ebp, ebp
0x14001c7f6  jz      short loc_14001C800
0x14001c7f8  test    edi, edi
0x14001c7fa  jnz     short loc_14001C800
0x14001c7fc  btr     edx, 0Ah
0x14001c800  mov     eax, ebx
0x14001c802  mov     ecx, edx
0x14001c804  and     eax, r13d
0x14001c807  and     ecx, 0FFFFFFCFh
0x14001c80a  cmp     eax, esi
0x14001c80c  mov     eax, ebx
0x14001c80e  cmovz   ecx, edx
0x14001c811  btr     ecx, 9
0x14001c815  mov     dword ptr [rsp+48h+arg_0], ecx
0x14001c819  lock cmpxchg [r15], ecx
0x14001c81e  jz      short loc_14001C824
0x14001c820  mov     ebx, eax
0x14001c822  jmp     short loc_14001C7ED
0x14001c824  mov     rax, [rsp+48h+arg_0]
0x14001c829  mov     rbx, [rsp+48h+arg_8]
0x14001c82e  mov     rbp, [rsp+48h+arg_10]
0x14001c833  add     rsp, 20h
0x14001c837  pop     r15
0x14001c839  pop     r14
0x14001c83b  pop     r13
0x14001c83d  pop     rdi
0x14001c83e  pop     rsi
0x14001c83f  retn
```
