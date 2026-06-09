# CheckCertificateForCorruption

- ea: `0x1800028dc`
- end: `0x180002a68`
- name: `CheckCertificateForCorruption`
- size: `396`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800032a8`

## callees

- `0x1800028dc`
- `0x180007040`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800029c4`
- `KERNEL32!CreateFileW` at `0x1800029c4`
- `KERNEL32!GetLastError` at `0x1800029d3`
- `KERNEL32!GetLastError` at `0x180002a07`
- `KERNEL32!GetLastError` at `0x1800029d3`
- `KERNEL32!GetLastError` at `0x180002a07`
- `KERNEL32!CloseHandle` at `0x180002a12`
- `KERNEL32!CloseHandle` at `0x180002a12`
- `imagehlp!ImageEnumerateCertificates` at `0x1800029ff`
- `imagehlp!ImageEnumerateCertificates` at `0x1800029ff`
- `WINTRUST!WinVerifyTrust` at `0x18000298a`
- `WINTRUST!WinVerifyTrust` at `0x18000298a`

## pseudocode

```c
int __fastcall CheckCertificateForCorruption(LPCWSTR lpFileName, _DWORD *a2)
{
  int result; // eax
  HANDLE FileW; // rax
  void *v6; // r14
  BOOL v7; // ebx
  signed int LastError; // edi
  DWORD CertificateCount[4]; // [rsp+40h] [rbp-79h] BYREF
  _QWORD pWVTData[12]; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v11[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v12; // [rsp+C0h] [rbp+7h]
  GUID pgActionID; // [rsp+D0h] [rbp+17h] BYREF

  v11[1] = lpFileName;
  *a2 = 0;
  memset(&pWVTData[6], 0, 24);
  pWVTData[10] = 0;
  v11[0] = 32;
  pWVTData[5] = v11;
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  v12 = 0;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  pWVTData[0] = 88;
  pWVTData[4] = 1;
  pWVTData[1] = 0;
  pWVTData[2] = 0;
  pWVTData[3] = 2;
  pWVTData[9] = 528;
  result = WinVerifyTrust(0, &pgActionID, pWVTData);
  if ( !result )
    goto LABEL_13;
  if ( result != -2146762496 )
  {
LABEL_12:
    result = 1;
LABEL_13:
    *a2 = 0;
    return result;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  CertificateCount[0] = 0;
  v7 = ImageEnumerateCertificates(FileW, 0xFFu, CertificateCount, 0, 0);
  LastError = GetLastError();
  CloseHandle(v6);
  if ( v7 )
  {
    if ( CertificateCount[0] )
    {
      *a2 = 1;
      return 0;
    }
    goto LABEL_12;
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x1800028dc  mov     [rsp-8+arg_10], rbx
0x1800028e1  push    rbp
0x1800028e2  push    rsi
0x1800028e3  push    rdi
0x1800028e4  push    r14
0x1800028e6  push    r15
0x1800028e8  lea     rbp, [rsp-37h]
0x1800028ed  sub     rsp, 0F0h
0x1800028f4  mov     rax, cs:__security_cookie
0x1800028fb  xor     rax, rsp
0x1800028fe  mov     [rbp+57h+var_30], rax
0x180002902  xor     r15d, r15d
0x180002905  mov     [rbp+57h+var_58], rcx
0x180002909  xor     eax, eax
0x18000290b  mov     [rdx], r15d
0x18000290e  mov     [rbp+57h+var_90], rax
0x180002912  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x180002916  mov     [rbp+57h+var_70], rax
0x18000291a  mov     rsi, rdx
0x18000291d  lea     rax, [rbp+57h+var_60]
0x180002921  mov     [rbp+57h+var_60], 20h ; ' '
0x180002929  mov     rbx, rcx
0x18000292c  mov     [rbp+57h+var_98], rax
0x180002930  xorps   xmm0, xmm0
0x180002933  mov     [rbp+57h+pgActionID.Data1], 0AAC56Bh
0x18000293a  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x18000293e  mov     dword ptr [rbp+57h+pgActionID.Data2], 11D0CD44h
0x180002945  xor     ecx, ecx; hwnd
0x180002947  mov     dword ptr [rbp+57h+pgActionID.Data4], 0C000C28Ch
0x18000294e  movdqu  [rbp+57h+var_50], xmm0
0x180002953  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0EE95C24Fh
0x18000295a  mov     [rbp+57h+pWVTData], 58h ; 'X'
0x180002962  mov     [rbp+57h+var_A0], 1
0x18000296a  mov     [rbp+57h+var_B8], r15
0x18000296e  mov     [rbp+57h+var_B0], r15
0x180002972  mov     [rbp+57h+var_A8], 2
0x18000297a  mov     [rbp+57h+var_88], r15
0x18000297e  mov     [rbp+57h+var_80], r15
0x180002982  mov     [rbp+57h+var_78], 210h
0x18000298a  call    cs:__imp_WinVerifyTrust
0x180002990  test    eax, eax
0x180002992  jz      loc_180002A42
0x180002998  cmp     eax, 800B0100h
0x18000299d  jnz     loc_180002A3D
0x1800029a3  xor     r9d, r9d; lpSecurityAttributes
0x1800029a6  mov     [rsp+110h+hTemplateFile], r15; hTemplateFile
0x1800029ab  mov     [rsp+110h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800029b0  mov     edx, 80000000h; dwDesiredAccess
0x1800029b5  mov     rcx, rbx; lpFileName
0x1800029b8  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x1800029c0  lea     r8d, [r9+1]; dwShareMode
0x1800029c4  call    cs:__imp_CreateFileW
0x1800029ca  mov     r14, rax
0x1800029cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800029d1  jnz     short loc_1800029E7
0x1800029d3  call    cs:__imp_GetLastError
0x1800029d9  test    eax, eax
0x1800029db  jle     short loc_180002A45
0x1800029dd  movzx   eax, ax
0x1800029e0  or      eax, 80070000h
0x1800029e5  jmp     short loc_180002A45
0x1800029e7  mov     edx, 0FFh; TypeFilter
0x1800029ec  mov     [rbp+57h+CertificateCount], r15d
0x1800029f0  xor     r9d, r9d; Indices
0x1800029f3  mov     [rsp+110h+dwCreationDisposition], r15d; IndexCount
0x1800029f8  lea     r8, [rbp+57h+CertificateCount]; CertificateCount
0x1800029fc  mov     rcx, r14; FileHandle
0x1800029ff  call    cs:__imp_ImageEnumerateCertificates
0x180002a05  mov     ebx, eax
0x180002a07  call    cs:__imp_GetLastError
0x180002a0d  mov     rcx, r14; hObject
0x180002a10  mov     edi, eax
0x180002a12  call    cs:__imp_CloseHandle
0x180002a18  test    ebx, ebx
0x180002a1a  jnz     short loc_180002A2D
0x180002a1c  test    edi, edi
0x180002a1e  jle     short loc_180002A29
0x180002a20  movzx   edi, di
0x180002a23  or      edi, 80070000h
0x180002a29  mov     eax, edi
0x180002a2b  jmp     short loc_180002A45
0x180002a2d  cmp     [rbp+57h+CertificateCount], r15d
0x180002a31  jbe     short loc_180002A3D
0x180002a33  mov     dword ptr [rsi], 1
0x180002a39  xor     eax, eax
0x180002a3b  jmp     short loc_180002A45
0x180002a3d  mov     eax, 1
0x180002a42  mov     [rsi], r15d
0x180002a45  mov     rcx, [rbp+57h+var_30]
0x180002a49  xor     rcx, rsp; StackCookie
0x180002a4c  call    __security_check_cookie
0x180002a51  mov     rbx, [rsp+110h+arg_10]
0x180002a59  add     rsp, 0F0h
0x180002a60  pop     r15
0x180002a62  pop     r14
0x180002a64  pop     rdi
0x180002a65  pop     rsi
0x180002a66  pop     rbp
0x180002a67  retn
```
