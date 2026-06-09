# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x18001d1e0`
- end: `0x18001d2ed`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d090`
- `0x18001d1a4`

## callees

- `0x18001d1a4`
- `0x18001d1e0`

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
0x18001d1e0  mov     [rsp+arg_8], rbx
0x18001d1e5  mov     [rsp+arg_10], rbp
0x18001d1ea  push    rsi
0x18001d1eb  push    rdi
0x18001d1ec  push    r13
0x18001d1ee  push    r14
0x18001d1f0  push    r15
0x18001d1f2  sub     rsp, 20h
0x18001d1f6  mov     r13d, 1
0x18001d1fc  mov     [rsp+48h+arg_0], 0
0x18001d205  mov     esi, edx
0x18001d207  mov     r15, rcx
0x18001d20a  shr     esi, 6
0x18001d20d  mov     ecx, 0C00h
0x18001d212  mov     eax, edx
0x18001d214  and     esi, r13d
0x18001d217  and     eax, ecx
0x18001d219  mov     rbx, rdx
0x18001d21c  mov     edi, r13d
0x18001d21f  cmp     eax, ecx
0x18001d221  jz      short loc_18001D22B
0x18001d223  test    esi, esi
0x18001d225  jnz     short loc_18001D22B
0x18001d227  xor     ebp, ebp
0x18001d229  jmp     short loc_18001D299
0x18001d22b  mov     r14, [r8+20h]
0x18001d22f  xor     ebp, ebp
0x18001d231  cmp     eax, ecx
0x18001d233  setz    bpl
0x18001d237  test    r14, r14
0x18001d23a  jz      short loc_18001D299
0x18001d23c  mov     rax, [r14]
0x18001d23f  test    rax, rax
0x18001d242  jz      short loc_18001D28A
0x18001d244  cmp     byte ptr [rax+1Eh], 0
0x18001d248  jnz     short loc_18001D275
0x18001d24a  cmp     byte ptr [rax+1Dh], 0
0x18001d24e  jnz     short loc_18001D275
0x18001d250  mov     rcx, [rax]
0x18001d253  mov     rdx, rax
0x18001d256  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x18001d25b  test    edi, edi
0x18001d25d  jz      short loc_18001D269
0x18001d25f  test    r13b, al
0x18001d262  jz      short loc_18001D269
0x18001d264  mov     edi, r13d
0x18001d267  jmp     short loc_18001D26B
0x18001d269  xor     edi, edi
0x18001d26b  add     r14, 8
0x18001d26f  test    edi, edi
0x18001d271  jnz     short loc_18001D23C
0x18001d273  jmp     short loc_18001D28A
0x18001d275  test    edi, edi
0x18001d277  jz      short loc_18001D288
0x18001d279  cmp     byte ptr [rax+1Fh], 0
0x18001d27d  jz      short loc_18001D288
0x18001d27f  mov     edi, r13d
0x18001d282  add     r14, 8
0x18001d286  jmp     short loc_18001D23C
0x18001d288  xor     edi, edi
0x18001d28a  test    esi, esi
0x18001d28c  jz      short loc_18001D297
0x18001d28e  test    edi, edi
0x18001d290  jz      short loc_18001D297
0x18001d292  mov     esi, r13d
0x18001d295  jmp     short loc_18001D299
0x18001d297  xor     esi, esi
0x18001d299  mov     edx, ebx
0x18001d29b  and     edx, 0FFFFFFFEh
0x18001d29e  or      edx, esi
0x18001d2a0  test    ebp, ebp
0x18001d2a2  jz      short loc_18001D2AC
0x18001d2a4  test    edi, edi
0x18001d2a6  jnz     short loc_18001D2AC
0x18001d2a8  btr     edx, 0Ah
0x18001d2ac  mov     eax, ebx
0x18001d2ae  mov     ecx, edx
0x18001d2b0  and     eax, r13d
0x18001d2b3  and     ecx, 0FFFFFFCFh
0x18001d2b6  cmp     eax, esi
0x18001d2b8  mov     eax, ebx
0x18001d2ba  cmovz   ecx, edx
0x18001d2bd  btr     ecx, 9
0x18001d2c1  mov     dword ptr [rsp+48h+arg_0], ecx
0x18001d2c5  lock cmpxchg [r15], ecx
0x18001d2ca  jz      short loc_18001D2D0
0x18001d2cc  mov     ebx, eax
0x18001d2ce  jmp     short loc_18001D299
0x18001d2d0  mov     rax, [rsp+48h+arg_0]
0x18001d2d5  mov     rbx, [rsp+48h+arg_8]
0x18001d2da  mov     rbp, [rsp+48h+arg_10]
0x18001d2df  add     rsp, 20h
0x18001d2e3  pop     r15
0x18001d2e5  pop     r14
0x18001d2e7  pop     r13
0x18001d2e9  pop     rdi
0x18001d2ea  pop     rsi
0x18001d2eb  retn
```
