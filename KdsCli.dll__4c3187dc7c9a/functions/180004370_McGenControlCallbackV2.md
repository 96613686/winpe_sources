# McGenControlCallbackV2

- ea: `0x180004370`
- end: `0x180004470`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f7c`
- `0x180004370`

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
0x180004370  push    rbx
0x180004372  sub     rsp, 20h
0x180004376  mov     r10, [rsp+28h+CallbackContext]
0x18000437b  xor     ebx, ebx
0x18000437d  test    r10, r10
0x180004380  jz      loc_18000446A
0x180004386  test    edx, edx
0x180004388  jz      loc_18000442F
0x18000438e  cmp     edx, 1
0x180004391  jnz     loc_18000446A
0x180004397  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000439c  mov     [r10+28h], r8b
0x1800043a0  mov     r8d, ebx
0x1800043a3  mov     [r10+18h], rax
0x1800043a7  mov     [r10+10h], r9
0x1800043ab  mov     [r10+24h], edx
0x1800043af  cmp     bx, [r10+2Ah]
0x1800043b4  jnb     loc_18000446A
0x1800043ba  mov     rax, [r10+40h]
0x1800043be  mov     cl, [r10+28h]
0x1800043c2  mov     r9d, r8d
0x1800043c5  cmp     [r9+rax], cl
0x1800043c9  jbe     short loc_1800043CF
0x1800043cb  test    cl, cl
0x1800043cd  jnz     short loc_1800043EF
0x1800043cf  mov     rax, [r10+38h]
0x1800043d3  mov     rcx, [rax+r9*8]
0x1800043d7  test    rcx, rcx
0x1800043da  jz      short loc_1800043F4
0x1800043dc  test    [r10+10h], rcx
0x1800043e0  jz      short loc_1800043EF
0x1800043e2  mov     rax, [r10+18h]
0x1800043e6  and     rax, rcx
0x1800043e9  cmp     rax, [r10+18h]
0x1800043ed  jz      short loc_1800043F4
0x1800043ef  mov     r11b, bl
0x1800043f2  jmp     short loc_1800043F7
0x1800043f4  mov     r11b, 1
0x1800043f7  mov     rax, [r10+30h]
0x1800043fb  mov     ecx, r8d
0x1800043fe  shr     r9, 5
0x180004402  mov     edx, 1
0x180004407  shl     edx, cl
0x180004409  lea     rcx, [rax+r9*4]
0x18000440d  test    r11b, r11b
0x180004410  jz      short loc_180004416
0x180004412  or      edx, [rcx]
0x180004414  jmp     short loc_18000441A
0x180004416  not     edx
0x180004418  and     edx, [rcx]
0x18000441a  mov     [rcx], edx
0x18000441c  inc     r8d
0x18000441f  movzx   eax, word ptr [r10+2Ah]
0x180004424  cmp     r8d, eax
0x180004427  jb      short loc_1800043BA
0x180004429  add     rsp, 20h
0x18000442d  pop     rbx
0x18000442e  retn
0x18000442f  mov     [r10+24h], ebx
0x180004433  mov     [r10+28h], bl
0x180004437  mov     [r10+10h], rbx
0x18000443b  mov     [r10+18h], rbx
0x18000443f  cmp     [r10+2Ah], bx
0x180004444  jbe     short loc_18000446A
0x180004446  movzx   eax, word ptr [r10+2Ah]
0x18000444b  mov     rcx, [r10+30h]; void *
0x18000444f  dec     eax
0x180004451  cdq
0x180004452  and     edx, 1Fh
0x180004455  add     eax, edx
0x180004457  xor     edx, edx; Val
0x180004459  sar     eax, 5
0x18000445c  inc     eax
0x18000445e  movsxd  r8, eax
0x180004461  shl     r8, 2; Size
0x180004465  call    memset_0
0x18000446a  add     rsp, 20h
0x18000446e  pop     rbx
0x18000446f  retn
```
