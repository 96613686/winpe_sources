# EndDocEx

- ea: `0x18000faac`
- end: `0x18000fcb2`
- name: `EndDocEx`
- size: `518`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800066d0`
- `0x18000eb70`

## callees

- `0x180009f04`
- `0x180009f34`
- `0x180009fe8`
- `0x18000faac`
- `0x18000fcb8`

## import_xrefs

- `GDI32!EndDoc` at `0x18000fb3f`
- `GDI32!EndDoc` at `0x18000fb3f`
- `KERNEL32!GetLastError` at `0x18000fb4f`
- `KERNEL32!GetLastError` at `0x18000fbb7`
- `KERNEL32!GetLastError` at `0x18000fc6d`
- `KERNEL32!GetLastError` at `0x18000fb4f`
- `KERNEL32!GetLastError` at `0x18000fbb7`
- `KERNEL32!GetLastError` at `0x18000fc6d`
- `KERNEL32!SetLastError` at `0x18000fc96`
- `KERNEL32!SetLastError` at `0x18000fc96`
- `WINSPOOL!ClosePrinter` at `0x18000fc45`
- `WINSPOOL!ClosePrinter` at `0x18000fc45`
- `WINSPOOL!OpenPrinterW` at `0x18000fba7`
- `WINSPOOL!OpenPrinterW` at `0x18000fba7`

## pseudocode

```c
__int64 __fastcall EndDocEx(LPWSTR pPrinterName, __int64 a2, __int64 a3, HDC a4)
{
  _QWORD *v6; // rcx
  DWORD v7; // ebx
  DWORD LastError; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  HANDLE v11; // rcx
  int v12; // edi
  char v13; // al
  int v14; // edx
  int v15; // r8d
  DWORD v16; // eax
  HANDLE phPrinter; // [rsp+30h] [rbp-38h] BYREF

  phPrinter = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a4 )
  {
    v7 = 87;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_(v6[2], 71, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
    goto LABEL_39;
  }
  if ( EndDoc(a4) <= 0 )
  {
    LastError = GetLastError();
    v7 = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    v10 = 72;
LABEL_38:
    WPP_SF_d(v9[2], v10, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, LastError);
    goto LABEL_39;
  }
  v11 = phPrinter;
  v12 = 0;
  if ( pPrinterName )
  {
    if ( !OpenPrinterW(pPrinterName, &phPrinter, 0) )
    {
      v13 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sl(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, (_DWORD)pPrinterName, v13);
      }
      v7 = 0;
      goto LABEL_39;
    }
    v11 = phPrinter;
    v12 = 1;
  }
  v7 = 0;
  if ( v11 )
  {
    v16 = WaitForPrinterNotificationForCompletion(v11);
    v7 = v16;
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v16);
      }
      v7 = 0;
    }
    v11 = phPrinter;
  }
  if ( v12
    && !ClosePrinter(v11)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    LastError = GetLastError();
    v9 = WPP_GLOBAL_Control;
    v10 = 75;
    goto LABEL_38;
  }
LABEL_39:
  SetLastError(v7);
  return 1;
}

```

## disassembly

```asm
0x18000faac  push    rbx
0x18000faae  push    rbp
0x18000faaf  push    rdi
0x18000fab0  push    r14
0x18000fab2  sub     rsp, 48h
0x18000fab6  mov     rdi, r9
0x18000fab9  mov     [rsp+68h+phPrinter], 0
0x18000fac2  mov     rbx, rcx
0x18000fac5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000facc  lea     rbp, WPP_GLOBAL_Control
0x18000fad3  lea     r14, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18000fada  cmp     rcx, rbp
0x18000fadd  jz      short loc_18000FB03
0x18000fadf  test    byte ptr [rcx+1Ch], 2
0x18000fae3  jz      short loc_18000FB03
0x18000fae5  cmp     byte ptr [rcx+19h], 5
0x18000fae9  jb      short loc_18000FB03
0x18000faeb  mov     rcx, [rcx+10h]
0x18000faef  mov     edx, 46h ; 'F'
0x18000faf4  mov     r8, r14
0x18000faf7  call    WPP_SF_
0x18000fafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb03  test    rdi, rdi
0x18000fb06  jnz     short loc_18000FB3C
0x18000fb08  lea     ebx, [rdi+57h]
0x18000fb0b  cmp     rcx, rbp
0x18000fb0e  jz      loc_18000FC94
0x18000fb14  test    byte ptr [rcx+1Ch], 2
0x18000fb18  jz      loc_18000FC94
0x18000fb1e  cmp     byte ptr [rcx+19h], 2
0x18000fb22  jb      loc_18000FC94
0x18000fb28  mov     rcx, [rcx+10h]
0x18000fb2c  lea     edx, [rdi+47h]
0x18000fb2f  mov     r8, r14
0x18000fb32  call    WPP_SF_
0x18000fb37  jmp     loc_18000FC94
0x18000fb3c  mov     rcx, rdi; hdc
0x18000fb3f  call    cs:__imp_EndDoc
0x18000fb46  nop     dword ptr [rax+rax+00h]
0x18000fb4b  test    eax, eax
0x18000fb4d  jg      short loc_18000FB8B
0x18000fb4f  call    cs:__imp_GetLastError
0x18000fb56  nop     dword ptr [rax+rax+00h]
0x18000fb5b  mov     ebx, eax
0x18000fb5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb64  cmp     rcx, rbp
0x18000fb67  jz      loc_18000FC94
0x18000fb6d  test    byte ptr [rcx+1Ch], 2
0x18000fb71  jz      loc_18000FC94
0x18000fb77  cmp     byte ptr [rcx+19h], 2
0x18000fb7b  jb      loc_18000FC94
0x18000fb81  mov     edx, 48h ; 'H'
0x18000fb86  jmp     loc_18000FC85
0x18000fb8b  mov     rcx, [rsp+68h+phPrinter]
0x18000fb90  xor     edi, edi
0x18000fb92  test    rcx, rcx
0x18000fb95  jnz     short loc_18000FBFC
0x18000fb97  test    rbx, rbx
0x18000fb9a  jz      short loc_18000FBFC
0x18000fb9c  xor     r8d, r8d; pDefault
0x18000fb9f  lea     rdx, [rsp+68h+phPrinter]; phPrinter
0x18000fba4  mov     rcx, rbx; pPrinterName
0x18000fba7  call    cs:__imp_OpenPrinterW
0x18000fbae  nop     dword ptr [rax+rax+00h]
0x18000fbb3  test    eax, eax
0x18000fbb5  jnz     short loc_18000FBF2
0x18000fbb7  call    cs:__imp_GetLastError
0x18000fbbe  nop     dword ptr [rax+rax+00h]
0x18000fbc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbca  cmp     rcx, rbp
0x18000fbcd  jz      short loc_18000FBEB
0x18000fbcf  test    byte ptr [rcx+1Ch], 2
0x18000fbd3  jz      short loc_18000FBEB
0x18000fbd5  cmp     byte ptr [rcx+19h], 2
0x18000fbd9  jb      short loc_18000FBEB
0x18000fbdb  mov     rcx, [rcx+10h]
0x18000fbdf  mov     r9, rbx
0x18000fbe2  mov     [rsp+68h+var_48], eax
0x18000fbe6  call    WPP_SF_Sl
0x18000fbeb  xor     ebx, ebx
0x18000fbed  jmp     loc_18000FC94
0x18000fbf2  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x18000fbf7  mov     edi, 1
0x18000fbfc  xor     ebx, ebx
0x18000fbfe  test    rcx, rcx
0x18000fc01  jz      short loc_18000FC41
0x18000fc03  call    WaitForPrinterNotificationForCompletion
0x18000fc08  mov     ebx, eax
0x18000fc0a  test    eax, eax
0x18000fc0c  jz      short loc_18000FC3C
0x18000fc0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc15  cmp     rcx, rbp
0x18000fc18  jz      short loc_18000FC3A
0x18000fc1a  test    byte ptr [rcx+1Ch], 2
0x18000fc1e  jz      short loc_18000FC3A
0x18000fc20  cmp     byte ptr [rcx+19h], 3
0x18000fc24  jb      short loc_18000FC3A
0x18000fc26  mov     rcx, [rcx+10h]
0x18000fc2a  mov     edx, 4Ah ; 'J'
0x18000fc2f  mov     r9d, eax
0x18000fc32  mov     r8, r14
0x18000fc35  call    WPP_SF_d
0x18000fc3a  xor     ebx, ebx
0x18000fc3c  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x18000fc41  test    edi, edi
0x18000fc43  jz      short loc_18000FC94
0x18000fc45  call    cs:__imp_ClosePrinter
0x18000fc4c  nop     dword ptr [rax+rax+00h]
0x18000fc51  test    eax, eax
0x18000fc53  jnz     short loc_18000FC94
0x18000fc55  mov     rax, cs:WPP_GLOBAL_Control
0x18000fc5c  cmp     rax, rbp
0x18000fc5f  jz      short loc_18000FC94
0x18000fc61  test    byte ptr [rax+1Ch], 2
0x18000fc65  jz      short loc_18000FC94
0x18000fc67  cmp     byte ptr [rax+19h], 3
0x18000fc6b  jb      short loc_18000FC94
0x18000fc6d  call    cs:__imp_GetLastError
0x18000fc74  nop     dword ptr [rax+rax+00h]
0x18000fc79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc80  mov     edx, 4Bh ; 'K'
0x18000fc85  mov     rcx, [rcx+10h]
0x18000fc89  mov     r9d, eax
0x18000fc8c  mov     r8, r14
0x18000fc8f  call    WPP_SF_d
0x18000fc94  mov     ecx, ebx; dwErrCode
0x18000fc96  call    cs:__imp_SetLastError
0x18000fc9d  nop     dword ptr [rax+rax+00h]
0x18000fca2  mov     eax, 1
0x18000fca7  add     rsp, 48h
0x18000fcab  pop     r14
0x18000fcad  pop     rdi
0x18000fcae  pop     rbp
0x18000fcaf  pop     rbx
0x18000fcb0  retn
```
