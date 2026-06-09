# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140007a60`
- end: `0x140007b31`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007970`
- `0x140007a60`

## callees

- `0x140007a60`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2)
{
  unsigned __int32 v2; // esi
  int v4; // ebx
  __int64 *v5; // rdi
  __int64 v6; // rax
  unsigned __int32 v7; // eax
  unsigned int v8; // r8d
  __int64 v10; // [rsp+50h] [rbp+8h]

  v2 = *a1;
  v10 = *(unsigned int *)a1;
  if ( (*a1 & 0x200) != 0 )
  {
    HIDWORD(v10) = 0;
    v4 = (v2 >> 6) & 1;
    if ( v4 )
    {
      v5 = *(__int64 **)(a2 + 32);
      if ( v5 )
      {
        while ( 1 )
        {
          v6 = *v5;
          if ( !*v5 )
            break;
          if ( *(_BYTE *)(v6 + 30) || *(_BYTE *)(v6 + 29) )
          {
            if ( !*(_BYTE *)(v6 + 31) )
            {
              v4 = 0;
              goto LABEL_12;
            }
            v4 = 1;
            ++v5;
          }
          else
          {
            v4 = (wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_QWORD *)v6, *v5++) & 1) != 0;
            if ( !v4 )
              goto LABEL_12;
          }
        }
      }
    }
    do
    {
LABEL_12:
      v7 = v2;
      v8 = v4 & 0xFFFFFFCF | v2 & 0xFFFFFFCE;
      if ( (v2 & 1) == v4 )
        v8 = v4 | v2 & 0xFFFFFFFE;
      LODWORD(v10) = v8 & 0xFFFFFDFF;
      v2 = _InterlockedCompareExchange(a1, v8 & 0xFFFFFDFF, v2);
    }
    while ( v7 != v2 );
  }
  return v10;
}

```

## disassembly

```asm
0x140007a60  push    rbx
0x140007a62  push    rsi
0x140007a63  push    rdi
0x140007a64  push    r14
0x140007a66  sub     rsp, 28h
0x140007a6a  mov     esi, [rcx]
0x140007a6c  mov     r14, rcx
0x140007a6f  mov     [rsp+48h+arg_0], 0
0x140007a78  mov     dword ptr [rsp+48h+arg_0], esi
0x140007a7c  bt      esi, 9
0x140007a80  jnb     loc_140007B21
0x140007a86  mov     ebx, esi
0x140007a88  mov     [rsp+48h+arg_0], 0
0x140007a91  shr     ebx, 6
0x140007a94  and     ebx, 1
0x140007a97  jz      short loc_140007AF3
0x140007a99  mov     rdi, [rdx+20h]
0x140007a9d  test    rdi, rdi
0x140007aa0  jz      short loc_140007AF3
0x140007aa2  mov     rax, [rdi]
0x140007aa5  test    rax, rax
0x140007aa8  jz      short loc_140007AF3
0x140007aaa  cmp     byte ptr [rax+1Eh], 0
0x140007aae  jnz     short loc_140007ADC
0x140007ab0  cmp     byte ptr [rax+1Dh], 0
0x140007ab4  jnz     short loc_140007ADC
0x140007ab6  mov     rcx, [rax]
0x140007ab9  mov     rdx, rax
0x140007abc  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140007ac1  test    ebx, ebx
0x140007ac3  jz      short loc_140007AD0
0x140007ac5  test    al, 1
0x140007ac7  jz      short loc_140007AD0
0x140007ac9  mov     ebx, 1
0x140007ace  jmp     short loc_140007AD2
0x140007ad0  xor     ebx, ebx
0x140007ad2  add     rdi, 8
0x140007ad6  test    ebx, ebx
0x140007ad8  jnz     short loc_140007AA2
0x140007ada  jmp     short loc_140007AF3
0x140007adc  test    ebx, ebx
0x140007ade  jz      short loc_140007AF1
0x140007ae0  cmp     byte ptr [rax+1Fh], 0
0x140007ae4  jz      short loc_140007AF1
0x140007ae6  mov     ebx, 1
0x140007aeb  add     rdi, 8
0x140007aef  jmp     short loc_140007AA2
0x140007af1  xor     ebx, ebx
0x140007af3  mov     edx, esi
0x140007af5  mov     ecx, esi
0x140007af7  and     edx, 0FFFFFFFEh
0x140007afa  and     ecx, 1
0x140007afd  or      edx, ebx
0x140007aff  mov     eax, esi
0x140007b01  mov     r8d, edx
0x140007b04  and     r8d, 0FFFFFFCFh
0x140007b08  cmp     ecx, ebx
0x140007b0a  cmovz   r8d, edx
0x140007b0e  btr     r8d, 9
0x140007b13  mov     dword ptr [rsp+48h+arg_0], r8d
0x140007b18  lock cmpxchg [r14], r8d
0x140007b1d  mov     esi, eax
0x140007b1f  jnz     short loc_140007AF3
0x140007b21  mov     rax, [rsp+48h+arg_0]
0x140007b26  add     rsp, 28h
0x140007b2a  pop     r14
0x140007b2c  pop     rdi
0x140007b2d  pop     rsi
0x140007b2e  pop     rbx
0x140007b2f  retn
```
