# McGenControlCallbackV2

- ea: `0x180004310`
- end: `0x180004410`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004310`
- `0x180006956`

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
0x180004310  push    rbx
0x180004312  sub     rsp, 20h
0x180004316  mov     r10, [rsp+28h+CallbackContext]
0x18000431b  xor     ebx, ebx
0x18000431d  test    r10, r10
0x180004320  jz      loc_18000440A
0x180004326  test    edx, edx
0x180004328  jz      loc_1800043CF
0x18000432e  cmp     edx, 1
0x180004331  jnz     loc_18000440A
0x180004337  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000433c  mov     [r10+28h], r8b
0x180004340  mov     r8d, ebx
0x180004343  mov     [r10+18h], rax
0x180004347  mov     [r10+10h], r9
0x18000434b  mov     [r10+24h], edx
0x18000434f  cmp     bx, [r10+2Ah]
0x180004354  jnb     loc_18000440A
0x18000435a  mov     rax, [r10+40h]
0x18000435e  mov     cl, [r10+28h]
0x180004362  mov     r9d, r8d
0x180004365  cmp     [r9+rax], cl
0x180004369  jbe     short loc_18000436F
0x18000436b  test    cl, cl
0x18000436d  jnz     short loc_18000438F
0x18000436f  mov     rax, [r10+38h]
0x180004373  mov     rcx, [rax+r9*8]
0x180004377  test    rcx, rcx
0x18000437a  jz      short loc_180004394
0x18000437c  test    [r10+10h], rcx
0x180004380  jz      short loc_18000438F
0x180004382  mov     rax, [r10+18h]
0x180004386  and     rax, rcx
0x180004389  cmp     rax, [r10+18h]
0x18000438d  jz      short loc_180004394
0x18000438f  mov     r11b, bl
0x180004392  jmp     short loc_180004397
0x180004394  mov     r11b, 1
0x180004397  mov     rax, [r10+30h]
0x18000439b  mov     ecx, r8d
0x18000439e  shr     r9, 5
0x1800043a2  mov     edx, 1
0x1800043a7  shl     edx, cl
0x1800043a9  lea     rcx, [rax+r9*4]
0x1800043ad  test    r11b, r11b
0x1800043b0  jz      short loc_1800043B6
0x1800043b2  or      edx, [rcx]
0x1800043b4  jmp     short loc_1800043BA
0x1800043b6  not     edx
0x1800043b8  and     edx, [rcx]
0x1800043ba  mov     [rcx], edx
0x1800043bc  inc     r8d
0x1800043bf  movzx   eax, word ptr [r10+2Ah]
0x1800043c4  cmp     r8d, eax
0x1800043c7  jb      short loc_18000435A
0x1800043c9  add     rsp, 20h
0x1800043cd  pop     rbx
0x1800043ce  retn
0x1800043cf  mov     [r10+24h], ebx
0x1800043d3  mov     [r10+28h], bl
0x1800043d7  mov     [r10+10h], rbx
0x1800043db  mov     [r10+18h], rbx
0x1800043df  cmp     [r10+2Ah], bx
0x1800043e4  jbe     short loc_18000440A
0x1800043e6  movzx   eax, word ptr [r10+2Ah]
0x1800043eb  mov     rcx, [r10+30h]; void *
0x1800043ef  dec     eax
0x1800043f1  cdq
0x1800043f2  and     edx, 1Fh
0x1800043f5  add     eax, edx
0x1800043f7  xor     edx, edx; Val
0x1800043f9  sar     eax, 5
0x1800043fc  inc     eax
0x1800043fe  movsxd  r8, eax
0x180004401  shl     r8, 2; Size
0x180004405  call    memset_0
0x18000440a  add     rsp, 20h
0x18000440e  pop     rbx
0x18000440f  retn
```
