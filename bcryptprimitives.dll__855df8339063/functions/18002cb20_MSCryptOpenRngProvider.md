# MSCryptOpenRngProvider

- ea: `0x18002cb20`
- end: `0x18002cc48`
- name: `MSCryptOpenRngProvider`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ee60`
- `0x1800102a0`
- `0x18002cb20`
- `0x18007f765`

## string_xrefs

- `0x18002cbc4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\rng.c`

## pseudocode

```c
__int64 __fastcall MSCryptOpenRngProvider(_QWORD *a1, const wchar_t *a2, int a3)
{
  char v3; // bl
  int v6; // ebx
  _DWORD *v7; // rax
  unsigned int v8; // ebx

  v3 = a3;
  if ( (a3 & 0xFFFFFFF6) != 0 )
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\rng.c",
        87);
  }
  else if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    if ( !wcscmp_0(a2, L"RNG") )
    {
      v6 = 327681;
    }
    else if ( !wcscmp_0(a2, L"FIPS186DSARNG") )
    {
      v6 = 327682;
    }
    else
    {
      if ( wcscmp_0(a2, L"DUALECRNG") || (v3 & 1) != 0 )
        return (unsigned int)-1073741637;
      v6 = 327683;
    }
    v7 = (_DWORD *)SafeAllocaAllocateFromHeap(12);
    if ( v7 )
    {
      v7[2] = v6;
      v8 = 0;
      v7[1] = 1297239623;
      *v7 = 12;
      *a1 = v7;
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18002cb20  mov     [rsp+arg_0], rbx
0x18002cb25  mov     [rsp+arg_8], rsi
0x18002cb2a  push    rdi
0x18002cb2b  sub     rsp, 40h
0x18002cb2f  mov     ebx, r8d
0x18002cb32  mov     rdi, rdx
0x18002cb35  mov     rsi, rcx
0x18002cb38  test    r8d, 0FFFFFFF6h
0x18002cb3f  jnz     short loc_18002CBA2
0x18002cb41  test    ebx, 0FFFFFFFEh
0x18002cb47  jnz     loc_18002CBEE
0x18002cb4d  lea     rdx, aRng; "RNG"
0x18002cb54  mov     rcx, rdi; String1
0x18002cb57  call    wcscmp_0
0x18002cb5c  test    eax, eax
0x18002cb5e  jnz     loc_18002CBF5
0x18002cb64  mov     ebx, 50001h
0x18002cb69  mov     edi, 0Ch
0x18002cb6e  mov     ecx, edi
0x18002cb70  call    SafeAllocaAllocateFromHeap
0x18002cb75  test    rax, rax
0x18002cb78  jz      loc_18002CC3E
0x18002cb7e  mov     [rax+8], ebx
0x18002cb81  xor     ebx, ebx
0x18002cb83  mov     dword ptr [rax+4], 4D524E47h
0x18002cb8a  mov     [rax], edi
0x18002cb8c  mov     [rsi], rax
0x18002cb8f  mov     rsi, [rsp+48h+arg_8]
0x18002cb94  mov     eax, ebx
0x18002cb96  mov     rbx, [rsp+48h+arg_0]
0x18002cb9b  add     rsp, 40h
0x18002cb9f  pop     rdi
0x18002cba0  retn
0x18002cba2  mov     ebx, 0C000000Dh
0x18002cba7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbae  lea     rax, WPP_GLOBAL_Control
0x18002cbb5  cmp     rcx, rax
0x18002cbb8  jz      short loc_18002CB8F
0x18002cbba  test    byte ptr [rcx+1Ch], 1
0x18002cbbe  jz      short loc_18002CB8F
0x18002cbc0  mov     rcx, [rcx+10h]
0x18002cbc4  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002cbcb  mov     [rsp+48h+var_18], 57h ; 'W'
0x18002cbd3  lea     r9, aStatus; "Status"
0x18002cbda  mov     [rsp+48h+var_20], rax
0x18002cbdf  mov     [rsp+48h+var_28], 0C000000Dh
0x18002cbe7  call    WPP_SF_sDsd
0x18002cbec  jmp     short loc_18002CB8F
0x18002cbee  mov     ebx, 0C000000Dh
0x18002cbf3  jmp     short loc_18002CB8F
0x18002cbf5  lea     rdx, aFips186dsarng; "FIPS186DSARNG"
0x18002cbfc  mov     rcx, rdi; String1
0x18002cbff  call    wcscmp_0
0x18002cc04  test    eax, eax
0x18002cc06  jz      short loc_18002CC25
0x18002cc08  lea     rdx, aDualecrng; "DUALECRNG"
0x18002cc0f  mov     rcx, rdi; String1
0x18002cc12  call    wcscmp_0
0x18002cc17  test    eax, eax
0x18002cc19  jz      short loc_18002CC2F
0x18002cc1b  mov     ebx, 0C00000BBh
0x18002cc20  jmp     loc_18002CB8F
0x18002cc25  mov     ebx, 50002h
0x18002cc2a  jmp     loc_18002CB69
0x18002cc2f  test    bl, 1
0x18002cc32  jnz     short loc_18002CC1B
0x18002cc34  mov     ebx, 50003h
0x18002cc39  jmp     loc_18002CB69
0x18002cc3e  mov     ebx, 0C0000017h
0x18002cc43  jmp     loc_18002CB8F
```
