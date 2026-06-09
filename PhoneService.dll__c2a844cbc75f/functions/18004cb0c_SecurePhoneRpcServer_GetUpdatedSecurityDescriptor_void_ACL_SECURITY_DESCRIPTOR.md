# SecurePhoneRpcServer::_GetUpdatedSecurityDescriptor(void *,_ACL *,_SECURITY_DESCRIPTOR * *)

- ea: `0x18004cb0c`
- end: `0x18004cecc`
- name: `?_GetUpdatedSecurityDescriptor@SecurePhoneRpcServer@@AEAAJPEAXPEAU_ACL@@PEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `960`
- prototype: `int(SecurePhoneRpcServer *__hidden this, void *, struct _ACL *, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004c6e4`
- `0x18004c908`

## callees

- `0x180006e94`
- `0x18004c528`
- `0x18004cb0c`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cbbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cd1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cdca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cbbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cd1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cdca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cd55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cd55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ce9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cbe1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cc02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cc37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cc6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cca1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cdf3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cbe1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cc02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cc37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cc6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cca1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cdf3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004cd6d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004cd6d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004cdaf`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004ce1c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004cdaf`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004ce1c`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18004cb8f`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18004cd11`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18004cb8f`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18004cd11`

## string_xrefs

- `0x18004cba5`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004cc16`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004cc4b`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004cc80`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004ccb5`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004cd41`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004ce4c`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`

## pseudocode

```c
__int64 __fastcall SecurePhoneRpcServer::_GetUpdatedSecurityDescriptor(
        SecurePhoneRpcServer *this,
        void *a2,
        struct _ACL *a3,
        struct _SECURITY_DESCRIPTOR **a4)
{
  __int64 v6; // r9
  unsigned int v7; // r13d
  BackTraceCollection *v8; // rcx
  HLOCAL v9; // rbx
  struct _ACL *v10; // r14
  struct _ACL *pSacl; // r15
  HLOCAL pOwner; // r12
  HLOCAL pPrimaryGroup; // rax
  void *v14; // rdi
  signed int v15; // eax
  BackTraceCollection *v16; // rcx
  __int64 v17; // r9
  signed int v18; // eax
  BackTraceCollection *v19; // rcx
  BackTraceCollection *v20; // rcx
  struct _SECURITY_DESCRIPTOR *v21; // rax
  struct _SECURITY_DESCRIPTOR *v22; // rsi
  signed int LastError; // eax
  BackTraceCollection *v24; // rcx
  SIZE_T uBytes; // [rsp+70h] [rbp-1h] BYREF
  DWORD dwSaclSize; // [rsp+78h] [rbp+7h] BYREF
  DWORD dwDaclSize; // [rsp+7Ch] [rbp+Bh] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+80h] [rbp+Fh] BYREF
  DWORD dwBufferLength; // [rsp+84h] [rbp+13h] BYREF

  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  uBytes = 0;
  if ( !MakeAbsoluteSD(
          a2,
          0,
          &dwAbsoluteSecurityDescriptorSize,
          0,
          &dwDaclSize,
          0,
          &dwSaclSize,
          0,
          (LPDWORD)&uBytes + 1,
          0,
          (LPDWORD)&uBytes) )
  {
    if ( GetLastError() != 122 )
    {
      v7 = -2147418113;
      BackTraceCollection::Capture(v8, -2147418113);
      v6 = 292;
      goto LABEL_3;
    }
    v9 = LocalAlloc(0, dwAbsoluteSecurityDescriptorSize);
    if ( !v9 )
    {
      v6 = 298;
      v7 = -2147024882;
      goto LABEL_3;
    }
    v10 = (struct _ACL *)LocalAlloc(0, dwDaclSize);
    if ( !v10 )
    {
      v7 = -2147024882;
      Log_HREvent_8(
        2147942414LL,
        0,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp",
        301);
LABEL_40:
      LocalFree(v9);
      return v7;
    }
    pSacl = (struct _ACL *)LocalAlloc(0, dwSaclSize);
    if ( !pSacl )
    {
      v7 = -2147024882;
      Log_HREvent_8(
        2147942414LL,
        0,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp",
        304);
LABEL_39:
      LocalFree(v10);
      goto LABEL_40;
    }
    pOwner = LocalAlloc(0, HIDWORD(uBytes));
    if ( !pOwner )
    {
      v7 = -2147024882;
      Log_HREvent_8(
        2147942414LL,
        0,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp",
        307);
LABEL_38:
      LocalFree(pSacl);
      goto LABEL_39;
    }
    pPrimaryGroup = LocalAlloc(0, (unsigned int)uBytes);
    v14 = pPrimaryGroup;
    if ( !pPrimaryGroup )
    {
      v7 = -2147024882;
      Log_HREvent_8(
        2147942414LL,
        0,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp",
        310);
LABEL_37:
      LocalFree(pOwner);
      goto LABEL_38;
    }
    if ( MakeAbsoluteSD(
           a2,
           v9,
           &dwAbsoluteSecurityDescriptorSize,
           v10,
           &dwDaclSize,
           pSacl,
           &dwSaclSize,
           pOwner,
           (LPDWORD)&uBytes + 1,
           pPrimaryGroup,
           (LPDWORD)&uBytes) )
    {
      if ( SetSecurityDescriptorDacl(v9, 1, a3, 0) )
      {
        dwBufferLength = 0;
        if ( MakeSelfRelativeSD(v9, 0, &dwBufferLength) )
        {
          v17 = 322;
          v7 = -2147418113;
        }
        else if ( GetLastError() == 122 )
        {
          v21 = (struct _SECURITY_DESCRIPTOR *)LocalAlloc(0, dwBufferLength);
          v22 = v21;
          if ( v21 )
          {
            if ( MakeSelfRelativeSD(v9, v21, &dwBufferLength) )
            {
              *a4 = v22;
              LocalFree(v14);
              v7 = 0;
              goto LABEL_37;
            }
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            BackTraceCollection::Capture(v24, v7);
            Log_HREvent_8(v7, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", 331);
            LocalFree(v22);
            goto LABEL_21;
          }
          v17 = 329;
          v7 = -2147024882;
        }
        else
        {
          v7 = -2147418113;
          BackTraceCollection::Capture(v20, -2147418113);
          v17 = 324;
        }
      }
      else
      {
        v18 = GetLastError();
        v7 = v18;
        if ( v18 > 0 )
          v7 = (unsigned __int16)v18 | 0x80070000;
        BackTraceCollection::Capture(v19, v7);
        v17 = 317;
      }
    }
    else
    {
      v15 = GetLastError();
      v7 = v15;
      if ( v15 > 0 )
        v7 = (unsigned __int16)v15 | 0x80070000;
      BackTraceCollection::Capture(v16, v7);
      v17 = 314;
    }
    Log_HREvent_8(v7, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", v17);
LABEL_21:
    LocalFree(v14);
    goto LABEL_37;
  }
  v6 = 290;
  v7 = -2147418113;
LABEL_3:
  Log_HREvent_8(v7, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", v6);
  return v7;
}

```

## disassembly

```asm
0x18004cb0c  mov     r11, rsp
0x18004cb0f  mov     [r11+8], rbx
0x18004cb13  push    rbp
0x18004cb14  push    rsi
0x18004cb15  push    rdi
0x18004cb16  push    r12
0x18004cb18  push    r13
0x18004cb1a  push    r14
0x18004cb1c  push    r15
0x18004cb1e  lea     rbp, [r11-5Fh]
0x18004cb22  sub     rsp, 90h
0x18004cb29  mov     rax, cs:__security_cookie
0x18004cb30  xor     rax, rsp
0x18004cb33  mov     [rbp+57h+var_40], rax
0x18004cb37  xor     edi, edi
0x18004cb39  mov     [rbp+57h+var_60], r9
0x18004cb3d  mov     rsi, rdx
0x18004cb40  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], edi
0x18004cb43  lea     rax, [rbp+57h+uBytes]
0x18004cb47  mov     [rbp+57h+dwDaclSize], edi
0x18004cb4a  mov     [r11-78h], rax
0x18004cb4e  mov     r13, r8
0x18004cb51  mov     [r11-80h], rdi
0x18004cb55  lea     rax, [rbp+57h+uBytes+4]
0x18004cb59  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18004cb5e  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18004cb62  mov     [rsp+0C0h+pOwner], rdi; pOwner
0x18004cb67  lea     rax, [rbp+57h+dwSaclSize]
0x18004cb6b  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x18004cb70  xor     r9d, r9d; pDacl
0x18004cb73  lea     rax, [rbp+57h+dwDaclSize]
0x18004cb77  mov     [rsp+0C0h+pSacl], rdi; pSacl
0x18004cb7c  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18004cb7e  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x18004cb83  mov     rcx, rsi; pSelfRelativeSecurityDescriptor
0x18004cb86  mov     [rbp+57h+dwSaclSize], edi
0x18004cb89  mov     dword ptr [rbp+57h+uBytes+4], edi
0x18004cb8c  mov     dword ptr [rbp+57h+uBytes], edi
0x18004cb8f  call    cs:__imp_MakeAbsoluteSD
0x18004cb95  test    eax, eax
0x18004cb97  jz      short loc_18004CBBB
0x18004cb99  mov     r9d, 122h
0x18004cb9f  mov     r13d, 8000FFFFh
0x18004cba5  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004cbac  xor     edx, edx
0x18004cbae  mov     ecx, r13d
0x18004cbb1  call    Log_HREvent_8
0x18004cbb6  jmp     loc_18004CEA2
0x18004cbbb  call    cs:__imp_GetLastError
0x18004cbc1  cmp     eax, 7Ah ; 'z'
0x18004cbc4  jz      short loc_18004CBDC
0x18004cbc6  mov     r13d, 8000FFFFh
0x18004cbcc  mov     edx, r13d; int
0x18004cbcf  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004cbd4  mov     r9d, 124h
0x18004cbda  jmp     short loc_18004CBA5
0x18004cbdc  mov     edx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; uBytes
0x18004cbdf  xor     ecx, ecx; uFlags
0x18004cbe1  call    cs:__imp_LocalAlloc
0x18004cbe7  mov     rbx, rax
0x18004cbea  test    rax, rax
0x18004cbed  jnz     short loc_18004CBFD
0x18004cbef  mov     r9d, 12Ah
0x18004cbf5  mov     r13d, 8007000Eh
0x18004cbfb  jmp     short loc_18004CBA5
0x18004cbfd  mov     edx, [rbp+57h+dwDaclSize]; uBytes
0x18004cc00  xor     ecx, ecx; uFlags
0x18004cc02  call    cs:__imp_LocalAlloc
0x18004cc08  mov     r14, rax
0x18004cc0b  test    rax, rax
0x18004cc0e  jnz     short loc_18004CC32
0x18004cc10  mov     r13d, 8007000Eh
0x18004cc16  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004cc1d  mov     ecx, r13d
0x18004cc20  mov     r9d, 12Dh
0x18004cc26  xor     edx, edx
0x18004cc28  call    Log_HREvent_8
0x18004cc2d  jmp     loc_18004CE99
0x18004cc32  mov     edx, [rbp+57h+dwSaclSize]; uBytes
0x18004cc35  xor     ecx, ecx; uFlags
0x18004cc37  call    cs:__imp_LocalAlloc
0x18004cc3d  mov     r15, rax
0x18004cc40  test    rax, rax
0x18004cc43  jnz     short loc_18004CC67
0x18004cc45  mov     r13d, 8007000Eh
0x18004cc4b  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004cc52  mov     ecx, r13d
0x18004cc55  mov     r9d, 130h
0x18004cc5b  xor     edx, edx
0x18004cc5d  call    Log_HREvent_8
0x18004cc62  jmp     loc_18004CE90
0x18004cc67  mov     edx, dword ptr [rbp+57h+uBytes+4]; uBytes
0x18004cc6a  xor     ecx, ecx; uFlags
0x18004cc6c  call    cs:__imp_LocalAlloc
0x18004cc72  mov     r12, rax
0x18004cc75  test    rax, rax
0x18004cc78  jnz     short loc_18004CC9C
0x18004cc7a  mov     r13d, 8007000Eh
0x18004cc80  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004cc87  mov     ecx, r13d
0x18004cc8a  mov     r9d, 133h
0x18004cc90  xor     edx, edx
0x18004cc92  call    Log_HREvent_8
0x18004cc97  jmp     loc_18004CE87
0x18004cc9c  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x18004cc9f  xor     ecx, ecx; uFlags
0x18004cca1  call    cs:__imp_LocalAlloc
0x18004cca7  mov     rdi, rax
0x18004ccaa  test    rax, rax
0x18004ccad  jnz     short loc_18004CCD1
0x18004ccaf  mov     r13d, 8007000Eh
0x18004ccb5  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004ccbc  mov     ecx, r13d
0x18004ccbf  mov     r9d, 136h
0x18004ccc5  xor     edx, edx
0x18004ccc7  call    Log_HREvent_8
0x18004cccc  jmp     loc_18004CE7E
0x18004ccd1  lea     rax, [rbp+57h+uBytes]
0x18004ccd5  mov     r9, r14; pDacl
0x18004ccd8  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x18004ccdd  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18004cce1  mov     [rsp+0C0h+pPrimaryGroup], rdi; pPrimaryGroup
0x18004cce6  lea     rax, [rbp+57h+uBytes+4]
0x18004ccea  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18004ccef  mov     rdx, rbx; pAbsoluteSecurityDescriptor
0x18004ccf2  mov     [rsp+0C0h+pOwner], r12; pOwner
0x18004ccf7  lea     rax, [rbp+57h+dwSaclSize]
0x18004ccfb  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x18004cd00  mov     rcx, rsi; pSelfRelativeSecurityDescriptor
0x18004cd03  lea     rax, [rbp+57h+dwDaclSize]
0x18004cd07  mov     [rsp+0C0h+pSacl], r15; pSacl
0x18004cd0c  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x18004cd11  call    cs:__imp_MakeAbsoluteSD
0x18004cd17  test    eax, eax
0x18004cd19  jnz     short loc_18004CD60
0x18004cd1b  call    cs:__imp_GetLastError
0x18004cd21  mov     r13d, eax
0x18004cd24  test    eax, eax
0x18004cd26  jle     short loc_18004CD33
0x18004cd28  movzx   r13d, ax
0x18004cd2c  or      r13d, 80070000h
0x18004cd33  mov     edx, r13d; int
0x18004cd36  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004cd3b  mov     r9d, 13Ah
0x18004cd41  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004cd48  xor     edx, edx
0x18004cd4a  mov     ecx, r13d
0x18004cd4d  call    Log_HREvent_8
0x18004cd52  mov     rcx, rdi; hMem
0x18004cd55  call    cs:__imp_LocalFree
0x18004cd5b  jmp     loc_18004CE7E
0x18004cd60  xor     r9d, r9d; bDaclDefaulted
0x18004cd63  mov     r8, r13; pDacl
0x18004cd66  mov     rcx, rbx; pSecurityDescriptor
0x18004cd69  lea     edx, [r9+1]; bDaclPresent
0x18004cd6d  call    cs:__imp_SetSecurityDescriptorDacl
0x18004cd73  test    eax, eax
0x18004cd75  jnz     short loc_18004CD9F
0x18004cd77  call    cs:__imp_GetLastError
0x18004cd7d  mov     r13d, eax
0x18004cd80  test    eax, eax
0x18004cd82  jle     short loc_18004CD8F
0x18004cd84  movzx   r13d, ax
0x18004cd88  or      r13d, 80070000h
0x18004cd8f  mov     edx, r13d; int
0x18004cd92  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004cd97  mov     r9d, 13Dh
0x18004cd9d  jmp     short loc_18004CD41
0x18004cd9f  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x18004cda3  mov     [rbp+57h+dwBufferLength], 0
0x18004cdaa  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x18004cdac  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18004cdaf  call    cs:__imp_MakeSelfRelativeSD
0x18004cdb5  test    eax, eax
0x18004cdb7  jz      short loc_18004CDCA
0x18004cdb9  mov     r9d, 142h
0x18004cdbf  mov     r13d, 8000FFFFh
0x18004cdc5  jmp     loc_18004CD41
0x18004cdca  call    cs:__imp_GetLastError
0x18004cdd0  cmp     eax, 7Ah ; 'z'
0x18004cdd3  jz      short loc_18004CDEE
0x18004cdd5  mov     r13d, 8000FFFFh
0x18004cddb  mov     edx, r13d; int
0x18004cdde  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004cde3  mov     r9d, 144h
0x18004cde9  jmp     loc_18004CD41
0x18004cdee  mov     edx, [rbp+57h+dwBufferLength]; uBytes
0x18004cdf1  xor     ecx, ecx; uFlags
0x18004cdf3  call    cs:__imp_LocalAlloc
0x18004cdf9  mov     rsi, rax
0x18004cdfc  test    rax, rax
0x18004cdff  jnz     short loc_18004CE12
0x18004ce01  mov     r9d, 149h
0x18004ce07  mov     r13d, 8007000Eh
0x18004ce0d  jmp     loc_18004CD41
0x18004ce12  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x18004ce16  mov     rdx, rsi; pSelfRelativeSecurityDescriptor
0x18004ce19  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18004ce1c  call    cs:__imp_MakeSelfRelativeSD
0x18004ce22  test    eax, eax
0x18004ce24  jnz     short loc_18004CE6B
0x18004ce26  call    cs:__imp_GetLastError
0x18004ce2c  mov     r13d, eax
0x18004ce2f  test    eax, eax
0x18004ce31  jle     short loc_18004CE3E
0x18004ce33  movzx   r13d, ax
0x18004ce37  or      r13d, 80070000h
0x18004ce3e  mov     edx, r13d; int
0x18004ce41  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004ce46  mov     r9d, 14Bh
0x18004ce4c  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004ce53  xor     edx, edx
0x18004ce55  mov     ecx, r13d
0x18004ce58  call    Log_HREvent_8
0x18004ce5d  mov     rcx, rsi; hMem
0x18004ce60  call    cs:__imp_LocalFree
0x18004ce66  jmp     loc_18004CD52
0x18004ce6b  mov     rax, [rbp+57h+var_60]
0x18004ce6f  mov     rcx, rdi; hMem
0x18004ce72  mov     [rax], rsi
0x18004ce75  call    cs:__imp_LocalFree
0x18004ce7b  xor     r13d, r13d
0x18004ce7e  mov     rcx, r12; hMem
0x18004ce81  call    cs:__imp_LocalFree
0x18004ce87  mov     rcx, r15; hMem
0x18004ce8a  call    cs:__imp_LocalFree
0x18004ce90  mov     rcx, r14; hMem
0x18004ce93  call    cs:__imp_LocalFree
0x18004ce99  mov     rcx, rbx; hMem
0x18004ce9c  call    cs:__imp_LocalFree
0x18004cea2  mov     eax, r13d
0x18004cea5  mov     rcx, [rbp+57h+var_40]
0x18004cea9  xor     rcx, rsp; StackCookie
0x18004ceac  call    __security_check_cookie
0x18004ceb1  mov     rbx, [rsp+0C0h+arg_0]
0x18004ceb9  add     rsp, 90h
0x18004cec0  pop     r15
0x18004cec2  pop     r14
0x18004cec4  pop     r13
0x18004cec6  pop     r12
0x18004cec8  pop     rdi
0x18004cec9  pop     rsi
0x18004ceca  pop     rbp
0x18004cecb  retn
```
