# AllocAbsoluteSDFromString

- ea: `0x18000a1d4`
- end: `0x18000a434`
- name: `AllocAbsoluteSDFromString`
- size: `608`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006710`
- `0x180006be0`
- `0x1800523d0`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000a1d4`
- `0x18000dce4`
- `0x18000dd60`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a233`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a233`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a40d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a40d`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000a287`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000a3cf`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000a287`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000a3cf`

## string_xrefs

- `0x18000a356`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x18000a3e2`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall AllocAbsoluteSDFromString(const WCHAR *a1, _QWORD *a2)
{
  char *v2; // rbx
  unsigned int LastError; // edi
  __int64 v5; // rdx
  const char *v6; // r9
  __int64 v7; // rdx
  DWORD v8; // r9d
  DWORD v9; // r10d
  DWORD v10; // r11d
  DWORD v11; // ecx
  DWORD v12; // edx
  int lpdwDaclSize; // [rsp+20h] [rbp-29h]
  DWORD dwPrimaryGroupSize; // [rsp+60h] [rbp+17h] BYREF
  DWORD dwOwnerSize; // [rsp+64h] [rbp+1Bh] BYREF
  DWORD dwDaclSize; // [rsp+68h] [rbp+1Fh] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+6Ch] [rbp+23h] BYREF
  DWORD dwSaclSize; // [rsp+70h] [rbp+27h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v2 = 0;
  SecurityDescriptor = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  if ( !a2 )
  {
    LastError = -2147467261;
    v5 = 541;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)LastError,
      lpdwDaclSize);
    goto LABEL_17;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(a1, 1u, &SecurityDescriptor, 0) )
  {
    if ( MakeAbsoluteSD(
           SecurityDescriptor,
           0,
           &dwAbsoluteSecurityDescriptorSize,
           0,
           &dwDaclSize,
           0,
           &dwSaclSize,
           0,
           &dwOwnerSize,
           0,
           &dwPrimaryGroupSize) )
    {
      LastError = -2145120257;
      v5 = 551;
      goto LABEL_12;
    }
    if ( GetLastError() == 122 )
    {
      v8 = 8 - (dwAbsoluteSecurityDescriptorSize & 7) + dwAbsoluteSecurityDescriptorSize;
      dwAbsoluteSecurityDescriptorSize = v8;
      v9 = 8 - (dwDaclSize & 7) + dwDaclSize;
      dwDaclSize = v9;
      dwSaclSize += 8 - (dwSaclSize & 7);
      v10 = 8 - (dwOwnerSize & 7) + dwOwnerSize;
      dwOwnerSize = v10;
      v11 = 8 - (dwPrimaryGroupSize & 7) + dwPrimaryGroupSize;
      dwPrimaryGroupSize = v11;
      v12 = v8 + v9 + v11 + v10 + dwSaclSize;
      if ( v12 )
      {
        v2 = (char *)SafeSusAllocArray(v12, 1u);
        LastError = v2 == 0 ? 0x8007000E : 0;
        if ( !v2 )
        {
          v5 = 563;
          goto LABEL_12;
        }
        v8 = dwAbsoluteSecurityDescriptorSize;
        v10 = dwOwnerSize;
        v11 = dwPrimaryGroupSize;
        v9 = dwDaclSize;
      }
      if ( MakeAbsoluteSD(
             SecurityDescriptor,
             v2,
             &dwAbsoluteSecurityDescriptorSize,
             (PACL)&v2[v8 + v11 + v10],
             &dwDaclSize,
             (PACL)&v2[v8 + v11 + v10 + v9],
             &dwSaclSize,
             &v2[v8 + v11],
             &dwOwnerSize,
             &v2[v8],
             &dwPrimaryGroupSize) )
      {
        *a2 = v2;
        LastError = 0;
        goto LABEL_20;
      }
      v7 = 580;
    }
    else
    {
      v7 = 553;
    }
  }
  else
  {
    v7 = 547;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v7,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
                v6);
LABEL_17:
  if ( v2 )
    SusFree(v2);
LABEL_20:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x18000a1d4  mov     [rsp-8+arg_10], rbx
0x18000a1d9  push    rbp
0x18000a1da  push    rsi
0x18000a1db  push    rdi
0x18000a1dc  lea     rbp, [rsp-47h]
0x18000a1e1  sub     rsp, 90h
0x18000a1e8  mov     rax, cs:__security_cookie
0x18000a1ef  xor     rax, rsp
0x18000a1f2  mov     [rbp+57h+var_20], rax
0x18000a1f6  xor     ebx, ebx
0x18000a1f8  mov     [rbp+57h+SecurityDescriptor], 0
0x18000a200  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], ebx
0x18000a203  mov     rsi, rdx
0x18000a206  mov     [rbp+57h+dwOwnerSize], ebx
0x18000a209  mov     [rbp+57h+dwPrimaryGroupSize], ebx
0x18000a20c  mov     [rbp+57h+dwDaclSize], ebx
0x18000a20f  mov     [rbp+57h+dwSaclSize], ebx
0x18000a212  test    rdx, rdx
0x18000a215  jnz     short loc_18000A226
0x18000a217  mov     edi, 80004003h
0x18000a21c  mov     edx, 21Dh
0x18000a221  jmp     loc_18000A352
0x18000a226  xor     r9d, r9d; SecurityDescriptorSize
0x18000a229  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000a22d  lea     edi, [r9+1]
0x18000a231  mov     edx, edi; StringSDRevision
0x18000a233  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000a239  test    eax, eax
0x18000a23b  jnz     short loc_18000A247
0x18000a23d  mov     edx, 223h
0x18000a242  jmp     loc_18000A3DE
0x18000a247  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18000a24b  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18000a24f  mov     [rsp+0A0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18000a254  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18000a258  mov     [rsp+0A0h+pPrimaryGroup], rbx; pPrimaryGroup
0x18000a25d  lea     rax, [rbp+57h+dwOwnerSize]
0x18000a261  mov     [rsp+0A0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18000a266  xor     r9d, r9d; pDacl
0x18000a269  mov     [rsp+0A0h+pOwner], rbx; pOwner
0x18000a26e  lea     rax, [rbp+57h+dwSaclSize]
0x18000a272  mov     [rsp+0A0h+lpdwSaclSize], rax; lpdwSaclSize
0x18000a277  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18000a279  lea     rax, [rbp+57h+dwDaclSize]
0x18000a27d  mov     [rsp+0A0h+pSacl], rbx; pSacl
0x18000a282  mov     [rsp+0A0h+lpdwDaclSize], rax; int
0x18000a287  call    cs:__imp_MakeAbsoluteSD
0x18000a28d  test    eax, eax
0x18000a28f  jz      short loc_18000A2A0
0x18000a291  mov     edi, 80240FFFh
0x18000a296  mov     edx, 227h
0x18000a29b  jmp     loc_18000A352
0x18000a2a0  call    cs:__imp_GetLastError
0x18000a2a6  cmp     eax, 7Ah ; 'z'
0x18000a2a9  jz      short loc_18000A2B5
0x18000a2ab  mov     edx, 229h
0x18000a2b0  jmp     loc_18000A3DE
0x18000a2b5  mov     r9d, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x18000a2b9  mov     r8d, 8
0x18000a2bf  mov     r10d, [rbp+57h+dwDaclSize]
0x18000a2c3  mov     ecx, r9d
0x18000a2c6  mov     edx, [rbp+57h+dwSaclSize]
0x18000a2c9  and     ecx, 7
0x18000a2cc  mov     r11d, [rbp+57h+dwOwnerSize]
0x18000a2d0  mov     eax, r8d
0x18000a2d3  sub     eax, ecx
0x18000a2d5  mov     ecx, r10d
0x18000a2d8  add     r9d, eax
0x18000a2db  and     ecx, 7
0x18000a2de  mov     eax, r8d
0x18000a2e1  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r9d
0x18000a2e5  sub     eax, ecx
0x18000a2e7  mov     ecx, edx
0x18000a2e9  add     r10d, eax
0x18000a2ec  and     ecx, 7
0x18000a2ef  mov     eax, r8d
0x18000a2f2  mov     [rbp+57h+dwDaclSize], r10d
0x18000a2f6  sub     eax, ecx
0x18000a2f8  mov     ecx, r11d
0x18000a2fb  add     edx, eax
0x18000a2fd  and     ecx, 7
0x18000a300  mov     [rbp+57h+dwSaclSize], edx
0x18000a303  mov     eax, r8d
0x18000a306  sub     eax, ecx
0x18000a308  mov     ecx, [rbp+57h+dwPrimaryGroupSize]
0x18000a30b  add     r11d, eax
0x18000a30e  mov     eax, ecx
0x18000a310  and     eax, 7
0x18000a313  mov     [rbp+57h+dwOwnerSize], r11d
0x18000a317  sub     r8d, eax
0x18000a31a  add     ecx, r8d
0x18000a31d  mov     [rbp+57h+dwPrimaryGroupSize], ecx
0x18000a320  lea     eax, [rcx+r11]
0x18000a324  add     edx, eax
0x18000a326  add     edx, r10d
0x18000a329  add     edx, r9d
0x18000a32c  jz      short loc_18000A379
0x18000a32e  mov     ecx, edx; unsigned __int64
0x18000a330  mov     rdx, rdi; unsigned __int64
0x18000a333  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18000a338  mov     rbx, rax
0x18000a33b  neg     rax
0x18000a33e  sbb     edi, edi
0x18000a340  not     edi
0x18000a342  and     edi, 8007000Eh
0x18000a348  test    rbx, rbx
0x18000a34b  jnz     short loc_18000A36A
0x18000a34d  mov     edx, 233h; void *
0x18000a352  mov     rcx, [rbp+5Fh]; this
0x18000a356  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000a35d  mov     r9d, edi; char *
0x18000a360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a365  jmp     loc_18000A3F0
0x18000a36a  mov     r9d, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x18000a36e  mov     r11d, [rbp+57h+dwOwnerSize]
0x18000a372  mov     ecx, [rbp+57h+dwPrimaryGroupSize]
0x18000a375  mov     r10d, [rbp+57h+dwDaclSize]
0x18000a379  mov     r8d, ecx
0x18000a37c  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x18000a380  mov     [rsp+0A0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x18000a385  lea     rcx, [rbp+57h+dwOwnerSize]
0x18000a389  mov     edx, r9d
0x18000a38c  add     rdx, rbx
0x18000a38f  mov     r9d, r11d
0x18000a392  mov     [rsp+0A0h+pPrimaryGroup], rdx; pPrimaryGroup
0x18000a397  add     r8, rdx
0x18000a39a  mov     [rsp+0A0h+lpdwOwnerSize], rcx; lpdwOwnerSize
0x18000a39f  add     r9, r8; pDacl
0x18000a3a2  mov     [rsp+0A0h+pOwner], r8; pOwner
0x18000a3a7  lea     rcx, [rbp+57h+dwSaclSize]
0x18000a3ab  mov     [rsp+0A0h+lpdwSaclSize], rcx; lpdwSaclSize
0x18000a3b0  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18000a3b4  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18000a3b8  mov     rdx, rbx; pAbsoluteSecurityDescriptor
0x18000a3bb  mov     eax, r10d
0x18000a3be  add     rax, r9
0x18000a3c1  mov     [rsp+0A0h+pSacl], rax; pSacl
0x18000a3c6  lea     rax, [rbp+57h+dwDaclSize]
0x18000a3ca  mov     [rsp+0A0h+lpdwDaclSize], rax; lpdwDaclSize
0x18000a3cf  call    cs:__imp_MakeAbsoluteSD
0x18000a3d5  test    eax, eax
0x18000a3d7  jnz     short loc_18000A3FF
0x18000a3d9  mov     edx, 244h; void *
0x18000a3de  mov     rcx, [rbp+5Fh]; this
0x18000a3e2  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000a3e9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a3ee  mov     edi, eax
0x18000a3f0  test    rbx, rbx
0x18000a3f3  jz      short loc_18000A404
0x18000a3f5  mov     rcx, rbx; lpMem
0x18000a3f8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000a3fd  jmp     short loc_18000A404
0x18000a3ff  mov     [rsi], rbx
0x18000a402  xor     edi, edi
0x18000a404  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18000a408  test    rcx, rcx
0x18000a40b  jz      short loc_18000A413
0x18000a40d  call    cs:__imp_LocalFree
0x18000a413  mov     eax, edi
0x18000a415  mov     rcx, [rbp+57h+var_20]
0x18000a419  xor     rcx, rsp; StackCookie
0x18000a41c  call    __security_check_cookie
0x18000a421  mov     rbx, [rsp+0A0h+arg_10]
0x18000a429  add     rsp, 90h
0x18000a430  pop     rdi
0x18000a431  pop     rsi
0x18000a432  pop     rbp
0x18000a433  retn
```
