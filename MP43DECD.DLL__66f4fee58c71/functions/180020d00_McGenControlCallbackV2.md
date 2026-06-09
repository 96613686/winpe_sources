# McGenControlCallbackV2

- ea: `0x180020d00`
- end: `0x180020e00`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002144`
- `0x180020d00`

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
0x180020d00  push    rbx
0x180020d02  sub     rsp, 20h
0x180020d06  mov     r10, [rsp+28h+CallbackContext]
0x180020d0b  xor     ebx, ebx
0x180020d0d  test    r10, r10
0x180020d10  jz      loc_180020DFA
0x180020d16  test    edx, edx
0x180020d18  jz      loc_180020DBF
0x180020d1e  cmp     edx, 1
0x180020d21  jnz     loc_180020DFA
0x180020d27  mov     rax, [rsp+28h+MatchAllKeyword]
0x180020d2c  mov     [r10+28h], r8b
0x180020d30  mov     r8d, ebx
0x180020d33  mov     [r10+18h], rax
0x180020d37  mov     [r10+10h], r9
0x180020d3b  mov     [r10+24h], edx
0x180020d3f  cmp     bx, [r10+2Ah]
0x180020d44  jnb     loc_180020DFA
0x180020d4a  mov     rax, [r10+40h]
0x180020d4e  mov     cl, [r10+28h]
0x180020d52  mov     r9d, r8d
0x180020d55  cmp     [r9+rax], cl
0x180020d59  jbe     short loc_180020D5F
0x180020d5b  test    cl, cl
0x180020d5d  jnz     short loc_180020D7F
0x180020d5f  mov     rax, [r10+38h]
0x180020d63  mov     rcx, [rax+r9*8]
0x180020d67  test    rcx, rcx
0x180020d6a  jz      short loc_180020D84
0x180020d6c  test    [r10+10h], rcx
0x180020d70  jz      short loc_180020D7F
0x180020d72  mov     rax, [r10+18h]
0x180020d76  and     rax, rcx
0x180020d79  cmp     rax, [r10+18h]
0x180020d7d  jz      short loc_180020D84
0x180020d7f  mov     r11b, bl
0x180020d82  jmp     short loc_180020D87
0x180020d84  mov     r11b, 1
0x180020d87  mov     rax, [r10+30h]
0x180020d8b  mov     ecx, r8d
0x180020d8e  shr     r9, 5
0x180020d92  mov     edx, 1
0x180020d97  shl     edx, cl
0x180020d99  lea     rcx, [rax+r9*4]
0x180020d9d  test    r11b, r11b
0x180020da0  jz      short loc_180020DA6
0x180020da2  or      edx, [rcx]
0x180020da4  jmp     short loc_180020DAA
0x180020da6  not     edx
0x180020da8  and     edx, [rcx]
0x180020daa  mov     [rcx], edx
0x180020dac  inc     r8d
0x180020daf  movzx   eax, word ptr [r10+2Ah]
0x180020db4  cmp     r8d, eax
0x180020db7  jb      short loc_180020D4A
0x180020db9  add     rsp, 20h
0x180020dbd  pop     rbx
0x180020dbe  retn
0x180020dbf  mov     [r10+24h], ebx
0x180020dc3  mov     [r10+28h], bl
0x180020dc7  mov     [r10+10h], rbx
0x180020dcb  mov     [r10+18h], rbx
0x180020dcf  cmp     [r10+2Ah], bx
0x180020dd4  jbe     short loc_180020DFA
0x180020dd6  movzx   eax, word ptr [r10+2Ah]
0x180020ddb  mov     rcx, [r10+30h]; void *
0x180020ddf  dec     eax
0x180020de1  cdq
0x180020de2  and     edx, 1Fh
0x180020de5  add     eax, edx
0x180020de7  xor     edx, edx; Val
0x180020de9  sar     eax, 5
0x180020dec  inc     eax
0x180020dee  movsxd  r8, eax
0x180020df1  shl     r8, 2; Size
0x180020df5  call    memset_0
0x180020dfa  add     rsp, 20h
0x180020dfe  pop     rbx
0x180020dff  retn
```
