# McGenControlCallbackV2

- ea: `0x180006fb0`
- end: `0x1800070af`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006fb0`
- `0x18001dfe2`

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
0x180006fb0  push    rbx
0x180006fb2  sub     rsp, 20h
0x180006fb6  mov     r10, [rsp+28h+CallbackContext]
0x180006fbb  xor     ebx, ebx
0x180006fbd  test    r10, r10
0x180006fc0  jz      loc_1800070A9
0x180006fc6  test    edx, edx
0x180006fc8  jz      loc_18000706F
0x180006fce  cmp     edx, 1
0x180006fd1  jnz     loc_1800070A9
0x180006fd7  mov     rax, [rsp+28h+MatchAllKeyword]
0x180006fdc  mov     [r10+28h], r8b
0x180006fe0  mov     r8d, ebx
0x180006fe3  mov     [r10+18h], rax
0x180006fe7  mov     [r10+10h], r9
0x180006feb  mov     [r10+24h], edx
0x180006fef  cmp     bx, [r10+2Ah]
0x180006ff4  jnb     loc_1800070A9
0x180006ffa  mov     rax, [r10+40h]
0x180006ffe  mov     cl, [r10+28h]
0x180007002  mov     r9d, r8d
0x180007005  cmp     [r9+rax], cl
0x180007009  jbe     short loc_18000700F
0x18000700b  test    cl, cl
0x18000700d  jnz     short loc_18000702F
0x18000700f  mov     rax, [r10+38h]
0x180007013  mov     rcx, [rax+r9*8]
0x180007017  test    rcx, rcx
0x18000701a  jz      short loc_180007034
0x18000701c  test    [r10+10h], rcx
0x180007020  jz      short loc_18000702F
0x180007022  mov     rax, [r10+18h]
0x180007026  and     rax, rcx
0x180007029  cmp     rax, [r10+18h]
0x18000702d  jz      short loc_180007034
0x18000702f  mov     r11b, bl
0x180007032  jmp     short loc_180007037
0x180007034  mov     r11b, 1
0x180007037  mov     rax, [r10+30h]
0x18000703b  mov     ecx, r8d
0x18000703e  shr     r9, 5
0x180007042  mov     edx, 1
0x180007047  shl     edx, cl
0x180007049  lea     rcx, [rax+r9*4]
0x18000704d  test    r11b, r11b
0x180007050  jz      short loc_180007056
0x180007052  or      edx, [rcx]
0x180007054  jmp     short loc_18000705A
0x180007056  not     edx
0x180007058  and     edx, [rcx]
0x18000705a  mov     [rcx], edx
0x18000705c  inc     r8d
0x18000705f  movzx   eax, word ptr [r10+2Ah]
0x180007064  cmp     r8d, eax
0x180007067  jb      short loc_180006FFA
0x180007069  add     rsp, 20h
0x18000706d  pop     rbx
0x18000706e  retn
0x18000706f  mov     [r10+24h], ebx
0x180007073  mov     [r10+28h], bl
0x180007077  mov     [r10+10h], rbx
0x18000707b  mov     [r10+18h], rbx
0x18000707f  cmp     [r10+2Ah], bx
0x180007084  jbe     short loc_1800070A9
0x180007086  movzx   eax, word ptr [r10+2Ah]
0x18000708b  mov     ecx, 20h ; ' '
0x180007090  dec     eax
0x180007092  cdq
0x180007093  idiv    ecx
0x180007095  mov     rcx, [r10+30h]; void *
0x180007099  xor     edx, edx; Val
0x18000709b  inc     eax
0x18000709d  movsxd  r8, eax
0x1800070a0  shl     r8, 2; Size
0x1800070a4  call    memset_0
0x1800070a9  add     rsp, 20h
0x1800070ad  pop     rbx
0x1800070ae  retn
```
