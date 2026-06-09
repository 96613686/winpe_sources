# McGenControlCallbackV2

- ea: `0x180016230`
- end: `0x18001632f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180016230`
- `0x18001bf00`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rdx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
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
          v13 = *v12;
          if ( v10 )
            v14 = v13 | v11;
          else
            v14 = v13 & ~v11;
          *v12 = v14;
        }
      }
    }
    else
    {
      v15 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v15 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v15 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x180016230  push    rbx
0x180016232  sub     rsp, 20h
0x180016236  mov     r10, [rsp+28h+CallbackContext]
0x18001623b  xor     ebx, ebx
0x18001623d  test    r10, r10
0x180016240  jz      loc_180016328
0x180016246  test    edx, edx
0x180016248  jz      loc_1800162EF
0x18001624e  cmp     edx, 1
0x180016251  jnz     loc_180016328
0x180016257  mov     rax, [rsp+28h+MatchAllKeyword]
0x18001625c  mov     [r10+28h], r8b
0x180016260  mov     r8d, ebx
0x180016263  mov     [r10+18h], rax
0x180016267  mov     [r10+10h], r9
0x18001626b  mov     [r10+24h], edx
0x18001626f  cmp     bx, [r10+2Ah]
0x180016274  jnb     loc_180016328
0x18001627a  mov     rax, [r10+40h]
0x18001627e  mov     cl, [r10+28h]
0x180016282  mov     r9d, r8d
0x180016285  cmp     [r9+rax], cl
0x180016289  jbe     short loc_18001628F
0x18001628b  test    cl, cl
0x18001628d  jnz     short loc_1800162B1
0x18001628f  mov     rax, [r10+38h]
0x180016293  mov     rdx, [rax+r9*8]
0x180016297  test    rdx, rdx
0x18001629a  jz      short loc_1800162B6
0x18001629c  test    [r10+10h], rdx
0x1800162a0  jz      short loc_1800162B1
0x1800162a2  mov     rcx, [r10+18h]
0x1800162a6  mov     rax, rcx
0x1800162a9  and     rax, rdx
0x1800162ac  cmp     rax, rcx
0x1800162af  jz      short loc_1800162B6
0x1800162b1  mov     r11b, bl
0x1800162b4  jmp     short loc_1800162B9
0x1800162b6  mov     r11b, 1
0x1800162b9  mov     rax, [r10+30h]
0x1800162bd  mov     ecx, r8d
0x1800162c0  shr     r9, 5
0x1800162c4  mov     edx, 1
0x1800162c9  shl     edx, cl
0x1800162cb  lea     rcx, [rax+r9*4]
0x1800162cf  mov     eax, [rcx]
0x1800162d1  test    r11b, r11b
0x1800162d4  jz      short loc_1800162DA
0x1800162d6  or      edx, eax
0x1800162d8  jmp     short loc_1800162DE
0x1800162da  not     edx
0x1800162dc  and     edx, eax
0x1800162de  mov     [rcx], edx
0x1800162e0  inc     r8d
0x1800162e3  movzx   eax, word ptr [r10+2Ah]
0x1800162e8  cmp     r8d, eax
0x1800162eb  jb      short loc_18001627A
0x1800162ed  jmp     short loc_180016328
0x1800162ef  movzx   eax, word ptr [r10+2Ah]
0x1800162f4  mov     [r10+24h], ebx
0x1800162f8  mov     [r10+28h], bl
0x1800162fc  mov     [r10+10h], rbx
0x180016300  mov     [r10+18h], rbx
0x180016304  test    ax, ax
0x180016307  jz      short loc_180016328
0x180016309  mov     rcx, [r10+30h]; void *
0x18001630d  dec     eax
0x18001630f  cdq
0x180016310  and     edx, 1Fh
0x180016313  add     eax, edx
0x180016315  xor     edx, edx; Val
0x180016317  sar     eax, 5
0x18001631a  inc     eax
0x18001631c  movsxd  r8, eax
0x18001631f  shl     r8, 2; Size
0x180016323  call    memset
0x180016328  add     rsp, 20h
0x18001632c  pop     rbx
0x18001632d  retn
```
