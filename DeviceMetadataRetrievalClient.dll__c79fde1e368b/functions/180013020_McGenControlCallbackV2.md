# McGenControlCallbackV2

- ea: `0x180013020`
- end: `0x180013120`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180013020`
- `0x1800136c6`

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
0x180013020  push    rbx
0x180013022  sub     rsp, 20h
0x180013026  mov     r10, [rsp+28h+CallbackContext]
0x18001302b  xor     ebx, ebx
0x18001302d  test    r10, r10
0x180013030  jz      loc_18001311A
0x180013036  test    edx, edx
0x180013038  jz      loc_1800130DF
0x18001303e  cmp     edx, 1
0x180013041  jnz     loc_18001311A
0x180013047  mov     rax, [rsp+28h+MatchAllKeyword]
0x18001304c  mov     [r10+28h], r8b
0x180013050  mov     r8d, ebx
0x180013053  mov     [r10+18h], rax
0x180013057  mov     [r10+10h], r9
0x18001305b  mov     [r10+24h], edx
0x18001305f  cmp     bx, [r10+2Ah]
0x180013064  jnb     loc_18001311A
0x18001306a  mov     rax, [r10+40h]
0x18001306e  mov     cl, [r10+28h]
0x180013072  mov     r9d, r8d
0x180013075  cmp     [r9+rax], cl
0x180013079  jbe     short loc_18001307F
0x18001307b  test    cl, cl
0x18001307d  jnz     short loc_18001309F
0x18001307f  mov     rax, [r10+38h]
0x180013083  mov     rcx, [rax+r9*8]
0x180013087  test    rcx, rcx
0x18001308a  jz      short loc_1800130A4
0x18001308c  test    [r10+10h], rcx
0x180013090  jz      short loc_18001309F
0x180013092  mov     rax, [r10+18h]
0x180013096  and     rax, rcx
0x180013099  cmp     rax, [r10+18h]
0x18001309d  jz      short loc_1800130A4
0x18001309f  mov     r11b, bl
0x1800130a2  jmp     short loc_1800130A7
0x1800130a4  mov     r11b, 1
0x1800130a7  mov     rax, [r10+30h]
0x1800130ab  mov     ecx, r8d
0x1800130ae  shr     r9, 5
0x1800130b2  mov     edx, 1
0x1800130b7  shl     edx, cl
0x1800130b9  lea     rcx, [rax+r9*4]
0x1800130bd  test    r11b, r11b
0x1800130c0  jz      short loc_1800130C6
0x1800130c2  or      edx, [rcx]
0x1800130c4  jmp     short loc_1800130CA
0x1800130c6  not     edx
0x1800130c8  and     edx, [rcx]
0x1800130ca  mov     [rcx], edx
0x1800130cc  inc     r8d
0x1800130cf  movzx   eax, word ptr [r10+2Ah]
0x1800130d4  cmp     r8d, eax
0x1800130d7  jb      short loc_18001306A
0x1800130d9  add     rsp, 20h
0x1800130dd  pop     rbx
0x1800130de  retn
0x1800130df  mov     [r10+24h], ebx
0x1800130e3  mov     [r10+28h], bl
0x1800130e7  mov     [r10+10h], rbx
0x1800130eb  mov     [r10+18h], rbx
0x1800130ef  cmp     [r10+2Ah], bx
0x1800130f4  jbe     short loc_18001311A
0x1800130f6  movzx   eax, word ptr [r10+2Ah]
0x1800130fb  mov     rcx, [r10+30h]; void *
0x1800130ff  dec     eax
0x180013101  cdq
0x180013102  and     edx, 1Fh
0x180013105  add     eax, edx
0x180013107  xor     edx, edx; Val
0x180013109  sar     eax, 5
0x18001310c  inc     eax
0x18001310e  movsxd  r8, eax
0x180013111  shl     r8, 2; Size
0x180013115  call    memset_0
0x18001311a  add     rsp, 20h
0x18001311e  pop     rbx
0x18001311f  retn
```
