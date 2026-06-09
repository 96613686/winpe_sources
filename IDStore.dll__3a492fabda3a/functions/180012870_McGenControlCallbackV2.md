# McGenControlCallbackV2

- ea: `0x180012870`
- end: `0x18001296f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012870`
- `0x180019722`

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
0x180012870  push    rbx
0x180012872  sub     rsp, 20h
0x180012876  mov     r10, [rsp+28h+CallbackContext]
0x18001287b  xor     ebx, ebx
0x18001287d  test    r10, r10
0x180012880  jz      loc_180012969
0x180012886  test    edx, edx
0x180012888  jz      loc_18001292F
0x18001288e  cmp     edx, 1
0x180012891  jnz     loc_180012969
0x180012897  mov     rax, [rsp+28h+MatchAllKeyword]
0x18001289c  mov     [r10+28h], r8b
0x1800128a0  mov     r8d, ebx
0x1800128a3  mov     [r10+18h], rax
0x1800128a7  mov     [r10+10h], r9
0x1800128ab  mov     [r10+24h], edx
0x1800128af  cmp     bx, [r10+2Ah]
0x1800128b4  jnb     loc_180012969
0x1800128ba  mov     rax, [r10+40h]
0x1800128be  mov     cl, [r10+28h]
0x1800128c2  mov     r9d, r8d
0x1800128c5  cmp     [r9+rax], cl
0x1800128c9  jbe     short loc_1800128CF
0x1800128cb  test    cl, cl
0x1800128cd  jnz     short loc_1800128EF
0x1800128cf  mov     rax, [r10+38h]
0x1800128d3  mov     rcx, [rax+r9*8]
0x1800128d7  test    rcx, rcx
0x1800128da  jz      short loc_1800128F4
0x1800128dc  test    [r10+10h], rcx
0x1800128e0  jz      short loc_1800128EF
0x1800128e2  mov     rax, [r10+18h]
0x1800128e6  and     rax, rcx
0x1800128e9  cmp     rax, [r10+18h]
0x1800128ed  jz      short loc_1800128F4
0x1800128ef  mov     r11b, bl
0x1800128f2  jmp     short loc_1800128F7
0x1800128f4  mov     r11b, 1
0x1800128f7  mov     rax, [r10+30h]
0x1800128fb  mov     ecx, r8d
0x1800128fe  shr     r9, 5
0x180012902  mov     edx, 1
0x180012907  shl     edx, cl
0x180012909  lea     rcx, [rax+r9*4]
0x18001290d  test    r11b, r11b
0x180012910  jz      short loc_180012916
0x180012912  or      edx, [rcx]
0x180012914  jmp     short loc_18001291A
0x180012916  not     edx
0x180012918  and     edx, [rcx]
0x18001291a  mov     [rcx], edx
0x18001291c  inc     r8d
0x18001291f  movzx   eax, word ptr [r10+2Ah]
0x180012924  cmp     r8d, eax
0x180012927  jb      short loc_1800128BA
0x180012929  add     rsp, 20h
0x18001292d  pop     rbx
0x18001292e  retn
0x18001292f  mov     [r10+24h], ebx
0x180012933  mov     [r10+28h], bl
0x180012937  mov     [r10+10h], rbx
0x18001293b  mov     [r10+18h], rbx
0x18001293f  cmp     [r10+2Ah], bx
0x180012944  jbe     short loc_180012969
0x180012946  movzx   eax, word ptr [r10+2Ah]
0x18001294b  mov     ecx, 20h ; ' '
0x180012950  dec     eax
0x180012952  cdq
0x180012953  idiv    ecx
0x180012955  mov     rcx, [r10+30h]; void *
0x180012959  xor     edx, edx; Val
0x18001295b  inc     eax
0x18001295d  movsxd  r8, eax
0x180012960  shl     r8, 2; Size
0x180012964  call    memset_0
0x180012969  add     rsp, 20h
0x18001296d  pop     rbx
0x18001296e  retn
```
