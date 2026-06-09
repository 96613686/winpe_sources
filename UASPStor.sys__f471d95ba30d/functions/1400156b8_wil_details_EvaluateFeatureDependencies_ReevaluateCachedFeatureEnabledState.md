# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400156b8`
- end: `0x1400157c5`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140015564`
- `0x14001567c`

## callees

- `0x14001567c`
- `0x1400156b8`

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
0x1400156b8  mov     [rsp+arg_8], rbx
0x1400156bd  mov     [rsp+arg_10], rbp
0x1400156c2  push    rsi
0x1400156c3  push    rdi
0x1400156c4  push    r13
0x1400156c6  push    r14
0x1400156c8  push    r15
0x1400156ca  sub     rsp, 20h
0x1400156ce  mov     r13d, 1
0x1400156d4  mov     [rsp+48h+arg_0], 0
0x1400156dd  mov     esi, edx
0x1400156df  mov     r15, rcx
0x1400156e2  shr     esi, 6
0x1400156e5  mov     ecx, 0C00h
0x1400156ea  mov     eax, edx
0x1400156ec  and     esi, r13d
0x1400156ef  and     eax, ecx
0x1400156f1  mov     rbx, rdx
0x1400156f4  mov     edi, r13d
0x1400156f7  cmp     eax, ecx
0x1400156f9  jz      short loc_140015703
0x1400156fb  test    esi, esi
0x1400156fd  jnz     short loc_140015703
0x1400156ff  xor     ebp, ebp
0x140015701  jmp     short loc_140015771
0x140015703  mov     r14, [r8+20h]
0x140015707  xor     ebp, ebp
0x140015709  cmp     eax, ecx
0x14001570b  setz    bpl
0x14001570f  test    r14, r14
0x140015712  jz      short loc_140015771
0x140015714  mov     rax, [r14]
0x140015717  test    rax, rax
0x14001571a  jz      short loc_140015762
0x14001571c  cmp     byte ptr [rax+1Eh], 0
0x140015720  jnz     short loc_14001574D
0x140015722  cmp     byte ptr [rax+1Dh], 0
0x140015726  jnz     short loc_14001574D
0x140015728  mov     rcx, [rax]
0x14001572b  mov     rdx, rax
0x14001572e  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140015733  test    edi, edi
0x140015735  jz      short loc_140015741
0x140015737  test    r13b, al
0x14001573a  jz      short loc_140015741
0x14001573c  mov     edi, r13d
0x14001573f  jmp     short loc_140015743
0x140015741  xor     edi, edi
0x140015743  add     r14, 8
0x140015747  test    edi, edi
0x140015749  jnz     short loc_140015714
0x14001574b  jmp     short loc_140015762
0x14001574d  test    edi, edi
0x14001574f  jz      short loc_140015760
0x140015751  cmp     byte ptr [rax+1Fh], 0
0x140015755  jz      short loc_140015760
0x140015757  mov     edi, r13d
0x14001575a  add     r14, 8
0x14001575e  jmp     short loc_140015714
0x140015760  xor     edi, edi
0x140015762  test    esi, esi
0x140015764  jz      short loc_14001576F
0x140015766  test    edi, edi
0x140015768  jz      short loc_14001576F
0x14001576a  mov     esi, r13d
0x14001576d  jmp     short loc_140015771
0x14001576f  xor     esi, esi
0x140015771  mov     edx, ebx
0x140015773  and     edx, 0FFFFFFFEh
0x140015776  or      edx, esi
0x140015778  test    ebp, ebp
0x14001577a  jz      short loc_140015784
0x14001577c  test    edi, edi
0x14001577e  jnz     short loc_140015784
0x140015780  btr     edx, 0Ah
0x140015784  mov     eax, ebx
0x140015786  mov     ecx, edx
0x140015788  and     eax, r13d
0x14001578b  and     ecx, 0FFFFFFCFh
0x14001578e  cmp     eax, esi
0x140015790  mov     eax, ebx
0x140015792  cmovz   ecx, edx
0x140015795  btr     ecx, 9
0x140015799  mov     dword ptr [rsp+48h+arg_0], ecx
0x14001579d  lock cmpxchg [r15], ecx
0x1400157a2  jz      short loc_1400157A8
0x1400157a4  mov     ebx, eax
0x1400157a6  jmp     short loc_140015771
0x1400157a8  mov     rax, [rsp+48h+arg_0]
0x1400157ad  mov     rbx, [rsp+48h+arg_8]
0x1400157b2  mov     rbp, [rsp+48h+arg_10]
0x1400157b7  add     rsp, 20h
0x1400157bb  pop     r15
0x1400157bd  pop     r14
0x1400157bf  pop     r13
0x1400157c1  pop     rdi
0x1400157c2  pop     rsi
0x1400157c3  retn
```
