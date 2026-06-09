# McGenControlCallbackV2

- ea: `0x180010180`
- end: `0x18001027f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010180`
- `0x1800119c2`

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
0x180010180  push    rbx
0x180010182  sub     rsp, 20h
0x180010186  mov     r10, [rsp+28h+CallbackContext]
0x18001018b  xor     ebx, ebx
0x18001018d  test    r10, r10
0x180010190  jz      loc_180010279
0x180010196  test    edx, edx
0x180010198  jz      loc_18001023F
0x18001019e  cmp     edx, 1
0x1800101a1  jnz     loc_180010279
0x1800101a7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800101ac  mov     [r10+28h], r8b
0x1800101b0  mov     r8d, ebx
0x1800101b3  mov     [r10+18h], rax
0x1800101b7  mov     [r10+10h], r9
0x1800101bb  mov     [r10+24h], edx
0x1800101bf  cmp     bx, [r10+2Ah]
0x1800101c4  jnb     loc_180010279
0x1800101ca  mov     rax, [r10+40h]
0x1800101ce  mov     cl, [r10+28h]
0x1800101d2  mov     r9d, r8d
0x1800101d5  cmp     [r9+rax], cl
0x1800101d9  jbe     short loc_1800101DF
0x1800101db  test    cl, cl
0x1800101dd  jnz     short loc_1800101FF
0x1800101df  mov     rax, [r10+38h]
0x1800101e3  mov     rcx, [rax+r9*8]
0x1800101e7  test    rcx, rcx
0x1800101ea  jz      short loc_180010204
0x1800101ec  test    [r10+10h], rcx
0x1800101f0  jz      short loc_1800101FF
0x1800101f2  mov     rax, [r10+18h]
0x1800101f6  and     rax, rcx
0x1800101f9  cmp     rax, [r10+18h]
0x1800101fd  jz      short loc_180010204
0x1800101ff  mov     r11b, bl
0x180010202  jmp     short loc_180010207
0x180010204  mov     r11b, 1
0x180010207  mov     rax, [r10+30h]
0x18001020b  mov     ecx, r8d
0x18001020e  shr     r9, 5
0x180010212  mov     edx, 1
0x180010217  shl     edx, cl
0x180010219  lea     rcx, [rax+r9*4]
0x18001021d  test    r11b, r11b
0x180010220  jz      short loc_180010226
0x180010222  or      edx, [rcx]
0x180010224  jmp     short loc_18001022A
0x180010226  not     edx
0x180010228  and     edx, [rcx]
0x18001022a  mov     [rcx], edx
0x18001022c  inc     r8d
0x18001022f  movzx   eax, word ptr [r10+2Ah]
0x180010234  cmp     r8d, eax
0x180010237  jb      short loc_1800101CA
0x180010239  add     rsp, 20h
0x18001023d  pop     rbx
0x18001023e  retn
0x18001023f  mov     [r10+24h], ebx
0x180010243  mov     [r10+28h], bl
0x180010247  mov     [r10+10h], rbx
0x18001024b  mov     [r10+18h], rbx
0x18001024f  cmp     [r10+2Ah], bx
0x180010254  jbe     short loc_180010279
0x180010256  movzx   eax, word ptr [r10+2Ah]
0x18001025b  mov     ecx, 20h ; ' '
0x180010260  dec     eax
0x180010262  cdq
0x180010263  idiv    ecx
0x180010265  mov     rcx, [r10+30h]; void *
0x180010269  xor     edx, edx; Val
0x18001026b  inc     eax
0x18001026d  movsxd  r8, eax
0x180010270  shl     r8, 2; Size
0x180010274  call    memset_0
0x180010279  add     rsp, 20h
0x18001027d  pop     rbx
0x18001027e  retn
```
