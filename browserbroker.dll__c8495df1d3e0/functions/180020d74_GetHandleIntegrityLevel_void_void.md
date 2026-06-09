# GetHandleIntegrityLevel(void *,void * *)

- ea: `0x180020d74`
- end: `0x180020fe1`
- name: `?GetHandleIntegrityLevel@@YAJPEAXPEAPEAX@Z`
- size: `621`
- prototype: `__int64 __fastcall(HANDLE Handle, PSID *Sid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020c60`
- `0x1800211f4`

## callees

- `0x180020d74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fa0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020de0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020eda`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020de0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020eda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020fba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020fba`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180020db2`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180020e11`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180020db2`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180020e11`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180020ecd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180020ef0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180020ecd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180020ef0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180020efe`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180020efe`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180020ea9`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180020ea9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180020e50`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180020e50`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020f6b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020f96`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020f6b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020f96`

## pseudocode

```c
__int64 __fastcall GetHandleIntegrityLevel(HANDLE Handle, PSID *Sid)
{
  signed int LastError; // eax
  signed int v5; // ebx
  HLOCAL v6; // rsi
  PACL v7; // rcx
  char v8; // r15
  WORD v9; // r14
  char *v10; // r12
  DWORD LengthSid; // eax
  HLOCAL v12; // rax
  void *v13; // rdi
  DWORD v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  PACL pSacl; // [rsp+30h] [rbp-10h] BYREF
  LPVOID pAce; // [rsp+38h] [rbp-8h] BYREF
  DWORD nLengthNeeded; // [rsp+88h] [rbp+48h] BYREF
  WINBOOL bSaclPresent; // [rsp+90h] [rbp+50h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+98h] [rbp+58h] BYREF

  *Sid = 0;
  nLengthNeeded = 0;
  if ( GetKernelObjectSecurity(Handle, 0x10u, 0, 0, &nLengthNeeded) )
    return (unsigned int)-2147418113;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError == 122 )
  {
    v6 = LocalAlloc(0x40u, nLengthNeeded);
    if ( !v6 )
      return (unsigned int)-2147024882;
    v5 = 0;
    if ( GetKernelObjectSecurity(Handle, 0x10u, v6, nLengthNeeded, &nLengthNeeded) )
      goto LABEL_11;
    LastError = GetLastError();
    v5 = LastError;
  }
  else
  {
    v6 = 0;
  }
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( !v5 )
  {
LABEL_11:
    pSacl = 0;
    bSaclPresent = 0;
    bSaclDefaulted = 0;
    if ( !GetSecurityDescriptorSacl(v6, &bSaclPresent, &pSacl, &bSaclDefaulted) )
      goto LABEL_37;
    if ( bSaclPresent )
    {
      v7 = pSacl;
      if ( pSacl )
      {
        if ( pSacl->AceCount )
        {
          v8 = 0;
          v5 = 0;
          v9 = 0;
          while ( 1 )
          {
            if ( v8 )
              goto LABEL_39;
            if ( v9 >= v7->AceCount )
            {
              if ( !ConvertStringSidToSidW(L"ME", Sid) )
              {
                v16 = GetLastError();
                v5 = v16;
                if ( v16 > 0 )
                  v5 = (unsigned __int16)v16 | 0x80070000;
              }
              goto LABEL_39;
            }
            pAce = 0;
            if ( !GetAce(v7, v9, &pAce) )
              goto LABEL_26;
            if ( *(_BYTE *)pAce != 17 )
              goto LABEL_29;
            if ( (*((_BYTE *)pAce + 1) & 8) != 0 )
            {
              v5 = -2147023556;
              goto LABEL_39;
            }
            v10 = (char *)pAce + 8;
            LengthSid = GetLengthSid((char *)pAce + 8);
            v12 = LocalAlloc(0x40u, LengthSid);
            v13 = v12;
            if ( v10 )
              break;
            if ( !v12 )
            {
LABEL_31:
              v5 = -2147024882;
              goto LABEL_39;
            }
LABEL_29:
            ++v9;
            if ( v5 < 0 )
              goto LABEL_39;
            v7 = pSacl;
          }
          if ( !v12 )
            goto LABEL_31;
          v14 = GetLengthSid(v10);
          if ( CopySid(v14, v13, v10) )
          {
            *Sid = v13;
            v8 = 1;
            goto LABEL_29;
          }
          LocalFree(v13);
LABEL_26:
          v15 = GetLastError();
          v5 = v15;
          if ( v15 > 0 )
            v5 = (unsigned __int16)v15 | 0x80070000;
          goto LABEL_29;
        }
      }
    }
    if ( !ConvertStringSidToSidW(L"ME", Sid) )
    {
LABEL_37:
      v17 = GetLastError();
      v5 = v17;
      if ( v17 > 0 )
        v5 = (unsigned __int16)v17 | 0x80070000;
    }
  }
LABEL_39:
  if ( v6 )
    LocalFree(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020d74  mov     [rsp-38h+arg_0], rbx
0x180020d79  push    rbp
0x180020d7a  push    rsi
0x180020d7b  push    rdi
0x180020d7c  push    r12
0x180020d7e  push    r13
0x180020d80  push    r14
0x180020d82  push    r15
0x180020d84  mov     rbp, rsp
0x180020d87  sub     rsp, 40h
0x180020d8b  xor     r12d, r12d
0x180020d8e  lea     rax, [rbp+nLengthNeeded]
0x180020d92  mov     r13, rdx
0x180020d95  mov     [rdx], r12
0x180020d98  xor     r9d, r9d; nLength
0x180020d9b  mov     [rbp+nLengthNeeded], r12d
0x180020d9f  xor     r8d, r8d; pSecurityDescriptor
0x180020da2  mov     [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180020da7  lea     r15d, [r12+10h]
0x180020dac  mov     rdi, rcx
0x180020daf  mov     edx, r15d; RequestedInformation
0x180020db2  call    cs:__imp_GetKernelObjectSecurity
0x180020db8  test    eax, eax
0x180020dba  jnz     loc_180020FC2
0x180020dc0  call    cs:__imp_GetLastError
0x180020dc6  mov     ebx, eax
0x180020dc8  mov     r14d, 80070000h
0x180020dce  cmp     eax, 7Ah ; 'z'
0x180020dd1  jz      short loc_180020DD8
0x180020dd3  mov     esi, r12d
0x180020dd6  jmp     short loc_180020E23
0x180020dd8  mov     edx, [rbp+nLengthNeeded]; uBytes
0x180020ddb  mov     ecx, 40h ; '@'; uFlags
0x180020de0  call    cs:__imp_LocalAlloc
0x180020de6  mov     rsi, rax
0x180020de9  test    rax, rax
0x180020dec  jnz     short loc_180020DF8
0x180020dee  mov     ebx, 8007000Eh
0x180020df3  jmp     loc_180020FC7
0x180020df8  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180020dfc  lea     rax, [rbp+nLengthNeeded]
0x180020e00  mov     r8, rsi; pSecurityDescriptor
0x180020e03  mov     [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180020e08  mov     edx, r15d; RequestedInformation
0x180020e0b  mov     rcx, rdi; Handle
0x180020e0e  mov     ebx, r12d
0x180020e11  call    cs:__imp_GetKernelObjectSecurity
0x180020e17  test    eax, eax
0x180020e19  jnz     short loc_180020E35
0x180020e1b  call    cs:__imp_GetLastError
0x180020e21  mov     ebx, eax
0x180020e23  test    eax, eax
0x180020e25  jle     short loc_180020E2D
0x180020e27  movzx   ebx, ax
0x180020e2a  or      ebx, r14d
0x180020e2d  test    ebx, ebx
0x180020e2f  jnz     loc_180020FB2
0x180020e35  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x180020e39  mov     [rbp+pSacl], r12
0x180020e3d  lea     r8, [rbp+pSacl]; pSacl
0x180020e41  mov     [rbp+bSaclPresent], r12d
0x180020e45  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x180020e49  mov     [rbp+bSaclDefaulted], r12d
0x180020e4d  mov     rcx, rsi; pSecurityDescriptor
0x180020e50  call    cs:__imp_GetSecurityDescriptorSacl
0x180020e56  test    eax, eax
0x180020e58  jz      loc_180020FA0
0x180020e5e  cmp     [rbp+bSaclPresent], r12d
0x180020e62  jz      loc_180020F8C
0x180020e68  mov     rcx, [rbp+pSacl]; pAcl
0x180020e6c  test    rcx, rcx
0x180020e6f  jz      loc_180020F8C
0x180020e75  cmp     [rcx+4], r12w
0x180020e7a  jbe     loc_180020F8C
0x180020e80  mov     r15b, r12b
0x180020e83  mov     ebx, r12d
0x180020e86  mov     r14d, r12d
0x180020e89  test    r15b, r15b
0x180020e8c  jnz     loc_180020FB2
0x180020e92  cmp     r14w, [rcx+4]
0x180020e97  jnb     loc_180020F58
0x180020e9d  movzx   edx, r14w; dwAceIndex
0x180020ea1  lea     r8, [rbp+pAce]; pAce
0x180020ea5  mov     [rbp+pAce], r12
0x180020ea9  call    cs:__imp_GetAce
0x180020eaf  test    eax, eax
0x180020eb1  jz      short loc_180020F1D
0x180020eb3  mov     rax, [rbp+pAce]
0x180020eb7  cmp     byte ptr [rax], 11h
0x180020eba  jnz     short loc_180020F39
0x180020ebc  test    byte ptr [rax+1], 8
0x180020ec0  jnz     loc_180020F51
0x180020ec6  lea     r12, [rax+8]
0x180020eca  mov     rcx, r12; pSid
0x180020ecd  call    cs:__imp_GetLengthSid
0x180020ed3  mov     edx, eax; uBytes
0x180020ed5  mov     ecx, 40h ; '@'; uFlags
0x180020eda  call    cs:__imp_LocalAlloc
0x180020ee0  mov     rdi, rax
0x180020ee3  test    r12, r12
0x180020ee6  jz      short loc_180020F34
0x180020ee8  test    rax, rax
0x180020eeb  jz      short loc_180020F4A
0x180020eed  mov     rcx, r12; pSid
0x180020ef0  call    cs:__imp_GetLengthSid
0x180020ef6  mov     r8, r12; pSourceSid
0x180020ef9  mov     rdx, rdi; pDestinationSid
0x180020efc  mov     ecx, eax; nDestinationSidLength
0x180020efe  call    cs:__imp_CopySid
0x180020f04  xor     r12d, r12d
0x180020f07  test    eax, eax
0x180020f09  jz      short loc_180020F14
0x180020f0b  mov     [r13+0], rdi
0x180020f0f  mov     r15b, 1
0x180020f12  jmp     short loc_180020F39
0x180020f14  mov     rcx, rdi; hMem
0x180020f17  call    cs:__imp_LocalFree
0x180020f1d  call    cs:__imp_GetLastError
0x180020f23  mov     ebx, eax
0x180020f25  test    eax, eax
0x180020f27  jle     short loc_180020F39
0x180020f29  movzx   ebx, ax
0x180020f2c  or      ebx, 80070000h
0x180020f32  jmp     short loc_180020F39
0x180020f34  test    rdi, rdi
0x180020f37  jz      short loc_180020F4A
0x180020f39  inc     r14w
0x180020f3d  test    ebx, ebx
0x180020f3f  js      short loc_180020FB2
0x180020f41  mov     rcx, [rbp+pSacl]
0x180020f45  jmp     loc_180020E89
0x180020f4a  mov     ebx, 8007000Eh
0x180020f4f  jmp     short loc_180020FB2
0x180020f51  mov     ebx, 8007053Ch
0x180020f56  jmp     short loc_180020FB2
0x180020f58  test    ebx, ebx
0x180020f5a  js      short loc_180020FB2
0x180020f5c  test    r15b, r15b
0x180020f5f  jnz     short loc_180020FB2
0x180020f61  mov     rdx, r13; Sid
0x180020f64  lea     rcx, aMe; "ME"
0x180020f6b  call    cs:__imp_ConvertStringSidToSidW
0x180020f71  test    eax, eax
0x180020f73  jnz     short loc_180020FB2
0x180020f75  call    cs:__imp_GetLastError
0x180020f7b  mov     ebx, eax
0x180020f7d  test    eax, eax
0x180020f7f  jle     short loc_180020FB2
0x180020f81  movzx   ebx, ax
0x180020f84  or      ebx, 80070000h
0x180020f8a  jmp     short loc_180020FB2
0x180020f8c  mov     rdx, r13; Sid
0x180020f8f  lea     rcx, aMe; "ME"
0x180020f96  call    cs:__imp_ConvertStringSidToSidW
0x180020f9c  test    eax, eax
0x180020f9e  jnz     short loc_180020FB2
0x180020fa0  call    cs:__imp_GetLastError
0x180020fa6  mov     ebx, eax
0x180020fa8  test    eax, eax
0x180020faa  jle     short loc_180020FB2
0x180020fac  movzx   ebx, ax
0x180020faf  or      ebx, r14d
0x180020fb2  test    rsi, rsi
0x180020fb5  jz      short loc_180020FC7
0x180020fb7  mov     rcx, rsi; hMem
0x180020fba  call    cs:__imp_LocalFree
0x180020fc0  jmp     short loc_180020FC7
0x180020fc2  mov     ebx, 8000FFFFh
0x180020fc7  mov     eax, ebx
0x180020fc9  mov     rbx, [rsp+40h+arg_0]
0x180020fd1  add     rsp, 40h
0x180020fd5  pop     r15
0x180020fd7  pop     r14
0x180020fd9  pop     r13
0x180020fdb  pop     r12
0x180020fdd  pop     rdi
0x180020fde  pop     rsi
0x180020fdf  pop     rbp
0x180020fe0  retn
```
