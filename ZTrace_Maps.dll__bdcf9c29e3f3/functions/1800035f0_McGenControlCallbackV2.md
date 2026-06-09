# McGenControlCallbackV2

- ea: `0x1800035f0`
- end: `0x1800036f0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800022be`
- `0x1800035f0`

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
0x1800035f0  push    rbx
0x1800035f2  sub     rsp, 20h
0x1800035f6  mov     r10, [rsp+28h+CallbackContext]
0x1800035fb  xor     ebx, ebx
0x1800035fd  test    r10, r10
0x180003600  jz      loc_1800036EA
0x180003606  test    edx, edx
0x180003608  jz      loc_1800036AF
0x18000360e  cmp     edx, 1
0x180003611  jnz     loc_1800036EA
0x180003617  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000361c  mov     [r10+28h], r8b
0x180003620  mov     r8d, ebx
0x180003623  mov     [r10+18h], rax
0x180003627  mov     [r10+10h], r9
0x18000362b  mov     [r10+24h], edx
0x18000362f  cmp     bx, [r10+2Ah]
0x180003634  jnb     loc_1800036EA
0x18000363a  mov     rax, [r10+40h]
0x18000363e  mov     cl, [r10+28h]
0x180003642  mov     r9d, r8d
0x180003645  cmp     [r9+rax], cl
0x180003649  jbe     short loc_18000364F
0x18000364b  test    cl, cl
0x18000364d  jnz     short loc_18000366F
0x18000364f  mov     rax, [r10+38h]
0x180003653  mov     rcx, [rax+r9*8]
0x180003657  test    rcx, rcx
0x18000365a  jz      short loc_180003674
0x18000365c  test    [r10+10h], rcx
0x180003660  jz      short loc_18000366F
0x180003662  mov     rax, [r10+18h]
0x180003666  and     rax, rcx
0x180003669  cmp     rax, [r10+18h]
0x18000366d  jz      short loc_180003674
0x18000366f  mov     r11b, bl
0x180003672  jmp     short loc_180003677
0x180003674  mov     r11b, 1
0x180003677  mov     rax, [r10+30h]
0x18000367b  mov     ecx, r8d
0x18000367e  shr     r9, 5
0x180003682  mov     edx, 1
0x180003687  shl     edx, cl
0x180003689  lea     rcx, [rax+r9*4]
0x18000368d  test    r11b, r11b
0x180003690  jz      short loc_180003696
0x180003692  or      edx, [rcx]
0x180003694  jmp     short loc_18000369A
0x180003696  not     edx
0x180003698  and     edx, [rcx]
0x18000369a  mov     [rcx], edx
0x18000369c  inc     r8d
0x18000369f  movzx   eax, word ptr [r10+2Ah]
0x1800036a4  cmp     r8d, eax
0x1800036a7  jb      short loc_18000363A
0x1800036a9  add     rsp, 20h
0x1800036ad  pop     rbx
0x1800036ae  retn
0x1800036af  mov     [r10+24h], ebx
0x1800036b3  mov     [r10+28h], bl
0x1800036b7  mov     [r10+10h], rbx
0x1800036bb  mov     [r10+18h], rbx
0x1800036bf  cmp     [r10+2Ah], bx
0x1800036c4  jbe     short loc_1800036EA
0x1800036c6  movzx   eax, word ptr [r10+2Ah]
0x1800036cb  mov     rcx, [r10+30h]; void *
0x1800036cf  dec     eax
0x1800036d1  cdq
0x1800036d2  and     edx, 1Fh
0x1800036d5  add     eax, edx
0x1800036d7  xor     edx, edx; Val
0x1800036d9  sar     eax, 5
0x1800036dc  inc     eax
0x1800036de  movsxd  r8, eax
0x1800036e1  shl     r8, 2; Size
0x1800036e5  call    memset_0
0x1800036ea  add     rsp, 20h
0x1800036ee  pop     rbx
0x1800036ef  retn
```
