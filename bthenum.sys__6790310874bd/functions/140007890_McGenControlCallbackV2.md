# McGenControlCallbackV2

- ea: `0x140007890`
- end: `0x14000798f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140007890`
- `0x140008140`

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
0x140007890  push    rbx
0x140007892  sub     rsp, 20h
0x140007896  mov     r10, [rsp+28h+CallbackContext]
0x14000789b  xor     ebx, ebx
0x14000789d  test    r10, r10
0x1400078a0  jz      loc_140007988
0x1400078a6  test    edx, edx
0x1400078a8  jz      loc_14000794F
0x1400078ae  cmp     edx, 1
0x1400078b1  jnz     loc_140007988
0x1400078b7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400078bc  mov     [r10+28h], r8b
0x1400078c0  mov     r8d, ebx
0x1400078c3  mov     [r10+18h], rax
0x1400078c7  mov     [r10+10h], r9
0x1400078cb  mov     [r10+24h], edx
0x1400078cf  cmp     bx, [r10+2Ah]
0x1400078d4  jnb     loc_140007988
0x1400078da  mov     rax, [r10+40h]
0x1400078de  mov     cl, [r10+28h]
0x1400078e2  mov     r9d, r8d
0x1400078e5  cmp     [r9+rax], cl
0x1400078e9  jbe     short loc_1400078EF
0x1400078eb  test    cl, cl
0x1400078ed  jnz     short loc_140007911
0x1400078ef  mov     rax, [r10+38h]
0x1400078f3  mov     rdx, [rax+r9*8]
0x1400078f7  test    rdx, rdx
0x1400078fa  jz      short loc_140007916
0x1400078fc  test    [r10+10h], rdx
0x140007900  jz      short loc_140007911
0x140007902  mov     rcx, [r10+18h]
0x140007906  mov     rax, rcx
0x140007909  and     rax, rdx
0x14000790c  cmp     rax, rcx
0x14000790f  jz      short loc_140007916
0x140007911  mov     r11b, bl
0x140007914  jmp     short loc_140007919
0x140007916  mov     r11b, 1
0x140007919  mov     rax, [r10+30h]
0x14000791d  mov     ecx, r8d
0x140007920  shr     r9, 5
0x140007924  mov     edx, 1
0x140007929  shl     edx, cl
0x14000792b  lea     rcx, [rax+r9*4]
0x14000792f  mov     eax, [rcx]
0x140007931  test    r11b, r11b
0x140007934  jz      short loc_14000793A
0x140007936  or      edx, eax
0x140007938  jmp     short loc_14000793E
0x14000793a  not     edx
0x14000793c  and     edx, eax
0x14000793e  mov     [rcx], edx
0x140007940  inc     r8d
0x140007943  movzx   eax, word ptr [r10+2Ah]
0x140007948  cmp     r8d, eax
0x14000794b  jb      short loc_1400078DA
0x14000794d  jmp     short loc_140007988
0x14000794f  movzx   eax, word ptr [r10+2Ah]
0x140007954  mov     [r10+24h], ebx
0x140007958  mov     [r10+28h], bl
0x14000795c  mov     [r10+10h], rbx
0x140007960  mov     [r10+18h], rbx
0x140007964  test    ax, ax
0x140007967  jz      short loc_140007988
0x140007969  mov     rcx, [r10+30h]; void *
0x14000796d  dec     eax
0x14000796f  cdq
0x140007970  and     edx, 1Fh
0x140007973  add     eax, edx
0x140007975  xor     edx, edx; Val
0x140007977  sar     eax, 5
0x14000797a  inc     eax
0x14000797c  movsxd  r8, eax
0x14000797f  shl     r8, 2; Size
0x140007983  call    memset
0x140007988  add     rsp, 20h
0x14000798c  pop     rbx
0x14000798d  retn
```
