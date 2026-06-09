# CRYPT_XML_TRANSFORM_C14_WRITE_CALLBACK

- ea: `0x1800088d0`
- end: `0x180008b01`
- name: `CRYPT_XML_TRANSFORM_C14_WRITE_CALLBACK`
- size: `561`
- prototype: `__int64 __fastcall(__int64, char *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x1800088d0`
- `0x180014ce0`
- `0x18001860d`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800088f6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000896c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800089a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800088f6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000896c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800089a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008952`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008952`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000893a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000893a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a8a`

## string_xrefs

- `0x1800089d4`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x180008a1d`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x180008a5d`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x180008a9d`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`

## pseudocode

```c
__int64 __fastcall CRYPT_XML_TRANSFORM_C14_WRITE_CALLBACK(__int64 a1, char *a2, unsigned int a3)
{
  unsigned int v6; // edx
  unsigned int v7; // ecx
  unsigned int v8; // eax
  __int64 v9; // rdi
  signed int LastError; // eax
  const char *v12; // r8
  char v13; // dl
  const char *v14; // r9
  bool v15; // zf
  int v16; // r9d
  char v17; // dl
  const char *v18; // r9
  bool v19; // zf
  signed int v20; // edx
  signed int v21; // eax
  unsigned int v22; // r10d
  signed int v23; // r10d
  signed int v24; // eax
  unsigned int v25; // r10d
  const char *v26; // rax
  int v27; // r10d

  while ( 1 )
  {
    if ( WaitForSingleObject(*(HANDLE *)(a1 + 48), 0xFFFFFFFF) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *(_DWORD *)(a1 + 96) = LastError;
      v12 = "";
      while ( 1 )
      {
        v17 = *(v12 - 1);
        v18 = v12--;
        v19 = v17 == 92;
        if ( v17 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp" )
        {
          v19 = v17 == 92;
          break;
        }
      }
      if ( v19 )
        v12 = v18;
      v16 = 178;
LABEL_30:
      v20 = LastError;
LABEL_34:
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v20, v12, v16);
      return *(unsigned int *)(a1 + 96);
    }
    v6 = *(_DWORD *)(a1 + 84);
    v7 = *(_DWORD *)(a1 + 80) - v6;
    if ( v7 )
    {
      v8 = a3;
      if ( v7 <= a3 )
        v8 = *(_DWORD *)(a1 + 80) - v6;
      v9 = v8;
      memcpy_0((void *)(*(_QWORD *)(a1 + 88) + v6), a2, v8);
      *(_DWORD *)(a1 + 84) += v9;
      a2 += v9;
      a3 -= v9;
    }
    if ( !SetEvent(*(HANDLE *)(a1 + 56)) )
      break;
    if ( !ReleaseMutex(*(HANDLE *)(a1 + 48)) )
    {
      v21 = GetLastError();
      v22 = v21;
      if ( v21 > 0 )
        v22 = (unsigned __int16)v21 | 0x80070000;
      *(_DWORD *)(a1 + 96) = v22;
      v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp");
      v20 = v23;
      v16 = 221;
      goto LABEL_34;
    }
    if ( !WaitForSingleObject(*(HANDLE *)(a1 + 72), 0) || !a3 )
      return *(unsigned int *)(a1 + 96);
    if ( WaitForSingleObject(*(HANDLE *)(a1 + 64), 0xFFFFFFFF) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *(_DWORD *)(a1 + 96) = LastError;
      v12 = "";
      while ( 1 )
      {
        v13 = *(v12 - 1);
        v14 = v12--;
        v15 = v13 == 92;
        if ( v13 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp" )
        {
          v15 = v13 == 92;
          break;
        }
      }
      if ( v15 )
        v12 = v14;
      v16 = 254;
      goto LABEL_30;
    }
  }
  v24 = GetLastError();
  v25 = v24;
  if ( v24 > 0 )
    v25 = (unsigned __int16)v24 | 0x80070000;
  *(_DWORD *)(a1 + 96) = v25;
  v26 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp");
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v27, v26, 213);
  return *(unsigned int *)(a1 + 96);
}

```

## disassembly

```asm
0x1800088d0  mov     [rsp+arg_8], rbx
0x1800088d5  mov     [rsp+arg_10], rbp
0x1800088da  push    rsi
0x1800088db  sub     rsp, 20h
0x1800088df  mov     esi, r8d
0x1800088e2  mov     [rsp+28h+arg_0], rdi
0x1800088e7  mov     rbp, rdx
0x1800088ea  mov     rbx, rcx
0x1800088ed  mov     rcx, [rbx+30h]; hHandle
0x1800088f1  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800088f6  call    cs:__imp_WaitForSingleObject
0x1800088fd  nop     dword ptr [rax+rax+00h]
0x180008902  test    eax, eax
0x180008904  jnz     loc_1800089FF
0x18000890a  mov     edx, [rbx+54h]
0x18000890d  mov     ecx, [rbx+50h]
0x180008910  sub     ecx, edx
0x180008912  jz      short loc_180008936
0x180008914  cmp     ecx, esi
0x180008916  mov     eax, esi
0x180008918  cmovbe  eax, ecx
0x18000891b  mov     ecx, edx
0x18000891d  add     rcx, [rbx+58h]; void *
0x180008921  mov     rdx, rbp; Src
0x180008924  mov     r8d, eax; Size
0x180008927  mov     edi, eax
0x180008929  call    memcpy_0
0x18000892e  add     [rbx+54h], edi
0x180008931  add     rbp, rdi
0x180008934  sub     esi, edi
0x180008936  mov     rcx, [rbx+38h]; hEvent
0x18000893a  call    cs:__imp_SetEvent
0x180008941  nop     dword ptr [rax+rax+00h]
0x180008946  test    eax, eax
0x180008948  jz      loc_180008A8A
0x18000894e  mov     rcx, [rbx+30h]; hMutex
0x180008952  call    cs:__imp_ReleaseMutex
0x180008959  nop     dword ptr [rax+rax+00h]
0x18000895e  test    eax, eax
0x180008960  jz      loc_180008A4A
0x180008966  mov     rcx, [rbx+48h]; hHandle
0x18000896a  xor     edx, edx; dwMilliseconds
0x18000896c  call    cs:__imp_WaitForSingleObject
0x180008973  nop     dword ptr [rax+rax+00h]
0x180008978  test    eax, eax
0x18000897a  jz      short loc_180008980
0x18000897c  test    esi, esi
0x18000897e  jnz     short loc_180008999
0x180008980  mov     eax, [rbx+60h]
0x180008983  mov     rdi, [rsp+28h+arg_0]
0x180008988  mov     rbx, [rsp+28h+arg_8]
0x18000898d  mov     rbp, [rsp+28h+arg_10]
0x180008992  add     rsp, 20h
0x180008996  pop     rsi
0x180008997  retn
0x180008999  mov     rcx, [rbx+40h]; hHandle
0x18000899d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800089a2  call    cs:__imp_WaitForSingleObject
0x1800089a9  nop     dword ptr [rax+rax+00h]
0x1800089ae  test    eax, eax
0x1800089b0  jz      loc_1800088ED
0x1800089b6  call    cs:__imp_GetLastError
0x1800089bd  nop     dword ptr [rax+rax+00h]
0x1800089c2  test    eax, eax
0x1800089c4  jg      loc_180008ACA
0x1800089ca  mov     [rbx+60h], eax
0x1800089cd  lea     r8, aOnecoreDsSecur_13+2Eh; ""
0x1800089d4  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800089db  movzx   edx, byte ptr [r8-1]
0x1800089e0  mov     r9, r8
0x1800089e3  dec     r8
0x1800089e6  cmp     dl, 5Ch ; '\'
0x1800089e9  jz      short loc_1800089F3
0x1800089eb  cmp     r8, rcx
0x1800089ee  ja      short loc_1800089DB
0x1800089f0  cmp     dl, 5Ch ; '\'
0x1800089f3  cmovz   r8, r9
0x1800089f7  mov     r9d, 0FEh
0x1800089fd  jmp     short loc_180008A46
0x1800089ff  call    cs:__imp_GetLastError
0x180008a06  nop     dword ptr [rax+rax+00h]
0x180008a0b  test    eax, eax
0x180008a0d  jg      loc_180008AF4
0x180008a13  mov     [rbx+60h], eax
0x180008a16  lea     r8, aOnecoreDsSecur_13+2Eh; ""
0x180008a1d  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008a24  movzx   edx, byte ptr [r8-1]
0x180008a29  mov     r9, r8
0x180008a2c  dec     r8
0x180008a2f  cmp     dl, 5Ch ; '\'
0x180008a32  jz      short loc_180008A3C
0x180008a34  cmp     r8, rcx
0x180008a37  ja      short loc_180008A24
0x180008a39  cmp     dl, 5Ch ; '\'
0x180008a3c  cmovz   r8, r9
0x180008a40  mov     r9d, 0B2h
0x180008a46  mov     edx, eax
0x180008a48  jmp     short loc_180008A79
0x180008a4a  call    cs:__imp_GetLastError
0x180008a51  nop     dword ptr [rax+rax+00h]
0x180008a56  mov     r10d, eax
0x180008a59  test    eax, eax
0x180008a5b  jg      short loc_180008AD7
0x180008a5d  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008a64  mov     [rbx+60h], r10d
0x180008a68  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180008a6d  mov     r8, rax
0x180008a70  mov     edx, r10d
0x180008a73  mov     r9d, 0DDh
0x180008a79  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008a80  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180008a85  jmp     loc_180008980
0x180008a8a  call    cs:__imp_GetLastError
0x180008a91  nop     dword ptr [rax+rax+00h]
0x180008a96  mov     r10d, eax
0x180008a99  test    eax, eax
0x180008a9b  jg      short loc_180008AE7
0x180008a9d  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008aa4  mov     [rbx+60h], r10d
0x180008aa8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180008aad  mov     r8, rax
0x180008ab0  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008ab7  mov     edx, r10d
0x180008aba  mov     r9d, 0D5h
0x180008ac0  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180008ac5  jmp     loc_180008980
0x180008aca  movzx   eax, ax
0x180008acd  or      eax, 80070000h
0x180008ad2  jmp     loc_1800089CA
0x180008ad7  movzx   r10d, ax
0x180008adb  or      r10d, 80070000h
0x180008ae2  jmp     loc_180008A5D
0x180008ae7  movzx   r10d, ax
0x180008aeb  or      r10d, 80070000h
0x180008af2  jmp     short loc_180008A9D
0x180008af4  movzx   eax, ax
0x180008af7  or      eax, 80070000h
0x180008afc  jmp     loc_180008A13
```
