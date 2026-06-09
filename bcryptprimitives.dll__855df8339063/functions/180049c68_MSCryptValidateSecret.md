# MSCryptValidateSecret

- ea: `0x180049c68`
- end: `0x180049d1e`
- name: `MSCryptValidateSecret`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800568e0`
- `0x18007e3d0`

## callees

- `0x18000ee60`
- `0x180049c68`
- `0x180049d24`

## string_xrefs

- `0x180049cd4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\common\secret.c`

## pseudocode

```c
__int64 __fastcall MSCryptValidateSecret(__int64 a1, _QWORD *a2, int a3)
{
  unsigned int v5; // ebx

  if ( a1 && a2 )
  {
    if ( *(_DWORD *)(a1 + 16) )
    {
      v5 = MSCryptValidateSecretHandle();
      *a2 = a1;
    }
    else
    {
      v5 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\common\\secret.c",
          129);
    }
  }
  else
  {
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\common\\secret.c",
        116);
  }
  return v5;
}

```

## disassembly

```asm
0x180049c68  mov     [rsp+arg_0], rbx
0x180049c6d  mov     [rsp+arg_8], rsi
0x180049c72  push    rdi
0x180049c73  sub     rsp, 40h
0x180049c77  mov     rsi, rdx
0x180049c7a  mov     rdi, rcx
0x180049c7d  test    rcx, rcx
0x180049c80  jz      short loc_180049CAA
0x180049c82  test    rdx, rdx
0x180049c85  jz      short loc_180049CAA
0x180049c87  cmp     dword ptr [rcx+10h], 0
0x180049c8b  jz      short loc_180049CF6
0x180049c8d  call    MSCryptValidateSecretHandle
0x180049c92  mov     ebx, eax
0x180049c94  mov     [rsi], rdi
0x180049c97  mov     rsi, [rsp+48h+arg_8]
0x180049c9c  mov     eax, ebx
0x180049c9e  mov     rbx, [rsp+48h+arg_0]
0x180049ca3  add     rsp, 40h
0x180049ca7  pop     rdi
0x180049ca8  retn
0x180049caa  mov     ebx, 0C000000Dh
0x180049caf  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cb6  lea     rax, WPP_GLOBAL_Control
0x180049cbd  cmp     rcx, rax
0x180049cc0  jz      short loc_180049C97
0x180049cc2  test    byte ptr [rcx+1Ch], 1
0x180049cc6  jz      short loc_180049C97
0x180049cc8  mov     [rsp+48h+var_18], 74h ; 't'
0x180049cd0  mov     rcx, [rcx+10h]
0x180049cd4  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049cdb  mov     [rsp+48h+var_20], rax
0x180049ce0  lea     r9, aStatus; "Status"
0x180049ce7  mov     [rsp+48h+var_28], 0C000000Dh
0x180049cef  call    WPP_SF_sDsd
0x180049cf4  jmp     short loc_180049C97
0x180049cf6  mov     ebx, 0C000000Dh
0x180049cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d02  lea     rax, WPP_GLOBAL_Control
0x180049d09  cmp     rcx, rax
0x180049d0c  jz      short loc_180049C97
0x180049d0e  test    byte ptr [rcx+1Ch], 1
0x180049d12  jz      short loc_180049C97
0x180049d14  mov     [rsp+48h+var_18], 81h
0x180049d1c  jmp     short loc_180049CD0
```
