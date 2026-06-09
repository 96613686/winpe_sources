# CTsRdpCertSignature::GetHandleToMsgStore(uchar const *,ulong)

- ea: `0x18007dc28`
- end: `0x18007dd75`
- name: `?GetHandleToMsgStore@CTsRdpCertSignature@@AEAAPEAXPEBEK@Z`
- size: `333`
- prototype: `void *(CTsRdpCertSignature *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18007f830`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x18007dc28`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x18007dd57`
- `CRYPT32!CertOpenStore` at `0x18007dd57`
- `CRYPT32!CryptMsgUpdate` at `0x18007dcd5`
- `CRYPT32!CryptMsgUpdate` at `0x18007dcd5`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18007dc51`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18007dc51`
- `CRYPT32!CryptMsgClose` at `0x18007dd63`
- `CRYPT32!CryptMsgClose` at `0x18007dd63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dc7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dcbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dcfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dd3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dc7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dcbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dcfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dd3b`

## pseudocode

```c
HCERTSTORE __fastcall CTsRdpCertSignature::GetHandleToMsgStore(
        CTsRdpCertSignature *this,
        const unsigned __int8 *a2,
        DWORD a3)
{
  HCERTSTORE v3; // rsi
  HCRYPTMSG v6; // rax
  void *v7; // rdi
  signed int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  signed int LastError; // eax
  unsigned int v12; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v3 = 0;
  v6 = CryptMsgOpenToDecode(0x10001u, 4u, 0, 0, 0, 0);
  v7 = v6;
  if ( v6 )
  {
    if ( CryptMsgUpdate(v6, a2, a3, 1) )
    {
      v3 = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, v7);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          CurrentThreadActivityIdPrefix,
          v12);
      }
      GetLastError();
    }
    CryptMsgClose(v7);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = GetLastError();
      v9 = v8;
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids, v10, v9);
    }
    GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x18007dc28  push    rbx
0x18007dc2a  push    rbp
0x18007dc2b  push    rsi
0x18007dc2c  push    rdi
0x18007dc2d  sub     rsp, 38h
0x18007dc31  xor     esi, esi
0x18007dc33  mov     ebx, r8d
0x18007dc36  mov     rbp, rdx
0x18007dc39  mov     [rsp+58h+pStreamInfo], rsi; pStreamInfo
0x18007dc3e  xor     r9d, r9d; hCryptProv
0x18007dc41  mov     [rsp+58h+pRecipientInfo], rsi; pRecipientInfo
0x18007dc46  xor     r8d, r8d; dwMsgType
0x18007dc49  mov     ecx, 10001h; dwMsgEncodingType
0x18007dc4e  lea     edx, [rsi+4]; dwFlags
0x18007dc51  call    cs:__imp_CryptMsgOpenToDecode
0x18007dc57  mov     rdi, rax
0x18007dc5a  test    rax, rax
0x18007dc5d  jnz     short loc_18007DCC6
0x18007dc5f  mov     rax, cs:WPP_GLOBAL_Control
0x18007dc66  lea     rcx, WPP_GLOBAL_Control
0x18007dc6d  cmp     rax, rcx
0x18007dc70  jz      short loc_18007DCBB
0x18007dc72  test    byte ptr [rax+1Ch], 8
0x18007dc76  jz      short loc_18007DCBB
0x18007dc78  cmp     byte ptr [rax+19h], 2
0x18007dc7c  jb      short loc_18007DCBB
0x18007dc7e  call    cs:__imp_GetLastError
0x18007dc84  mov     ebx, eax
0x18007dc86  test    eax, eax
0x18007dc88  jle     short loc_18007DC93
0x18007dc8a  movzx   ebx, ax
0x18007dc8d  or      ebx, 80070000h
0x18007dc93  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007dc98  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dc9f  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x18007dca6  mov     edx, 3Eh ; '>'
0x18007dcab  mov     dword ptr [rsp+58h+pRecipientInfo], ebx
0x18007dcaf  mov     r9d, eax
0x18007dcb2  mov     rcx, [rcx+10h]
0x18007dcb6  call    WPP_SF_Dd
0x18007dcbb  call    cs:__imp_GetLastError
0x18007dcc1  jmp     loc_18007DD69
0x18007dcc6  mov     r9d, 1; fFinal
0x18007dccc  mov     r8d, ebx; cbData
0x18007dccf  mov     rdx, rbp; pbData
0x18007dcd2  mov     rcx, rdi; hCryptMsg
0x18007dcd5  call    cs:__imp_CryptMsgUpdate
0x18007dcdb  test    eax, eax
0x18007dcdd  jnz     short loc_18007DD43
0x18007dcdf  mov     rax, cs:WPP_GLOBAL_Control
0x18007dce6  lea     rcx, WPP_GLOBAL_Control
0x18007dced  cmp     rax, rcx
0x18007dcf0  jz      short loc_18007DD3B
0x18007dcf2  test    byte ptr [rax+1Ch], 8
0x18007dcf6  jz      short loc_18007DD3B
0x18007dcf8  cmp     byte ptr [rax+19h], 2
0x18007dcfc  jb      short loc_18007DD3B
0x18007dcfe  call    cs:__imp_GetLastError
0x18007dd04  mov     ebx, eax
0x18007dd06  test    eax, eax
0x18007dd08  jle     short loc_18007DD13
0x18007dd0a  movzx   ebx, ax
0x18007dd0d  or      ebx, 80070000h
0x18007dd13  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007dd18  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dd1f  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x18007dd26  mov     edx, 3Fh ; '?'
0x18007dd2b  mov     dword ptr [rsp+58h+pRecipientInfo], ebx
0x18007dd2f  mov     r9d, eax
0x18007dd32  mov     rcx, [rcx+10h]
0x18007dd36  call    WPP_SF_Dd
0x18007dd3b  call    cs:__imp_GetLastError
0x18007dd41  jmp     short loc_18007DD60
0x18007dd43  xor     r9d, r9d; dwFlags
0x18007dd46  mov     [rsp+58h+pRecipientInfo], rdi; pvPara
0x18007dd4b  xor     r8d, r8d; hCryptProv
0x18007dd4e  mov     edx, 10001h; dwEncodingType
0x18007dd53  lea     ecx, [r9+1]; lpszStoreProvider
0x18007dd57  call    cs:__imp_CertOpenStore
0x18007dd5d  mov     rsi, rax
0x18007dd60  mov     rcx, rdi; hCryptMsg
0x18007dd63  call    cs:__imp_CryptMsgClose
0x18007dd69  mov     rax, rsi
0x18007dd6c  add     rsp, 38h
0x18007dd70  pop     rdi
0x18007dd71  pop     rsi
0x18007dd72  pop     rbp
0x18007dd73  pop     rbx
0x18007dd74  retn
```
