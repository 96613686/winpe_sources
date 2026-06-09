# MSCryptAuditCheckSecureZero

- ea: `0x1800213d0`
- end: `0x180021489`
- name: `MSCryptAuditCheckSecureZero`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180058400`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800213d0`
- `0x1800215e4`

## string_xrefs

- `0x180021440`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`
- `0x180021470`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`

## pseudocode

```c
__int64 __fastcall MSCryptAuditCheckSecureZero(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 i; // rax
  __int64 result; // rax
  unsigned int v6; // ebx

  if ( a1 )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= a2 )
        return 0;
      if ( *(_BYTE *)(i + a1) )
        break;
    }
    result = MSCryptAuditPrimitiveFailure(a1, a4, 0x986u, 0);
    v6 = result;
    if ( (int)result < 0 )
    {
      DebugTraceError((unsigned int)result, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c", 491);
      return v6;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c",
        220);
    return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800213d0  sub     rsp, 48h
0x1800213d4  mov     r10, r9
0x1800213d7  test    rcx, rcx
0x1800213da  jz      short loc_1800213F8
0x1800213dc  xor     r9d, r9d
0x1800213df  xor     eax, eax
0x1800213e1  cmp     eax, edx
0x1800213e3  jnb     short loc_1800213EF
0x1800213e5  cmp     [rax+rcx], r9b
0x1800213e9  jnz     short loc_18002141C
0x1800213eb  inc     eax
0x1800213ed  jmp     short loc_1800213E1
0x1800213ef  mov     eax, r9d
0x1800213f2  add     rsp, 48h
0x1800213f6  retn
0x1800213f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213ff  lea     rax, WPP_GLOBAL_Control
0x180021406  cmp     rcx, rax
0x180021409  jz      short loc_180021411
0x18002140b  test    byte ptr [rcx+1Ch], 1
0x18002140f  jnz     short loc_18002143C
0x180021411  mov     eax, 0C000000Dh
0x180021416  add     rsp, 48h
0x18002141a  retn
0x18002141c  mov     r8d, 986h
0x180021422  mov     [rsp+48h+var_8], rbx
0x180021427  mov     rdx, r10
0x18002142a  call    MSCryptAuditPrimitiveFailure
0x18002142f  mov     ebx, eax
0x180021431  test    eax, eax
0x180021433  js      short loc_18002146A
0x180021435  mov     rbx, [rsp+48h+var_8]
0x18002143a  jmp     short loc_1800213F2
0x18002143c  mov     rcx, [rcx+10h]
0x180021440  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021447  mov     [rsp+48h+var_18], 1DCh
0x18002144f  lea     r9, aStatus; "Status"
0x180021456  mov     [rsp+48h+var_20], r8
0x18002145b  mov     [rsp+48h+var_28], 0C000000Dh
0x180021463  call    WPP_SF_sDsd
0x180021468  jmp     short loc_180021411
0x18002146a  mov     r9d, 1EBh
0x180021470  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021477  lea     rdx, aStatus; "Status"
0x18002147e  mov     ecx, ebx
0x180021480  call    DebugTraceError
0x180021485  mov     eax, ebx
0x180021487  jmp     short loc_180021435
```
