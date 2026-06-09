# sub_1800ECB2C

- ea: `0x1800ecb2c`
- end: `0x1800ed0ee`
- name: `sub_1800ECB2C`
- size: `1474`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800fa1e0`

## callees

- `0x18003708c`
- `0x1800399c0`
- `0x18003b30c`
- `0x18003b920`
- `0x18003dee4`
- `0x18003dfb8`
- `0x18003f010`
- `0x18003f438`
- `0x18003f488`
- `0x18003f4cc`
- `0x18003f6d0`
- `0x180041800`
- `0x180067aa0`
- `0x180067aec`
- `0x1800a9750`
- `0x1800a98e0`
- `0x1800a9a54`
- `0x1800a9d44`
- `0x1800ecb2c`
- `0x18014721c`
- `0x180473c00`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1800ecd99`
- `KERNEL32!GetCurrentProcess` at `0x1800ecd99`
- `KERNEL32!CloseHandle` at `0x1800ecdab`
- `KERNEL32!CloseHandle` at `0x1800ecdfc`
- `KERNEL32!CloseHandle` at `0x1800ed00e`
- `KERNEL32!CloseHandle` at `0x1800ed047`
- `KERNEL32!CloseHandle` at `0x1800ed0bc`
- `KERNEL32!CloseHandle` at `0x1800ecdab`
- `KERNEL32!CloseHandle` at `0x1800ecdfc`
- `KERNEL32!CloseHandle` at `0x1800ed00e`
- `KERNEL32!CloseHandle` at `0x1800ed047`
- `KERNEL32!CloseHandle` at `0x1800ed0bc`
- `ADVAPI32!RegCloseKey` at `0x1800ecc28`
- `ADVAPI32!RegCloseKey` at `0x1800ecd65`
- `ADVAPI32!RegCloseKey` at `0x1800ecc28`
- `ADVAPI32!RegCloseKey` at `0x1800ecd65`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800ecf6e`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800ecf6e`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1800ecee4`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1800ecee4`

## string_xrefs

- `0x1800ecb59`: `SeImpersonatePrivilege`
- `0x1800ecc9d`: `SeImpersonatePrivilege`
- `0x1800ecea7`: `SeImpersonatePrivilege`
- `0x1800ecba8`: `SYSTEM\CurrentControlSet\Services\WinDefend`
- `0x1800ecc49`: `RequiredPrivileges`
- `0x1800ecce8`: `RequiredPrivileges`

## pseudocode

```c
__int64 sub_1800ECB2C()
{
  __int64 v0; // rdi
  unsigned int v1; // r14d
  __int64 v2; // rdx
  __int64 v3; // rcx
  int v4; // eax
  int v5; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rdx
  HANDLE CurrentProcess; // rbx
  int v12; // eax
  int v13; // eax
  void *v14; // rcx
  unsigned __int64 v15; // rdx
  struct _LUID *v16; // rbx
  __int64 v17; // rdi
  const WCHAR *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  struct _TOKEN_PRIVILEGES *v21; // r8
  int v22; // edi
  int v23; // esi
  __int64 i; // r9
  __int64 v25; // r10
  __int64 v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // edi
  unsigned int v29; // eax
  HANDLE hObject; // [rsp+30h] [rbp-40h] BYREF
  PTOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  __int64 v34; // [rsp+50h] [rbp-20h] BYREF
  __int128 v35; // [rsp+58h] [rbp-18h] BYREF

  v0 = sub_18003F488(L"SeImpersonatePrivilege");
  v1 = sub_18003F438(v0, L"SeImpersonatePrivilege");
  if ( !(unsigned int)sub_18014721C(v3, v2) || !(unsigned int)sub_18003708C() )
    goto LABEL_37;
  if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 4) != 0 )
    sub_1800A9A54(
      *(_QWORD *)(*(_QWORD *)&NameType + 16LL),
      248,
      &stru_1804C4148,
      L"SYSTEM\\CurrentControlSet\\Services\\WinDefend");
  hKey = 0;
  v4 = sub_18003F4CC(&hKey, -2147483646, L"SYSTEM\\CurrentControlSet\\Services\\WinDefend", 131103);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 4) != 0 )
      sub_1800A9D44(
        *(_QWORD *)(*(_QWORD *)&NameType + 16LL),
        249,
        (unsigned int)&stru_1804C4148,
        (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\WinDefend",
        v4);
LABEL_10:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v5;
  }
  lpMem = 0;
  v34 = 0;
  v5 = sub_18003F010(hKey, L"RequiredPrivileges", &v34, &lpMem);
  if ( v5 < 0 )
  {
    v7 = *(_QWORD *)&NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
    {
      v8 = 250;
LABEL_17:
      sub_1800A9750(*(_QWORD *)(v7 + 16), v8, &stru_1804C4148, (unsigned int)v5);
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  if ( v34 != v0 || (unsigned int)sub_180473C00(lpMem, L"SeImpersonatePrivilege", 2 * v34) )
  {
    v5 = sub_18003F6D0(
           (_DWORD)hKey,
           (unsigned int)L"RequiredPrivileges",
           7,
           2 * (int)v0,
           (__int64)L"SeImpersonatePrivilege");
    if ( v5 < 0 )
    {
      v7 = *(_QWORD *)&NameType;
      if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      {
        v8 = 252;
        goto LABEL_17;
      }
LABEL_18:
      if ( lpMem )
        sub_180067AEC(lpMem);
      goto LABEL_10;
    }
    v9 = *(_QWORD *)&NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 4) != 0 )
    {
      v10 = 253;
      goto LABEL_32;
    }
  }
  else
  {
    v9 = *(_QWORD *)&NameType;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 4) != 0 )
    {
      v10 = 251;
LABEL_32:
      sub_1800A9A54(*(_QWORD *)(v9 + 16), v10, &stru_1804C4148, L"SYSTEM\\CurrentControlSet\\Services\\WinDefend");
      v9 = *(_QWORD *)&NameType;
    }
  }
  if ( lpMem )
  {
    sub_180067AEC(lpMem);
    v9 = *(_QWORD *)&NameType;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
LABEL_37:
    v9 = *(_QWORD *)&NameType;
  }
  if ( (COMPUTER_NAME_FORMAT *)v9 != &NameType && (*(_BYTE *)(v9 + 28) & 4) != 0 )
    sub_1800A9750(*(_QWORD *)(v9 + 16), 254, &stru_1804C4148, v1);
  hObject = 0;
  CurrentProcess = GetCurrentProcess();
  v12 = sub_18003B30C(&hObject, CurrentProcess, 40);
  v5 = v12;
  if ( v12 < 0 )
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 255, &stru_1804C4148, (unsigned int)v12);
LABEL_45:
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)v5;
  }
  NewState = 0;
  v13 = sub_180041800(&NewState, hObject, 3);
  v5 = v13;
  if ( v13 < 0 )
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 256, &stru_1804C4148, (unsigned int)v13);
LABEL_51:
    if ( NewState )
      sub_180067AEC(NewState);
    goto LABEL_45;
  }
  v14 = 0;
  v15 = 8LL * v1;
  lpMem = 0;
  if ( v15 < 8 )
  {
    v5 = -2147024809;
    goto LABEL_57;
  }
  _mm_lfence();
  v5 = sub_18003B920(&lpMem, v15);
  if ( v5 < 0 )
  {
    v14 = lpMem;
LABEL_57:
    if ( v14 )
      sub_180067AEC(v14);
    goto LABEL_51;
  }
  v35 = 0;
  sub_18003DEE4(&v35, v0, L"SeImpersonatePrivilege");
  v16 = (struct _LUID *)lpMem;
  v17 = 0;
  if ( v1 )
  {
    while ( 1 )
    {
      v18 = (const WCHAR *)sub_18003DFB8(&v35);
      if ( !v18 )
      {
        if ( v16 )
          sub_180067AEC(v16);
        if ( NewState )
          sub_180067AEC(NewState);
        if ( hObject )
          CloseHandle(hObject);
        return 2147500037LL;
      }
      if ( !LookupPrivilegeValueW(0, v18, &v16[v17]) && (unsigned int)sub_1800399C0(v19) != -2147023583 )
        break;
      v17 = (unsigned int)(v17 + 1);
      if ( (unsigned int)v17 >= v1 )
        goto LABEL_64;
    }
    v29 = sub_1800399C0(v20);
    v28 = v29;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 257, &stru_1804C4148, v29);
    if ( !v16 )
      goto LABEL_81;
LABEL_80:
    sub_180067AEC(v16);
LABEL_81:
    if ( NewState )
      sub_180067AEC(NewState);
    if ( hObject )
      CloseHandle(hObject);
    return v28;
  }
LABEL_64:
  v21 = NewState;
  v22 = 0;
  v23 = 0;
  for ( i = 0; (unsigned int)i < NewState->PrivilegeCount; i = (unsigned int)(i + 1) )
  {
    v25 = 0;
    if ( v1 )
    {
      while ( *(_QWORD *)&v21->Privileges[i].Luid != *(_QWORD *)&v16[v25] )
      {
        v25 = (unsigned int)(v25 + 1);
        if ( (unsigned int)v25 >= v1 )
          goto LABEL_68;
      }
      v21->Privileges[i].Attributes = 2;
      ++v22;
    }
    else
    {
LABEL_68:
      ++v23;
      v21->Privileges[i].Attributes = 4;
    }
    v21 = NewState;
  }
  if ( !AdjustTokenPrivileges(hObject, 0, v21, 0, 0, 0) )
  {
    v27 = sub_1800399C0(v26);
    v28 = v27;
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 258, &stru_1804C4148, v27);
    if ( !v16 )
      goto LABEL_81;
    goto LABEL_80;
  }
  if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 4) != 0 )
    sub_1800A98E0(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 259, &stru_1804C4148);
  if ( v16 )
    sub_180067AEC(v16);
  if ( NewState )
    sub_180067AEC(NewState);
  if ( hObject )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x1800ecb2c  mov     rax, rsp
0x1800ecb2f  mov     [rax+8], rbx
0x1800ecb33  mov     [rax+10h], rsi
0x1800ecb37  mov     [rax+18h], rdi
0x1800ecb3b  mov     [rax+20h], r12
0x1800ecb3f  push    rbp
0x1800ecb40  push    r13
0x1800ecb42  push    r14
0x1800ecb44  mov     rbp, rsp
0x1800ecb47  sub     rsp, 70h
0x1800ecb4b  mov     rax, cs:__security_cookie
0x1800ecb52  xor     rax, rsp
0x1800ecb55  mov     [rbp+var_8], rax
0x1800ecb59  lea     rbx, aSeimpersonatep; "SeImpersonatePrivilege"
0x1800ecb60  mov     rcx, rbx
0x1800ecb63  call    sub_18003F488
0x1800ecb68  mov     rdx, rbx
0x1800ecb6b  mov     rcx, rax
0x1800ecb6e  mov     rdi, rax
0x1800ecb71  call    sub_18003F438
0x1800ecb76  mov     r14, rax
0x1800ecb79  call    sub_18014721C
0x1800ecb7e  lea     r12, NameType
0x1800ecb85  lea     r13, stru_1804C4148
0x1800ecb8c  test    eax, eax
0x1800ecb8e  jz      loc_1800ECD6B
0x1800ecb94  call    sub_18003708C
0x1800ecb99  test    eax, eax
0x1800ecb9b  jz      loc_1800ECD6B
0x1800ecba1  mov     rcx, cs:NameType
0x1800ecba8  lea     rsi, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Wi"...
0x1800ecbaf  cmp     rcx, r12
0x1800ecbb2  jz      short loc_1800ECBCE
0x1800ecbb4  test    byte ptr [rcx+1Ch], 4
0x1800ecbb8  jz      short loc_1800ECBCE
0x1800ecbba  mov     rcx, [rcx+10h]
0x1800ecbbe  mov     edx, 0F8h
0x1800ecbc3  mov     r9, rsi
0x1800ecbc6  mov     r8, r13
0x1800ecbc9  call    sub_1800A9A54
0x1800ecbce  mov     r9d, 2001Fh
0x1800ecbd4  mov     [rbp+hKey], 0
0x1800ecbdc  mov     r8, rsi
0x1800ecbdf  lea     rcx, [rbp+hKey]
0x1800ecbe3  mov     rdx, 0FFFFFFFF80000002h
0x1800ecbea  call    sub_18003F4CC
0x1800ecbef  mov     ebx, eax
0x1800ecbf1  test    eax, eax
0x1800ecbf3  jns     short loc_1800ECC35
0x1800ecbf5  mov     rcx, cs:NameType
0x1800ecbfc  cmp     rcx, r12
0x1800ecbff  jz      short loc_1800ECC1F
0x1800ecc01  test    byte ptr [rcx+1Ch], 4
0x1800ecc05  jz      short loc_1800ECC1F
0x1800ecc07  mov     rcx, [rcx+10h]
0x1800ecc0b  mov     edx, 0F9h
0x1800ecc10  mov     r9, rsi
0x1800ecc13  mov     dword ptr [rsp+70h+PreviousState], eax
0x1800ecc17  mov     r8, r13
0x1800ecc1a  call    sub_1800A9D44
0x1800ecc1f  mov     rcx, [rbp+hKey]; hKey
0x1800ecc23  test    rcx, rcx
0x1800ecc26  jz      short loc_1800ECC2E
0x1800ecc28  call    cs:__imp_RegCloseKey
0x1800ecc2e  mov     eax, ebx
0x1800ecc30  jmp     loc_1800ED0C4
0x1800ecc35  mov     rcx, [rbp+hKey]
0x1800ecc39  lea     r9, [rbp+lpMem]
0x1800ecc3d  lea     r8, [rbp+var_20]
0x1800ecc41  mov     [rbp+lpMem], 0
0x1800ecc49  lea     rdx, aRequiredprivil; "RequiredPrivileges"
0x1800ecc50  mov     [rbp+var_20], 0
0x1800ecc58  call    sub_18003F010
0x1800ecc5d  mov     ebx, eax
0x1800ecc5f  test    eax, eax
0x1800ecc61  jns     short loc_1800ECC99
0x1800ecc63  mov     rcx, cs:NameType
0x1800ecc6a  cmp     rcx, r12
0x1800ecc6d  jz      short loc_1800ECC89
0x1800ecc6f  test    byte ptr [rcx+1Ch], 1
0x1800ecc73  jz      short loc_1800ECC89
0x1800ecc75  mov     edx, 0FAh
0x1800ecc7a  mov     rcx, [rcx+10h]
0x1800ecc7e  mov     r9d, ebx
0x1800ecc81  mov     r8, r13
0x1800ecc84  call    sub_1800A9750
0x1800ecc89  mov     rcx, [rbp+lpMem]; lpMem
0x1800ecc8d  test    rcx, rcx
0x1800ecc90  jz      short loc_1800ECC1F
0x1800ecc92  call    sub_180067AEC
0x1800ecc97  jmp     short loc_1800ECC1F
0x1800ecc99  mov     r8, [rbp+var_20]
0x1800ecc9d  lea     rbx, aSeimpersonatep; "SeImpersonatePrivilege"
0x1800ecca4  cmp     r8, rdi
0x1800ecca7  jnz     short loc_1800ECCD5
0x1800ecca9  mov     rcx, [rbp+lpMem]
0x1800eccad  add     r8, r8
0x1800eccb0  mov     rdx, rbx
0x1800eccb3  call    sub_180473C00
0x1800eccb8  test    eax, eax
0x1800eccba  jnz     short loc_1800ECCD5
0x1800eccbc  mov     rax, cs:NameType
0x1800eccc3  cmp     rax, r12
0x1800eccc6  jz      short loc_1800ECD47
0x1800eccc8  test    byte ptr [rax+1Ch], 4
0x1800ecccc  jz      short loc_1800ECD47
0x1800eccce  mov     edx, 0FBh
0x1800eccd3  jmp     short loc_1800ECD31
0x1800eccd5  mov     rcx, [rbp+hKey]
0x1800eccd9  lea     r9, [rdi+rdi]
0x1800eccdd  mov     r8d, 7
0x1800ecce3  mov     [rsp+70h+PreviousState], rbx
0x1800ecce8  lea     rdx, aRequiredprivil; "RequiredPrivileges"
0x1800eccef  call    sub_18003F6D0
0x1800eccf4  mov     ebx, eax
0x1800eccf6  test    eax, eax
0x1800eccf8  jns     short loc_1800ECD1A
0x1800eccfa  mov     rcx, cs:NameType
0x1800ecd01  cmp     rcx, r12
0x1800ecd04  jz      short loc_1800ECC89
0x1800ecd06  test    byte ptr [rcx+1Ch], 1
0x1800ecd0a  jz      loc_1800ECC89
0x1800ecd10  mov     edx, 0FCh
0x1800ecd15  jmp     loc_1800ECC7A
0x1800ecd1a  mov     rax, cs:NameType
0x1800ecd21  cmp     rax, r12
0x1800ecd24  jz      short loc_1800ECD47
0x1800ecd26  test    byte ptr [rax+1Ch], 4
0x1800ecd2a  jz      short loc_1800ECD47
0x1800ecd2c  mov     edx, 0FDh
0x1800ecd31  mov     rcx, [rax+10h]
0x1800ecd35  mov     r9, rsi
0x1800ecd38  mov     r8, r13
0x1800ecd3b  call    sub_1800A9A54
0x1800ecd40  mov     rax, cs:NameType
0x1800ecd47  mov     rcx, [rbp+lpMem]; lpMem
0x1800ecd4b  test    rcx, rcx
0x1800ecd4e  jz      short loc_1800ECD5C
0x1800ecd50  call    sub_180067AEC
0x1800ecd55  mov     rax, cs:NameType
0x1800ecd5c  mov     rcx, [rbp+hKey]; hKey
0x1800ecd60  test    rcx, rcx
0x1800ecd63  jz      short loc_1800ECD72
0x1800ecd65  call    cs:__imp_RegCloseKey
0x1800ecd6b  mov     rax, cs:NameType
0x1800ecd72  cmp     rax, r12
0x1800ecd75  jz      short loc_1800ECD91
0x1800ecd77  test    byte ptr [rax+1Ch], 4
0x1800ecd7b  jz      short loc_1800ECD91
0x1800ecd7d  mov     rcx, [rax+10h]
0x1800ecd81  mov     edx, 0FEh
0x1800ecd86  mov     r9d, r14d
0x1800ecd89  mov     r8, r13
0x1800ecd8c  call    sub_1800A9750
0x1800ecd91  mov     [rbp+hObject], 0
0x1800ecd99  call    cs:GetCurrentProcess
0x1800ecd9f  mov     rcx, [rbp+hObject]; hObject
0x1800ecda3  mov     rbx, rax
0x1800ecda6  test    rcx, rcx
0x1800ecda9  jz      short loc_1800ECDB1
0x1800ecdab  call    cs:CloseHandle
0x1800ecdb1  mov     r8d, 28h ; '('
0x1800ecdb7  lea     rcx, [rbp+hObject]
0x1800ecdbb  mov     rdx, rbx
0x1800ecdbe  call    sub_18003B30C
0x1800ecdc3  mov     ebx, eax
0x1800ecdc5  test    eax, eax
0x1800ecdc7  jns     short loc_1800ECE07
0x1800ecdc9  mov     rcx, cs:NameType
0x1800ecdd0  cmp     rcx, r12
0x1800ecdd3  jz      short loc_1800ECDEF
0x1800ecdd5  test    byte ptr [rcx+1Ch], 1
0x1800ecdd9  jz      short loc_1800ECDEF
0x1800ecddb  mov     rcx, [rcx+10h]
0x1800ecddf  mov     edx, 0FFh
0x1800ecde4  mov     r9d, eax
0x1800ecde7  mov     r8, r13
0x1800ecdea  call    sub_1800A9750
0x1800ecdef  mov     rcx, [rbp+hObject]; hObject
0x1800ecdf3  test    rcx, rcx
0x1800ecdf6  jz      loc_1800ECC2E
0x1800ecdfc  call    cs:CloseHandle
0x1800ece02  jmp     loc_1800ECC2E
0x1800ece07  mov     rdx, [rbp+hObject]
0x1800ece0b  lea     rcx, [rbp+NewState]
0x1800ece0f  mov     r8d, 3
0x1800ece15  mov     [rbp+NewState], 0
0x1800ece1d  call    sub_180041800
0x1800ece22  mov     ebx, eax
0x1800ece24  test    eax, eax
0x1800ece26  jns     short loc_1800ECE63
0x1800ece28  mov     rcx, cs:NameType
0x1800ece2f  cmp     rcx, r12
0x1800ece32  jz      short loc_1800ECE4E
0x1800ece34  test    byte ptr [rcx+1Ch], 1
0x1800ece38  jz      short loc_1800ECE4E
0x1800ece3a  mov     rcx, [rcx+10h]
0x1800ece3e  mov     edx, 100h
0x1800ece43  mov     r9d, eax
0x1800ece46  mov     r8, r13
0x1800ece49  call    sub_1800A9750
0x1800ece4e  mov     rcx, [rbp+NewState]; lpMem
0x1800ece52  test    rcx, rcx
0x1800ece55  jz      short loc_1800ECDEF
0x1800ece57  mov     edx, 10h
0x1800ece5c  call    sub_180067AEC
0x1800ece61  jmp     short loc_1800ECDEF
0x1800ece63  xor     ecx, ecx
0x1800ece65  mov     edx, r14d
0x1800ece68  shl     rdx, 3
0x1800ece6c  mov     [rbp+lpMem], rcx
0x1800ece70  lea     esi, [rcx+8]
0x1800ece73  cmp     rdx, rsi
0x1800ece76  jnb     short loc_1800ECE7F
0x1800ece78  mov     ebx, 80070057h
0x1800ece7d  jmp     short loc_1800ECE95
0x1800ece7f  lfence
0x1800ece82  lea     rcx, [rbp+lpMem]
0x1800ece86  call    sub_18003B920
0x1800ece8b  mov     ebx, eax
0x1800ece8d  test    eax, eax
0x1800ece8f  jns     short loc_1800ECEA4
0x1800ece91  mov     rcx, [rbp+lpMem]; lpMem
0x1800ece95  test    rcx, rcx
0x1800ece98  jz      short loc_1800ECE4E
0x1800ece9a  mov     rdx, rsi
0x1800ece9d  call    sub_180067AEC
0x1800ecea2  jmp     short loc_1800ECE4E
0x1800ecea4  xorps   xmm0, xmm0
0x1800ecea7  lea     r8, aSeimpersonatep; "SeImpersonatePrivilege"
0x1800eceae  mov     rdx, rdi
0x1800eceb1  lea     rcx, [rbp+var_18]
0x1800eceb5  movups  [rbp+var_18], xmm0
0x1800eceb9  call    sub_18003DEE4
0x1800ecebe  mov     rbx, [rbp+lpMem]
0x1800ecec2  xor     edi, edi
0x1800ecec4  test    r14d, r14d
0x1800ecec7  jz      short loc_1800ECF05
0x1800ecec9  lea     rcx, [rbp+var_18]
0x1800ececd  call    sub_18003DFB8
0x1800eced2  test    rax, rax
0x1800eced5  jz      loc_1800ED01B
0x1800ecedb  lea     r8, [rbx+rdi*8]; lpLuid
0x1800ecedf  mov     rdx, rax; lpName
0x1800ecee2  xor     ecx, ecx; lpSystemName
0x1800ecee4  call    cs:LookupPrivilegeValueW
0x1800eceea  test    eax, eax
0x1800eceec  jnz     short loc_1800ECEFE
0x1800eceee  call    sub_1800399C0
0x1800ecef3  cmp     eax, 80070521h
0x1800ecef8  jnz     loc_1800ECFB5
0x1800ecefe  inc     edi
0x1800ecf00  cmp     edi, r14d
0x1800ecf03  jb      short loc_1800ECEC9
0x1800ecf05  mov     r8, [rbp+NewState]
0x1800ecf09  xor     edi, edi
0x1800ecf0b  xor     esi, esi
0x1800ecf0d  xor     r9d, r9d
0x1800ecf10  cmp     [r8], esi
0x1800ecf13  jbe     short loc_1800ECF53
0x1800ecf15  xor     r10d, r10d
0x1800ecf18  test    r14d, r14d
0x1800ecf1b  jz      short loc_1800ECF38
0x1800ecf1d  lea     r11, [r9+r9*2]
0x1800ecf21  mov     rax, [r8+r11*4+4]
0x1800ecf26  cmp     rax, [rbx+r10*8]
0x1800ecf2a  jz      loc_1800ED054
0x1800ecf30  inc     r10d
0x1800ecf33  cmp     r10d, r14d
0x1800ecf36  jb      short loc_1800ECF21
0x1800ecf38  lea     rax, [r9+r9*2]
0x1800ecf3c  inc     esi
0x1800ecf3e  mov     dword ptr [r8+rax*4+0Ch], 4
0x1800ecf47  mov     r8, [rbp+NewState]; NewState
0x1800ecf4b  inc     r9d
0x1800ecf4e  cmp     r9d, [r8]
0x1800ecf51  jb      short loc_1800ECF15
0x1800ecf53  mov     rcx, [rbp+hObject]; TokenHandle
0x1800ecf57  xor     r9d, r9d; BufferLength
0x1800ecf5a  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x1800ecf63  xor     edx, edx; DisableAllPrivileges
0x1800ecf65  mov     [rsp+70h+PreviousState], 0; PreviousState
0x1800ecf6e  call    cs:AdjustTokenPrivileges
0x1800ecf74  test    eax, eax
0x1800ecf76  jnz     loc_1800ED064
0x1800ecf7c  call    sub_1800399C0
0x1800ecf81  mov     edi, eax
0x1800ecf83  mov     rcx, cs:NameType
0x1800ecf8a  cmp     rcx, r12
0x1800ecf8d  jz      short loc_1800ECFA9
0x1800ecf8f  test    byte ptr [rcx+1Ch], 1
0x1800ecf93  jz      short loc_1800ECFA9
0x1800ecf95  mov     rcx, [rcx+10h]
0x1800ecf99  mov     edx, 102h
0x1800ecf9e  mov     r9d, eax
0x1800ecfa1  mov     r8, r13
0x1800ecfa4  call    sub_1800A9750
0x1800ecfa9  test    rbx, rbx
0x1800ecfac  jz      short loc_1800ECFF2
0x1800ecfae  mov     edx, 8
  ... truncated ...
```
