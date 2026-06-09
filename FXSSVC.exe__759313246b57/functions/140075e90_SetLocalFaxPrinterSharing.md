# SetLocalFaxPrinterSharing

- ea: `0x140075e90`
- end: `0x14007619e`
- name: `SetLocalFaxPrinterSharing`
- size: `782`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14004ae64`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400698ec`
- `0x14006998c`
- `0x140075714`
- `0x140075e90`
- `0x140086ec0`
- `0x140086f80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140075f21`
- `KERNEL32!GetLastError` at `0x140075f93`
- `KERNEL32!GetLastError` at `0x140076005`
- `KERNEL32!GetLastError` at `0x140076057`
- `KERNEL32!GetLastError` at `0x1400760bf`
- `KERNEL32!GetLastError` at `0x140076118`
- `KERNEL32!GetLastError` at `0x140075f21`
- `KERNEL32!GetLastError` at `0x140075f93`
- `KERNEL32!GetLastError` at `0x140076005`
- `KERNEL32!GetLastError` at `0x140076057`
- `KERNEL32!GetLastError` at `0x1400760bf`
- `KERNEL32!GetLastError` at `0x140076118`
- `WINSPOOL!SetPrinterW` at `0x140076108`
- `WINSPOOL!SetPrinterW` at `0x140076108`
- `WINSPOOL!OpenPrinterW` at `0x140075f83`
- `WINSPOOL!OpenPrinterW` at `0x140075f83`
- `WINSPOOL!GetPrinterW` at `0x140075ff1`
- `WINSPOOL!GetPrinterW` at `0x1400760af`
- `WINSPOOL!GetPrinterW` at `0x140075ff1`
- `WINSPOOL!GetPrinterW` at `0x1400760af`
- `WINSPOOL!ClosePrinter` at `0x14007615c`
- `WINSPOOL!ClosePrinter` at `0x14007615c`

## pseudocode

```c
__int64 SetLocalFaxPrinterSharing()
{
  DWORD LastError; // ebx
  CMapDeviceId *v1; // rcx
  __int64 v2; // rdx
  BYTE *v3; // rdi
  DWORD v4; // eax
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  int v8; // eax
  DWORD cbBuf; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE phPrinter; // [rsp+38h] [rbp-C8h] BYREF
  _PRINTER_DEFAULTSW pDefault; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pPrinterName[784]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE pPrinter[4096]; // [rsp+680h] [rbp+580h] BYREF

  phPrinter = 0;
  memset(&pDefault, 0, sizeof(pDefault));
  cbBuf = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
  }
  if ( !(unsigned int)GetFirstFaxPrinterName(pPrinterName) )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = 54;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v1 + 2), v2, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, LastError);
      return LastError;
    }
    return LastError;
  }
  pDefault.DesiredAccess = 983052;
  if ( OpenPrinterW(pPrinterName, &phPrinter, &pDefault) )
  {
    v3 = pPrinter;
    if ( GetPrinterW(phPrinter, 2u, pPrinter, 0x1000u, &cbBuf) )
      goto LABEL_32;
    v4 = GetLastError();
    LastError = v4;
    if ( v4 != 122 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v6 = 56;
      goto LABEL_38;
    }
    v3 = (BYTE *)pMemAlloc(cbBuf);
    if ( !v3 )
    {
      LastError = GetLastError();
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v7 = cbBuf;
      v6 = 57;
      goto LABEL_39;
    }
    if ( GetPrinterW(phPrinter, 2u, v3, cbBuf, &cbBuf) )
    {
LABEL_32:
      v8 = *((_DWORD *)v3 + 26);
      LastError = 0;
      if ( (v8 & 8) == 0 )
        goto LABEL_40;
      *((_DWORD *)v3 + 26) = v8 & 0xFFFFFFF7;
      if ( SetPrinterW(phPrinter, 2u, v3, 0) )
        goto LABEL_40;
      v4 = GetLastError();
      LastError = v4;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v6 = 59;
    }
    else
    {
      v4 = GetLastError();
      LastError = v4;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      v6 = 58;
    }
LABEL_38:
    v7 = v4;
LABEL_39:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v7);
LABEL_40:
    if ( phPrinter )
      ClosePrinter(phPrinter);
    if ( v3 != pPrinter )
      pMemFree(v3);
    return LastError;
  }
  LastError = GetLastError();
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v2 = 55;
    goto LABEL_10;
  }
  return LastError;
}

```

## disassembly

```asm
0x140075e90  push    rbp
0x140075e92  push    rbx
0x140075e93  push    rsi
0x140075e94  push    rdi
0x140075e95  push    r14
0x140075e97  push    r15
0x140075e99  lea     rbp, [rsp-1598h]
0x140075ea1  mov     eax, 1698h
0x140075ea6  call    _alloca_probe
0x140075eab  sub     rsp, rax
0x140075eae  mov     rax, cs:__security_cookie
0x140075eb5  xor     rax, rsp
0x140075eb8  mov     [rbp+15C0h+var_40], rax
0x140075ebf  xor     eax, eax
0x140075ec1  mov     [rsp+16C0h+phPrinter], 0
0x140075eca  xorps   xmm0, xmm0
0x140075ecd  mov     qword ptr [rsp+16C0h+pDefault.DesiredAccess], rax
0x140075ed2  movups  xmmword ptr [rsp+16C0h+pDefault.pDatatype], xmm0
0x140075ed7  mov     [rsp+16C0h+cbBuf], eax
0x140075edb  mov     rcx, cs:WPP_GLOBAL_Control
0x140075ee2  lea     r14, WPP_GLOBAL_Control
0x140075ee9  lea     r15, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x140075ef0  lea     esi, [rax+2]
0x140075ef3  cmp     rcx, r14
0x140075ef6  jz      short loc_140075F13
0x140075ef8  test    [rcx+1Ch], sil
0x140075efc  jz      short loc_140075F13
0x140075efe  cmp     byte ptr [rcx+19h], 5
0x140075f02  jb      short loc_140075F13
0x140075f04  mov     rcx, [rcx+10h]
0x140075f08  lea     edx, [rax+35h]
0x140075f0b  mov     r8, r15
0x140075f0e  call    WPP_SF_
0x140075f13  lea     rcx, [rsp+16C0h+pPrinterName]; unsigned __int16 *
0x140075f18  call    ?GetFirstFaxPrinterName@@YAHPEAGKK@Z; GetFirstFaxPrinterName(ushort *,ulong,ulong)
0x140075f1d  test    eax, eax
0x140075f1f  jnz     short loc_140075F6C
0x140075f21  call    cs:__imp_GetLastError
0x140075f28  nop     dword ptr [rax+rax+00h]
0x140075f2d  mov     ebx, eax
0x140075f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140075f36  cmp     rcx, r14
0x140075f39  jz      loc_14007617C
0x140075f3f  test    [rcx+1Ch], sil
0x140075f43  jz      loc_14007617C
0x140075f49  cmp     [rcx+19h], sil
0x140075f4d  jb      loc_14007617C
0x140075f53  mov     edx, 36h ; '6'
0x140075f58  mov     rcx, [rcx+10h]
0x140075f5c  mov     r9d, ebx
0x140075f5f  mov     r8, r15
0x140075f62  call    WPP_SF_d
0x140075f67  jmp     loc_14007617C
0x140075f6c  lea     r8, [rsp+16C0h+pDefault]; pDefault
0x140075f71  mov     [rsp+16C0h+pDefault.DesiredAccess], 0F000Ch
0x140075f79  lea     rdx, [rsp+16C0h+phPrinter]; phPrinter
0x140075f7e  lea     rcx, [rsp+16C0h+pPrinterName]; pPrinterName
0x140075f83  call    cs:__imp_OpenPrinterW
0x140075f8a  nop     dword ptr [rax+rax+00h]
0x140075f8f  test    eax, eax
0x140075f91  jnz     short loc_140075FCC
0x140075f93  call    cs:__imp_GetLastError
0x140075f9a  nop     dword ptr [rax+rax+00h]
0x140075f9f  mov     ebx, eax
0x140075fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140075fa8  cmp     rcx, r14
0x140075fab  jz      loc_14007617C
0x140075fb1  test    [rcx+1Ch], sil
0x140075fb5  jz      loc_14007617C
0x140075fbb  cmp     [rcx+19h], sil
0x140075fbf  jb      loc_14007617C
0x140075fc5  mov     edx, 37h ; '7'
0x140075fca  jmp     short loc_140075F58
0x140075fcc  mov     rcx, [rsp+16C0h+phPrinter]; hPrinter
0x140075fd1  lea     rax, [rsp+16C0h+cbBuf]
0x140075fd6  mov     r9d, 1000h; cbBuf
0x140075fdc  mov     [rsp+16C0h+pcbNeeded], rax; pcbNeeded
0x140075fe1  lea     r8, [rbp+15C0h+pPrinter]; pPrinter
0x140075fe8  mov     edx, esi; Level
0x140075fea  lea     rdi, [rbp+15C0h+pPrinter]
0x140075ff1  call    cs:__imp_GetPrinterW
0x140075ff8  nop     dword ptr [rax+rax+00h]
0x140075ffd  test    eax, eax
0x140075fff  jnz     loc_1400760EC
0x140076005  call    cs:__imp_GetLastError
0x14007600c  nop     dword ptr [rax+rax+00h]
0x140076011  mov     ebx, eax
0x140076013  cmp     eax, 7Ah ; 'z'
0x140076016  jz      short loc_140076046
0x140076018  mov     rcx, cs:WPP_GLOBAL_Control
0x14007601f  cmp     rcx, r14
0x140076022  jz      loc_140076152
0x140076028  test    [rcx+1Ch], sil
0x14007602c  jz      loc_140076152
0x140076032  cmp     [rcx+19h], sil
0x140076036  jb      loc_140076152
0x14007603c  mov     edx, 38h ; '8'
0x140076041  jmp     loc_140076143
0x140076046  mov     ecx, [rsp+16C0h+cbBuf]; dwBytes
0x14007604a  call    pMemAlloc
0x14007604f  mov     rdi, rax
0x140076052  test    rax, rax
0x140076055  jnz     short loc_140076096
0x140076057  call    cs:__imp_GetLastError
0x14007605e  nop     dword ptr [rax+rax+00h]
0x140076063  mov     ebx, eax
0x140076065  mov     rcx, cs:WPP_GLOBAL_Control
0x14007606c  cmp     rcx, r14
0x14007606f  jz      loc_140076152
0x140076075  test    [rcx+1Ch], sil
0x140076079  jz      loc_140076152
0x14007607f  cmp     [rcx+19h], sil
0x140076083  jb      loc_140076152
0x140076089  mov     r9d, [rsp+16C0h+cbBuf]
0x14007608e  lea     edx, [rdi+39h]
0x140076091  jmp     loc_140076146
0x140076096  mov     r9d, [rsp+16C0h+cbBuf]; cbBuf
0x14007609b  lea     rax, [rsp+16C0h+cbBuf]
0x1400760a0  mov     rcx, [rsp+16C0h+phPrinter]; hPrinter
0x1400760a5  mov     r8, rdi; pPrinter
0x1400760a8  mov     edx, esi; Level
0x1400760aa  mov     [rsp+16C0h+pcbNeeded], rax; pcbNeeded
0x1400760af  call    cs:__imp_GetPrinterW
0x1400760b6  nop     dword ptr [rax+rax+00h]
0x1400760bb  test    eax, eax
0x1400760bd  jnz     short loc_1400760EC
0x1400760bf  call    cs:__imp_GetLastError
0x1400760c6  nop     dword ptr [rax+rax+00h]
0x1400760cb  mov     ebx, eax
0x1400760cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400760d4  cmp     rcx, r14
0x1400760d7  jz      short loc_140076152
0x1400760d9  test    [rcx+1Ch], sil
0x1400760dd  jz      short loc_140076152
0x1400760df  cmp     [rcx+19h], sil
0x1400760e3  jb      short loc_140076152
0x1400760e5  mov     edx, 3Ah ; ':'
0x1400760ea  jmp     short loc_140076143
0x1400760ec  mov     eax, [rdi+68h]
0x1400760ef  xor     ebx, ebx
0x1400760f1  test    al, 8
0x1400760f3  jz      short loc_140076152
0x1400760f5  and     eax, 0FFFFFFF7h
0x1400760f8  xor     r9d, r9d; Command
0x1400760fb  mov     [rdi+68h], eax
0x1400760fe  mov     r8, rdi; pPrinter
0x140076101  mov     rcx, [rsp+16C0h+phPrinter]; hPrinter
0x140076106  mov     edx, esi; Level
0x140076108  call    cs:__imp_SetPrinterW
0x14007610f  nop     dword ptr [rax+rax+00h]
0x140076114  test    eax, eax
0x140076116  jnz     short loc_140076152
0x140076118  call    cs:__imp_GetLastError
0x14007611f  nop     dword ptr [rax+rax+00h]
0x140076124  mov     ebx, eax
0x140076126  mov     rcx, cs:WPP_GLOBAL_Control
0x14007612d  cmp     rcx, r14
0x140076130  jz      short loc_140076152
0x140076132  test    [rcx+1Ch], sil
0x140076136  jz      short loc_140076152
0x140076138  cmp     [rcx+19h], sil
0x14007613c  jb      short loc_140076152
0x14007613e  mov     edx, 3Bh ; ';'
0x140076143  mov     r9d, eax
0x140076146  mov     rcx, [rcx+10h]
0x14007614a  mov     r8, r15
0x14007614d  call    WPP_SF_d
0x140076152  mov     rcx, [rsp+16C0h+phPrinter]; hPrinter
0x140076157  test    rcx, rcx
0x14007615a  jz      short loc_140076168
0x14007615c  call    cs:__imp_ClosePrinter
0x140076163  nop     dword ptr [rax+rax+00h]
0x140076168  lea     rax, [rbp+15C0h+pPrinter]
0x14007616f  cmp     rdi, rax
0x140076172  jz      short loc_14007617C
0x140076174  mov     rcx, rdi; lpMem
0x140076177  call    pMemFree
0x14007617c  mov     eax, ebx
0x14007617e  mov     rcx, [rbp+15C0h+var_40]
0x140076185  xor     rcx, rsp; StackCookie
0x140076188  call    __security_check_cookie
0x14007618d  add     rsp, 1698h
0x140076194  pop     r15
0x140076196  pop     r14
0x140076198  pop     rdi
0x140076199  pop     rsi
0x14007619a  pop     rbx
0x14007619b  pop     rbp
0x14007619c  retn
```
