# ComputeSha1Hash

- ea: `0x180025d40`
- end: `0x180026050`
- name: `ComputeSha1Hash`
- size: `784`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180034908`

## callees

- `0x180025d40`
- `0x1801167f0`
- `0x180116eac`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x180025d9b`
- `ADVAPI32!CryptAcquireContextW` at `0x180025d9b`
- `ADVAPI32!CryptCreateHash` at `0x180025dc1`
- `ADVAPI32!CryptCreateHash` at `0x180025dc1`
- `ADVAPI32!CryptHashData` at `0x180025ddc`
- `ADVAPI32!CryptHashData` at `0x180025ddc`
- `ADVAPI32!CryptDestroyHash` at `0x180026030`
- `ADVAPI32!CryptDestroyHash` at `0x180026030`
- `ADVAPI32!CryptGetHashParam` at `0x180025e03`
- `ADVAPI32!CryptGetHashParam` at `0x180025e30`
- `ADVAPI32!CryptGetHashParam` at `0x180025e03`
- `ADVAPI32!CryptGetHashParam` at `0x180025e30`
- `ADVAPI32!CryptReleaseContext` at `0x180026045`
- `ADVAPI32!CryptReleaseContext` at `0x180026045`
- `KERNEL32!GetLastError` at `0x180025e87`
- `KERNEL32!GetLastError` at `0x180025ebf`
- `KERNEL32!GetLastError` at `0x180025eff`
- `KERNEL32!GetLastError` at `0x180025f3c`
- `KERNEL32!GetLastError` at `0x180025f79`
- `KERNEL32!GetLastError` at `0x180025e87`
- `KERNEL32!GetLastError` at `0x180025ebf`
- `KERNEL32!GetLastError` at `0x180025eff`
- `KERNEL32!GetLastError` at `0x180025f3c`
- `KERNEL32!GetLastError` at `0x180025f79`

## pseudocode

```c
__int64 __fastcall ComputeSha1Hash(BYTE *pbData, DWORD dwDataLen, BYTE *a3)
{
  unsigned int v6; // ebx
  signed int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  signed int LastError; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  HCRYPTPROV phProv[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD pdwDataLen; // [rsp+60h] [rbp+20h] BYREF
  HCRYPTHASH phHash; // [rsp+78h] [rbp+38h] BYREF

  phProv[0] = 0;
  phHash = 0;
  pdwDataLen = 0;
  if ( !pbData || !a3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_585f96fa0b7d330982784073340d9920_Traceguids);
    v6 = -2147024809;
    goto LABEL_10;
  }
  if ( !CryptAcquireContextW(phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v10 = 11;
LABEL_42:
    WPP_SF_D(v9[2], v10, WPP_585f96fa0b7d330982784073340d9920_Traceguids, v6);
    goto LABEL_10;
  }
  if ( !CryptCreateHash(phProv[0], 0x8004u, 0, 0, &phHash) )
  {
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v10 = 12;
    goto LABEL_42;
  }
  if ( !CryptHashData(phHash, pbData, dwDataLen, 0) )
  {
    v12 = GetLastError();
    v6 = v12;
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v10 = 13;
    goto LABEL_42;
  }
  if ( !CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
  {
    v13 = GetLastError();
    v6 = v13;
    if ( v13 > 0 )
      v6 = (unsigned __int16)v13 | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v10 = 14;
    goto LABEL_42;
  }
  if ( pdwDataLen > 0x14 )
  {
    v6 = -2147418113;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_585f96fa0b7d330982784073340d9920_Traceguids);
  }
  else
  {
    if ( CryptGetHashParam(phHash, 2u, a3, &pdwDataLen, 0) )
    {
      v6 = 0;
      goto LABEL_10;
    }
    v14 = GetLastError();
    v6 = v14;
    if ( v14 > 0 )
      v6 = (unsigned __int16)v14 | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 16;
      goto LABEL_42;
    }
  }
LABEL_10:
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phProv[0] )
    CryptReleaseContext(phProv[0], 0);
  return v6;
}

```

## disassembly

```asm
0x180025d40  mov     [rsp-18h+arg_8], rbx
0x180025d45  push    rbp
0x180025d46  push    rsi
0x180025d47  push    rdi
0x180025d48  mov     rbp, rsp
0x180025d4b  sub     rsp, 40h
0x180025d4f  mov     [rbp+phProv], 0
0x180025d57  mov     rbx, r8
0x180025d5a  mov     [rbp+phHash], 0
0x180025d62  mov     esi, edx
0x180025d64  mov     [rbp+pdwDataLen], 0
0x180025d6b  mov     rdi, rcx
0x180025d6e  test    rcx, rcx
0x180025d71  jz      loc_180025E69
0x180025d77  test    rbx, rbx
0x180025d7a  jz      loc_180025E69
0x180025d80  mov     r9d, 1; dwProvType
0x180025d86  mov     [rsp+40h+dwFlags], 0F0000000h; dwFlags
0x180025d8e  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180025d95  xor     edx, edx; szContainer
0x180025d97  lea     rcx, [rbp+phProv]; phProv
0x180025d9b  call    cs:__imp_CryptAcquireContextW
0x180025da1  test    eax, eax
0x180025da3  jz      loc_180025EBF
0x180025da9  mov     rcx, [rbp+phProv]; hProv
0x180025dad  lea     rax, [rbp+phHash]
0x180025db1  xor     r9d, r9d; dwFlags
0x180025db4  mov     qword ptr [rsp+40h+dwFlags], rax; phHash
0x180025db9  xor     r8d, r8d; hKey
0x180025dbc  mov     edx, 8004h; Algid
0x180025dc1  call    cs:__imp_CryptCreateHash
0x180025dc7  test    eax, eax
0x180025dc9  jz      loc_180025E87
0x180025dcf  mov     rcx, [rbp+phHash]; hHash
0x180025dd3  xor     r9d, r9d; dwFlags
0x180025dd6  mov     r8d, esi; dwDataLen
0x180025dd9  mov     rdx, rdi; pbData
0x180025ddc  call    cs:__imp_CryptHashData
0x180025de2  test    eax, eax
0x180025de4  jz      loc_180025EFF
0x180025dea  mov     rcx, [rbp+phHash]; hHash
0x180025dee  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180025df2  xor     r8d, r8d; pbData
0x180025df5  mov     [rsp+40h+dwFlags], 0; dwFlags
0x180025dfd  lea     edi, [r8+2]
0x180025e01  mov     edx, edi; dwParam
0x180025e03  call    cs:__imp_CryptGetHashParam
0x180025e09  test    eax, eax
0x180025e0b  jz      loc_180025F3C
0x180025e11  cmp     [rbp+pdwDataLen], 14h
0x180025e15  ja      loc_180025FCC
0x180025e1b  mov     rcx, [rbp+phHash]; hHash
0x180025e1f  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180025e23  mov     r8, rbx; pbData
0x180025e26  mov     [rsp+40h+dwFlags], 0; dwFlags
0x180025e2e  mov     edx, edi; dwParam
0x180025e30  call    cs:__imp_CryptGetHashParam
0x180025e36  test    eax, eax
0x180025e38  jz      loc_180025F79
0x180025e3e  xor     ebx, ebx
0x180025e40  mov     rcx, [rbp+phHash]; hHash
0x180025e44  test    rcx, rcx
0x180025e47  jnz     loc_180026030
0x180025e4d  mov     rcx, [rbp+phProv]; hProv
0x180025e51  test    rcx, rcx
0x180025e54  jnz     loc_180026043
0x180025e5a  mov     eax, ebx
0x180025e5c  mov     rbx, [rsp+40h+arg_8]
0x180025e61  add     rsp, 40h
0x180025e65  pop     rdi
0x180025e66  pop     rsi
0x180025e67  pop     rbp
0x180025e68  retn
0x180025e69  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e70  lea     rax, WPP_GLOBAL_Control
0x180025e77  cmp     rcx, rax
0x180025e7a  jnz     loc_18002600C
0x180025e80  mov     ebx, 80070057h
0x180025e85  jmp     short loc_180025E40
0x180025e87  call    cs:__imp_GetLastError
0x180025e8d  mov     ebx, eax
0x180025e8f  test    eax, eax
0x180025e91  jle     short loc_180025E9C
0x180025e93  movzx   ebx, ax
0x180025e96  or      ebx, 80070000h
0x180025e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ea3  lea     rax, WPP_GLOBAL_Control
0x180025eaa  cmp     rcx, rax
0x180025ead  jz      short loc_180025E40
0x180025eaf  test    byte ptr [rcx+1Ch], 1
0x180025eb3  jz      short loc_180025E40
0x180025eb5  mov     edx, 0Ch
0x180025eba  jmp     loc_180025FB4
0x180025ebf  call    cs:__imp_GetLastError
0x180025ec5  mov     ebx, eax
0x180025ec7  test    eax, eax
0x180025ec9  jle     short loc_180025ED4
0x180025ecb  movzx   ebx, ax
0x180025ece  or      ebx, 80070000h
0x180025ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180025edb  lea     rax, WPP_GLOBAL_Control
0x180025ee2  cmp     rcx, rax
0x180025ee5  jz      loc_180025E40
0x180025eeb  test    byte ptr [rcx+1Ch], 1
0x180025eef  jz      loc_180025E40
0x180025ef5  mov     edx, 0Bh
0x180025efa  jmp     loc_180025FB4
0x180025eff  call    cs:__imp_GetLastError
0x180025f05  mov     ebx, eax
0x180025f07  test    eax, eax
0x180025f09  jle     short loc_180025F14
0x180025f0b  movzx   ebx, ax
0x180025f0e  or      ebx, 80070000h
0x180025f14  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f1b  lea     rax, WPP_GLOBAL_Control
0x180025f22  cmp     rcx, rax
0x180025f25  jz      loc_180025E40
0x180025f2b  test    byte ptr [rcx+1Ch], 1
0x180025f2f  jz      loc_180025E40
0x180025f35  mov     edx, 0Dh
0x180025f3a  jmp     short loc_180025FB4
0x180025f3c  call    cs:__imp_GetLastError
0x180025f42  mov     ebx, eax
0x180025f44  test    eax, eax
0x180025f46  jle     short loc_180025F51
0x180025f48  movzx   ebx, ax
0x180025f4b  or      ebx, 80070000h
0x180025f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f58  lea     rax, WPP_GLOBAL_Control
0x180025f5f  cmp     rcx, rax
0x180025f62  jz      loc_180025E40
0x180025f68  test    byte ptr [rcx+1Ch], 1
0x180025f6c  jz      loc_180025E40
0x180025f72  mov     edx, 0Eh
0x180025f77  jmp     short loc_180025FB4
0x180025f79  call    cs:__imp_GetLastError
0x180025f7f  mov     ebx, eax
0x180025f81  test    eax, eax
0x180025f83  jle     short loc_180025F8E
0x180025f85  movzx   ebx, ax
0x180025f88  or      ebx, 80070000h
0x180025f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f95  lea     rax, WPP_GLOBAL_Control
0x180025f9c  cmp     rcx, rax
0x180025f9f  jz      loc_180025E40
0x180025fa5  test    byte ptr [rcx+1Ch], 1
0x180025fa9  jz      loc_180025E40
0x180025faf  mov     edx, 10h
0x180025fb4  mov     rcx, [rcx+10h]
0x180025fb8  lea     r8, WPP_585f96fa0b7d330982784073340d9920_Traceguids
0x180025fbf  mov     r9d, ebx
0x180025fc2  call    WPP_SF_D
0x180025fc7  jmp     loc_180025E40
0x180025fcc  mov     ebx, 8000FFFFh
0x180025fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fd8  lea     rax, WPP_GLOBAL_Control
0x180025fdf  cmp     rcx, rax
0x180025fe2  jz      loc_180025E40
0x180025fe8  test    byte ptr [rcx+1Ch], 1
0x180025fec  jz      loc_180025E40
0x180025ff2  mov     rcx, [rcx+10h]
0x180025ff6  lea     r8, WPP_585f96fa0b7d330982784073340d9920_Traceguids
0x180025ffd  mov     edx, 0Fh
0x180026002  call    WPP_SF_
0x180026007  jmp     loc_180025E40
0x18002600c  test    byte ptr [rcx+1Ch], 1
0x180026010  jz      loc_180025E80
0x180026016  mov     rcx, [rcx+10h]
0x18002601a  lea     r8, WPP_585f96fa0b7d330982784073340d9920_Traceguids
0x180026021  mov     edx, 0Ah
0x180026026  call    WPP_SF_
0x18002602b  jmp     loc_180025E80
0x180026030  call    cs:__imp_CryptDestroyHash
0x180026036  mov     [rbp+phHash], 0
0x18002603e  jmp     loc_180025E4D
0x180026043  xor     edx, edx; dwFlags
0x180026045  call    cs:__imp_CryptReleaseContext
0x18002604b  jmp     loc_180025E5A
```
