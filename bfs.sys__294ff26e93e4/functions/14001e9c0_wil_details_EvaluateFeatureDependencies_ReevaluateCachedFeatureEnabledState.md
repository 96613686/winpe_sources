# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14001e9c0`
- end: `0x14001eacd`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001e984`

## callees

- `0x14001e984`
- `0x14001e9c0`

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
0x14001e9c0  mov     [rsp+arg_8], rbx
0x14001e9c5  mov     [rsp+arg_10], rbp
0x14001e9ca  push    rsi
0x14001e9cb  push    rdi
0x14001e9cc  push    r13
0x14001e9ce  push    r14
0x14001e9d0  push    r15
0x14001e9d2  sub     rsp, 20h
0x14001e9d6  mov     r13d, 1
0x14001e9dc  mov     [rsp+48h+arg_0], 0
0x14001e9e5  mov     esi, edx
0x14001e9e7  mov     r15, rcx
0x14001e9ea  shr     esi, 6
0x14001e9ed  mov     ecx, 0C00h
0x14001e9f2  mov     eax, edx
0x14001e9f4  and     esi, r13d
0x14001e9f7  and     eax, ecx
0x14001e9f9  mov     rbx, rdx
0x14001e9fc  mov     edi, r13d
0x14001e9ff  cmp     eax, ecx
0x14001ea01  jz      short loc_14001EA0B
0x14001ea03  test    esi, esi
0x14001ea05  jnz     short loc_14001EA0B
0x14001ea07  xor     ebp, ebp
0x14001ea09  jmp     short loc_14001EA79
0x14001ea0b  mov     r14, [r8+20h]
0x14001ea0f  xor     ebp, ebp
0x14001ea11  cmp     eax, ecx
0x14001ea13  setz    bpl
0x14001ea17  test    r14, r14
0x14001ea1a  jz      short loc_14001EA79
0x14001ea1c  mov     rax, [r14]
0x14001ea1f  test    rax, rax
0x14001ea22  jz      short loc_14001EA6A
0x14001ea24  cmp     byte ptr [rax+1Eh], 0
0x14001ea28  jnz     short loc_14001EA55
0x14001ea2a  cmp     byte ptr [rax+1Dh], 0
0x14001ea2e  jnz     short loc_14001EA55
0x14001ea30  mov     rcx, [rax]
0x14001ea33  mov     rdx, rax
0x14001ea36  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14001ea3b  test    edi, edi
0x14001ea3d  jz      short loc_14001EA49
0x14001ea3f  test    r13b, al
0x14001ea42  jz      short loc_14001EA49
0x14001ea44  mov     edi, r13d
0x14001ea47  jmp     short loc_14001EA4B
0x14001ea49  xor     edi, edi
0x14001ea4b  add     r14, 8
0x14001ea4f  test    edi, edi
0x14001ea51  jnz     short loc_14001EA1C
0x14001ea53  jmp     short loc_14001EA6A
0x14001ea55  test    edi, edi
0x14001ea57  jz      short loc_14001EA68
0x14001ea59  cmp     byte ptr [rax+1Fh], 0
0x14001ea5d  jz      short loc_14001EA68
0x14001ea5f  mov     edi, r13d
0x14001ea62  add     r14, 8
0x14001ea66  jmp     short loc_14001EA1C
0x14001ea68  xor     edi, edi
0x14001ea6a  test    esi, esi
0x14001ea6c  jz      short loc_14001EA77
0x14001ea6e  test    edi, edi
0x14001ea70  jz      short loc_14001EA77
0x14001ea72  mov     esi, r13d
0x14001ea75  jmp     short loc_14001EA79
0x14001ea77  xor     esi, esi
0x14001ea79  mov     edx, ebx
0x14001ea7b  and     edx, 0FFFFFFFEh
0x14001ea7e  or      edx, esi
0x14001ea80  test    ebp, ebp
0x14001ea82  jz      short loc_14001EA8C
0x14001ea84  test    edi, edi
0x14001ea86  jnz     short loc_14001EA8C
0x14001ea88  btr     edx, 0Ah
0x14001ea8c  mov     eax, ebx
0x14001ea8e  mov     ecx, edx
0x14001ea90  and     eax, r13d
0x14001ea93  and     ecx, 0FFFFFFCFh
0x14001ea96  cmp     eax, esi
0x14001ea98  mov     eax, ebx
0x14001ea9a  cmovz   ecx, edx
0x14001ea9d  btr     ecx, 9
0x14001eaa1  mov     dword ptr [rsp+48h+arg_0], ecx
0x14001eaa5  lock cmpxchg [r15], ecx
0x14001eaaa  jz      short loc_14001EAB0
0x14001eaac  mov     ebx, eax
0x14001eaae  jmp     short loc_14001EA79
0x14001eab0  mov     rax, [rsp+48h+arg_0]
0x14001eab5  mov     rbx, [rsp+48h+arg_8]
0x14001eaba  mov     rbp, [rsp+48h+arg_10]
0x14001eabf  add     rsp, 20h
0x14001eac3  pop     r15
0x14001eac5  pop     r14
0x14001eac7  pop     r13
0x14001eac9  pop     rdi
0x14001eaca  pop     rsi
0x14001eacb  retn
```
