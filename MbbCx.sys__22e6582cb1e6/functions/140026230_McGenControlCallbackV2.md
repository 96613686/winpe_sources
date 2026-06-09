# McGenControlCallbackV2

- ea: `0x140026230`
- end: `0x14002632f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140026230`
- `0x140048340`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rdx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
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
          v13 = *v12;
          if ( v10 )
            v14 = v13 | v11;
          else
            v14 = v13 & ~v11;
          *v12 = v14;
        }
      }
    }
    else
    {
      v15 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v15 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v15 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x140026230  push    rbx
0x140026232  sub     rsp, 20h
0x140026236  mov     r10, [rsp+28h+CallbackContext]
0x14002623b  xor     ebx, ebx
0x14002623d  test    r10, r10
0x140026240  jz      loc_140026328
0x140026246  test    edx, edx
0x140026248  jz      loc_1400262EF
0x14002624e  cmp     edx, 1
0x140026251  jnz     loc_140026328
0x140026257  mov     rax, [rsp+28h+MatchAllKeyword]
0x14002625c  mov     [r10+28h], r8b
0x140026260  mov     r8d, ebx
0x140026263  mov     [r10+18h], rax
0x140026267  mov     [r10+10h], r9
0x14002626b  mov     [r10+24h], edx
0x14002626f  cmp     bx, [r10+2Ah]
0x140026274  jnb     loc_140026328
0x14002627a  mov     rax, [r10+40h]
0x14002627e  mov     cl, [r10+28h]
0x140026282  mov     r9d, r8d
0x140026285  cmp     [r9+rax], cl
0x140026289  jbe     short loc_14002628F
0x14002628b  test    cl, cl
0x14002628d  jnz     short loc_1400262B1
0x14002628f  mov     rax, [r10+38h]
0x140026293  mov     rdx, [rax+r9*8]
0x140026297  test    rdx, rdx
0x14002629a  jz      short loc_1400262B6
0x14002629c  test    [r10+10h], rdx
0x1400262a0  jz      short loc_1400262B1
0x1400262a2  mov     rcx, [r10+18h]
0x1400262a6  mov     rax, rcx
0x1400262a9  and     rax, rdx
0x1400262ac  cmp     rax, rcx
0x1400262af  jz      short loc_1400262B6
0x1400262b1  mov     r11b, bl
0x1400262b4  jmp     short loc_1400262B9
0x1400262b6  mov     r11b, 1
0x1400262b9  mov     rax, [r10+30h]
0x1400262bd  mov     ecx, r8d
0x1400262c0  shr     r9, 5
0x1400262c4  mov     edx, 1
0x1400262c9  shl     edx, cl
0x1400262cb  lea     rcx, [rax+r9*4]
0x1400262cf  mov     eax, [rcx]
0x1400262d1  test    r11b, r11b
0x1400262d4  jz      short loc_1400262DA
0x1400262d6  or      edx, eax
0x1400262d8  jmp     short loc_1400262DE
0x1400262da  not     edx
0x1400262dc  and     edx, eax
0x1400262de  mov     [rcx], edx
0x1400262e0  inc     r8d
0x1400262e3  movzx   eax, word ptr [r10+2Ah]
0x1400262e8  cmp     r8d, eax
0x1400262eb  jb      short loc_14002627A
0x1400262ed  jmp     short loc_140026328
0x1400262ef  movzx   eax, word ptr [r10+2Ah]
0x1400262f4  mov     [r10+24h], ebx
0x1400262f8  mov     [r10+28h], bl
0x1400262fc  mov     [r10+10h], rbx
0x140026300  mov     [r10+18h], rbx
0x140026304  test    ax, ax
0x140026307  jz      short loc_140026328
0x140026309  mov     rcx, [r10+30h]; void *
0x14002630d  dec     eax
0x14002630f  cdq
0x140026310  and     edx, 1Fh
0x140026313  add     eax, edx
0x140026315  xor     edx, edx; Val
0x140026317  sar     eax, 5
0x14002631a  inc     eax
0x14002631c  movsxd  r8, eax
0x14002631f  shl     r8, 2; Size
0x140026323  call    memset
0x140026328  add     rsp, 20h
0x14002632c  pop     rbx
0x14002632d  retn
```
