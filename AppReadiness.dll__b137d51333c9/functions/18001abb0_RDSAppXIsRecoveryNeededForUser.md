# RDSAppXIsRecoveryNeededForUser

- ea: `0x18001abb0`
- end: `0x18001ae8d`
- name: `RDSAppXIsRecoveryNeededForUser`
- size: `733`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180063d50`

## callees

- `0x180019620`
- `0x18001abb0`
- `0x18003e210`
- `0x180074158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001addc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001addc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ac4d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001adf6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001adf6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ace9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ace9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ac02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ac02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae82`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ac3a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ad8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ac3a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ad8d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001acac`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001acac`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001ae08`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001ae08`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RDSAppXIsRecoveryNeededForUser(PSID Sid)
{
  LPWSTR v2; // rcx
  unsigned __int16 *v3; // rsi
  WCHAR *v4; // rbp
  int AppReadinessDirectory; // ebx
  HANDLE FileW; // rax
  __int64 v8; // rcx
  WCHAR *v9; // rax
  __int64 v10; // rdi
  WCHAR *v11; // rax
  unsigned __int64 v12; // r8
  __int64 v13; // rcx
  WCHAR *v14; // rdx
  WCHAR *v15; // r9
  WCHAR *v16; // rcx
  signed int v17; // eax
  signed int LastError; // eax
  unsigned __int64 v19; // rdx
  int v20; // eax
  LPWSTR StringSid; // [rsp+40h] [rbp-248h] BYREF
  unsigned __int16 *v22; // [rsp+48h] [rbp-240h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-238h] BYREF

  v22 = 0;
  v2 = 0;
  StringSid = 0;
  v3 = 0;
  v4 = 0;
  if ( Sid )
  {
    if ( IsValidSid(Sid) )
    {
      if ( !ConvertSidToStringSidW(Sid, &StringSid) )
        GetLastError();
      v20 = UserSidToRecoveryFileName(StringSid, &v22);
      v2 = StringSid;
      AppReadinessDirectory = v20;
      v3 = v22;
      goto LABEL_3;
    }
    v2 = StringSid;
  }
  AppReadinessDirectory = -2147024809;
LABEL_3:
  if ( v2 )
    LocalFree(v2);
  if ( AppReadinessDirectory >= 0 )
  {
    FileW = CreateFileW(v3, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
LABEL_7:
      CloseHandle(FileW);
      goto LABEL_8;
    }
    LastError = GetLastError();
    AppReadinessDirectory = LastError;
    if ( LastError > 0 )
      AppReadinessDirectory = (unsigned __int16)LastError | 0x80070000;
    if ( AppReadinessDirectory < 0 )
    {
      AppReadinessDirectory = GetAppReadinessDirectory(pszPath, v19);
      if ( AppReadinessDirectory >= 0 )
      {
        AppReadinessDirectory = PathCchAppend(pszPath, 0x104u, L"S-1-5-18");
        if ( AppReadinessDirectory >= 0 )
        {
          v8 = 260;
          v9 = pszPath;
          while ( *v9 )
          {
            ++v9;
            if ( !--v8 )
            {
              AppReadinessDirectory = -2147024809;
              goto LABEL_8;
            }
          }
          v10 = 260 - v8;
          v11 = (WCHAR *)LocalAlloc(0x40u, 2 * (260 - v8) + 2);
          if ( !v11 )
          {
            AppReadinessDirectory = -2147024882;
            goto LABEL_8;
          }
          v12 = v10 + 1;
          if ( v10 == -1 )
          {
            AppReadinessDirectory = -2147024809;
          }
          else
          {
            if ( v12 > 0x7FFFFFFF )
            {
              *v11 = 0;
              AppReadinessDirectory = -2147024809;
              goto LABEL_45;
            }
            v13 = 2147483646;
            v14 = pszPath;
            v15 = v11;
            do
            {
              if ( !v13 )
                break;
              if ( !*v14 )
                break;
              *v15++ = *v14++;
              --v13;
              --v12;
            }
            while ( v12 );
            v16 = v15 - 1;
            AppReadinessDirectory = -2147024774;
            if ( v12 )
            {
              v16 = v15;
              AppReadinessDirectory = 0;
            }
            *v16 = 0;
          }
          if ( AppReadinessDirectory >= 0 )
          {
            v4 = v11;
            FileW = CreateFileW(v11, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
            if ( FileW != (HANDLE)-1LL )
              goto LABEL_7;
            v17 = GetLastError();
            AppReadinessDirectory = v17;
            if ( v17 > 0 )
              AppReadinessDirectory = (unsigned __int16)v17 | 0x80070000;
            goto LABEL_8;
          }
LABEL_45:
          LocalFree(v11);
        }
      }
    }
  }
LABEL_8:
  if ( v3 )
    LocalFree(v3);
  if ( v4 )
    LocalFree(v4);
  return (unsigned int)AppReadinessDirectory;
}

```

## disassembly

```asm
0x18001abb0  mov     r11, rsp
0x18001abb3  push    rbx
0x18001abb4  push    rbp
0x18001abb5  sub     rsp, 278h
0x18001abbc  mov     rax, cs:__security_cookie
0x18001abc3  xor     rax, rsp
0x18001abc6  mov     [rsp+288h+var_28], rax
0x18001abce  mov     [r11+10h], rsi
0x18001abd2  mov     rbx, rcx
0x18001abd5  mov     [r11-18h], r14
0x18001abd9  xor     r14d, r14d
0x18001abdc  mov     [rsp+288h+var_240], r14
0x18001abe1  mov     ecx, r14d; hMem
0x18001abe4  mov     [rsp+288h+StringSid], rcx
0x18001abe9  mov     esi, r14d
0x18001abec  mov     ebp, r14d
0x18001abef  test    rbx, rbx
0x18001abf2  jnz     loc_18001ADF3
0x18001abf8  mov     ebx, 80070057h
0x18001abfd  test    rcx, rcx
0x18001ac00  jz      short loc_18001AC08
0x18001ac02  call    cs:__imp_LocalFree
0x18001ac08  mov     [rsp+288h+arg_10], rdi
0x18001ac10  test    ebx, ebx
0x18001ac12  js      short loc_18001AC53
0x18001ac14  mov     [rsp+288h+hTemplateFile], r14; hTemplateFile
0x18001ac19  xor     r9d, r9d; lpSecurityAttributes
0x18001ac1c  mov     [rsp+288h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001ac24  mov     edx, 0C0000000h; dwDesiredAccess
0x18001ac29  mov     r8d, 3; dwShareMode
0x18001ac2f  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x18001ac37  mov     rcx, rsi; lpFileName
0x18001ac3a  call    cs:__imp_CreateFileW
0x18001ac40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ac44  jz      loc_18001ADDC
0x18001ac4a  mov     rcx, rax; hObject
0x18001ac4d  call    cs:__imp_CloseHandle
0x18001ac53  mov     r14, [rsp+288h+var_18]
0x18001ac5b  mov     rdi, [rsp+288h+arg_10]
0x18001ac63  test    rsi, rsi
0x18001ac66  jnz     loc_18001AE71
0x18001ac6c  mov     rsi, [rsp+288h+arg_8]
0x18001ac74  test    rbp, rbp
0x18001ac77  jnz     loc_18001AE7F
0x18001ac7d  mov     eax, ebx
0x18001ac7f  mov     rcx, [rsp+288h+var_28]
0x18001ac87  xor     rcx, rsp; StackCookie
0x18001ac8a  call    __security_check_cookie
0x18001ac8f  add     rsp, 278h
0x18001ac96  pop     rbp
0x18001ac97  pop     rbx
0x18001ac98  retn
0x18001ac99  mov     edi, 104h
0x18001ac9e  lea     r8, pszMore; "S-1-5-18"
0x18001aca5  mov     edx, edi; cchPath
0x18001aca7  lea     rcx, [rsp+288h+pszPath]; pszPath
0x18001acac  call    cs:__imp_PathCchAppend
0x18001acb2  mov     ebx, eax
0x18001acb4  test    eax, eax
0x18001acb6  js      short loc_18001AC53
0x18001acb8  mov     ecx, edi
0x18001acba  lea     rax, [rsp+288h+pszPath]
0x18001acbf  nop
0x18001acc0  cmp     [rax], bp
0x18001acc3  jz      short loc_18001ACD9
0x18001acc5  add     rax, 2
0x18001acc9  sub     rcx, 1
0x18001accd  jnz     short loc_18001ACC0
0x18001accf  mov     ebx, 80070057h
0x18001acd4  jmp     loc_18001AC53
0x18001acd9  sub     rdi, rcx
0x18001acdc  mov     ecx, 40h ; '@'; uFlags
0x18001ace1  lea     rdx, ds:2[rdi*2]; uBytes
0x18001ace9  call    cs:__imp_LocalAlloc
0x18001acef  mov     r10, rax
0x18001acf2  test    rax, rax
0x18001acf5  jz      loc_18001AE42
0x18001acfb  lea     r8, [rdi+1]
0x18001acff  test    r8, r8
0x18001ad02  jz      loc_18001AE4C
0x18001ad08  cmp     r8, 7FFFFFFFh
0x18001ad0f  ja      loc_18001AE5A
0x18001ad15  mov     ecx, 7FFFFFFEh
0x18001ad1a  lea     rdx, [rsp+288h+pszPath]
0x18001ad1f  mov     r9, rax
0x18001ad22  test    rcx, rcx
0x18001ad25  jz      short loc_18001AD44
0x18001ad27  movzx   eax, word ptr [rdx]
0x18001ad2a  test    ax, ax
0x18001ad2d  jz      short loc_18001AD44
0x18001ad2f  mov     [r9], ax
0x18001ad33  add     rdx, 2
0x18001ad37  add     r9, 2
0x18001ad3b  dec     rcx
0x18001ad3e  sub     r8, 1
0x18001ad42  jnz     short loc_18001AD22
0x18001ad44  test    r8, r8
0x18001ad47  lea     rcx, [r9-2]
0x18001ad4b  mov     ebx, 8007007Ah
0x18001ad50  cmovnz  rcx, r9
0x18001ad54  cmovnz  ebx, r14d
0x18001ad58  mov     [rcx], r14w
0x18001ad5c  test    ebx, ebx
0x18001ad5e  js      loc_18001AE63
0x18001ad64  mov     [rsp+288h+hTemplateFile], r14; hTemplateFile
0x18001ad69  xor     r9d, r9d; lpSecurityAttributes
0x18001ad6c  mov     [rsp+288h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001ad74  mov     edx, 0C0000000h; dwDesiredAccess
0x18001ad79  mov     r8d, 3; dwShareMode
0x18001ad7f  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x18001ad87  mov     rcx, r10; lpFileName
0x18001ad8a  mov     rbp, r10
0x18001ad8d  call    cs:__imp_CreateFileW
0x18001ad93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ad97  jnz     loc_18001AC4A
0x18001ad9d  call    cs:__imp_GetLastError
0x18001ada3  mov     ebx, eax
0x18001ada5  test    eax, eax
0x18001ada7  jle     loc_18001AC53
0x18001adad  movzx   ebx, ax
0x18001adb0  or      ebx, 80070000h
0x18001adb6  jmp     loc_18001AC53
0x18001adbb  test    ebx, ebx
0x18001adbd  jns     loc_18001AC53
0x18001adc3  lea     rcx, [rsp+288h+pszPath]; lpPathName
0x18001adc8  call    ?GetAppReadinessDirectory@@YAJPEAG_K@Z; GetAppReadinessDirectory(ushort *,unsigned __int64)
0x18001adcd  mov     ebx, eax
0x18001adcf  test    eax, eax
0x18001add1  js      loc_18001AC53
0x18001add7  jmp     loc_18001AC99
0x18001addc  call    cs:__imp_GetLastError
0x18001ade2  mov     ebx, eax
0x18001ade4  test    eax, eax
0x18001ade6  jle     short loc_18001ADBB
0x18001ade8  movzx   ebx, ax
0x18001adeb  or      ebx, 80070000h
0x18001adf1  jmp     short loc_18001ADBB
0x18001adf3  mov     rcx, rbx; pSid
0x18001adf6  call    cs:__imp_IsValidSid
0x18001adfc  test    eax, eax
0x18001adfe  jz      short loc_18001AE38
0x18001ae00  lea     rdx, [rsp+288h+StringSid]; StringSid
0x18001ae05  mov     rcx, rbx; Sid
0x18001ae08  call    cs:__imp_ConvertSidToStringSidW
0x18001ae0e  test    eax, eax
0x18001ae10  jnz     short loc_18001AE18
0x18001ae12  call    cs:__imp_GetLastError
0x18001ae18  mov     rcx, [rsp+288h+StringSid]; pszMore
0x18001ae1d  lea     rdx, [rsp+288h+var_240]; unsigned __int16 **
0x18001ae22  call    ?UserSidToRecoveryFileName@@YAJPEBGPEAPEAG@Z; UserSidToRecoveryFileName(ushort const *,ushort * *)
0x18001ae27  mov     rcx, [rsp+288h+StringSid]
0x18001ae2c  mov     ebx, eax
0x18001ae2e  mov     rsi, [rsp+288h+var_240]
0x18001ae33  jmp     loc_18001ABFD
0x18001ae38  mov     rcx, [rsp+288h+StringSid]
0x18001ae3d  jmp     loc_18001ABF8
0x18001ae42  mov     ebx, 8007000Eh
0x18001ae47  jmp     loc_18001AC53
0x18001ae4c  mov     ebx, 80070057h
0x18001ae51  test    r8, r8
0x18001ae54  jz      loc_18001AD5C
0x18001ae5a  mov     [rax], r14w
0x18001ae5e  mov     ebx, 80070057h
0x18001ae63  mov     rcx, r10; hMem
0x18001ae66  call    cs:__imp_LocalFree
0x18001ae6c  jmp     loc_18001AC53
0x18001ae71  mov     rcx, rsi; hMem
0x18001ae74  call    cs:__imp_LocalFree
0x18001ae7a  jmp     loc_18001AC6C
0x18001ae7f  mov     rcx, rbp; hMem
0x18001ae82  call    cs:__imp_LocalFree
0x18001ae88  jmp     loc_18001AC7D
```
