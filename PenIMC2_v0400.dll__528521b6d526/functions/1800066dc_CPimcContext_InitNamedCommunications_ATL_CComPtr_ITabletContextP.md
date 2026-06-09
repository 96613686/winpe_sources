# CPimcContext::InitNamedCommunications(ATL::CComPtr<ITabletContextP>)

- ea: `0x1800066dc`
- end: `0x180006a25`
- name: `?InitNamedCommunications@CPimcContext@@QEAAJV?$CComPtr@UITabletContextP@@@ATL@@@Z`
- size: `841`
- prototype: `__int64 __fastcall(CPimcContext *this, WCHAR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800062a0`

## callees

- `0x180001360`
- `0x1800066dc`
- `0x180006a28`
- `0x180007f00`
- `0x18000cbb8`
- `0x18000cdb0`
- `0x18000ce0c`
- `0x18000d488`
- `0x18000e4a0`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x18000674b`
- `ADVAPI32!OpenProcessToken` at `0x18000674b`
- `ADVAPI32!GetTokenInformation` at `0x180006778`
- `ADVAPI32!GetTokenInformation` at `0x1800067b5`
- `ADVAPI32!GetTokenInformation` at `0x180006778`
- `ADVAPI32!GetTokenInformation` at `0x1800067b5`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800067c7`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800067c7`
- `KERNEL32!GetLastError` at `0x180006782`
- `KERNEL32!GetLastError` at `0x1800068ef`
- `KERNEL32!GetLastError` at `0x180006924`
- `KERNEL32!GetLastError` at `0x180006955`
- `KERNEL32!GetLastError` at `0x180006984`
- `KERNEL32!GetLastError` at `0x180006782`
- `KERNEL32!GetLastError` at `0x1800068ef`
- `KERNEL32!GetLastError` at `0x180006924`
- `KERNEL32!GetLastError` at `0x180006955`
- `KERNEL32!GetLastError` at `0x180006984`
- `KERNEL32!CloseHandle` at `0x1800067e0`
- `KERNEL32!CloseHandle` at `0x1800067e0`
- `KERNEL32!GetCurrentProcessId` at `0x180006718`
- `KERNEL32!GetCurrentProcessId` at `0x180006718`
- `KERNEL32!OpenEventW` at `0x1800068db`
- `KERNEL32!OpenEventW` at `0x180006915`
- `KERNEL32!OpenEventW` at `0x1800068db`
- `KERNEL32!OpenEventW` at `0x180006915`
- `KERNEL32!OpenMutexW` at `0x180006946`
- `KERNEL32!OpenMutexW` at `0x180006946`
- `KERNEL32!LocalFree` at `0x1800069d0`
- `KERNEL32!LocalFree` at `0x1800069dc`
- `KERNEL32!LocalFree` at `0x1800069d0`
- `KERNEL32!LocalFree` at `0x1800069dc`
- `KERNEL32!GetCurrentProcess` at `0x180006738`
- `KERNEL32!GetCurrentProcess` at `0x180006738`
- `KERNEL32!OpenFileMappingW` at `0x180006975`
- `KERNEL32!OpenFileMappingW` at `0x180006975`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPimcContext::InitNamedCommunications(CPimcContext *this, WCHAR *a2)
{
  DWORD CurrentProcessId; // r15d
  signed int MandatoryLabel; // ebx
  HANDLE CurrentProcess; // rax
  PSID *v7; // rsi
  HANDLE v8; // rax
  signed int LastError; // eax
  HANDLE v10; // rax
  signed int v11; // eax
  HANDLE v12; // rax
  signed int v13; // eax
  HANDLE v14; // rax
  signed int v15; // eax
  PDWORD ReturnLength; // [rsp+20h] [rbp-E0h]
  PDWORD ReturnLengtha; // [rsp+20h] [rbp-E0h]
  PDWORD ReturnLengthb; // [rsp+20h] [rbp-E0h]
  DWORD TokenInformationLength; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+64h] [rbp-9Ch] BYREF
  int v24; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v25; // [rsp+6Ch] [rbp-94h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR StringSid[3]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR v30[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR v31[264]; // [rsp+6C0h] [rbp+5C0h] BYREF

  StringSid[1] = a2;
  CurrentProcessId = GetCurrentProcessId();
  StringSid[0] = 0;
  hMem = 0;
  MandatoryLabel = -2147467259;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v7 = (PSID *)operator new[](TokenInformationLength);
      if ( GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength)
        && ConvertSidToStringSidW(*v7, StringSid) )
      {
        MandatoryLabel = 0;
      }
      operator delete(v7);
    }
    CloseHandle(TokenHandle);
  }
  if ( MandatoryLabel < 0 )
    goto LABEL_29;
  MandatoryLabel = GetMandatoryLabel((LPWSTR *)&hMem);
  if ( MandatoryLabel < 0 )
    goto LABEL_29;
  MandatoryLabel = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPWSTR, HLOCAL, int *, unsigned int *, int *, int *))(**(_QWORD **)a2 + 280LL))(
                     *(_QWORD *)a2,
                     CurrentProcessId,
                     StringSid[0],
                     hMem,
                     &v22,
                     &v25,
                     &v23,
                     &v24);
  if ( MandatoryLabel < 0 )
    goto LABEL_29;
  LODWORD(ReturnLength) = v22;
  StringCchPrintfW(Buffer, 0x105u, L"wisptis-1-%d-%u", CurrentProcessId, ReturnLength);
  LODWORD(ReturnLengtha) = v23;
  StringCchPrintfW(v30, 0x105u, L"wisptis-2-%d-%u", CurrentProcessId, ReturnLengtha);
  LODWORD(ReturnLengthb) = v24;
  StringCchPrintfW(v31, 0x105u, L"wisptis-3-%d-%u", CurrentProcessId, ReturnLengthb);
  StringCchPrintfW(Name, 0x105u, L"wisptis-4-%u", v25);
  v8 = OpenEventW(0x1F0003u, 0, Name);
  *((_QWORD *)this + 8) = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    MandatoryLabel = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      MandatoryLabel = LastError;
    if ( MandatoryLabel < 0 )
      goto LABEL_29;
  }
  v10 = OpenEventW(0x100000u, 0, Buffer);
  *((_QWORD *)this + 7) = v10;
  if ( !v10 )
  {
    v11 = GetLastError();
    MandatoryLabel = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      MandatoryLabel = v11;
    if ( MandatoryLabel < 0 )
      goto LABEL_29;
  }
  v12 = OpenMutexW(0x1F0001u, 0, v30);
  *((_QWORD *)this + 9) = v12;
  if ( !v12 )
  {
    v13 = GetLastError();
    MandatoryLabel = (unsigned __int16)v13 | 0x80070000;
    if ( v13 <= 0 )
      MandatoryLabel = v13;
    if ( MandatoryLabel < 0 )
      goto LABEL_29;
  }
  v14 = OpenFileMappingW(6u, 0, v31);
  *((_QWORD *)this + 10) = v14;
  if ( !v14 )
  {
    v15 = GetLastError();
    MandatoryLabel = (unsigned __int16)v15 | 0x80070000;
    if ( v15 <= 0 )
      MandatoryLabel = v15;
    if ( MandatoryLabel < 0 )
      goto LABEL_29;
  }
  MandatoryLabel = CPimcContext::InitCommunicationsCore(this);
  if ( MandatoryLabel < 0 )
  {
LABEL_29:
    SafeCloseHandle((void **)this + 10);
    SafeCloseHandle((void **)this + 9);
    SafeCloseHandle((void **)this + 7);
    SafeCloseHandle((void **)this + 8);
  }
  LocalFree(hMem);
  LocalFree(StringSid[0]);
  if ( *(_QWORD *)a2 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)a2 + 16LL))(*(_QWORD *)a2);
  return (unsigned int)MandatoryLabel;
}

```

## disassembly

```asm
0x1800066dc  mov     [rsp-8+arg_10], rbx
0x1800066e1  mov     [rsp-8+arg_18], rsi
0x1800066e6  push    rbp
0x1800066e7  push    rdi
0x1800066e8  push    r12
0x1800066ea  push    r14
0x1800066ec  push    r15
0x1800066ee  lea     rbp, [rsp-7E0h]
0x1800066f6  sub     rsp, 8E0h
0x1800066fd  mov     rax, cs:__security_cookie
0x180006704  xor     rax, rsp
0x180006707  mov     [rbp+800h+var_30], rax
0x18000670e  mov     r14, rdx
0x180006711  mov     rdi, rcx
0x180006714  mov     [rbp+800h+var_880], rdx
0x180006718  call    cs:__imp_GetCurrentProcessId
0x18000671e  mov     r15d, eax
0x180006721  xor     r12d, r12d
0x180006724  mov     [rsp+900h+StringSid], r12
0x180006729  mov     [rsp+900h+hMem], r12
0x18000672e  mov     ebx, 80004005h
0x180006733  mov     [rsp+900h+TokenHandle], r12
0x180006738  call    cs:__imp_GetCurrentProcess
0x18000673e  mov     rcx, rax; ProcessHandle
0x180006741  lea     r8, [rsp+900h+TokenHandle]; TokenHandle
0x180006746  lea     edx, [r12+8]; DesiredAccess
0x18000674b  call    cs:__imp_OpenProcessToken
0x180006751  test    eax, eax
0x180006753  jz      loc_1800067E6
0x180006759  mov     [rsp+900h+TokenInformationLength], r12d
0x18000675e  lea     rax, [rsp+900h+TokenInformationLength]
0x180006763  mov     [rsp+900h+ReturnLength], rax; ReturnLength
0x180006768  xor     r9d, r9d; TokenInformationLength
0x18000676b  xor     r8d, r8d; TokenInformation
0x18000676e  lea     edx, [r12+1]; TokenInformationClass
0x180006773  mov     rcx, [rsp+900h+TokenHandle]; TokenHandle
0x180006778  call    cs:__imp_GetTokenInformation
0x18000677e  test    eax, eax
0x180006780  jnz     short loc_1800067DB
0x180006782  call    cs:__imp_GetLastError
0x180006788  cmp     eax, 7Ah ; 'z'
0x18000678b  jnz     short loc_1800067DB
0x18000678d  mov     ecx, [rsp+900h+TokenInformationLength]; unsigned __int64
0x180006791  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006796  mov     rsi, rax
0x180006799  lea     rax, [rsp+900h+TokenInformationLength]
0x18000679e  mov     [rsp+900h+ReturnLength], rax; ReturnLength
0x1800067a3  mov     r9d, [rsp+900h+TokenInformationLength]; TokenInformationLength
0x1800067a8  mov     r8, rsi; TokenInformation
0x1800067ab  lea     edx, [r12+1]; TokenInformationClass
0x1800067b0  mov     rcx, [rsp+900h+TokenHandle]; TokenHandle
0x1800067b5  call    cs:__imp_GetTokenInformation
0x1800067bb  test    eax, eax
0x1800067bd  jz      short loc_1800067D3
0x1800067bf  lea     rdx, [rsp+900h+StringSid]; StringSid
0x1800067c4  mov     rcx, [rsi]; Sid
0x1800067c7  call    cs:__imp_ConvertSidToStringSidW
0x1800067cd  test    eax, eax
0x1800067cf  cmovnz  ebx, r12d
0x1800067d3  mov     rcx, rsi; Block
0x1800067d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800067db  mov     rcx, [rsp+900h+TokenHandle]; hObject
0x1800067e0  call    cs:__imp_CloseHandle
0x1800067e6  test    ebx, ebx
0x1800067e8  js      loc_1800069A6
0x1800067ee  lea     rcx, [rsp+900h+hMem]; StringSid
0x1800067f3  call    ?GetMandatoryLabel@@YAJPEAPEAG@Z; GetMandatoryLabel(ushort * *)
0x1800067f8  mov     ebx, eax
0x1800067fa  test    eax, eax
0x1800067fc  js      loc_1800069A6
0x180006802  mov     rcx, [r14]
0x180006805  mov     rax, [rcx]
0x180006808  lea     rdx, [rsp+900h+var_898]
0x18000680d  mov     [rsp+900h+var_8C8], rdx
0x180006812  lea     rdx, [rsp+900h+var_89C]
0x180006817  mov     [rsp+900h+var_8D0], rdx
0x18000681c  lea     rdx, [rsp+900h+var_894]
0x180006821  mov     [rsp+900h+var_8D8], rdx
0x180006826  lea     rdx, [rsp+900h+var_8A0]
0x18000682b  mov     [rsp+900h+ReturnLength], rdx
0x180006830  mov     r9, [rsp+900h+hMem]
0x180006835  mov     r8, [rsp+900h+StringSid]
0x18000683a  mov     edx, r15d
0x18000683d  mov     rax, [rax+118h]
0x180006844  call    cs:__guard_dispatch_icall_fptr
0x18000684a  mov     ebx, eax
0x18000684c  test    eax, eax
0x18000684e  js      loc_1800069A6
0x180006854  mov     eax, [rsp+900h+var_8A0]
0x180006858  mov     dword ptr [rsp+900h+ReturnLength], eax
0x18000685c  mov     r9d, r15d
0x18000685f  lea     r8, aWisptis1DU; "wisptis-1-%d-%u"
0x180006866  mov     ebx, 105h
0x18000686b  mov     edx, ebx; unsigned __int64
0x18000686d  lea     rcx, [rbp+800h+Buffer]; Buffer
0x180006874  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006879  mov     eax, [rsp+900h+var_89C]
0x18000687d  mov     dword ptr [rsp+900h+ReturnLength], eax
0x180006881  mov     r9d, r15d
0x180006884  lea     r8, aWisptis2DU; "wisptis-2-%d-%u"
0x18000688b  mov     edx, ebx; unsigned __int64
0x18000688d  lea     rcx, [rbp+800h+var_450]; Buffer
0x180006894  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006899  mov     eax, [rsp+900h+var_898]
0x18000689d  mov     dword ptr [rsp+900h+ReturnLength], eax
0x1800068a1  mov     r9d, r15d
0x1800068a4  lea     r8, aWisptis3DU; "wisptis-3-%d-%u"
0x1800068ab  mov     edx, ebx; unsigned __int64
0x1800068ad  lea     rcx, [rbp+800h+var_240]; Buffer
0x1800068b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800068b9  mov     r9d, [rsp+900h+var_894]
0x1800068be  lea     r8, aWisptis4U; "wisptis-4-%u"
0x1800068c5  mov     edx, ebx; unsigned __int64
0x1800068c7  lea     rcx, [rbp+800h+Name]; Buffer
0x1800068cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800068d0  lea     r8, [rbp+800h+Name]; lpName
0x1800068d4  xor     edx, edx; bInheritHandle
0x1800068d6  mov     ecx, 1F0003h; dwDesiredAccess
0x1800068db  call    cs:__imp_OpenEventW
0x1800068e1  mov     [rdi+40h], rax
0x1800068e5  mov     esi, 80070000h
0x1800068ea  test    rax, rax
0x1800068ed  jnz     short loc_180006907
0x1800068ef  call    cs:__imp_GetLastError
0x1800068f5  movzx   ebx, ax
0x1800068f8  or      ebx, esi
0x1800068fa  test    eax, eax
0x1800068fc  cmovle  ebx, eax
0x1800068ff  test    ebx, ebx
0x180006901  js      loc_1800069A6
0x180006907  lea     r8, [rbp+800h+Buffer]; lpName
0x18000690e  xor     edx, edx; bInheritHandle
0x180006910  mov     ecx, 100000h; dwDesiredAccess
0x180006915  call    cs:__imp_OpenEventW
0x18000691b  mov     [rdi+38h], rax
0x18000691f  test    rax, rax
0x180006922  jnz     short loc_180006938
0x180006924  call    cs:__imp_GetLastError
0x18000692a  movzx   ebx, ax
0x18000692d  or      ebx, esi
0x18000692f  test    eax, eax
0x180006931  cmovle  ebx, eax
0x180006934  test    ebx, ebx
0x180006936  js      short loc_1800069A6
0x180006938  lea     r8, [rbp+800h+var_450]; lpName
0x18000693f  xor     edx, edx; bInheritHandle
0x180006941  mov     ecx, 1F0001h; dwDesiredAccess
0x180006946  call    cs:__imp_OpenMutexW
0x18000694c  mov     [rdi+48h], rax
0x180006950  test    rax, rax
0x180006953  jnz     short loc_180006969
0x180006955  call    cs:__imp_GetLastError
0x18000695b  movzx   ebx, ax
0x18000695e  or      ebx, esi
0x180006960  test    eax, eax
0x180006962  cmovle  ebx, eax
0x180006965  test    ebx, ebx
0x180006967  js      short loc_1800069A6
0x180006969  lea     r8, [rbp+800h+var_240]; lpName
0x180006970  xor     edx, edx; bInheritHandle
0x180006972  lea     ecx, [rdx+6]; dwDesiredAccess
0x180006975  call    cs:__imp_OpenFileMappingW
0x18000697b  mov     [rdi+50h], rax
0x18000697f  test    rax, rax
0x180006982  jnz     short loc_180006998
0x180006984  call    cs:__imp_GetLastError
0x18000698a  movzx   ebx, ax
0x18000698d  or      ebx, esi
0x18000698f  test    eax, eax
0x180006991  cmovle  ebx, eax
0x180006994  test    ebx, ebx
0x180006996  js      short loc_1800069A6
0x180006998  mov     rcx, rdi; this
0x18000699b  call    ?InitCommunicationsCore@CPimcContext@@QEAAJXZ; CPimcContext::InitCommunicationsCore(void)
0x1800069a0  mov     ebx, eax
0x1800069a2  test    eax, eax
0x1800069a4  jns     short loc_1800069CB
0x1800069a6  lea     rcx, [rdi+50h]; void **
0x1800069aa  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x1800069af  lea     rcx, [rdi+48h]; void **
0x1800069b3  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x1800069b8  lea     rcx, [rdi+38h]; void **
0x1800069bc  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x1800069c1  lea     rcx, [rdi+40h]; void **
0x1800069c5  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x1800069ca  nop
0x1800069cb  mov     rcx, [rsp+900h+hMem]; hMem
0x1800069d0  call    cs:__imp_LocalFree
0x1800069d6  nop
0x1800069d7  mov     rcx, [rsp+900h+StringSid]; hMem
0x1800069dc  call    cs:__imp_LocalFree
0x1800069e2  nop
0x1800069e3  mov     rcx, [r14]
0x1800069e6  test    rcx, rcx
0x1800069e9  jz      short loc_1800069F8
0x1800069eb  mov     rax, [rcx]
0x1800069ee  mov     rax, [rax+10h]
0x1800069f2  call    cs:__guard_dispatch_icall_fptr
0x1800069f8  mov     eax, ebx
0x1800069fa  mov     rcx, [rbp+800h+var_30]
0x180006a01  xor     rcx, rsp; StackCookie
0x180006a04  call    __security_check_cookie
0x180006a09  lea     r11, [rsp+900h+var_20]
0x180006a11  mov     rbx, [r11+40h]
0x180006a15  mov     rsi, [r11+48h]
0x180006a19  mov     rsp, r11
0x180006a1c  pop     r15
0x180006a1e  pop     r14
0x180006a20  pop     r12
0x180006a22  pop     rdi
0x180006a23  pop     rbp
0x180006a24  retn
```
