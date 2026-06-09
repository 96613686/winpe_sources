# MSCryptRsaEncryptVerifySignature

- ea: `0x18003cf30`
- end: `0x18003cfcd`
- name: `MSCryptRsaEncryptVerifySignature`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ee60`
- `0x18003cf30`
- `0x18003cfd4`
- `0x18003d000`

## string_xrefs

- `0x18003cfa3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaEncryptVerifySignature(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // r9d
  __int64 v11; // r10
  unsigned int v12; // ebx

  v7 = validateMSCryptRsaKey(a1);
  if ( v7 && *(_DWORD *)(v7 + 16) )
  {
    **(_DWORD **)(v7 + 32) |= 0x1000u;
    return (unsigned int)MSCryptRsaVerifySignature(v11, v8, v9, v10, a5, a6, a7);
  }
  else
  {
    v12 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        v9,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        29);
  }
  return v12;
}

```

## disassembly

```asm
0x18003cf30  push    rbx
0x18003cf32  sub     rsp, 40h
0x18003cf36  mov     r10, rcx
0x18003cf39  call    validateMSCryptRsaKey
0x18003cf3e  test    rax, rax
0x18003cf41  jz      short loc_18003CF81
0x18003cf43  cmp     dword ptr [rax+10h], 0
0x18003cf47  jz      short loc_18003CF81
0x18003cf49  mov     rax, [rax+20h]
0x18003cf4d  mov     rcx, r10
0x18003cf50  bts     dword ptr [rax], 0Ch
0x18003cf54  mov     eax, [rsp+48h+arg_30]
0x18003cf5b  mov     [rsp+48h+var_18], eax
0x18003cf5f  mov     eax, [rsp+48h+arg_28]
0x18003cf63  mov     dword ptr [rsp+48h+var_20], eax
0x18003cf67  mov     rax, [rsp+48h+arg_20]
0x18003cf6c  mov     [rsp+48h+var_28], rax
0x18003cf71  call    MSCryptRsaVerifySignature
0x18003cf76  mov     ebx, eax
0x18003cf78  mov     eax, ebx
0x18003cf7a  add     rsp, 40h
0x18003cf7e  pop     rbx
0x18003cf7f  retn
0x18003cf81  mov     ebx, 0C0000008h
0x18003cf86  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf8d  lea     rax, WPP_GLOBAL_Control
0x18003cf94  cmp     rcx, rax
0x18003cf97  jz      short loc_18003CF78
0x18003cf99  test    byte ptr [rcx+1Ch], 1
0x18003cf9d  jz      short loc_18003CF78
0x18003cf9f  mov     rcx, [rcx+10h]
0x18003cfa3  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003cfaa  mov     [rsp+48h+var_18], 91Dh
0x18003cfb2  lea     r9, aStatus; "Status"
0x18003cfb9  mov     [rsp+48h+var_20], rax
0x18003cfbe  mov     dword ptr [rsp+48h+var_28], 0C0000008h
0x18003cfc6  call    WPP_SF_sDsd
0x18003cfcb  jmp     short loc_18003CF78
```
