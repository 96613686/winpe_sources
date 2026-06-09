# CAxisServHelper::Initialize(void)

- ea: `0x18000bf6c`
- end: `0x18000c21d`
- name: `?Initialize@CAxisServHelper@@QEAAJXZ`
- size: `689`
- prototype: `__int64 __fastcall(CAxisServHelper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000c224`

## callees

- `0x180001720`
- `0x180005060`
- `0x1800056e0`
- `0x18000725c`
- `0x18000a2fc`
- `0x18000bf6c`
- `0x18000c5ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000c016`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000c016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1ee`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c1d1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c1d1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c1e4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c1e4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c0a9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c12e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c0a9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000c12e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bfe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bfe2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c066`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c0db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c066`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000c0db`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000c159`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000c159`

## string_xrefs

- `0x18000bfae`: `InitializeSecurity Failed, hr=%!HRESULT!\n`
- `0x18000c089`: `Failed to Convert AXIS Directory SDDL. Error 0x%x`
- `0x18000c0b7`: `Failed to Get Security Descriptor. Error 0x%x`
- `0x18000c0fe`: `Failed to Convert AXIS User IE Read SDDL. Error 0x%x`
- `0x18000c13c`: `Failed to Get AXIS User IE Read Security Descriptor. Error 0x%x`
- `0x18000c1c2`: `Failed to Create root Temp Folder. Error 0x%x`

## pseudocode

```c
__int64 __fastcall CAxisServHelper::Initialize(CAxisServHelper *this)
{
  int DirectoryWithAcls; // eax
  unsigned int v3; // ebx
  unsigned __int16 *v4; // r9
  signed int v5; // eax
  wchar_t *v6; // rax
  unsigned int v7; // r9d
  int appended; // eax
  signed int v9; // eax
  signed int v10; // eax
  void *v11; // rcx
  unsigned int v12; // r9d
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  int v16; // [rsp+20h] [rbp-248h]
  unsigned int v17; // [rsp+20h] [rbp-248h]
  int v18; // [rsp+20h] [rbp-248h]
  unsigned int v19; // [rsp+20h] [rbp-248h]
  unsigned int v20; // [rsp+20h] [rbp-248h]
  unsigned int v21; // [rsp+20h] [rbp-248h]
  unsigned int v22; // [rsp+20h] [rbp-248h]
  unsigned int v23; // [rsp+20h] [rbp-248h]
  WINBOOL bDaclDefaulted; // [rsp+30h] [rbp-238h] BYREF
  WINBOOL bDaclPresent[3]; // [rsp+34h] [rbp-234h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  bDaclPresent[0] = 0;
  bDaclDefaulted = 0;
  DirectoryWithAcls = CAxisServHelper::InitializeSecurity(this);
  v3 = DirectoryWithAcls;
  if ( DirectoryWithAcls < 0 )
  {
    v4 = L"InitializeSecurity Failed, hr=%!HRESULT!\n";
LABEL_3:
    v16 = DirectoryWithAcls;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, v4, v16);
    return v3;
  }
  if ( GetModuleFileNameW(0, (LPWSTR)this + 4, 0x104u) )
  {
    v6 = wcsrchr((const wchar_t *)this + 4, 0x5Cu);
    if ( v6 )
      *v6 = 0;
    appended = Utils::AppendPath((const unsigned __int16 *)this + 4, L"AxInstUI.exe", (unsigned __int16 *)this + 4, v7);
    v3 = appended;
    if ( appended >= 0 )
    {
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"D:(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)",
             1u,
             (PSECURITY_DESCRIPTOR *)this + 131,
             0) )
      {
        if ( GetSecurityDescriptorDacl(
               *((PSECURITY_DESCRIPTOR *)this + 131),
               bDaclPresent,
               (PACL *)this + 132,
               &bDaclDefaulted) )
        {
          if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                 L"D:(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OICI;GR;;;BU)(A;OICI;GR;;;S-1-15-3-4096)",
                 1u,
                 (PSECURITY_DESCRIPTOR *)this + 133,
                 0) )
          {
            v11 = (void *)*((_QWORD *)this + 133);
            bDaclPresent[0] = 0;
            bDaclDefaulted = 0;
            if ( GetSecurityDescriptorDacl(v11, bDaclPresent, (PACL *)this + 134, &bDaclDefaulted) )
            {
              Buffer[0] = 0;
              if ( GetWindowsDirectoryW(Buffer, 0x104u) )
              {
                v3 = Utils::AppendPath(Buffer, L"AxInstSV", (unsigned __int16 *)this + 264, v12);
                if ( (v3 & 0x80000000) == 0 )
                {
                  Utils::RemoveDirectoryAndChildren((const unsigned __int16 *)this + 264);
                  DirectoryWithAcls = CAxisServHelper::CreateDirectoryWithAcls(this, (unsigned __int16 *)this + 264);
                  v3 = DirectoryWithAcls;
                  if ( DirectoryWithAcls < 0 )
                  {
                    v4 = L"Failed to Create root Temp Folder. Error 0x%x";
                    goto LABEL_3;
                  }
                  FileAttributesW = GetFileAttributesW((LPCWSTR)this + 264);
                  if ( FileAttributesW == -1 || !SetFileAttributesW((LPCWSTR)this + 264, FileAttributesW | 2) )
                    GetLastError();
                  return 0;
                }
              }
              else
              {
                LastError = GetLastError();
                v3 = LastError;
                if ( LastError > 0 )
                  v3 = (unsigned __int16)LastError | 0x80070000;
                v23 = v3;
                AxISEvents::DebugMsg(
                  (AxISEvents *)&qword_180021AD8,
                  8u,
                  2u,
                  L"Failed to get Windows Folder Name. Error 0x%x",
                  v23);
              }
            }
            else
            {
              v22 = v3;
              AxISEvents::DebugMsg(
                (AxISEvents *)&qword_180021AD8,
                8u,
                2u,
                L"Failed to Get AXIS User IE Read Security Descriptor. Error 0x%x",
                v22);
            }
          }
          else
          {
            v10 = GetLastError();
            v3 = v10;
            if ( v10 > 0 )
              v3 = (unsigned __int16)v10 | 0x80070000;
            v21 = v3;
            AxISEvents::DebugMsg(
              (AxISEvents *)&qword_180021AD8,
              8u,
              2u,
              L"Failed to Convert AXIS User IE Read SDDL. Error 0x%x",
              v21);
          }
        }
        else
        {
          v20 = v3;
          AxISEvents::DebugMsg(
            (AxISEvents *)&qword_180021AD8,
            8u,
            2u,
            L"Failed to Get Security Descriptor. Error 0x%x",
            v20);
        }
      }
      else
      {
        v9 = GetLastError();
        v3 = v9;
        if ( v9 > 0 )
          v3 = (unsigned __int16)v9 | 0x80070000;
        v19 = v3;
        AxISEvents::DebugMsg(
          (AxISEvents *)&qword_180021AD8,
          8u,
          2u,
          L"Failed to Convert AXIS Directory SDDL. Error 0x%x",
          v19);
      }
    }
    else
    {
      v18 = appended;
      AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"Failed to get UI Process Name. Error 0x%x", v18);
    }
  }
  else
  {
    v5 = GetLastError();
    v3 = v5;
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    v17 = v3;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"Failed to get Module file name. Error 0x%x", v17);
  }
  return v3;
}

```

## disassembly

```asm
0x18000bf6c  mov     [rsp+arg_8], rbx
0x18000bf71  mov     [rsp+arg_10], rsi
0x18000bf76  push    rdi
0x18000bf77  sub     rsp, 260h
0x18000bf7e  mov     rax, cs:__security_cookie
0x18000bf85  xor     rax, rsp
0x18000bf88  mov     [rsp+268h+var_18], rax
0x18000bf90  mov     rsi, rcx
0x18000bf93  mov     [rsp+268h+bDaclPresent], 0
0x18000bf9b  mov     [rsp+268h+bDaclDefaulted], 0
0x18000bfa3  call    ?InitializeSecurity@CAxisServHelper@@QEAAJXZ; CAxisServHelper::InitializeSecurity(void)
0x18000bfa8  mov     ebx, eax
0x18000bfaa  test    eax, eax
0x18000bfac  jns     short loc_18000BFD3
0x18000bfae  lea     r9, aInitializesecu; "InitializeSecurity Failed, hr=%!HRESULT"...
0x18000bfb5  mov     [rsp+268h+var_248], eax
0x18000bfb9  mov     edx, 8; unsigned int
0x18000bfbe  lea     rcx, qword_180021AD8; this
0x18000bfc5  lea     r8d, [rdx-6]; unsigned __int8
0x18000bfc9  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000bfce  jmp     loc_18000C1F6
0x18000bfd3  lea     rbx, [rsi+8]
0x18000bfd7  mov     r8d, 104h; nSize
0x18000bfdd  mov     rdx, rbx; lpFilename
0x18000bfe0  xor     ecx, ecx; hModule
0x18000bfe2  call    cs:__imp_GetModuleFileNameW
0x18000bfe8  test    eax, eax
0x18000bfea  jnz     short loc_18000C00E
0x18000bfec  call    cs:__imp_GetLastError
0x18000bff2  mov     ebx, eax
0x18000bff4  test    eax, eax
0x18000bff6  jle     short loc_18000C001
0x18000bff8  movzx   ebx, ax
0x18000bffb  or      ebx, 80070000h
0x18000c001  mov     [rsp+268h+var_248], ebx
0x18000c005  lea     r9, aFailedToGetMod; "Failed to get Module file name. Error 0"...
0x18000c00c  jmp     short loc_18000BFB9
0x18000c00e  mov     edx, 5Ch ; '\'; Ch
0x18000c013  mov     rcx, rbx; Str
0x18000c016  call    cs:__imp_wcsrchr
0x18000c01c  test    rax, rax
0x18000c01f  jz      short loc_18000C026
0x18000c021  xor     ecx, ecx
0x18000c023  mov     [rax], cx
0x18000c026  mov     r8, rbx; unsigned __int16 *
0x18000c029  lea     rdx, aAxinstuiExe; "AxInstUI.exe"
0x18000c030  mov     rcx, rbx; unsigned __int16 *
0x18000c033  call    ?AppendPath@Utils@@SAJPEBG0PEAGK@Z; Utils::AppendPath(ushort const *,ushort const *,ushort *,ulong)
0x18000c038  mov     ebx, eax
0x18000c03a  test    eax, eax
0x18000c03c  jns     short loc_18000C04E
0x18000c03e  mov     [rsp+268h+var_248], eax
0x18000c042  lea     r9, aFailedToGetUiP; "Failed to get UI Process Name. Error 0x"...
0x18000c049  jmp     loc_18000BFB9
0x18000c04e  xor     r9d, r9d; SecurityDescriptorSize
0x18000c051  lea     rdi, [rsi+418h]
0x18000c058  mov     r8, rdi; SecurityDescriptor
0x18000c05b  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)"
0x18000c062  lea     edx, [r9+1]; StringSDRevision
0x18000c066  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000c06c  test    eax, eax
0x18000c06e  jnz     short loc_18000C095
0x18000c070  call    cs:__imp_GetLastError
0x18000c076  mov     ebx, eax
0x18000c078  test    eax, eax
0x18000c07a  jle     short loc_18000C085
0x18000c07c  movzx   ebx, ax
0x18000c07f  or      ebx, 80070000h
0x18000c085  mov     [rsp+268h+var_248], ebx
0x18000c089  lea     r9, aFailedToConver; "Failed to Convert AXIS Directory SDDL. "...
0x18000c090  jmp     loc_18000BFB9
0x18000c095  mov     rcx, [rdi]; pSecurityDescriptor
0x18000c098  lea     r8, [rsi+420h]; pDacl
0x18000c09f  lea     r9, [rsp+268h+bDaclDefaulted]; lpbDaclDefaulted
0x18000c0a4  lea     rdx, [rsp+268h+bDaclPresent]; lpbDaclPresent
0x18000c0a9  call    cs:__imp_GetSecurityDescriptorDacl
0x18000c0af  test    eax, eax
0x18000c0b1  jnz     short loc_18000C0C3
0x18000c0b3  mov     [rsp+268h+var_248], ebx
0x18000c0b7  lea     r9, aFailedToGetSec; "Failed to Get Security Descriptor. Erro"...
0x18000c0be  jmp     loc_18000BFB9
0x18000c0c3  xor     r9d, r9d; SecurityDescriptorSize
0x18000c0c6  lea     rdi, [rsi+428h]
0x18000c0cd  mov     r8, rdi; SecurityDescriptor
0x18000c0d0  lea     rcx, aDAOiciGaSyAOic_0; "D:(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OI"...
0x18000c0d7  lea     edx, [r9+1]; StringSDRevision
0x18000c0db  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000c0e1  test    eax, eax
0x18000c0e3  jnz     short loc_18000C10A
0x18000c0e5  call    cs:__imp_GetLastError
0x18000c0eb  mov     ebx, eax
0x18000c0ed  test    eax, eax
0x18000c0ef  jle     short loc_18000C0FA
0x18000c0f1  movzx   ebx, ax
0x18000c0f4  or      ebx, 80070000h
0x18000c0fa  mov     [rsp+268h+var_248], ebx
0x18000c0fe  lea     r9, aFailedToConver_0; "Failed to Convert AXIS User IE Read SDD"...
0x18000c105  jmp     loc_18000BFB9
0x18000c10a  mov     rcx, [rdi]; pSecurityDescriptor
0x18000c10d  lea     r8, [rsi+430h]; pDacl
0x18000c114  lea     r9, [rsp+268h+bDaclDefaulted]; lpbDaclDefaulted
0x18000c119  mov     [rsp+268h+bDaclPresent], 0
0x18000c121  lea     rdx, [rsp+268h+bDaclPresent]; lpbDaclPresent
0x18000c126  mov     [rsp+268h+bDaclDefaulted], 0
0x18000c12e  call    cs:__imp_GetSecurityDescriptorDacl
0x18000c134  test    eax, eax
0x18000c136  jnz     short loc_18000C148
0x18000c138  mov     [rsp+268h+var_248], ebx
0x18000c13c  lea     r9, aFailedToGetAxi; "Failed to Get AXIS User IE Read Securit"...
0x18000c143  jmp     loc_18000BFB9
0x18000c148  xor     eax, eax
0x18000c14a  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x18000c14f  mov     edx, 104h; uSize
0x18000c154  mov     [rsp+268h+Buffer], ax
0x18000c159  call    cs:__imp_GetWindowsDirectoryW
0x18000c15f  test    eax, eax
0x18000c161  jnz     short loc_18000C188
0x18000c163  call    cs:__imp_GetLastError
0x18000c169  mov     ebx, eax
0x18000c16b  test    eax, eax
0x18000c16d  jle     short loc_18000C178
0x18000c16f  movzx   ebx, ax
0x18000c172  or      ebx, 80070000h
0x18000c178  mov     [rsp+268h+var_248], ebx
0x18000c17c  lea     r9, aFailedToGetWin; "Failed to get Windows Folder Name. Erro"...
0x18000c183  jmp     loc_18000BFB9
0x18000c188  lea     rdi, [rsi+210h]
0x18000c18f  mov     r8, rdi; unsigned __int16 *
0x18000c192  lea     rdx, ServiceName; "AxInstSV"
0x18000c199  lea     rcx, [rsp+268h+Buffer]; unsigned __int16 *
0x18000c19e  call    ?AppendPath@Utils@@SAJPEBG0PEAGK@Z; Utils::AppendPath(ushort const *,ushort const *,ushort *,ulong)
0x18000c1a3  mov     ebx, eax
0x18000c1a5  test    eax, eax
0x18000c1a7  js      short loc_18000C1F6
0x18000c1a9  mov     rcx, rdi; unsigned __int16 *
0x18000c1ac  call    ?RemoveDirectoryAndChildren@Utils@@SAJPEBG@Z; Utils::RemoveDirectoryAndChildren(ushort const *)
0x18000c1b1  mov     rdx, rdi; unsigned __int16 *
0x18000c1b4  mov     rcx, rsi; this
0x18000c1b7  call    ?CreateDirectoryWithAcls@CAxisServHelper@@QEAAJPEAG@Z; CAxisServHelper::CreateDirectoryWithAcls(ushort *)
0x18000c1bc  mov     ebx, eax
0x18000c1be  test    eax, eax
0x18000c1c0  jns     short loc_18000C1CE
0x18000c1c2  lea     r9, aFailedToCreate_1; "Failed to Create root Temp Folder. Erro"...
0x18000c1c9  jmp     loc_18000BFB5
0x18000c1ce  mov     rcx, rdi; lpFileName
0x18000c1d1  call    cs:__imp_GetFileAttributesW
0x18000c1d7  cmp     eax, 0FFFFFFFFh
0x18000c1da  jz      short loc_18000C1EE
0x18000c1dc  or      eax, 2
0x18000c1df  mov     rcx, rdi; lpFileName
0x18000c1e2  mov     edx, eax; dwFileAttributes
0x18000c1e4  call    cs:__imp_SetFileAttributesW
0x18000c1ea  test    eax, eax
0x18000c1ec  jnz     short loc_18000C1F4
0x18000c1ee  call    cs:__imp_GetLastError
0x18000c1f4  xor     ebx, ebx
0x18000c1f6  mov     eax, ebx
0x18000c1f8  mov     rcx, [rsp+268h+var_18]
0x18000c200  xor     rcx, rsp; StackCookie
0x18000c203  call    __security_check_cookie
0x18000c208  lea     r11, [rsp+268h+var_8]
0x18000c210  mov     rbx, [r11+18h]
0x18000c214  mov     rsi, [r11+20h]
0x18000c218  mov     rsp, r11
0x18000c21b  pop     rdi
0x18000c21c  retn
```
