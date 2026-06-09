# McGenControlCallbackV2

- ea: `0x1400069b0`
- end: `0x140006ab0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400023f3`
- `0x1400069b0`

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
0x1400069b0  push    rbx
0x1400069b2  sub     rsp, 20h
0x1400069b6  mov     r10, [rsp+28h+CallbackContext]
0x1400069bb  xor     ebx, ebx
0x1400069bd  test    r10, r10
0x1400069c0  jz      loc_140006AAA
0x1400069c6  test    edx, edx
0x1400069c8  jz      loc_140006A6F
0x1400069ce  cmp     edx, 1
0x1400069d1  jnz     loc_140006AAA
0x1400069d7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400069dc  mov     [r10+28h], r8b
0x1400069e0  mov     r8d, ebx
0x1400069e3  mov     [r10+18h], rax
0x1400069e7  mov     [r10+10h], r9
0x1400069eb  mov     [r10+24h], edx
0x1400069ef  cmp     bx, [r10+2Ah]
0x1400069f4  jnb     loc_140006AAA
0x1400069fa  mov     rax, [r10+40h]
0x1400069fe  mov     cl, [r10+28h]
0x140006a02  mov     r9d, r8d
0x140006a05  cmp     [r9+rax], cl
0x140006a09  jbe     short loc_140006A0F
0x140006a0b  test    cl, cl
0x140006a0d  jnz     short loc_140006A2F
0x140006a0f  mov     rax, [r10+38h]
0x140006a13  mov     rcx, [rax+r9*8]
0x140006a17  test    rcx, rcx
0x140006a1a  jz      short loc_140006A34
0x140006a1c  test    [r10+10h], rcx
0x140006a20  jz      short loc_140006A2F
0x140006a22  mov     rax, [r10+18h]
0x140006a26  and     rax, rcx
0x140006a29  cmp     rax, [r10+18h]
0x140006a2d  jz      short loc_140006A34
0x140006a2f  mov     r11b, bl
0x140006a32  jmp     short loc_140006A37
0x140006a34  mov     r11b, 1
0x140006a37  mov     rax, [r10+30h]
0x140006a3b  mov     ecx, r8d
0x140006a3e  shr     r9, 5
0x140006a42  mov     edx, 1
0x140006a47  shl     edx, cl
0x140006a49  lea     rcx, [rax+r9*4]
0x140006a4d  test    r11b, r11b
0x140006a50  jz      short loc_140006A56
0x140006a52  or      edx, [rcx]
0x140006a54  jmp     short loc_140006A5A
0x140006a56  not     edx
0x140006a58  and     edx, [rcx]
0x140006a5a  mov     [rcx], edx
0x140006a5c  inc     r8d
0x140006a5f  movzx   eax, word ptr [r10+2Ah]
0x140006a64  cmp     r8d, eax
0x140006a67  jb      short loc_1400069FA
0x140006a69  add     rsp, 20h
0x140006a6d  pop     rbx
0x140006a6e  retn
0x140006a6f  mov     [r10+24h], ebx
0x140006a73  mov     [r10+28h], bl
0x140006a77  mov     [r10+10h], rbx
0x140006a7b  mov     [r10+18h], rbx
0x140006a7f  cmp     [r10+2Ah], bx
0x140006a84  jbe     short loc_140006AAA
0x140006a86  movzx   eax, word ptr [r10+2Ah]
0x140006a8b  mov     rcx, [r10+30h]; void *
0x140006a8f  dec     eax
0x140006a91  cdq
0x140006a92  and     edx, 1Fh
0x140006a95  add     eax, edx
0x140006a97  xor     edx, edx; Val
0x140006a99  sar     eax, 5
0x140006a9c  inc     eax
0x140006a9e  movsxd  r8, eax
0x140006aa1  shl     r8, 2; Size
0x140006aa5  call    memset_0
0x140006aaa  add     rsp, 20h
0x140006aae  pop     rbx
0x140006aaf  retn
```
