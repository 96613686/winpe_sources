# MSCryptRsaEncryptSignHash

- ea: `0x18003ce80`
- end: `0x18003cf2a`
- name: `MSCryptRsaEncryptSignHash`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ee60`
- `0x18003ce80`
- `0x18003cfd4`
- `0x18003d300`

## string_xrefs

- `0x18003cf00`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaEncryptSignHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int *a7,
        int a8)
{
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // r9d
  __int64 v12; // r10
  unsigned int v13; // ebx

  v8 = validateMSCryptRsaKey(a1);
  if ( v8 && *(_DWORD *)(v8 + 16) )
  {
    **(_DWORD **)(v8 + 32) |= 0x1000u;
    return (unsigned int)MSCryptRsaSignHash(v12, v9, v10, v11, a5, a6, a7, a8);
  }
  else
  {
    v13 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        v10,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        102);
  }
  return v13;
}

```

## disassembly

```asm
0x18003ce80  push    rbx
0x18003ce82  sub     rsp, 40h
0x18003ce86  mov     r10, rcx
0x18003ce89  call    validateMSCryptRsaKey
0x18003ce8e  test    rax, rax
0x18003ce91  jz      short loc_18003CEDE
0x18003ce93  cmp     dword ptr [rax+10h], 0
0x18003ce97  jz      short loc_18003CEDE
0x18003ce99  mov     rax, [rax+20h]
0x18003ce9d  mov     rcx, r10
0x18003cea0  bts     dword ptr [rax], 0Ch
0x18003cea4  mov     eax, [rsp+48h+arg_38]
0x18003ceab  mov     [rsp+48h+var_10], eax
0x18003ceaf  mov     rax, [rsp+48h+arg_30]
0x18003ceb7  mov     [rsp+48h+var_18], rax
0x18003cebc  mov     eax, [rsp+48h+arg_28]
0x18003cec0  mov     dword ptr [rsp+48h+var_20], eax
0x18003cec4  mov     rax, [rsp+48h+arg_20]
0x18003cec9  mov     [rsp+48h+var_28], rax
0x18003cece  call    MSCryptRsaSignHash
0x18003ced3  mov     ebx, eax
0x18003ced5  mov     eax, ebx
0x18003ced7  add     rsp, 40h
0x18003cedb  pop     rbx
0x18003cedc  retn
0x18003cede  mov     ebx, 0C0000008h
0x18003cee3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ceea  lea     rax, WPP_GLOBAL_Control
0x18003cef1  cmp     rcx, rax
0x18003cef4  jz      short loc_18003CED5
0x18003cef6  test    byte ptr [rcx+1Ch], 1
0x18003cefa  jz      short loc_18003CED5
0x18003cefc  mov     rcx, [rcx+10h]
0x18003cf00  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003cf07  mov     dword ptr [rsp+48h+var_18], 866h
0x18003cf0f  lea     r9, aStatus; "Status"
0x18003cf16  mov     [rsp+48h+var_20], rax
0x18003cf1b  mov     dword ptr [rsp+48h+var_28], 0C0000008h
0x18003cf23  call    WPP_SF_sDsd
0x18003cf28  jmp     short loc_18003CED5
```
