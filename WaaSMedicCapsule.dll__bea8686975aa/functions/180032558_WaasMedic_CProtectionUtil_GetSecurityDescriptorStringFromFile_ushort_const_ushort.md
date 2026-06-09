# WaasMedic::CProtectionUtil::GetSecurityDescriptorStringFromFile(ushort const *,ushort * *)

- ea: `0x180032558`
- end: `0x180032766`
- name: `?GetSecurityDescriptorStringFromFile@CProtectionUtil@WaasMedic@@SAJPEBGPEAPEAG@Z`
- size: `526`
- prototype: `__int64 __fastcall(LPCWSTR pObjectName, LPWSTR *StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005b214`

## callees

- `0x18002543c`
- `0x180032558`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800325be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003261e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003267f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800325be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003261e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003267f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032631`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032631`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800326b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032714`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800326b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032714`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800325af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800325af`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180032675`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180032675`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800325f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032629`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032723`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032747`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800325f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032629`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032723`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032747`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800326e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800326e4`

## string_xrefs

- `0x18003272d`: `GetSecurityDescriptorStringFromFile requries file name and pointer to SDDL string.`
- `0x180032694`: `GetNamedSecurityInfo failed wih error: 0x%08x`
- `0x1800325d6`: `CreateFile failed wih error: 0x%08x`
- `0x180032703`: `GetSecurityInfo failed wih error: 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::CProtectionUtil::GetSecurityDescriptorStringFromFile(
        LPCWSTR pObjectName,
        LPWSTR *StringSecurityDescriptor)
{
  HANDLE FileW; // rbx
  signed int LastError; // eax
  unsigned int v6; // ebx
  HLOCAL v8; // r14
  DWORD v9; // edi
  signed int v10; // eax
  unsigned int v11; // edi
  signed int v12; // eax
  PSID ppsidOwner; // [rsp+40h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+30h] BYREF
  PACL ppDacl; // [rsp+90h] [rbp+40h] BYREF
  PSID ppsidGroup; // [rsp+98h] [rbp+48h] BYREF

  hMem = 0;
  if ( pObjectName && StringSecurityDescriptor )
  {
    FileW = CreateFileW(pObjectName, 0x1020000u, 1u, 0, 3u, 0x2000080u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(2u, L"CreateFile failed wih error: 0x%08x", v6);
      if ( hMem )
        LocalFree(hMem);
      return v6;
    }
    v8 = hMem;
    ppDacl = 0;
    ppsidOwner = 0;
    ppsidGroup = 0;
    if ( hMem )
    {
      v9 = GetLastError();
      LocalFree(v8);
      SetLastError(v9);
    }
    hMem = 0;
    if ( GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 7u, &ppsidOwner, &ppsidGroup, &ppDacl, 0, &hMem) )
    {
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      LogLevelW(2u, L"GetNamedSecurityInfo failed wih error: 0x%08x", v11);
LABEL_15:
      if ( FileW )
        CloseHandle(FileW);
      if ( hMem )
        LocalFree(hMem);
      return v11;
    }
    if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(hMem, 1u, 7u, StringSecurityDescriptor, 0) )
    {
      v12 = GetLastError();
      v11 = v12;
      if ( v12 > 0 )
        v11 = (unsigned __int16)v12 | 0x80070000;
      LogLevelW(2u, L"GetSecurityInfo failed wih error: 0x%08x", v11);
      goto LABEL_15;
    }
    if ( FileW )
      CloseHandle(FileW);
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
  else
  {
    LogLevelW(2u, L"GetSecurityDescriptorStringFromFile requries file name and pointer to SDDL string.");
    if ( hMem )
      LocalFree(hMem);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180032558  mov     rax, rsp
0x18003255b  mov     [rax+10h], rbx
0x18003255f  push    rbp
0x180032560  push    rsi
0x180032561  push    rdi
0x180032562  push    r14
0x180032564  push    r15
0x180032566  mov     rbp, rsp
0x180032569  sub     rsp, 50h
0x18003256d  mov     [rbp+hMem], 0
0x180032575  mov     r15, rdx
0x180032578  mov     rsi, rcx
0x18003257b  test    rcx, rcx
0x18003257e  jz      loc_18003272D
0x180032584  test    rdx, rdx
0x180032587  jz      loc_18003272D
0x18003258d  mov     qword ptr [rax-48h], 0
0x180032595  xor     r9d, r9d; lpSecurityAttributes
0x180032598  mov     dword ptr [rax-50h], 2000080h
0x18003259f  mov     edx, 1020000h; dwDesiredAccess
0x1800325a4  mov     dword ptr [rax-58h], 3
0x1800325ab  lea     r8d, [r9+1]; dwShareMode
0x1800325af  call    cs:__imp_CreateFileW
0x1800325b5  mov     rbx, rax
0x1800325b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800325bc  jnz     short loc_1800325FD
0x1800325be  call    cs:__imp_GetLastError
0x1800325c4  mov     ebx, eax
0x1800325c6  test    eax, eax
0x1800325c8  jle     short loc_1800325D3
0x1800325ca  movzx   ebx, ax
0x1800325cd  or      ebx, 80070000h
0x1800325d3  mov     r8d, ebx
0x1800325d6  lea     rdx, aCreatefileFail; "CreateFile failed wih error: 0x%08x"
0x1800325dd  mov     ecx, 2; unsigned __int8
0x1800325e2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800325e7  mov     rcx, [rbp+hMem]; hMem
0x1800325eb  test    rcx, rcx
0x1800325ee  jz      short loc_1800325F6
0x1800325f0  call    cs:__imp_LocalFree
0x1800325f6  mov     eax, ebx
0x1800325f8  jmp     loc_180032752
0x1800325fd  mov     r14, [rbp+hMem]
0x180032601  mov     [rbp+arg_10], 0
0x180032609  mov     [rbp+ppsidOwner], 0
0x180032611  mov     [rbp+arg_18], 0
0x180032619  test    r14, r14
0x18003261c  jz      short loc_180032637
0x18003261e  call    cs:__imp_GetLastError
0x180032624  mov     rcx, r14; hMem
0x180032627  mov     edi, eax
0x180032629  call    cs:__imp_LocalFree
0x18003262f  mov     ecx, edi; dwErrCode
0x180032631  call    cs:__imp_SetLastError
0x180032637  lea     rax, [rbp+hMem]
0x18003263b  mov     [rbp+hMem], 0
0x180032643  mov     [rsp+50h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180032648  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x18003264c  mov     edi, 7
0x180032651  mov     [rsp+50h+ppSacl], 0; ppSacl
0x18003265a  lea     rax, [rbp+arg_10]
0x18003265e  mov     r8d, edi; SecurityInfo
0x180032661  mov     [rsp+50h+ppDacl], rax; ppDacl
0x180032666  mov     rcx, rsi; pObjectName
0x180032669  lea     rax, [rbp+arg_18]
0x18003266d  lea     edx, [rdi-6]; ObjectType
0x180032670  mov     [rsp+50h+ppsidGroup], rax; ppsidGroup
0x180032675  call    cs:__imp_GetNamedSecurityInfoW
0x18003267b  test    eax, eax
0x18003267d  jz      short loc_1800326CC
0x18003267f  call    cs:__imp_GetLastError
0x180032685  mov     edi, eax
0x180032687  test    eax, eax
0x180032689  jle     short loc_180032694
0x18003268b  movzx   edi, ax
0x18003268e  or      edi, 80070000h
0x180032694  lea     rdx, aGetnamedsecuri; "GetNamedSecurityInfo failed wih error: "...
0x18003269b  mov     r8d, edi
0x18003269e  mov     ecx, 2; unsigned __int8
0x1800326a3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800326a8  test    rbx, rbx
0x1800326ab  jz      short loc_1800326B6
0x1800326ad  mov     rcx, rbx; hObject
0x1800326b0  call    cs:__imp_CloseHandle
0x1800326b6  mov     rcx, [rbp+hMem]; hMem
0x1800326ba  test    rcx, rcx
0x1800326bd  jz      short loc_1800326C5
0x1800326bf  call    cs:__imp_LocalFree
0x1800326c5  mov     eax, edi
0x1800326c7  jmp     loc_180032752
0x1800326cc  mov     rcx, [rbp+hMem]; SecurityDescriptor
0x1800326d0  mov     r9, r15; StringSecurityDescriptor
0x1800326d3  mov     r8d, edi; SecurityInformation
0x1800326d6  mov     [rsp+50h+ppsidGroup], 0; StringSecurityDescriptorLen
0x1800326df  mov     edx, 1; RequestedStringSDRevision
0x1800326e4  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800326ea  test    eax, eax
0x1800326ec  jnz     short loc_18003270C
0x1800326ee  call    cs:__imp_GetLastError
0x1800326f4  mov     edi, eax
0x1800326f6  test    eax, eax
0x1800326f8  jle     short loc_180032703
0x1800326fa  movzx   edi, ax
0x1800326fd  or      edi, 80070000h
0x180032703  lea     rdx, aGetsecurityinf; "GetSecurityInfo failed wih error: 0x%08"...
0x18003270a  jmp     short loc_18003269B
0x18003270c  test    rbx, rbx
0x18003270f  jz      short loc_18003271A
0x180032711  mov     rcx, rbx; hObject
0x180032714  call    cs:__imp_CloseHandle
0x18003271a  mov     rcx, [rbp+hMem]; hMem
0x18003271e  test    rcx, rcx
0x180032721  jz      short loc_180032729
0x180032723  call    cs:__imp_LocalFree
0x180032729  xor     eax, eax
0x18003272b  jmp     short loc_180032752
0x18003272d  lea     rdx, aGetsecuritydes; "GetSecurityDescriptorStringFromFile req"...
0x180032734  mov     ecx, 2; unsigned __int8
0x180032739  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003273e  mov     rcx, [rbp+hMem]; hMem
0x180032742  test    rcx, rcx
0x180032745  jz      short loc_18003274D
0x180032747  call    cs:__imp_LocalFree
0x18003274d  mov     eax, 80070057h
0x180032752  mov     rbx, [rsp+50h+arg_8]
0x18003275a  add     rsp, 50h
0x18003275e  pop     r15
0x180032760  pop     r14
0x180032762  pop     rdi
0x180032763  pop     rsi
0x180032764  pop     rbp
0x180032765  retn
```
