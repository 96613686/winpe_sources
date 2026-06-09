# McGenControlCallbackV2

- ea: `0x140002b00`
- end: `0x140002bff`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002b00`
- `0x140012f22`

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
0x140002b00  push    rbx
0x140002b02  sub     rsp, 20h
0x140002b06  mov     r10, [rsp+28h+CallbackContext]
0x140002b0b  xor     ebx, ebx
0x140002b0d  test    r10, r10
0x140002b10  jz      loc_140002BF9
0x140002b16  test    edx, edx
0x140002b18  jz      loc_140002BBF
0x140002b1e  cmp     edx, 1
0x140002b21  jnz     loc_140002BF9
0x140002b27  mov     rax, [rsp+28h+MatchAllKeyword]
0x140002b2c  mov     [r10+28h], r8b
0x140002b30  mov     r8d, ebx
0x140002b33  mov     [r10+18h], rax
0x140002b37  mov     [r10+10h], r9
0x140002b3b  mov     [r10+24h], edx
0x140002b3f  cmp     bx, [r10+2Ah]
0x140002b44  jnb     loc_140002BF9
0x140002b4a  mov     rax, [r10+40h]
0x140002b4e  mov     cl, [r10+28h]
0x140002b52  mov     r9d, r8d
0x140002b55  cmp     [r9+rax], cl
0x140002b59  jbe     short loc_140002B5F
0x140002b5b  test    cl, cl
0x140002b5d  jnz     short loc_140002B7F
0x140002b5f  mov     rax, [r10+38h]
0x140002b63  mov     rcx, [rax+r9*8]
0x140002b67  test    rcx, rcx
0x140002b6a  jz      short loc_140002B84
0x140002b6c  test    [r10+10h], rcx
0x140002b70  jz      short loc_140002B7F
0x140002b72  mov     rax, [r10+18h]
0x140002b76  and     rax, rcx
0x140002b79  cmp     rax, [r10+18h]
0x140002b7d  jz      short loc_140002B84
0x140002b7f  mov     r11b, bl
0x140002b82  jmp     short loc_140002B87
0x140002b84  mov     r11b, 1
0x140002b87  mov     rax, [r10+30h]
0x140002b8b  mov     ecx, r8d
0x140002b8e  shr     r9, 5
0x140002b92  mov     edx, 1
0x140002b97  shl     edx, cl
0x140002b99  lea     rcx, [rax+r9*4]
0x140002b9d  test    r11b, r11b
0x140002ba0  jz      short loc_140002BA6
0x140002ba2  or      edx, [rcx]
0x140002ba4  jmp     short loc_140002BAA
0x140002ba6  not     edx
0x140002ba8  and     edx, [rcx]
0x140002baa  mov     [rcx], edx
0x140002bac  inc     r8d
0x140002baf  movzx   eax, word ptr [r10+2Ah]
0x140002bb4  cmp     r8d, eax
0x140002bb7  jb      short loc_140002B4A
0x140002bb9  add     rsp, 20h
0x140002bbd  pop     rbx
0x140002bbe  retn
0x140002bbf  mov     [r10+24h], ebx
0x140002bc3  mov     [r10+28h], bl
0x140002bc7  mov     [r10+10h], rbx
0x140002bcb  mov     [r10+18h], rbx
0x140002bcf  cmp     [r10+2Ah], bx
0x140002bd4  jbe     short loc_140002BF9
0x140002bd6  movzx   eax, word ptr [r10+2Ah]
0x140002bdb  mov     ecx, 20h ; ' '
0x140002be0  dec     eax
0x140002be2  cdq
0x140002be3  idiv    ecx
0x140002be5  mov     rcx, [r10+30h]; void *
0x140002be9  xor     edx, edx; Val
0x140002beb  inc     eax
0x140002bed  movsxd  r8, eax
0x140002bf0  shl     r8, 2; Size
0x140002bf4  call    memset_0
0x140002bf9  add     rsp, 20h
0x140002bfd  pop     rbx
0x140002bfe  retn
```
