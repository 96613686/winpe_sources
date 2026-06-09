# McGenControlCallbackV2

- ea: `0x1800063e0`
- end: `0x1800064e2`
- name: `McGenControlCallbackV2`
- size: `258`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001fd4`
- `0x1800063e0`

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
  __int64 v9; // rcx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // edx

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < CallbackContext[21]; ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          v10 = 0;
          if ( *(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8 )
          {
            v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7);
            if ( !v9
              || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3) )
            {
              v10 = 1;
            }
          }
          v11 = 1 << v7;
          v12 = (int *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
          if ( v10 )
            v13 = *v12 | v11;
          else
            v13 = *v12 & ~v11;
          *v12 = v13;
        }
      }
    }
    else
    {
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( CallbackContext[21] )
        memset_0(*((void **)CallbackContext + 6), 0, 4LL * ((CallbackContext[21] - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x1800063e0  push    rbx
0x1800063e2  sub     rsp, 20h
0x1800063e6  mov     r10, [rsp+28h+CallbackContext]
0x1800063eb  xor     ebx, ebx
0x1800063ed  test    r10, r10
0x1800063f0  jz      loc_1800064DB
0x1800063f6  test    edx, edx
0x1800063f8  jz      loc_1800064A0
0x1800063fe  cmp     edx, 1
0x180006401  jnz     loc_1800064DB
0x180006407  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000640c  mov     [r10+28h], r8b
0x180006410  mov     r8d, ebx
0x180006413  mov     [r10+18h], rax
0x180006417  mov     [r10+10h], r9
0x18000641b  mov     [r10+24h], edx
0x18000641f  cmp     bx, [r10+2Ah]
0x180006424  jnb     loc_1800064DB
0x18000642a  mov     rax, [r10+40h]
0x18000642e  mov     cl, [r10+28h]
0x180006432  mov     r9d, r8d
0x180006435  cmp     [r9+rax], cl
0x180006439  jbe     short loc_18000643F
0x18000643b  test    cl, cl
0x18000643d  jnz     short loc_18000645F
0x18000643f  mov     rax, [r10+38h]
0x180006443  mov     rcx, [rax+r9*8]
0x180006447  test    rcx, rcx
0x18000644a  jz      short loc_180006464
0x18000644c  test    [r10+10h], rcx
0x180006450  jz      short loc_18000645F
0x180006452  mov     rax, [r10+18h]
0x180006456  and     rax, rcx
0x180006459  cmp     rax, [r10+18h]
0x18000645d  jz      short loc_180006464
0x18000645f  mov     r11b, bl
0x180006462  jmp     short loc_180006467
0x180006464  mov     r11b, 1
0x180006467  mov     rax, [r10+30h]
0x18000646b  mov     ecx, r8d
0x18000646e  shr     r9, 5
0x180006472  mov     edx, 1
0x180006477  shl     edx, cl
0x180006479  lea     rcx, [rax+r9*4]
0x18000647d  test    r11b, r11b
0x180006480  jz      short loc_180006486
0x180006482  or      edx, [rcx]
0x180006484  jmp     short loc_18000648A
0x180006486  not     edx
0x180006488  and     edx, [rcx]
0x18000648a  mov     [rcx], edx
0x18000648c  inc     r8d
0x18000648f  movzx   eax, word ptr [r10+2Ah]
0x180006494  cmp     r8d, eax
0x180006497  jb      short loc_18000642A
0x180006499  add     rsp, 20h
0x18000649d  pop     rbx
0x18000649e  retn
0x1800064a0  mov     [r10+24h], ebx
0x1800064a4  mov     [r10+28h], bl
0x1800064a8  mov     [r10+10h], rbx
0x1800064ac  mov     [r10+18h], rbx
0x1800064b0  cmp     [r10+2Ah], bx
0x1800064b5  jbe     short loc_1800064DB
0x1800064b7  movzx   eax, word ptr [r10+2Ah]
0x1800064bc  mov     rcx, [r10+30h]; void *
0x1800064c0  dec     eax
0x1800064c2  cdq
0x1800064c3  and     edx, 1Fh
0x1800064c6  add     eax, edx
0x1800064c8  xor     edx, edx; Val
0x1800064ca  sar     eax, 5
0x1800064cd  inc     eax
0x1800064cf  movsxd  r8, eax
0x1800064d2  shl     r8, 2; Size
0x1800064d6  call    memset_0
0x1800064db  add     rsp, 20h
0x1800064df  pop     rbx
0x1800064e0  retn
```
