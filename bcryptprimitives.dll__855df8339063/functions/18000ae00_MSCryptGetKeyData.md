# MSCryptGetKeyData

- ea: `0x18000ae00`
- end: `0x18000afca`
- name: `MSCryptGetKeyData`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000afd0`

## callees

- `0x18000ae00`
- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x18002b960`
- `0x180063170`
- `0x18007f790`

## string_xrefs

- `0x18000aefe`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x18000af50`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`
- `0x18000afa8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\aeskeywrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetKeyData(_DWORD *a1, void *a2, unsigned int a3)
{
  size_t v3; // r14
  unsigned int v6; // edi
  __int64 v7; // rbp
  _BYTE *v8; // rbx
  char *v9; // rsi
  int v10; // edx
  int v11; // edi
  __int64 v13; // rax
  int v14; // edx
  _BYTE *i; // rax
  _DWORD v16[4]; // [rsp+40h] [rbp-A8h] BYREF
  char v17; // [rsp+50h] [rbp-98h] BYREF

  v3 = a3;
  v16[0] = 0;
  v6 = a3 + 12;
  v7 = a3 + 12;
  if ( a3 + 12 <= 0x4C )
  {
    v8 = 0;
    v9 = &v17;
LABEL_3:
    v11 = MSCryptExportKey(a1, 0, L"KeyDataBlob", v9, v6, v16, 0);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
          (unsigned int)"Status",
          v11,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
          94);
    }
    else if ( (_DWORD)v3 == *((_DWORD *)v9 + 2) )
    {
      memcpy_0(a2, v9 + 12, v3);
      v11 = 0;
    }
    else
    {
      v11 = -1073741811;
      DebugTraceError(
        3221225485LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
        103);
    }
    if ( v8 )
    {
      for ( i = v8; v7; --v7 )
        *i++ = 0;
      MSCryptFree(v8);
    }
    return (unsigned int)v11;
  }
  v13 = SafeAllocaAllocateFromHeap(v6);
  v8 = (_BYTE *)v13;
  if ( v13 )
  {
    v9 = (char *)v13;
    goto LABEL_3;
  }
  v11 = -1073741801;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
      (unsigned int)"Status",
      23,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\aeskeywrap.c",
      77);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000ae00  push    rbx
0x18000ae02  push    rbp
0x18000ae03  push    rsi
0x18000ae04  push    rdi
0x18000ae05  push    r12
0x18000ae07  push    r14
0x18000ae09  push    r15
0x18000ae0b  sub     rsp, 0B0h
0x18000ae12  mov     rax, cs:__security_cookie
0x18000ae19  xor     rax, rsp
0x18000ae1c  mov     [rsp+0E8h+var_48], rax
0x18000ae24  mov     r14d, r8d
0x18000ae27  mov     r15, rdx
0x18000ae2a  mov     r12, rcx
0x18000ae2d  mov     [rsp+0E8h+var_A8], 0
0x18000ae35  lea     edi, [r14+0Ch]
0x18000ae39  mov     ebp, edi
0x18000ae3b  cmp     edi, 4Ch ; 'L'
0x18000ae3e  ja      loc_18000AEC8
0x18000ae44  xor     ebx, ebx
0x18000ae46  lea     rsi, [rsp+0E8h+var_98]
0x18000ae4b  lea     rax, [rsp+0E8h+var_A8]
0x18000ae50  mov     [rsp+0E8h+var_B8], 0
0x18000ae58  mov     [rsp+0E8h+var_C0], rax
0x18000ae5d  lea     r8, aKeydatablob; "KeyDataBlob"
0x18000ae64  mov     r9, rsi
0x18000ae67  mov     [rsp+0E8h+var_C8], edi
0x18000ae6b  xor     edx, edx
0x18000ae6d  mov     rcx, r12
0x18000ae70  call    MSCryptExportKey
0x18000ae75  mov     edi, eax
0x18000ae77  test    eax, eax
0x18000ae79  js      loc_18000AF2B
0x18000ae7f  cmp     r14d, [rsi+8]
0x18000ae83  jnz     loc_18000AFA2
0x18000ae89  mov     r8, r14; Size
0x18000ae8c  lea     rdx, [rsi+0Ch]; Src
0x18000ae90  mov     rcx, r15; void *
0x18000ae93  call    memcpy_0
0x18000ae98  xor     edi, edi
0x18000ae9a  test    rbx, rbx
0x18000ae9d  jnz     loc_18000AF79
0x18000aea3  mov     eax, edi
0x18000aea5  mov     rcx, [rsp+0E8h+var_48]
0x18000aead  xor     rcx, rsp; StackCookie
0x18000aeb0  call    __security_check_cookie
0x18000aeb5  add     rsp, 0B0h
0x18000aebc  pop     r15
0x18000aebe  pop     r14
0x18000aec0  pop     r12
0x18000aec2  pop     rdi
0x18000aec3  pop     rsi
0x18000aec4  pop     rbp
0x18000aec5  pop     rbx
0x18000aec6  retn
0x18000aec8  mov     rcx, rbp
0x18000aecb  call    SafeAllocaAllocateFromHeap
0x18000aed0  mov     rbx, rax
0x18000aed3  test    rax, rax
0x18000aed6  jnz     loc_18000AF9A
0x18000aedc  mov     edi, 0C0000017h
0x18000aee1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aee8  lea     rax, WPP_GLOBAL_Control
0x18000aeef  cmp     rcx, rax
0x18000aef2  jz      short loc_18000AEA3
0x18000aef4  test    byte ptr [rcx+1Ch], 1
0x18000aef8  jz      short loc_18000AEA3
0x18000aefa  mov     rcx, [rcx+10h]
0x18000aefe  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000af05  mov     [rsp+0E8h+var_B8], 4Dh ; 'M'
0x18000af0d  lea     r9, aStatus; "Status"
0x18000af14  mov     [rsp+0E8h+var_C0], r8
0x18000af19  mov     [rsp+0E8h+var_C8], 0C0000017h
0x18000af21  call    WPP_SF_sDsd
0x18000af26  jmp     loc_18000AEA3
0x18000af2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af32  lea     rax, WPP_GLOBAL_Control
0x18000af39  cmp     rcx, rax
0x18000af3c  jz      loc_18000AE9A
0x18000af42  test    byte ptr [rcx+1Ch], 1
0x18000af46  jz      loc_18000AE9A
0x18000af4c  mov     rcx, [rcx+10h]
0x18000af50  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000af57  mov     [rsp+0E8h+var_B8], 5Eh ; '^'
0x18000af5f  lea     r9, aStatus; "Status"
0x18000af66  mov     [rsp+0E8h+var_C0], r8
0x18000af6b  mov     [rsp+0E8h+var_C8], edi
0x18000af6f  call    WPP_SF_sDsd
0x18000af74  jmp     loc_18000AE9A
0x18000af79  mov     rax, rbx
0x18000af7c  test    rbp, rbp
0x18000af7f  jz      short loc_18000AF8D
0x18000af81  mov     byte ptr [rax], 0
0x18000af84  inc     rax
0x18000af87  sub     rbp, 1
0x18000af8b  jnz     short loc_18000AF81
0x18000af8d  mov     rcx, rbx
0x18000af90  call    MSCryptFree
0x18000af95  jmp     loc_18000AEA3
0x18000af9a  mov     rsi, rax
0x18000af9d  jmp     loc_18000AE4B
0x18000afa2  mov     r9d, 67h ; 'g'
0x18000afa8  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000afaf  lea     rdx, aStatus; "Status"
0x18000afb6  mov     ecx, 0C000000Dh
0x18000afbb  mov     edi, 0C000000Dh
0x18000afc0  call    DebugTraceError
0x18000afc5  jmp     loc_18000AE9A
```
