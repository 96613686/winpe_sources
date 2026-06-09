# GetFaxPrinterInfo

- ea: `0x18002fbc8`
- end: `0x18002fe13`
- name: `GetFaxPrinterInfo`
- size: `587`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18002ffb8`
- `0x18003015c`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180021530`
- `0x18002bab8`
- `0x18002bb58`
- `0x18002fbc8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002fd99`
- `KERNEL32!SetLastError` at `0x18002fd99`
- `KERNEL32!GetLastError` at `0x18002fc3b`
- `KERNEL32!GetLastError` at `0x18002fc6d`
- `KERNEL32!GetLastError` at `0x18002fcc4`
- `KERNEL32!GetLastError` at `0x18002fd53`
- `KERNEL32!GetLastError` at `0x18002fdd7`
- `KERNEL32!GetLastError` at `0x18002fc3b`
- `KERNEL32!GetLastError` at `0x18002fc6d`
- `KERNEL32!GetLastError` at `0x18002fcc4`
- `KERNEL32!GetLastError` at `0x18002fd53`
- `KERNEL32!GetLastError` at `0x18002fdd7`
- `WINSPOOL!GetPrinterW` at `0x18002fcb4`
- `WINSPOOL!GetPrinterW` at `0x18002fd43`
- `WINSPOOL!GetPrinterW` at `0x18002fcb4`
- `WINSPOOL!GetPrinterW` at `0x18002fd43`
- `WINSPOOL!OpenPrinterW` at `0x18002fc2b`
- `WINSPOOL!OpenPrinterW` at `0x18002fc2b`
- `WINSPOOL!ClosePrinter` at `0x18002fdaf`
- `WINSPOOL!ClosePrinter` at `0x18002fdaf`

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

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v5);
    }
  }
  else
  {
    v3 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
0x18002fbc8  mov     [rsp+arg_0], rbx
0x18002fbcd  push    rbp
0x18002fbce  push    rsi
0x18002fbcf  push    rdi
0x18002fbd0  push    r14
0x18002fbd2  push    r15
0x18002fbd4  sub     rsp, 30h
0x18002fbd8  mov     rsi, rcx
0x18002fbdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbe2  lea     r14, WPP_GLOBAL_Control
0x18002fbe9  lea     r15, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18002fbf0  mov     ebp, 2
0x18002fbf5  cmp     rcx, r14
0x18002fbf8  jz      short loc_18002FC15
0x18002fbfa  test    [rcx+1Ch], bpl
0x18002fbfe  jz      short loc_18002FC15
0x18002fc00  cmp     byte ptr [rcx+19h], 5
0x18002fc04  jb      short loc_18002FC15
0x18002fc06  mov     rcx, [rcx+10h]
0x18002fc0a  lea     edx, [rbp+0Bh]
0x18002fc0d  mov     r8, r15
0x18002fc10  call    WPP_SF_
0x18002fc15  xor     edi, edi
0x18002fc17  lea     rdx, [rsp+58h+phPrinter]; phPrinter
0x18002fc1c  xor     r8d, r8d; pDefault
0x18002fc1f  mov     [rsp+58h+cbBuf], edi
0x18002fc23  mov     rcx, rsi; pPrinterName
0x18002fc26  mov     [rsp+58h+phPrinter], rdi
0x18002fc2b  call    cs:__imp_OpenPrinterW
0x18002fc32  nop     dword ptr [rax+rax+00h]
0x18002fc37  test    eax, eax
0x18002fc39  jnz     short loc_18002FC9B
0x18002fc3b  call    cs:__imp_GetLastError
0x18002fc42  nop     dword ptr [rax+rax+00h]
0x18002fc47  mov     ebx, eax
0x18002fc49  mov     rax, cs:WPP_GLOBAL_Control
0x18002fc50  cmp     rax, r14
0x18002fc53  jz      loc_18002FD97
0x18002fc59  test    [rax+1Ch], bpl
0x18002fc5d  jz      loc_18002FD97
0x18002fc63  cmp     [rax+19h], bpl
0x18002fc67  jb      loc_18002FD97
0x18002fc6d  call    cs:__imp_GetLastError
0x18002fc74  nop     dword ptr [rax+rax+00h]
0x18002fc79  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc80  lea     edx, [rdi+0Eh]
0x18002fc83  mov     r9, rsi
0x18002fc86  mov     dword ptr [rsp+58h+pcbNeeded], eax
0x18002fc8a  mov     r8, r15
0x18002fc8d  mov     rcx, [rcx+10h]
0x18002fc91  call    WPP_SF_Sd
0x18002fc96  jmp     loc_18002FD97
0x18002fc9b  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x18002fca0  lea     rax, [rsp+58h+cbBuf]
0x18002fca5  xor     r9d, r9d; cbBuf
0x18002fca8  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x18002fcad  xor     r8d, r8d; pPrinter
0x18002fcb0  mov     edx, ebp; Level
0x18002fcb2  xor     ebx, ebx
0x18002fcb4  call    cs:__imp_GetPrinterW
0x18002fcbb  nop     dword ptr [rax+rax+00h]
0x18002fcc0  test    eax, eax
0x18002fcc2  jnz     short loc_18002FD14
0x18002fcc4  call    cs:__imp_GetLastError
0x18002fccb  nop     dword ptr [rax+rax+00h]
0x18002fcd0  mov     ebx, eax
0x18002fcd2  cmp     eax, 7Ah ; 'z'
0x18002fcd5  jz      short loc_18002FD14
0x18002fcd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fcde  cmp     rcx, r14
0x18002fce1  jz      loc_18002FD97
0x18002fce7  test    [rcx+1Ch], bpl
0x18002fceb  jz      loc_18002FD97
0x18002fcf1  cmp     [rcx+19h], bpl
0x18002fcf5  jb      loc_18002FD97
0x18002fcfb  mov     rcx, [rcx+10h]
0x18002fcff  mov     edx, 0Fh
0x18002fd04  mov     r9d, eax
0x18002fd07  mov     r8, r15
0x18002fd0a  call    WPP_SF_d
0x18002fd0f  jmp     loc_18002FD97
0x18002fd14  mov     ecx, [rsp+58h+cbBuf]; dwBytes
0x18002fd18  call    pMemAlloc
0x18002fd1d  mov     rdi, rax
0x18002fd20  test    rax, rax
0x18002fd23  jnz     short loc_18002FD2A
0x18002fd25  lea     ebx, [rax+8]
0x18002fd28  jmp     short loc_18002FD97
0x18002fd2a  mov     r9d, [rsp+58h+cbBuf]; cbBuf
0x18002fd2f  lea     rax, [rsp+58h+cbBuf]
0x18002fd34  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x18002fd39  mov     r8, rdi; pPrinter
0x18002fd3c  mov     edx, ebp; Level
0x18002fd3e  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x18002fd43  call    cs:__imp_GetPrinterW
0x18002fd4a  nop     dword ptr [rax+rax+00h]
0x18002fd4f  test    eax, eax
0x18002fd51  jnz     short loc_18002FD97
0x18002fd53  call    cs:__imp_GetLastError
0x18002fd5a  nop     dword ptr [rax+rax+00h]
0x18002fd5f  mov     ebx, eax
0x18002fd61  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd68  cmp     rcx, r14
0x18002fd6b  jz      short loc_18002FD8D
0x18002fd6d  test    [rcx+1Ch], bpl
0x18002fd71  jz      short loc_18002FD8D
0x18002fd73  cmp     [rcx+19h], bpl
0x18002fd77  jb      short loc_18002FD8D
0x18002fd79  mov     rcx, [rcx+10h]
0x18002fd7d  mov     edx, 10h
0x18002fd82  mov     r9d, eax
0x18002fd85  mov     r8, r15
0x18002fd88  call    WPP_SF_d
0x18002fd8d  mov     rcx, rdi; lpMem
0x18002fd90  call    pMemFree
0x18002fd95  xor     edi, edi
0x18002fd97  mov     ecx, ebx; dwErrCode
0x18002fd99  call    cs:__imp_SetLastError
0x18002fda0  nop     dword ptr [rax+rax+00h]
0x18002fda5  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x18002fdaa  test    rcx, rcx
0x18002fdad  jz      short loc_18002FDFE
0x18002fdaf  call    cs:__imp_ClosePrinter
0x18002fdb6  nop     dword ptr [rax+rax+00h]
0x18002fdbb  test    eax, eax
0x18002fdbd  jnz     short loc_18002FDFE
0x18002fdbf  mov     rax, cs:WPP_GLOBAL_Control
0x18002fdc6  cmp     rax, r14
0x18002fdc9  jz      short loc_18002FDFE
0x18002fdcb  test    [rax+1Ch], bpl
0x18002fdcf  jz      short loc_18002FDFE
0x18002fdd1  cmp     [rax+19h], bpl
0x18002fdd5  jb      short loc_18002FDFE
0x18002fdd7  call    cs:__imp_GetLastError
0x18002fdde  nop     dword ptr [rax+rax+00h]
0x18002fde3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdea  mov     edx, 11h
0x18002fdef  mov     r9d, eax
0x18002fdf2  mov     r8, r15
0x18002fdf5  mov     rcx, [rcx+10h]
0x18002fdf9  call    WPP_SF_d
0x18002fdfe  mov     rbx, [rsp+58h+arg_0]
0x18002fe03  mov     rax, rdi
0x18002fe06  add     rsp, 30h
0x18002fe0a  pop     r15
0x18002fe0c  pop     r14
0x18002fe0e  pop     rdi
0x18002fe0f  pop     rsi
0x18002fe10  pop     rbp
0x18002fe11  retn
```
