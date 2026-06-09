# _bidLdrReadProfile

- ea: `0x180019808`
- end: `0x180019ad6`
- name: `_bidLdrReadProfile`
- size: `718`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a03c`

## callees

- `0x180001838`
- `0x180018cfc`
- `0x1800196ec`
- `0x180019808`
- `0x180019adc`
- `0x18002e060`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800198a4`
- `msvcrt!wcsncpy_s` at `0x1800199f2`
- `msvcrt!wcsncpy_s` at `0x1800198a4`
- `msvcrt!wcsncpy_s` at `0x1800199f2`
- `KERNEL32!OutputDebugStringW` at `0x180019a52`
- `KERNEL32!OutputDebugStringW` at `0x180019a5d`
- `KERNEL32!OutputDebugStringW` at `0x180019a6a`
- `KERNEL32!OutputDebugStringW` at `0x180019a75`
- `KERNEL32!OutputDebugStringW` at `0x180019a82`
- `KERNEL32!OutputDebugStringW` at `0x180019a8b`
- `KERNEL32!OutputDebugStringW` at `0x180019a98`
- `KERNEL32!OutputDebugStringW` at `0x180019a52`
- `KERNEL32!OutputDebugStringW` at `0x180019a5d`
- `KERNEL32!OutputDebugStringW` at `0x180019a6a`
- `KERNEL32!OutputDebugStringW` at `0x180019a75`
- `KERNEL32!OutputDebugStringW` at `0x180019a82`
- `KERNEL32!OutputDebugStringW` at `0x180019a8b`
- `KERNEL32!OutputDebugStringW` at `0x180019a98`
- `ADVAPI32!RegOpenKeyExW` at `0x18001988b`
- `ADVAPI32!RegOpenKeyExW` at `0x18001988b`
- `ADVAPI32!RegQueryValueExW` at `0x1800198fc`
- `ADVAPI32!RegQueryValueExW` at `0x1800198fc`
- `ADVAPI32!RegCloseKey` at `0x1800199fd`
- `ADVAPI32!RegCloseKey` at `0x180019a1c`
- `ADVAPI32!RegCloseKey` at `0x1800199fd`
- `ADVAPI32!RegCloseKey` at `0x180019a1c`

## string_xrefs

- `0x1800199bf`: `:Path`

## pseudocode

```c
__int64 __fastcall bidLdrReadProfile(wchar_t *lpRootPathName, __int64 a2, __int64 a3, _DWORD *a4)
{
  int IsPathLocal; // eax
  int v7; // ecx
  unsigned int v8; // edi
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpOutputString; // [rsp+40h] [rbp-C0h]
  LPCWSTR v16; // [rsp+48h] [rbp-B8h]
  wchar_t *v17; // [rsp+50h] [rbp-B0h]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  WCHAR Filename[280]; // [rsp+80h] [rbp-80h] BYREF

  v17 = lpRootPathName;
  *lpRootPathName = 0;
  v19 = 0;
  hKey = 0;
  v18 = 538;
  lpOutputString = L"SOFTWARE\\Microsoft\\BidInterface\\Loader";
  v16 = L"<NotFound>";
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\BidInterface\\Loader", 0, 0x20019u, &hKey) )
  {
    wcsncpy_s(lpRootPathName, 0x10Du, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
    IsPathLocal = 0;
    v7 = 0;
    v8 = 0;
    goto LABEL_21;
  }
  v22 = 0;
  v21 = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  v8 = 1;
  if ( RegQueryValueExW(hKey, L":LdrMsg", 0, &Type, Data, &cbData) || Type != 4 || (LODWORD(v19) = 1, !*(_DWORD *)Data) )
    LODWORD(v19) = 0;
  if ( !(unsigned int)BuildApplicationPid(Filename) )
    goto LABEL_14;
  v16 = Filename;
  if ( (unsigned int)bidLdrReadStr(&hKey) )
    goto LABEL_17;
  if ( (unsigned __int64)(2 * v21) >= 0x224 )
    goto LABEL_16;
  Filename[v21] = 0;
  if ( (unsigned int)bidLdrReadStr(&hKey) )
    goto LABEL_17;
  v9 = v22;
  if ( !v22 )
    goto LABEL_14;
  Filename[v22] = 42;
  v10 = 2 * v9 + 2;
  if ( v10 >= 0x224 )
LABEL_16:
    _report_rangecheckfailure();
  *(WCHAR *)((char *)Filename + v10) = 0;
  if ( (unsigned int)bidLdrReadStr(&hKey) )
    goto LABEL_17;
LABEL_14:
  v16 = L":Path";
  if ( (unsigned int)bidLdrReadStr(&hKey) )
  {
LABEL_17:
    RegCloseKey(hKey);
    IsPathLocal = HIDWORD(v18);
    hKey = 0;
    lpRootPathName[269] = 0;
    if ( IsPathLocal )
    {
      IsPathLocal = bidLdrIsPathLocal(lpRootPathName);
      HIDWORD(v18) = IsPathLocal;
    }
    goto LABEL_19;
  }
  v16 = L"<NotFound>";
  HIDWORD(v18) = 0;
  wcsncpy_s(lpRootPathName, 0x10Du, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
  RegCloseKey(hKey);
  IsPathLocal = HIDWORD(v18);
  v8 = 0;
  hKey = 0;
LABEL_19:
  v7 = v19;
  if ( (_DWORD)v19 )
  {
    OutputDebugStringW(L"*** [HKLM\\");
    OutputDebugStringW(lpOutputString);
    OutputDebugStringW(L"\\\"");
    OutputDebugStringW(v16);
    OutputDebugStringW(L"\"] \n*** \"");
    OutputDebugStringW(lpRootPathName);
    OutputDebugStringW(L"\"\n");
    v7 = v19;
    IsPathLocal = HIDWORD(v18);
  }
LABEL_21:
  *a4 = v7;
  dword_180045794 = IsPathLocal;
  return v8;
}

```

## disassembly

```asm
0x180019808  mov     [rsp-8+arg_8], rbx
0x18001980d  push    rbp
0x18001980e  push    rsi
0x18001980f  push    rdi
0x180019810  push    r12
0x180019812  push    r14
0x180019814  lea     rbp, [rsp-1C0h]
0x18001981c  sub     rsp, 2C0h
0x180019823  mov     rax, cs:__security_cookie
0x18001982a  xor     rax, rsp
0x18001982d  mov     [rbp+1E0h+var_30], rax
0x180019834  xor     r14d, r14d
0x180019837  mov     [rsp+2E0h+var_290], rcx
0x18001983c  mov     [rcx], r14w
0x180019840  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x180019847  mov     rsi, r9
0x18001984a  mov     [rsp+2E0h+var_280], r14
0x18001984f  mov     rbx, rcx
0x180019852  mov     [rsp+2E0h+hKey], r14
0x180019857  lea     rax, [rsp+2E0h+hKey]
0x18001985c  mov     [rsp+2E0h+var_288], 21Ah
0x180019865  lea     r12, aNotfound; "<NotFound>"
0x18001986c  mov     [rsp+2E0h+lpOutputString], rdx
0x180019871  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019878  mov     [rsp+2E0h+var_298], r12
0x18001987d  mov     r9d, 20019h; samDesired
0x180019883  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180019888  xor     r8d, r8d; ulOptions
0x18001988b  call    cs:__imp_RegOpenKeyExW
0x180019891  test    eax, eax
0x180019893  jz      short loc_1800198B8
0x180019895  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019899  mov     r8, r12; Source
0x18001989c  mov     edx, 10Dh; SizeInWords
0x1800198a1  mov     rcx, rbx; Destination
0x1800198a4  call    cs:__imp_wcsncpy_s
0x1800198aa  mov     eax, r14d
0x1800198ad  mov     ecx, r14d
0x1800198b0  mov     edi, r14d
0x1800198b3  jmp     loc_180019AA6
0x1800198b8  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800198bd  lea     rax, [rsp+2E0h+cbData]
0x1800198c2  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800198c7  lea     r9, [rsp+2E0h+Type]; lpType
0x1800198cc  lea     rax, [rsp+2E0h+Data]
0x1800198d1  mov     [rsp+2E0h+var_268], r14
0x1800198d6  xor     r8d, r8d; lpReserved
0x1800198d9  mov     [rsp+2E0h+phkResult], rax; lpData
0x1800198de  lea     rdx, ValueName; ":LdrMsg"
0x1800198e5  mov     [rsp+2E0h+var_270], r14
0x1800198ea  mov     dword ptr [rsp+2E0h+Data], r14d
0x1800198ef  mov     [rsp+2E0h+cbData], 4
0x1800198f7  mov     [rsp+2E0h+Type], r14d
0x1800198fc  call    cs:__imp_RegQueryValueExW
0x180019902  mov     edi, 1
0x180019907  test    eax, eax
0x180019909  jnz     short loc_18001991D
0x18001990b  cmp     [rsp+2E0h+Type], 4
0x180019910  jnz     short loc_18001991D
0x180019912  mov     dword ptr [rsp+2E0h+var_280], edi
0x180019916  cmp     dword ptr [rsp+2E0h+Data], r14d
0x18001991b  jnz     short loc_180019922
0x18001991d  mov     dword ptr [rsp+2E0h+var_280], r14d
0x180019922  lea     r9, [rsp+2E0h+var_270]
0x180019927  lea     r8, [rsp+2E0h+var_268]
0x18001992c  lea     rcx, [rbp+1E0h+Filename]; lpFilename
0x180019930  call    BuildApplicationPid
0x180019935  test    eax, eax
0x180019937  jz      loc_1800199BF
0x18001993d  lea     rax, [rbp+1E0h+Filename]
0x180019941  lea     rcx, [rsp+2E0h+hKey]
0x180019946  mov     [rsp+2E0h+var_298], rax
0x18001994b  call    _bidLdrReadStr
0x180019950  test    eax, eax
0x180019952  jnz     loc_180019A17
0x180019958  mov     rax, [rsp+2E0h+var_270]
0x18001995d  lea     rcx, [rax+rax]
0x180019961  cmp     rcx, 224h
0x180019968  jnb     loc_180019A11
0x18001996e  mov     [rbp+rcx+1E0h+Filename], r14w
0x180019974  lea     rcx, [rsp+2E0h+hKey]
0x180019979  call    _bidLdrReadStr
0x18001997e  test    eax, eax
0x180019980  jnz     loc_180019A17
0x180019986  mov     rax, [rsp+2E0h+var_268]
0x18001998b  test    rax, rax
0x18001998e  jz      short loc_1800199BF
0x180019990  mov     ecx, 2Ah ; '*'
0x180019995  mov     [rbp+rax*2+1E0h+Filename], cx
0x18001999a  lea     rcx, ds:2[rax*2]
0x1800199a2  cmp     rcx, 224h
0x1800199a9  jnb     short loc_180019A11
0x1800199ab  mov     [rbp+rcx+1E0h+Filename], r14w
0x1800199b1  lea     rcx, [rsp+2E0h+hKey]
0x1800199b6  call    _bidLdrReadStr
0x1800199bb  test    eax, eax
0x1800199bd  jnz     short loc_180019A17
0x1800199bf  lea     rax, aPath; ":Path"
0x1800199c6  lea     rcx, [rsp+2E0h+hKey]
0x1800199cb  mov     [rsp+2E0h+var_298], rax
0x1800199d0  call    _bidLdrReadStr
0x1800199d5  test    eax, eax
0x1800199d7  jnz     short loc_180019A17
0x1800199d9  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800199dd  mov     [rsp+2E0h+var_298], r12
0x1800199e2  mov     r8, r12; Source
0x1800199e5  mov     dword ptr [rsp+2E0h+var_288+4], r14d
0x1800199ea  mov     edx, 10Dh; SizeInWords
0x1800199ef  mov     rcx, rbx; Destination
0x1800199f2  call    cs:__imp_wcsncpy_s
0x1800199f8  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800199fd  call    cs:__imp_RegCloseKey
0x180019a03  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x180019a07  mov     edi, r14d
0x180019a0a  mov     [rsp+2E0h+hKey], r14
0x180019a0f  jmp     short loc_180019A43
0x180019a11  call    __report_rangecheckfailure
0x180019a17  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180019a1c  call    cs:__imp_RegCloseKey
0x180019a22  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x180019a26  mov     [rsp+2E0h+hKey], r14
0x180019a2b  mov     [rbx+21Ah], r14w
0x180019a33  test    eax, eax
0x180019a35  jz      short loc_180019A43
0x180019a37  mov     rcx, rbx; lpRootPathName
0x180019a3a  call    _bidLdrIsPathLocal
0x180019a3f  mov     dword ptr [rsp+2E0h+var_288+4], eax
0x180019a43  mov     ecx, dword ptr [rsp+2E0h+var_280]
0x180019a47  test    ecx, ecx
0x180019a49  jz      short loc_180019AA6
0x180019a4b  lea     rcx, OutputString; "*** [HKLM\\"
0x180019a52  call    cs:__imp_OutputDebugStringW
0x180019a58  mov     rcx, [rsp+2E0h+lpOutputString]; lpOutputString
0x180019a5d  call    cs:__imp_OutputDebugStringW
0x180019a63  lea     rcx, asc_180039448; "\\\""
0x180019a6a  call    cs:__imp_OutputDebugStringW
0x180019a70  mov     rcx, [rsp+2E0h+var_298]; lpOutputString
0x180019a75  call    cs:__imp_OutputDebugStringW
0x180019a7b  lea     rcx, asc_180039450; "\"] \n*** \""
0x180019a82  call    cs:__imp_OutputDebugStringW
0x180019a88  mov     rcx, rbx; lpOutputString
0x180019a8b  call    cs:__imp_OutputDebugStringW
0x180019a91  lea     rcx, asc_180039464; "\"\n"
0x180019a98  call    cs:__imp_OutputDebugStringW
0x180019a9e  mov     ecx, dword ptr [rsp+2E0h+var_280]
0x180019aa2  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x180019aa6  mov     [rsi], ecx
0x180019aa8  mov     cs:dword_180045794, eax
0x180019aae  mov     eax, edi
0x180019ab0  mov     rcx, [rbp+1E0h+var_30]
0x180019ab7  xor     rcx, rsp; StackCookie
0x180019aba  call    __security_check_cookie
0x180019abf  mov     rbx, [rsp+2E0h+arg_8]
0x180019ac7  add     rsp, 2C0h
0x180019ace  pop     r14
0x180019ad0  pop     r12
0x180019ad2  pop     rdi
0x180019ad3  pop     rsi
0x180019ad4  pop     rbp
0x180019ad5  retn
```
