# PbdevicetypeFromPszTypeA

- ea: `0x18007ffdc`
- end: `0x18008030c`
- name: `PbdevicetypeFromPszTypeA`
- size: `816`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800658f8`
- `0x180070f30`
- `0x18007ff2c`
- `0x1800818cc`

## callees

- `0x180005e0c`
- `0x18005ccf0`
- `0x18007ffdc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800802ca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800802ca`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008005b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180080088`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800800ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800800da`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180080106`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180080132`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008015e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008018a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800801b6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800801e2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008020e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008023a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180080263`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008028c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800802b5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008005b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180080088`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800800ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800800da`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180080106`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180080132`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008015e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008018a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800801b6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800801e2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008020e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008023a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180080263`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008028c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800802b5`

## pseudocode

```c
const WCHAR *__fastcall PbdevicetypeFromPszTypeA(LPCCH lpMultiByteStr)
{
  const WCHAR *result; // rax
  WCHAR *lpString2; // rdi
  unsigned int v4; // ebx

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 94, WPP_38cda081c674317ed40163d707084d83_Traceguids);
  }
  result = (const WCHAR *)StrDupWFromAInternal(lpMultiByteStr, 0xFDE9u);
  lpString2 = (WCHAR *)result;
  if ( result )
  {
    v4 = 1;
    if ( CompareStringW(0x7Fu, 1u, L"modem", -1, result, -1) == 2 )
    {
      v4 = 3;
    }
    else if ( CompareStringW(0x7Fu, 1u, L"null", -1, lpString2, -1) != 2 )
    {
      if ( CompareStringW(0x7Fu, 1u, L"PARALLEL", -1, lpString2, -1) == 2 )
      {
        v4 = 14;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"IRDA", -1, lpString2, -1) == 2 )
      {
        v4 = 10;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"pad", -1, lpString2, -1) == 2 )
      {
        v4 = 4;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"switch", -1, lpString2, -1) == 2 )
      {
        v4 = 5;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"isdn", -1, lpString2, -1) == 2 )
      {
        v4 = 6;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"x25", -1, lpString2, -1) == 2 )
      {
        v4 = 7;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"vpn", -1, lpString2, -1) == 2 )
      {
        v4 = 11;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"ATM", -1, lpString2, -1) == 2 )
      {
        v4 = 13;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"SERIAL", -1, lpString2, -1) == 2 )
      {
        v4 = 12;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"FRAMERELAY", -1, lpString2, -1) == 2 )
      {
        v4 = 17;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"SONET", -1, lpString2, -1) == 2 )
      {
        v4 = 15;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"SW56", -1, lpString2, -1) == 2 )
      {
        v4 = 16;
      }
      else
      {
        v4 = 2;
        if ( CompareStringW(0x7Fu, 1u, L"PPPoE", -1, lpString2, -1) == 2 )
          v4 = 18;
      }
    }
    GlobalFree(lpString2);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 95, WPP_38cda081c674317ed40163d707084d83_Traceguids);
    }
    return (const WCHAR *)v4;
  }
  return result;
}

```

## disassembly

```asm
0x18007ffdc  push    rbx
0x18007ffde  push    rbp
0x18007ffdf  push    rsi
0x18007ffe0  push    rdi
0x18007ffe1  push    r14
0x18007ffe3  push    r15
0x18007ffe5  sub     rsp, 38h
0x18007ffe9  mov     rbx, rcx
0x18007ffec  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fff3  lea     r15, WPP_GLOBAL_Control
0x18007fffa  cmp     rcx, r15
0x18007fffd  jz      short loc_180080020
0x18007ffff  test    byte ptr [rcx+1Ch], 80h
0x180080003  jz      short loc_180080020
0x180080005  cmp     byte ptr [rcx+19h], 6
0x180080009  jb      short loc_180080020
0x18008000b  mov     rcx, [rcx+10h]
0x18008000f  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x180080016  mov     edx, 5Eh ; '^'
0x18008001b  call    WPP_SF_
0x180080020  mov     edx, 0FDE9h; CodePage
0x180080025  mov     rcx, rbx; lpMultiByteStr
0x180080028  call    StrDupWFromAInternal
0x18008002d  mov     rdi, rax
0x180080030  test    rax, rax
0x180080033  jz      loc_1800802FF
0x180080039  or      esi, 0FFFFFFFFh
0x18008003c  lea     r8, aModem_1; "modem"
0x180080043  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180080047  mov     r9d, esi; cchCount1
0x18008004a  mov     [rsp+68h+lpString2], rdi; lpString2
0x18008004f  lea     ebx, [rsi+2]
0x180080052  lea     r14d, [rbx+7Eh]
0x180080056  mov     edx, ebx; dwCmpFlags
0x180080058  mov     ecx, r14d; Locale
0x18008005b  call    cs:__imp_CompareStringW
0x180080061  lea     ebp, [rsi+3]
0x180080064  cmp     eax, ebp
0x180080066  jnz     short loc_180080070
0x180080068  lea     ebx, [rsi+4]
0x18008006b  jmp     loc_1800802C7
0x180080070  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180080074  lea     r8, aNull; "null"
0x18008007b  mov     r9d, esi; cchCount1
0x18008007e  mov     [rsp+68h+lpString2], rdi; lpString2
0x180080083  mov     edx, ebx; dwCmpFlags
0x180080085  mov     ecx, r14d; Locale
0x180080088  call    cs:__imp_CompareStringW
0x18008008e  cmp     eax, ebp
0x180080090  jz      loc_1800802C7
0x180080096  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18008009a  lea     r8, aParallel; "PARALLEL"
0x1800800a1  mov     r9d, esi; cchCount1
0x1800800a4  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800800a9  mov     edx, ebx; dwCmpFlags
0x1800800ab  mov     ecx, r14d; Locale
0x1800800ae  call    cs:__imp_CompareStringW
0x1800800b4  cmp     eax, ebp
0x1800800b6  jnz     short loc_1800800C2
0x1800800b8  mov     ebx, 0Eh
0x1800800bd  jmp     loc_1800802C7
0x1800800c2  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800800c6  lea     r8, aIrda; "IRDA"
0x1800800cd  mov     r9d, esi; cchCount1
0x1800800d0  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800800d5  mov     edx, ebx; dwCmpFlags
0x1800800d7  mov     ecx, r14d; Locale
0x1800800da  call    cs:__imp_CompareStringW
0x1800800e0  cmp     eax, ebp
0x1800800e2  jnz     short loc_1800800EE
0x1800800e4  mov     ebx, 0Ah
0x1800800e9  jmp     loc_1800802C7
0x1800800ee  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800800f2  lea     r8, aPad_1; "pad"
0x1800800f9  mov     r9d, esi; cchCount1
0x1800800fc  mov     [rsp+68h+lpString2], rdi; lpString2
0x180080101  mov     edx, ebx; dwCmpFlags
0x180080103  mov     ecx, r14d; Locale
0x180080106  call    cs:__imp_CompareStringW
0x18008010c  cmp     eax, ebp
0x18008010e  jnz     short loc_18008011A
0x180080110  mov     ebx, 4
0x180080115  jmp     loc_1800802C7
0x18008011a  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18008011e  lea     r8, aSwitch_1; "switch"
0x180080125  mov     r9d, esi; cchCount1
0x180080128  mov     [rsp+68h+lpString2], rdi; lpString2
0x18008012d  mov     edx, ebx; dwCmpFlags
0x18008012f  mov     ecx, r14d; Locale
0x180080132  call    cs:__imp_CompareStringW
0x180080138  cmp     eax, ebp
0x18008013a  jnz     short loc_180080146
0x18008013c  mov     ebx, 5
0x180080141  jmp     loc_1800802C7
0x180080146  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18008014a  lea     r8, aIsdn; "isdn"
0x180080151  mov     r9d, esi; cchCount1
0x180080154  mov     [rsp+68h+lpString2], rdi; lpString2
0x180080159  mov     edx, ebx; dwCmpFlags
0x18008015b  mov     ecx, r14d; Locale
0x18008015e  call    cs:__imp_CompareStringW
0x180080164  cmp     eax, ebp
0x180080166  jnz     short loc_180080172
0x180080168  mov     ebx, 6
0x18008016d  jmp     loc_1800802C7
0x180080172  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180080176  lea     r8, aX25; "x25"
0x18008017d  mov     r9d, esi; cchCount1
0x180080180  mov     [rsp+68h+lpString2], rdi; lpString2
0x180080185  mov     edx, ebx; dwCmpFlags
0x180080187  mov     ecx, r14d; Locale
0x18008018a  call    cs:__imp_CompareStringW
0x180080190  cmp     eax, ebp
0x180080192  jnz     short loc_18008019E
0x180080194  mov     ebx, 7
0x180080199  jmp     loc_1800802C7
0x18008019e  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800801a2  lea     r8, aVpn_2; "vpn"
0x1800801a9  mov     r9d, esi; cchCount1
0x1800801ac  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800801b1  mov     edx, ebx; dwCmpFlags
0x1800801b3  mov     ecx, r14d; Locale
0x1800801b6  call    cs:__imp_CompareStringW
0x1800801bc  cmp     eax, ebp
0x1800801be  jnz     short loc_1800801CA
0x1800801c0  mov     ebx, 0Bh
0x1800801c5  jmp     loc_1800802C7
0x1800801ca  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800801ce  lea     r8, aAtm; "ATM"
0x1800801d5  mov     r9d, esi; cchCount1
0x1800801d8  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800801dd  mov     edx, ebx; dwCmpFlags
0x1800801df  mov     ecx, r14d; Locale
0x1800801e2  call    cs:__imp_CompareStringW
0x1800801e8  cmp     eax, ebp
0x1800801ea  jnz     short loc_1800801F6
0x1800801ec  mov     ebx, 0Dh
0x1800801f1  jmp     loc_1800802C7
0x1800801f6  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800801fa  lea     r8, aSerial; "SERIAL"
0x180080201  mov     r9d, esi; cchCount1
0x180080204  mov     [rsp+68h+lpString2], rdi; lpString2
0x180080209  mov     edx, ebx; dwCmpFlags
0x18008020b  mov     ecx, r14d; Locale
0x18008020e  call    cs:__imp_CompareStringW
0x180080214  cmp     eax, ebp
0x180080216  jnz     short loc_180080222
0x180080218  mov     ebx, 0Ch
0x18008021d  jmp     loc_1800802C7
0x180080222  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180080226  lea     r8, aFramerelay; "FRAMERELAY"
0x18008022d  mov     r9d, esi; cchCount1
0x180080230  mov     [rsp+68h+lpString2], rdi; lpString2
0x180080235  mov     edx, ebx; dwCmpFlags
0x180080237  mov     ecx, r14d; Locale
0x18008023a  call    cs:__imp_CompareStringW
0x180080240  cmp     eax, ebp
0x180080242  jnz     short loc_18008024B
0x180080244  mov     ebx, 11h
0x180080249  jmp     short loc_1800802C7
0x18008024b  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18008024f  lea     r8, aSonet; "SONET"
0x180080256  mov     r9d, esi; cchCount1
0x180080259  mov     [rsp+68h+lpString2], rdi; lpString2
0x18008025e  mov     edx, ebx; dwCmpFlags
0x180080260  mov     ecx, r14d; Locale
0x180080263  call    cs:__imp_CompareStringW
0x180080269  cmp     eax, ebp
0x18008026b  jnz     short loc_180080274
0x18008026d  mov     ebx, 0Fh
0x180080272  jmp     short loc_1800802C7
0x180080274  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180080278  lea     r8, aSw56; "SW56"
0x18008027f  mov     r9d, esi; cchCount1
0x180080282  mov     [rsp+68h+lpString2], rdi; lpString2
0x180080287  mov     edx, ebx; dwCmpFlags
0x180080289  mov     ecx, r14d; Locale
0x18008028c  call    cs:__imp_CompareStringW
0x180080292  cmp     eax, ebp
0x180080294  jnz     short loc_18008029D
0x180080296  mov     ebx, 10h
0x18008029b  jmp     short loc_1800802C7
0x18008029d  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800802a1  lea     r8, aPppoe; "PPPoE"
0x1800802a8  mov     r9d, esi; cchCount1
0x1800802ab  mov     [rsp+68h+lpString2], rdi; lpString2
0x1800802b0  mov     edx, ebx; dwCmpFlags
0x1800802b2  mov     ecx, r14d; Locale
0x1800802b5  call    cs:__imp_CompareStringW
0x1800802bb  mov     ebx, ebp
0x1800802bd  mov     ecx, 12h
0x1800802c2  cmp     eax, ebp
0x1800802c4  cmovz   ebx, ecx
0x1800802c7  mov     rcx, rdi; hMem
0x1800802ca  call    cs:__imp_GlobalFree
0x1800802d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800802d7  cmp     rcx, r15
0x1800802da  jz      short loc_1800802FD
0x1800802dc  test    byte ptr [rcx+1Ch], 80h
0x1800802e0  jz      short loc_1800802FD
0x1800802e2  cmp     byte ptr [rcx+19h], 6
0x1800802e6  jb      short loc_1800802FD
0x1800802e8  mov     rcx, [rcx+10h]
0x1800802ec  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x1800802f3  mov     edx, 5Fh ; '_'
0x1800802f8  call    WPP_SF_
0x1800802fd  mov     eax, ebx
0x1800802ff  add     rsp, 38h
0x180080303  pop     r15
0x180080305  pop     r14
0x180080307  pop     rdi
0x180080308  pop     rsi
0x180080309  pop     rbp
0x18008030a  pop     rbx
0x18008030b  retn
```
