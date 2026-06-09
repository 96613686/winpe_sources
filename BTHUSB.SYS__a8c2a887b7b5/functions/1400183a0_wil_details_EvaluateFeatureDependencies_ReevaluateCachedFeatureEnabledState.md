# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400183a0`
- end: `0x1400184ad`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140018250`
- `0x140018364`

## callees

- `0x140018364`
- `0x1400183a0`

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
0x1400183a0  mov     [rsp+arg_8], rbx
0x1400183a5  mov     [rsp+arg_10], rbp
0x1400183aa  push    rsi
0x1400183ab  push    rdi
0x1400183ac  push    r13
0x1400183ae  push    r14
0x1400183b0  push    r15
0x1400183b2  sub     rsp, 20h
0x1400183b6  mov     r13d, 1
0x1400183bc  mov     [rsp+48h+arg_0], 0
0x1400183c5  mov     esi, edx
0x1400183c7  mov     r15, rcx
0x1400183ca  shr     esi, 6
0x1400183cd  mov     ecx, 0C00h
0x1400183d2  mov     eax, edx
0x1400183d4  and     esi, r13d
0x1400183d7  and     eax, ecx
0x1400183d9  mov     rbx, rdx
0x1400183dc  mov     edi, r13d
0x1400183df  cmp     eax, ecx
0x1400183e1  jz      short loc_1400183EB
0x1400183e3  test    esi, esi
0x1400183e5  jnz     short loc_1400183EB
0x1400183e7  xor     ebp, ebp
0x1400183e9  jmp     short loc_140018459
0x1400183eb  mov     r14, [r8+20h]
0x1400183ef  xor     ebp, ebp
0x1400183f1  cmp     eax, ecx
0x1400183f3  setz    bpl
0x1400183f7  test    r14, r14
0x1400183fa  jz      short loc_140018459
0x1400183fc  mov     rax, [r14]
0x1400183ff  test    rax, rax
0x140018402  jz      short loc_14001844A
0x140018404  cmp     byte ptr [rax+1Eh], 0
0x140018408  jnz     short loc_140018435
0x14001840a  cmp     byte ptr [rax+1Dh], 0
0x14001840e  jnz     short loc_140018435
0x140018410  mov     rcx, [rax]
0x140018413  mov     rdx, rax
0x140018416  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14001841b  test    edi, edi
0x14001841d  jz      short loc_140018429
0x14001841f  test    r13b, al
0x140018422  jz      short loc_140018429
0x140018424  mov     edi, r13d
0x140018427  jmp     short loc_14001842B
0x140018429  xor     edi, edi
0x14001842b  add     r14, 8
0x14001842f  test    edi, edi
0x140018431  jnz     short loc_1400183FC
0x140018433  jmp     short loc_14001844A
0x140018435  test    edi, edi
0x140018437  jz      short loc_140018448
0x140018439  cmp     byte ptr [rax+1Fh], 0
0x14001843d  jz      short loc_140018448
0x14001843f  mov     edi, r13d
0x140018442  add     r14, 8
0x140018446  jmp     short loc_1400183FC
0x140018448  xor     edi, edi
0x14001844a  test    esi, esi
0x14001844c  jz      short loc_140018457
0x14001844e  test    edi, edi
0x140018450  jz      short loc_140018457
0x140018452  mov     esi, r13d
0x140018455  jmp     short loc_140018459
0x140018457  xor     esi, esi
0x140018459  mov     edx, ebx
0x14001845b  and     edx, 0FFFFFFFEh
0x14001845e  or      edx, esi
0x140018460  test    ebp, ebp
0x140018462  jz      short loc_14001846C
0x140018464  test    edi, edi
0x140018466  jnz     short loc_14001846C
0x140018468  btr     edx, 0Ah
0x14001846c  mov     eax, ebx
0x14001846e  mov     ecx, edx
0x140018470  and     eax, r13d
0x140018473  and     ecx, 0FFFFFFCFh
0x140018476  cmp     eax, esi
0x140018478  mov     eax, ebx
0x14001847a  cmovz   ecx, edx
0x14001847d  btr     ecx, 9
0x140018481  mov     dword ptr [rsp+48h+arg_0], ecx
0x140018485  lock cmpxchg [r15], ecx
0x14001848a  jz      short loc_140018490
0x14001848c  mov     ebx, eax
0x14001848e  jmp     short loc_140018459
0x140018490  mov     rax, [rsp+48h+arg_0]
0x140018495  mov     rbx, [rsp+48h+arg_8]
0x14001849a  mov     rbp, [rsp+48h+arg_10]
0x14001849f  add     rsp, 20h
0x1400184a3  pop     r15
0x1400184a5  pop     r14
0x1400184a7  pop     r13
0x1400184a9  pop     rdi
0x1400184aa  pop     rsi
0x1400184ab  retn
```
