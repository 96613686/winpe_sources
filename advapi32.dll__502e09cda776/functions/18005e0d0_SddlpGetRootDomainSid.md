# SddlpGetRootDomainSid

- ea: `0x18005e0d0`
- end: `0x18005e56a`
- name: `SddlpGetRootDomainSid`
- size: `1178`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18001c000`

## callees

- `0x18001d86c`
- `0x18001d8c4`
- `0x18005e0d0`
- `0x180074010`

## import_xrefs

- `msvcrt!tolower` at `0x18005e4a0`
- `msvcrt!tolower` at `0x18005e4c9`
- `msvcrt!tolower` at `0x18005e4a0`
- `msvcrt!tolower` at `0x18005e4c9`
- `msvcrt!strstr` at `0x18005e42c`
- `msvcrt!strstr` at `0x18005e42c`
- `msvcrt!strchr` at `0x18005e44c`
- `msvcrt!strchr` at `0x18005e44c`
- `KERNEL32!LoadLibraryA` at `0x18005e139`
- `KERNEL32!LoadLibraryA` at `0x18005e139`
- `KERNEL32!GetProcAddress` at `0x18005e15f`
- `KERNEL32!GetProcAddress` at `0x18005e179`
- `KERNEL32!GetProcAddress` at `0x18005e192`
- `KERNEL32!GetProcAddress` at `0x18005e1ac`
- `KERNEL32!GetProcAddress` at `0x18005e1c5`
- `KERNEL32!GetProcAddress` at `0x18005e1df`
- `KERNEL32!GetProcAddress` at `0x18005e1f9`
- `KERNEL32!GetProcAddress` at `0x18005e213`
- `KERNEL32!GetProcAddress` at `0x18005e22c`
- `KERNEL32!GetProcAddress` at `0x18005e249`
- `KERNEL32!GetProcAddress` at `0x18005e15f`
- `KERNEL32!GetProcAddress` at `0x18005e179`
- `KERNEL32!GetProcAddress` at `0x18005e192`
- `KERNEL32!GetProcAddress` at `0x18005e1ac`
- `KERNEL32!GetProcAddress` at `0x18005e1c5`
- `KERNEL32!GetProcAddress` at `0x18005e1df`
- `KERNEL32!GetProcAddress` at `0x18005e1f9`
- `KERNEL32!GetProcAddress` at `0x18005e213`
- `KERNEL32!GetProcAddress` at `0x18005e22c`
- `KERNEL32!GetProcAddress` at `0x18005e249`
- `KERNEL32!FreeLibrary` at `0x18005e2d9`
- `KERNEL32!FreeLibrary` at `0x18005e2d9`
- `KERNEL32!SetLastError` at `0x18005e2e7`
- `KERNEL32!SetLastError` at `0x18005e2e7`

## string_xrefs

- `0x18005e0fe`: `wldap32.dll`
- `0x18005e425`: `<SID=`

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
0x18005e0d0  push    rbp
0x18005e0d2  push    rbx
0x18005e0d3  push    rsi
0x18005e0d4  push    rdi
0x18005e0d5  push    r12
0x18005e0d7  push    r13
0x18005e0d9  push    r14
0x18005e0db  push    r15
0x18005e0dd  lea     rbp, [rsp-1Fh]
0x18005e0e2  sub     rsp, 0D8h
0x18005e0e9  xor     esi, esi
0x18005e0eb  mov     [rbp+57h+var_80], 1
0x18005e0ef  lea     rax, a12840113556145; "1.2.840.113556.1.4.529"
0x18005e0f6  mov     [rbp+57h+var_90], rsi
0x18005e0fa  mov     [rbp+57h+var_98], rax
0x18005e0fe  lea     rcx, aWldap32Dll; "wldap32.dll"
0x18005e105  xor     eax, eax
0x18005e107  mov     [rbp+57h+var_88], rsi
0x18005e10b  mov     [rbp+57h+var_7F], eax
0x18005e10e  mov     ebx, esi
0x18005e110  mov     [rbp+57h+var_7B], ax
0x18005e114  mov     [rbp+57h+var_79], al
0x18005e117  lea     rax, aRootdomainnami; "rootDomainNamingContext"
0x18005e11e  mov     [rbp+57h+var_68], rax
0x18005e122  lea     rax, [rbp+57h+var_98]
0x18005e126  mov     [rbp+57h+var_58], rax
0x18005e12a  mov     dword ptr [rbp+57h+arg_0], ebx
0x18005e12d  mov     [rbp+57h+var_60], rsi
0x18005e131  mov     [rbp+57h+var_50], rsi
0x18005e135  mov     [rbp+57h+arg_10], rsi
0x18005e139  call    cs:__imp_LoadLibraryA
0x18005e140  nop     dword ptr [rax+rax+00h]
0x18005e145  mov     [rbp+57h+var_70], rax
0x18005e149  mov     r15, rax
0x18005e14c  test    rax, rax
0x18005e14f  jz      loc_18005E557
0x18005e155  lea     rdx, aLdapInita; "ldap_initA"
0x18005e15c  mov     rcx, rax; hModule
0x18005e15f  call    cs:__imp_GetProcAddress
0x18005e166  nop     dword ptr [rax+rax+00h]
0x18005e16b  lea     rdx, aLdapSetOption; "ldap_set_option"
0x18005e172  mov     rcx, r15; hModule
0x18005e175  mov     [rbp+57h+arg_8], rax
0x18005e179  call    cs:__imp_GetProcAddress
0x18005e180  nop     dword ptr [rax+rax+00h]
0x18005e185  lea     rdx, aLdapBindSa; "ldap_bind_sA"
0x18005e18c  mov     rcx, r15; hModule
0x18005e18f  mov     rsi, rax
0x18005e192  call    cs:__imp_GetProcAddress
0x18005e199  nop     dword ptr [rax+rax+00h]
0x18005e19e  lea     rdx, aLdapUnbind; "ldap_unbind"
0x18005e1a5  mov     rcx, r15; hModule
0x18005e1a8  mov     [rbp+57h+arg_18], rax
0x18005e1ac  call    cs:__imp_GetProcAddress
0x18005e1b3  nop     dword ptr [rax+rax+00h]
0x18005e1b8  lea     rdx, aLdapSearchExtS; "ldap_search_ext_sA"
0x18005e1bf  mov     rcx, r15; hModule
0x18005e1c2  mov     rdi, rax
0x18005e1c5  call    cs:__imp_GetProcAddress
0x18005e1cc  nop     dword ptr [rax+rax+00h]
0x18005e1d1  lea     rdx, aLdapFirstEntry; "ldap_first_entry"
0x18005e1d8  mov     rcx, r15; hModule
0x18005e1db  mov     [rbp+57h+var_B0], rax
0x18005e1df  call    cs:__imp_GetProcAddress
0x18005e1e6  nop     dword ptr [rax+rax+00h]
0x18005e1eb  lea     rdx, aLdapGetValuesa; "ldap_get_valuesA"
0x18005e1f2  mov     rcx, r15; hModule
0x18005e1f5  mov     [rbp+57h+var_A8], rax
0x18005e1f9  call    cs:__imp_GetProcAddress
0x18005e200  nop     dword ptr [rax+rax+00h]
0x18005e205  lea     rdx, aLdapMsgfree; "ldap_msgfree"
0x18005e20c  mov     rcx, r15; hModule
0x18005e20f  mov     [rbp+57h+var_A0], rax
0x18005e213  call    cs:__imp_GetProcAddress
0x18005e21a  nop     dword ptr [rax+rax+00h]
0x18005e21f  lea     rdx, aLdapValueFreea; "ldap_value_freeA"
0x18005e226  mov     rcx, r15; hModule
0x18005e229  mov     r14, rax
0x18005e22c  call    cs:__imp_GetProcAddress
0x18005e233  nop     dword ptr [rax+rax+00h]
0x18005e238  lea     rdx, aLdapmaperrorto; "LdapMapErrorToWin32"
0x18005e23f  mov     rcx, r15; hModule
0x18005e242  mov     r12, rax
0x18005e245  mov     [rbp+57h+var_78], rax
0x18005e249  call    cs:__imp_GetProcAddress
0x18005e250  nop     dword ptr [rax+rax+00h]
0x18005e255  mov     r13, rax
0x18005e258  mov     rax, [rbp+57h+arg_8]
0x18005e25c  test    rax, rax
0x18005e25f  jz      loc_18005E557
0x18005e265  test    rsi, rsi
0x18005e268  jz      loc_18005E557
0x18005e26e  cmp     [rbp+57h+arg_18], rbx
0x18005e272  jz      loc_18005E557
0x18005e278  test    rdi, rdi
0x18005e27b  jz      loc_18005E557
0x18005e281  cmp     [rbp+57h+var_B0], rbx
0x18005e285  jz      loc_18005E557
0x18005e28b  cmp     [rbp+57h+var_A8], rbx
0x18005e28f  jz      loc_18005E557
0x18005e295  cmp     [rbp+57h+var_A0], rbx
0x18005e299  jz      loc_18005E557
0x18005e29f  test    r14, r14
0x18005e2a2  jz      loc_18005E557
0x18005e2a8  test    r12, r12
0x18005e2ab  jz      loc_18005E557
0x18005e2b1  test    r13, r13
0x18005e2b4  jz      loc_18005E557
0x18005e2ba  mov     edx, 185h
0x18005e2bf  xor     ecx, ecx
0x18005e2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2c6  mov     rbx, rax
0x18005e2c9  test    rax, rax
0x18005e2cc  jnz     short loc_18005E30A
0x18005e2ce  mov     esi, 200Fh
0x18005e2d3  mov     ebx, dword ptr [rbp+57h+arg_0]
0x18005e2d6  mov     rcx, r15; hLibModule
0x18005e2d9  call    cs:__imp_FreeLibrary
0x18005e2e0  nop     dword ptr [rax+rax+00h]
0x18005e2e5  mov     ecx, esi; dwErrCode
0x18005e2e7  call    cs:__imp_SetLastError
0x18005e2ee  nop     dword ptr [rax+rax+00h]
0x18005e2f3  mov     eax, ebx
0x18005e2f5  add     rsp, 0D8h
0x18005e2fc  pop     r15
0x18005e2fe  pop     r14
0x18005e300  pop     r13
0x18005e302  pop     r12
0x18005e304  pop     rdi
0x18005e305  pop     rsi
0x18005e306  pop     rbx
0x18005e307  pop     rbp
0x18005e308  retn
0x18005e30a  lea     r8, [rbp+57h+arg_8]
0x18005e30e  mov     dword ptr [rbp+57h+arg_8], 1
0x18005e315  mov     edx, 96h
0x18005e31a  mov     rcx, rbx
0x18005e31d  mov     rax, rsi
0x18005e320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e325  mov     ecx, eax
0x18005e327  mov     rax, r13
0x18005e32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e32f  mov     esi, eax
0x18005e331  test    eax, eax
0x18005e333  jnz     loc_18005E547
0x18005e339  mov     rax, [rbp+57h+arg_18]
0x18005e33d  mov     r9d, 486h
0x18005e343  xor     r8d, r8d
0x18005e346  xor     edx, edx
0x18005e348  mov     rcx, rbx
0x18005e34b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e350  mov     ecx, eax
0x18005e352  mov     rax, r13
0x18005e355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e35a  mov     esi, eax
0x18005e35c  test    eax, eax
0x18005e35e  jnz     loc_18005E535
0x18005e364  lea     rax, [rbp+57h+arg_10]
0x18005e368  xor     r8d, r8d
0x18005e36b  mov     [rsp+110h+var_C0], rax
0x18005e370  lea     r9, aObjectclass; "(objectClass=*)"
0x18005e377  mov     [rsp+110h+var_C8], 2710h
0x18005e37f  lea     rax, [rbp+57h+var_58]
0x18005e383  mov     [rsp+110h+var_D0], 0
0x18005e38c  lea     rdx, ServerPrincName
0x18005e393  mov     [rsp+110h+var_D8], 0
0x18005e39c  mov     rcx, rbx
0x18005e39f  mov     [rsp+110h+var_E0], rax
0x18005e3a4  lea     rax, [rbp+57h+var_68]
0x18005e3a8  mov     [rsp+110h+var_E8], esi
0x18005e3ac  mov     [rsp+110h+var_F0], rax
0x18005e3b1  mov     rax, [rbp+57h+var_B0]
0x18005e3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3ba  mov     esi, eax
0x18005e3bc  test    eax, eax
0x18005e3be  jnz     loc_18005E535
0x18005e3c4  mov     rdx, [rbp+57h+arg_10]
0x18005e3c8  test    rdx, rdx
0x18005e3cb  jz      loc_18005E535
0x18005e3d1  mov     rax, [rbp+57h+var_A8]
0x18005e3d5  mov     rcx, rbx
0x18005e3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3dd  test    rax, rax
0x18005e3e0  jz      short loc_18005E3FE
0x18005e3e2  mov     r8, [rbp+57h+var_68]
0x18005e3e6  mov     rdx, rax
0x18005e3e9  mov     rax, [rbp+57h+var_A0]
0x18005e3ed  mov     rcx, rbx
0x18005e3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3f5  mov     [rbp+57h+arg_18], rax
0x18005e3f9  test    rax, rax
0x18005e3fc  jnz     short loc_18005E410
0x18005e3fe  mov     ecx, [rbx+74h]
0x18005e401  mov     rax, r13
0x18005e404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e409  mov     esi, eax
0x18005e40b  jmp     loc_18005E529
0x18005e410  mov     rcx, [rax]; Str
0x18005e413  test    rcx, rcx
0x18005e416  jz      loc_18005E524
0x18005e41c  cmp     byte ptr [rcx], 0
0x18005e41f  jz      loc_18005E524
0x18005e425  lea     rdx, aSid; "<SID="
0x18005e42c  call    cs:__imp_strstr
0x18005e433  nop     dword ptr [rax+rax+00h]
0x18005e438  mov     r13, rax
0x18005e43b  test    rax, rax
0x18005e43e  jz      loc_18005E511
0x18005e444  mov     edx, 3Eh ; '>'; Val
0x18005e449  mov     rcx, rax; Str
0x18005e44c  call    cs:__imp_strchr
0x18005e453  nop     dword ptr [rax+rax+00h]
0x18005e458  mov     [rbp+57h+arg_8], rax
0x18005e45c  test    rax, rax
0x18005e45f  jz      loc_18005E511
0x18005e465  xor     esi, esi
0x18005e467  call    EnterWaitSddlSidLookup
0x18005e46c  mov     rax, [rbp+57h+arg_8]
0x18005e470  lea     rdx, RootDomSidBuf
0x18005e477  dec     rax
0x18005e47a  mov     [rbp+57h+arg_0], rdx
0x18005e47e  add     r13, 5
0x18005e482  cmp     r13, rax
0x18005e485  jnb     short loc_18005E4F9
0x18005e487  mov     r12, rax
0x18005e48a  movsx   r15d, byte ptr [r13+0]
0x18005e48f  lea     eax, [r15-30h]
0x18005e493  cmp     al, 9
0x18005e495  ja      short loc_18005E49D
0x18005e497  sub     r15b, 30h ; '0'
0x18005e49b  jmp     short loc_18005E4B4
0x18005e49d  mov     ecx, r15d; C
0x18005e4a0  call    cs:__imp_tolower
0x18005e4a7  nop     dword ptr [rax+rax+00h]
0x18005e4ac  mov     rdx, [rbp+57h+arg_0]
0x18005e4b0  lea     r15d, [rax-57h]
0x18005e4b4  movsx   ecx, byte ptr [r13+1]; C
0x18005e4b9  shl     r15b, 4
0x18005e4bd  lea     eax, [rcx-30h]
0x18005e4c0  cmp     al, 9
0x18005e4c2  ja      short loc_18005E4C9
0x18005e4c4  sub     cl, 30h ; '0'
0x18005e4c7  jmp     short loc_18005E4DC
0x18005e4c9  call    cs:__imp_tolower
0x18005e4d0  nop     dword ptr [rax+rax+00h]
0x18005e4d5  mov     rdx, [rbp+57h+arg_0]
0x18005e4d9  lea     ecx, [rax-57h]
0x18005e4dc  add     cl, r15b
0x18005e4df  add     r13, 2
0x18005e4e3  mov     [rdx], cl
0x18005e4e5  inc     rdx
0x18005e4e8  mov     [rbp+57h+arg_0], rdx
0x18005e4ec  cmp     r13, r12
0x18005e4ef  jb      short loc_18005E48A
0x18005e4f1  mov     r12, [rbp+57h+var_78]
0x18005e4f5  mov     r15, [rbp+57h+var_70]
0x18005e4f9  mov     cs:RootDomInited, 1
0x18005e503  call    LeaveWaitSddlSidLookup
0x18005e508  mov     dword ptr [rbp+57h+arg_0], 1
0x18005e50f  jmp     short loc_18005E516
0x18005e511  mov     esi, 10D8h
0x18005e516  mov     rcx, [rbp+57h+arg_18]
0x18005e51a  mov     rax, r12
0x18005e51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e522  jmp     short loc_18005E529
0x18005e524  mov     esi, 10D8h
0x18005e529  mov     rcx, [rbp+57h+arg_10]
0x18005e52d  mov     rax, r14
0x18005e530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e535  test    rbx, rbx
0x18005e538  jz      loc_18005E2D3
0x18005e53e  test    rdi, rdi
0x18005e541  jz      loc_18005E2D3
0x18005e547  mov     rcx, rbx
0x18005e54a  mov     rax, rdi
0x18005e54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e552  jmp     loc_18005E2D3
0x18005e557  mov     esi, 7Fh
0x18005e55c  test    r15, r15
0x18005e55f  jz      loc_18005E2E5
0x18005e565  jmp     loc_18005E2D6
```
