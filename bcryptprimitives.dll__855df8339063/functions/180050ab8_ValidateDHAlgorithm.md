# ValidateDHAlgorithm

- ea: `0x180050ab8`
- end: `0x180050bc3`
- name: `ValidateDHAlgorithm`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800508b0`
- `0x180068050`
- `0x1800686e0`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180050ab8`

## string_xrefs

- `0x180050b55`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x180050b8d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall ValidateDHAlgorithm(_DWORD *a1, unsigned int a2, unsigned int *a3, _QWORD *a4)
{
  unsigned int v4; // ebx
  __int64 v6; // r9

  if ( a1 && a3 && a4 )
  {
    if ( a2 && ((a2 & 7) != 0 || a2 - 512 > 0xE00) )
    {
      v6 = 137;
    }
    else if ( *a1 == 16 && a1[1] == 1297301836 && a1[2] == 196610 )
    {
      if ( !a2 )
      {
        *a3 = 128;
        goto LABEL_12;
      }
      *a3 = a2 >> 3;
      if ( a2 == 8 * (a2 >> 3) )
      {
LABEL_12:
        v4 = 0;
        *a4 = a1;
        return v4;
      }
      v6 = 176;
    }
    else
    {
      v6 = 151;
    }
    v4 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v6);
    return v4;
  }
  v4 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c",
      124);
  return v4;
}

```

## disassembly

```asm
0x180050ab8  push    rbx
0x180050aba  sub     rsp, 40h
0x180050abe  test    rcx, rcx
0x180050ac1  jz      short loc_180050B33
0x180050ac3  test    r8, r8
0x180050ac6  jz      short loc_180050B33
0x180050ac8  test    r9, r9
0x180050acb  jz      short loc_180050B33
0x180050acd  test    edx, edx
0x180050acf  jz      short loc_180050AEB
0x180050ad1  test    dl, 7
0x180050ad4  jnz     loc_180050B7F
0x180050ada  lea     eax, [rdx-200h]
0x180050ae0  cmp     eax, 0E00h
0x180050ae5  ja      loc_180050B7F
0x180050aeb  cmp     dword ptr [rcx], 10h
0x180050aee  jnz     loc_180050B87
0x180050af4  cmp     dword ptr [rcx+4], 4D53414Ch
0x180050afb  jnz     loc_180050B87
0x180050b01  cmp     dword ptr [rcx+8], 30002h
0x180050b08  jnz     short loc_180050B87
0x180050b0a  test    edx, edx
0x180050b0c  jz      loc_180050BAF
0x180050b12  mov     eax, edx
0x180050b14  shr     eax, 3
0x180050b17  mov     [r8], eax
0x180050b1a  shl     eax, 3
0x180050b1d  cmp     edx, eax
0x180050b1f  jnz     loc_180050BBB
0x180050b25  xor     ebx, ebx
0x180050b27  mov     [r9], rcx
0x180050b2a  mov     eax, ebx
0x180050b2c  add     rsp, 40h
0x180050b30  pop     rbx
0x180050b31  retn
0x180050b33  mov     ebx, 0C000000Dh
0x180050b38  mov     rcx, cs:WPP_GLOBAL_Control
0x180050b3f  lea     rax, WPP_GLOBAL_Control
0x180050b46  cmp     rcx, rax
0x180050b49  jz      short loc_180050B2A
0x180050b4b  test    byte ptr [rcx+1Ch], 1
0x180050b4f  jz      short loc_180050B2A
0x180050b51  mov     rcx, [rcx+10h]
0x180050b55  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180050b5c  mov     [rsp+48h+var_18], 7Ch ; '|'
0x180050b64  lea     r9, aStatus; "Status"
0x180050b6b  mov     [rsp+48h+var_20], rax
0x180050b70  mov     [rsp+48h+var_28], 0C000000Dh
0x180050b78  call    WPP_SF_sDsd
0x180050b7d  jmp     short loc_180050B2A
0x180050b7f  mov     r9d, 89h
0x180050b85  jmp     short loc_180050B8D
0x180050b87  mov     r9d, 97h
0x180050b8d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180050b94  mov     ecx, 0C000000Dh
0x180050b99  lea     rdx, aStatus; "Status"
0x180050ba0  mov     ebx, 0C000000Dh
0x180050ba5  call    DebugTraceError
0x180050baa  jmp     loc_180050B2A
0x180050baf  mov     dword ptr [r8], 80h
0x180050bb6  jmp     loc_180050B25
0x180050bbb  mov     r9d, 0B0h
0x180050bc1  jmp     short loc_180050B8D
```
