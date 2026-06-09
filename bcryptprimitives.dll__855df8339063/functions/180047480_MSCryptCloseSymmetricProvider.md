# MSCryptCloseSymmetricProvider

- ea: `0x180047480`
- end: `0x180047557`
- name: `MSCryptCloseSymmetricProvider`
- size: `215`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180067358`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180047480`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800474cc`
- `ntdll!RtlFreeHeap` at `0x1800474cc`

## string_xrefs

- `0x180047508`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180047538`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptCloseSymmetricProvider(unsigned int *P, int a2)
{
  __int64 v3; // rcx
  _BYTE *i; // rax

  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        169);
    return 3221225485LL;
  }
  else if ( P && P[1] == 1297306433 )
  {
    v3 = *P;
    for ( i = P; v3; --v3 )
      *i++ = 0;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    return 0;
  }
  else
  {
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 434);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x180047480  sub     rsp, 48h
0x180047484  mov     r8, rcx; P
0x180047487  test    edx, edx
0x180047489  jnz     short loc_1800474E0
0x18004748b  test    rcx, rcx
0x18004748e  jz      loc_180047532
0x180047494  cmp     dword ptr [rcx+4], 4D535341h
0x18004749b  jnz     loc_180047532
0x1800474a1  mov     ecx, [rcx]
0x1800474a3  mov     rax, r8
0x1800474a6  test    rcx, rcx
0x1800474a9  jz      short loc_1800474BD
0x1800474ab  nop     dword ptr [rax+rax+00h]
0x1800474b0  mov     byte ptr [rax], 0
0x1800474b3  lea     rax, [rax+1]
0x1800474b7  sub     rcx, 1
0x1800474bb  jnz     short loc_1800474B0
0x1800474bd  mov     rcx, gs:60h
0x1800474c6  xor     edx, edx; Flags
0x1800474c8  mov     rcx, [rcx+30h]; HeapHandle
0x1800474cc  call    cs:__imp_RtlFreeHeap
0x1800474d3  nop     dword ptr [rax+rax+00h]
0x1800474d8  xor     eax, eax
0x1800474da  add     rsp, 48h
0x1800474de  retn
0x1800474e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800474e7  lea     rax, WPP_GLOBAL_Control
0x1800474ee  cmp     rcx, rax
0x1800474f1  jz      short loc_1800474F9
0x1800474f3  test    byte ptr [rcx+1Ch], 1
0x1800474f7  jnz     short loc_180047504
0x1800474f9  mov     eax, 0C000000Dh
0x1800474fe  add     rsp, 48h
0x180047502  retn
0x180047504  mov     rcx, [rcx+10h]
0x180047508  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004750f  mov     [rsp+48h+var_18], 1A9h
0x180047517  lea     r9, aStatus; "Status"
0x18004751e  mov     [rsp+48h+var_20], r8
0x180047523  mov     [rsp+48h+var_28], 0C000000Dh
0x18004752b  call    WPP_SF_sDsd
0x180047530  jmp     short loc_1800474F9
0x180047532  mov     r9d, 1B2h
0x180047538  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004753f  lea     rdx, aStatus; "Status"
0x180047546  mov     ecx, 0C0000008h
0x18004754b  call    DebugTraceError
0x180047550  mov     eax, 0C0000008h
0x180047555  jmp     short loc_1800474DA
```
