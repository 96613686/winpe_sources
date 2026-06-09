# MsiSIPGetSignedDataMsg(SIP_SUBJECTINFO_ *,ulong *,ulong,ulong *,uchar *)

- ea: `0x180005a30`
- end: `0x180005e97`
- name: `?MsiSIPGetSignedDataMsg@@YAHPEAUSIP_SUBJECTINFO_@@PEAKK1PEAE@Z`
- size: `1127`
- prototype: `__int64 __fastcall(struct SIP_SUBJECTINFO_ *, unsigned int *, int, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003340`
- `0x180005a30`
- `0x18000d2ce`
- `0x18000d300`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005adf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005b1f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005b6f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005ce3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005d69`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005dd7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005adf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005b1f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005b6f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005ce3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005d69`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005dd7`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180005cbd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180005d7c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180005dea`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180005cbd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180005d7c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180005dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005cac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ccf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005dba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005dfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005cac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ccf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005dba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005dfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e5c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180005ac7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180005ac7`

## string_xrefs

- `0x180005ac0`: `ole32.dll`
- `0x180005b65`: `StgOpenStorage`
- `0x180005cd9`: `StgOpenStorage`

## pseudocode

```c
__int64 __fastcall MsiSIPGetSignedDataMsg(
        struct SIP_SUBJECTINFO_ *a1,
        unsigned int *a2,
        int a3,
        unsigned int *a4,
        unsigned __int8 *a5)
{
  DWORD v8; // ecx
  HMODULE LibraryW; // rax
  HMODULE v11; // rsi
  FARPROC ProcAddress; // rax
  int v13; // r14d
  bool v14; // r14
  GUID *pgSubjectType; // rdi
  FARPROC v16; // rax
  unsigned int v17; // r15d
  FARPROC v18; // rax
  LPCWSTR *p_pwsFileName; // rdi
  __int64 v20; // rbx
  __int64 v21; // rdi
  unsigned int v22; // edi
  DWORD LastError; // ebx
  FARPROC v24; // rax
  DWORD v25; // edi
  void (*v26)(void); // rax
  DWORD v27; // ebx
  void (*v28)(void); // rax
  __int64 v29; // [rsp+40h] [rbp-61h] BYREF
  __int64 v30; // [rsp+48h] [rbp-59h]
  int v31; // [rsp+50h] [rbp-51h] BYREF
  __int64 v32; // [rsp+58h] [rbp-49h]
  _BYTE v33[16]; // [rsp+60h] [rbp-41h] BYREF
  unsigned int v34; // [rsp+70h] [rbp-31h]

  v32 = -2;
  if ( !a1 || !a4 || !a2 || a3 || a1->cbSize < 0x58 )
  {
    v8 = 87;
LABEL_7:
    SetLastError(v8);
    return 0;
  }
  LibraryW = LoadLibraryW(L"ole32.dll");
  v11 = LibraryW;
  if ( !LibraryW )
    return 0;
  ProcAddress = GetProcAddress(LibraryW, "CoInitialize");
  if ( !ProcAddress )
  {
LABEL_31:
    LastError = GetLastError();
    FreeLibrary(v11);
    v8 = LastError;
    goto LABEL_7;
  }
  v13 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
  if ( (int)(v13 + 0x80000000) >= 0 && v13 != -2147417850 )
  {
    SetLastError((unsigned __int16)v13);
    goto LABEL_31;
  }
  v14 = v13 >= 0;
  pgSubjectType = a1->pgSubjectType;
  v16 = GetProcAddress(v11, "IsEqualGUID");
  if ( !v16 )
  {
LABEL_51:
    v27 = GetLastError();
    if ( v14 )
    {
      v28 = (void (*)(void))GetProcAddress(v11, "CoUninitialize");
      if ( v28 )
        v28();
    }
    FreeLibrary(v11);
    v8 = v27;
    goto LABEL_7;
  }
  if ( !pgSubjectType || !((unsigned int (__fastcall *)(GUID *, GUID *))v16)(pgSubjectType, &gMSI) )
  {
    SetLastError(0x800B0003);
    goto LABEL_51;
  }
  if ( !a5 )
    *a4 = 0;
  *a2 = 65537;
  v17 = 0;
  v30 = 0;
  v18 = GetProcAddress(v11, "StgOpenStorage");
  p_pwsFileName = &a1->pwsFileName;
  if ( !v18 )
  {
LABEL_33:
    v30 = 0;
    v24 = GetProcAddress(v11, "StgOpenStorage");
    if ( v24 )
    {
      v29 = 0;
      if ( ((int (__fastcall *)(LPCWSTR, _QWORD, __int64, _QWORD, _DWORD, __int64 *))v24)(
             *p_pwsFileName,
             0,
             65600,
             0,
             0,
             &v29) >= 0 )
      {
        v20 = v29;
        if ( v29 )
          goto LABEL_20;
      }
      SetLastError(0xBu);
    }
    v20 = 0;
    v30 = 0;
    goto LABEL_38;
  }
  v29 = 0;
  if ( ((int (__fastcall *)(LPCWSTR, _QWORD, __int64, _QWORD, _DWORD, __int64 *))v18)(*p_pwsFileName, 0, 32, 0, 0, &v29) < 0
    || (v20 = v29) == 0 )
  {
    SetLastError(0xBu);
    goto LABEL_33;
  }
LABEL_20:
  v30 = v20;
  v29 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64 *, _QWORD, __int64, _DWORD, __int64 *))(*(_QWORD *)v20 + 32LL))(
         v20,
         qword_18000F930,
         0,
         16,
         0,
         &v29) >= 0
    && (v21 = v29) != 0 )
  {
    memset_0(v33, 0, 0x50u);
    v17 = 1;
    if ( (*(int (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v21 + 96LL))(v21, v33, 1) < 0 )
    {
      SetLastError(0xBu);
      CComPointer<IStream>::~CComPointer<IStream>(&v29);
      v17 = 0;
    }
    else
    {
      v22 = v34;
      if ( !a5 )
      {
        *a4 = v34;
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        goto LABEL_49;
      }
      if ( *a4 < v34 )
      {
        *a4 = v34;
        SetLastError(0x7Au);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        v17 = 0;
      }
      else
      {
        v31 = 0;
        if ( (*(int (__fastcall **)(__int64, unsigned __int8 *, _QWORD, int *))(*(_QWORD *)v29 + 24LL))(
               v29,
               a5,
               v34,
               &v31) >= 0
          && v22 == v31 )
        {
          CComPointer<IStream>::~CComPointer<IStream>(&v29);
LABEL_49:
          v25 = 0;
          goto LABEL_39;
        }
        SetLastError(0xBu);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        v17 = 0;
      }
    }
  }
  else
  {
    SetLastError(0xBu);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
LABEL_38:
  v25 = GetLastError();
LABEL_39:
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v30 = 0;
  if ( v14 )
  {
    v26 = (void (*)(void))GetProcAddress(v11, "CoUninitialize");
    if ( v26 )
      v26();
  }
  FreeLibrary(v11);
  if ( v25 )
    SetLastError(v25);
  return v17;
}

```

## disassembly

```asm
0x180005a30  push    rbp
0x180005a32  push    rsi
0x180005a33  push    rdi
0x180005a34  push    r12
0x180005a36  push    r13
0x180005a38  push    r14
0x180005a3a  push    r15
0x180005a3c  lea     rbp, [rsp-1Fh]
0x180005a41  sub     rsp, 0C0h
0x180005a48  mov     [rbp+4Fh+var_98], 0FFFFFFFFFFFFFFFEh
0x180005a50  mov     [rsp+0F0h+arg_10], rbx
0x180005a58  mov     rax, cs:__security_cookie
0x180005a5f  xor     rax, rsp
0x180005a62  mov     [rbp+4Fh+var_40], rax
0x180005a66  mov     r12, r9
0x180005a69  mov     r15, rdx
0x180005a6c  mov     rbx, rcx
0x180005a6f  mov     r13, [rbp+4Fh+arg_20]
0x180005a73  test    rcx, rcx
0x180005a76  jz      short loc_180005A8C
0x180005a78  test    r9, r9
0x180005a7b  jz      short loc_180005A8C
0x180005a7d  test    rdx, rdx
0x180005a80  jz      short loc_180005A8C
0x180005a82  test    r8d, r8d
0x180005a85  jnz     short loc_180005A8C
0x180005a87  cmp     dword ptr [rcx], 58h ; 'X'
0x180005a8a  jnb     short loc_180005AC0
0x180005a8c  mov     ecx, 57h ; 'W'; dwErrCode
0x180005a91  call    cs:__imp_SetLastError
0x180005a97  xor     eax, eax
0x180005a99  mov     rcx, [rbp+4Fh+var_40]
0x180005a9d  xor     rcx, rsp; StackCookie
0x180005aa0  call    __security_check_cookie
0x180005aa5  mov     rbx, [rsp+0F0h+arg_10]
0x180005aad  add     rsp, 0C0h
0x180005ab4  pop     r15
0x180005ab6  pop     r14
0x180005ab8  pop     r13
0x180005aba  pop     r12
0x180005abc  pop     rdi
0x180005abd  pop     rsi
0x180005abe  pop     rbp
0x180005abf  retn
0x180005ac0  lea     rcx, LibFileName; "ole32.dll"
0x180005ac7  call    cs:__imp_LoadLibraryW
0x180005acd  mov     rsi, rax
0x180005ad0  test    rax, rax
0x180005ad3  jz      short loc_180005A97
0x180005ad5  lea     rdx, aCoinitialize; "CoInitialize"
0x180005adc  mov     rcx, rax; hModule
0x180005adf  call    cs:__imp_GetProcAddress
0x180005ae5  test    rax, rax
0x180005ae8  jz      loc_180005CB2
0x180005aee  xor     ecx, ecx
0x180005af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af5  mov     r14d, eax
0x180005af8  mov     eax, 80000000h
0x180005afd  lea     ecx, [r14+rax]
0x180005b01  test    eax, ecx
0x180005b03  jz      loc_180005C9B
0x180005b09  shr     r14d, 1Fh
0x180005b0d  xor     r14b, 1
0x180005b11  mov     rdi, [rbx+8]
0x180005b15  lea     rdx, aIsequalguid; "IsEqualGUID"
0x180005b1c  mov     rcx, rsi; hModule
0x180005b1f  call    cs:__imp_GetProcAddress
0x180005b25  test    rax, rax
0x180005b28  jz      loc_180005DC0
0x180005b2e  test    rdi, rdi
0x180005b31  jz      loc_180005DB5
0x180005b37  lea     rdx, ?gMSI@@3U_GUID@@A; _GUID gMSI
0x180005b3e  mov     rcx, rdi
0x180005b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b46  test    eax, eax
0x180005b48  jz      loc_180005DB5
0x180005b4e  test    r13, r13
0x180005b51  jnz     short loc_180005B57
0x180005b53  mov     [r12], r13d
0x180005b57  mov     dword ptr [r15], 10001h
0x180005b5e  xor     r15d, r15d
0x180005b61  mov     [rbp+4Fh+var_A8], r15
0x180005b65  lea     rdx, aStgopenstorage; "StgOpenStorage"
0x180005b6c  mov     rcx, rsi; hModule
0x180005b6f  call    cs:__imp_GetProcAddress
0x180005b75  lea     rdi, [rbx+18h]
0x180005b79  test    rax, rax
0x180005b7c  jz      loc_180005CD5
0x180005b82  mov     [rbp+4Fh+var_B0], r15
0x180005b86  lea     rcx, [rbp+4Fh+var_B0]
0x180005b8a  mov     [rsp+0F0h+var_C8], rcx
0x180005b8f  mov     [rsp+0F0h+var_D0], r15d
0x180005b94  xor     r9d, r9d
0x180005b97  xor     edx, edx
0x180005b99  mov     r8d, 20h ; ' '
0x180005b9f  mov     rcx, [rdi]
0x180005ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ba7  test    eax, eax
0x180005ba9  js      loc_180005CCA
0x180005baf  mov     rbx, [rbp+4Fh+var_B0]
0x180005bb3  test    rbx, rbx
0x180005bb6  jz      loc_180005CCA
0x180005bbc  mov     [rbp+4Fh+var_A8], rbx
0x180005bc0  mov     [rbp+4Fh+var_B0], r15
0x180005bc4  mov     rax, [rbx]
0x180005bc7  lea     rcx, [rbp+4Fh+var_B0]
0x180005bcb  mov     [rsp+0F0h+var_C8], rcx
0x180005bd0  mov     [rsp+0F0h+var_D0], r15d
0x180005bd5  mov     r9d, 10h
0x180005bdb  xor     r8d, r8d
0x180005bde  lea     rdx, qword_18000F930
0x180005be5  mov     rcx, rbx
0x180005be8  mov     rax, [rax+20h]
0x180005bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf1  test    eax, eax
0x180005bf3  js      loc_180005DF7
0x180005bf9  mov     rdi, [rbp+4Fh+var_B0]
0x180005bfd  test    rdi, rdi
0x180005c00  jz      loc_180005DF7
0x180005c06  xor     edx, edx; Val
0x180005c08  mov     r8d, 50h ; 'P'; Size
0x180005c0e  lea     rcx, [rbp+4Fh+var_90]; void *
0x180005c12  call    memset_0
0x180005c17  mov     rax, [rdi]
0x180005c1a  mov     r15d, 1
0x180005c20  mov     r8d, r15d
0x180005c23  lea     rdx, [rbp+4Fh+var_90]
0x180005c27  mov     rcx, rdi
0x180005c2a  mov     rax, [rax+60h]
0x180005c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c33  test    eax, eax
0x180005c35  js      loc_180005E57
0x180005c3b  mov     edi, [rbp+4Fh+var_80]
0x180005c3e  test    r13, r13
0x180005c41  jz      loc_180005D97
0x180005c47  cmp     [r12], edi
0x180005c4b  jb      loc_180005E11
0x180005c51  mov     [rbp+4Fh+var_A0], 0
0x180005c58  mov     rcx, [rbp+4Fh+var_B0]
0x180005c5c  mov     rax, [rcx]
0x180005c5f  lea     r9, [rbp+4Fh+var_A0]
0x180005c63  mov     r8d, edi
0x180005c66  mov     rdx, r13
0x180005c69  mov     rax, [rax+18h]
0x180005c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c72  test    eax, eax
0x180005c74  jns     loc_180005E32
0x180005c7a  mov     ecx, 0Bh; dwErrCode
0x180005c7f  call    cs:__imp_SetLastError
0x180005c85  nop
0x180005c86  mov     rcx, [rbp+4Fh+var_B0]
0x180005c8a  test    rcx, rcx
0x180005c8d  jnz     loc_180005E74
0x180005c93  xor     r15d, r15d
0x180005c96  jmp     loc_180005D36
0x180005c9b  cmp     r14d, 80010106h
0x180005ca2  jz      loc_180005B09
0x180005ca8  movzx   ecx, r14w; dwErrCode
0x180005cac  call    cs:__imp_SetLastError
0x180005cb2  call    cs:__imp_GetLastError
0x180005cb8  mov     ebx, eax
0x180005cba  mov     rcx, rsi; hLibModule
0x180005cbd  call    cs:__imp_FreeLibrary
0x180005cc3  mov     ecx, ebx
0x180005cc5  jmp     loc_180005A91
0x180005cca  mov     ecx, 0Bh; dwErrCode
0x180005ccf  call    cs:__imp_SetLastError
0x180005cd5  mov     [rbp+4Fh+var_A8], r15
0x180005cd9  lea     rdx, aStgopenstorage; "StgOpenStorage"
0x180005ce0  mov     rcx, rsi; hModule
0x180005ce3  call    cs:__imp_GetProcAddress
0x180005ce9  test    rax, rax
0x180005cec  jz      short loc_180005D2F
0x180005cee  mov     [rbp+4Fh+var_B0], r15
0x180005cf2  lea     rcx, [rbp+4Fh+var_B0]
0x180005cf6  mov     [rsp+0F0h+var_C8], rcx
0x180005cfb  mov     [rsp+0F0h+var_D0], r15d
0x180005d00  xor     r9d, r9d
0x180005d03  xor     edx, edx
0x180005d05  mov     r8d, 10040h
0x180005d0b  mov     rcx, [rdi]
0x180005d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d13  test    eax, eax
0x180005d15  js      short loc_180005D24
0x180005d17  mov     rbx, [rbp+4Fh+var_B0]
0x180005d1b  test    rbx, rbx
0x180005d1e  jnz     loc_180005BBC
0x180005d24  mov     ecx, 0Bh; dwErrCode
0x180005d29  call    cs:__imp_SetLastError
0x180005d2f  mov     rbx, r15
0x180005d32  mov     [rbp+4Fh+var_A8], rbx
0x180005d36  call    cs:__imp_GetLastError
0x180005d3c  mov     edi, eax
0x180005d3e  test    rbx, rbx
0x180005d41  jz      short loc_180005D52
0x180005d43  mov     rcx, [rbx]
0x180005d46  mov     rax, [rcx+10h]
0x180005d4a  mov     rcx, rbx
0x180005d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d52  mov     [rbp+4Fh+var_A8], 0
0x180005d5a  test    r14b, r14b
0x180005d5d  jz      short loc_180005D79
0x180005d5f  lea     rdx, ProcName; "CoUninitialize"
0x180005d66  mov     rcx, rsi; hModule
0x180005d69  call    cs:__imp_GetProcAddress
0x180005d6f  test    rax, rax
0x180005d72  jz      short loc_180005D79
0x180005d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d79  mov     rcx, rsi; hLibModule
0x180005d7c  call    cs:__imp_FreeLibrary
0x180005d82  test    edi, edi
0x180005d84  jz      short loc_180005D8F
0x180005d86  mov     ecx, edi; dwErrCode
0x180005d88  call    cs:__imp_SetLastError
0x180005d8e  nop
0x180005d8f  mov     eax, r15d
0x180005d92  jmp     loc_180005A99
0x180005d97  mov     [r12], edi
0x180005d9b  mov     rcx, [rbp+4Fh+var_B0]
0x180005d9f  test    rcx, rcx
0x180005da2  jz      short loc_180005DB1
0x180005da4  mov     rax, [rcx]
0x180005da7  mov     rax, [rax+10h]
0x180005dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db0  nop
0x180005db1  xor     edi, edi
0x180005db3  jmp     short loc_180005D3E
0x180005db5  mov     ecx, 800B0003h; dwErrCode
0x180005dba  call    cs:__imp_SetLastError
0x180005dc0  call    cs:__imp_GetLastError
0x180005dc6  mov     ebx, eax
0x180005dc8  test    r14b, r14b
0x180005dcb  jz      short loc_180005DE7
0x180005dcd  lea     rdx, ProcName; "CoUninitialize"
0x180005dd4  mov     rcx, rsi; hModule
0x180005dd7  call    cs:__imp_GetProcAddress
0x180005ddd  test    rax, rax
0x180005de0  jz      short loc_180005DE7
0x180005de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de7  mov     rcx, rsi; hLibModule
0x180005dea  call    cs:__imp_FreeLibrary
0x180005df0  mov     ecx, ebx
0x180005df2  jmp     loc_180005A91
0x180005df7  mov     ecx, 0Bh; dwErrCode
0x180005dfc  call    cs:__imp_SetLastError
0x180005e02  nop
0x180005e03  mov     rcx, [rbp+4Fh+var_B0]
0x180005e07  test    rcx, rcx
0x180005e0a  jnz     short loc_180005E85
0x180005e0c  jmp     loc_180005D36
0x180005e11  mov     [r12], edi
0x180005e15  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180005e1a  call    cs:__imp_SetLastError
0x180005e20  nop
0x180005e21  mov     rcx, [rbp+4Fh+var_B0]
0x180005e25  test    rcx, rcx
0x180005e28  jnz     short loc_180005E49
0x180005e2a  xor     r15d, r15d
0x180005e2d  jmp     loc_180005D36
0x180005e32  cmp     edi, [rbp+4Fh+var_A0]
0x180005e35  jnz     loc_180005C7A
0x180005e3b  lea     rcx, [rbp+4Fh+var_B0]
0x180005e3f  call    ??1?$CComPointer@UIStream@@@@QEAA@XZ; CComPointer<IStream>::~CComPointer<IStream>(void)
0x180005e44  jmp     loc_180005DB1
0x180005e49  mov     rax, [rcx]
0x180005e4c  mov     rax, [rax+10h]
0x180005e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e55  jmp     short loc_180005E2A
0x180005e57  mov     ecx, 0Bh; dwErrCode
0x180005e5c  call    cs:__imp_SetLastError
0x180005e62  nop
0x180005e63  lea     rcx, [rbp+4Fh+var_B0]
0x180005e67  call    ??1?$CComPointer@UIStream@@@@QEAA@XZ; CComPointer<IStream>::~CComPointer<IStream>(void)
0x180005e6c  xor     r15d, r15d
0x180005e6f  jmp     loc_180005D36
0x180005e74  mov     rax, [rcx]
0x180005e77  mov     rax, [rax+10h]
0x180005e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e80  jmp     loc_180005C93
0x180005e85  mov     rax, [rcx]
0x180005e88  mov     rax, [rax+10h]
0x180005e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e91  jmp     loc_180005E0C
```
