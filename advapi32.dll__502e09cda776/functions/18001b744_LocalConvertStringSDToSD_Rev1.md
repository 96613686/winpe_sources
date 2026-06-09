# LocalConvertStringSDToSD_Rev1

- ea: `0x18001b744`
- end: `0x18001bff3`
- name: `LocalConvertStringSDToSD_Rev1`
- size: `2223`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019e70`
- `0x18003452c`
- `0x18005e940`
- `0x18005eae0`

## callees

- `0x1800194f8`
- `0x180019ed0`
- `0x18001b744`
- `0x18001c000`
- `0x18001c890`
- `0x18001d86c`
- `0x18001d8c4`
- `0x180072042`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001bcae`
- `msvcrt!_wcsnicmp` at `0x18001bdbf`
- `msvcrt!_wcsnicmp` at `0x18001bcae`
- `msvcrt!_wcsnicmp` at `0x18001bdbf`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001b950`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001b950`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001bcf4`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001bcf4`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18001bb84`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18001bb84`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001b99e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001b99e`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001b9d1`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001ba19`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001b9d1`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001ba19`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18001bd2f`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18001bd2f`
- `ntdll!RtlNtStatusToDosError` at `0x18001ba3e`
- `ntdll!RtlNtStatusToDosError` at `0x18001bb9d`
- `ntdll!RtlNtStatusToDosError` at `0x18001bd0a`
- `ntdll!RtlNtStatusToDosError` at `0x18001bd45`
- `ntdll!RtlNtStatusToDosError` at `0x18001bf09`
- `ntdll!RtlNtStatusToDosError` at `0x18001bfc5`
- `ntdll!RtlNtStatusToDosError` at `0x18001ba3e`
- `ntdll!RtlNtStatusToDosError` at `0x18001bb9d`
- `ntdll!RtlNtStatusToDosError` at `0x18001bd0a`
- `ntdll!RtlNtStatusToDosError` at `0x18001bd45`
- `ntdll!RtlNtStatusToDosError` at `0x18001bf09`
- `ntdll!RtlNtStatusToDosError` at `0x18001bfc5`
- `KERNELBASE!LocalAlloc` at `0x18001b9f0`
- `KERNELBASE!LocalAlloc` at `0x18001bf3f`
- `KERNELBASE!LocalAlloc` at `0x18001b9f0`
- `KERNELBASE!LocalAlloc` at `0x18001bf3f`
- `KERNEL32!LocalFree` at `0x18001ba4f`
- `KERNEL32!LocalFree` at `0x18001ba88`
- `KERNEL32!LocalFree` at `0x18001ba98`
- `KERNEL32!LocalFree` at `0x18001baac`
- `KERNEL32!LocalFree` at `0x18001bc62`
- `KERNEL32!LocalFree` at `0x18001be19`
- `KERNEL32!LocalFree` at `0x18001ba4f`
- `KERNEL32!LocalFree` at `0x18001ba88`
- `KERNEL32!LocalFree` at `0x18001ba98`
- `KERNEL32!LocalFree` at `0x18001baac`
- `KERNEL32!LocalFree` at `0x18001bc62`
- `KERNEL32!LocalFree` at `0x18001be19`
- `KERNEL32!GetLastError` at `0x18001be72`
- `KERNEL32!GetLastError` at `0x18001bedc`
- `KERNEL32!GetLastError` at `0x18001be72`
- `KERNEL32!GetLastError` at `0x18001bedc`

## pseudocode

```c
__int64 __fastcall LocalConvertStringSDToSD_Rev1(__int64 a1, __int64 a2, __int64 a3, __int64 a4, HLOCAL *a5, ULONG *a6)
{
  wchar_t *v6; // rdi
  _BYTE *v7; // r14
  void *v8; // r15
  void *v9; // r12
  _BYTE *v10; // rdx
  HLOCAL v11; // rcx
  unsigned int AclForString; // ebx
  BOOLEAN v13; // r13
  char v14; // si
  wchar_t *v15; // rdi
  wchar_t *v16; // rdi
  int v17; // eax
  int v18; // eax
  HLOCAL v19; // rax
  int v20; // eax
  HLOCAL v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  wchar_t *v31; // rdi
  char v32; // si
  __int64 *v33; // rax
  int v34; // eax
  wchar_t *v35; // rdi
  char v36; // si
  __int64 *v37; // rax
  int v38; // r13d
  unsigned int i; // ebx
  int v40; // eax
  int v41; // eax
  unsigned int j; // ebx
  int v43; // ecx
  __int64 v44; // rax
  HLOCAL v45; // rax
  __int64 v46; // [rsp+28h] [rbp-99h]
  __int64 v47; // [rsp+30h] [rbp-91h]
  __int64 v48; // [rsp+38h] [rbp-89h]
  char v49; // [rsp+48h] [rbp-79h]
  BOOLEAN SaclPresent; // [rsp+49h] [rbp-78h]
  wchar_t *v51; // [rsp+50h] [rbp-71h] BYREF
  HLOCAL v52; // [rsp+58h] [rbp-69h]
  int v53; // [rsp+60h] [rbp-61h]
  ULONG BufferLength; // [rsp+64h] [rbp-5Dh] BYREF
  int v55; // [rsp+68h] [rbp-59h]
  void *v56; // [rsp+70h] [rbp-51h] BYREF
  void *v57; // [rsp+78h] [rbp-49h] BYREF
  __int64 v58; // [rsp+80h] [rbp-41h] BYREF
  PACL Dacl; // [rsp+88h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-31h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+98h] [rbp-29h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-9h]
  _BYTE *v63; // [rsp+118h] [rbp+57h]
  char v65; // [rsp+128h] [rbp+67h]
  char v66; // [rsp+130h] [rbp+6Fh]

  v65 = a3;
  v63 = (_BYTE *)a1;
  v56 = 0;
  v57 = 0;
  v6 = (wchar_t *)a4;
  Dacl = 0;
  v7 = (_BYTE *)a1;
  hMem = 0;
  v8 = 0;
  v62 = 0;
  v9 = 0;
  v51 = 0;
  BufferLength = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( !a4 || !a5 )
    return 87;
  if ( a6 )
    *a6 = 0;
  if ( a1 )
  {
    EnterWaitSddlSidLookup();
    gbLookupTableInitialized = 0;
  }
  LOBYTE(a1) = 1;
  InitializeSidLookupTable(a1, a2, a3, a4);
  v10 = (_BYTE *)a2;
  if ( a2 )
  {
    v45 = LocalAlloc(0x40u, 0x618u);
    v52 = v45;
    v21 = v45;
    if ( !v45 )
    {
      AclForString = 8;
      goto LABEL_49;
    }
    AclForString = 0;
    memcpy_0(v45, SidLookupDomOrRootDomRelative, 0x618u);
    v10 = (_BYTE *)a2;
    v11 = v21;
  }
  else
  {
    v11 = 0;
    AclForString = 0;
    v52 = 0;
  }
  v66 = 0;
  v13 = 0;
  v49 = 0;
  SaclPresent = 0;
  v55 = 0;
  v53 = 0;
  while ( 2 )
  {
    v14 = v65;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( !v6 )
          {
            v17 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
            if ( v17 < 0 )
              AclForString = RtlNtStatusToDosError(v17);
            WORD1(SecurityDescriptor[0]) |= (unsigned __int16)v55 | (unsigned __int16)v53;
            if ( !AclForString )
            {
              if ( !v8
                || (v40 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, v8, 0), v40 >= 0)
                || (AclForString = RtlNtStatusToDosError(v40)) == 0 )
              {
                if ( !v9
                  || (v41 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, v9, 0), v41 >= 0)
                  || (AclForString = RtlNtStatusToDosError(v41)) == 0 )
                {
                  if ( !v13
                    || (v18 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, v13, Dacl, 0), v18 >= 0)
                    || (AclForString = RtlNtStatusToDosError(v18)) == 0 )
                  {
                    if ( !SaclPresent
                      || (v34 = RtlSetSaclSecurityDescriptor(SecurityDescriptor, SaclPresent, (PACL)hMem, 0), v34 >= 0)
                      || (AclForString = RtlNtStatusToDosError(v34)) == 0 )
                    {
                      if ( RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, *a5, &BufferLength) == -1073741789 )
                      {
                        v19 = LocalAlloc(0x40u, BufferLength);
                        *a5 = v19;
                        if ( v19 )
                        {
                          AclForString = 0;
                          v20 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v19, &BufferLength);
                          if ( v20 >= 0
                            || (AclForString = RtlNtStatusToDosError(v20), LocalFree(*a5), *a5 = 0, !AclForString) )
                          {
                            if ( a6 )
                              *a6 = BufferLength;
                          }
                        }
                        else
                        {
                          AclForString = 8;
                        }
                      }
                      else
                      {
                        AclForString = 122;
                      }
                    }
                  }
                }
              }
            }
            goto LABEL_44;
          }
          if ( *v6 )
            break;
          v6 = 0;
        }
        if ( *v6 != 68 )
          break;
        if ( v6[1] != 58 || Dacl )
        {
LABEL_97:
          AclForString = 87;
          goto LABEL_44;
        }
        v16 = v6 + 2;
        if ( *v16 != 40 )
        {
          v38 = 0;
          v55 = 0;
          do
          {
            if ( *v16 != 32 )
              break;
            ++v16;
          }
          while ( v16 );
LABEL_80:
          for ( i = 0; i < 6; ++i )
          {
            if ( ((__int64)(&ControlLookup)[3 * i + 1] & 1) != 0
              && !_wcsnicmp(v16, (&ControlLookup)[3 * i], *((unsigned int *)&ControlLookup + 6 * i + 2)) )
            {
              LOWORD(v38) = *((_WORD *)&ControlLookup + 12 * i + 6) | v38;
              for ( v16 += *((unsigned int *)&ControlLookup + 6 * i + 2); v16; ++v16 )
              {
                if ( *v16 != 32 )
                  break;
              }
              goto LABEL_80;
            }
          }
          v11 = v52;
          v10 = (_BYTE *)a2;
          v14 = v65;
          v55 = v38;
          v51 = v16;
        }
        AclForString = LocalGetAclForString(v16, 1, (HLOCAL *)&Dacl, &v51, v63, v10, (__int64)v11, v14);
        if ( AclForString )
          goto LABEL_44;
        v13 = 1;
LABEL_28:
        v6 = v51;
        v11 = v52;
        v10 = (_BYTE *)a2;
      }
      if ( *v6 == 79 )
        break;
      if ( *v6 == 71 )
      {
        AclForString = 87;
        if ( v6[1] != 58 )
          goto LABEL_44;
        if ( v9 )
          goto LABEL_44;
        v58 = 0;
        v35 = v6 + 2;
        if ( !v35 )
          goto LABEL_44;
        v36 = 0;
        v49 = 0;
        if ( !*v35 || !v35[1] )
        {
          AclForString = 1332;
          goto LABEL_44;
        }
        AclForString = 0;
        v51 = v35 + 2;
        LOBYTE(v47) = v65;
        v37 = LookupSidInTable(v35, 0, v63, v10, (__int64)v11, v47, (PSID *)&v58);
        if ( v37 )
        {
          v9 = (void *)v37[2];
          goto LABEL_74;
        }
        v9 = (void *)v58;
        if ( v58 )
        {
          v36 = 1;
LABEL_74:
          v57 = v9;
        }
        else
        {
          v51 -= 2;
          if ( (unsigned int)LocalConvertStringSidToSid(v35, &v57, &v51) || (AclForString = GetLastError()) == 0 )
          {
            v9 = v57;
            if ( v57 )
              v36 = 1;
          }
          else
          {
            v9 = v57;
          }
        }
        v49 = v36;
        if ( !AclForString )
        {
          v49 = v36;
          goto LABEL_77;
        }
        goto LABEL_44;
      }
      if ( *v6 != 32 )
      {
        if ( *v6 != 83 || v6[1] != 58 || hMem )
          goto LABEL_97;
        v15 = v6 + 2;
        if ( *v15 != 40 )
        {
          v53 = 0;
          do
          {
            if ( *v15 != 32 )
              break;
            ++v15;
          }
          while ( v15 );
LABEL_100:
          for ( j = 0; j < 6; ++j )
          {
            if ( ((__int64)(&ControlLookup)[3 * j + 1] & 2) != 0
              && !_wcsnicmp(v15, (&ControlLookup)[3 * j], *((unsigned int *)&ControlLookup + 6 * j + 2)) )
            {
              HIWORD(v43) = HIWORD(v53);
              LOWORD(v43) = *((_WORD *)&ControlLookup + 12 * j + 6) | v53;
              v44 = *((unsigned int *)&ControlLookup + 6 * j + 2);
              v53 = v43;
              for ( v15 += v44; v15; ++v15 )
              {
                if ( *v15 != 32 )
                  break;
              }
              goto LABEL_100;
            }
          }
          v11 = v52;
          v10 = (_BYTE *)a2;
          v14 = v65;
          v51 = v15;
        }
        AclForString = LocalGetAclForString(v15, 0, &hMem, &v51, v63, v10, (__int64)v11, v14);
        if ( AclForString )
          goto LABEL_44;
        SaclPresent = 1;
        goto LABEL_28;
      }
      ++v6;
    }
    AclForString = 87;
    if ( v6[1] != 58 )
      break;
    if ( v8 )
      break;
    v58 = 0;
    v31 = v6 + 2;
    if ( !v31 )
      break;
    if ( !*v31 || !v31[1] )
    {
      AclForString = 1332;
      goto LABEL_46;
    }
    v66 = 0;
    v51 = v31 + 2;
    v32 = 0;
    AclForString = 0;
    LOBYTE(v47) = v65;
    v33 = LookupSidInTable(v31, 0, v63, v10, (__int64)v11, v47, (PSID *)&v58);
    if ( v33 )
    {
      v8 = (void *)v33[2];
      goto LABEL_61;
    }
    v8 = (void *)v58;
    if ( v58 )
    {
      v32 = 1;
      v66 = 1;
LABEL_61:
      v56 = v8;
    }
    else
    {
      v51 -= 2;
      if ( (unsigned int)LocalConvertStringSidToSid(v31, &v56, &v51) || (AclForString = GetLastError()) == 0 )
      {
        v8 = v56;
        if ( v56 )
        {
          v32 = 1;
          v66 = 1;
        }
      }
      else
      {
        v8 = v56;
      }
    }
    if ( !AclForString )
    {
      v66 = v32;
LABEL_77:
      v6 = v51;
      v11 = v52;
      v10 = (_BYTE *)a2;
      continue;
    }
    break;
  }
LABEL_44:
  if ( v66 == 1 )
    LocalFree(v8);
LABEL_46:
  if ( v49 == 1 )
    LocalFree(v9);
  v7 = v63;
  v21 = v52;
LABEL_49:
  LocalFree(Dacl);
  LocalFree(hMem);
  if ( v21 )
    LocalFree(v21);
  LOBYTE(v23) = 2;
  InitializeSidLookupTable(v23, v22, v24, v25);
  if ( v7 )
  {
    gbLookupTableInitialized = 0;
    LeaveWaitSddlSidLookup(v27, v26, v28, v29, v46, v47, v48);
  }
  return AclForString;
}

```

## disassembly

```asm
0x18001b744  mov     rax, rsp
0x18001b747  mov     [rax+18h], r8b
0x18001b74b  mov     [rax+10h], rdx
0x18001b74f  mov     [rax+8], rcx
0x18001b753  push    rbp
0x18001b754  push    rbx
0x18001b755  push    rsi
0x18001b756  push    rdi
0x18001b757  push    r12
0x18001b759  push    r13
0x18001b75b  push    r14
0x18001b75d  push    r15
0x18001b75f  lea     rbp, [rax-4Fh]
0x18001b763  sub     rsp, 0C8h
0x18001b76a  xor     r13d, r13d
0x18001b76d  xor     eax, eax
0x18001b76f  mov     [rbp+47h+var_98], r13
0x18001b773  xorps   xmm0, xmm0
0x18001b776  mov     [rbp+47h+var_90], r13
0x18001b77a  mov     rdi, r9
0x18001b77d  mov     [rbp+47h+Dacl], r13
0x18001b781  mov     r14, rcx
0x18001b784  mov     [rbp+47h+hMem], r13
0x18001b788  mov     r15d, r13d
0x18001b78b  mov     [rbp+47h+var_50], rax
0x18001b78f  mov     r12d, r13d
0x18001b792  mov     [rbp+47h+var_B8], r13
0x18001b796  mov     [rbp+47h+BufferLength], r13d
0x18001b79a  movups  [rbp+47h+SecurityDescriptor], xmm0
0x18001b79e  movups  [rbp+47h+var_60], xmm0
0x18001b7a2  test    r9, r9
0x18001b7a5  jz      loc_18001BD60
0x18001b7ab  cmp     [rbp+47h+arg_20], r13
0x18001b7af  jz      loc_18001BD60
0x18001b7b5  mov     rax, [rbp+47h+arg_28]
0x18001b7b9  test    rax, rax
0x18001b7bc  jz      short loc_18001B7C1
0x18001b7be  mov     [rax], r13d
0x18001b7c1  test    rcx, rcx
0x18001b7c4  jnz     loc_18001BF24
0x18001b7ca  mov     cl, 1
0x18001b7cc  call    InitializeSidLookupTable
0x18001b7d1  mov     rdx, [rbp+47h+arg_8]
0x18001b7d5  xor     r8d, r8d
0x18001b7d8  test    rdx, rdx
0x18001b7db  jnz     loc_18001BF35
0x18001b7e1  mov     ecx, r8d
0x18001b7e4  mov     ebx, r8d
0x18001b7e7  mov     [rbp+47h+var_B0], rcx
0x18001b7eb  mov     [rbp+47h+arg_18], r8b
0x18001b7ef  mov     r13b, r8b
0x18001b7f2  mov     [rbp+47h+var_C0], r8b
0x18001b7f6  mov     r14d, 57h ; 'W'
0x18001b7fc  mov     [rbp+47h+SaclPresent], r8b
0x18001b800  mov     [rbp+47h+var_A0], r8d
0x18001b804  mov     [rbp+47h+var_A8], r8d
0x18001b808  mov     sil, [rbp+47h+arg_10]
0x18001b80c  lea     r9, ControlLookup
0x18001b813  test    rdi, rdi
0x18001b816  jz      loc_18001B941
0x18001b81c  cmp     [rdi], r8w
0x18001b820  jz      loc_18001B936
0x18001b826  cmp     word ptr [rdi], 44h ; 'D'
0x18001b82a  jz      loc_18001B8C0
0x18001b830  cmp     word ptr [rdi], 4Fh ; 'O'
0x18001b834  jz      loc_18001BADF
0x18001b83a  cmp     word ptr [rdi], 47h ; 'G'
0x18001b83e  jz      loc_18001BBB8
0x18001b844  cmp     word ptr [rdi], 20h ; ' '
0x18001b848  jz      loc_18001BFBA
0x18001b84e  cmp     word ptr [rdi], 53h ; 'S'
0x18001b852  jnz     loc_18001BD83
0x18001b858  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001b85d  jnz     loc_18001BD83
0x18001b863  cmp     [rbp+47h+hMem], r8
0x18001b867  jnz     loc_18001BD83
0x18001b86d  add     rdi, 4
0x18001b871  cmp     word ptr [rdi], 28h ; '('
0x18001b875  jnz     loc_18001BD8B
0x18001b87b  test    ebx, ebx
0x18001b87d  jnz     loc_18001BA65
0x18001b883  mov     rax, [rbp+47h+arg_0]
0x18001b887  lea     r9, [rbp+47h+var_B8]
0x18001b88b  mov     [rsp+38h], sil; char
0x18001b890  lea     r8, [rbp+47h+hMem]
0x18001b894  mov     [rsp+100h+var_D0], rcx; __int64
0x18001b899  mov     rcx, rdi; String1
0x18001b89c  mov     [rsp+100h+var_D8], rdx; __int64
0x18001b8a1  xor     edx, edx
0x18001b8a3  mov     [rsp+100h+var_E0], rax; __int64
0x18001b8a8  call    LocalGetAclForString
0x18001b8ad  xor     r8d, r8d
0x18001b8b0  mov     ebx, eax
0x18001b8b2  test    eax, eax
0x18001b8b4  jnz     loc_18001BA65
0x18001b8ba  mov     [rbp+47h+SaclPresent], 1
0x18001b8be  jmp     short loc_18001B925
0x18001b8c0  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001b8c5  jnz     loc_18001BD83
0x18001b8cb  cmp     [rbp+47h+Dacl], r8
0x18001b8cf  jnz     loc_18001BD83
0x18001b8d5  add     rdi, 4
0x18001b8d9  cmp     word ptr [rdi], 28h ; '('
0x18001b8dd  jnz     loc_18001BC73
0x18001b8e3  test    ebx, ebx
0x18001b8e5  jnz     loc_18001BA65
0x18001b8eb  mov     rax, [rbp+47h+arg_0]
0x18001b8ef  lea     r9, [rbp+47h+var_B8]
0x18001b8f3  mov     [rsp+38h], sil; char
0x18001b8f8  lea     r8, [rbp+47h+Dacl]
0x18001b8fc  mov     [rsp+100h+var_D0], rcx; __int64
0x18001b901  mov     rcx, rdi; String1
0x18001b904  mov     [rsp+100h+var_D8], rdx; __int64
0x18001b909  mov     dl, 1
0x18001b90b  mov     [rsp+100h+var_E0], rax; __int64
0x18001b910  call    LocalGetAclForString
0x18001b915  xor     r8d, r8d
0x18001b918  mov     ebx, eax
0x18001b91a  test    eax, eax
0x18001b91c  jnz     loc_18001BA65
0x18001b922  mov     r13b, 1
0x18001b925  mov     rdi, [rbp+47h+var_B8]
0x18001b929  mov     rcx, [rbp+47h+var_B0]
0x18001b92d  mov     rdx, [rbp+47h+arg_8]
0x18001b931  jmp     loc_18001B80C
0x18001b936  mov     rdi, r8
0x18001b939  test    ebx, ebx
0x18001b93b  jz      loc_18001B813
0x18001b941  test    ebx, ebx
0x18001b943  jnz     loc_18001BA65
0x18001b949  lea     edx, [rbx+1]; Revision
0x18001b94c  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x18001b950  call    cs:__imp_RtlCreateSecurityDescriptor
0x18001b957  nop     dword ptr [rax+rax+00h]
0x18001b95c  test    eax, eax
0x18001b95e  js      loc_18001BFC3
0x18001b964  mov     esi, [rbp+47h+var_A8]
0x18001b967  mov     eax, [rbp+47h+var_A0]
0x18001b96a  or      si, ax
0x18001b96d  or      word ptr [rbp+47h+SecurityDescriptor+2], si
0x18001b971  test    ebx, ebx
0x18001b973  jnz     loc_18001BA65
0x18001b979  test    r15, r15
0x18001b97c  jnz     loc_18001BCEA
0x18001b982  test    r12, r12
0x18001b985  jnz     loc_18001BD25
0x18001b98b  test    r13b, r13b
0x18001b98e  jz      short loc_18001B9B2
0x18001b990  mov     r8, [rbp+47h+Dacl]; Dacl
0x18001b994  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x18001b998  xor     r9d, r9d; DaclDefaulted
0x18001b99b  mov     dl, r13b; DaclPresent
0x18001b99e  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18001b9a5  nop     dword ptr [rax+rax+00h]
0x18001b9aa  test    eax, eax
0x18001b9ac  js      loc_18001BF07
0x18001b9b2  mov     sil, [rbp+47h+SaclPresent]
0x18001b9b6  test    sil, sil
0x18001b9b9  jnz     loc_18001BB76
0x18001b9bf  xor     r13d, r13d
0x18001b9c2  mov     rdi, [rbp+47h+arg_20]
0x18001b9c6  lea     r8, [rbp+47h+BufferLength]; BufferLength
0x18001b9ca  lea     rcx, [rbp+47h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18001b9ce  mov     rdx, [rdi]; SelfRelativeSecurityDescriptor
0x18001b9d1  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18001b9d8  nop     dword ptr [rax+rax+00h]
0x18001b9dd  cmp     eax, 0C0000023h
0x18001b9e2  jnz     loc_18001BFD8
0x18001b9e8  mov     edx, [rbp+47h+BufferLength]; uBytes
0x18001b9eb  mov     ecx, 40h ; '@'; uFlags
0x18001b9f0  call    cs:__imp_LocalAlloc
0x18001b9f7  nop     dword ptr [rax+rax+00h]
0x18001b9fc  xor     r8d, r8d
0x18001b9ff  mov     [rdi], rax
0x18001ba02  test    rax, rax
0x18001ba05  jz      loc_18001BE2A
0x18001ba0b  mov     ebx, r8d
0x18001ba0e  lea     rcx, [rbp+47h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18001ba12  lea     r8, [rbp+47h+BufferLength]; BufferLength
0x18001ba16  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x18001ba19  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18001ba20  nop     dword ptr [rax+rax+00h]
0x18001ba25  test    eax, eax
0x18001ba27  js      short loc_18001BA3C
0x18001ba29  mov     rcx, [rbp+47h+arg_28]
0x18001ba2d  xor     r13d, r13d
0x18001ba30  test    rcx, rcx
0x18001ba33  jz      short loc_18001BA68
0x18001ba35  mov     eax, [rbp+47h+BufferLength]
0x18001ba38  mov     [rcx], eax
0x18001ba3a  jmp     short loc_18001BA68
0x18001ba3c  mov     ecx, eax; Status
0x18001ba3e  call    cs:__imp_RtlNtStatusToDosError
0x18001ba45  nop     dword ptr [rax+rax+00h]
0x18001ba4a  mov     rcx, [rdi]; hMem
0x18001ba4d  mov     ebx, eax
0x18001ba4f  call    cs:__imp_LocalFree
0x18001ba56  nop     dword ptr [rax+rax+00h]
0x18001ba5b  xor     r8d, r8d
0x18001ba5e  mov     [rdi], r8
0x18001ba61  test    ebx, ebx
0x18001ba63  jz      short loc_18001BA29
0x18001ba65  xor     r13d, r13d
0x18001ba68  cmp     [rbp+47h+arg_18], 1
0x18001ba6c  jz      loc_18001BC5F
0x18001ba72  cmp     [rbp+47h+var_C0], 1
0x18001ba76  jz      loc_18001BE16
0x18001ba7c  mov     r14, [rbp+47h+arg_0]
0x18001ba80  mov     rsi, [rbp+47h+var_B0]
0x18001ba84  mov     rcx, [rbp+47h+Dacl]; hMem
0x18001ba88  call    cs:__imp_LocalFree
0x18001ba8f  nop     dword ptr [rax+rax+00h]
0x18001ba94  mov     rcx, [rbp+47h+hMem]; hMem
0x18001ba98  call    cs:__imp_LocalFree
0x18001ba9f  nop     dword ptr [rax+rax+00h]
0x18001baa4  test    rsi, rsi
0x18001baa7  jz      short loc_18001BAB8
0x18001baa9  mov     rcx, rsi; hMem
0x18001baac  call    cs:__imp_LocalFree
0x18001bab3  nop     dword ptr [rax+rax+00h]
0x18001bab8  mov     cl, 2
0x18001baba  call    InitializeSidLookupTable
0x18001babf  test    r14, r14
0x18001bac2  jnz     loc_18001BFE2
0x18001bac8  mov     eax, ebx
0x18001baca  add     rsp, 0C8h
0x18001bad1  pop     r15
0x18001bad3  pop     r14
0x18001bad5  pop     r13
0x18001bad7  pop     r12
0x18001bad9  pop     rdi
0x18001bada  pop     rsi
0x18001badb  pop     rbx
0x18001badc  pop     rbp
0x18001badd  retn
0x18001badf  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001bae4  mov     ebx, r14d
0x18001bae7  jnz     loc_18001BA65
0x18001baed  test    r15, r15
0x18001baf0  jnz     loc_18001BA65
0x18001baf6  mov     [rbp+47h+var_88], r8
0x18001bafa  add     rdi, 4
0x18001bafe  jz      loc_18001BA65
0x18001bb04  cmp     [rdi], r8w
0x18001bb08  jz      loc_18001BEFA
0x18001bb0e  cmp     [rdi+2], r8w
0x18001bb13  jz      loc_18001BEFA
0x18001bb19  lea     rax, [rdi+4]
0x18001bb1d  mov     [rbp+47h+arg_18], r8b
0x18001bb21  mov     [rbp+47h+var_B8], rax
0x18001bb25  mov     sil, r8b
0x18001bb28  lea     rax, [rbp+47h+var_88]
0x18001bb2c  mov     ebx, r8d
0x18001bb2f  mov     r8, [rbp+47h+arg_0]
0x18001bb33  mov     r9, rdx
0x18001bb36  mov     [rsp+100h+var_D0], rax; __int64
0x18001bb3b  xor     edx, edx; Sid2
0x18001bb3d  mov     al, [rbp+47h+arg_10]
0x18001bb40  mov     byte ptr [rsp+100h+var_D8], al; __int64
0x18001bb44  mov     [rsp+100h+var_E0], rcx; __int64
0x18001bb49  mov     rcx, rdi; String1
0x18001bb4c  call    LookupSidInTable
0x18001bb51  xor     r8d, r8d
0x18001bb54  test    rax, rax
0x18001bb57  jz      loc_18001BE9A
0x18001bb5d  mov     r15, [rax+10h]
0x18001bb61  mov     [rbp+47h+var_98], r15
0x18001bb65  test    ebx, ebx
0x18001bb67  jnz     loc_18001BA65
0x18001bb6d  mov     [rbp+47h+arg_18], sil
0x18001bb71  jmp     loc_18001BC4E
0x18001bb76  mov     r8, [rbp+47h+hMem]; Sacl
0x18001bb7a  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x18001bb7e  xor     r9d, r9d; SaclDefaulted
0x18001bb81  mov     dl, sil; SaclPresent
0x18001bb84  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18001bb8b  nop     dword ptr [rax+rax+00h]
0x18001bb90  xor     r13d, r13d
0x18001bb93  test    eax, eax
0x18001bb95  jns     loc_18001B9C2
0x18001bb9b  mov     ecx, eax; Status
0x18001bb9d  call    cs:__imp_RtlNtStatusToDosError
0x18001bba4  nop     dword ptr [rax+rax+00h]
0x18001bba9  mov     ebx, eax
0x18001bbab  test    eax, eax
0x18001bbad  jz      loc_18001B9C2
0x18001bbb3  jmp     loc_18001BA68
0x18001bbb8  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001bbbd  mov     ebx, r14d
0x18001bbc0  jnz     loc_18001BA65
0x18001bbc6  test    r12, r12
0x18001bbc9  jnz     loc_18001BA65
0x18001bbcf  mov     [rbp+47h+var_88], r8
0x18001bbd3  add     rdi, 4
0x18001bbd7  jz      loc_18001BA65
0x18001bbdd  mov     sil, r8b
0x18001bbe0  mov     [rbp+47h+var_C0], r8b
0x18001bbe4  cmp     [rdi], r8w
0x18001bbe8  jz      loc_18001BE90
0x18001bbee  cmp     [rdi+2], r8w
  ... truncated ...
```
