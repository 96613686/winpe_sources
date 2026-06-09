# McGenControlCallbackV2

- ea: `0x180020dc0`
- end: `0x180020ec0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002174`
- `0x180020dc0`

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
0x180020dc0  push    rbx
0x180020dc2  sub     rsp, 20h
0x180020dc6  mov     r10, [rsp+28h+CallbackContext]
0x180020dcb  xor     ebx, ebx
0x180020dcd  test    r10, r10
0x180020dd0  jz      loc_180020EBA
0x180020dd6  test    edx, edx
0x180020dd8  jz      loc_180020E7F
0x180020dde  cmp     edx, 1
0x180020de1  jnz     loc_180020EBA
0x180020de7  mov     rax, [rsp+28h+MatchAllKeyword]
0x180020dec  mov     [r10+28h], r8b
0x180020df0  mov     r8d, ebx
0x180020df3  mov     [r10+18h], rax
0x180020df7  mov     [r10+10h], r9
0x180020dfb  mov     [r10+24h], edx
0x180020dff  cmp     bx, [r10+2Ah]
0x180020e04  jnb     loc_180020EBA
0x180020e0a  mov     rax, [r10+40h]
0x180020e0e  mov     cl, [r10+28h]
0x180020e12  mov     r9d, r8d
0x180020e15  cmp     [r9+rax], cl
0x180020e19  jbe     short loc_180020E1F
0x180020e1b  test    cl, cl
0x180020e1d  jnz     short loc_180020E3F
0x180020e1f  mov     rax, [r10+38h]
0x180020e23  mov     rcx, [rax+r9*8]
0x180020e27  test    rcx, rcx
0x180020e2a  jz      short loc_180020E44
0x180020e2c  test    [r10+10h], rcx
0x180020e30  jz      short loc_180020E3F
0x180020e32  mov     rax, [r10+18h]
0x180020e36  and     rax, rcx
0x180020e39  cmp     rax, [r10+18h]
0x180020e3d  jz      short loc_180020E44
0x180020e3f  mov     r11b, bl
0x180020e42  jmp     short loc_180020E47
0x180020e44  mov     r11b, 1
0x180020e47  mov     rax, [r10+30h]
0x180020e4b  mov     ecx, r8d
0x180020e4e  shr     r9, 5
0x180020e52  mov     edx, 1
0x180020e57  shl     edx, cl
0x180020e59  lea     rcx, [rax+r9*4]
0x180020e5d  test    r11b, r11b
0x180020e60  jz      short loc_180020E66
0x180020e62  or      edx, [rcx]
0x180020e64  jmp     short loc_180020E6A
0x180020e66  not     edx
0x180020e68  and     edx, [rcx]
0x180020e6a  mov     [rcx], edx
0x180020e6c  inc     r8d
0x180020e6f  movzx   eax, word ptr [r10+2Ah]
0x180020e74  cmp     r8d, eax
0x180020e77  jb      short loc_180020E0A
0x180020e79  add     rsp, 20h
0x180020e7d  pop     rbx
0x180020e7e  retn
0x180020e7f  mov     [r10+24h], ebx
0x180020e83  mov     [r10+28h], bl
0x180020e87  mov     [r10+10h], rbx
0x180020e8b  mov     [r10+18h], rbx
0x180020e8f  cmp     [r10+2Ah], bx
0x180020e94  jbe     short loc_180020EBA
0x180020e96  movzx   eax, word ptr [r10+2Ah]
0x180020e9b  mov     rcx, [r10+30h]; void *
0x180020e9f  dec     eax
0x180020ea1  cdq
0x180020ea2  and     edx, 1Fh
0x180020ea5  add     eax, edx
0x180020ea7  xor     edx, edx; Val
0x180020ea9  sar     eax, 5
0x180020eac  inc     eax
0x180020eae  movsxd  r8, eax
0x180020eb1  shl     r8, 2; Size
0x180020eb5  call    memset_0
0x180020eba  add     rsp, 20h
0x180020ebe  pop     rbx
0x180020ebf  retn
```
