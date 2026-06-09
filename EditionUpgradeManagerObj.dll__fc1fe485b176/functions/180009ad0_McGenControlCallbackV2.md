# McGenControlCallbackV2

- ea: `0x180009ad0`
- end: `0x180009bd0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800026b4`
- `0x180009ad0`

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
0x180009ad0  push    rbx
0x180009ad2  sub     rsp, 20h
0x180009ad6  mov     r10, [rsp+28h+CallbackContext]
0x180009adb  xor     ebx, ebx
0x180009add  test    r10, r10
0x180009ae0  jz      loc_180009BCA
0x180009ae6  test    edx, edx
0x180009ae8  jz      loc_180009B8F
0x180009aee  cmp     edx, 1
0x180009af1  jnz     loc_180009BCA
0x180009af7  mov     rax, [rsp+28h+MatchAllKeyword]
0x180009afc  mov     [r10+28h], r8b
0x180009b00  mov     r8d, ebx
0x180009b03  mov     [r10+18h], rax
0x180009b07  mov     [r10+10h], r9
0x180009b0b  mov     [r10+24h], edx
0x180009b0f  cmp     bx, [r10+2Ah]
0x180009b14  jnb     loc_180009BCA
0x180009b1a  mov     rax, [r10+40h]
0x180009b1e  mov     cl, [r10+28h]
0x180009b22  mov     r9d, r8d
0x180009b25  cmp     [r9+rax], cl
0x180009b29  jbe     short loc_180009B2F
0x180009b2b  test    cl, cl
0x180009b2d  jnz     short loc_180009B4F
0x180009b2f  mov     rax, [r10+38h]
0x180009b33  mov     rcx, [rax+r9*8]
0x180009b37  test    rcx, rcx
0x180009b3a  jz      short loc_180009B54
0x180009b3c  test    [r10+10h], rcx
0x180009b40  jz      short loc_180009B4F
0x180009b42  mov     rax, [r10+18h]
0x180009b46  and     rax, rcx
0x180009b49  cmp     rax, [r10+18h]
0x180009b4d  jz      short loc_180009B54
0x180009b4f  mov     r11b, bl
0x180009b52  jmp     short loc_180009B57
0x180009b54  mov     r11b, 1
0x180009b57  mov     rax, [r10+30h]
0x180009b5b  mov     ecx, r8d
0x180009b5e  shr     r9, 5
0x180009b62  mov     edx, 1
0x180009b67  shl     edx, cl
0x180009b69  lea     rcx, [rax+r9*4]
0x180009b6d  test    r11b, r11b
0x180009b70  jz      short loc_180009B76
0x180009b72  or      edx, [rcx]
0x180009b74  jmp     short loc_180009B7A
0x180009b76  not     edx
0x180009b78  and     edx, [rcx]
0x180009b7a  mov     [rcx], edx
0x180009b7c  inc     r8d
0x180009b7f  movzx   eax, word ptr [r10+2Ah]
0x180009b84  cmp     r8d, eax
0x180009b87  jb      short loc_180009B1A
0x180009b89  add     rsp, 20h
0x180009b8d  pop     rbx
0x180009b8e  retn
0x180009b8f  mov     [r10+24h], ebx
0x180009b93  mov     [r10+28h], bl
0x180009b97  mov     [r10+10h], rbx
0x180009b9b  mov     [r10+18h], rbx
0x180009b9f  cmp     [r10+2Ah], bx
0x180009ba4  jbe     short loc_180009BCA
0x180009ba6  movzx   eax, word ptr [r10+2Ah]
0x180009bab  mov     rcx, [r10+30h]; void *
0x180009baf  dec     eax
0x180009bb1  cdq
0x180009bb2  and     edx, 1Fh
0x180009bb5  add     eax, edx
0x180009bb7  xor     edx, edx; Val
0x180009bb9  sar     eax, 5
0x180009bbc  inc     eax
0x180009bbe  movsxd  r8, eax
0x180009bc1  shl     r8, 2; Size
0x180009bc5  call    memset_0
0x180009bca  add     rsp, 20h
0x180009bce  pop     rbx
0x180009bcf  retn
```
