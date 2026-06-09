# BCryptFinalizeKeyPair

- ea: `0x18000af30`
- end: `0x18000b08c`
- name: `BCryptFinalizeKeyPair`
- size: `348`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180007a7c`
- `0x180009740`
- `0x18000af30`
- `0x180015484`
- `0x18001c010`

## string_xrefs

- `0x18000afcb`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000b010`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000b055`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptFinalizeKeyPair(BCRYPT_KEY_HANDLE hKey, ULONG dwFlags)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  NTSTATUS v8; // ebx
  __int64 v10; // rcx
  char v11; // [rsp+20h] [rbp-28h]
  char v12; // [rsp+30h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_GLOBAL_Control, hKey, dwFlags);
  v4 = ValidateBaseKeyHandle(hKey);
  if ( !v4 )
  {
    v8 = -1073741816;
    if ( (_UNKNOWN **)v6 == &WPP_GLOBAL_Control || (*(_BYTE *)(v6 + 28) & 1) == 0 )
      return v8;
    v12 = -13;
    v11 = 8;
LABEL_19:
    v10 = *(_QWORD *)(v6 + 16);
    goto LABEL_14;
  }
  v5 = *(_QWORD *)(v4 + 8);
  if ( *(_DWORD *)(v5 + 36) != 3 )
  {
    if ( *(_DWORD *)(v5 + 36) == 4 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v5 + 120))(*(_QWORD *)(v4 + 16), dwFlags);
      goto LABEL_8;
    }
    if ( *(_DWORD *)(v5 + 36) != 5 && *(_DWORD *)(v5 + 36) != 8 )
    {
      v8 = -1073741637;
      if ( (_UNKNOWN **)v6 == &WPP_GLOBAL_Control || (*(_BYTE *)(v6 + 28) & 1) == 0 )
        return v8;
      v12 = 15;
      v11 = -69;
      goto LABEL_19;
    }
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v5 + 96))(*(_QWORD *)(v4 + 16), dwFlags);
LABEL_8:
  v8 = v7;
  if ( v7 >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v12 = 23;
    v11 = v7;
LABEL_14:
    WPP_SF_sDsd(
      v10,
      v5,
      v6,
      (unsigned int)"Status",
      v11,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      v12);
  }
  return v8;
}

```

## disassembly

```asm
0x18000af30  mov     [rsp+arg_0], rbx
0x18000af35  mov     [rsp+arg_8], rsi
0x18000af3a  push    rdi
0x18000af3b  sub     rsp, 40h
0x18000af3f  mov     edi, edx
0x18000af41  mov     rbx, rcx
0x18000af44  mov     r8, cs:WPP_GLOBAL_Control
0x18000af4b  lea     rsi, WPP_GLOBAL_Control
0x18000af52  cmp     r8, rsi
0x18000af55  jz      short loc_18000AF62
0x18000af57  test    byte ptr [r8+1Ch], 4
0x18000af5c  jnz     loc_18000B06B
0x18000af62  mov     rcx, rbx
0x18000af65  call    ValidateBaseKeyHandle
0x18000af6a  mov     r9, rax
0x18000af6d  test    rax, rax
0x18000af70  jz      loc_18000AFF7
0x18000af76  mov     rdx, [rax+8]
0x18000af7a  mov     ecx, [rdx+24h]
0x18000af7d  sub     ecx, 3
0x18000af80  jz      short loc_18000AFF1
0x18000af82  sub     ecx, 1
0x18000af85  jnz     loc_18000B02A
0x18000af8b  mov     rax, [rdx+78h]
0x18000af8f  mov     rcx, [r9+10h]
0x18000af93  mov     edx, edi
0x18000af95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af9a  mov     ebx, eax
0x18000af9c  test    eax, eax
0x18000af9e  js      short loc_18000AFB5
0x18000afa0  xor     ebx, ebx
0x18000afa2  mov     rsi, [rsp+48h+arg_8]
0x18000afa7  mov     eax, ebx
0x18000afa9  mov     rbx, [rsp+48h+arg_0]
0x18000afae  add     rsp, 40h
0x18000afb2  pop     rdi
0x18000afb3  retn
0x18000afb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afbc  cmp     rcx, rsi
0x18000afbf  jz      short loc_18000AFA2
0x18000afc1  test    byte ptr [rcx+1Ch], 1
0x18000afc5  jz      short loc_18000AFA2
0x18000afc7  mov     rcx, [rcx+10h]
0x18000afcb  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000afd2  mov     dword ptr [rsp+48h+var_18], 0E17h
0x18000afda  mov     [rsp+48h+var_20], rax
0x18000afdf  mov     dword ptr [rsp+48h+var_28], ebx
0x18000afe3  lea     r9, aStatus; "Status"
0x18000afea  call    WPP_SF_sDsd
0x18000afef  jmp     short loc_18000AFA2
0x18000aff1  mov     rax, [rdx+60h]
0x18000aff5  jmp     short loc_18000AF8F
0x18000aff7  mov     ebx, 0C0000008h
0x18000affc  cmp     r8, rsi
0x18000afff  jz      short loc_18000AFA2
0x18000b001  test    byte ptr [r8+1Ch], 1
0x18000b006  jz      short loc_18000AFA2
0x18000b008  mov     dword ptr [rsp+48h+var_18], 0DF3h
0x18000b010  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b017  mov     [rsp+48h+var_20], rax
0x18000b01c  mov     dword ptr [rsp+48h+var_28], 0C0000008h
0x18000b024  mov     rcx, [r8+10h]
0x18000b028  jmp     short loc_18000AFE3
0x18000b02a  sub     ecx, 1
0x18000b02d  jz      short loc_18000AFF1
0x18000b02f  cmp     ecx, 3
0x18000b032  jz      short loc_18000AFF1
0x18000b034  mov     ebx, 0C00000BBh
0x18000b039  cmp     r8, rsi
0x18000b03c  jz      loc_18000AFA2
0x18000b042  test    byte ptr [r8+1Ch], 1
0x18000b047  jz      loc_18000AFA2
0x18000b04d  mov     dword ptr [rsp+48h+var_18], 0E0Fh
0x18000b055  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b05c  mov     [rsp+48h+var_20], rax
0x18000b061  mov     dword ptr [rsp+48h+var_28], 0C00000BBh
0x18000b069  jmp     short loc_18000B024
0x18000b06b  mov     rcx, [r8+10h]
0x18000b06f  mov     edx, 16h
0x18000b074  mov     r9, rbx
0x18000b077  mov     dword ptr [rsp+48h+var_28], edi
0x18000b07b  call    WPP_SF_qD
0x18000b080  mov     r8, cs:WPP_GLOBAL_Control
0x18000b087  jmp     loc_18000AF62
```
