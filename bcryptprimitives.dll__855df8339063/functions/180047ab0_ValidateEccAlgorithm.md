# ValidateEccAlgorithm

- ea: `0x180047ab0`
- end: `0x180047c42`
- name: `ValidateEccAlgorithm`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004490c`
- `0x1800476d0`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180047ab0`

## string_xrefs

- `0x180047b7e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180047c20`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ValidateEccAlgorithm(__int64 a1, int a2, int a3, _DWORD *a4, _QWORD *a5)
{
  wchar_t **v8; // r9
  __int64 i; // rax
  _QWORD *v10; // rcx
  int v11; // edx
  unsigned int v12; // ebx

  if ( a1 && a5 )
  {
    if ( *(_DWORD *)(a1 + 4) == 1297301836 && *(_DWORD *)a1 == 24 )
    {
      v8 = &off_180084710;
      if ( !a3 )
        v8 = &off_1800847D0;
      for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
      {
        a3 = 6 * i;
        if ( *(_DWORD *)(a1 + 8) == LODWORD(v8[6 * i + 1]) )
        {
          if ( v8[6 * i] )
          {
            v10 = *(_QWORD **)(a1 + 16);
            if ( v10 )
            {
              v11 = *(_DWORD *)(v10[1] + 12LL);
              LODWORD(v10) = *(_DWORD *)(*v10 + 12LL);
            }
            else
            {
              v11 = 0;
            }
            *a4 = (_DWORD)v10;
            if ( !a2 || v11 == a2 )
            {
              *a5 = a1;
              return 0;
            }
            else
            {
              v12 = -1073741811;
              DebugTraceError(
                3221225485LL,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                526);
            }
            return v12;
          }
          break;
        }
      }
      v12 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          249);
    }
    else
    {
      v12 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          241);
    }
  }
  else
  {
    v12 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        231);
  }
  return v12;
}

```

## disassembly

```asm
0x180047ab0  mov     [rsp+arg_0], rbx
0x180047ab5  push    rdi
0x180047ab6  sub     rsp, 40h
0x180047aba  mov     rdi, r9
0x180047abd  mov     ebx, edx
0x180047abf  mov     r10, rcx
0x180047ac2  test    rcx, rcx
0x180047ac5  jz      loc_180047B54
0x180047acb  mov     r11, [rsp+48h+arg_20]
0x180047ad0  test    r11, r11
0x180047ad3  jz      short loc_180047B54
0x180047ad5  cmp     dword ptr [rcx+4], 4D53414Ch
0x180047adc  jnz     loc_180047BDF
0x180047ae2  cmp     dword ptr [rcx], 18h
0x180047ae5  jnz     loc_180047BDF
0x180047aeb  test    r8d, r8d
0x180047aee  lea     rax, off_1800847D0; "ECDH_P256"
0x180047af5  lea     r9, off_180084710; "ECDSA_P256"
0x180047afc  cmovz   r9, rax
0x180047b00  xor     eax, eax
0x180047b02  cmp     eax, 4
0x180047b05  jnb     loc_180047BAF
0x180047b0b  lea     r8, [rax+rax*2]
0x180047b0f  add     r8, r8
0x180047b12  mov     ecx, [r9+r8*8+8]
0x180047b17  cmp     [r10+8], ecx
0x180047b1b  jz      short loc_180047B21
0x180047b1d  inc     eax
0x180047b1f  jmp     short loc_180047B02
0x180047b21  cmp     qword ptr [r9+r8*8], 0
0x180047b26  jz      loc_180047BAF
0x180047b2c  mov     rcx, [r10+10h]
0x180047b30  test    rcx, rcx
0x180047b33  jnz     short loc_180047BA0
0x180047b35  xor     edx, edx
0x180047b37  mov     [rdi], ecx
0x180047b39  test    ebx, ebx
0x180047b3b  jnz     loc_180047C12
0x180047b41  mov     [r11], r10
0x180047b44  xor     ebx, ebx
0x180047b46  mov     eax, ebx
0x180047b48  mov     rbx, [rsp+48h+arg_0]
0x180047b4d  add     rsp, 40h
0x180047b51  pop     rdi
0x180047b52  retn
0x180047b54  mov     ebx, 0C000000Dh
0x180047b59  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b60  lea     rax, WPP_GLOBAL_Control
0x180047b67  cmp     rcx, rax
0x180047b6a  jz      short loc_180047B46
0x180047b6c  test    byte ptr [rcx+1Ch], 1
0x180047b70  jz      short loc_180047B46
0x180047b72  mov     [rsp+48h+var_18], 1E7h
0x180047b7a  mov     rcx, [rcx+10h]
0x180047b7e  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047b85  mov     [rsp+48h+var_20], rax
0x180047b8a  lea     r9, aStatus; "Status"
0x180047b91  mov     [rsp+48h+var_28], 0C000000Dh
0x180047b99  call    WPP_SF_sDsd
0x180047b9e  jmp     short loc_180047B46
0x180047ba0  mov     rax, [rcx+8]
0x180047ba4  mov     edx, [rax+0Ch]
0x180047ba7  mov     rax, [rcx]
0x180047baa  mov     ecx, [rax+0Ch]
0x180047bad  jmp     short loc_180047B37
0x180047baf  mov     ebx, 0C000000Dh
0x180047bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180047bbb  lea     rax, WPP_GLOBAL_Control
0x180047bc2  cmp     rcx, rax
0x180047bc5  jz      loc_180047B46
0x180047bcb  test    byte ptr [rcx+1Ch], 1
0x180047bcf  jz      loc_180047B46
0x180047bd5  mov     [rsp+48h+var_18], 1F9h
0x180047bdd  jmp     short loc_180047B7A
0x180047bdf  mov     ebx, 0C000000Dh
0x180047be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180047beb  lea     rax, WPP_GLOBAL_Control
0x180047bf2  cmp     rcx, rax
0x180047bf5  jz      loc_180047B46
0x180047bfb  test    byte ptr [rcx+1Ch], 1
0x180047bff  jz      loc_180047B46
0x180047c05  mov     [rsp+48h+var_18], 1F1h
0x180047c0d  jmp     loc_180047B7A
0x180047c12  cmp     edx, ebx
0x180047c14  jz      loc_180047B41
0x180047c1a  mov     r9d, 20Eh
0x180047c20  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047c27  lea     rdx, aStatus; "Status"
0x180047c2e  mov     ecx, 0C000000Dh
0x180047c33  mov     ebx, 0C000000Dh
0x180047c38  call    DebugTraceError
0x180047c3d  jmp     loc_180047B46
```
