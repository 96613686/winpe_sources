# BCryptSetProperty

- ea: `0x180007b50`
- end: `0x180007d58`
- name: `BCryptSetProperty`
- size: `520`
- prototype: `NTSTATUS __stdcall(BCRYPT_HANDLE hObject, LPCWSTR pszProperty, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006bd0`

## callees

- `0x180005060`
- `0x180006bd0`
- `0x180007a7c`
- `0x180007b50`
- `0x18000d000`
- `0x18000f820`
- `0x18001c010`

## string_xrefs

- `0x180007c43`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180007cbb`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180007ce3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180007d22`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptSetProperty(
        BCRYPT_HANDLE hObject,
        LPCWSTR pszProperty,
        PUCHAR pbInput,
        ULONG cbInput,
        ULONG dwFlags)
{
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // r10
  int v13; // ecx
  int v14; // eax
  NTSTATUS v15; // ebx
  __int64 v17; // rax
  __int64 v18; // r10

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qSqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)pszProperty,
      (_DWORD)pbInput,
      (_DWORD)hObject,
      (__int64)pszProperty,
      (char)pbInput,
      cbInput,
      dwFlags);
  if ( !pszProperty )
  {
    v15 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    return v15;
  }
  v9 = ValidateBaseAlgHandle(hObject);
  if ( v9 )
  {
    if ( *(int *)(v9 + 8) < 0 )
    {
      v15 = -1073741790;
      DebugTraceError(3221225506LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
      return v15;
    }
    v12 = *(_QWORD *)(v9 + 24);
    goto LABEL_8;
  }
  if ( ((unsigned __int8)hObject & 0xF) != 1 )
  {
    v17 = ValidateBaseObjectHandle(hObject);
    v18 = v17;
    if ( v17 )
    {
      v9 = *(_QWORD *)(v17 + 8);
      v12 = *(_QWORD *)(v18 + 16);
LABEL_8:
      v13 = *(_DWORD *)(v9 + 36);
      if ( v13 == 1 )
      {
LABEL_9:
        v14 = (*(__int64 (__fastcall **)(__int64, LPCWSTR, PUCHAR, _QWORD, ULONG))(v9 + 72))(
                v12,
                pszProperty,
                pbInput,
                cbInput,
                dwFlags);
        v15 = v14;
        if ( v14 < 0 )
          DebugTraceError((unsigned int)v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
        else
          return 0;
      }
      else
      {
        switch ( v13 )
        {
          case 2:
          case 3:
          case 4:
          case 5:
          case 6:
          case 7:
          case 8:
            goto LABEL_9;
          default:
            v15 = -1073741816;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v10,
                v11,
                (unsigned int)"Status",
                8,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                205);
            break;
        }
      }
      return v15;
    }
  }
  v15 = -1073741816;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v11,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      165);
  return v15;
}

```

## disassembly

```asm
0x180007b50  push    rbx
0x180007b52  push    rbp
0x180007b53  push    rsi
0x180007b54  push    rdi
0x180007b55  push    r14
0x180007b57  push    r15
0x180007b59  sub     rsp, 48h
0x180007b5d  mov     esi, r9d
0x180007b60  mov     rbp, r8
0x180007b63  mov     rbx, rdx
0x180007b66  mov     rdi, rcx
0x180007b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b70  lea     r15, WPP_GLOBAL_Control
0x180007b77  mov     r14d, [rsp+78h+dwFlags]
0x180007b7f  cmp     rcx, r15
0x180007b82  jz      short loc_180007B8E
0x180007b84  test    byte ptr [rcx+1Ch], 4
0x180007b88  jnz     loc_180007C91
0x180007b8e  test    rbx, rbx
0x180007b91  jz      loc_180007CB5
0x180007b97  mov     rcx, rdi
0x180007b9a  call    ValidateBaseAlgHandle
0x180007b9f  test    rax, rax
0x180007ba2  jz      short loc_180007BF0
0x180007ba4  cmp     dword ptr [rax+8], 0
0x180007ba8  jl      loc_180007CDD
0x180007bae  mov     r10, [rax+18h]
0x180007bb2  mov     ecx, [rax+24h]
0x180007bb5  cmp     ecx, 1
0x180007bb8  jnz     short loc_180007C14
0x180007bba  mov     rax, [rax+48h]; jumptable 0000000180007D16 cases 2-8
0x180007bbe  mov     r9d, esi
0x180007bc1  mov     r8, rbp
0x180007bc4  mov     dword ptr [rsp+78h+var_58], r14d
0x180007bc9  mov     rdx, rbx
0x180007bcc  mov     rcx, r10
0x180007bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bd4  mov     ebx, eax
0x180007bd6  test    eax, eax
0x180007bd8  js      loc_180007D1C
0x180007bde  xor     ebx, ebx
0x180007be0  mov     eax, ebx
0x180007be2  add     rsp, 48h
0x180007be6  pop     r15
0x180007be8  pop     r14
0x180007bea  pop     rdi
0x180007beb  pop     rsi
0x180007bec  pop     rbp
0x180007bed  pop     rbx
0x180007bee  retn
0x180007bf0  movzx   eax, dil
0x180007bf4  and     al, 0Fh
0x180007bf6  cmp     al, 1
0x180007bf8  jz      short loc_180007C68
0x180007bfa  mov     rcx, rdi
0x180007bfd  call    ValidateBaseObjectHandle
0x180007c02  mov     r10, rax
0x180007c05  test    rax, rax
0x180007c08  jz      short loc_180007C68
0x180007c0a  mov     rax, [rax+8]
0x180007c0e  mov     r10, [r10+10h]
0x180007c12  jmp     short loc_180007BB2
0x180007c14  add     ecx, 0FFFFFFFEh; switch 7 cases
0x180007c17  cmp     ecx, 6
0x180007c1a  jbe     loc_180007D05
0x180007c20  mov     ebx, 0C0000008h; jumptable 0000000180007D16 default case
0x180007c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c2c  cmp     rcx, r15
0x180007c2f  jz      short loc_180007BE0
0x180007c31  test    byte ptr [rcx+1Ch], 1
0x180007c35  jz      short loc_180007BE0
0x180007c37  mov     [rsp+78h+var_48], 0CCDh
0x180007c3f  mov     rcx, [rcx+10h]
0x180007c43  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007c4a  mov     [rsp+78h+var_50], rax
0x180007c4f  lea     r9, aStatus; "Status"
0x180007c56  mov     dword ptr [rsp+78h+var_58], 0C0000008h
0x180007c5e  call    WPP_SF_sDsd
0x180007c63  jmp     loc_180007BE0
0x180007c68  mov     ebx, 0C0000008h
0x180007c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c74  cmp     rcx, r15
0x180007c77  jz      loc_180007BE0
0x180007c7d  test    byte ptr [rcx+1Ch], 1
0x180007c81  jz      loc_180007BE0
0x180007c87  mov     [rsp+78h+var_48], 0CA5h
0x180007c8f  jmp     short loc_180007C3F
0x180007c91  mov     rcx, [rcx+10h]
0x180007c95  mov     r9, rdi
0x180007c98  mov     [rsp+78h+var_40], r14d
0x180007c9d  mov     [rsp+78h+var_48], esi
0x180007ca1  mov     [rsp+78h+var_50], rbp
0x180007ca6  mov     [rsp+78h+var_58], rbx
0x180007cab  call    WPP_SF_qSqdD
0x180007cb0  jmp     loc_180007B8E
0x180007cb5  mov     r9d, 0C8Bh
0x180007cbb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007cc2  lea     rdx, aStatus; "Status"
0x180007cc9  mov     ecx, 0C000000Dh
0x180007cce  mov     ebx, 0C000000Dh
0x180007cd3  call    DebugTraceError
0x180007cd8  jmp     loc_180007BE0
0x180007cdd  mov     r9d, 0C98h
0x180007ce3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007cea  lea     rdx, aStatus; "Status"
0x180007cf1  mov     ecx, 0C0000022h
0x180007cf6  mov     ebx, 0C0000022h
0x180007cfb  call    DebugTraceError
0x180007d00  jmp     loc_180007BE0
0x180007d05  lea     rdx, __ImageBase
0x180007d0c  mov     ecx, ds:(jpt_180007D16 - 180000000h)[rdx+rcx*4]
0x180007d13  add     rcx, rdx
0x180007d16  jmp     rcx; switch jump
0x180007d1c  mov     r9d, 0CD9h
0x180007d22  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007d29  lea     rdx, aStatus; "Status"
0x180007d30  mov     ecx, eax
0x180007d32  call    DebugTraceError
0x180007d37  jmp     loc_180007BE0
```
