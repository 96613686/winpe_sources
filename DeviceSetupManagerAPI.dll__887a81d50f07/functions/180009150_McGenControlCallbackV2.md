# McGenControlCallbackV2

- ea: `0x180009150`
- end: `0x180009250`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002570`
- `0x180009150`

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
0x180009150  push    rbx
0x180009152  sub     rsp, 20h
0x180009156  mov     r10, [rsp+28h+CallbackContext]
0x18000915b  xor     ebx, ebx
0x18000915d  test    r10, r10
0x180009160  jz      loc_18000924A
0x180009166  test    edx, edx
0x180009168  jz      loc_18000920F
0x18000916e  cmp     edx, 1
0x180009171  jnz     loc_18000924A
0x180009177  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000917c  mov     [r10+28h], r8b
0x180009180  mov     r8d, ebx
0x180009183  mov     [r10+18h], rax
0x180009187  mov     [r10+10h], r9
0x18000918b  mov     [r10+24h], edx
0x18000918f  cmp     bx, [r10+2Ah]
0x180009194  jnb     loc_18000924A
0x18000919a  mov     rax, [r10+40h]
0x18000919e  mov     cl, [r10+28h]
0x1800091a2  mov     r9d, r8d
0x1800091a5  cmp     [r9+rax], cl
0x1800091a9  jbe     short loc_1800091AF
0x1800091ab  test    cl, cl
0x1800091ad  jnz     short loc_1800091CF
0x1800091af  mov     rax, [r10+38h]
0x1800091b3  mov     rcx, [rax+r9*8]
0x1800091b7  test    rcx, rcx
0x1800091ba  jz      short loc_1800091D4
0x1800091bc  test    [r10+10h], rcx
0x1800091c0  jz      short loc_1800091CF
0x1800091c2  mov     rax, [r10+18h]
0x1800091c6  and     rax, rcx
0x1800091c9  cmp     rax, [r10+18h]
0x1800091cd  jz      short loc_1800091D4
0x1800091cf  mov     r11b, bl
0x1800091d2  jmp     short loc_1800091D7
0x1800091d4  mov     r11b, 1
0x1800091d7  mov     rax, [r10+30h]
0x1800091db  mov     ecx, r8d
0x1800091de  shr     r9, 5
0x1800091e2  mov     edx, 1
0x1800091e7  shl     edx, cl
0x1800091e9  lea     rcx, [rax+r9*4]
0x1800091ed  test    r11b, r11b
0x1800091f0  jz      short loc_1800091F6
0x1800091f2  or      edx, [rcx]
0x1800091f4  jmp     short loc_1800091FA
0x1800091f6  not     edx
0x1800091f8  and     edx, [rcx]
0x1800091fa  mov     [rcx], edx
0x1800091fc  inc     r8d
0x1800091ff  movzx   eax, word ptr [r10+2Ah]
0x180009204  cmp     r8d, eax
0x180009207  jb      short loc_18000919A
0x180009209  add     rsp, 20h
0x18000920d  pop     rbx
0x18000920e  retn
0x18000920f  mov     [r10+24h], ebx
0x180009213  mov     [r10+28h], bl
0x180009217  mov     [r10+10h], rbx
0x18000921b  mov     [r10+18h], rbx
0x18000921f  cmp     [r10+2Ah], bx
0x180009224  jbe     short loc_18000924A
0x180009226  movzx   eax, word ptr [r10+2Ah]
0x18000922b  mov     rcx, [r10+30h]; void *
0x18000922f  dec     eax
0x180009231  cdq
0x180009232  and     edx, 1Fh
0x180009235  add     eax, edx
0x180009237  xor     edx, edx; Val
0x180009239  sar     eax, 5
0x18000923c  inc     eax
0x18000923e  movsxd  r8, eax
0x180009241  shl     r8, 2; Size
0x180009245  call    memset_0
0x18000924a  add     rsp, 20h
0x18000924e  pop     rbx
0x18000924f  retn
```
