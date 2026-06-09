# McGenControlCallbackV2

- ea: `0x18000f890`
- end: `0x18000f990`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002ac8`
- `0x18000f890`

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
0x18000f890  push    rbx
0x18000f892  sub     rsp, 20h
0x18000f896  mov     r10, [rsp+28h+CallbackContext]
0x18000f89b  xor     ebx, ebx
0x18000f89d  test    r10, r10
0x18000f8a0  jz      loc_18000F98A
0x18000f8a6  test    edx, edx
0x18000f8a8  jz      loc_18000F94F
0x18000f8ae  cmp     edx, 1
0x18000f8b1  jnz     loc_18000F98A
0x18000f8b7  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000f8bc  mov     [r10+28h], r8b
0x18000f8c0  mov     r8d, ebx
0x18000f8c3  mov     [r10+18h], rax
0x18000f8c7  mov     [r10+10h], r9
0x18000f8cb  mov     [r10+24h], edx
0x18000f8cf  cmp     bx, [r10+2Ah]
0x18000f8d4  jnb     loc_18000F98A
0x18000f8da  mov     rax, [r10+40h]
0x18000f8de  mov     cl, [r10+28h]
0x18000f8e2  mov     r9d, r8d
0x18000f8e5  cmp     [r9+rax], cl
0x18000f8e9  jbe     short loc_18000F8EF
0x18000f8eb  test    cl, cl
0x18000f8ed  jnz     short loc_18000F90F
0x18000f8ef  mov     rax, [r10+38h]
0x18000f8f3  mov     rcx, [rax+r9*8]
0x18000f8f7  test    rcx, rcx
0x18000f8fa  jz      short loc_18000F914
0x18000f8fc  test    [r10+10h], rcx
0x18000f900  jz      short loc_18000F90F
0x18000f902  mov     rax, [r10+18h]
0x18000f906  and     rax, rcx
0x18000f909  cmp     rax, [r10+18h]
0x18000f90d  jz      short loc_18000F914
0x18000f90f  mov     r11b, bl
0x18000f912  jmp     short loc_18000F917
0x18000f914  mov     r11b, 1
0x18000f917  mov     rax, [r10+30h]
0x18000f91b  mov     ecx, r8d
0x18000f91e  shr     r9, 5
0x18000f922  mov     edx, 1
0x18000f927  shl     edx, cl
0x18000f929  lea     rcx, [rax+r9*4]
0x18000f92d  test    r11b, r11b
0x18000f930  jz      short loc_18000F936
0x18000f932  or      edx, [rcx]
0x18000f934  jmp     short loc_18000F93A
0x18000f936  not     edx
0x18000f938  and     edx, [rcx]
0x18000f93a  mov     [rcx], edx
0x18000f93c  inc     r8d
0x18000f93f  movzx   eax, word ptr [r10+2Ah]
0x18000f944  cmp     r8d, eax
0x18000f947  jb      short loc_18000F8DA
0x18000f949  add     rsp, 20h
0x18000f94d  pop     rbx
0x18000f94e  retn
0x18000f94f  mov     [r10+24h], ebx
0x18000f953  mov     [r10+28h], bl
0x18000f957  mov     [r10+10h], rbx
0x18000f95b  mov     [r10+18h], rbx
0x18000f95f  cmp     [r10+2Ah], bx
0x18000f964  jbe     short loc_18000F98A
0x18000f966  movzx   eax, word ptr [r10+2Ah]
0x18000f96b  mov     rcx, [r10+30h]; void *
0x18000f96f  dec     eax
0x18000f971  cdq
0x18000f972  and     edx, 1Fh
0x18000f975  add     eax, edx
0x18000f977  xor     edx, edx; Val
0x18000f979  sar     eax, 5
0x18000f97c  inc     eax
0x18000f97e  movsxd  r8, eax
0x18000f981  shl     r8, 2; Size
0x18000f985  call    memset_0
0x18000f98a  add     rsp, 20h
0x18000f98e  pop     rbx
0x18000f98f  retn
```
