# McGenControlCallbackV2

- ea: `0x18000ced0`
- end: `0x18000cfd0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002a28`
- `0x18000ced0`

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
0x18000ced0  push    rbx
0x18000ced2  sub     rsp, 20h
0x18000ced6  mov     r10, [rsp+28h+CallbackContext]
0x18000cedb  xor     ebx, ebx
0x18000cedd  test    r10, r10
0x18000cee0  jz      loc_18000CFCA
0x18000cee6  test    edx, edx
0x18000cee8  jz      loc_18000CF8F
0x18000ceee  cmp     edx, 1
0x18000cef1  jnz     loc_18000CFCA
0x18000cef7  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000cefc  mov     [r10+28h], r8b
0x18000cf00  mov     r8d, ebx
0x18000cf03  mov     [r10+18h], rax
0x18000cf07  mov     [r10+10h], r9
0x18000cf0b  mov     [r10+24h], edx
0x18000cf0f  cmp     bx, [r10+2Ah]
0x18000cf14  jnb     loc_18000CFCA
0x18000cf1a  mov     rax, [r10+40h]
0x18000cf1e  mov     cl, [r10+28h]
0x18000cf22  mov     r9d, r8d
0x18000cf25  cmp     [r9+rax], cl
0x18000cf29  jbe     short loc_18000CF2F
0x18000cf2b  test    cl, cl
0x18000cf2d  jnz     short loc_18000CF4F
0x18000cf2f  mov     rax, [r10+38h]
0x18000cf33  mov     rcx, [rax+r9*8]
0x18000cf37  test    rcx, rcx
0x18000cf3a  jz      short loc_18000CF54
0x18000cf3c  test    [r10+10h], rcx
0x18000cf40  jz      short loc_18000CF4F
0x18000cf42  mov     rax, [r10+18h]
0x18000cf46  and     rax, rcx
0x18000cf49  cmp     rax, [r10+18h]
0x18000cf4d  jz      short loc_18000CF54
0x18000cf4f  mov     r11b, bl
0x18000cf52  jmp     short loc_18000CF57
0x18000cf54  mov     r11b, 1
0x18000cf57  mov     rax, [r10+30h]
0x18000cf5b  mov     ecx, r8d
0x18000cf5e  shr     r9, 5
0x18000cf62  mov     edx, 1
0x18000cf67  shl     edx, cl
0x18000cf69  lea     rcx, [rax+r9*4]
0x18000cf6d  test    r11b, r11b
0x18000cf70  jz      short loc_18000CF76
0x18000cf72  or      edx, [rcx]
0x18000cf74  jmp     short loc_18000CF7A
0x18000cf76  not     edx
0x18000cf78  and     edx, [rcx]
0x18000cf7a  mov     [rcx], edx
0x18000cf7c  inc     r8d
0x18000cf7f  movzx   eax, word ptr [r10+2Ah]
0x18000cf84  cmp     r8d, eax
0x18000cf87  jb      short loc_18000CF1A
0x18000cf89  add     rsp, 20h
0x18000cf8d  pop     rbx
0x18000cf8e  retn
0x18000cf8f  mov     [r10+24h], ebx
0x18000cf93  mov     [r10+28h], bl
0x18000cf97  mov     [r10+10h], rbx
0x18000cf9b  mov     [r10+18h], rbx
0x18000cf9f  cmp     [r10+2Ah], bx
0x18000cfa4  jbe     short loc_18000CFCA
0x18000cfa6  movzx   eax, word ptr [r10+2Ah]
0x18000cfab  mov     rcx, [r10+30h]; void *
0x18000cfaf  dec     eax
0x18000cfb1  cdq
0x18000cfb2  and     edx, 1Fh
0x18000cfb5  add     eax, edx
0x18000cfb7  xor     edx, edx; Val
0x18000cfb9  sar     eax, 5
0x18000cfbc  inc     eax
0x18000cfbe  movsxd  r8, eax
0x18000cfc1  shl     r8, 2; Size
0x18000cfc5  call    memset_0
0x18000cfca  add     rsp, 20h
0x18000cfce  pop     rbx
0x18000cfcf  retn
```
