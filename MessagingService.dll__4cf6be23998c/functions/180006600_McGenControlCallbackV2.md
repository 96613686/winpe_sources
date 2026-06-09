# McGenControlCallbackV2

- ea: `0x180006600`
- end: `0x180006700`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006600`
- `0x18000aa27`

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
0x180006600  push    rbx
0x180006602  sub     rsp, 20h
0x180006606  mov     r10, [rsp+28h+CallbackContext]
0x18000660b  xor     ebx, ebx
0x18000660d  test    r10, r10
0x180006610  jz      loc_1800066FA
0x180006616  test    edx, edx
0x180006618  jz      loc_1800066BF
0x18000661e  cmp     edx, 1
0x180006621  jnz     loc_1800066FA
0x180006627  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000662c  mov     [r10+28h], r8b
0x180006630  mov     r8d, ebx
0x180006633  mov     [r10+18h], rax
0x180006637  mov     [r10+10h], r9
0x18000663b  mov     [r10+24h], edx
0x18000663f  cmp     bx, [r10+2Ah]
0x180006644  jnb     loc_1800066FA
0x18000664a  mov     rax, [r10+40h]
0x18000664e  mov     cl, [r10+28h]
0x180006652  mov     r9d, r8d
0x180006655  cmp     [r9+rax], cl
0x180006659  jbe     short loc_18000665F
0x18000665b  test    cl, cl
0x18000665d  jnz     short loc_18000667F
0x18000665f  mov     rax, [r10+38h]
0x180006663  mov     rcx, [rax+r9*8]
0x180006667  test    rcx, rcx
0x18000666a  jz      short loc_180006684
0x18000666c  test    [r10+10h], rcx
0x180006670  jz      short loc_18000667F
0x180006672  mov     rax, [r10+18h]
0x180006676  and     rax, rcx
0x180006679  cmp     rax, [r10+18h]
0x18000667d  jz      short loc_180006684
0x18000667f  mov     r11b, bl
0x180006682  jmp     short loc_180006687
0x180006684  mov     r11b, 1
0x180006687  mov     rax, [r10+30h]
0x18000668b  mov     ecx, r8d
0x18000668e  shr     r9, 5
0x180006692  mov     edx, 1
0x180006697  shl     edx, cl
0x180006699  lea     rcx, [rax+r9*4]
0x18000669d  test    r11b, r11b
0x1800066a0  jz      short loc_1800066A6
0x1800066a2  or      edx, [rcx]
0x1800066a4  jmp     short loc_1800066AA
0x1800066a6  not     edx
0x1800066a8  and     edx, [rcx]
0x1800066aa  mov     [rcx], edx
0x1800066ac  inc     r8d
0x1800066af  movzx   eax, word ptr [r10+2Ah]
0x1800066b4  cmp     r8d, eax
0x1800066b7  jb      short loc_18000664A
0x1800066b9  add     rsp, 20h
0x1800066bd  pop     rbx
0x1800066be  retn
0x1800066bf  mov     [r10+24h], ebx
0x1800066c3  mov     [r10+28h], bl
0x1800066c7  mov     [r10+10h], rbx
0x1800066cb  mov     [r10+18h], rbx
0x1800066cf  cmp     [r10+2Ah], bx
0x1800066d4  jbe     short loc_1800066FA
0x1800066d6  movzx   eax, word ptr [r10+2Ah]
0x1800066db  mov     rcx, [r10+30h]; void *
0x1800066df  dec     eax
0x1800066e1  cdq
0x1800066e2  and     edx, 1Fh
0x1800066e5  add     eax, edx
0x1800066e7  xor     edx, edx; Val
0x1800066e9  sar     eax, 5
0x1800066ec  inc     eax
0x1800066ee  movsxd  r8, eax
0x1800066f1  shl     r8, 2; Size
0x1800066f5  call    memset_0
0x1800066fa  add     rsp, 20h
0x1800066fe  pop     rbx
0x1800066ff  retn
```
