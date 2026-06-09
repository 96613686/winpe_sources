# McGenControlCallbackV2

- ea: `0x180006260`
- end: `0x180006356`
- name: `McGenControlCallbackV2`
- size: `246`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006260`
- `0x18000a192`

## pseudocode

```c
void __fastcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        unsigned __int16 *CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // r9
  _DWORD *v10; // rdx
  _DWORD *v11; // rdx
  int v12; // eax

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < CallbackContext[21]; ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          if ( (*(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8)
            && ((v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7)) == 0
             || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
             && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3)) )
          {
            v11 = (_DWORD *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
            *v11 |= 1 << v7;
          }
          else
          {
            v10 = (_DWORD *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
            *v10 &= ~(1 << v7);
          }
        }
      }
    }
    else
    {
      v12 = CallbackContext[21];
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v12 )
        memset_0(*((void **)CallbackContext + 6), 0, 4LL * ((v12 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x180006260  mov     r10, [rsp+CallbackContext]
0x180006265  test    r10, r10
0x180006268  jz      locret_180006355
0x18000626e  test    edx, edx
0x180006270  jz      loc_180006319
0x180006276  cmp     edx, 1
0x180006279  jnz     locret_180006355
0x18000627f  mov     rax, [rsp+MatchAllKeyword]
0x180006284  mov     [r10+28h], r8b
0x180006288  xor     r8d, r8d
0x18000628b  mov     [r10+10h], r9
0x18000628f  mov     [r10+18h], rax
0x180006293  mov     [r10+24h], edx
0x180006297  cmp     r8w, [r10+2Ah]
0x18000629c  jnb     locret_180006355
0x1800062a2  mov     rax, [r10+40h]
0x1800062a6  movzx   ecx, byte ptr [r10+28h]
0x1800062ab  mov     edx, r8d
0x1800062ae  cmp     [rdx+rax], cl
0x1800062b1  jbe     short loc_1800062B7
0x1800062b3  test    cl, cl
0x1800062b5  jnz     short loc_1800062D7
0x1800062b7  mov     rax, [r10+38h]
0x1800062bb  mov     r9, [rax+rdx*8]
0x1800062bf  test    r9, r9
0x1800062c2  jz      short loc_1800062F3
0x1800062c4  test    [r10+10h], r9
0x1800062c8  jz      short loc_1800062D7
0x1800062ca  mov     rax, [r10+18h]
0x1800062ce  and     rax, r9
0x1800062d1  cmp     rax, [r10+18h]
0x1800062d5  jz      short loc_1800062F3
0x1800062d7  mov     rax, [r10+30h]
0x1800062db  mov     ecx, r8d
0x1800062de  shr     rdx, 5
0x1800062e2  lea     rdx, [rax+rdx*4]
0x1800062e6  mov     eax, 1
0x1800062eb  shl     eax, cl
0x1800062ed  not     eax
0x1800062ef  and     [rdx], eax
0x1800062f1  jmp     short loc_18000630B
0x1800062f3  mov     rax, [r10+30h]
0x1800062f7  mov     ecx, r8d
0x1800062fa  shr     rdx, 5
0x1800062fe  lea     rdx, [rax+rdx*4]
0x180006302  mov     eax, 1
0x180006307  shl     eax, cl
0x180006309  or      [rdx], eax
0x18000630b  movzx   eax, word ptr [r10+2Ah]
0x180006310  inc     r8d
0x180006313  cmp     r8d, eax
0x180006316  jb      short loc_1800062A2
0x180006318  retn
0x180006319  movzx   eax, word ptr [r10+2Ah]
0x18000631e  xor     r8d, r8d
0x180006321  mov     [r10+24h], r8d
0x180006325  mov     [r10+28h], r8b
0x180006329  mov     [r10+10h], r8
0x18000632d  mov     [r10+18h], r8
0x180006331  test    ax, ax
0x180006334  jz      short locret_180006355
0x180006336  mov     rcx, [r10+30h]; void *
0x18000633a  dec     eax
0x18000633c  cdq
0x18000633d  and     edx, 1Fh
0x180006340  add     eax, edx
0x180006342  xor     edx, edx; Val
0x180006344  sar     eax, 5
0x180006347  inc     eax
0x180006349  movsxd  r8, eax
0x18000634c  shl     r8, 2; Size
0x180006350  jmp     memset_0
0x180006355  retn
```
