# CDsmDeviceTask::_GetPairedDevicePerUserSid(ushort const *,ushort * *)

- ea: `0x180036240`
- end: `0x1800363ba`
- name: `?_GetPairedDevicePerUserSid@CDsmDeviceTask@@AEAAJPEBGPEAPEAG@Z`
- size: `378`
- prototype: `__int64 __fastcall(CDsmDeviceTask *this, const unsigned __int16 *, unsigned __int16 **, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800363d8`

## callees

- `0x1800112a4`
- `0x1800112c8`
- `0x18003605c`
- `0x180036240`
- `0x18003ebb4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800362ae`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800362ae`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800362f2`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800362f2`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180036320`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180036330`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180036320`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180036330`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036355`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180036355`

## string_xrefs

- `0x180036368`: `onecoreuap\base\devices\setup\dsm\service\devicetask.cpp`
- `0x180036396`: `onecoreuap\base\devices\setup\dsm\service\devicetask.cpp`

## pseudocode

```c
__int64 __fastcall CDsmDeviceTask::_GetPairedDevicePerUserSid(
        CDsmDeviceTask *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        int a4)
{
  int DeviceObjectCustomProperty__lambda_5bf5e9a6d8d8a2bb587bd9659b4b2890; // eax
  unsigned int LastError; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  const char *v9; // r9
  __int64 v10; // rdx
  struct _ACL *v11; // rcx
  DWORD v12; // edi
  char *v13; // rbx
  int v15; // [rsp+20h] [rbp-30h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+30h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pAce[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  CDsmDeviceTask *bDaclPresent; // [rsp+70h] [rbp+20h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+88h] [rbp+38h] BYREF

  bDaclPresent = this;
  pSecurityDescriptor = 0;
  pAce[0] = &pSecurityDescriptor;
  DeviceObjectCustomProperty__lambda_5bf5e9a6d8d8a2bb587bd9659b4b2890 = GetDeviceObjectCustomProperty__lambda_5bf5e9a6d8d8a2bb587bd9659b4b2890_(
                                                                          (_DWORD)this,
                                                                          (_DWORD)a2,
                                                                          (_DWORD)a3,
                                                                          a4,
                                                                          (__int64)pAce);
  LastError = DeviceObjectCustomProperty__lambda_5bf5e9a6d8d8a2bb587bd9659b4b2890;
  if ( DeviceObjectCustomProperty__lambda_5bf5e9a6d8d8a2bb587bd9659b4b2890 < 0 )
  {
    v7 = (unsigned int)DeviceObjectCustomProperty__lambda_5bf5e9a6d8d8a2bb587bd9659b4b2890;
    v8 = 347;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\devicetask.cpp",
      (const char *)v7,
      v15);
    goto LABEL_22;
  }
  pDacl = 0;
  LODWORD(bDaclPresent) = 0;
  bDaclDefaulted = 0;
  if ( GetSecurityDescriptorDacl(pSecurityDescriptor, (LPBOOL)&bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    if ( (_DWORD)bDaclPresent )
    {
      v11 = pDacl;
      v12 = 0;
      if ( pDacl->AceCount )
      {
        do
        {
          pAce[0] = 0;
          if ( GetAce(v11, v12, pAce) )
          {
            if ( !*(_BYTE *)pAce[0] && (*((_DWORD *)pAce[0] + 1) & 0x10001) == 0x10001 )
            {
              v13 = (char *)pAce[0] + 8;
              if ( !IsWellKnownSid((char *)pAce[0] + 8, WinLocalSystemSid)
                && !IsWellKnownSid(v13, WinBuiltinAnyPackageSid) )
              {
                break;
              }
            }
          }
          v11 = pDacl;
          ++v12;
          v13 = 0;
        }
        while ( v12 < pDacl->AceCount );
        if ( v13 )
        {
          if ( ConvertSidToStringSidW(v13, a3) )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
            return 0;
          }
          v10 = 400;
          goto LABEL_17;
        }
      }
      v8 = 399;
    }
    else
    {
      v8 = 359;
    }
    LastError = -2147023728;
    v7 = 2147943568LL;
    goto LABEL_21;
  }
  v10 = 357;
LABEL_17:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v10,
                (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\devicetask.cpp",
                v9);
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x180036240  mov     [rsp-18h+arg_8], rbx
0x180036245  mov     [rsp-18h+bDaclPresent], rcx
0x18003624a  push    rbp
0x18003624b  push    rsi
0x18003624c  push    rdi
0x18003624d  mov     rbp, rsp
0x180036250  sub     rsp, 50h
0x180036254  lea     rax, [rbp+pSecurityDescriptor]
0x180036258  mov     [rbp+pSecurityDescriptor], 0
0x180036260  mov     [rbp+pAce], rax
0x180036264  mov     rsi, r8
0x180036267  lea     rax, [rbp+pAce]
0x18003626b  mov     qword ptr [rsp+50h+var_30], rax; int
0x180036270  call    GetDeviceObjectCustomProperty__lambda_5bf5e9a6d8d8a2bb587bd9659b4b2890___; GetDeviceObjectCustomProperty__lambda_5bf5e9a6d8d8a2bb587bd9659b4b2890_
0x180036275  mov     ebx, eax
0x180036277  test    eax, eax
0x180036279  jns     short loc_180036288
0x18003627b  mov     r9d, eax
0x18003627e  mov     edx, 15Bh
0x180036283  jmp     loc_180036392
0x180036288  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18003628c  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180036290  lea     r8, [rbp+pDacl]; pDacl
0x180036294  mov     [rbp+pDacl], 0
0x18003629c  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800362a0  mov     dword ptr [rbp+bDaclPresent], 0
0x1800362a7  mov     [rbp+bDaclDefaulted], 0
0x1800362ae  call    cs:__imp_GetSecurityDescriptorDacl
0x1800362b4  test    eax, eax
0x1800362b6  jnz     short loc_1800362C2
0x1800362b8  mov     edx, 165h
0x1800362bd  jmp     loc_180036364
0x1800362c2  cmp     dword ptr [rbp+bDaclPresent], 0
0x1800362c6  jnz     short loc_1800362D2
0x1800362c8  mov     edx, 167h
0x1800362cd  jmp     loc_18003638A
0x1800362d2  mov     rcx, [rbp+pDacl]; pAcl
0x1800362d6  xor     edi, edi
0x1800362d8  xor     eax, eax
0x1800362da  cmp     ax, [rcx+4]
0x1800362de  jnb     loc_180036385
0x1800362e4  lea     r8, [rbp+pAce]; pAce
0x1800362e8  mov     [rbp+pAce], 0
0x1800362f0  mov     edx, edi; dwAceIndex
0x1800362f2  call    cs:__imp_GetAce
0x1800362f8  test    eax, eax
0x1800362fa  jz      short loc_18003633A
0x1800362fc  mov     rbx, [rbp+pAce]
0x180036300  cmp     byte ptr [rbx], 0
0x180036303  jnz     short loc_18003633A
0x180036305  mov     eax, [rbx+4]
0x180036308  and     eax, 10001h
0x18003630d  cmp     eax, 10001h
0x180036312  jnz     short loc_18003633A
0x180036314  add     rbx, 8
0x180036318  mov     edx, 16h; WellKnownSidType
0x18003631d  mov     rcx, rbx; pSid
0x180036320  call    cs:__imp_IsWellKnownSid
0x180036326  test    eax, eax
0x180036328  jnz     short loc_18003633A
0x18003632a  lea     edx, [rax+54h]; WellKnownSidType
0x18003632d  mov     rcx, rbx; pSid
0x180036330  call    cs:__imp_IsWellKnownSid
0x180036336  test    eax, eax
0x180036338  jz      short loc_18003634A
0x18003633a  mov     rcx, [rbp+pDacl]
0x18003633e  inc     edi
0x180036340  xor     ebx, ebx
0x180036342  movzx   eax, word ptr [rcx+4]
0x180036346  cmp     edi, eax
0x180036348  jb      short loc_1800362E4
0x18003634a  test    rbx, rbx
0x18003634d  jz      short loc_180036385
0x18003634f  mov     rdx, rsi; StringSid
0x180036352  mov     rcx, rbx; Sid
0x180036355  call    cs:__imp_ConvertSidToStringSidW
0x18003635b  test    eax, eax
0x18003635d  jnz     short loc_180036378
0x18003635f  mov     edx, 190h; void *
0x180036364  mov     rcx, [rbp+18h]; this
0x180036368  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18003636f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036374  mov     ebx, eax
0x180036376  jmp     short loc_1800363A2
0x180036378  lea     rcx, [rbp+pSecurityDescriptor]
0x18003637c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180036381  xor     eax, eax
0x180036383  jmp     short loc_1800363AD
0x180036385  mov     edx, 18Fh; void *
0x18003638a  mov     ebx, 80070490h
0x18003638f  mov     r9d, ebx; char *
0x180036392  mov     rcx, [rbp+18h]; this
0x180036396  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18003639d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800363a2  lea     rcx, [rbp+pSecurityDescriptor]
0x1800363a6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800363ab  mov     eax, ebx
0x1800363ad  mov     rbx, [rsp+50h+arg_8]
0x1800363b2  add     rsp, 50h
0x1800363b6  pop     rdi
0x1800363b7  pop     rsi
0x1800363b8  pop     rbp
0x1800363b9  retn
```
