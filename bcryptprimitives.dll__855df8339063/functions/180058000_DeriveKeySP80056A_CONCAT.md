# DeriveKeySP80056A_CONCAT

- ea: `0x180058000`
- end: `0x1800580c3`
- name: `DeriveKeySP80056A_CONCAT`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012060`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180058000`
- `0x18007dd2c`

## string_xrefs

- `0x180058059`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180058092`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall DeriveKeySP80056A_CONCAT(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx

  if ( a6 || !a2 )
  {
    v7 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
        127);
  }
  else
  {
    v6 = SP800_56A_KDF(*(const void **)(a1 + 24), *(_DWORD *)(a1 + 16), 0, a2, a3, a4, a5, 1, *(_DWORD *)(a1 + 32));
    v7 = v6;
    if ( v6 )
      DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 663);
  }
  return v7;
}

```

## disassembly

```asm
0x180058000  push    rbx
0x180058002  sub     rsp, 50h
0x180058006  cmp     [rsp+58h+arg_28], 0
0x18005800e  jnz     short loc_180058070
0x180058010  test    rdx, rdx
0x180058013  jz      short loc_180058070
0x180058015  mov     eax, [rcx+20h]
0x180058018  mov     [rsp+58h+var_18], eax
0x18005801c  mov     rax, [rsp+58h+arg_20]
0x180058024  mov     [rsp+58h+var_20], 1
0x18005802c  mov     [rsp+58h+var_28], rax
0x180058031  mov     dword ptr [rsp+58h+var_30], r9d
0x180058036  mov     r9, rdx
0x180058039  mov     edx, [rcx+10h]
0x18005803c  mov     rcx, [rcx+18h]
0x180058040  mov     [rsp+58h+var_38], r8
0x180058045  xor     r8d, r8d
0x180058048  call    _SP800_56A_KDF
0x18005804d  mov     ebx, eax
0x18005804f  test    eax, eax
0x180058051  jz      short loc_1800580BA
0x180058053  mov     r9d, 297h
0x180058059  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058060  lea     rdx, aStatus; "Status"
0x180058067  mov     ecx, eax
0x180058069  call    DebugTraceError
0x18005806e  jmp     short loc_1800580BA
0x180058070  mov     ebx, 0C000000Dh
0x180058075  mov     rcx, cs:WPP_GLOBAL_Control
0x18005807c  lea     rax, WPP_GLOBAL_Control
0x180058083  cmp     rcx, rax
0x180058086  jz      short loc_1800580BA
0x180058088  test    byte ptr [rcx+1Ch], 1
0x18005808c  jz      short loc_1800580BA
0x18005808e  mov     rcx, [rcx+10h]
0x180058092  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058099  mov     dword ptr [rsp+58h+var_28], 27Fh
0x1800580a1  lea     r9, aStatus; "Status"
0x1800580a8  mov     [rsp+58h+var_30], rax
0x1800580ad  mov     dword ptr [rsp+58h+var_38], 0C000000Dh
0x1800580b5  call    WPP_SF_sDsd
0x1800580ba  mov     eax, ebx
0x1800580bc  add     rsp, 50h
0x1800580c0  pop     rbx
0x1800580c1  retn
```
