# McGenControlCallbackV2

- ea: `0x140008320`
- end: `0x14000841f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140008320`
- `0x140014000`

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
0x140008320  push    rbx
0x140008322  sub     rsp, 20h
0x140008326  mov     r10, [rsp+28h+CallbackContext]
0x14000832b  xor     ebx, ebx
0x14000832d  test    r10, r10
0x140008330  jz      loc_140008418
0x140008336  test    edx, edx
0x140008338  jz      loc_1400083DF
0x14000833e  cmp     edx, 1
0x140008341  jnz     loc_140008418
0x140008347  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000834c  mov     [r10+28h], r8b
0x140008350  mov     r8d, ebx
0x140008353  mov     [r10+18h], rax
0x140008357  mov     [r10+10h], r9
0x14000835b  mov     [r10+24h], edx
0x14000835f  cmp     bx, [r10+2Ah]
0x140008364  jnb     loc_140008418
0x14000836a  mov     rax, [r10+40h]
0x14000836e  mov     cl, [r10+28h]
0x140008372  mov     r9d, r8d
0x140008375  cmp     [r9+rax], cl
0x140008379  jbe     short loc_14000837F
0x14000837b  test    cl, cl
0x14000837d  jnz     short loc_1400083A1
0x14000837f  mov     rax, [r10+38h]
0x140008383  mov     rdx, [rax+r9*8]
0x140008387  test    rdx, rdx
0x14000838a  jz      short loc_1400083A6
0x14000838c  test    [r10+10h], rdx
0x140008390  jz      short loc_1400083A1
0x140008392  mov     rcx, [r10+18h]
0x140008396  mov     rax, rcx
0x140008399  and     rax, rdx
0x14000839c  cmp     rax, rcx
0x14000839f  jz      short loc_1400083A6
0x1400083a1  mov     r11b, bl
0x1400083a4  jmp     short loc_1400083A9
0x1400083a6  mov     r11b, 1
0x1400083a9  mov     rax, [r10+30h]
0x1400083ad  mov     ecx, r8d
0x1400083b0  shr     r9, 5
0x1400083b4  mov     edx, 1
0x1400083b9  shl     edx, cl
0x1400083bb  lea     rcx, [rax+r9*4]
0x1400083bf  mov     eax, [rcx]
0x1400083c1  test    r11b, r11b
0x1400083c4  jz      short loc_1400083CA
0x1400083c6  or      edx, eax
0x1400083c8  jmp     short loc_1400083CE
0x1400083ca  not     edx
0x1400083cc  and     edx, eax
0x1400083ce  mov     [rcx], edx
0x1400083d0  inc     r8d
0x1400083d3  movzx   eax, word ptr [r10+2Ah]
0x1400083d8  cmp     r8d, eax
0x1400083db  jb      short loc_14000836A
0x1400083dd  jmp     short loc_140008418
0x1400083df  movzx   eax, word ptr [r10+2Ah]
0x1400083e4  mov     [r10+24h], ebx
0x1400083e8  mov     [r10+28h], bl
0x1400083ec  mov     [r10+10h], rbx
0x1400083f0  mov     [r10+18h], rbx
0x1400083f4  test    ax, ax
0x1400083f7  jz      short loc_140008418
0x1400083f9  mov     rcx, [r10+30h]; void *
0x1400083fd  dec     eax
0x1400083ff  cdq
0x140008400  and     edx, 1Fh
0x140008403  add     eax, edx
0x140008405  xor     edx, edx; Val
0x140008407  sar     eax, 5
0x14000840a  inc     eax
0x14000840c  movsxd  r8, eax
0x14000840f  shl     r8, 2; Size
0x140008413  call    memset
0x140008418  add     rsp, 20h
0x14000841c  pop     rbx
0x14000841d  retn
```
