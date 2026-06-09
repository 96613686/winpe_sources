# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14002a268`
- end: `0x14002a375`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002a22c`

## callees

- `0x14002a22c`
- `0x14002a268`

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
0x14002a268  mov     [rsp+arg_8], rbx
0x14002a26d  mov     [rsp+arg_10], rbp
0x14002a272  push    rsi
0x14002a273  push    rdi
0x14002a274  push    r13
0x14002a276  push    r14
0x14002a278  push    r15
0x14002a27a  sub     rsp, 20h
0x14002a27e  mov     r13d, 1
0x14002a284  mov     [rsp+48h+arg_0], 0
0x14002a28d  mov     esi, edx
0x14002a28f  mov     r15, rcx
0x14002a292  shr     esi, 6
0x14002a295  mov     ecx, 0C00h
0x14002a29a  mov     eax, edx
0x14002a29c  and     esi, r13d
0x14002a29f  and     eax, ecx
0x14002a2a1  mov     rbx, rdx
0x14002a2a4  mov     edi, r13d
0x14002a2a7  cmp     eax, ecx
0x14002a2a9  jz      short loc_14002A2B3
0x14002a2ab  test    esi, esi
0x14002a2ad  jnz     short loc_14002A2B3
0x14002a2af  xor     ebp, ebp
0x14002a2b1  jmp     short loc_14002A321
0x14002a2b3  mov     r14, [r8+20h]
0x14002a2b7  xor     ebp, ebp
0x14002a2b9  cmp     eax, ecx
0x14002a2bb  setz    bpl
0x14002a2bf  test    r14, r14
0x14002a2c2  jz      short loc_14002A321
0x14002a2c4  mov     rax, [r14]
0x14002a2c7  test    rax, rax
0x14002a2ca  jz      short loc_14002A312
0x14002a2cc  cmp     byte ptr [rax+1Eh], 0
0x14002a2d0  jnz     short loc_14002A2FD
0x14002a2d2  cmp     byte ptr [rax+1Dh], 0
0x14002a2d6  jnz     short loc_14002A2FD
0x14002a2d8  mov     rcx, [rax]
0x14002a2db  mov     rdx, rax
0x14002a2de  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14002a2e3  test    edi, edi
0x14002a2e5  jz      short loc_14002A2F1
0x14002a2e7  test    r13b, al
0x14002a2ea  jz      short loc_14002A2F1
0x14002a2ec  mov     edi, r13d
0x14002a2ef  jmp     short loc_14002A2F3
0x14002a2f1  xor     edi, edi
0x14002a2f3  add     r14, 8
0x14002a2f7  test    edi, edi
0x14002a2f9  jnz     short loc_14002A2C4
0x14002a2fb  jmp     short loc_14002A312
0x14002a2fd  test    edi, edi
0x14002a2ff  jz      short loc_14002A310
0x14002a301  cmp     byte ptr [rax+1Fh], 0
0x14002a305  jz      short loc_14002A310
0x14002a307  mov     edi, r13d
0x14002a30a  add     r14, 8
0x14002a30e  jmp     short loc_14002A2C4
0x14002a310  xor     edi, edi
0x14002a312  test    esi, esi
0x14002a314  jz      short loc_14002A31F
0x14002a316  test    edi, edi
0x14002a318  jz      short loc_14002A31F
0x14002a31a  mov     esi, r13d
0x14002a31d  jmp     short loc_14002A321
0x14002a31f  xor     esi, esi
0x14002a321  mov     edx, ebx
0x14002a323  and     edx, 0FFFFFFFEh
0x14002a326  or      edx, esi
0x14002a328  test    ebp, ebp
0x14002a32a  jz      short loc_14002A334
0x14002a32c  test    edi, edi
0x14002a32e  jnz     short loc_14002A334
0x14002a330  btr     edx, 0Ah
0x14002a334  mov     eax, ebx
0x14002a336  mov     ecx, edx
0x14002a338  and     eax, r13d
0x14002a33b  and     ecx, 0FFFFFFCFh
0x14002a33e  cmp     eax, esi
0x14002a340  mov     eax, ebx
0x14002a342  cmovz   ecx, edx
0x14002a345  btr     ecx, 9
0x14002a349  mov     dword ptr [rsp+48h+arg_0], ecx
0x14002a34d  lock cmpxchg [r15], ecx
0x14002a352  jz      short loc_14002A358
0x14002a354  mov     ebx, eax
0x14002a356  jmp     short loc_14002A321
0x14002a358  mov     rax, [rsp+48h+arg_0]
0x14002a35d  mov     rbx, [rsp+48h+arg_8]
0x14002a362  mov     rbp, [rsp+48h+arg_10]
0x14002a367  add     rsp, 20h
0x14002a36b  pop     r15
0x14002a36d  pop     r14
0x14002a36f  pop     r13
0x14002a371  pop     rdi
0x14002a372  pop     rsi
0x14002a373  retn
```
