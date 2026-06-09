# McGenControlCallbackV2

- ea: `0x180006380`
- end: `0x180006480`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001fd4`
- `0x180006380`

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
0x180006380  push    rbx
0x180006382  sub     rsp, 20h
0x180006386  mov     r10, [rsp+28h+CallbackContext]
0x18000638b  xor     ebx, ebx
0x18000638d  test    r10, r10
0x180006390  jz      loc_18000647A
0x180006396  test    edx, edx
0x180006398  jz      loc_18000643F
0x18000639e  cmp     edx, 1
0x1800063a1  jnz     loc_18000647A
0x1800063a7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800063ac  mov     [r10+28h], r8b
0x1800063b0  mov     r8d, ebx
0x1800063b3  mov     [r10+18h], rax
0x1800063b7  mov     [r10+10h], r9
0x1800063bb  mov     [r10+24h], edx
0x1800063bf  cmp     bx, [r10+2Ah]
0x1800063c4  jnb     loc_18000647A
0x1800063ca  mov     rax, [r10+40h]
0x1800063ce  mov     cl, [r10+28h]
0x1800063d2  mov     r9d, r8d
0x1800063d5  cmp     [r9+rax], cl
0x1800063d9  jbe     short loc_1800063DF
0x1800063db  test    cl, cl
0x1800063dd  jnz     short loc_1800063FF
0x1800063df  mov     rax, [r10+38h]
0x1800063e3  mov     rcx, [rax+r9*8]
0x1800063e7  test    rcx, rcx
0x1800063ea  jz      short loc_180006404
0x1800063ec  test    [r10+10h], rcx
0x1800063f0  jz      short loc_1800063FF
0x1800063f2  mov     rax, [r10+18h]
0x1800063f6  and     rax, rcx
0x1800063f9  cmp     rax, [r10+18h]
0x1800063fd  jz      short loc_180006404
0x1800063ff  mov     r11b, bl
0x180006402  jmp     short loc_180006407
0x180006404  mov     r11b, 1
0x180006407  mov     rax, [r10+30h]
0x18000640b  mov     ecx, r8d
0x18000640e  shr     r9, 5
0x180006412  mov     edx, 1
0x180006417  shl     edx, cl
0x180006419  lea     rcx, [rax+r9*4]
0x18000641d  test    r11b, r11b
0x180006420  jz      short loc_180006426
0x180006422  or      edx, [rcx]
0x180006424  jmp     short loc_18000642A
0x180006426  not     edx
0x180006428  and     edx, [rcx]
0x18000642a  mov     [rcx], edx
0x18000642c  inc     r8d
0x18000642f  movzx   eax, word ptr [r10+2Ah]
0x180006434  cmp     r8d, eax
0x180006437  jb      short loc_1800063CA
0x180006439  add     rsp, 20h
0x18000643d  pop     rbx
0x18000643e  retn
0x18000643f  mov     [r10+24h], ebx
0x180006443  mov     [r10+28h], bl
0x180006447  mov     [r10+10h], rbx
0x18000644b  mov     [r10+18h], rbx
0x18000644f  cmp     [r10+2Ah], bx
0x180006454  jbe     short loc_18000647A
0x180006456  movzx   eax, word ptr [r10+2Ah]
0x18000645b  mov     rcx, [r10+30h]; void *
0x18000645f  dec     eax
0x180006461  cdq
0x180006462  and     edx, 1Fh
0x180006465  add     eax, edx
0x180006467  xor     edx, edx; Val
0x180006469  sar     eax, 5
0x18000646c  inc     eax
0x18000646e  movsxd  r8, eax
0x180006471  shl     r8, 2; Size
0x180006475  call    memset_0
0x18000647a  add     rsp, 20h
0x18000647e  pop     rbx
0x18000647f  retn
```
