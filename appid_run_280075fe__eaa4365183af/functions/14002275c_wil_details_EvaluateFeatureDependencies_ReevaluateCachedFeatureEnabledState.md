# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14002275c`
- end: `0x140022869`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022720`

## callees

- `0x140022720`
- `0x14002275c`

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
0x14002275c  mov     [rsp+arg_8], rbx
0x140022761  mov     [rsp+arg_10], rbp
0x140022766  push    rsi
0x140022767  push    rdi
0x140022768  push    r13
0x14002276a  push    r14
0x14002276c  push    r15
0x14002276e  sub     rsp, 20h
0x140022772  mov     r13d, 1
0x140022778  mov     [rsp+48h+arg_0], 0
0x140022781  mov     esi, edx
0x140022783  mov     r15, rcx
0x140022786  shr     esi, 6
0x140022789  mov     ecx, 0C00h
0x14002278e  mov     eax, edx
0x140022790  and     esi, r13d
0x140022793  and     eax, ecx
0x140022795  mov     rbx, rdx
0x140022798  mov     edi, r13d
0x14002279b  cmp     eax, ecx
0x14002279d  jz      short loc_1400227A7
0x14002279f  test    esi, esi
0x1400227a1  jnz     short loc_1400227A7
0x1400227a3  xor     ebp, ebp
0x1400227a5  jmp     short loc_140022815
0x1400227a7  mov     r14, [r8+20h]
0x1400227ab  xor     ebp, ebp
0x1400227ad  cmp     eax, ecx
0x1400227af  setz    bpl
0x1400227b3  test    r14, r14
0x1400227b6  jz      short loc_140022815
0x1400227b8  mov     rax, [r14]
0x1400227bb  test    rax, rax
0x1400227be  jz      short loc_140022806
0x1400227c0  cmp     byte ptr [rax+1Eh], 0
0x1400227c4  jnz     short loc_1400227F1
0x1400227c6  cmp     byte ptr [rax+1Dh], 0
0x1400227ca  jnz     short loc_1400227F1
0x1400227cc  mov     rcx, [rax]
0x1400227cf  mov     rdx, rax
0x1400227d2  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400227d7  test    edi, edi
0x1400227d9  jz      short loc_1400227E5
0x1400227db  test    r13b, al
0x1400227de  jz      short loc_1400227E5
0x1400227e0  mov     edi, r13d
0x1400227e3  jmp     short loc_1400227E7
0x1400227e5  xor     edi, edi
0x1400227e7  add     r14, 8
0x1400227eb  test    edi, edi
0x1400227ed  jnz     short loc_1400227B8
0x1400227ef  jmp     short loc_140022806
0x1400227f1  test    edi, edi
0x1400227f3  jz      short loc_140022804
0x1400227f5  cmp     byte ptr [rax+1Fh], 0
0x1400227f9  jz      short loc_140022804
0x1400227fb  mov     edi, r13d
0x1400227fe  add     r14, 8
0x140022802  jmp     short loc_1400227B8
0x140022804  xor     edi, edi
0x140022806  test    esi, esi
0x140022808  jz      short loc_140022813
0x14002280a  test    edi, edi
0x14002280c  jz      short loc_140022813
0x14002280e  mov     esi, r13d
0x140022811  jmp     short loc_140022815
0x140022813  xor     esi, esi
0x140022815  mov     edx, ebx
0x140022817  and     edx, 0FFFFFFFEh
0x14002281a  or      edx, esi
0x14002281c  test    ebp, ebp
0x14002281e  jz      short loc_140022828
0x140022820  test    edi, edi
0x140022822  jnz     short loc_140022828
0x140022824  btr     edx, 0Ah
0x140022828  mov     eax, ebx
0x14002282a  mov     ecx, edx
0x14002282c  and     eax, r13d
0x14002282f  and     ecx, 0FFFFFFCFh
0x140022832  cmp     eax, esi
0x140022834  mov     eax, ebx
0x140022836  cmovz   ecx, edx
0x140022839  btr     ecx, 9
0x14002283d  mov     dword ptr [rsp+48h+arg_0], ecx
0x140022841  lock cmpxchg [r15], ecx
0x140022846  jz      short loc_14002284C
0x140022848  mov     ebx, eax
0x14002284a  jmp     short loc_140022815
0x14002284c  mov     rax, [rsp+48h+arg_0]
0x140022851  mov     rbx, [rsp+48h+arg_8]
0x140022856  mov     rbp, [rsp+48h+arg_10]
0x14002285b  add     rsp, 20h
0x14002285f  pop     r15
0x140022861  pop     r14
0x140022863  pop     r13
0x140022865  pop     rdi
0x140022866  pop     rsi
0x140022867  retn
```
