# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140021468`
- end: `0x140021575`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002142c`

## callees

- `0x14002142c`
- `0x140021468`

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
0x140021468  mov     [rsp+arg_8], rbx
0x14002146d  mov     [rsp+arg_10], rbp
0x140021472  push    rsi
0x140021473  push    rdi
0x140021474  push    r13
0x140021476  push    r14
0x140021478  push    r15
0x14002147a  sub     rsp, 20h
0x14002147e  mov     r13d, 1
0x140021484  mov     [rsp+48h+arg_0], 0
0x14002148d  mov     esi, edx
0x14002148f  mov     r15, rcx
0x140021492  shr     esi, 6
0x140021495  mov     ecx, 0C00h
0x14002149a  mov     eax, edx
0x14002149c  and     esi, r13d
0x14002149f  and     eax, ecx
0x1400214a1  mov     rbx, rdx
0x1400214a4  mov     edi, r13d
0x1400214a7  cmp     eax, ecx
0x1400214a9  jz      short loc_1400214B3
0x1400214ab  test    esi, esi
0x1400214ad  jnz     short loc_1400214B3
0x1400214af  xor     ebp, ebp
0x1400214b1  jmp     short loc_140021521
0x1400214b3  mov     r14, [r8+20h]
0x1400214b7  xor     ebp, ebp
0x1400214b9  cmp     eax, ecx
0x1400214bb  setz    bpl
0x1400214bf  test    r14, r14
0x1400214c2  jz      short loc_140021521
0x1400214c4  mov     rax, [r14]
0x1400214c7  test    rax, rax
0x1400214ca  jz      short loc_140021512
0x1400214cc  cmp     byte ptr [rax+1Eh], 0
0x1400214d0  jnz     short loc_1400214FD
0x1400214d2  cmp     byte ptr [rax+1Dh], 0
0x1400214d6  jnz     short loc_1400214FD
0x1400214d8  mov     rcx, [rax]
0x1400214db  mov     rdx, rax
0x1400214de  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400214e3  test    edi, edi
0x1400214e5  jz      short loc_1400214F1
0x1400214e7  test    r13b, al
0x1400214ea  jz      short loc_1400214F1
0x1400214ec  mov     edi, r13d
0x1400214ef  jmp     short loc_1400214F3
0x1400214f1  xor     edi, edi
0x1400214f3  add     r14, 8
0x1400214f7  test    edi, edi
0x1400214f9  jnz     short loc_1400214C4
0x1400214fb  jmp     short loc_140021512
0x1400214fd  test    edi, edi
0x1400214ff  jz      short loc_140021510
0x140021501  cmp     byte ptr [rax+1Fh], 0
0x140021505  jz      short loc_140021510
0x140021507  mov     edi, r13d
0x14002150a  add     r14, 8
0x14002150e  jmp     short loc_1400214C4
0x140021510  xor     edi, edi
0x140021512  test    esi, esi
0x140021514  jz      short loc_14002151F
0x140021516  test    edi, edi
0x140021518  jz      short loc_14002151F
0x14002151a  mov     esi, r13d
0x14002151d  jmp     short loc_140021521
0x14002151f  xor     esi, esi
0x140021521  mov     edx, ebx
0x140021523  and     edx, 0FFFFFFFEh
0x140021526  or      edx, esi
0x140021528  test    ebp, ebp
0x14002152a  jz      short loc_140021534
0x14002152c  test    edi, edi
0x14002152e  jnz     short loc_140021534
0x140021530  btr     edx, 0Ah
0x140021534  mov     eax, ebx
0x140021536  mov     ecx, edx
0x140021538  and     eax, r13d
0x14002153b  and     ecx, 0FFFFFFCFh
0x14002153e  cmp     eax, esi
0x140021540  mov     eax, ebx
0x140021542  cmovz   ecx, edx
0x140021545  btr     ecx, 9
0x140021549  mov     dword ptr [rsp+48h+arg_0], ecx
0x14002154d  lock cmpxchg [r15], ecx
0x140021552  jz      short loc_140021558
0x140021554  mov     ebx, eax
0x140021556  jmp     short loc_140021521
0x140021558  mov     rax, [rsp+48h+arg_0]
0x14002155d  mov     rbx, [rsp+48h+arg_8]
0x140021562  mov     rbp, [rsp+48h+arg_10]
0x140021567  add     rsp, 20h
0x14002156b  pop     r15
0x14002156d  pop     r14
0x14002156f  pop     r13
0x140021571  pop     rdi
0x140021572  pop     rsi
0x140021573  retn
```
