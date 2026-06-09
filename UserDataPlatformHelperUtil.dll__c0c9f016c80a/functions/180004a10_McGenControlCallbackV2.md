# McGenControlCallbackV2

- ea: `0x180004a10`
- end: `0x180004b10`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004a10`
- `0x18000a15a`

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
0x180004a10  push    rbx
0x180004a12  sub     rsp, 20h
0x180004a16  mov     r10, [rsp+28h+CallbackContext]
0x180004a1b  xor     ebx, ebx
0x180004a1d  test    r10, r10
0x180004a20  jz      loc_180004B0A
0x180004a26  test    edx, edx
0x180004a28  jz      loc_180004ACF
0x180004a2e  cmp     edx, 1
0x180004a31  jnz     loc_180004B0A
0x180004a37  mov     rax, [rsp+28h+MatchAllKeyword]
0x180004a3c  mov     [r10+28h], r8b
0x180004a40  mov     r8d, ebx
0x180004a43  mov     [r10+18h], rax
0x180004a47  mov     [r10+10h], r9
0x180004a4b  mov     [r10+24h], edx
0x180004a4f  cmp     bx, [r10+2Ah]
0x180004a54  jnb     loc_180004B0A
0x180004a5a  mov     rax, [r10+40h]
0x180004a5e  mov     cl, [r10+28h]
0x180004a62  mov     r9d, r8d
0x180004a65  cmp     [r9+rax], cl
0x180004a69  jbe     short loc_180004A6F
0x180004a6b  test    cl, cl
0x180004a6d  jnz     short loc_180004A8F
0x180004a6f  mov     rax, [r10+38h]
0x180004a73  mov     rcx, [rax+r9*8]
0x180004a77  test    rcx, rcx
0x180004a7a  jz      short loc_180004A94
0x180004a7c  test    [r10+10h], rcx
0x180004a80  jz      short loc_180004A8F
0x180004a82  mov     rax, [r10+18h]
0x180004a86  and     rax, rcx
0x180004a89  cmp     rax, [r10+18h]
0x180004a8d  jz      short loc_180004A94
0x180004a8f  mov     r11b, bl
0x180004a92  jmp     short loc_180004A97
0x180004a94  mov     r11b, 1
0x180004a97  mov     rax, [r10+30h]
0x180004a9b  mov     ecx, r8d
0x180004a9e  shr     r9, 5
0x180004aa2  mov     edx, 1
0x180004aa7  shl     edx, cl
0x180004aa9  lea     rcx, [rax+r9*4]
0x180004aad  test    r11b, r11b
0x180004ab0  jz      short loc_180004AB6
0x180004ab2  or      edx, [rcx]
0x180004ab4  jmp     short loc_180004ABA
0x180004ab6  not     edx
0x180004ab8  and     edx, [rcx]
0x180004aba  mov     [rcx], edx
0x180004abc  inc     r8d
0x180004abf  movzx   eax, word ptr [r10+2Ah]
0x180004ac4  cmp     r8d, eax
0x180004ac7  jb      short loc_180004A5A
0x180004ac9  add     rsp, 20h
0x180004acd  pop     rbx
0x180004ace  retn
0x180004acf  mov     [r10+24h], ebx
0x180004ad3  mov     [r10+28h], bl
0x180004ad7  mov     [r10+10h], rbx
0x180004adb  mov     [r10+18h], rbx
0x180004adf  cmp     [r10+2Ah], bx
0x180004ae4  jbe     short loc_180004B0A
0x180004ae6  movzx   eax, word ptr [r10+2Ah]
0x180004aeb  mov     rcx, [r10+30h]; void *
0x180004aef  dec     eax
0x180004af1  cdq
0x180004af2  and     edx, 1Fh
0x180004af5  add     eax, edx
0x180004af7  xor     edx, edx; Val
0x180004af9  sar     eax, 5
0x180004afc  inc     eax
0x180004afe  movsxd  r8, eax
0x180004b01  shl     r8, 2; Size
0x180004b05  call    memset_0
0x180004b0a  add     rsp, 20h
0x180004b0e  pop     rbx
0x180004b0f  retn
```
