# McGenControlCallbackV2

- ea: `0x180002260`
- end: `0x18000235f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000206a`
- `0x180002260`

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
0x180002260  push    rbx
0x180002262  sub     rsp, 20h
0x180002266  mov     r10, [rsp+28h+CallbackContext]
0x18000226b  xor     ebx, ebx
0x18000226d  test    r10, r10
0x180002270  jz      loc_180002359
0x180002276  test    edx, edx
0x180002278  jz      loc_18000231F
0x18000227e  cmp     edx, 1
0x180002281  jnz     loc_180002359
0x180002287  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000228c  mov     [r10+28h], r8b
0x180002290  mov     r8d, ebx
0x180002293  mov     [r10+18h], rax
0x180002297  mov     [r10+10h], r9
0x18000229b  mov     [r10+24h], edx
0x18000229f  cmp     bx, [r10+2Ah]
0x1800022a4  jnb     loc_180002359
0x1800022aa  mov     rax, [r10+40h]
0x1800022ae  mov     cl, [r10+28h]
0x1800022b2  mov     r9d, r8d
0x1800022b5  cmp     [r9+rax], cl
0x1800022b9  jbe     short loc_1800022BF
0x1800022bb  test    cl, cl
0x1800022bd  jnz     short loc_1800022DF
0x1800022bf  mov     rax, [r10+38h]
0x1800022c3  mov     rcx, [rax+r9*8]
0x1800022c7  test    rcx, rcx
0x1800022ca  jz      short loc_1800022E4
0x1800022cc  test    [r10+10h], rcx
0x1800022d0  jz      short loc_1800022DF
0x1800022d2  mov     rax, [r10+18h]
0x1800022d6  and     rax, rcx
0x1800022d9  cmp     rax, [r10+18h]
0x1800022dd  jz      short loc_1800022E4
0x1800022df  mov     r11b, bl
0x1800022e2  jmp     short loc_1800022E7
0x1800022e4  mov     r11b, 1
0x1800022e7  mov     rax, [r10+30h]
0x1800022eb  mov     ecx, r8d
0x1800022ee  shr     r9, 5
0x1800022f2  mov     edx, 1
0x1800022f7  shl     edx, cl
0x1800022f9  lea     rcx, [rax+r9*4]
0x1800022fd  test    r11b, r11b
0x180002300  jz      short loc_180002306
0x180002302  or      edx, [rcx]
0x180002304  jmp     short loc_18000230A
0x180002306  not     edx
0x180002308  and     edx, [rcx]
0x18000230a  mov     [rcx], edx
0x18000230c  inc     r8d
0x18000230f  movzx   eax, word ptr [r10+2Ah]
0x180002314  cmp     r8d, eax
0x180002317  jb      short loc_1800022AA
0x180002319  add     rsp, 20h
0x18000231d  pop     rbx
0x18000231e  retn
0x18000231f  mov     [r10+24h], ebx
0x180002323  mov     [r10+28h], bl
0x180002327  mov     [r10+10h], rbx
0x18000232b  mov     [r10+18h], rbx
0x18000232f  cmp     [r10+2Ah], bx
0x180002334  jbe     short loc_180002359
0x180002336  movzx   eax, word ptr [r10+2Ah]
0x18000233b  mov     ecx, 20h ; ' '
0x180002340  dec     eax
0x180002342  cdq
0x180002343  idiv    ecx
0x180002345  mov     rcx, [r10+30h]; void *
0x180002349  xor     edx, edx; Val
0x18000234b  inc     eax
0x18000234d  movsxd  r8, eax
0x180002350  shl     r8, 2; Size
0x180002354  call    memset_0
0x180002359  add     rsp, 20h
0x18000235d  pop     rbx
0x18000235e  retn
```
