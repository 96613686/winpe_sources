# McGenControlCallbackV2

- ea: `0x1800040c0`
- end: `0x1800041bf`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800040c0`
- `0x18000b6de`

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
0x1800040c0  push    rbx
0x1800040c2  sub     rsp, 20h
0x1800040c6  mov     r10, [rsp+28h+CallbackContext]
0x1800040cb  xor     ebx, ebx
0x1800040cd  test    r10, r10
0x1800040d0  jz      loc_1800041B9
0x1800040d6  test    edx, edx
0x1800040d8  jz      loc_18000417F
0x1800040de  cmp     edx, 1
0x1800040e1  jnz     loc_1800041B9
0x1800040e7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800040ec  mov     [r10+28h], r8b
0x1800040f0  mov     r8d, ebx
0x1800040f3  mov     [r10+18h], rax
0x1800040f7  mov     [r10+10h], r9
0x1800040fb  mov     [r10+24h], edx
0x1800040ff  cmp     bx, [r10+2Ah]
0x180004104  jnb     loc_1800041B9
0x18000410a  mov     rax, [r10+40h]
0x18000410e  mov     cl, [r10+28h]
0x180004112  mov     r9d, r8d
0x180004115  cmp     [r9+rax], cl
0x180004119  jbe     short loc_18000411F
0x18000411b  test    cl, cl
0x18000411d  jnz     short loc_18000413F
0x18000411f  mov     rax, [r10+38h]
0x180004123  mov     rcx, [rax+r9*8]
0x180004127  test    rcx, rcx
0x18000412a  jz      short loc_180004144
0x18000412c  test    [r10+10h], rcx
0x180004130  jz      short loc_18000413F
0x180004132  mov     rax, [r10+18h]
0x180004136  and     rax, rcx
0x180004139  cmp     rax, [r10+18h]
0x18000413d  jz      short loc_180004144
0x18000413f  mov     r11b, bl
0x180004142  jmp     short loc_180004147
0x180004144  mov     r11b, 1
0x180004147  mov     rax, [r10+30h]
0x18000414b  mov     ecx, r8d
0x18000414e  shr     r9, 5
0x180004152  mov     edx, 1
0x180004157  shl     edx, cl
0x180004159  lea     rcx, [rax+r9*4]
0x18000415d  test    r11b, r11b
0x180004160  jz      short loc_180004166
0x180004162  or      edx, [rcx]
0x180004164  jmp     short loc_18000416A
0x180004166  not     edx
0x180004168  and     edx, [rcx]
0x18000416a  mov     [rcx], edx
0x18000416c  inc     r8d
0x18000416f  movzx   eax, word ptr [r10+2Ah]
0x180004174  cmp     r8d, eax
0x180004177  jb      short loc_18000410A
0x180004179  add     rsp, 20h
0x18000417d  pop     rbx
0x18000417e  retn
0x18000417f  mov     [r10+24h], ebx
0x180004183  mov     [r10+28h], bl
0x180004187  mov     [r10+10h], rbx
0x18000418b  mov     [r10+18h], rbx
0x18000418f  cmp     [r10+2Ah], bx
0x180004194  jbe     short loc_1800041B9
0x180004196  movzx   eax, word ptr [r10+2Ah]
0x18000419b  mov     ecx, 20h ; ' '
0x1800041a0  dec     eax
0x1800041a2  cdq
0x1800041a3  idiv    ecx
0x1800041a5  mov     rcx, [r10+30h]; void *
0x1800041a9  xor     edx, edx; Val
0x1800041ab  inc     eax
0x1800041ad  movsxd  r8, eax
0x1800041b0  shl     r8, 2; Size
0x1800041b4  call    memset_0
0x1800041b9  add     rsp, 20h
0x1800041bd  pop     rbx
0x1800041be  retn
```
