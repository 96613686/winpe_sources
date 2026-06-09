# EnableCallback

- ea: `0x1800767e0`
- end: `0x1800768e7`
- name: `EnableCallback`
- size: `263`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800767e0`
- `0x18007b9de`

## pseudocode

```c
void __fastcall EnableCallback(
        LPCGUID SourceId,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        unsigned __int16 *CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // r9
  __int64 v9; // rdx
  bool v10; // r9
  int v11; // edx
  int *v12; // r11
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
          v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7);
          v10 = (*(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8)
             && (!v9
              || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3));
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
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((CallbackContext[21] - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x1800767e0  push    rbx
0x1800767e2  sub     rsp, 20h
0x1800767e6  mov     r10, [rsp+28h+CallbackContext]
0x1800767eb  xor     ebx, ebx
0x1800767ed  test    r10, r10
0x1800767f0  jz      loc_1800768E1
0x1800767f6  test    edx, edx
0x1800767f8  jz      loc_1800768A6
0x1800767fe  cmp     edx, 1
0x180076801  jnz     loc_1800768E1
0x180076807  mov     rax, [rsp+28h+MatchAllKeyword]
0x18007680c  mov     [r10+28h], r8b
0x180076810  mov     r8d, ebx
0x180076813  mov     [r10+18h], rax
0x180076817  mov     [r10+10h], r9
0x18007681b  mov     [r10+24h], edx
0x18007681f  cmp     bx, [r10+2Ah]
0x180076824  jnb     loc_1800768E1
0x18007682a  mov     rax, [r10+38h]
0x18007682e  mov     r9b, [r10+28h]
0x180076832  mov     ecx, r8d
0x180076835  mov     rdx, [rax+rcx*8]
0x180076839  mov     rax, [r10+40h]
0x18007683d  cmp     [rcx+rax], r9b
0x180076841  jbe     short loc_180076848
0x180076843  test    r9b, r9b
0x180076846  jnz     short loc_180076860
0x180076848  test    rdx, rdx
0x18007684b  jz      short loc_180076865
0x18007684d  test    [r10+10h], rdx
0x180076851  jz      short loc_180076860
0x180076853  mov     rax, [r10+18h]
0x180076857  and     rax, rdx
0x18007685a  cmp     rax, [r10+18h]
0x18007685e  jz      short loc_180076865
0x180076860  mov     r9b, bl
0x180076863  jmp     short loc_180076868
0x180076865  mov     r9b, 1
0x180076868  mov     rax, [r10+30h]
0x18007686c  mov     ecx, r8d
0x18007686f  mov     edx, 1
0x180076874  shl     edx, cl
0x180076876  mov     ecx, r8d
0x180076879  shr     rcx, 5
0x18007687d  lea     r11, [rax+rcx*4]
0x180076881  test    r9b, r9b
0x180076884  jz      short loc_18007688B
0x180076886  or      edx, [r11]
0x180076889  jmp     short loc_180076890
0x18007688b  not     edx
0x18007688d  and     edx, [r11]
0x180076890  mov     [r11], edx
0x180076893  inc     r8d
0x180076896  movzx   eax, word ptr [r10+2Ah]
0x18007689b  cmp     r8d, eax
0x18007689e  jb      short loc_18007682A
0x1800768a0  add     rsp, 20h
0x1800768a4  pop     rbx
0x1800768a5  retn
0x1800768a6  mov     [r10+24h], ebx
0x1800768aa  mov     [r10+28h], bl
0x1800768ae  mov     [r10+10h], rbx
0x1800768b2  mov     [r10+18h], rbx
0x1800768b6  cmp     [r10+2Ah], bx
0x1800768bb  jbe     short loc_1800768E1
0x1800768bd  movzx   eax, word ptr [r10+2Ah]
0x1800768c2  mov     rcx, [r10+30h]; void *
0x1800768c6  dec     eax
0x1800768c8  cdq
0x1800768c9  and     edx, 1Fh
0x1800768cc  add     eax, edx
0x1800768ce  xor     edx, edx; Val
0x1800768d0  sar     eax, 5
0x1800768d3  inc     eax
0x1800768d5  movsxd  r8, eax
0x1800768d8  shl     r8, 2; Size
0x1800768dc  call    memset
0x1800768e1  add     rsp, 20h
0x1800768e5  pop     rbx
0x1800768e6  retn
```
