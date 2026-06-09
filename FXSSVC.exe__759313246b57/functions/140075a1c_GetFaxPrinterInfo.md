# GetFaxPrinterInfo

- ea: `0x140075a1c`
- end: `0x140075c67`
- name: `GetFaxPrinterInfo`
- size: `587`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140075c70`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x1400698ec`
- `0x14006998c`
- `0x140075a1c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140075a8f`
- `KERNEL32!GetLastError` at `0x140075ac1`
- `KERNEL32!GetLastError` at `0x140075b18`
- `KERNEL32!GetLastError` at `0x140075ba7`
- `KERNEL32!GetLastError` at `0x140075c2b`
- `KERNEL32!GetLastError` at `0x140075a8f`
- `KERNEL32!GetLastError` at `0x140075ac1`
- `KERNEL32!GetLastError` at `0x140075b18`
- `KERNEL32!GetLastError` at `0x140075ba7`
- `KERNEL32!GetLastError` at `0x140075c2b`
- `KERNEL32!SetLastError` at `0x140075bed`
- `KERNEL32!SetLastError` at `0x140075bed`
- `WINSPOOL!OpenPrinterW` at `0x140075a7f`
- `WINSPOOL!OpenPrinterW` at `0x140075a7f`
- `WINSPOOL!GetPrinterW` at `0x140075b08`
- `WINSPOOL!GetPrinterW` at `0x140075b97`
- `WINSPOOL!GetPrinterW` at `0x140075b08`
- `WINSPOOL!GetPrinterW` at `0x140075b97`
- `WINSPOOL!ClosePrinter` at `0x140075c03`
- `WINSPOOL!ClosePrinter` at `0x140075c03`

## pseudocode

```c
void *__fastcall GetFaxPrinterInfo(LPWSTR pPrinterName)
{
  void *v2; // rdi
  DWORD v3; // ebx
  char v4; // al
  DWORD v5; // eax
  DWORD LastError; // eax
  DWORD v7; // eax
  DWORD cbBuf; // [rsp+68h] [rbp+10h] BYREF
  HANDLE phPrinter; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
  }
  v2 = 0;
  cbBuf = 0;
  phPrinter = 0;
  if ( OpenPrinterW(pPrinterName, &phPrinter, 0) )
  {
    v3 = 0;
    if ( GetPrinterW(phPrinter, 2u, 0, 0, &cbBuf) || (v5 = GetLastError(), v3 = v5, v5 == 122) )
    {
      v2 = (void *)pMemAlloc(cbBuf);
      if ( v2 )
      {
        if ( !GetPrinterW(phPrinter, 2u, (LPBYTE)v2, cbBuf, &cbBuf) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids,
              LastError);
          }
          pMemFree(v2);
          v2 = 0;
        }
      }
      else
      {
        v3 = 8;
      }
    }
    else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v5);
    }
  }
  else
  {
    v3 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids,
        (_DWORD)pPrinterName,
        v4);
    }
  }
  SetLastError(v3);
  if ( phPrinter
    && !ClosePrinter(phPrinter)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v7);
  }
  return v2;
}

```

## disassembly

```asm
0x140075a1c  mov     [rsp+arg_0], rbx
0x140075a21  push    rbp
0x140075a22  push    rsi
0x140075a23  push    rdi
0x140075a24  push    r14
0x140075a26  push    r15
0x140075a28  sub     rsp, 30h
0x140075a2c  mov     rsi, rcx
0x140075a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140075a36  lea     r14, WPP_GLOBAL_Control
0x140075a3d  lea     r15, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x140075a44  mov     ebp, 2
0x140075a49  cmp     rcx, r14
0x140075a4c  jz      short loc_140075A69
0x140075a4e  test    [rcx+1Ch], bpl
0x140075a52  jz      short loc_140075A69
0x140075a54  cmp     byte ptr [rcx+19h], 5
0x140075a58  jb      short loc_140075A69
0x140075a5a  mov     rcx, [rcx+10h]
0x140075a5e  lea     edx, [rbp+0Bh]
0x140075a61  mov     r8, r15
0x140075a64  call    WPP_SF_
0x140075a69  xor     edi, edi
0x140075a6b  lea     rdx, [rsp+58h+phPrinter]; phPrinter
0x140075a70  xor     r8d, r8d; pDefault
0x140075a73  mov     [rsp+58h+cbBuf], edi
0x140075a77  mov     rcx, rsi; pPrinterName
0x140075a7a  mov     [rsp+58h+phPrinter], rdi
0x140075a7f  call    cs:__imp_OpenPrinterW
0x140075a86  nop     dword ptr [rax+rax+00h]
0x140075a8b  test    eax, eax
0x140075a8d  jnz     short loc_140075AEF
0x140075a8f  call    cs:__imp_GetLastError
0x140075a96  nop     dword ptr [rax+rax+00h]
0x140075a9b  mov     ebx, eax
0x140075a9d  mov     rax, cs:WPP_GLOBAL_Control
0x140075aa4  cmp     rax, r14
0x140075aa7  jz      loc_140075BEB
0x140075aad  test    [rax+1Ch], bpl
0x140075ab1  jz      loc_140075BEB
0x140075ab7  cmp     [rax+19h], bpl
0x140075abb  jb      loc_140075BEB
0x140075ac1  call    cs:__imp_GetLastError
0x140075ac8  nop     dword ptr [rax+rax+00h]
0x140075acd  mov     rcx, cs:WPP_GLOBAL_Control
0x140075ad4  lea     edx, [rdi+0Eh]
0x140075ad7  mov     r9, rsi
0x140075ada  mov     dword ptr [rsp+58h+pcbNeeded], eax
0x140075ade  mov     r8, r15
0x140075ae1  mov     rcx, [rcx+10h]
0x140075ae5  call    WPP_SF_Sd
0x140075aea  jmp     loc_140075BEB
0x140075aef  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x140075af4  lea     rax, [rsp+58h+cbBuf]
0x140075af9  xor     r9d, r9d; cbBuf
0x140075afc  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x140075b01  xor     r8d, r8d; pPrinter
0x140075b04  mov     edx, ebp; Level
0x140075b06  xor     ebx, ebx
0x140075b08  call    cs:__imp_GetPrinterW
0x140075b0f  nop     dword ptr [rax+rax+00h]
0x140075b14  test    eax, eax
0x140075b16  jnz     short loc_140075B68
0x140075b18  call    cs:__imp_GetLastError
0x140075b1f  nop     dword ptr [rax+rax+00h]
0x140075b24  mov     ebx, eax
0x140075b26  cmp     eax, 7Ah ; 'z'
0x140075b29  jz      short loc_140075B68
0x140075b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140075b32  cmp     rcx, r14
0x140075b35  jz      loc_140075BEB
0x140075b3b  test    [rcx+1Ch], bpl
0x140075b3f  jz      loc_140075BEB
0x140075b45  cmp     [rcx+19h], bpl
0x140075b49  jb      loc_140075BEB
0x140075b4f  mov     rcx, [rcx+10h]
0x140075b53  mov     edx, 0Fh
0x140075b58  mov     r9d, eax
0x140075b5b  mov     r8, r15
0x140075b5e  call    WPP_SF_d
0x140075b63  jmp     loc_140075BEB
0x140075b68  mov     ecx, [rsp+58h+cbBuf]; dwBytes
0x140075b6c  call    pMemAlloc
0x140075b71  mov     rdi, rax
0x140075b74  test    rax, rax
0x140075b77  jnz     short loc_140075B7E
0x140075b79  lea     ebx, [rax+8]
0x140075b7c  jmp     short loc_140075BEB
0x140075b7e  mov     r9d, [rsp+58h+cbBuf]; cbBuf
0x140075b83  lea     rax, [rsp+58h+cbBuf]
0x140075b88  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x140075b8d  mov     r8, rdi; pPrinter
0x140075b90  mov     edx, ebp; Level
0x140075b92  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x140075b97  call    cs:__imp_GetPrinterW
0x140075b9e  nop     dword ptr [rax+rax+00h]
0x140075ba3  test    eax, eax
0x140075ba5  jnz     short loc_140075BEB
0x140075ba7  call    cs:__imp_GetLastError
0x140075bae  nop     dword ptr [rax+rax+00h]
0x140075bb3  mov     ebx, eax
0x140075bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140075bbc  cmp     rcx, r14
0x140075bbf  jz      short loc_140075BE1
0x140075bc1  test    [rcx+1Ch], bpl
0x140075bc5  jz      short loc_140075BE1
0x140075bc7  cmp     [rcx+19h], bpl
0x140075bcb  jb      short loc_140075BE1
0x140075bcd  mov     rcx, [rcx+10h]
0x140075bd1  mov     edx, 10h
0x140075bd6  mov     r9d, eax
0x140075bd9  mov     r8, r15
0x140075bdc  call    WPP_SF_d
0x140075be1  mov     rcx, rdi; lpMem
0x140075be4  call    pMemFree
0x140075be9  xor     edi, edi
0x140075beb  mov     ecx, ebx; dwErrCode
0x140075bed  call    cs:__imp_SetLastError
0x140075bf4  nop     dword ptr [rax+rax+00h]
0x140075bf9  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x140075bfe  test    rcx, rcx
0x140075c01  jz      short loc_140075C52
0x140075c03  call    cs:__imp_ClosePrinter
0x140075c0a  nop     dword ptr [rax+rax+00h]
0x140075c0f  test    eax, eax
0x140075c11  jnz     short loc_140075C52
0x140075c13  mov     rax, cs:WPP_GLOBAL_Control
0x140075c1a  cmp     rax, r14
0x140075c1d  jz      short loc_140075C52
0x140075c1f  test    [rax+1Ch], bpl
0x140075c23  jz      short loc_140075C52
0x140075c25  cmp     [rax+19h], bpl
0x140075c29  jb      short loc_140075C52
0x140075c2b  call    cs:__imp_GetLastError
0x140075c32  nop     dword ptr [rax+rax+00h]
0x140075c37  mov     rcx, cs:WPP_GLOBAL_Control
0x140075c3e  mov     edx, 11h
0x140075c43  mov     r9d, eax
0x140075c46  mov     r8, r15
0x140075c49  mov     rcx, [rcx+10h]
0x140075c4d  call    WPP_SF_d
0x140075c52  mov     rbx, [rsp+58h+arg_0]
0x140075c57  mov     rax, rdi
0x140075c5a  add     rsp, 30h
0x140075c5e  pop     r15
0x140075c60  pop     r14
0x140075c62  pop     rdi
0x140075c63  pop     rsi
0x140075c64  pop     rbp
0x140075c65  retn
```
