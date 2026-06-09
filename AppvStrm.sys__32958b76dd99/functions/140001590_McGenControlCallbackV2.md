# McGenControlCallbackV2

- ea: `0x140001590`
- end: `0x14000168f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001590`
- `0x140015f00`

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
0x140001590  push    rbx
0x140001592  sub     rsp, 20h
0x140001596  mov     r10, [rsp+28h+CallbackContext]
0x14000159b  xor     ebx, ebx
0x14000159d  test    r10, r10
0x1400015a0  jz      loc_140001688
0x1400015a6  test    edx, edx
0x1400015a8  jz      loc_14000164F
0x1400015ae  cmp     edx, 1
0x1400015b1  jnz     loc_140001688
0x1400015b7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400015bc  mov     [r10+28h], r8b
0x1400015c0  mov     r8d, ebx
0x1400015c3  mov     [r10+18h], rax
0x1400015c7  mov     [r10+10h], r9
0x1400015cb  mov     [r10+24h], edx
0x1400015cf  cmp     bx, [r10+2Ah]
0x1400015d4  jnb     loc_140001688
0x1400015da  mov     rax, [r10+40h]
0x1400015de  mov     cl, [r10+28h]
0x1400015e2  mov     r9d, r8d
0x1400015e5  cmp     [r9+rax], cl
0x1400015e9  jbe     short loc_1400015EF
0x1400015eb  test    cl, cl
0x1400015ed  jnz     short loc_140001611
0x1400015ef  mov     rax, [r10+38h]
0x1400015f3  mov     rdx, [rax+r9*8]
0x1400015f7  test    rdx, rdx
0x1400015fa  jz      short loc_140001616
0x1400015fc  test    [r10+10h], rdx
0x140001600  jz      short loc_140001611
0x140001602  mov     rcx, [r10+18h]
0x140001606  mov     rax, rcx
0x140001609  and     rax, rdx
0x14000160c  cmp     rax, rcx
0x14000160f  jz      short loc_140001616
0x140001611  mov     r11b, bl
0x140001614  jmp     short loc_140001619
0x140001616  mov     r11b, 1
0x140001619  mov     rax, [r10+30h]
0x14000161d  mov     ecx, r8d
0x140001620  shr     r9, 5
0x140001624  mov     edx, 1
0x140001629  shl     edx, cl
0x14000162b  lea     rcx, [rax+r9*4]
0x14000162f  mov     eax, [rcx]
0x140001631  test    r11b, r11b
0x140001634  jz      short loc_14000163A
0x140001636  or      edx, eax
0x140001638  jmp     short loc_14000163E
0x14000163a  not     edx
0x14000163c  and     edx, eax
0x14000163e  mov     [rcx], edx
0x140001640  inc     r8d
0x140001643  movzx   eax, word ptr [r10+2Ah]
0x140001648  cmp     r8d, eax
0x14000164b  jb      short loc_1400015DA
0x14000164d  jmp     short loc_140001688
0x14000164f  movzx   eax, word ptr [r10+2Ah]
0x140001654  mov     [r10+24h], ebx
0x140001658  mov     [r10+28h], bl
0x14000165c  mov     [r10+10h], rbx
0x140001660  mov     [r10+18h], rbx
0x140001664  test    ax, ax
0x140001667  jz      short loc_140001688
0x140001669  mov     rcx, [r10+30h]; void *
0x14000166d  dec     eax
0x14000166f  cdq
0x140001670  and     edx, 1Fh
0x140001673  add     eax, edx
0x140001675  xor     edx, edx; Val
0x140001677  sar     eax, 5
0x14000167a  inc     eax
0x14000167c  movsxd  r8, eax
0x14000167f  shl     r8, 2; Size
0x140001683  call    memset
0x140001688  add     rsp, 20h
0x14000168c  pop     rbx
0x14000168d  retn
```
