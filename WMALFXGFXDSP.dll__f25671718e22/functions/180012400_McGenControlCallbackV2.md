# McGenControlCallbackV2

- ea: `0x180012400`
- end: `0x1800124f1`
- name: `McGenControlCallbackV2`
- size: `241`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012400`
- `0x180015ea8`

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
0x180012400  push    rbx
0x180012402  mov     r10, [rsp+8+CallbackContext]
0x180012407  xor     ebx, ebx
0x180012409  test    r10, r10
0x18001240c  jnz     short loc_180012410
0x18001240e  pop     rbx
0x18001240f  retn
0x180012410  test    edx, edx
0x180012412  jz      loc_1800124B2
0x180012418  cmp     edx, 1
0x18001241b  jnz     short loc_18001240E
0x18001241d  mov     rax, [rsp+8+MatchAllKeyword]
0x180012422  mov     [r10+28h], r8b
0x180012426  mov     r8d, ebx
0x180012429  mov     [r10+18h], rax
0x18001242d  mov     [r10+10h], r9
0x180012431  mov     [r10+24h], edx
0x180012435  cmp     bx, [r10+2Ah]
0x18001243a  jnb     short loc_18001240E
0x18001243c  mov     rax, [r10+40h]
0x180012440  mov     cl, [r10+28h]
0x180012444  mov     r9d, r8d
0x180012447  cmp     [r9+rax], cl
0x18001244b  ja      short loc_1800124AC
0x18001244d  mov     rax, [r10+38h]
0x180012451  mov     rcx, [rax+r9*8]
0x180012455  test    rcx, rcx
0x180012458  jz      short loc_1800124A7
0x18001245a  test    [r10+10h], rcx
0x18001245e  jnz     short loc_18001249A
0x180012460  mov     r11b, bl
0x180012463  mov     rax, [r10+30h]
0x180012467  mov     ecx, r8d
0x18001246a  shr     r9, 5
0x18001246e  mov     edx, 1
0x180012473  shl     edx, cl
0x180012475  lea     rcx, [rax+r9*4]
0x180012479  test    r11b, r11b
0x18001247c  jnz     short loc_180012496
0x18001247e  not     edx
0x180012480  and     edx, [rcx]
0x180012482  mov     [rcx], edx
0x180012484  inc     r8d
0x180012487  movzx   eax, word ptr [r10+2Ah]
0x18001248c  cmp     r8d, eax
0x18001248f  jb      short loc_18001243C
0x180012491  jmp     loc_18001240E
0x180012496  or      edx, [rcx]
0x180012498  jmp     short loc_180012482
0x18001249a  mov     rax, [r10+18h]
0x18001249e  and     rax, rcx
0x1800124a1  cmp     rax, [r10+18h]
0x1800124a5  jnz     short loc_180012460
0x1800124a7  mov     r11b, 1
0x1800124aa  jmp     short loc_180012463
0x1800124ac  test    cl, cl
0x1800124ae  jnz     short loc_180012460
0x1800124b0  jmp     short loc_18001244D
0x1800124b2  mov     [r10+24h], ebx
0x1800124b6  mov     [r10+28h], bl
0x1800124ba  mov     [r10+10h], rbx
0x1800124be  mov     [r10+18h], rbx
0x1800124c2  cmp     [r10+2Ah], bx
0x1800124c7  jbe     loc_18001240E
0x1800124cd  movzx   eax, word ptr [r10+2Ah]
0x1800124d2  mov     ecx, 20h ; ' '
0x1800124d7  dec     eax
0x1800124d9  cdq
0x1800124da  idiv    ecx
0x1800124dc  mov     rcx, [r10+30h]; void *
0x1800124e0  xor     edx, edx; Val
0x1800124e2  inc     eax
0x1800124e4  movsxd  r8, eax
0x1800124e7  shl     r8, 2; Size
0x1800124eb  pop     rbx
0x1800124ec  jmp     memset_0
```
