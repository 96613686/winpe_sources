# McGenControlCallbackV2

- ea: `0x140010790`
- end: `0x14001088e`
- name: `McGenControlCallbackV2`
- size: `254`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140010790`
- `0x140013d40`

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
0x140010790  push    rbx
0x140010792  sub     rsp, 20h
0x140010796  mov     r10, [rsp+28h+CallbackContext]
0x14001079b  xor     ebx, ebx
0x14001079d  test    r10, r10
0x1400107a0  jz      loc_140010887
0x1400107a6  test    edx, edx
0x1400107a8  jz      loc_14001084F
0x1400107ae  cmp     edx, 1
0x1400107b1  jnz     loc_140010887
0x1400107b7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400107bc  mov     [r10+28h], r8b
0x1400107c0  mov     r8d, ebx
0x1400107c3  mov     [r10+18h], rax
0x1400107c7  mov     [r10+10h], r9
0x1400107cb  mov     [r10+24h], edx
0x1400107cf  cmp     bx, [r10+2Ah]
0x1400107d4  jnb     loc_140010887
0x1400107da  mov     rax, [r10+40h]
0x1400107de  mov     cl, [r10+28h]
0x1400107e2  mov     r9d, r8d
0x1400107e5  cmp     [r9+rax], cl
0x1400107e9  jbe     short loc_1400107EF
0x1400107eb  test    cl, cl
0x1400107ed  jnz     short loc_140010811
0x1400107ef  mov     rax, [r10+38h]
0x1400107f3  mov     rdx, [rax+r9*8]
0x1400107f7  test    rdx, rdx
0x1400107fa  jz      short loc_140010816
0x1400107fc  test    [r10+10h], rdx
0x140010800  jz      short loc_140010811
0x140010802  mov     rcx, [r10+18h]
0x140010806  mov     rax, rcx
0x140010809  and     rax, rdx
0x14001080c  cmp     rax, rcx
0x14001080f  jz      short loc_140010816
0x140010811  mov     r11b, bl
0x140010814  jmp     short loc_140010819
0x140010816  mov     r11b, 1
0x140010819  mov     rax, [r10+30h]
0x14001081d  mov     ecx, r8d
0x140010820  shr     r9, 5
0x140010824  mov     edx, 1
0x140010829  shl     edx, cl
0x14001082b  lea     rcx, [rax+r9*4]
0x14001082f  mov     eax, [rcx]
0x140010831  test    r11b, r11b
0x140010834  jz      short loc_14001083A
0x140010836  or      edx, eax
0x140010838  jmp     short loc_14001083E
0x14001083a  not     edx
0x14001083c  and     edx, eax
0x14001083e  mov     [rcx], edx
0x140010840  inc     r8d
0x140010843  movzx   eax, word ptr [r10+2Ah]
0x140010848  cmp     r8d, eax
0x14001084b  jb      short loc_1400107DA
0x14001084d  jmp     short loc_140010887
0x14001084f  movzx   eax, word ptr [r10+2Ah]
0x140010854  mov     [r10+24h], ebx
0x140010858  mov     [r10+28h], bl
0x14001085c  mov     [r10+10h], rbx
0x140010860  mov     [r10+18h], rbx
0x140010864  test    ax, ax
0x140010867  jz      short loc_140010887
0x140010869  dec     eax
0x14001086b  mov     ecx, 20h ; ' '
0x140010870  cdq
0x140010871  idiv    ecx
0x140010873  mov     rcx, [r10+30h]; void *
0x140010877  xor     edx, edx; Val
0x140010879  inc     eax
0x14001087b  movsxd  r8, eax
0x14001087e  shl     r8, 2; Size
0x140010882  call    memset
0x140010887  add     rsp, 20h
0x14001088b  pop     rbx
0x14001088c  retn
```
