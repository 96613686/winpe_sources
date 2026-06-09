# MSCryptKDF_TRUNCATE

- ea: `0x18004bd10`
- end: `0x18004be0d`
- name: `MSCryptKDF_TRUNCATE`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18004bd10`

## string_xrefs

- `0x18004bdab`: `onecore\ds\security\cryptoapi\ncrypt\kdf\truncate.c`
- `0x18004bdeb`: `onecore\ds\security\cryptoapi\ncrypt\kdf\truncate.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDF_TRUNCATE(
        _BYTE *a1,
        unsigned int a2,
        int a3,
        __int64 a4,
        unsigned __int64 a5,
        unsigned int a6,
        unsigned int *a7)
{
  _BYTE *v7; // r9
  unsigned int v8; // ebx
  _BYTE *i; // rcx

  v7 = a1;
  if ( a1 && a2 )
  {
    if ( (unsigned int)(a3 - 196615) <= 3 || a3 == 196610 )
    {
      if ( a5 && a6 )
      {
        v8 = 0;
        if ( a2 >= a6 )
          a2 = a6;
        for ( i = (_BYTE *)(a2 + a5 - 1); (unsigned __int64)i >= a5; --i )
          *i = *v7++;
        *a7 = a2;
      }
      else
      {
        v8 = 0;
        *a7 = a2;
      }
    }
    else
    {
      v8 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\truncate.c", 62);
    }
  }
  else
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\truncate.c",
        49);
  }
  return v8;
}

```

## disassembly

```asm
0x18004bd10  push    rbx
0x18004bd12  sub     rsp, 40h
0x18004bd16  mov     r9, rcx
0x18004bd19  test    rcx, rcx
0x18004bd1c  jz      short loc_18004BD89
0x18004bd1e  test    edx, edx
0x18004bd20  jz      short loc_18004BD89
0x18004bd22  lea     eax, [r8-30007h]
0x18004bd29  cmp     eax, 3
0x18004bd2c  ja      loc_18004BDD8
0x18004bd32  mov     r8, [rsp+48h+arg_20]
0x18004bd37  test    r8, r8
0x18004bd3a  jnz     short loc_18004BD51
0x18004bd3c  mov     rax, [rsp+48h+arg_30]
0x18004bd44  xor     ebx, ebx
0x18004bd46  mov     [rax], edx
0x18004bd48  mov     eax, ebx
0x18004bd4a  add     rsp, 40h
0x18004bd4e  pop     rbx
0x18004bd4f  retn
0x18004bd51  mov     eax, [rsp+48h+arg_28]
0x18004bd55  test    eax, eax
0x18004bd57  jz      short loc_18004BD3C
0x18004bd59  xor     ebx, ebx
0x18004bd5b  lea     rcx, [r8-1]
0x18004bd5f  cmp     edx, eax
0x18004bd61  cmovnb  edx, eax
0x18004bd64  mov     r10d, edx
0x18004bd67  add     rcx, r10
0x18004bd6a  jmp     short loc_18004BD77
0x18004bd6c  mov     al, [r9]
0x18004bd6f  mov     [rcx], al
0x18004bd71  dec     rcx
0x18004bd74  inc     r9
0x18004bd77  cmp     rcx, r8
0x18004bd7a  jnb     short loc_18004BD6C
0x18004bd7c  mov     rax, [rsp+48h+arg_30]
0x18004bd84  mov     [rax], r10d
0x18004bd87  jmp     short loc_18004BD48
0x18004bd89  mov     ebx, 0C000000Dh
0x18004bd8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd95  lea     rax, WPP_GLOBAL_Control
0x18004bd9c  cmp     rcx, rax
0x18004bd9f  jz      short loc_18004BD48
0x18004bda1  test    byte ptr [rcx+1Ch], 1
0x18004bda5  jz      short loc_18004BD48
0x18004bda7  mov     rcx, [rcx+10h]
0x18004bdab  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004bdb2  mov     [rsp+48h+var_18], 31h ; '1'
0x18004bdba  lea     r9, aStatus; "Status"
0x18004bdc1  mov     [rsp+48h+var_20], rax
0x18004bdc6  mov     [rsp+48h+var_28], 0C000000Dh
0x18004bdce  call    WPP_SF_sDsd
0x18004bdd3  jmp     loc_18004BD48
0x18004bdd8  cmp     r8d, 30002h
0x18004bddf  jz      loc_18004BD32
0x18004bde5  mov     r9d, 3Eh ; '>'
0x18004bdeb  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004bdf2  lea     rdx, aStatus; "Status"
0x18004bdf9  mov     ecx, 0C000000Dh
0x18004bdfe  mov     ebx, 0C000000Dh
0x18004be03  call    DebugTraceError
0x18004be08  jmp     loc_18004BD48
```
