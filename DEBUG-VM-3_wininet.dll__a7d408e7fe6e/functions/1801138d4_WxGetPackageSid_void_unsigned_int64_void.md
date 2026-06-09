# WxGetPackageSid(void *,unsigned __int64,void *)

- ea: `0x1801138d4`
- end: `0x180113a66`
- name: `?WxGetPackageSid@@YAJPEAX_K0@Z`
- size: `402`
- prototype: `__int64 __fastcall(HANDLE token, unsigned __int64, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18011379c`

## callees

- `0x1800548ec`
- `0x1801138d4`
- `0x18014a7a0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18011394d`
- `ntdll!NtQueryInformationToken` at `0x18011394d`
- `KERNELBASE!GetPackageSecurityContext` at `0x1801139dc`
- `KERNELBASE!GetPackageSecurityContext` at `0x1801139dc`
- `KERNELBASE!GetPackageSecurityProperty` at `0x180113a15`
- `KERNELBASE!GetPackageSecurityProperty` at `0x180113a15`
- `ext-ms-win-kernel32-package-l1-1-0!ClosePackageInfo` at `0x180113a3c`
- `ext-ms-win-kernel32-package-l1-1-0!ClosePackageInfo` at `0x180113a3c`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x1801139b1`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x1801139b1`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x180113979`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x180113979`

## pseudocode

```c
__int64 __fastcall WxGetPackageSid(HANDLE token, __int64 a2, void *a3)
{
  NTSTATUS v5; // eax
  signed int v6; // ebx
  LONG PackageFullNameFromToken; // eax
  LONG v8; // eax
  int PackageSecurityContext; // eax
  int PackageSecurityProperty; // eax
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+48h] [rbp-B8h] BYREF
  ULONG ReturnLength; // [rsp+4Ch] [rbp-B4h] BYREF
  UINT32 packageFullNameLength[4]; // [rsp+50h] [rbp-B0h] BYREF
  PSID TokenInformation[12]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR packageFullName[128]; // [rsp+C0h] [rbp-40h] BYREF

  ReturnLength = 0;
  packageFullNameLength[0] = 128;
  packageInfoReference = 0;
  v13 = 0;
  v14 = 0;
  v5 = NtQueryInformationToken(token, TokenUser, TokenInformation, 0x54u, &ReturnLength);
  v6 = HRESULT_FROM_NTSTATUS(v5);
  if ( v6 >= 0 )
  {
    PackageFullNameFromToken = GetPackageFullNameFromToken(token, packageFullNameLength, packageFullName);
    v6 = PackageFullNameFromToken;
    if ( PackageFullNameFromToken > 0 )
      v6 = (unsigned __int16)PackageFullNameFromToken | 0x80070000;
    if ( v6 >= 0 )
    {
      v8 = OpenPackageInfoByFullNameForUser(TokenInformation[0], packageFullName, 0, &packageInfoReference);
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v6 >= 0 )
      {
        PackageSecurityContext = GetPackageSecurityContext(packageInfoReference, 0, &v13);
        v6 = PackageSecurityContext;
        if ( PackageSecurityContext > 0 )
          v6 = (unsigned __int16)PackageSecurityContext | 0x80070000;
        if ( v6 >= 0 )
        {
          v14 = 68;
          PackageSecurityProperty = GetPackageSecurityProperty(v13, 2, &v14, a3);
          v6 = PackageSecurityProperty;
          if ( PackageSecurityProperty > 0 )
            v6 = (unsigned __int16)PackageSecurityProperty | 0x80070000;
        }
      }
    }
  }
  if ( packageInfoReference )
    ClosePackageInfo(packageInfoReference);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801138d4  mov     [rsp-8+arg_8], rbx
0x1801138d9  push    rbp
0x1801138da  push    rsi
0x1801138db  push    rdi
0x1801138dc  lea     rbp, [rsp-0D0h]
0x1801138e4  sub     rsp, 1D0h
0x1801138eb  mov     rax, cs:__security_cookie
0x1801138f2  xor     rax, rsp
0x1801138f5  mov     [rbp+0E0h+var_20], rax
0x1801138fc  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180113902  mov     [rsp+1E0h+var_1AC], 0
0x18011390a  mov     rsi, r8
0x18011390d  mov     [rsp+1E0h+var_194], 0
0x180113915  lea     rax, [rsp+1E0h+var_194]
0x18011391a  mov     [rsp+1E0h+packageFullNameLength], 80h
0x180113922  lea     r8, [rsp+1E0h+TokenInformation]; TokenInformation
0x180113927  mov     [rsp+1E0h+packageInfoReference], 0
0x180113930  lea     edx, [r9-53h]; TokenInformationClass
0x180113934  mov     [rsp+1E0h+var_1A0], 0
0x18011393d  mov     rdi, rcx
0x180113940  mov     [rsp+1E0h+var_198], 0
0x180113948  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x18011394d  call    cs:__imp_NtQueryInformationToken
0x180113953  mov     ecx, eax; int
0x180113955  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x18011395a  mov     ebx, eax
0x18011395c  test    eax, eax
0x18011395e  jns     short loc_18011396D
0x180113960  mov     [rsp+1E0h+var_1AC], 7Ch ; '|'
0x180113968  jmp     loc_180113A32
0x18011396d  lea     r8, [rbp+0E0h+packageFullName]; packageFullName
0x180113971  mov     rcx, rdi; token
0x180113974  lea     rdx, [rsp+1E0h+packageFullNameLength]; packageFullNameLength
0x180113979  call    cs:__imp_GetPackageFullNameFromToken
0x18011397f  mov     ebx, eax
0x180113981  mov     edi, 80070000h
0x180113986  test    eax, eax
0x180113988  jle     short loc_18011398F
0x18011398a  movzx   ebx, ax
0x18011398d  or      ebx, edi
0x18011398f  test    ebx, ebx
0x180113991  jns     short loc_1801139A0
0x180113993  mov     [rsp+1E0h+var_1AC], 7Dh ; '}'
0x18011399b  jmp     loc_180113A32
0x1801139a0  mov     rcx, [rsp+1E0h+TokenInformation]; userSid
0x1801139a5  lea     r9, [rsp+1E0h+packageInfoReference]; packageInfoReference
0x1801139aa  xor     r8d, r8d; reserved
0x1801139ad  lea     rdx, [rbp+0E0h+packageFullName]; packageFullName
0x1801139b1  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x1801139b7  mov     ebx, eax
0x1801139b9  test    eax, eax
0x1801139bb  jle     short loc_1801139C2
0x1801139bd  movzx   ebx, ax
0x1801139c0  or      ebx, edi
0x1801139c2  test    ebx, ebx
0x1801139c4  jns     short loc_1801139D0
0x1801139c6  mov     [rsp+1E0h+var_1AC], 7Fh
0x1801139ce  jmp     short loc_180113A32
0x1801139d0  mov     rcx, [rsp+1E0h+packageInfoReference]
0x1801139d5  lea     r8, [rsp+1E0h+var_1A0]
0x1801139da  xor     edx, edx
0x1801139dc  call    cs:__imp_GetPackageSecurityContext
0x1801139e2  mov     ebx, eax
0x1801139e4  test    eax, eax
0x1801139e6  jle     short loc_1801139ED
0x1801139e8  movzx   ebx, ax
0x1801139eb  or      ebx, edi
0x1801139ed  test    ebx, ebx
0x1801139ef  jns     short loc_1801139FB
0x1801139f1  mov     [rsp+1E0h+var_1AC], 80h
0x1801139f9  jmp     short loc_180113A32
0x1801139fb  mov     rcx, [rsp+1E0h+var_1A0]
0x180113a00  lea     r8, [rsp+1E0h+var_198]
0x180113a05  mov     r9, rsi
0x180113a08  mov     [rsp+1E0h+var_198], 44h ; 'D'
0x180113a10  mov     edx, 2
0x180113a15  call    cs:__imp_GetPackageSecurityProperty
0x180113a1b  mov     ebx, eax
0x180113a1d  test    eax, eax
0x180113a1f  jle     short loc_180113A26
0x180113a21  movzx   ebx, ax
0x180113a24  or      ebx, edi
0x180113a26  test    ebx, ebx
0x180113a28  jns     short loc_180113A32
0x180113a2a  mov     [rsp+1E0h+var_1AC], 83h
0x180113a32  mov     rcx, [rsp+1E0h+packageInfoReference]; packageInfoReference
0x180113a37  test    rcx, rcx
0x180113a3a  jz      short loc_180113A42
0x180113a3c  call    cs:__imp_ClosePackageInfo
0x180113a42  mov     eax, ebx
0x180113a44  mov     rcx, [rbp+0E0h+var_20]
0x180113a4b  xor     rcx, rsp; StackCookie
0x180113a4e  call    __security_check_cookie
0x180113a53  mov     rbx, [rsp+1E0h+arg_8]
0x180113a5b  add     rsp, 1D0h
0x180113a62  pop     rdi
0x180113a63  pop     rsi
0x180113a64  pop     rbp
0x180113a65  retn
```
