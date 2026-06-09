# EnableCallback

- ea: `0x14000c670`
- end: `0x14000c777`
- name: `EnableCallback`
- size: `263`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000c670`
- `0x14005b856`

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
0x14000c670  push    rbx
0x14000c672  sub     rsp, 20h
0x14000c676  mov     r10, [rsp+28h+CallbackContext]
0x14000c67b  xor     ebx, ebx
0x14000c67d  test    r10, r10
0x14000c680  jz      loc_14000C771
0x14000c686  test    edx, edx
0x14000c688  jz      loc_14000C736
0x14000c68e  cmp     edx, 1
0x14000c691  jnz     loc_14000C771
0x14000c697  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000c69c  mov     [r10+28h], r8b
0x14000c6a0  mov     r8d, ebx
0x14000c6a3  mov     [r10+18h], rax
0x14000c6a7  mov     [r10+10h], r9
0x14000c6ab  mov     [r10+24h], edx
0x14000c6af  cmp     bx, [r10+2Ah]
0x14000c6b4  jnb     loc_14000C771
0x14000c6ba  mov     rax, [r10+38h]
0x14000c6be  mov     r9b, [r10+28h]
0x14000c6c2  mov     ecx, r8d
0x14000c6c5  mov     rdx, [rax+rcx*8]
0x14000c6c9  mov     rax, [r10+40h]
0x14000c6cd  cmp     [rcx+rax], r9b
0x14000c6d1  jbe     short loc_14000C6D8
0x14000c6d3  test    r9b, r9b
0x14000c6d6  jnz     short loc_14000C6F0
0x14000c6d8  test    rdx, rdx
0x14000c6db  jz      short loc_14000C6F5
0x14000c6dd  test    [r10+10h], rdx
0x14000c6e1  jz      short loc_14000C6F0
0x14000c6e3  mov     rax, [r10+18h]
0x14000c6e7  and     rax, rdx
0x14000c6ea  cmp     rax, [r10+18h]
0x14000c6ee  jz      short loc_14000C6F5
0x14000c6f0  mov     r9b, bl
0x14000c6f3  jmp     short loc_14000C6F8
0x14000c6f5  mov     r9b, 1
0x14000c6f8  mov     rax, [r10+30h]
0x14000c6fc  mov     ecx, r8d
0x14000c6ff  mov     edx, 1
0x14000c704  shl     edx, cl
0x14000c706  mov     ecx, r8d
0x14000c709  shr     rcx, 5
0x14000c70d  lea     r11, [rax+rcx*4]
0x14000c711  test    r9b, r9b
0x14000c714  jz      short loc_14000C71B
0x14000c716  or      edx, [r11]
0x14000c719  jmp     short loc_14000C720
0x14000c71b  not     edx
0x14000c71d  and     edx, [r11]
0x14000c720  mov     [r11], edx
0x14000c723  inc     r8d
0x14000c726  movzx   eax, word ptr [r10+2Ah]
0x14000c72b  cmp     r8d, eax
0x14000c72e  jb      short loc_14000C6BA
0x14000c730  add     rsp, 20h
0x14000c734  pop     rbx
0x14000c735  retn
0x14000c736  mov     [r10+24h], ebx
0x14000c73a  mov     [r10+28h], bl
0x14000c73e  mov     [r10+10h], rbx
0x14000c742  mov     [r10+18h], rbx
0x14000c746  cmp     [r10+2Ah], bx
0x14000c74b  jbe     short loc_14000C771
0x14000c74d  movzx   eax, word ptr [r10+2Ah]
0x14000c752  mov     rcx, [r10+30h]; void *
0x14000c756  dec     eax
0x14000c758  cdq
0x14000c759  and     edx, 1Fh
0x14000c75c  add     eax, edx
0x14000c75e  xor     edx, edx; Val
0x14000c760  sar     eax, 5
0x14000c763  inc     eax
0x14000c765  movsxd  r8, eax
0x14000c768  shl     r8, 2; Size
0x14000c76c  call    memset
0x14000c771  add     rsp, 20h
0x14000c775  pop     rbx
0x14000c776  retn
```
