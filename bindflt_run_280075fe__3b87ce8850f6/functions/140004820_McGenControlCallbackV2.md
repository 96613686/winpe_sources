# McGenControlCallbackV2

- ea: `0x140004820`
- end: `0x14000491e`
- name: `McGenControlCallbackV2`
- size: `254`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140004820`
- `0x140004fc0`

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
0x140004820  push    rbx
0x140004822  sub     rsp, 20h
0x140004826  mov     r10, [rsp+28h+CallbackContext]
0x14000482b  xor     ebx, ebx
0x14000482d  test    r10, r10
0x140004830  jz      loc_140004917
0x140004836  test    edx, edx
0x140004838  jz      loc_1400048DF
0x14000483e  cmp     edx, 1
0x140004841  jnz     loc_140004917
0x140004847  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000484c  mov     [r10+28h], r8b
0x140004850  mov     r8d, ebx
0x140004853  mov     [r10+18h], rax
0x140004857  mov     [r10+10h], r9
0x14000485b  mov     [r10+24h], edx
0x14000485f  cmp     bx, [r10+2Ah]
0x140004864  jnb     loc_140004917
0x14000486a  mov     rax, [r10+40h]
0x14000486e  mov     cl, [r10+28h]
0x140004872  mov     r9d, r8d
0x140004875  cmp     [r9+rax], cl
0x140004879  jbe     short loc_14000487F
0x14000487b  test    cl, cl
0x14000487d  jnz     short loc_1400048A1
0x14000487f  mov     rax, [r10+38h]
0x140004883  mov     rdx, [rax+r9*8]
0x140004887  test    rdx, rdx
0x14000488a  jz      short loc_1400048A6
0x14000488c  test    [r10+10h], rdx
0x140004890  jz      short loc_1400048A1
0x140004892  mov     rcx, [r10+18h]
0x140004896  mov     rax, rcx
0x140004899  and     rax, rdx
0x14000489c  cmp     rax, rcx
0x14000489f  jz      short loc_1400048A6
0x1400048a1  mov     r11b, bl
0x1400048a4  jmp     short loc_1400048A9
0x1400048a6  mov     r11b, 1
0x1400048a9  mov     rax, [r10+30h]
0x1400048ad  mov     ecx, r8d
0x1400048b0  shr     r9, 5
0x1400048b4  mov     edx, 1
0x1400048b9  shl     edx, cl
0x1400048bb  lea     rcx, [rax+r9*4]
0x1400048bf  mov     eax, [rcx]
0x1400048c1  test    r11b, r11b
0x1400048c4  jz      short loc_1400048CA
0x1400048c6  or      edx, eax
0x1400048c8  jmp     short loc_1400048CE
0x1400048ca  not     edx
0x1400048cc  and     edx, eax
0x1400048ce  mov     [rcx], edx
0x1400048d0  inc     r8d
0x1400048d3  movzx   eax, word ptr [r10+2Ah]
0x1400048d8  cmp     r8d, eax
0x1400048db  jb      short loc_14000486A
0x1400048dd  jmp     short loc_140004917
0x1400048df  movzx   eax, word ptr [r10+2Ah]
0x1400048e4  mov     [r10+24h], ebx
0x1400048e8  mov     [r10+28h], bl
0x1400048ec  mov     [r10+10h], rbx
0x1400048f0  mov     [r10+18h], rbx
0x1400048f4  test    ax, ax
0x1400048f7  jz      short loc_140004917
0x1400048f9  dec     eax
0x1400048fb  mov     ecx, 20h ; ' '
0x140004900  cdq
0x140004901  idiv    ecx
0x140004903  mov     rcx, [r10+30h]; void *
0x140004907  xor     edx, edx; Val
0x140004909  inc     eax
0x14000490b  movsxd  r8, eax
0x14000490e  shl     r8, 2; Size
0x140004912  call    memset
0x140004917  add     rsp, 20h
0x14000491b  pop     rbx
0x14000491c  retn
```
