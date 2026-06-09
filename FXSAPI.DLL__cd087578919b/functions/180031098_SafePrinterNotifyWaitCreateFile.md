# SafePrinterNotifyWaitCreateFile

- ea: `0x180031098`
- end: `0x1800312bd`
- name: `SafePrinterNotifyWaitCreateFile`
- size: `549`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, LPCWSTR lpFileName, __int64, __int64, HANDLE phPrinter)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a82c`
- `0x18001ad28`
- `0x18001ba58`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180021530`
- `0x1800305d4`
- `0x1800308e0`
- `0x180031098`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800312a1`
- `KERNEL32!SetLastError` at `0x1800312a1`
- `KERNEL32!GetLastError` at `0x180031111`
- `KERNEL32!GetLastError` at `0x180031189`
- `KERNEL32!GetLastError` at `0x180031111`
- `KERNEL32!GetLastError` at `0x180031189`
- `WINSPOOL!OpenPrinterW` at `0x180031179`
- `WINSPOOL!OpenPrinterW` at `0x180031179`
- `WINSPOOL!ClosePrinter` at `0x18003126a`
- `WINSPOOL!ClosePrinter` at `0x18003126a`

## pseudocode

```c
__int64 __fastcall SafePrinterNotifyWaitCreateFile(
        LPWSTR pPrinterName,
        LPCWSTR lpFileName,
        __int64 a3,
        __int64 a4,
        HANDLE phPrinter)
{
  DWORD LastError; // ebx
  __int64 File; // rsi
  _QWORD *v9; // rcx
  char v10; // al
  int v11; // edi

  LastError = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  }
  File = InternalSafeCreateFile(lpFileName, 0x80000000, 1u, 3u, 128);
  if ( File == -1 )
  {
    LastError = GetLastError();
    if ( LastError == 32 )
    {
      phPrinter = 0;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
        v9 = WPP_GLOBAL_Control;
      }
      if ( !pPrinterName )
      {
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 2u )
          WPP_SF_(v9[2], 80, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
        goto LABEL_37;
      }
      if ( !OpenPrinterW(pPrinterName, &phPrinter, 0) )
      {
        v10 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
            (_DWORD)pPrinterName,
            v10);
        }
LABEL_37:
        LastError = 32;
        goto LABEL_38;
      }
      v11 = 0;
      while ( 1 )
      {
        LastError = WaitForPrinterNotificationForCompletion(phPrinter);
        if ( LastError != 258 )
          break;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 258);
        }
        if ( (unsigned int)++v11 >= 3 )
          goto LABEL_31;
      }
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, LastError);
        }
        LastError = 32;
      }
LABEL_31:
      if ( phPrinter )
        ClosePrinter(phPrinter);
    }
  }
LABEL_38:
  SetLastError(LastError);
  return File;
}

```

## disassembly

```asm
0x180031098  push    rbx
0x18003109a  push    rsi
0x18003109b  push    rdi
0x18003109c  push    r12
0x18003109e  push    r14
0x1800310a0  sub     rsp, 40h
0x1800310a4  mov     rsi, rdx
0x1800310a7  mov     rdi, rcx
0x1800310aa  xor     ebx, ebx
0x1800310ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800310b3  lea     r14, WPP_GLOBAL_Control
0x1800310ba  lea     r12, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x1800310c1  cmp     rcx, r14
0x1800310c4  jz      short loc_1800310E1
0x1800310c6  test    byte ptr [rcx+1Ch], 2
0x1800310ca  jz      short loc_1800310E1
0x1800310cc  cmp     byte ptr [rcx+19h], 5
0x1800310d0  jb      short loc_1800310E1
0x1800310d2  mov     rcx, [rcx+10h]
0x1800310d6  lea     edx, [rbx+4Bh]
0x1800310d9  mov     r8, r12
0x1800310dc  call    WPP_SF_
0x1800310e1  mov     [rsp+68h+var_40], 80h; int
0x1800310e9  mov     edx, 80000000h; dwDesiredAccess
0x1800310ee  mov     r8d, 1; dwShareMode
0x1800310f4  mov     [rsp+68h+var_48], 3; DWORD
0x1800310fc  mov     rcx, rsi; lpFileName
0x1800310ff  call    InternalSafeCreateFile
0x180031104  mov     rsi, rax
0x180031107  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003110b  jnz     loc_18003129F
0x180031111  call    cs:__imp_GetLastError
0x180031118  nop     dword ptr [rax+rax+00h]
0x18003111d  mov     ebx, eax
0x18003111f  cmp     eax, 20h ; ' '
0x180031122  jnz     loc_18003129F
0x180031128  mov     [rsp+68h+phPrinter], 0
0x180031134  mov     rcx, cs:WPP_GLOBAL_Control
0x18003113b  cmp     rcx, r14
0x18003113e  jz      short loc_180031162
0x180031140  test    byte ptr [rcx+1Ch], 2
0x180031144  jz      short loc_180031162
0x180031146  cmp     byte ptr [rcx+19h], 3
0x18003114a  jb      short loc_180031162
0x18003114c  mov     rcx, [rcx+10h]
0x180031150  lea     edx, [rsi+4Dh]
0x180031153  mov     r8, r12
0x180031156  call    WPP_SF_
0x18003115b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031162  test    rdi, rdi
0x180031165  jz      loc_180031278
0x18003116b  xor     r8d, r8d; pDefault
0x18003116e  lea     rdx, [rsp+68h+phPrinter]; phPrinter
0x180031176  mov     rcx, rdi; pPrinterName
0x180031179  call    cs:__imp_OpenPrinterW
0x180031180  nop     dword ptr [rax+rax+00h]
0x180031185  test    eax, eax
0x180031187  jnz     short loc_1800311D6
0x180031189  call    cs:__imp_GetLastError
0x180031190  nop     dword ptr [rax+rax+00h]
0x180031195  mov     rcx, cs:WPP_GLOBAL_Control
0x18003119c  cmp     rcx, r14
0x18003119f  jz      loc_18003129A
0x1800311a5  test    byte ptr [rcx+1Ch], 2
0x1800311a9  jz      loc_18003129A
0x1800311af  cmp     byte ptr [rcx+19h], 2
0x1800311b3  jb      loc_18003129A
0x1800311b9  mov     rcx, [rcx+10h]
0x1800311bd  mov     edx, 4Dh ; 'M'
0x1800311c2  mov     r9, rdi
0x1800311c5  mov     [rsp+68h+var_48], eax
0x1800311c9  mov     r8, r12
0x1800311cc  call    WPP_SF_Sd
0x1800311d1  jmp     loc_18003129A
0x1800311d6  xor     edi, edi
0x1800311d8  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x1800311e0  or      edx, 0FFFFFFFFh
0x1800311e3  call    WaitForPrinterNotificationForCompletion
0x1800311e8  mov     ebx, eax
0x1800311ea  mov     eax, 102h
0x1800311ef  cmp     ebx, eax
0x1800311f1  jnz     short loc_180031228
0x1800311f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311fa  cmp     rcx, r14
0x1800311fd  jz      short loc_18003121F
0x1800311ff  test    byte ptr [rcx+1Ch], 2
0x180031203  jz      short loc_18003121F
0x180031205  cmp     byte ptr [rcx+19h], 3
0x180031209  jb      short loc_18003121F
0x18003120b  mov     rcx, [rcx+10h]
0x18003120f  mov     edx, 4Eh ; 'N'
0x180031214  mov     r9d, eax
0x180031217  mov     r8, r12
0x18003121a  call    WPP_SF_d
0x18003121f  inc     edi
0x180031221  cmp     edi, 3
0x180031224  jb      short loc_1800311D8
0x180031226  jmp     short loc_18003125D
0x180031228  test    ebx, ebx
0x18003122a  jz      short loc_18003125D
0x18003122c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031233  cmp     rcx, r14
0x180031236  jz      short loc_180031258
0x180031238  test    byte ptr [rcx+1Ch], 2
0x18003123c  jz      short loc_180031258
0x18003123e  cmp     byte ptr [rcx+19h], 2
0x180031242  jb      short loc_180031258
0x180031244  mov     rcx, [rcx+10h]
0x180031248  mov     edx, 4Fh ; 'O'
0x18003124d  mov     r9d, ebx
0x180031250  mov     r8, r12
0x180031253  call    WPP_SF_d
0x180031258  mov     ebx, 20h ; ' '
0x18003125d  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x180031265  test    rcx, rcx
0x180031268  jz      short loc_18003129F
0x18003126a  call    cs:__imp_ClosePrinter
0x180031271  nop     dword ptr [rax+rax+00h]
0x180031276  jmp     short loc_18003129F
0x180031278  cmp     rcx, r14
0x18003127b  jz      short loc_18003129A
0x18003127d  test    byte ptr [rcx+1Ch], 2
0x180031281  jz      short loc_18003129A
0x180031283  cmp     byte ptr [rcx+19h], 2
0x180031287  jb      short loc_18003129A
0x180031289  mov     rcx, [rcx+10h]
0x18003128d  mov     edx, 50h ; 'P'
0x180031292  mov     r8, r12
0x180031295  call    WPP_SF_
0x18003129a  mov     ebx, 20h ; ' '
0x18003129f  mov     ecx, ebx; dwErrCode
0x1800312a1  call    cs:__imp_SetLastError
0x1800312a8  nop     dword ptr [rax+rax+00h]
0x1800312ad  mov     rax, rsi
0x1800312b0  add     rsp, 40h
0x1800312b4  pop     r14
0x1800312b6  pop     r12
0x1800312b8  pop     rdi
0x1800312b9  pop     rsi
0x1800312ba  pop     rbx
0x1800312bb  retn
```
