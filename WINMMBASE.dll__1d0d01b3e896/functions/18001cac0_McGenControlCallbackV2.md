# McGenControlCallbackV2

- ea: `0x18001cac0`
- end: `0x18001cbbf`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001102a`
- `0x18001cac0`

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
0x18001cac0  push    rbx
0x18001cac2  sub     rsp, 20h
0x18001cac6  mov     r10, [rsp+28h+CallbackContext]
0x18001cacb  xor     ebx, ebx
0x18001cacd  test    r10, r10
0x18001cad0  jz      loc_18001CBB9
0x18001cad6  test    edx, edx
0x18001cad8  jz      loc_18001CB7F
0x18001cade  cmp     edx, 1
0x18001cae1  jnz     loc_18001CBB9
0x18001cae7  mov     rax, [rsp+28h+MatchAllKeyword]
0x18001caec  mov     [r10+28h], r8b
0x18001caf0  mov     r8d, ebx
0x18001caf3  mov     [r10+18h], rax
0x18001caf7  mov     [r10+10h], r9
0x18001cafb  mov     [r10+24h], edx
0x18001caff  cmp     bx, [r10+2Ah]
0x18001cb04  jnb     loc_18001CBB9
0x18001cb0a  mov     rax, [r10+40h]
0x18001cb0e  mov     cl, [r10+28h]
0x18001cb12  mov     r9d, r8d
0x18001cb15  cmp     [r9+rax], cl
0x18001cb19  jbe     short loc_18001CB1F
0x18001cb1b  test    cl, cl
0x18001cb1d  jnz     short loc_18001CB3F
0x18001cb1f  mov     rax, [r10+38h]
0x18001cb23  mov     rcx, [rax+r9*8]
0x18001cb27  test    rcx, rcx
0x18001cb2a  jz      short loc_18001CB44
0x18001cb2c  test    [r10+10h], rcx
0x18001cb30  jz      short loc_18001CB3F
0x18001cb32  mov     rax, [r10+18h]
0x18001cb36  and     rax, rcx
0x18001cb39  cmp     rax, [r10+18h]
0x18001cb3d  jz      short loc_18001CB44
0x18001cb3f  mov     r11b, bl
0x18001cb42  jmp     short loc_18001CB47
0x18001cb44  mov     r11b, 1
0x18001cb47  mov     rax, [r10+30h]
0x18001cb4b  mov     ecx, r8d
0x18001cb4e  shr     r9, 5
0x18001cb52  mov     edx, 1
0x18001cb57  shl     edx, cl
0x18001cb59  lea     rcx, [rax+r9*4]
0x18001cb5d  test    r11b, r11b
0x18001cb60  jz      short loc_18001CB66
0x18001cb62  or      edx, [rcx]
0x18001cb64  jmp     short loc_18001CB6A
0x18001cb66  not     edx
0x18001cb68  and     edx, [rcx]
0x18001cb6a  mov     [rcx], edx
0x18001cb6c  inc     r8d
0x18001cb6f  movzx   eax, word ptr [r10+2Ah]
0x18001cb74  cmp     r8d, eax
0x18001cb77  jb      short loc_18001CB0A
0x18001cb79  add     rsp, 20h
0x18001cb7d  pop     rbx
0x18001cb7e  retn
0x18001cb7f  mov     [r10+24h], ebx
0x18001cb83  mov     [r10+28h], bl
0x18001cb87  mov     [r10+10h], rbx
0x18001cb8b  mov     [r10+18h], rbx
0x18001cb8f  cmp     [r10+2Ah], bx
0x18001cb94  jbe     short loc_18001CBB9
0x18001cb96  movzx   eax, word ptr [r10+2Ah]
0x18001cb9b  mov     ecx, 20h ; ' '
0x18001cba0  dec     eax
0x18001cba2  cdq
0x18001cba3  idiv    ecx
0x18001cba5  mov     rcx, [r10+30h]; void *
0x18001cba9  xor     edx, edx; Val
0x18001cbab  inc     eax
0x18001cbad  movsxd  r8, eax
0x18001cbb0  shl     r8, 2; Size
0x18001cbb4  call    memset_0
0x18001cbb9  add     rsp, 20h
0x18001cbbd  pop     rbx
0x18001cbbe  retn
```
