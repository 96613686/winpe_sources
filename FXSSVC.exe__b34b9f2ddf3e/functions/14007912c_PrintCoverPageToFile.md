# PrintCoverPageToFile

- ea: `0x14007912c`
- end: `0x140079653`
- name: `PrintCoverPageToFile`
- size: `1319`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, __int64@<rdx>, LPCWSTR pwszDevice@<r8>, __int16, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14002dee0`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x140065d14`
- `0x140065dbc`
- `0x14007116c`
- `0x140079000`
- `0x14007912c`
- `0x14007a5bc`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400791dd`
- `KERNEL32!GetLastError` at `0x140079252`
- `KERNEL32!GetLastError` at `0x140079314`
- `KERNEL32!GetLastError` at `0x14007937f`
- `KERNEL32!GetLastError` at `0x1400793f8`
- `KERNEL32!GetLastError` at `0x140079451`
- `KERNEL32!GetLastError` at `0x1400794fb`
- `KERNEL32!GetLastError` at `0x140079557`
- `KERNEL32!GetLastError` at `0x1400795b8`
- `KERNEL32!GetLastError` at `0x140079605`
- `KERNEL32!GetLastError` at `0x1400791dd`
- `KERNEL32!GetLastError` at `0x140079252`
- `KERNEL32!GetLastError` at `0x140079314`
- `KERNEL32!GetLastError` at `0x14007937f`
- `KERNEL32!GetLastError` at `0x1400793f8`
- `KERNEL32!GetLastError` at `0x140079451`
- `KERNEL32!GetLastError` at `0x1400794fb`
- `KERNEL32!GetLastError` at `0x140079557`
- `KERNEL32!GetLastError` at `0x1400795b8`
- `KERNEL32!GetLastError` at `0x140079605`
- `GDI32!StartPage` at `0x140079447`
- `GDI32!StartPage` at `0x140079447`
- `GDI32!CreateDCW` at `0x140079371`
- `GDI32!CreateDCW` at `0x140079371`
- `GDI32!DeleteDC` at `0x140079592`
- `GDI32!DeleteDC` at `0x140079592`
- `GDI32!StartDocW` at `0x1400793ec`
- `GDI32!StartDocW` at `0x1400793ec`
- `GDI32!EndPage` at `0x1400794f1`
- `GDI32!EndPage` at `0x1400794f1`
- `WINSPOOL!DocumentPropertiesW` at `0x140079248`
- `WINSPOOL!DocumentPropertiesW` at `0x140079309`
- `WINSPOOL!DocumentPropertiesW` at `0x140079248`
- `WINSPOOL!DocumentPropertiesW` at `0x140079309`
- `WINSPOOL!OpenPrinterW` at `0x1400791d3`
- `WINSPOOL!OpenPrinterW` at `0x1400791d3`
- `WINSPOOL!ClosePrinter` at `0x1400795df`
- `WINSPOOL!ClosePrinter` at `0x1400795df`

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
0x14007912c  mov     [rsp-8+arg_18], rbx
0x140079131  push    rbp
0x140079132  push    rsi
0x140079133  push    rdi
0x140079134  push    r12
0x140079136  push    r13
0x140079138  push    r14
0x14007913a  push    r15
0x14007913c  lea     rbp, [rsp-17h]
0x140079141  sub     rsp, 0F0h
0x140079148  mov     rax, cs:__security_cookie
0x14007914f  xor     rax, rsp
0x140079152  mov     [rbp+47h+var_40], rax
0x140079156  mov     rdi, [rbp+47h+arg_28]
0x14007915a  mov     r15, rdx
0x14007915d  xor     edx, edx; Val
0x14007915f  mov     rsi, r8
0x140079162  mov     r12, rcx
0x140079165  movzx   ebx, r9w
0x140079169  lea     rcx, [rbp+47h+var_C0]; void *
0x14007916d  lea     r8d, [rdx+74h]; Size
0x140079171  call    memset_0
0x140079176  xor     eax, eax
0x140079178  xorps   xmm0, xmm0
0x14007917b  movups  xmmword ptr [rsp+120h+var_E8.cbSize], xmm0
0x140079180  mov     [rsp+120h+var_E8.fwType], eax
0x140079184  xor     r14d, r14d
0x140079187  movups  xmmword ptr [rsp+120h+var_E8.lpszOutput], xmm0
0x14007918c  mov     [rsp+120h+phPrinter], rax
0x140079191  mov     rcx, cs:WPP_GLOBAL_Control
0x140079198  lea     rax, WPP_GLOBAL_Control
0x14007919f  lea     r13d, [r14+2]
0x1400791a3  cmp     rcx, rax
0x1400791a6  jz      short loc_1400791C8
0x1400791a8  test    [rcx+1Ch], r13b
0x1400791ac  jz      short loc_1400791C8
0x1400791ae  cmp     byte ptr [rcx+19h], 5
0x1400791b2  jb      short loc_1400791C8
0x1400791b4  mov     rcx, [rcx+10h]
0x1400791b8  lea     edx, [r14+2Dh]
0x1400791bc  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x1400791c3  call    WPP_SF_
0x1400791c8  xor     r8d, r8d; pDefault
0x1400791cb  lea     rdx, [rsp+120h+phPrinter]; phPrinter
0x1400791d0  mov     rcx, rsi; pPrinterName
0x1400791d3  call    cs:__imp_OpenPrinterW
0x1400791d9  test    eax, eax
0x1400791db  jnz     short loc_140079231
0x1400791dd  call    cs:__imp_GetLastError
0x1400791e3  mov     edi, eax
0x1400791e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400791ec  lea     r15, WPP_GLOBAL_Control
0x1400791f3  cmp     rcx, r15
0x1400791f6  jz      loc_1400795D5
0x1400791fc  test    [rcx+1Ch], r13b
0x140079200  jz      loc_1400795D5
0x140079206  cmp     [rcx+19h], r13b
0x14007920a  jb      loc_1400795D5
0x140079210  mov     edx, 2Eh ; '.'
0x140079215  mov     rcx, [rcx+10h]
0x140079219  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x140079220  mov     r9, rsi
0x140079223  mov     dword ptr [rsp+120h+pDevModeInput], eax
0x140079227  call    WPP_SF_Sd
0x14007922c  jmp     loc_1400795D5
0x140079231  mov     rdx, [rsp+120h+phPrinter]; hPrinter
0x140079236  xor     r9d, r9d; pDevModeOutput
0x140079239  mov     [rsp+120h+fMode], r14d; fMode
0x14007923e  xor     r8d, r8d; pDeviceName
0x140079241  xor     ecx, ecx; hWnd
0x140079243  mov     [rsp+120h+pDevModeInput], r14; pDevModeInput
0x140079248  call    cs:__imp_DocumentPropertiesW
0x14007924e  test    eax, eax
0x140079250  jg      short loc_1400792A2
0x140079252  call    cs:__imp_GetLastError
0x140079258  mov     edi, eax
0x14007925a  mov     rcx, cs:WPP_GLOBAL_Control
0x140079261  lea     r15, WPP_GLOBAL_Control
0x140079268  cmp     rcx, r15
0x14007926b  jz      loc_1400795D5
0x140079271  test    [rcx+1Ch], r13b
0x140079275  jz      loc_1400795D5
0x14007927b  cmp     [rcx+19h], r13b
0x14007927f  jb      loc_1400795D5
0x140079285  mov     edx, 2Fh ; '/'
0x14007928a  mov     rcx, [rcx+10h]
0x14007928e  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x140079295  mov     r9d, eax
0x140079298  call    WPP_SF_d
0x14007929d  jmp     loc_1400795D5
0x1400792a2  movsxd  rcx, eax; dwBytes
0x1400792a5  call    pMemAlloc
0x1400792aa  mov     r14, rax
0x1400792ad  test    rax, rax
0x1400792b0  jnz     short loc_1400792EE
0x1400792b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400792b9  lea     r15, WPP_GLOBAL_Control
0x1400792c0  cmp     rcx, r15
0x1400792c3  jz      short loc_1400792E4
0x1400792c5  test    [rcx+1Ch], r13b
0x1400792c9  jz      short loc_1400792E4
0x1400792cb  cmp     [rcx+19h], r13b
0x1400792cf  jb      short loc_1400792E4
0x1400792d1  mov     rcx, [rcx+10h]
0x1400792d5  lea     edx, [rax+30h]
0x1400792d8  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x1400792df  call    WPP_SF_
0x1400792e4  mov     edi, 8
0x1400792e9  jmp     loc_1400795D5
0x1400792ee  mov     rdx, [rsp+120h+phPrinter]; hPrinter
0x1400792f3  mov     r9, r14; pDevModeOutput
0x1400792f6  mov     [rsp+120h+fMode], r13d; fMode
0x1400792fb  xor     r8d, r8d; pDeviceName
0x1400792fe  xor     ecx, ecx; hWnd
0x140079300  mov     [rsp+120h+pDevModeInput], 0; pDevModeInput
0x140079309  call    cs:__imp_DocumentPropertiesW
0x14007930f  cmp     eax, 1
0x140079312  jz      short loc_140079351
0x140079314  call    cs:__imp_GetLastError
0x14007931a  mov     edi, eax
0x14007931c  mov     rcx, cs:WPP_GLOBAL_Control
0x140079323  lea     r15, WPP_GLOBAL_Control
0x14007932a  cmp     rcx, r15
0x14007932d  jz      loc_1400795D5
0x140079333  test    [rcx+1Ch], r13b
0x140079337  jz      loc_1400795D5
0x14007933d  cmp     [rcx+19h], r13b
0x140079341  jb      loc_1400795D5
0x140079347  mov     edx, 31h ; '1'
0x14007934c  jmp     loc_14007928A
0x140079351  movzx   ecx, [rbp+47h+arg_20]
0x140079355  xor     eax, eax
0x140079357  mov     [r14+4Ch], bx
0x14007935c  cmp     ax, cx
0x14007935f  jz      short loc_140079366
0x140079361  mov     [r14+60h], cx
0x140079366  mov     r9, r14; pdm
0x140079369  xor     r8d, r8d; pszPort
0x14007936c  mov     rdx, rsi; pwszDevice
0x14007936f  xor     ecx, ecx; pwszDriver
0x140079371  call    cs:__imp_CreateDCW
0x140079377  mov     rbx, rax
0x14007937a  test    rax, rax
0x14007937d  jnz     short loc_1400793BA
0x14007937f  call    cs:__imp_GetLastError
0x140079385  mov     edi, eax
0x140079387  mov     rcx, cs:WPP_GLOBAL_Control
0x14007938e  lea     r15, WPP_GLOBAL_Control
0x140079395  cmp     rcx, r15
0x140079398  jz      loc_1400795D5
0x14007939e  test    [rcx+1Ch], r13b
0x1400793a2  jz      loc_1400795D5
0x1400793a8  cmp     [rcx+19h], r13b
0x1400793ac  jb      loc_1400795D5
0x1400793b2  lea     edx, [rbx+32h]
0x1400793b5  jmp     loc_140079215
0x1400793ba  lea     rax, Class
0x1400793c1  mov     [rsp+120h+var_E8.cbSize], 28h ; '('
0x1400793c9  lea     rdx, [rsp+120h+var_E8]; lpdi
0x1400793ce  mov     [rsp+120h+var_E8.lpszDocName], rax
0x1400793d3  mov     rcx, rbx; hdc
0x1400793d6  mov     [rsp+120h+var_E8.lpszOutput], r15
0x1400793db  mov     [rsp+120h+var_E8.lpszDatatype], 0
0x1400793e4  mov     [rsp+120h+var_E8.fwType], 0
0x1400793ec  call    cs:__imp_StartDocW
0x1400793f2  mov     esi, eax
0x1400793f4  test    eax, eax
0x1400793f6  jg      short loc_140079444
0x1400793f8  call    cs:__imp_GetLastError
0x1400793fe  mov     edi, eax
0x140079400  mov     rcx, cs:WPP_GLOBAL_Control
0x140079407  lea     r15, WPP_GLOBAL_Control
0x14007940e  cmp     rcx, r15
0x140079411  jz      short loc_140079437
0x140079413  test    [rcx+1Ch], r13b
0x140079417  jz      short loc_140079437
0x140079419  cmp     [rcx+19h], r13b
0x14007941d  jb      short loc_140079437
0x14007941f  mov     rcx, [rcx+10h]
0x140079423  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007942a  mov     edx, 33h ; '3'
0x14007942f  mov     r9d, eax
0x140079432  call    WPP_SF_d
0x140079437  test    esi, esi
0x140079439  jnz     loc_140079543
0x14007943f  jmp     loc_14007958F
0x140079444  mov     rcx, rbx; hdc
0x140079447  call    cs:__imp_StartPage
0x14007944d  test    eax, eax
0x14007944f  jg      short loc_1400794A1
0x140079451  call    cs:__imp_GetLastError
0x140079457  mov     edi, eax
0x140079459  mov     rcx, cs:WPP_GLOBAL_Control
0x140079460  lea     r15, WPP_GLOBAL_Control
0x140079467  cmp     rcx, r15
0x14007946a  jz      loc_140079543
0x140079470  test    [rcx+1Ch], r13b
0x140079474  jz      loc_140079543
0x14007947a  cmp     [rcx+19h], r13b
0x14007947e  jb      loc_140079543
0x140079484  mov     rcx, [rcx+10h]
0x140079488  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007948f  mov     edx, 34h ; '4'
0x140079494  mov     r9d, eax
0x140079497  call    WPP_SF_d
0x14007949c  jmp     loc_140079543
0x1400794a1  lea     r9, [rbp+47h+var_C0]
0x1400794a5  mov     r8, r12
0x1400794a8  mov     rdx, rdi
0x1400794ab  mov     rcx, rbx; hdc
0x1400794ae  call    PrintCoverPage
0x1400794b3  mov     edi, eax
0x1400794b5  test    eax, eax
0x1400794b7  jz      short loc_1400794EE
0x1400794b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400794c0  lea     rax, WPP_GLOBAL_Control
0x1400794c7  cmp     rcx, rax
0x1400794ca  jz      short loc_1400794EE
0x1400794cc  test    [rcx+1Ch], r13b
0x1400794d0  jz      short loc_1400794EE
0x1400794d2  cmp     [rcx+19h], r13b
0x1400794d6  jb      short loc_1400794EE
0x1400794d8  mov     rcx, [rcx+10h]; LoggerHandle
0x1400794dc  mov     r9d, edi
0x1400794df  mov     qword ptr [rsp+120h+fMode], r15; __int64
0x1400794e4  mov     [rsp+120h+pDevModeInput], r12; __int64
0x1400794e9  call    WPP_SF_lSS
0x1400794ee  mov     rcx, rbx; hdc
0x1400794f1  call    cs:__imp_EndPage
0x1400794f7  test    eax, eax
0x1400794f9  jg      short loc_14007953C
0x1400794fb  call    cs:__imp_GetLastError
0x140079501  mov     edi, eax
0x140079503  mov     rcx, cs:WPP_GLOBAL_Control
0x14007950a  lea     r15, WPP_GLOBAL_Control
0x140079511  cmp     rcx, r15
0x140079514  jz      short loc_140079543
0x140079516  test    [rcx+1Ch], r13b
0x14007951a  jz      short loc_140079543
0x14007951c  cmp     [rcx+19h], r13b
0x140079520  jb      short loc_140079543
0x140079522  mov     rcx, [rcx+10h]
0x140079526  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007952d  mov     edx, 36h ; '6'
0x140079532  mov     r9d, eax
0x140079535  call    WPP_SF_d
0x14007953a  jmp     short loc_140079543
0x14007953c  lea     r15, WPP_GLOBAL_Control
0x140079543  mov     rdx, [rsp+120h+phPrinter]
0x140079548  mov     r9, rbx
0x14007954b  mov     r8d, esi
0x14007954e  call    EndDocEx
0x140079553  test    eax, eax
0x140079555  jg      short loc_14007958F
0x140079557  call    cs:__imp_GetLastError
0x14007955d  mov     edi, eax
0x14007955f  mov     rcx, cs:WPP_GLOBAL_Control
0x140079566  cmp     rcx, r15
0x140079569  jz      short loc_14007958F
0x14007956b  test    [rcx+1Ch], r13b
0x14007956f  jz      short loc_14007958F
0x140079571  cmp     [rcx+19h], r13b
0x140079575  jb      short loc_14007958F
0x140079577  mov     rcx, [rcx+10h]
0x14007957b  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x140079582  mov     edx, 37h ; '7'
0x140079587  mov     r9d, eax
0x14007958a  call    WPP_SF_d
0x14007958f  mov     rcx, rbx; hdc
0x140079592  call    cs:__imp_DeleteDC
0x140079598  test    eax, eax
0x14007959a  jnz     short loc_1400795D5
0x14007959c  mov     rbx, cs:WPP_GLOBAL_Control
0x1400795a3  cmp     rbx, r15
0x1400795a6  jz      short loc_1400795D5
0x1400795a8  test    [rbx+1Ch], r13b
0x1400795ac  jz      short loc_1400795D5
0x1400795ae  cmp     [rbx+19h], r13b
0x1400795b2  jb      short loc_1400795D5
0x1400795b4  mov     rbx, [rbx+10h]
0x1400795b8  call    cs:__imp_GetLastError
0x1400795be  mov     edx, 38h ; '8'
0x1400795c3  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x1400795ca  mov     r9d, eax
0x1400795cd  mov     rcx, rbx
0x1400795d0  call    WPP_SF_d
0x1400795d5  mov     rcx, [rsp+120h+phPrinter]; hPrinter
0x1400795da  test    rcx, rcx
0x1400795dd  jz      short loc_140079622
0x1400795df  call    cs:__imp_ClosePrinter
0x1400795e5  test    eax, eax
0x1400795e7  jnz     short loc_140079622
0x1400795e9  mov     rbx, cs:WPP_GLOBAL_Control
0x1400795f0  cmp     rbx, r15
0x1400795f3  jz      short loc_140079622
0x1400795f5  test    [rbx+1Ch], r13b
0x1400795f9  jz      short loc_140079622
0x1400795fb  cmp     [rbx+19h], r13b
0x1400795ff  jb      short loc_140079622
0x140079601  mov     rbx, [rbx+10h]
  ... truncated ...
```
