# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14001e9c0`
- end: `0x14001ea76`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
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
  signed __int32 v3; // ebx
  int v5; // edi
  __int64 *v6; // rsi
  __int64 v7; // rax
  unsigned int v8; // edx
  signed __int32 v9; // eax
  __int64 v11; // [rsp+50h] [rbp+8h]

  HIDWORD(v11) = 0;
  v3 = a2;
  v5 = (a2 >> 6) & 1;
  if ( v5 )
  {
    v6 = *(__int64 **)(a3 + 32);
    if ( v6 )
    {
      while ( 1 )
      {
        v7 = *v6;
        if ( !*v6 )
          break;
        if ( *(_BYTE *)(v7 + 30) || *(_BYTE *)(v7 + 29) )
        {
          if ( !*(_BYTE *)(v7 + 31) )
          {
            v5 = 0;
            goto LABEL_11;
          }
          v5 = 1;
          ++v6;
        }
        else
        {
          v5 = (wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_DWORD **)v7, *v6++) & 1) != 0;
          if ( !v5 )
            goto LABEL_11;
        }
      }
    }
  }
  while ( 1 )
  {
LABEL_11:
    v8 = v5 & 0xFFFFFFCF | v3 & 0xFFFFFFCE;
    if ( (v3 & 1) == v5 )
      v8 = v5 | v3 & 0xFFFFFFFE;
    v9 = _InterlockedCompareExchange(a1, v8 & 0xFFFFFDFF, v3);
    if ( v3 == v9 )
      break;
    v3 = v9;
  }
  LODWORD(v11) = v8 & 0xFFFFFDFF;
  return v11;
}

```

## disassembly

```asm
0x14001e9c0  push    rbx
0x14001e9c2  push    rbp
0x14001e9c3  push    rsi
0x14001e9c4  push    rdi
0x14001e9c5  sub     rsp, 28h
0x14001e9c9  mov     edi, edx
0x14001e9cb  mov     [rsp+48h+arg_0], 0
0x14001e9d4  shr     edi, 6
0x14001e9d7  mov     rbx, rdx
0x14001e9da  mov     rbp, rcx
0x14001e9dd  and     edi, 1
0x14001e9e0  jz      short loc_14001EA3C
0x14001e9e2  mov     rsi, [r8+20h]
0x14001e9e6  test    rsi, rsi
0x14001e9e9  jz      short loc_14001EA3C
0x14001e9eb  mov     rax, [rsi]
0x14001e9ee  test    rax, rax
0x14001e9f1  jz      short loc_14001EA3C
0x14001e9f3  cmp     byte ptr [rax+1Eh], 0
0x14001e9f7  jnz     short loc_14001EA25
0x14001e9f9  cmp     byte ptr [rax+1Dh], 0
0x14001e9fd  jnz     short loc_14001EA25
0x14001e9ff  mov     rcx, [rax]
0x14001ea02  mov     rdx, rax
0x14001ea05  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14001ea0a  test    edi, edi
0x14001ea0c  jz      short loc_14001EA19
0x14001ea0e  test    al, 1
0x14001ea10  jz      short loc_14001EA19
0x14001ea12  mov     edi, 1
0x14001ea17  jmp     short loc_14001EA1B
0x14001ea19  xor     edi, edi
0x14001ea1b  add     rsi, 8
0x14001ea1f  test    edi, edi
0x14001ea21  jnz     short loc_14001E9EB
0x14001ea23  jmp     short loc_14001EA3C
0x14001ea25  test    edi, edi
0x14001ea27  jz      short loc_14001EA3A
0x14001ea29  cmp     byte ptr [rax+1Fh], 0
0x14001ea2d  jz      short loc_14001EA3A
0x14001ea2f  mov     edi, 1
0x14001ea34  add     rsi, 8
0x14001ea38  jmp     short loc_14001E9EB
0x14001ea3a  xor     edi, edi
0x14001ea3c  mov     ecx, ebx
0x14001ea3e  mov     eax, ebx
0x14001ea40  and     ecx, 0FFFFFFFEh
0x14001ea43  and     eax, 1
0x14001ea46  or      ecx, edi
0x14001ea48  mov     edx, ecx
0x14001ea4a  and     edx, 0FFFFFFCFh
0x14001ea4d  cmp     eax, edi
0x14001ea4f  mov     eax, ebx
0x14001ea51  cmovz   edx, ecx
0x14001ea54  btr     edx, 9
0x14001ea58  mov     dword ptr [rsp+48h+arg_0], edx
0x14001ea5c  lock cmpxchg [rbp+0], edx
0x14001ea61  jz      short loc_14001EA67
0x14001ea63  mov     ebx, eax
0x14001ea65  jmp     short loc_14001EA3C
0x14001ea67  mov     rax, [rsp+48h+arg_0]
0x14001ea6c  add     rsp, 28h
0x14001ea70  pop     rdi
0x14001ea71  pop     rsi
0x14001ea72  pop     rbp
0x14001ea73  pop     rbx
0x14001ea74  retn
```
