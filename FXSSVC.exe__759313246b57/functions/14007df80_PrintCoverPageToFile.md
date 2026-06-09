# PrintCoverPageToFile

- ea: `0x14007df80`
- end: `0x14007e51a`
- name: `PrintCoverPageToFile`
- size: `1434`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, WCHAR *pwszDevice, __int16, __int16)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14002f530`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x1400698ec`
- `0x14006998c`
- `0x1400758d0`
- `0x14007de2c`
- `0x14007df80`
- `0x14007f5e0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14007e037`
- `KERNEL32!GetLastError` at `0x14007e0b8`
- `KERNEL32!GetLastError` at `0x14007e186`
- `KERNEL32!GetLastError` at `0x14007e1fd`
- `KERNEL32!GetLastError` at `0x14007e282`
- `KERNEL32!GetLastError` at `0x14007e2e7`
- `KERNEL32!GetLastError` at `0x14007e39d`
- `KERNEL32!GetLastError` at `0x14007e3ff`
- `KERNEL32!GetLastError` at `0x14007e46c`
- `KERNEL32!GetLastError` at `0x14007e4c5`
- `KERNEL32!GetLastError` at `0x14007e037`
- `KERNEL32!GetLastError` at `0x14007e0b8`
- `KERNEL32!GetLastError` at `0x14007e186`
- `KERNEL32!GetLastError` at `0x14007e1fd`
- `KERNEL32!GetLastError` at `0x14007e282`
- `KERNEL32!GetLastError` at `0x14007e2e7`
- `KERNEL32!GetLastError` at `0x14007e39d`
- `KERNEL32!GetLastError` at `0x14007e3ff`
- `KERNEL32!GetLastError` at `0x14007e46c`
- `KERNEL32!GetLastError` at `0x14007e4c5`
- `GDI32!StartPage` at `0x14007e2d7`
- `GDI32!StartPage` at `0x14007e2d7`
- `GDI32!CreateDCW` at `0x14007e1e9`
- `GDI32!CreateDCW` at `0x14007e1e9`
- `GDI32!DeleteDC` at `0x14007e440`
- `GDI32!DeleteDC` at `0x14007e440`
- `GDI32!StartDocW` at `0x14007e270`
- `GDI32!StartDocW` at `0x14007e270`
- `GDI32!EndPage` at `0x14007e38d`
- `GDI32!EndPage` at `0x14007e38d`
- `WINSPOOL!DocumentPropertiesW` at `0x14007e0a8`
- `WINSPOOL!DocumentPropertiesW` at `0x14007e175`
- `WINSPOOL!DocumentPropertiesW` at `0x14007e0a8`
- `WINSPOOL!DocumentPropertiesW` at `0x14007e175`
- `WINSPOOL!OpenPrinterW` at `0x14007e027`
- `WINSPOOL!OpenPrinterW` at `0x14007e027`
- `WINSPOOL!ClosePrinter` at `0x14007e499`
- `WINSPOOL!ClosePrinter` at `0x14007e499`

## pseudocode

```c
__int64 __fastcall PrintCoverPageToFile(__int64 a1, const WCHAR *a2, WCHAR *pwszDevice, __int16 a4, __int16 a5)
{
  DEVMODEW *v9; // r14
  DWORD LastError; // eax
  unsigned int v11; // edi
  CMapDeviceId *v12; // rcx
  int v13; // edx
  LONG v14; // eax
  DWORD v15; // eax
  CMapDeviceId *v16; // rcx
  __int64 v17; // rdx
  struct _devicemodeW *v18; // rax
  HDC DCW; // rbx
  int started; // esi
  DWORD v21; // eax
  CMapDeviceId *v22; // rcx
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  __int64 v26; // rbx
  DWORD v27; // eax
  __int64 v28; // rbx
  DWORD v29; // eax
  HANDLE phPrinter; // [rsp+30h] [rbp-A9h] BYREF
  DOCINFOW v32; // [rsp+38h] [rbp-A1h] BYREF
  _BYTE v33[128]; // [rsp+60h] [rbp-79h] BYREF

  memset_0(v33, 0, 0x74u);
  memset(&v32, 0, 36);
  v9 = 0;
  phPrinter = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids);
  }
  if ( !OpenPrinterW(pwszDevice, &phPrinter, 0) )
  {
    LastError = GetLastError();
    v11 = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 46;
LABEL_10:
      WPP_SF_Sd(
        *((_QWORD *)v12 + 2),
        v13,
        (unsigned int)&WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids,
        (_DWORD)pwszDevice,
        LastError);
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  v14 = DocumentPropertiesW(0, phPrinter, 0, 0, 0, 0);
  if ( v14 <= 0 )
  {
    v15 = GetLastError();
    v11 = v15;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v17 = 47;
    goto LABEL_16;
  }
  v18 = (struct _devicemodeW *)pMemAlloc(v14);
  v9 = v18;
  if ( !v18 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids);
    }
    v11 = 8;
    goto LABEL_67;
  }
  if ( DocumentPropertiesW(0, phPrinter, 0, v18, 0, 2u) != 1 )
  {
    v15 = GetLastError();
    v11 = v15;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v17 = 49;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v15);
    goto LABEL_67;
  }
  v9->dmOrientation = a4;
  if ( a5 )
    v9->dmYResolution = a5;
  DCW = CreateDCW(0, pwszDevice, 0, v9);
  if ( DCW )
  {
    v32.cbSize = 40;
    v32.lpszDocName = &Class;
    v32.lpszOutput = a2;
    v32.lpszDatatype = 0;
    v32.fwType = 0;
    started = StartDocW(DCW, &v32);
    if ( started > 0 )
    {
      if ( StartPage(DCW) > 0 )
      {
        v11 = PrintCoverPage(DCW);
        if ( v11
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_lSS(*((_QWORD *)WPP_GLOBAL_Control + 2), a1, (__int64)a2);
        }
        if ( EndPage(DCW) <= 0 )
        {
          v24 = GetLastError();
          v11 = v24;
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v24);
          }
        }
      }
      else
      {
        v23 = GetLastError();
        v11 = v23;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v23);
        }
      }
    }
    else
    {
      v21 = GetLastError();
      v11 = v21;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v21);
      }
      if ( !started )
        goto LABEL_62;
    }
    if ( (int)EndDocEx(v22, phPrinter, (unsigned int)started, DCW) <= 0 )
    {
      v25 = GetLastError();
      v11 = v25;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v25);
      }
    }
LABEL_62:
    if ( !DeleteDC(DCW)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v27 = GetLastError();
      WPP_SF_d(v26, 56, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v27);
    }
    goto LABEL_67;
  }
  LastError = GetLastError();
  v11 = LastError;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 50;
    goto LABEL_10;
  }
LABEL_67:
  if ( phPrinter
    && !ClosePrinter(phPrinter)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v28 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v29 = GetLastError();
    WPP_SF_d(v28, 57, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v29);
  }
  pMemFree(v9);
  return v11;
}

```

## disassembly

```asm
0x14007df80  mov     [rsp-8+arg_18], rbx
0x14007df85  push    rbp
0x14007df86  push    rsi
0x14007df87  push    rdi
0x14007df88  push    r12
0x14007df8a  push    r13
0x14007df8c  push    r14
0x14007df8e  push    r15
0x14007df90  lea     rbp, [rsp-17h]
0x14007df95  sub     rsp, 0F0h
0x14007df9c  mov     rax, cs:__security_cookie
0x14007dfa3  xor     rax, rsp
0x14007dfa6  mov     [rbp+47h+var_40], rax
0x14007dfaa  mov     rdi, [rbp+47h+arg_28]
0x14007dfae  mov     r15, rdx
0x14007dfb1  xor     edx, edx; Val
0x14007dfb3  mov     rsi, r8
0x14007dfb6  mov     r12, rcx
0x14007dfb9  movzx   ebx, r9w
0x14007dfbd  lea     rcx, [rbp+47h+var_C0]; void *
0x14007dfc1  lea     r8d, [rdx+74h]; Size
0x14007dfc5  call    memset_0
0x14007dfca  xor     eax, eax
0x14007dfcc  xorps   xmm0, xmm0
0x14007dfcf  movups  xmmword ptr [rsp+120h+var_E8.cbSize], xmm0
0x14007dfd4  mov     [rsp+120h+var_E8.fwType], eax
0x14007dfd8  xor     r14d, r14d
0x14007dfdb  movups  xmmword ptr [rsp+120h+var_E8.lpszOutput], xmm0
0x14007dfe0  mov     [rsp+120h+phPrinter], rax
0x14007dfe5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dfec  lea     rax, WPP_GLOBAL_Control
0x14007dff3  lea     r13d, [r14+2]
0x14007dff7  cmp     rcx, rax
0x14007dffa  jz      short loc_14007E01C
0x14007dffc  test    [rcx+1Ch], r13b
0x14007e000  jz      short loc_14007E01C
0x14007e002  cmp     byte ptr [rcx+19h], 5
0x14007e006  jb      short loc_14007E01C
0x14007e008  mov     rcx, [rcx+10h]
0x14007e00c  lea     edx, [r14+2Dh]
0x14007e010  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e017  call    WPP_SF_
0x14007e01c  xor     r8d, r8d; pDefault
0x14007e01f  lea     rdx, [rsp+120h+phPrinter]; phPrinter
0x14007e024  mov     rcx, rsi; pPrinterName
0x14007e027  call    cs:__imp_OpenPrinterW
0x14007e02e  nop     dword ptr [rax+rax+00h]
0x14007e033  test    eax, eax
0x14007e035  jnz     short loc_14007E091
0x14007e037  call    cs:__imp_GetLastError
0x14007e03e  nop     dword ptr [rax+rax+00h]
0x14007e043  mov     edi, eax
0x14007e045  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e04c  lea     r15, WPP_GLOBAL_Control
0x14007e053  cmp     rcx, r15
0x14007e056  jz      loc_14007E48F
0x14007e05c  test    [rcx+1Ch], r13b
0x14007e060  jz      loc_14007E48F
0x14007e066  cmp     [rcx+19h], r13b
0x14007e06a  jb      loc_14007E48F
0x14007e070  mov     edx, 2Eh ; '.'
0x14007e075  mov     rcx, [rcx+10h]
0x14007e079  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e080  mov     r9, rsi
0x14007e083  mov     dword ptr [rsp+120h+pDevModeInput], eax
0x14007e087  call    WPP_SF_Sd
0x14007e08c  jmp     loc_14007E48F
0x14007e091  mov     rdx, [rsp+120h+phPrinter]; hPrinter
0x14007e096  xor     r9d, r9d; pDevModeOutput
0x14007e099  mov     [rsp+120h+fMode], r14d; fMode
0x14007e09e  xor     r8d, r8d; pDeviceName
0x14007e0a1  xor     ecx, ecx; hWnd
0x14007e0a3  mov     [rsp+120h+pDevModeInput], r14; pDevModeInput
0x14007e0a8  call    cs:__imp_DocumentPropertiesW
0x14007e0af  nop     dword ptr [rax+rax+00h]
0x14007e0b4  test    eax, eax
0x14007e0b6  jg      short loc_14007E10E
0x14007e0b8  call    cs:__imp_GetLastError
0x14007e0bf  nop     dword ptr [rax+rax+00h]
0x14007e0c4  mov     edi, eax
0x14007e0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e0cd  lea     r15, WPP_GLOBAL_Control
0x14007e0d4  cmp     rcx, r15
0x14007e0d7  jz      loc_14007E48F
0x14007e0dd  test    [rcx+1Ch], r13b
0x14007e0e1  jz      loc_14007E48F
0x14007e0e7  cmp     [rcx+19h], r13b
0x14007e0eb  jb      loc_14007E48F
0x14007e0f1  mov     edx, 2Fh ; '/'
0x14007e0f6  mov     rcx, [rcx+10h]
0x14007e0fa  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e101  mov     r9d, eax
0x14007e104  call    WPP_SF_d
0x14007e109  jmp     loc_14007E48F
0x14007e10e  movsxd  rcx, eax; dwBytes
0x14007e111  call    pMemAlloc
0x14007e116  mov     r14, rax
0x14007e119  test    rax, rax
0x14007e11c  jnz     short loc_14007E15A
0x14007e11e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e125  lea     r15, WPP_GLOBAL_Control
0x14007e12c  cmp     rcx, r15
0x14007e12f  jz      short loc_14007E150
0x14007e131  test    [rcx+1Ch], r13b
0x14007e135  jz      short loc_14007E150
0x14007e137  cmp     [rcx+19h], r13b
0x14007e13b  jb      short loc_14007E150
0x14007e13d  mov     rcx, [rcx+10h]
0x14007e141  lea     edx, [rax+30h]
0x14007e144  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e14b  call    WPP_SF_
0x14007e150  mov     edi, 8
0x14007e155  jmp     loc_14007E48F
0x14007e15a  mov     rdx, [rsp+120h+phPrinter]; hPrinter
0x14007e15f  mov     r9, r14; pDevModeOutput
0x14007e162  mov     [rsp+120h+fMode], r13d; fMode
0x14007e167  xor     r8d, r8d; pDeviceName
0x14007e16a  xor     ecx, ecx; hWnd
0x14007e16c  mov     [rsp+120h+pDevModeInput], 0; pDevModeInput
0x14007e175  call    cs:__imp_DocumentPropertiesW
0x14007e17c  nop     dword ptr [rax+rax+00h]
0x14007e181  cmp     eax, 1
0x14007e184  jz      short loc_14007E1C9
0x14007e186  call    cs:__imp_GetLastError
0x14007e18d  nop     dword ptr [rax+rax+00h]
0x14007e192  mov     edi, eax
0x14007e194  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e19b  lea     r15, WPP_GLOBAL_Control
0x14007e1a2  cmp     rcx, r15
0x14007e1a5  jz      loc_14007E48F
0x14007e1ab  test    [rcx+1Ch], r13b
0x14007e1af  jz      loc_14007E48F
0x14007e1b5  cmp     [rcx+19h], r13b
0x14007e1b9  jb      loc_14007E48F
0x14007e1bf  mov     edx, 31h ; '1'
0x14007e1c4  jmp     loc_14007E0F6
0x14007e1c9  movzx   ecx, [rbp+47h+arg_20]
0x14007e1cd  xor     eax, eax
0x14007e1cf  mov     [r14+4Ch], bx
0x14007e1d4  cmp     ax, cx
0x14007e1d7  jz      short loc_14007E1DE
0x14007e1d9  mov     [r14+60h], cx
0x14007e1de  mov     r9, r14; pdm
0x14007e1e1  xor     r8d, r8d; pszPort
0x14007e1e4  mov     rdx, rsi; pwszDevice
0x14007e1e7  xor     ecx, ecx; pwszDriver
0x14007e1e9  call    cs:__imp_CreateDCW
0x14007e1f0  nop     dword ptr [rax+rax+00h]
0x14007e1f5  mov     rbx, rax
0x14007e1f8  test    rax, rax
0x14007e1fb  jnz     short loc_14007E23E
0x14007e1fd  call    cs:__imp_GetLastError
0x14007e204  nop     dword ptr [rax+rax+00h]
0x14007e209  mov     edi, eax
0x14007e20b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e212  lea     r15, WPP_GLOBAL_Control
0x14007e219  cmp     rcx, r15
0x14007e21c  jz      loc_14007E48F
0x14007e222  test    [rcx+1Ch], r13b
0x14007e226  jz      loc_14007E48F
0x14007e22c  cmp     [rcx+19h], r13b
0x14007e230  jb      loc_14007E48F
0x14007e236  lea     edx, [rbx+32h]
0x14007e239  jmp     loc_14007E075
0x14007e23e  lea     rax, Class
0x14007e245  mov     [rsp+120h+var_E8.cbSize], 28h ; '('
0x14007e24d  lea     rdx, [rsp+120h+var_E8]; lpdi
0x14007e252  mov     [rsp+120h+var_E8.lpszDocName], rax
0x14007e257  mov     rcx, rbx; hdc
0x14007e25a  mov     [rsp+120h+var_E8.lpszOutput], r15
0x14007e25f  mov     [rsp+120h+var_E8.lpszDatatype], 0
0x14007e268  mov     [rsp+120h+var_E8.fwType], 0
0x14007e270  call    cs:__imp_StartDocW
0x14007e277  nop     dword ptr [rax+rax+00h]
0x14007e27c  mov     esi, eax
0x14007e27e  test    eax, eax
0x14007e280  jg      short loc_14007E2D4
0x14007e282  call    cs:__imp_GetLastError
0x14007e289  nop     dword ptr [rax+rax+00h]
0x14007e28e  mov     edi, eax
0x14007e290  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e297  lea     r15, WPP_GLOBAL_Control
0x14007e29e  cmp     rcx, r15
0x14007e2a1  jz      short loc_14007E2C7
0x14007e2a3  test    [rcx+1Ch], r13b
0x14007e2a7  jz      short loc_14007E2C7
0x14007e2a9  cmp     [rcx+19h], r13b
0x14007e2ad  jb      short loc_14007E2C7
0x14007e2af  mov     rcx, [rcx+10h]
0x14007e2b3  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e2ba  mov     edx, 33h ; '3'
0x14007e2bf  mov     r9d, eax
0x14007e2c2  call    WPP_SF_d
0x14007e2c7  test    esi, esi
0x14007e2c9  jnz     loc_14007E3EB
0x14007e2cf  jmp     loc_14007E43D
0x14007e2d4  mov     rcx, rbx; hdc
0x14007e2d7  call    cs:__imp_StartPage
0x14007e2de  nop     dword ptr [rax+rax+00h]
0x14007e2e3  test    eax, eax
0x14007e2e5  jg      short loc_14007E33D
0x14007e2e7  call    cs:__imp_GetLastError
0x14007e2ee  nop     dword ptr [rax+rax+00h]
0x14007e2f3  mov     edi, eax
0x14007e2f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e2fc  lea     r15, WPP_GLOBAL_Control
0x14007e303  cmp     rcx, r15
0x14007e306  jz      loc_14007E3EB
0x14007e30c  test    [rcx+1Ch], r13b
0x14007e310  jz      loc_14007E3EB
0x14007e316  cmp     [rcx+19h], r13b
0x14007e31a  jb      loc_14007E3EB
0x14007e320  mov     rcx, [rcx+10h]
0x14007e324  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e32b  mov     edx, 34h ; '4'
0x14007e330  mov     r9d, eax
0x14007e333  call    WPP_SF_d
0x14007e338  jmp     loc_14007E3EB
0x14007e33d  lea     r9, [rbp+47h+var_C0]
0x14007e341  mov     r8, r12
0x14007e344  mov     rdx, rdi
0x14007e347  mov     rcx, rbx; hdc
0x14007e34a  call    PrintCoverPage
0x14007e34f  mov     edi, eax
0x14007e351  test    eax, eax
0x14007e353  jz      short loc_14007E38A
0x14007e355  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e35c  lea     rax, WPP_GLOBAL_Control
0x14007e363  cmp     rcx, rax
0x14007e366  jz      short loc_14007E38A
0x14007e368  test    [rcx+1Ch], r13b
0x14007e36c  jz      short loc_14007E38A
0x14007e36e  cmp     [rcx+19h], r13b
0x14007e372  jb      short loc_14007E38A
0x14007e374  mov     rcx, [rcx+10h]; LoggerHandle
0x14007e378  mov     r9d, edi
0x14007e37b  mov     qword ptr [rsp+120h+fMode], r15; __int64
0x14007e380  mov     [rsp+120h+pDevModeInput], r12; __int64
0x14007e385  call    WPP_SF_lSS
0x14007e38a  mov     rcx, rbx; hdc
0x14007e38d  call    cs:__imp_EndPage
0x14007e394  nop     dword ptr [rax+rax+00h]
0x14007e399  test    eax, eax
0x14007e39b  jg      short loc_14007E3E4
0x14007e39d  call    cs:__imp_GetLastError
0x14007e3a4  nop     dword ptr [rax+rax+00h]
0x14007e3a9  mov     edi, eax
0x14007e3ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e3b2  lea     r15, WPP_GLOBAL_Control
0x14007e3b9  cmp     rcx, r15
0x14007e3bc  jz      short loc_14007E3EB
0x14007e3be  test    [rcx+1Ch], r13b
0x14007e3c2  jz      short loc_14007E3EB
0x14007e3c4  cmp     [rcx+19h], r13b
0x14007e3c8  jb      short loc_14007E3EB
0x14007e3ca  mov     rcx, [rcx+10h]
0x14007e3ce  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e3d5  mov     edx, 36h ; '6'
0x14007e3da  mov     r9d, eax
0x14007e3dd  call    WPP_SF_d
0x14007e3e2  jmp     short loc_14007E3EB
0x14007e3e4  lea     r15, WPP_GLOBAL_Control
0x14007e3eb  mov     rdx, [rsp+120h+phPrinter]
0x14007e3f0  mov     r9, rbx
0x14007e3f3  mov     r8d, esi
0x14007e3f6  call    EndDocEx
0x14007e3fb  test    eax, eax
0x14007e3fd  jg      short loc_14007E43D
0x14007e3ff  call    cs:__imp_GetLastError
0x14007e406  nop     dword ptr [rax+rax+00h]
0x14007e40b  mov     edi, eax
0x14007e40d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e414  cmp     rcx, r15
0x14007e417  jz      short loc_14007E43D
0x14007e419  test    [rcx+1Ch], r13b
0x14007e41d  jz      short loc_14007E43D
0x14007e41f  cmp     [rcx+19h], r13b
0x14007e423  jb      short loc_14007E43D
0x14007e425  mov     rcx, [rcx+10h]
0x14007e429  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e430  mov     edx, 37h ; '7'
0x14007e435  mov     r9d, eax
0x14007e438  call    WPP_SF_d
0x14007e43d  mov     rcx, rbx; hdc
0x14007e440  call    cs:__imp_DeleteDC
0x14007e447  nop     dword ptr [rax+rax+00h]
0x14007e44c  test    eax, eax
0x14007e44e  jnz     short loc_14007E48F
0x14007e450  mov     rbx, cs:WPP_GLOBAL_Control
0x14007e457  cmp     rbx, r15
0x14007e45a  jz      short loc_14007E48F
0x14007e45c  test    [rbx+1Ch], r13b
0x14007e460  jz      short loc_14007E48F
0x14007e462  cmp     [rbx+19h], r13b
0x14007e466  jb      short loc_14007E48F
0x14007e468  mov     rbx, [rbx+10h]
0x14007e46c  call    cs:__imp_GetLastError
0x14007e473  nop     dword ptr [rax+rax+00h]
0x14007e478  mov     edx, 38h ; '8'
0x14007e47d  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
  ... truncated ...
```
