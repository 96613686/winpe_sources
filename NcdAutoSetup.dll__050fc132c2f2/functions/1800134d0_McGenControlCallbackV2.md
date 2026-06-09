# McGenControlCallbackV2

- ea: `0x1800134d0`
- end: `0x1800135d0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800134d0`
- `0x18001380e`

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
0x1800134d0  push    rbx
0x1800134d2  sub     rsp, 20h
0x1800134d6  mov     r10, [rsp+28h+CallbackContext]
0x1800134db  xor     ebx, ebx
0x1800134dd  test    r10, r10
0x1800134e0  jz      loc_1800135CA
0x1800134e6  test    edx, edx
0x1800134e8  jz      loc_18001358F
0x1800134ee  cmp     edx, 1
0x1800134f1  jnz     loc_1800135CA
0x1800134f7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800134fc  mov     [r10+28h], r8b
0x180013500  mov     r8d, ebx
0x180013503  mov     [r10+18h], rax
0x180013507  mov     [r10+10h], r9
0x18001350b  mov     [r10+24h], edx
0x18001350f  cmp     bx, [r10+2Ah]
0x180013514  jnb     loc_1800135CA
0x18001351a  mov     rax, [r10+40h]
0x18001351e  mov     cl, [r10+28h]
0x180013522  mov     r9d, r8d
0x180013525  cmp     [r9+rax], cl
0x180013529  jbe     short loc_18001352F
0x18001352b  test    cl, cl
0x18001352d  jnz     short loc_18001354F
0x18001352f  mov     rax, [r10+38h]
0x180013533  mov     rcx, [rax+r9*8]
0x180013537  test    rcx, rcx
0x18001353a  jz      short loc_180013554
0x18001353c  test    [r10+10h], rcx
0x180013540  jz      short loc_18001354F
0x180013542  mov     rax, [r10+18h]
0x180013546  and     rax, rcx
0x180013549  cmp     rax, [r10+18h]
0x18001354d  jz      short loc_180013554
0x18001354f  mov     r11b, bl
0x180013552  jmp     short loc_180013557
0x180013554  mov     r11b, 1
0x180013557  mov     rax, [r10+30h]
0x18001355b  mov     ecx, r8d
0x18001355e  shr     r9, 5
0x180013562  mov     edx, 1
0x180013567  shl     edx, cl
0x180013569  lea     rcx, [rax+r9*4]
0x18001356d  test    r11b, r11b
0x180013570  jz      short loc_180013576
0x180013572  or      edx, [rcx]
0x180013574  jmp     short loc_18001357A
0x180013576  not     edx
0x180013578  and     edx, [rcx]
0x18001357a  mov     [rcx], edx
0x18001357c  inc     r8d
0x18001357f  movzx   eax, word ptr [r10+2Ah]
0x180013584  cmp     r8d, eax
0x180013587  jb      short loc_18001351A
0x180013589  add     rsp, 20h
0x18001358d  pop     rbx
0x18001358e  retn
0x18001358f  mov     [r10+24h], ebx
0x180013593  mov     [r10+28h], bl
0x180013597  mov     [r10+10h], rbx
0x18001359b  mov     [r10+18h], rbx
0x18001359f  cmp     [r10+2Ah], bx
0x1800135a4  jbe     short loc_1800135CA
0x1800135a6  movzx   eax, word ptr [r10+2Ah]
0x1800135ab  mov     rcx, [r10+30h]; void *
0x1800135af  dec     eax
0x1800135b1  cdq
0x1800135b2  and     edx, 1Fh
0x1800135b5  add     eax, edx
0x1800135b7  xor     edx, edx; Val
0x1800135b9  sar     eax, 5
0x1800135bc  inc     eax
0x1800135be  movsxd  r8, eax
0x1800135c1  shl     r8, 2; Size
0x1800135c5  call    memset_0
0x1800135ca  add     rsp, 20h
0x1800135ce  pop     rbx
0x1800135cf  retn
```
