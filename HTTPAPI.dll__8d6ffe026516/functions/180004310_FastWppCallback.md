# FastWppCallback

- ea: `0x180004310`
- end: `0x18000437a`
- name: `FastWppCallback`
- size: `106`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004310`

## pseudocode

```c
void __fastcall FastWppCallback(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword)
{
  UCHAR v4; // dl
  unsigned __int8 v5; // al
  __int64 v6; // rcx
  __int64 v7; // rcx

  if ( IsEnabled )
  {
    if ( IsEnabled == 1 )
    {
      v4 = 5;
      if ( Level <= 5u )
        v4 = Level;
      v5 = 1;
      if ( !v4 )
        goto LABEL_13;
      do
      {
        v6 = v5++;
        *((_QWORD *)&g_rgFastWppLevelEnabledFlags + v6) = MatchAnyKeyword;
      }
      while ( v5 <= v4 );
      if ( v5 < 5u )
      {
LABEL_13:
        do
        {
          v7 = v5++;
          *((_QWORD *)&g_rgFastWppLevelEnabledFlags + v7) = 0;
        }
        while ( v5 < 5u );
      }
    }
  }
  else
  {
    g_rgFastWppLevelEnabledFlags = 0;
    *(_OWORD *)byte_180012690 = 0;
    *(_OWORD *)byte_1800126A0 = 0;
  }
}

```

## disassembly

```asm
0x180004310  test    edx, edx
0x180004312  jz      short loc_180004361
0x180004314  cmp     edx, 1
0x180004317  jnz     short locret_180004379
0x180004319  movzx   eax, r8b
0x18000431d  mov     edx, 5
0x180004322  cmp     r8b, dl
0x180004325  lea     r8, g_rgFastWppLevelEnabledFlags
0x18000432c  cmovbe  edx, eax
0x18000432f  mov     al, 1
0x180004331  cmp     dl, al
0x180004333  jb      short loc_180004351
0x180004335  nop     word ptr [rax+rax+00000000h]
0x180004340  movzx   ecx, al
0x180004343  inc     al
0x180004345  mov     [r8+rcx*8], r9
0x180004349  cmp     al, dl
0x18000434b  jbe     short loc_180004340
0x18000434d  cmp     al, 5
0x18000434f  jnb     short locret_180004379
0x180004351  xor     edx, edx
0x180004353  movzx   ecx, al
0x180004356  inc     al
0x180004358  mov     [r8+rcx*8], rdx
0x18000435c  cmp     al, 5
0x18000435e  jb      short loc_180004353
0x180004360  retn
0x180004361  xorps   xmm0, xmm0
0x180004364  movups  cs:g_rgFastWppLevelEnabledFlags, xmm0
0x18000436b  movups  xmmword ptr cs:byte_180012690, xmm0
0x180004372  movups  xmmword ptr cs:byte_1800126A0, xmm0
0x180004379  retn
```
