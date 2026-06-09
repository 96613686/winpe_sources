# LocalConvertStringSDToSD_Rev1

- ea: `0x18001cbbc`
- end: `0x18001d3c8`
- name: `LocalConvertStringSDToSD_Rev1`
- size: `2060`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b420`
- `0x180030480`
- `0x180052ec0`
- `0x180053030`

## callees

- `0x18001ab84`
- `0x18001b480`
- `0x18001cbbc`
- `0x18001d3d0`
- `0x18001dbb0`
- `0x18001ea04`
- `0x18001ea50`
- `0x180065042`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001d0cb`
- `msvcrt!_wcsnicmp` at `0x18001d1be`
- `msvcrt!_wcsnicmp` at `0x18001d0cb`
- `msvcrt!_wcsnicmp` at `0x18001d1be`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001cdc8`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001cdc8`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001d10b`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18001d10b`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18001cfb3`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18001cfb3`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001ce10`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001ce10`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001ce3d`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001ce79`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001ce3d`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18001ce79`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18001d13a`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18001d13a`
- `ntdll!RtlNtStatusToDosError` at `0x18001ce98`
- `ntdll!RtlNtStatusToDosError` at `0x18001cfc6`
- `ntdll!RtlNtStatusToDosError` at `0x18001d11b`
- `ntdll!RtlNtStatusToDosError` at `0x18001d14a`
- `ntdll!RtlNtStatusToDosError` at `0x18001d2f0`
- `ntdll!RtlNtStatusToDosError` at `0x18001d3a0`
- `ntdll!RtlNtStatusToDosError` at `0x18001ce98`
- `ntdll!RtlNtStatusToDosError` at `0x18001cfc6`
- `ntdll!RtlNtStatusToDosError` at `0x18001d11b`
- `ntdll!RtlNtStatusToDosError` at `0x18001d14a`
- `ntdll!RtlNtStatusToDosError` at `0x18001d2f0`
- `ntdll!RtlNtStatusToDosError` at `0x18001d3a0`
- `KERNELBASE!LocalAlloc` at `0x18001ce56`
- `KERNELBASE!LocalAlloc` at `0x18001d320`
- `KERNELBASE!LocalAlloc` at `0x18001ce56`
- `KERNELBASE!LocalAlloc` at `0x18001d320`
- `KERNEL32!LocalFree` at `0x18001cea3`
- `KERNEL32!LocalFree` at `0x18001ced6`
- `KERNEL32!LocalFree` at `0x18001cee0`
- `KERNEL32!LocalFree` at `0x18001ceee`
- `KERNEL32!LocalFree` at `0x18001d085`
- `KERNEL32!LocalFree` at `0x18001d212`
- `KERNEL32!LocalFree` at `0x18001cea3`
- `KERNEL32!LocalFree` at `0x18001ced6`
- `KERNEL32!LocalFree` at `0x18001cee0`
- `KERNEL32!LocalFree` at `0x18001ceee`
- `KERNEL32!LocalFree` at `0x18001d085`
- `KERNEL32!LocalFree` at `0x18001d212`
- `KERNEL32!GetLastError` at `0x18001d265`
- `KERNEL32!GetLastError` at `0x18001d2c9`
- `KERNEL32!GetLastError` at `0x18001d265`
- `KERNEL32!GetLastError` at `0x18001d2c9`

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
0x18001cbbc  mov     rax, rsp
0x18001cbbf  mov     [rax+18h], r8b
0x18001cbc3  mov     [rax+10h], rdx
0x18001cbc7  mov     [rax+8], rcx
0x18001cbcb  push    rbp
0x18001cbcc  push    rbx
0x18001cbcd  push    rsi
0x18001cbce  push    rdi
0x18001cbcf  push    r12
0x18001cbd1  push    r13
0x18001cbd3  push    r14
0x18001cbd5  push    r15
0x18001cbd7  lea     rbp, [rax-4Fh]
0x18001cbdb  sub     rsp, 0C8h
0x18001cbe2  xor     r13d, r13d
0x18001cbe5  xor     eax, eax
0x18001cbe7  mov     [rbp+47h+var_98], r13
0x18001cbeb  xorps   xmm0, xmm0
0x18001cbee  mov     [rbp+47h+var_90], r13
0x18001cbf2  mov     rdi, r9
0x18001cbf5  mov     [rbp+47h+Dacl], r13
0x18001cbf9  mov     r14, rcx
0x18001cbfc  mov     [rbp+47h+hMem], r13
0x18001cc00  mov     r15d, r13d
0x18001cc03  mov     [rbp+47h+var_50], rax
0x18001cc07  mov     r12d, r13d
0x18001cc0a  mov     [rbp+47h+var_B8], r13
0x18001cc0e  mov     [rbp+47h+BufferLength], r13d
0x18001cc12  movups  [rbp+47h+SecurityDescriptor], xmm0
0x18001cc16  movups  [rbp+47h+var_60], xmm0
0x18001cc1a  test    r9, r9
0x18001cc1d  jz      loc_18001D15F
0x18001cc23  cmp     [rbp+47h+arg_20], r13
0x18001cc27  jz      loc_18001D15F
0x18001cc2d  mov     rax, [rbp+47h+arg_28]
0x18001cc31  test    rax, rax
0x18001cc34  jz      short loc_18001CC39
0x18001cc36  mov     [rax], r13d
0x18001cc39  test    rcx, rcx
0x18001cc3c  jnz     loc_18001D305
0x18001cc42  mov     cl, 1
0x18001cc44  call    InitializeSidLookupTable
0x18001cc49  mov     rdx, [rbp+47h+arg_8]
0x18001cc4d  xor     r8d, r8d
0x18001cc50  test    rdx, rdx
0x18001cc53  jnz     loc_18001D316
0x18001cc59  mov     ecx, r8d
0x18001cc5c  mov     ebx, r8d
0x18001cc5f  mov     [rbp+47h+var_B0], rcx
0x18001cc63  mov     [rbp+47h+arg_18], r8b
0x18001cc67  mov     r13b, r8b
0x18001cc6a  mov     [rbp+47h+var_C0], r8b
0x18001cc6e  mov     r14d, 57h ; 'W'
0x18001cc74  mov     [rbp+47h+SaclPresent], r8b
0x18001cc78  mov     [rbp+47h+var_A0], r8d
0x18001cc7c  mov     [rbp+47h+var_A8], r8d
0x18001cc80  mov     sil, [rbp+47h+arg_10]
0x18001cc84  lea     r9, ControlLookup
0x18001cc8b  test    rdi, rdi
0x18001cc8e  jz      loc_18001CDB9
0x18001cc94  cmp     [rdi], r8w
0x18001cc98  jz      loc_18001CDAE
0x18001cc9e  cmp     word ptr [rdi], 44h ; 'D'
0x18001cca2  jz      loc_18001CD38
0x18001cca8  cmp     word ptr [rdi], 4Fh ; 'O'
0x18001ccac  jz      loc_18001CF1A
0x18001ccb2  cmp     word ptr [rdi], 47h ; 'G'
0x18001ccb6  jz      loc_18001CFDB
0x18001ccbc  cmp     word ptr [rdi], 20h ; ' '
0x18001ccc0  jz      loc_18001D395
0x18001ccc6  cmp     word ptr [rdi], 53h ; 'S'
0x18001ccca  jnz     loc_18001D182
0x18001ccd0  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001ccd5  jnz     loc_18001D182
0x18001ccdb  cmp     [rbp+47h+hMem], r8
0x18001ccdf  jnz     loc_18001D182
0x18001cce5  add     rdi, 4
0x18001cce9  cmp     word ptr [rdi], 28h ; '('
0x18001cced  jnz     loc_18001D18A
0x18001ccf3  test    ebx, ebx
0x18001ccf5  jnz     loc_18001CEB3
0x18001ccfb  mov     rax, [rbp+47h+arg_0]
0x18001ccff  lea     r9, [rbp+47h+var_B8]
0x18001cd03  mov     [rsp+38h], sil; char
0x18001cd08  lea     r8, [rbp+47h+hMem]
0x18001cd0c  mov     [rsp+100h+var_D0], rcx; __int64
0x18001cd11  mov     rcx, rdi; String1
0x18001cd14  mov     [rsp+100h+var_D8], rdx; __int64
0x18001cd19  xor     edx, edx
0x18001cd1b  mov     [rsp+100h+var_E0], rax; __int64
0x18001cd20  call    LocalGetAclForString
0x18001cd25  xor     r8d, r8d
0x18001cd28  mov     ebx, eax
0x18001cd2a  test    eax, eax
0x18001cd2c  jnz     loc_18001CEB3
0x18001cd32  mov     [rbp+47h+SaclPresent], 1
0x18001cd36  jmp     short loc_18001CD9D
0x18001cd38  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001cd3d  jnz     loc_18001D182
0x18001cd43  cmp     [rbp+47h+Dacl], r8
0x18001cd47  jnz     loc_18001D182
0x18001cd4d  add     rdi, 4
0x18001cd51  cmp     word ptr [rdi], 28h ; '('
0x18001cd55  jnz     loc_18001D090
0x18001cd5b  test    ebx, ebx
0x18001cd5d  jnz     loc_18001CEB3
0x18001cd63  mov     rax, [rbp+47h+arg_0]
0x18001cd67  lea     r9, [rbp+47h+var_B8]
0x18001cd6b  mov     [rsp+38h], sil; char
0x18001cd70  lea     r8, [rbp+47h+Dacl]
0x18001cd74  mov     [rsp+100h+var_D0], rcx; __int64
0x18001cd79  mov     rcx, rdi; String1
0x18001cd7c  mov     [rsp+100h+var_D8], rdx; __int64
0x18001cd81  mov     dl, 1
0x18001cd83  mov     [rsp+100h+var_E0], rax; __int64
0x18001cd88  call    LocalGetAclForString
0x18001cd8d  xor     r8d, r8d
0x18001cd90  mov     ebx, eax
0x18001cd92  test    eax, eax
0x18001cd94  jnz     loc_18001CEB3
0x18001cd9a  mov     r13b, 1
0x18001cd9d  mov     rdi, [rbp+47h+var_B8]
0x18001cda1  mov     rcx, [rbp+47h+var_B0]
0x18001cda5  mov     rdx, [rbp+47h+arg_8]
0x18001cda9  jmp     loc_18001CC84
0x18001cdae  mov     rdi, r8
0x18001cdb1  test    ebx, ebx
0x18001cdb3  jz      loc_18001CC8B
0x18001cdb9  test    ebx, ebx
0x18001cdbb  jnz     loc_18001CEB3
0x18001cdc1  lea     edx, [rbx+1]; Revision
0x18001cdc4  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x18001cdc8  call    cs:__imp_RtlCreateSecurityDescriptor
0x18001cdce  test    eax, eax
0x18001cdd0  js      loc_18001D39E
0x18001cdd6  mov     esi, [rbp+47h+var_A8]
0x18001cdd9  mov     eax, [rbp+47h+var_A0]
0x18001cddc  or      si, ax
0x18001cddf  or      word ptr [rbp+47h+SecurityDescriptor+2], si
0x18001cde3  test    ebx, ebx
0x18001cde5  jnz     loc_18001CEB3
0x18001cdeb  test    r15, r15
0x18001cdee  jnz     loc_18001D101
0x18001cdf4  test    r12, r12
0x18001cdf7  jnz     loc_18001D130
0x18001cdfd  test    r13b, r13b
0x18001ce00  jz      short loc_18001CE1E
0x18001ce02  mov     r8, [rbp+47h+Dacl]; Dacl
0x18001ce06  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x18001ce0a  xor     r9d, r9d; DaclDefaulted
0x18001ce0d  mov     dl, r13b; DaclPresent
0x18001ce10  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18001ce16  test    eax, eax
0x18001ce18  js      loc_18001D2EE
0x18001ce1e  mov     sil, [rbp+47h+SaclPresent]
0x18001ce22  test    sil, sil
0x18001ce25  jnz     loc_18001CFA5
0x18001ce2b  xor     r13d, r13d
0x18001ce2e  mov     rdi, [rbp+47h+arg_20]
0x18001ce32  lea     r8, [rbp+47h+BufferLength]; BufferLength
0x18001ce36  lea     rcx, [rbp+47h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18001ce3a  mov     rdx, [rdi]; SelfRelativeSecurityDescriptor
0x18001ce3d  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18001ce43  cmp     eax, 0C0000023h
0x18001ce48  jnz     loc_18001D3AD
0x18001ce4e  mov     edx, [rbp+47h+BufferLength]; uBytes
0x18001ce51  mov     ecx, 40h ; '@'; uFlags
0x18001ce56  call    cs:__imp_LocalAlloc
0x18001ce5c  xor     r8d, r8d
0x18001ce5f  mov     [rdi], rax
0x18001ce62  test    rax, rax
0x18001ce65  jz      loc_18001D21D
0x18001ce6b  mov     ebx, r8d
0x18001ce6e  lea     rcx, [rbp+47h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18001ce72  lea     r8, [rbp+47h+BufferLength]; BufferLength
0x18001ce76  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x18001ce79  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18001ce7f  test    eax, eax
0x18001ce81  js      short loc_18001CE96
0x18001ce83  mov     rcx, [rbp+47h+arg_28]
0x18001ce87  xor     r13d, r13d
0x18001ce8a  test    rcx, rcx
0x18001ce8d  jz      short loc_18001CEB6
0x18001ce8f  mov     eax, [rbp+47h+BufferLength]
0x18001ce92  mov     [rcx], eax
0x18001ce94  jmp     short loc_18001CEB6
0x18001ce96  mov     ecx, eax; Status
0x18001ce98  call    cs:__imp_RtlNtStatusToDosError
0x18001ce9e  mov     rcx, [rdi]; hMem
0x18001cea1  mov     ebx, eax
0x18001cea3  call    cs:__imp_LocalFree
0x18001cea9  xor     r8d, r8d
0x18001ceac  mov     [rdi], r8
0x18001ceaf  test    ebx, ebx
0x18001ceb1  jz      short loc_18001CE83
0x18001ceb3  xor     r13d, r13d
0x18001ceb6  cmp     [rbp+47h+arg_18], 1
0x18001ceba  jz      loc_18001D082
0x18001cec0  cmp     [rbp+47h+var_C0], 1
0x18001cec4  jz      loc_18001D20F
0x18001ceca  mov     r14, [rbp+47h+arg_0]
0x18001cece  mov     rsi, [rbp+47h+var_B0]
0x18001ced2  mov     rcx, [rbp+47h+Dacl]; hMem
0x18001ced6  call    cs:__imp_LocalFree
0x18001cedc  mov     rcx, [rbp+47h+hMem]; hMem
0x18001cee0  call    cs:__imp_LocalFree
0x18001cee6  test    rsi, rsi
0x18001cee9  jz      short loc_18001CEF4
0x18001ceeb  mov     rcx, rsi; hMem
0x18001ceee  call    cs:__imp_LocalFree
0x18001cef4  mov     cl, 2
0x18001cef6  call    InitializeSidLookupTable
0x18001cefb  test    r14, r14
0x18001cefe  jnz     loc_18001D3B7
0x18001cf04  mov     eax, ebx
0x18001cf06  add     rsp, 0C8h
0x18001cf0d  pop     r15
0x18001cf0f  pop     r14
0x18001cf11  pop     r13
0x18001cf13  pop     r12
0x18001cf15  pop     rdi
0x18001cf16  pop     rsi
0x18001cf17  pop     rbx
0x18001cf18  pop     rbp
0x18001cf19  retn
0x18001cf1a  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001cf1f  mov     ebx, r14d
0x18001cf22  jnz     short loc_18001CEB3
0x18001cf24  test    r15, r15
0x18001cf27  jnz     short loc_18001CEB3
0x18001cf29  mov     [rbp+47h+var_88], r8
0x18001cf2d  add     rdi, 4
0x18001cf31  jz      short loc_18001CEB3
0x18001cf33  cmp     [rdi], r8w
0x18001cf37  jz      loc_18001D2E1
0x18001cf3d  cmp     [rdi+2], r8w
0x18001cf42  jz      loc_18001D2E1
0x18001cf48  lea     rax, [rdi+4]
0x18001cf4c  mov     [rbp+47h+arg_18], r8b
0x18001cf50  mov     [rbp+47h+var_B8], rax
0x18001cf54  mov     sil, r8b
0x18001cf57  lea     rax, [rbp+47h+var_88]
0x18001cf5b  mov     ebx, r8d
0x18001cf5e  mov     r8, [rbp+47h+arg_0]
0x18001cf62  mov     r9, rdx
0x18001cf65  mov     [rsp+100h+var_D0], rax; __int64
0x18001cf6a  xor     edx, edx; Sid2
0x18001cf6c  mov     al, [rbp+47h+arg_10]
0x18001cf6f  mov     byte ptr [rsp+100h+var_D8], al; __int64
0x18001cf73  mov     [rsp+100h+var_E0], rcx; __int64
0x18001cf78  mov     rcx, rdi; String1
0x18001cf7b  call    LookupSidInTable
0x18001cf80  xor     r8d, r8d
0x18001cf83  test    rax, rax
0x18001cf86  jz      loc_18001D287
0x18001cf8c  mov     r15, [rax+10h]
0x18001cf90  mov     [rbp+47h+var_98], r15
0x18001cf94  test    ebx, ebx
0x18001cf96  jnz     loc_18001CEB3
0x18001cf9c  mov     [rbp+47h+arg_18], sil
0x18001cfa0  jmp     loc_18001D071
0x18001cfa5  mov     r8, [rbp+47h+hMem]; Sacl
0x18001cfa9  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x18001cfad  xor     r9d, r9d; SaclDefaulted
0x18001cfb0  mov     dl, sil; SaclPresent
0x18001cfb3  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18001cfb9  xor     r13d, r13d
0x18001cfbc  test    eax, eax
0x18001cfbe  jns     loc_18001CE2E
0x18001cfc4  mov     ecx, eax; Status
0x18001cfc6  call    cs:__imp_RtlNtStatusToDosError
0x18001cfcc  mov     ebx, eax
0x18001cfce  test    eax, eax
0x18001cfd0  jz      loc_18001CE2E
0x18001cfd6  jmp     loc_18001CEB6
0x18001cfdb  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001cfe0  mov     ebx, r14d
0x18001cfe3  jnz     loc_18001CEB3
0x18001cfe9  test    r12, r12
0x18001cfec  jnz     loc_18001CEB3
0x18001cff2  mov     [rbp+47h+var_88], r8
0x18001cff6  add     rdi, 4
0x18001cffa  jz      loc_18001CEB3
0x18001d000  mov     sil, r8b
0x18001d003  mov     [rbp+47h+var_C0], r8b
0x18001d007  cmp     [rdi], r8w
0x18001d00b  jz      loc_18001D27D
0x18001d011  cmp     [rdi+2], r8w
0x18001d016  jz      loc_18001D27D
0x18001d01c  lea     rax, [rdi+4]
0x18001d020  mov     ebx, r8d
0x18001d023  mov     r8, [rbp+47h+arg_0]
0x18001d027  mov     r9, rdx
0x18001d02a  mov     [rbp+47h+var_B8], rax
0x18001d02e  xor     edx, edx; Sid2
0x18001d030  lea     rax, [rbp+47h+var_88]
0x18001d034  mov     [rsp+100h+var_D0], rax; __int64
0x18001d039  mov     al, [rbp+47h+arg_10]
0x18001d03c  mov     byte ptr [rsp+100h+var_D8], al; __int64
0x18001d040  mov     [rsp+100h+var_E0], rcx; __int64
  ... truncated ...
```
