# McGenControlCallbackV2

- ea: `0x1800455c0`
- end: `0x1800456bf`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002b394`
- `0x1800455c0`

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
0x1800455c0  push    rbx
0x1800455c2  sub     rsp, 20h
0x1800455c6  mov     r10, [rsp+28h+CallbackContext]
0x1800455cb  xor     ebx, ebx
0x1800455cd  test    r10, r10
0x1800455d0  jz      loc_1800456B9
0x1800455d6  test    edx, edx
0x1800455d8  jz      loc_18004567F
0x1800455de  cmp     edx, 1
0x1800455e1  jnz     loc_1800456B9
0x1800455e7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800455ec  mov     [r10+28h], r8b
0x1800455f0  mov     r8d, ebx
0x1800455f3  mov     [r10+18h], rax
0x1800455f7  mov     [r10+10h], r9
0x1800455fb  mov     [r10+24h], edx
0x1800455ff  cmp     bx, [r10+2Ah]
0x180045604  jnb     loc_1800456B9
0x18004560a  mov     rax, [r10+40h]
0x18004560e  mov     cl, [r10+28h]
0x180045612  mov     r9d, r8d
0x180045615  cmp     [r9+rax], cl
0x180045619  jbe     short loc_18004561F
0x18004561b  test    cl, cl
0x18004561d  jnz     short loc_18004563F
0x18004561f  mov     rax, [r10+38h]
0x180045623  mov     rcx, [rax+r9*8]
0x180045627  test    rcx, rcx
0x18004562a  jz      short loc_180045644
0x18004562c  test    [r10+10h], rcx
0x180045630  jz      short loc_18004563F
0x180045632  mov     rax, [r10+18h]
0x180045636  and     rax, rcx
0x180045639  cmp     rax, [r10+18h]
0x18004563d  jz      short loc_180045644
0x18004563f  mov     r11b, bl
0x180045642  jmp     short loc_180045647
0x180045644  mov     r11b, 1
0x180045647  mov     rax, [r10+30h]
0x18004564b  mov     ecx, r8d
0x18004564e  shr     r9, 5
0x180045652  mov     edx, 1
0x180045657  shl     edx, cl
0x180045659  lea     rcx, [rax+r9*4]
0x18004565d  test    r11b, r11b
0x180045660  jz      short loc_180045666
0x180045662  or      edx, [rcx]
0x180045664  jmp     short loc_18004566A
0x180045666  not     edx
0x180045668  and     edx, [rcx]
0x18004566a  mov     [rcx], edx
0x18004566c  inc     r8d
0x18004566f  movzx   eax, word ptr [r10+2Ah]
0x180045674  cmp     r8d, eax
0x180045677  jb      short loc_18004560A
0x180045679  add     rsp, 20h
0x18004567d  pop     rbx
0x18004567e  retn
0x18004567f  mov     [r10+24h], ebx
0x180045683  mov     [r10+28h], bl
0x180045687  mov     [r10+10h], rbx
0x18004568b  mov     [r10+18h], rbx
0x18004568f  cmp     [r10+2Ah], bx
0x180045694  jbe     short loc_1800456B9
0x180045696  movzx   eax, word ptr [r10+2Ah]
0x18004569b  mov     ecx, 20h ; ' '
0x1800456a0  dec     eax
0x1800456a2  cdq
0x1800456a3  idiv    ecx
0x1800456a5  mov     rcx, [r10+30h]; void *
0x1800456a9  xor     edx, edx; Val
0x1800456ab  inc     eax
0x1800456ad  movsxd  r8, eax
0x1800456b0  shl     r8, 2; Size
0x1800456b4  call    memset_0
0x1800456b9  add     rsp, 20h
0x1800456bd  pop     rbx
0x1800456be  retn
```
