# SddlpGetRootDomainSid

- ea: `0x180052738`
- end: `0x180052b6b`
- name: `SddlpGetRootDomainSid`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18001d3d0`

## callees

- `0x18001ea04`
- `0x18001ea50`
- `0x180052738`
- `0x180066010`

## import_xrefs

- `msvcrt!tolower` at `0x180052aad`
- `msvcrt!tolower` at `0x180052ad0`
- `msvcrt!tolower` at `0x180052aad`
- `msvcrt!tolower` at `0x180052ad0`
- `msvcrt!strstr` at `0x180052a45`
- `msvcrt!strstr` at `0x180052a45`
- `msvcrt!strchr` at `0x180052a5f`
- `msvcrt!strchr` at `0x180052a5f`
- `KERNEL32!LoadLibraryA` at `0x1800527a1`
- `KERNEL32!LoadLibraryA` at `0x1800527a1`
- `KERNEL32!GetProcAddress` at `0x1800527c1`
- `KERNEL32!GetProcAddress` at `0x1800527d5`
- `KERNEL32!GetProcAddress` at `0x1800527e8`
- `KERNEL32!GetProcAddress` at `0x1800527fc`
- `KERNEL32!GetProcAddress` at `0x18005280f`
- `KERNEL32!GetProcAddress` at `0x180052823`
- `KERNEL32!GetProcAddress` at `0x180052837`
- `KERNEL32!GetProcAddress` at `0x18005284b`
- `KERNEL32!GetProcAddress` at `0x18005285e`
- `KERNEL32!GetProcAddress` at `0x180052875`
- `KERNEL32!GetProcAddress` at `0x1800527c1`
- `KERNEL32!GetProcAddress` at `0x1800527d5`
- `KERNEL32!GetProcAddress` at `0x1800527e8`
- `KERNEL32!GetProcAddress` at `0x1800527fc`
- `KERNEL32!GetProcAddress` at `0x18005280f`
- `KERNEL32!GetProcAddress` at `0x180052823`
- `KERNEL32!GetProcAddress` at `0x180052837`
- `KERNEL32!GetProcAddress` at `0x18005284b`
- `KERNEL32!GetProcAddress` at `0x18005285e`
- `KERNEL32!GetProcAddress` at `0x180052875`
- `KERNEL32!FreeLibrary` at `0x1800528ff`
- `KERNEL32!FreeLibrary` at `0x1800528ff`
- `KERNEL32!SetLastError` at `0x180052907`
- `KERNEL32!SetLastError` at `0x180052907`

## string_xrefs

- `0x180052766`: `wldap32.dll`
- `0x180052a3e`: `<SID=`

## pseudocode

```c
__int64 SddlpGetRootDomainSid()
{
  unsigned int v0; // ebx
  HMODULE LibraryA; // rax
  HMODULE v2; // r15
  FARPROC v3; // rsi
  FARPROC v4; // rdi
  FARPROC v5; // r14
  FARPROC v6; // r12
  FARPROC v7; // r13
  __int64 v8; // rax
  __int64 v9; // rbx
  DWORD v10; // esi
  unsigned int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rax
  const char **v15; // rax
  const char *v16; // rcx
  char *v17; // rax
  char *v18; // r13
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rdx
  char *v23; // r13
  char *v24; // r12
  int v25; // r15d
  char v26; // r15
  char v27; // al
  char v28; // r15
  int v29; // eax
  FARPROC v30; // [rsp+60h] [rbp-59h]
  FARPROC v31; // [rsp+68h] [rbp-51h]
  FARPROC v32; // [rsp+70h] [rbp-49h]
  _QWORD v33[3]; // [rsp+78h] [rbp-41h] BYREF
  char v34; // [rsp+90h] [rbp-29h]
  int v35; // [rsp+91h] [rbp-28h]
  __int16 v36; // [rsp+95h] [rbp-24h]
  char v37; // [rsp+97h] [rbp-22h]
  INT_PTR (__stdcall *v38)(); // [rsp+98h] [rbp-21h]
  HMODULE v39; // [rsp+A0h] [rbp-19h]
  _QWORD v40[2]; // [rsp+A8h] [rbp-11h] BYREF
  _QWORD v41[11]; // [rsp+B8h] [rbp-1h] BYREF
  int v42; // [rsp+120h] [rbp+67h]
  __int64 *v43; // [rsp+120h] [rbp+67h]
  char *ProcAddress; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v45; // [rsp+130h] [rbp+77h]
  FARPROC v46; // [rsp+138h] [rbp+7Fh]

  v34 = 1;
  v33[1] = 0;
  v33[0] = "1.2.840.113556.1.4.529";
  v33[2] = 0;
  v35 = 0;
  v0 = 0;
  v36 = 0;
  v37 = 0;
  v40[0] = "rootDomainNamingContext";
  v41[0] = v33;
  v42 = 0;
  v40[1] = 0;
  v41[1] = 0;
  v45 = 0;
  LibraryA = LoadLibraryA("wldap32.dll");
  v39 = LibraryA;
  v2 = LibraryA;
  if ( !LibraryA )
    goto LABEL_45;
  ProcAddress = (char *)GetProcAddress(LibraryA, "ldap_initA");
  v3 = GetProcAddress(v2, "ldap_set_option");
  v46 = GetProcAddress(v2, "ldap_bind_sA");
  v4 = GetProcAddress(v2, "ldap_unbind");
  v30 = GetProcAddress(v2, "ldap_search_ext_sA");
  v31 = GetProcAddress(v2, "ldap_first_entry");
  v32 = GetProcAddress(v2, "ldap_get_valuesA");
  v5 = GetProcAddress(v2, "ldap_msgfree");
  v6 = GetProcAddress(v2, "ldap_value_freeA");
  v38 = v6;
  v7 = GetProcAddress(v2, "LdapMapErrorToWin32");
  if ( !ProcAddress )
    goto LABEL_45;
  if ( v3 && v46 && v4 && v30 && v31 && v32 && v5 && v6 && v7 )
  {
    v8 = ((__int64 (__fastcall *)(_QWORD, __int64))ProcAddress)(0, 389);
    v9 = v8;
    if ( v8 )
    {
      LODWORD(ProcAddress) = 1;
      v12 = ((__int64 (__fastcall *)(__int64, __int64, char **))v3)(v8, 150, &ProcAddress);
      v10 = ((__int64 (__fastcall *)(_QWORD))v7)(v12);
      if ( v10 )
        goto LABEL_44;
      v13 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64))v46)(v9, 0, 0, 1158);
      v10 = ((__int64 (__fastcall *)(_QWORD))v7)(v13);
      if ( !v10 )
      {
        v10 = ((__int64 (__fastcall *)(__int64, const unsigned __int8 *, _QWORD, const char *))v30)(
                v9,
                &ServerPrincName,
                0,
                "(objectClass=*)");
        if ( !v10 )
        {
          if ( v45 )
          {
            v14 = ((__int64 (__fastcall *)(__int64))v31)(v9);
            if ( v14
              && (v15 = (const char **)((__int64 (__fastcall *)(__int64, __int64, _QWORD))v32)(v9, v14, v40[0]),
                  (v46 = (FARPROC)v15) != 0) )
            {
              v16 = *v15;
              if ( *v15 && *v16 )
              {
                v17 = strstr(v16, "<SID=");
                v18 = v17;
                if ( v17 && (ProcAddress = strchr(v17, 62)) != 0 )
                {
                  v10 = 0;
                  EnterWaitSddlSidLookup();
                  v22 = RootDomSidBuf;
                  v43 = RootDomSidBuf;
                  v23 = v18 + 5;
                  if ( v23 < ProcAddress - 1 )
                  {
                    v24 = ProcAddress - 1;
                    do
                    {
                      v25 = *v23;
                      if ( (unsigned __int8)(*v23 - 48) > 9u )
                      {
                        v27 = tolower(v25);
                        v22 = v43;
                        v26 = v27 - 87;
                      }
                      else
                      {
                        v26 = v25 - 48;
                      }
                      v19 = (unsigned int)v23[1];
                      v28 = 16 * v26;
                      if ( (unsigned __int8)(v23[1] - 48) > 9u )
                      {
                        v29 = tolower(v19);
                        v22 = v43;
                        v19 = (unsigned int)(v29 - 87);
                      }
                      else
                      {
                        LOBYTE(v19) = v23[1] - 48;
                      }
                      LOBYTE(v19) = v28 + v19;
                      v23 += 2;
                      *(_BYTE *)v22 = v19;
                      v22 = (__int64 *)((char *)v22 + 1);
                      v43 = v22;
                    }
                    while ( v23 < v24 );
                    v6 = v38;
                    v2 = v39;
                  }
                  RootDomInited = 1;
                  LeaveWaitSddlSidLookup(v19, v22, v20, v21, v40, 0, v41);
                  v42 = 1;
                }
                else
                {
                  v10 = 4312;
                }
                ((void (__fastcall *)(FARPROC))v6)(v46);
              }
              else
              {
                v10 = 4312;
              }
            }
            else
            {
              v10 = ((__int64 (__fastcall *)(_QWORD))v7)(*(unsigned int *)(v9 + 116));
            }
            ((void (__fastcall *)(__int64))v5)(v45);
          }
        }
      }
      if ( v9 )
LABEL_44:
        ((void (__fastcall *)(__int64))v4)(v9);
    }
    else
    {
      v10 = 8207;
    }
    v0 = v42;
  }
  else
  {
LABEL_45:
    v10 = 127;
    if ( !v2 )
      goto LABEL_16;
  }
  FreeLibrary(v2);
LABEL_16:
  SetLastError(v10);
  return v0;
}

```

## disassembly

```asm
0x180052738  push    rbp
0x18005273a  push    rbx
0x18005273b  push    rsi
0x18005273c  push    rdi
0x18005273d  push    r12
0x18005273f  push    r13
0x180052741  push    r14
0x180052743  push    r15
0x180052745  lea     rbp, [rsp-1Fh]
0x18005274a  sub     rsp, 0D8h
0x180052751  xor     esi, esi
0x180052753  mov     [rbp+57h+var_80], 1
0x180052757  lea     rax, a12840113556145; "1.2.840.113556.1.4.529"
0x18005275e  mov     [rbp+57h+var_90], rsi
0x180052762  mov     [rbp+57h+var_98], rax
0x180052766  lea     rcx, aWldap32Dll; "wldap32.dll"
0x18005276d  xor     eax, eax
0x18005276f  mov     [rbp+57h+var_88], rsi
0x180052773  mov     [rbp+57h+var_7F], eax
0x180052776  mov     ebx, esi
0x180052778  mov     [rbp+57h+var_7B], ax
0x18005277c  mov     [rbp+57h+var_79], al
0x18005277f  lea     rax, aRootdomainnami; "rootDomainNamingContext"
0x180052786  mov     [rbp+57h+var_68], rax
0x18005278a  lea     rax, [rbp+57h+var_98]
0x18005278e  mov     [rbp+57h+var_58], rax
0x180052792  mov     dword ptr [rbp+57h+arg_0], ebx
0x180052795  mov     [rbp+57h+var_60], rsi
0x180052799  mov     [rbp+57h+var_50], rsi
0x18005279d  mov     [rbp+57h+arg_10], rsi
0x1800527a1  call    cs:__imp_LoadLibraryA
0x1800527a7  mov     [rbp+57h+var_70], rax
0x1800527ab  mov     r15, rax
0x1800527ae  test    rax, rax
0x1800527b1  jz      loc_180052B58
0x1800527b7  lea     rdx, aLdapInita; "ldap_initA"
0x1800527be  mov     rcx, rax; hModule
0x1800527c1  call    cs:__imp_GetProcAddress
0x1800527c7  lea     rdx, aLdapSetOption; "ldap_set_option"
0x1800527ce  mov     rcx, r15; hModule
0x1800527d1  mov     [rbp+57h+arg_8], rax
0x1800527d5  call    cs:__imp_GetProcAddress
0x1800527db  lea     rdx, aLdapBindSa; "ldap_bind_sA"
0x1800527e2  mov     rcx, r15; hModule
0x1800527e5  mov     rsi, rax
0x1800527e8  call    cs:__imp_GetProcAddress
0x1800527ee  lea     rdx, aLdapUnbind; "ldap_unbind"
0x1800527f5  mov     rcx, r15; hModule
0x1800527f8  mov     [rbp+57h+arg_18], rax
0x1800527fc  call    cs:__imp_GetProcAddress
0x180052802  lea     rdx, aLdapSearchExtS; "ldap_search_ext_sA"
0x180052809  mov     rcx, r15; hModule
0x18005280c  mov     rdi, rax
0x18005280f  call    cs:__imp_GetProcAddress
0x180052815  lea     rdx, aLdapFirstEntry; "ldap_first_entry"
0x18005281c  mov     rcx, r15; hModule
0x18005281f  mov     [rbp+57h+var_B0], rax
0x180052823  call    cs:__imp_GetProcAddress
0x180052829  lea     rdx, aLdapGetValuesa; "ldap_get_valuesA"
0x180052830  mov     rcx, r15; hModule
0x180052833  mov     [rbp+57h+var_A8], rax
0x180052837  call    cs:__imp_GetProcAddress
0x18005283d  lea     rdx, aLdapMsgfree; "ldap_msgfree"
0x180052844  mov     rcx, r15; hModule
0x180052847  mov     [rbp+57h+var_A0], rax
0x18005284b  call    cs:__imp_GetProcAddress
0x180052851  lea     rdx, aLdapValueFreea; "ldap_value_freeA"
0x180052858  mov     rcx, r15; hModule
0x18005285b  mov     r14, rax
0x18005285e  call    cs:__imp_GetProcAddress
0x180052864  lea     rdx, aLdapmaperrorto; "LdapMapErrorToWin32"
0x18005286b  mov     rcx, r15; hModule
0x18005286e  mov     r12, rax
0x180052871  mov     [rbp+57h+var_78], rax
0x180052875  call    cs:__imp_GetProcAddress
0x18005287b  mov     r13, rax
0x18005287e  mov     rax, [rbp+57h+arg_8]
0x180052882  test    rax, rax
0x180052885  jz      loc_180052B58
0x18005288b  test    rsi, rsi
0x18005288e  jz      loc_180052B58
0x180052894  cmp     [rbp+57h+arg_18], rbx
0x180052898  jz      loc_180052B58
0x18005289e  test    rdi, rdi
0x1800528a1  jz      loc_180052B58
0x1800528a7  cmp     [rbp+57h+var_B0], rbx
0x1800528ab  jz      loc_180052B58
0x1800528b1  cmp     [rbp+57h+var_A8], rbx
0x1800528b5  jz      loc_180052B58
0x1800528bb  cmp     [rbp+57h+var_A0], rbx
0x1800528bf  jz      loc_180052B58
0x1800528c5  test    r14, r14
0x1800528c8  jz      loc_180052B58
0x1800528ce  test    r12, r12
0x1800528d1  jz      loc_180052B58
0x1800528d7  test    r13, r13
0x1800528da  jz      loc_180052B58
0x1800528e0  mov     edx, 185h
0x1800528e5  xor     ecx, ecx
0x1800528e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528ec  mov     rbx, rax
0x1800528ef  test    rax, rax
0x1800528f2  jnz     short loc_180052923
0x1800528f4  mov     esi, 200Fh
0x1800528f9  mov     ebx, dword ptr [rbp+57h+arg_0]
0x1800528fc  mov     rcx, r15; hLibModule
0x1800528ff  call    cs:__imp_FreeLibrary
0x180052905  mov     ecx, esi; dwErrCode
0x180052907  call    cs:__imp_SetLastError
0x18005290d  mov     eax, ebx
0x18005290f  add     rsp, 0D8h
0x180052916  pop     r15
0x180052918  pop     r14
0x18005291a  pop     r13
0x18005291c  pop     r12
0x18005291e  pop     rdi
0x18005291f  pop     rsi
0x180052920  pop     rbx
0x180052921  pop     rbp
0x180052922  retn
0x180052923  lea     r8, [rbp+57h+arg_8]
0x180052927  mov     dword ptr [rbp+57h+arg_8], 1
0x18005292e  mov     edx, 96h
0x180052933  mov     rcx, rbx
0x180052936  mov     rax, rsi
0x180052939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005293e  mov     ecx, eax
0x180052940  mov     rax, r13
0x180052943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052948  mov     esi, eax
0x18005294a  test    eax, eax
0x18005294c  jnz     loc_180052B48
0x180052952  mov     rax, [rbp+57h+arg_18]
0x180052956  mov     r9d, 486h
0x18005295c  xor     r8d, r8d
0x18005295f  xor     edx, edx
0x180052961  mov     rcx, rbx
0x180052964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052969  mov     ecx, eax
0x18005296b  mov     rax, r13
0x18005296e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052973  mov     esi, eax
0x180052975  test    eax, eax
0x180052977  jnz     loc_180052B36
0x18005297d  lea     rax, [rbp+57h+arg_10]
0x180052981  xor     r8d, r8d
0x180052984  mov     [rsp+110h+var_C0], rax
0x180052989  lea     r9, aObjectclass; "(objectClass=*)"
0x180052990  mov     [rsp+110h+var_C8], 2710h
0x180052998  lea     rax, [rbp+57h+var_58]
0x18005299c  mov     [rsp+110h+var_D0], 0
0x1800529a5  lea     rdx, ServerPrincName
0x1800529ac  mov     [rsp+110h+var_D8], 0
0x1800529b5  mov     rcx, rbx
0x1800529b8  mov     [rsp+110h+var_E0], rax
0x1800529bd  lea     rax, [rbp+57h+var_68]
0x1800529c1  mov     [rsp+110h+var_E8], esi
0x1800529c5  mov     [rsp+110h+var_F0], rax
0x1800529ca  mov     rax, [rbp+57h+var_B0]
0x1800529ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529d3  mov     esi, eax
0x1800529d5  test    eax, eax
0x1800529d7  jnz     loc_180052B36
0x1800529dd  mov     rdx, [rbp+57h+arg_10]
0x1800529e1  test    rdx, rdx
0x1800529e4  jz      loc_180052B36
0x1800529ea  mov     rax, [rbp+57h+var_A8]
0x1800529ee  mov     rcx, rbx
0x1800529f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529f6  test    rax, rax
0x1800529f9  jz      short loc_180052A17
0x1800529fb  mov     r8, [rbp+57h+var_68]
0x1800529ff  mov     rdx, rax
0x180052a02  mov     rax, [rbp+57h+var_A0]
0x180052a06  mov     rcx, rbx
0x180052a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a0e  mov     [rbp+57h+arg_18], rax
0x180052a12  test    rax, rax
0x180052a15  jnz     short loc_180052A29
0x180052a17  mov     ecx, [rbx+74h]
0x180052a1a  mov     rax, r13
0x180052a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a22  mov     esi, eax
0x180052a24  jmp     loc_180052B2A
0x180052a29  mov     rcx, [rax]; Str
0x180052a2c  test    rcx, rcx
0x180052a2f  jz      loc_180052B25
0x180052a35  cmp     byte ptr [rcx], 0
0x180052a38  jz      loc_180052B25
0x180052a3e  lea     rdx, aSid; "<SID="
0x180052a45  call    cs:__imp_strstr
0x180052a4b  mov     r13, rax
0x180052a4e  test    rax, rax
0x180052a51  jz      loc_180052B12
0x180052a57  mov     edx, 3Eh ; '>'; Val
0x180052a5c  mov     rcx, rax; Str
0x180052a5f  call    cs:__imp_strchr
0x180052a65  mov     [rbp+57h+arg_8], rax
0x180052a69  test    rax, rax
0x180052a6c  jz      loc_180052B12
0x180052a72  xor     esi, esi
0x180052a74  call    EnterWaitSddlSidLookup
0x180052a79  mov     rax, [rbp+57h+arg_8]
0x180052a7d  lea     rdx, RootDomSidBuf
0x180052a84  dec     rax
0x180052a87  mov     [rbp+57h+arg_0], rdx
0x180052a8b  add     r13, 5
0x180052a8f  cmp     r13, rax
0x180052a92  jnb     short loc_180052AFA
0x180052a94  mov     r12, rax
0x180052a97  movsx   r15d, byte ptr [r13+0]
0x180052a9c  lea     eax, [r15-30h]
0x180052aa0  cmp     al, 9
0x180052aa2  ja      short loc_180052AAA
0x180052aa4  sub     r15b, 30h ; '0'
0x180052aa8  jmp     short loc_180052ABB
0x180052aaa  mov     ecx, r15d; C
0x180052aad  call    cs:__imp_tolower
0x180052ab3  mov     rdx, [rbp+57h+arg_0]
0x180052ab7  lea     r15d, [rax-57h]
0x180052abb  movsx   ecx, byte ptr [r13+1]; C
0x180052ac0  shl     r15b, 4
0x180052ac4  lea     eax, [rcx-30h]
0x180052ac7  cmp     al, 9
0x180052ac9  ja      short loc_180052AD0
0x180052acb  sub     cl, 30h ; '0'
0x180052ace  jmp     short loc_180052ADD
0x180052ad0  call    cs:__imp_tolower
0x180052ad6  mov     rdx, [rbp+57h+arg_0]
0x180052ada  lea     ecx, [rax-57h]
0x180052add  add     cl, r15b
0x180052ae0  add     r13, 2
0x180052ae4  mov     [rdx], cl
0x180052ae6  inc     rdx
0x180052ae9  mov     [rbp+57h+arg_0], rdx
0x180052aed  cmp     r13, r12
0x180052af0  jb      short loc_180052A97
0x180052af2  mov     r12, [rbp+57h+var_78]
0x180052af6  mov     r15, [rbp+57h+var_70]
0x180052afa  mov     cs:RootDomInited, 1
0x180052b04  call    LeaveWaitSddlSidLookup
0x180052b09  mov     dword ptr [rbp+57h+arg_0], 1
0x180052b10  jmp     short loc_180052B17
0x180052b12  mov     esi, 10D8h
0x180052b17  mov     rcx, [rbp+57h+arg_18]
0x180052b1b  mov     rax, r12
0x180052b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b23  jmp     short loc_180052B2A
0x180052b25  mov     esi, 10D8h
0x180052b2a  mov     rcx, [rbp+57h+arg_10]
0x180052b2e  mov     rax, r14
0x180052b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b36  test    rbx, rbx
0x180052b39  jz      loc_1800528F9
0x180052b3f  test    rdi, rdi
0x180052b42  jz      loc_1800528F9
0x180052b48  mov     rcx, rbx
0x180052b4b  mov     rax, rdi
0x180052b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b53  jmp     loc_1800528F9
0x180052b58  mov     esi, 7Fh
0x180052b5d  test    r15, r15
0x180052b60  jz      loc_180052905
0x180052b66  jmp     loc_1800528FC
```
