# _AppendPathAndCreateFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,bool,ushort *,uint)

- ea: `0x180004e00`
- end: `0x180005260`
- name: `?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z`
- size: `1120`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004578`
- `0x180043564`

## callees

- `0x180004e00`
- `0x1800064d4`
- `0x18000d2b8`
- `0x18003aa84`
- `0x180050ba0`
- `0x180051524`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180004ed1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800051ec`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180004ed1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800051ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004f84`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800051c3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004f84`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800051c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005121`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005121`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051d5`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18000506c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18000515e`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18000506c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18000515e`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800050ce`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800050ce`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004eab`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180004eab`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180004ef2`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180004ef2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000510c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000510c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005194`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005194`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800050b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800050b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180005187`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180005187`

## pseudocode

```c
__int64 __fastcall _AppendPathAndCreateFolder(
        const WCHAR *a1,
        WCHAR *a2,
        int a3,
        char a4,
        char a5,
        const WCHAR *lpString1)
{
  WCHAR *v6; // r11
  __int64 v7; // r12
  __int64 v8; // r15
  __int64 v9; // rsi
  __int64 v12; // rcx
  const WCHAR *v13; // r10
  __int64 v14; // r9
  WCHAR *v15; // rcx
  HRESULT Error; // edi
  wchar_t *i; // rax
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rax
  __int64 v21; // rcx
  WCHAR *v22; // rdx
  __int64 v23; // r8
  WCHAR *v24; // r9
  WCHAR *v25; // rcx
  const wchar_t *v26; // rdx
  WCHAR *v27; // rax
  WCHAR *v28; // rcx
  void *v29; // rax
  void *v30; // rbx
  bool v31; // si
  size_t v32; // rax
  LPWSTR v33; // r9
  DWORD nLengthNeeded[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+270h] [rbp+170h] BYREF

  v6 = pszPath;
  v7 = a3;
  v8 = 2147483646;
  v9 = 260;
  StringSecurityDescriptor = a2;
  v12 = 2147483646;
  v13 = lpString1;
  v14 = 260;
  do
  {
    if ( !v12 )
      break;
    if ( !*v13 )
      break;
    *v6++ = *v13++;
    --v12;
    --v14;
  }
  while ( v14 );
  v15 = v6 - 1;
  Error = -2147024774;
  if ( v14 )
  {
    v15 = v6;
    Error = 0;
  }
  *v15 = 0;
  if ( v14 )
  {
    Error = PathCchAppend(pszPath, 0x104u, a1);
    if ( Error >= 0 )
    {
      for ( i = wcsstr(pszPath, L"/"); i; i = wcsstr(i, L"/") )
        *i = 92;
      Error = PathCchCanonicalizeEx(pszPathOut, 0x104u, pszPath, 0);
      if ( Error >= 0 )
      {
        v18 = -1;
        do
          ++v18;
        while ( lpString1[v18] );
        if ( v18 > 0xFFFFFFFF )
          return (unsigned int)-2147024362;
        v19 = -1;
        do
          ++v19;
        while ( pszPathOut[v19] );
        if ( v19 > 0xFFFFFFFF )
          return (unsigned int)-2147024362;
        Error = -2147024809;
        if ( (unsigned int)v19 > (unsigned int)v18
          && CompareStringOrdinal(lpString1, v18, pszPathOut, v18, 0) == 2
          && pszPathOut[(unsigned int)v18] == 92 )
        {
          v21 = 2147483646;
          v22 = pszPathOut;
          v23 = 260;
          v24 = (WCHAR *)lpString1;
          do
          {
            if ( !v21 )
              break;
            if ( !*v22 )
              break;
            *v24++ = *v22++;
            --v21;
            --v23;
          }
          while ( v23 );
          v25 = v24 - 1;
          Error = -2147024774;
          if ( v23 )
          {
            v25 = v24;
            Error = 0;
          }
          *v25 = 0;
          if ( v23 && a5 )
          {
            if ( (_DWORD)v7 )
            {
              v33 = L"BU";
              if ( (a4 & 1) == 0 )
                v33 = StringSecurityDescriptor;
              Error = StringCchPrintfW(pszPathOut, 0x104u, (&off_1800E6010)[3 * v7], v33);
            }
            else
            {
              v26 = L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)";
              v27 = pszPathOut;
              do
              {
                if ( !v8 )
                  break;
                if ( !*v26 )
                  break;
                *v27++ = *v26++;
                --v8;
                --v9;
              }
              while ( v9 );
              v28 = v27 - 1;
              Error = -2147024774;
              if ( v9 )
              {
                v28 = v27;
                Error = 0;
              }
              *v28 = 0;
            }
            if ( Error >= 0 )
            {
              nLengthNeeded[0] = 0;
              if ( GetFileSecurityW(lpString1, 7u, 0, 0, nLengthNeeded) )
                goto LABEL_42;
              if ( (unsigned int)ResultFromKnownLastError() != -2147024774 )
                goto LABEL_42;
              v29 = CoTaskMemAlloc(nLengthNeeded[0]);
              v30 = v29;
              if ( !v29 )
                goto LABEL_42;
              v31 = 0;
              v32 = CTCoAllocPolicy::_CoTaskMemSize(v29);
              memset_0(v30, 0, v32);
              if ( GetFileSecurityW(lpString1, 7u, v30, nLengthNeeded[0], nLengthNeeded) )
              {
                StringSecurityDescriptor = 0;
                if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v30, 1u, 7u, &StringSecurityDescriptor, 0) )
                {
                  v31 = CompareStringOrdinal(StringSecurityDescriptor, -1, pszPathOut, -1, 1) == 2;
                  LocalFree(StringSecurityDescriptor);
                }
              }
              CoTaskMemFree(v30);
              if ( !v31 )
              {
LABEL_42:
                *(_QWORD *)nLengthNeeded = 0;
                if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                       pszPathOut,
                       1u,
                       (PSECURITY_DESCRIPTOR *)nLengthNeeded,
                       0)
                  || (Error = ResultFromKnownLastError(), Error >= 0) )
                {
                  if ( SetFileSecurityW(lpString1, 7u, *(PSECURITY_DESCRIPTOR *)nLengthNeeded) )
                    goto LABEL_46;
                  Error = ResultFromKnownLastError();
                  if ( Error != -2147024894 )
                  {
                    if ( Error == -2147024891 )
                      Error = 0;
                    goto LABEL_47;
                  }
                  SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)nLengthNeeded;
                  *(_QWORD *)&SecurityAttributes.nLength = 24;
                  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
                  if ( CreateDirectoryW(lpString1, &SecurityAttributes) )
LABEL_46:
                    Error = 0;
                  else
                    Error = ResultFromKnownLastError();
LABEL_47:
                  LocalFree(*(HLOCAL *)nLengthNeeded);
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180004e00  push    rbp
0x180004e02  push    rsi
0x180004e03  push    rdi
0x180004e04  push    r12
0x180004e06  push    r13
0x180004e08  push    r14
0x180004e0a  push    r15
0x180004e0c  lea     rbp, [rsp-390h]
0x180004e14  sub     rsp, 490h
0x180004e1b  mov     rax, cs:__security_cookie
0x180004e22  xor     rax, rsp
0x180004e25  mov     [rbp+3C0h+var_40], rax
0x180004e2c  mov     r14, [rbp+3C0h+lpString1]
0x180004e33  lea     r11, [rbp+3C0h+pszPath]
0x180004e3a  movsxd  r12, r8d
0x180004e3d  mov     r15d, 7FFFFFFEh
0x180004e43  mov     esi, 104h
0x180004e48  mov     [rsp+4C0h+StringSecurityDescriptor], rdx
0x180004e4d  mov     r8, rcx; pszMore
0x180004e50  mov     r13d, r9d
0x180004e53  mov     ecx, r15d
0x180004e56  mov     r10, r14
0x180004e59  mov     r9d, esi
0x180004e5c  nop     dword ptr [rax+00h]
0x180004e60  test    rcx, rcx
0x180004e63  jz      short loc_180004E83
0x180004e65  movzx   eax, word ptr [r10]
0x180004e69  test    ax, ax
0x180004e6c  jz      short loc_180004E83
0x180004e6e  mov     [r11], ax
0x180004e72  add     r10, 2
0x180004e76  add     r11, 2
0x180004e7a  dec     rcx
0x180004e7d  sub     r9, 1
0x180004e81  jnz     short loc_180004E60
0x180004e83  xor     eax, eax
0x180004e85  lea     rcx, [r11-2]
0x180004e89  test    r9, r9
0x180004e8c  mov     edi, 8007007Ah
0x180004e91  cmovnz  rcx, r11
0x180004e95  cmovnz  edi, eax
0x180004e98  mov     [rcx], ax
0x180004e9b  jz      loc_180004F42
0x180004ea1  mov     rdx, rsi; cchPath
0x180004ea4  lea     rcx, [rbp+3C0h+pszPath]; pszPath
0x180004eab  call    cs:__imp_PathCchAppend
0x180004eb1  mov     edi, eax
0x180004eb3  test    eax, eax
0x180004eb5  js      loc_180004F42
0x180004ebb  lea     rdx, SubStr
0x180004ec2  mov     [rsp+4C0h+arg_10], rbx
0x180004eca  lea     rcx, [rbp+3C0h+pszPath]; Str
0x180004ed1  call    cs:__imp_wcsstr
0x180004ed7  test    rax, rax
0x180004eda  jnz     loc_1800051DD
0x180004ee0  xor     r9d, r9d; dwFlags
0x180004ee3  lea     r8, [rbp+3C0h+pszPath]; pszPathIn
0x180004eea  mov     rdx, rsi; cchPathOut
0x180004eed  lea     rcx, [rsp+4C0h+pszPathOut]; pszPathOut
0x180004ef2  call    cs:__imp_PathCchCanonicalizeEx
0x180004ef8  mov     edi, eax
0x180004efa  test    eax, eax
0x180004efc  js      short loc_180004F3A
0x180004efe  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180004f05  inc     rbx
0x180004f08  cmp     word ptr [r14+rbx*2], 0
0x180004f0e  jnz     short loc_180004F05
0x180004f10  mov     edx, 0FFFFFFFFh
0x180004f15  cmp     rbx, rdx
0x180004f18  ja      short loc_180004F35
0x180004f1a  lea     rcx, [rsp+4C0h+pszPathOut]
0x180004f1f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004f26  inc     rax
0x180004f29  cmp     word ptr [rcx+rax*2], 0
0x180004f2e  jnz     short loc_180004F26
0x180004f30  cmp     rax, rdx
0x180004f33  jbe     short loc_180004F66
0x180004f35  mov     edi, 80070216h
0x180004f3a  mov     rbx, [rsp+4C0h+arg_10]
0x180004f42  mov     eax, edi
0x180004f44  mov     rcx, [rbp+3C0h+var_40]
0x180004f4b  xor     rcx, rsp; StackCookie
0x180004f4e  call    __security_check_cookie
0x180004f53  add     rsp, 490h
0x180004f5a  pop     r15
0x180004f5c  pop     r14
0x180004f5e  pop     r13
0x180004f60  pop     r12
0x180004f62  pop     rdi
0x180004f63  pop     rsi
0x180004f64  pop     rbp
0x180004f65  retn
0x180004f66  mov     edi, 80070057h
0x180004f6b  cmp     eax, ebx
0x180004f6d  jbe     short loc_180004F3A
0x180004f6f  mov     r9d, ebx; cchCount2
0x180004f72  mov     [rsp+4C0h+bIgnoreCase], 0; bIgnoreCase
0x180004f7a  lea     r8, [rsp+4C0h+pszPathOut]; lpString2
0x180004f7f  mov     edx, ebx; cchCount1
0x180004f81  mov     rcx, r14; lpString1
0x180004f84  call    cs:__imp_CompareStringOrdinal
0x180004f8a  cmp     eax, 2
0x180004f8d  jnz     short loc_180004F3A
0x180004f8f  mov     eax, ebx
0x180004f91  cmp     [rsp+rax*2+4C0h+pszPathOut], 5Ch ; '\'
0x180004f97  jnz     short loc_180004F3A
0x180004f99  mov     rcx, r15
0x180004f9c  lea     rdx, [rsp+4C0h+pszPathOut]
0x180004fa1  mov     r8, rsi
0x180004fa4  mov     r9, r14
0x180004fa7  test    rcx, rcx
0x180004faa  jz      short loc_180004FC9
0x180004fac  movzx   eax, word ptr [rdx]
0x180004faf  test    ax, ax
0x180004fb2  jz      short loc_180004FC9
0x180004fb4  mov     [r9], ax
0x180004fb8  add     rdx, 2
0x180004fbc  add     r9, 2
0x180004fc0  dec     rcx
0x180004fc3  sub     r8, 1
0x180004fc7  jnz     short loc_180004FA7
0x180004fc9  xor     eax, eax
0x180004fcb  lea     rcx, [r9-2]
0x180004fcf  test    r8, r8
0x180004fd2  mov     edi, 8007007Ah
0x180004fd7  cmovnz  rcx, r9
0x180004fdb  cmovnz  edi, eax
0x180004fde  mov     [rcx], ax
0x180004fe1  jz      loc_180004F3A
0x180004fe7  cmp     [rbp+3C0h+arg_20], al
0x180004fed  jz      loc_180004F3A
0x180004ff3  test    r12d, r12d
0x180004ff6  jnz     loc_1800051FC
0x180004ffc  mov     rdx, cs:off_1800E6010
0x180005003  lea     rax, [rsp+4C0h+pszPathOut]
0x180005008  test    r15, r15
0x18000500b  jz      short loc_180005029
0x18000500d  movzx   ecx, word ptr [rdx]
0x180005010  test    cx, cx
0x180005013  jz      short loc_180005029
0x180005015  mov     [rax], cx
0x180005018  add     rdx, 2
0x18000501c  add     rax, 2
0x180005020  dec     r15
0x180005023  sub     rsi, 1
0x180005027  jnz     short loc_180005008
0x180005029  test    rsi, rsi
0x18000502c  lea     rcx, [rax-2]
0x180005030  mov     edi, 8007007Ah
0x180005035  cmovnz  rcx, rax
0x180005039  xor     eax, eax
0x18000503b  test    rsi, rsi
0x18000503e  cmovnz  edi, eax
0x180005041  mov     [rcx], ax
0x180005044  test    edi, edi
0x180005046  js      loc_180004F3A
0x18000504c  lea     rax, [rsp+4C0h+nLengthNeeded]
0x180005051  mov     [rsp+4C0h+nLengthNeeded], 0
0x180005059  xor     r9d, r9d; nLength
0x18000505c  mov     qword ptr [rsp+4C0h+bIgnoreCase], rax; lpnLengthNeeded
0x180005061  xor     r8d, r8d; pSecurityDescriptor
0x180005064  mov     edx, 7; RequestedInformation
0x180005069  mov     rcx, r14; lpFileName
0x18000506c  call    cs:__imp_GetFileSecurityW
0x180005072  test    eax, eax
0x180005074  jnz     short loc_180005098
0x180005076  call    ?ResultFromKnownLastError@@YAJXZ
0x18000507b  cmp     eax, 8007007Ah
0x180005080  jnz     short loc_180005098
0x180005082  mov     ecx, [rsp+4C0h+nLengthNeeded]; cb
0x180005086  call    cs:__imp_CoTaskMemAlloc
0x18000508c  mov     rbx, rax
0x18000508f  test    rax, rax
0x180005092  jnz     loc_18000512C
0x180005098  xor     r9d, r9d; SecurityDescriptorSize
0x18000509b  mov     qword ptr [rsp+4C0h+nLengthNeeded], 0
0x1800050a4  lea     r8, [rsp+4C0h+nLengthNeeded]; SecurityDescriptor
0x1800050a9  mov     edx, 1; StringSDRevision
0x1800050ae  lea     rcx, [rsp+4C0h+pszPathOut]; StringSecurityDescriptor
0x1800050b3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800050b9  test    eax, eax
0x1800050bb  jz      loc_180005230
0x1800050c1  mov     r8, qword ptr [rsp+4C0h+nLengthNeeded]; pSecurityDescriptor
0x1800050c6  mov     edx, 7; SecurityInformation
0x1800050cb  mov     rcx, r14; lpFileName
0x1800050ce  call    cs:__imp_SetFileSecurityW
0x1800050d4  test    eax, eax
0x1800050d6  jnz     short loc_18000511A
0x1800050d8  call    ?ResultFromKnownLastError@@YAJXZ
0x1800050dd  mov     edi, eax
0x1800050df  cmp     eax, 80070002h
0x1800050e4  jnz     loc_180005250
0x1800050ea  mov     rax, qword ptr [rsp+4C0h+nLengthNeeded]
0x1800050ef  lea     rdx, [rsp+4C0h+SecurityAttributes]; lpSecurityAttributes
0x1800050f4  mov     [rsp+4C0h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800050f9  mov     rcx, r14; lpPathName
0x1800050fc  xor     eax, eax
0x1800050fe  mov     qword ptr [rsp+4C0h+SecurityAttributes.nLength], 18h
0x180005107  mov     qword ptr [rsp+4C0h+SecurityAttributes.bInheritHandle], rax
0x18000510c  call    cs:__imp_CreateDirectoryW
0x180005112  test    eax, eax
0x180005114  jz      loc_180005244
0x18000511a  xor     edi, edi
0x18000511c  mov     rcx, qword ptr [rsp+4C0h+nLengthNeeded]; hMem
0x180005121  call    cs:__imp_LocalFree
0x180005127  jmp     loc_180004F3A
0x18000512c  mov     rcx, rbx; void *
0x18000512f  xor     sil, sil
0x180005132  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z
0x180005137  mov     r8, rax; Size
0x18000513a  xor     edx, edx; Val
0x18000513c  mov     rcx, rbx; void *
0x18000513f  call    memset_0
0x180005144  mov     r9d, [rsp+4C0h+nLengthNeeded]; nLength
0x180005149  lea     rax, [rsp+4C0h+nLengthNeeded]
0x18000514e  mov     r8, rbx; pSecurityDescriptor
0x180005151  mov     qword ptr [rsp+4C0h+bIgnoreCase], rax; lpnLengthNeeded
0x180005156  mov     edx, 7; RequestedInformation
0x18000515b  mov     rcx, r14; lpFileName
0x18000515e  call    cs:__imp_GetFileSecurityW
0x180005164  test    eax, eax
0x180005166  jz      short loc_180005191
0x180005168  xor     eax, eax
0x18000516a  lea     r9, [rsp+4C0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000516f  mov     edx, 1; RequestedStringSDRevision
0x180005174  mov     [rsp+4C0h+StringSecurityDescriptor], rax
0x180005179  mov     r8d, 7; SecurityInformation
0x18000517f  mov     qword ptr [rsp+4C0h+bIgnoreCase], rax; StringSecurityDescriptorLen
0x180005184  mov     rcx, rbx; SecurityDescriptor
0x180005187  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18000518d  test    eax, eax
0x18000518f  jnz     short loc_1800051A8
0x180005191  mov     rcx, rbx; pv
0x180005194  call    cs:__imp_CoTaskMemFree
0x18000519a  test    sil, sil
0x18000519d  jnz     loc_180004F3A
0x1800051a3  jmp     loc_180005098
0x1800051a8  mov     rcx, [rsp+4C0h+StringSecurityDescriptor]; lpString1
0x1800051ad  lea     r8, [rsp+4C0h+pszPathOut]; lpString2
0x1800051b2  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800051b8  mov     [rsp+4C0h+bIgnoreCase], 1; bIgnoreCase
0x1800051c0  mov     edx, r9d; cchCount1
0x1800051c3  call    cs:__imp_CompareStringOrdinal
0x1800051c9  mov     rcx, [rsp+4C0h+StringSecurityDescriptor]; hMem
0x1800051ce  cmp     eax, 2
0x1800051d1  setz    sil
0x1800051d5  call    cs:__imp_LocalFree
0x1800051db  jmp     short loc_180005191
0x1800051dd  lea     rdx, SubStr
0x1800051e4  mov     word ptr [rax], 5Ch ; '\'
0x1800051e9  mov     rcx, rax; Str
0x1800051ec  call    cs:__imp_wcsstr
0x1800051f2  test    rax, rax
0x1800051f5  jnz     short loc_1800051DD
0x1800051f7  jmp     loc_180004EE0
0x1800051fc  test    r13b, 1
0x180005200  lea     rax, off_1800E6010
0x180005207  lea     r9, aBu
0x18000520e  mov     rdx, rsi; unsigned __int64
0x180005211  cmovz   r9, [rsp+4C0h+StringSecurityDescriptor]
0x180005217  lea     r8, [r12+r12*2]
0x18000521b  mov     r8, [rax+r8*8]; unsigned __int16 *
0x18000521f  lea     rcx, [rsp+4C0h+pszPathOut]; unsigned __int16 *
0x180005224  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ
0x180005229  mov     edi, eax
0x18000522b  jmp     loc_180005044
0x180005230  call    ?ResultFromKnownLastError@@YAJXZ
0x180005235  mov     edi, eax
0x180005237  test    eax, eax
0x180005239  js      loc_180004F3A
0x18000523f  jmp     loc_1800050C1
0x180005244  call    ?ResultFromKnownLastError@@YAJXZ
0x180005249  mov     edi, eax
0x18000524b  jmp     loc_18000511C
0x180005250  xor     eax, eax
0x180005252  cmp     edi, 80070005h
0x180005258  cmovz   edi, eax
0x18000525b  jmp     loc_18000511C
```
