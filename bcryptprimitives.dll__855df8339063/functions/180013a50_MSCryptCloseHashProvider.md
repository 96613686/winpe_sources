# MSCryptCloseHashProvider

- ea: `0x180013a50`
- end: `0x180013b27`
- name: `MSCryptCloseHashProvider`
- size: `215`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800117d0`
- `0x180012ff4`
- `0x180053de4`
- `0x180054188`
- `0x180058a04`
- `0x18007dd2c`
- `0x18007eb80`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180013a50`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180013a9c`
- `ntdll!RtlFreeHeap` at `0x180013a9c`

## string_xrefs

- `0x180013ad8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180013b08`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptCloseHashProvider(unsigned int *P, int a2)
{
  __int64 v3; // rcx
  _BYTE *i; // rax

  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        123);
    return 3221225485LL;
  }
  else if ( P && P[1] == 1297303617 )
  {
    v3 = *P;
    for ( i = P; v3; --v3 )
      *i++ = 0;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    return 0;
  }
  else
  {
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", 900);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x180013a50  sub     rsp, 48h
0x180013a54  mov     r8, rcx; P
0x180013a57  test    edx, edx
0x180013a59  jnz     short loc_180013AB0
0x180013a5b  test    rcx, rcx
0x180013a5e  jz      loc_180013B02
0x180013a64  cmp     dword ptr [rcx+4], 4D534841h
0x180013a6b  jnz     loc_180013B02
0x180013a71  mov     ecx, [rcx]
0x180013a73  mov     rax, r8
0x180013a76  test    rcx, rcx
0x180013a79  jz      short loc_180013A8D
0x180013a7b  nop     dword ptr [rax+rax+00h]
0x180013a80  mov     byte ptr [rax], 0
0x180013a83  lea     rax, [rax+1]
0x180013a87  sub     rcx, 1
0x180013a8b  jnz     short loc_180013A80
0x180013a8d  mov     rcx, gs:60h
0x180013a96  xor     edx, edx; Flags
0x180013a98  mov     rcx, [rcx+30h]; HeapHandle
0x180013a9c  call    cs:__imp_RtlFreeHeap
0x180013aa3  nop     dword ptr [rax+rax+00h]
0x180013aa8  xor     eax, eax
0x180013aaa  add     rsp, 48h
0x180013aae  retn
0x180013ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ab7  lea     rax, WPP_GLOBAL_Control
0x180013abe  cmp     rcx, rax
0x180013ac1  jz      short loc_180013AC9
0x180013ac3  test    byte ptr [rcx+1Ch], 1
0x180013ac7  jnz     short loc_180013AD4
0x180013ac9  mov     eax, 0C000000Dh
0x180013ace  add     rsp, 48h
0x180013ad2  retn
0x180013ad4  mov     rcx, [rcx+10h]
0x180013ad8  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013adf  mov     [rsp+48h+var_18], 37Bh
0x180013ae7  lea     r9, aStatus; "Status"
0x180013aee  mov     [rsp+48h+var_20], r8
0x180013af3  mov     [rsp+48h+var_28], 0C000000Dh
0x180013afb  call    WPP_SF_sDsd
0x180013b00  jmp     short loc_180013AC9
0x180013b02  mov     r9d, 384h
0x180013b08  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013b0f  lea     rdx, aStatus; "Status"
0x180013b16  mov     ecx, 0C0000008h
0x180013b1b  call    DebugTraceError
0x180013b20  mov     eax, 0C0000008h
0x180013b25  jmp     short loc_180013AAA
```
