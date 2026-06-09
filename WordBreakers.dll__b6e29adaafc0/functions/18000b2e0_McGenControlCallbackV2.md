# McGenControlCallbackV2

- ea: `0x18000b2e0`
- end: `0x18000b3e0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b2e0`
- `0x18000b612`

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
0x18000b2e0  push    rbx
0x18000b2e2  sub     rsp, 20h
0x18000b2e6  mov     r10, [rsp+28h+CallbackContext]
0x18000b2eb  xor     ebx, ebx
0x18000b2ed  test    r10, r10
0x18000b2f0  jz      loc_18000B3DA
0x18000b2f6  test    edx, edx
0x18000b2f8  jz      loc_18000B39F
0x18000b2fe  cmp     edx, 1
0x18000b301  jnz     loc_18000B3DA
0x18000b307  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000b30c  mov     [r10+28h], r8b
0x18000b310  mov     r8d, ebx
0x18000b313  mov     [r10+18h], rax
0x18000b317  mov     [r10+10h], r9
0x18000b31b  mov     [r10+24h], edx
0x18000b31f  cmp     bx, [r10+2Ah]
0x18000b324  jnb     loc_18000B3DA
0x18000b32a  mov     rax, [r10+40h]
0x18000b32e  mov     cl, [r10+28h]
0x18000b332  mov     r9d, r8d
0x18000b335  cmp     [r9+rax], cl
0x18000b339  jbe     short loc_18000B33F
0x18000b33b  test    cl, cl
0x18000b33d  jnz     short loc_18000B35F
0x18000b33f  mov     rax, [r10+38h]
0x18000b343  mov     rcx, [rax+r9*8]
0x18000b347  test    rcx, rcx
0x18000b34a  jz      short loc_18000B364
0x18000b34c  test    [r10+10h], rcx
0x18000b350  jz      short loc_18000B35F
0x18000b352  mov     rax, [r10+18h]
0x18000b356  and     rax, rcx
0x18000b359  cmp     rax, [r10+18h]
0x18000b35d  jz      short loc_18000B364
0x18000b35f  mov     r11b, bl
0x18000b362  jmp     short loc_18000B367
0x18000b364  mov     r11b, 1
0x18000b367  mov     rax, [r10+30h]
0x18000b36b  mov     ecx, r8d
0x18000b36e  shr     r9, 5
0x18000b372  mov     edx, 1
0x18000b377  shl     edx, cl
0x18000b379  lea     rcx, [rax+r9*4]
0x18000b37d  test    r11b, r11b
0x18000b380  jz      short loc_18000B386
0x18000b382  or      edx, [rcx]
0x18000b384  jmp     short loc_18000B38A
0x18000b386  not     edx
0x18000b388  and     edx, [rcx]
0x18000b38a  mov     [rcx], edx
0x18000b38c  inc     r8d
0x18000b38f  movzx   eax, word ptr [r10+2Ah]
0x18000b394  cmp     r8d, eax
0x18000b397  jb      short loc_18000B32A
0x18000b399  add     rsp, 20h
0x18000b39d  pop     rbx
0x18000b39e  retn
0x18000b39f  mov     [r10+24h], ebx
0x18000b3a3  mov     [r10+28h], bl
0x18000b3a7  mov     [r10+10h], rbx
0x18000b3ab  mov     [r10+18h], rbx
0x18000b3af  cmp     [r10+2Ah], bx
0x18000b3b4  jbe     short loc_18000B3DA
0x18000b3b6  movzx   eax, word ptr [r10+2Ah]
0x18000b3bb  mov     rcx, [r10+30h]; void *
0x18000b3bf  dec     eax
0x18000b3c1  cdq
0x18000b3c2  and     edx, 1Fh
0x18000b3c5  add     eax, edx
0x18000b3c7  xor     edx, edx; Val
0x18000b3c9  sar     eax, 5
0x18000b3cc  inc     eax
0x18000b3ce  movsxd  r8, eax
0x18000b3d1  shl     r8, 2; Size
0x18000b3d5  call    memset_0
0x18000b3da  add     rsp, 20h
0x18000b3de  pop     rbx
0x18000b3df  retn
```
