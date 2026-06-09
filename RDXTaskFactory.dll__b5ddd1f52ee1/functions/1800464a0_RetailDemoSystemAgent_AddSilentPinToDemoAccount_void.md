# RetailDemoSystemAgent::AddSilentPinToDemoAccount(void)

- ea: `0x1800464a0`
- end: `0x18004677d`
- name: `?AddSilentPinToDemoAccount@RetailDemoSystemAgent@@UEAAJXZ`
- size: `733`
- prototype: `__int64 __fastcall(RetailDemoSystemAgent *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800046b4`
- `0x18000aa5c`
- `0x18000aa7c`
- `0x18000e3bc`
- `0x180010a60`
- `0x180030538`
- `0x180031e88`
- `0x180046470`
- `0x1800464a0`
- `0x180046c00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800464e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046530`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800464e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046530`
- `CRYPT32!CryptUnprotectData` at `0x180046635`
- `CRYPT32!CryptUnprotectData` at `0x180046635`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalAddCredentialSilent` at `0x1800466c1`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalAddCredentialSilent` at `0x1800466c1`

## string_xrefs

- `0x180046526`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1800464d8`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x180046560`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemosystemagent\service\retaildemosystemagent.cpp`
- `0x180046647`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemosystemagent\service\retaildemosystemagent.cpp`
- `0x1800466d8`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemosystemagent\service\retaildemosystemagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RetailDemoSystemAgent::AddSilentPinToDemoAccount(RetailDemoSystemAgent *this)
{
  __int64 result; // rax
  unsigned __int16 **v2; // rdx
  const unsigned __int16 *v3; // rdx
  HKEY v4; // rcx
  const unsigned __int16 *v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ebx
  char v8; // bl
  const char *v9; // r9
  unsigned int LastError; // ebx
  __int64 cbData; // rax
  BYTE *pbData; // rcx
  BYTE *v13; // r8
  __int64 v14; // r9
  int v15; // eax
  int v16; // edi
  __int64 v17; // rax
  BYTE *v18; // rcx
  const char *v19; // r9
  __int64 v20; // rax
  BYTE *v21; // rcx
  int pdwType; // [rsp+20h] [rbp-68h]
  BYTE *v23; // [rsp+40h] [rbp-48h] BYREF
  DATA_BLOB pDataOut; // [rsp+48h] [rbp-40h] BYREF
  DATA_BLOB pDataIn; // [rsp+58h] [rbp-30h] BYREF
  char v26; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  DWORD pcbData; // [rsp+98h] [rbp+10h] BYREF
  int pvData; // [rsp+A0h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+A8h] [rbp+20h] BYREF

  pvData = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
         L"Enabled",
         0x10010u,
         0,
         &pvData,
         &pcbData) )
  {
    pcbData = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
      L"Enabled",
      0x20010010u,
      0,
      &pvData,
      &pcbData);
  }
  if ( !pvData )
    return 2147500033LL;
  if ( !(unsigned __int8)IsNgcLocalAddCredentialSilentPresent() )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemosystemagent\\service\\retaildemosystemagent.cpp",
      (const char *)0x80004001LL,
      pdwType);
    return 2147500033LL;
  }
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (void **)&StringSid,
    0);
  try
  {
    RetailDemoUtil::GetDemoUserSidString(&StringSid, v2);
    pDataOut = 0;
    pcbData = 0;
    v23 = 0;
    *(_QWORD *)&pDataIn.cbData = &v23;
    pDataIn.pbData = 0;
    v26 = 1;
    v7 = (unsigned int)SHRegAllocData(v4, v3, v5, v6, (void **)&pDataIn.pbData, &pcbData) >> 31;
    wil::details::out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>(&pDataIn);
    if ( (unsigned __int8)v7 != 1 )
    {
      v8 = 1;
      pDataIn.cbData = pcbData;
      *(&pDataIn.cbData + 1) = 0;
      pDataIn.pbData = v23;
      if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x39,
                      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemosystemagent\\service\\reta"
                                    "ildemosystemagent.cpp",
                      v9);
        wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(&v23, 0);
        cbData = pDataOut.cbData;
        pbData = pDataOut.pbData;
        if ( pDataOut.cbData )
        {
          do
          {
            *pbData++ = 0;
            --cbData;
          }
          while ( cbData );
        }
LABEL_20:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&StringSid);
        return LastError;
      }
      v13 = pDataOut.pbData;
      v14 = pDataOut.cbData;
    }
    else
    {
      v8 = 0;
      v13 = (BYTE *)&qword_180057BE0;
      pDataOut.pbData = (BYTE *)&qword_180057BE0;
      v14 = 2;
      pDataOut.cbData = 2;
    }
    v15 = NgcLocalAddCredentialSilent(StringSid, L"1234", v13, v14);
    v16 = v15;
    if ( v15 >= 0 )
    {
      wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(&v23, 0);
      if ( v8 )
      {
        v20 = pDataOut.cbData;
        v21 = pDataOut.pbData;
        if ( pDataOut.cbData )
        {
          do
          {
            *v21++ = 0;
            --v20;
          }
          while ( v20 );
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&StringSid);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemosystemagent\\service\\retaildemosystemagent.cpp",
      (const char *)(unsigned int)v15,
      0);
    wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(&v23, 0);
    if ( v8 )
    {
      v17 = pDataOut.cbData;
      v18 = pDataOut.pbData;
      if ( pDataOut.cbData )
      {
        do
        {
          *v18++ = 0;
          --v17;
        }
        while ( v17 );
      }
    }
    LastError = v16;
    goto LABEL_20;
  }
  catch ( ... )
  {
    pcbData = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x29,
                (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemosystemagent\\service\\retaildemosystemagent.cpp",
                v19);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&StringSid);
    return pcbData;
  }
  return result;
}

```

## disassembly

```asm
0x1800464a0  mov     r11, rsp
0x1800464a3  push    rbx
0x1800464a4  push    rsi
0x1800464a5  push    rdi
0x1800464a6  sub     rsp, 70h
0x1800464aa  xor     esi, esi
0x1800464ac  mov     [r11+18h], esi
0x1800464b0  lea     ebx, [rsi+4]
0x1800464b3  mov     [r11+10h], ebx
0x1800464b7  lea     rax, [r11+10h]
0x1800464bb  mov     [r11-58h], rax
0x1800464bf  lea     rax, [r11+18h]
0x1800464c3  mov     [r11-60h], rax
0x1800464c7  mov     [r11-68h], rsi
0x1800464cb  mov     r9d, 10010h; dwFlags
0x1800464d1  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1800464d8  lea     rdx, SubKey; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x1800464df  mov     rdi, 0FFFFFFFF80000002h
0x1800464e6  mov     rcx, rdi; hkey
0x1800464e9  call    cs:__imp_RegGetValueW
0x1800464ef  test    eax, eax
0x1800464f1  jz      short loc_180046536
0x1800464f3  mov     [rsp+88h+arg_8], ebx
0x1800464fa  lea     rax, [rsp+88h+arg_8]
0x180046502  mov     [rsp+88h+pcbData], rax; pcbData
0x180046507  lea     rax, [rsp+88h+arg_10]
0x18004650f  mov     [rsp+88h+pvData], rax; pvData
0x180046514  mov     [rsp+88h+pdwType], rsi; int
0x180046519  mov     r9d, 20010010h; dwFlags
0x18004651f  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x180046526  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004652d  mov     rcx, rdi; hkey
0x180046530  call    cs:__imp_RegGetValueW
0x180046536  cmp     [rsp+88h+arg_10], esi
0x18004653d  jnz     short loc_180046549
0x18004653f  mov     eax, 80004001h
0x180046544  jmp     loc_180046775
0x180046549  call    IsNgcLocalAddCredentialSilentPresent
0x18004654e  test    al, al
0x180046550  jnz     short loc_180046573
0x180046552  mov     rcx, [rsp+88h]; this
0x18004655a  mov     r9d, 80004001h; char *
0x180046560  lea     r8, aPcshellShellRe_22; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180046567  mov     edx, 22h ; '"'; void *
0x18004656c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046571  jmp     short loc_18004653F
0x180046573  mov     [rsp+88h+StringSid], rsi
0x18004657b  xor     edx, edx
0x18004657d  lea     rcx, [rsp+88h+StringSid]
0x180046585  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18004658a  lea     rcx, [rsp+88h+StringSid]; StringSid
0x180046592  call    ?GetDemoUserSidString@RetailDemoUtil@@YAXPEAPEAG@Z; RetailDemoUtil::GetDemoUserSidString(ushort * *)
0x180046597  nop
0x180046598  xorps   xmm0, xmm0
0x18004659b  movups  xmmword ptr [rsp+88h+pDataOut.cbData], xmm0
0x1800465a0  mov     [rsp+88h+arg_8], esi
0x1800465a7  mov     [rsp+88h+var_48], rsi
0x1800465ac  lea     rax, [rsp+88h+var_48]
0x1800465b1  mov     qword ptr [rsp+88h+pDataIn.cbData], rax
0x1800465b6  mov     [rsp+88h+pDataIn.pbData], rsi
0x1800465bb  mov     [rsp+88h+var_20], 1
0x1800465c0  lea     rax, [rsp+88h+arg_8]
0x1800465c8  mov     [rsp+88h+pvData], rax; unsigned int *
0x1800465cd  lea     rax, [rsp+88h+pDataIn.pbData]
0x1800465d2  mov     [rsp+88h+pdwType], rax; void **
0x1800465d7  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800465dc  mov     ebx, eax
0x1800465de  shr     ebx, 1Fh
0x1800465e1  lea     rcx, [rsp+88h+pDataIn]
0x1800465e6  call    ??1?$out_param_t@V?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>(void)
0x1800465eb  xor     bl, 1
0x1800465ee  jz      loc_180046693
0x1800465f4  mov     bl, 1
0x1800465f6  mov     eax, [rsp+88h+arg_8]
0x1800465fd  mov     [rsp+88h+pDataIn.cbData], eax
0x180046601  xor     eax, eax
0x180046603  mov     dword ptr [rsp+88h+pDataIn+4], eax
0x180046607  mov     rax, [rsp+88h+var_48]
0x18004660c  mov     [rsp+88h+pDataIn.pbData], rax
0x180046611  lea     rax, [rsp+88h+pDataOut]
0x180046616  mov     [rsp+88h+pcbData], rax; pDataOut
0x18004661b  mov     dword ptr [rsp+88h+pvData], 1; dwFlags
0x180046623  mov     [rsp+88h+pdwType], rsi; pPromptStruct
0x180046628  xor     r9d, r9d; pvReserved
0x18004662b  xor     r8d, r8d; pOptionalEntropy
0x18004662e  xor     edx, edx; ppszDataDescr
0x180046630  lea     rcx, [rsp+88h+pDataIn]; pDataIn
0x180046635  call    cs:__imp_CryptUnprotectData
0x18004663b  test    eax, eax
0x18004663d  jnz     short loc_180046687
0x18004663f  mov     rcx, [rsp+88h]; this
0x180046647  lea     r8, aPcshellShellRe_22; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18004664e  lea     edx, [rax+39h]; void *
0x180046651  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046656  mov     ebx, eax
0x180046658  xor     edx, edx
0x18004665a  lea     rcx, [rsp+88h+var_48]
0x18004665f  call    ?reset@?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(void *)
0x180046664  mov     eax, [rsp+88h+pDataOut.cbData]
0x180046668  mov     rcx, [rsp+88h+pDataOut.pbData]
0x18004666d  test    rax, rax
0x180046670  jz      loc_180046715
0x180046676  mov     [rcx], sil
0x180046679  inc     rcx
0x18004667c  sub     rax, 1
0x180046680  jnz     short loc_180046676
0x180046682  jmp     loc_180046715
0x180046687  mov     r8, [rsp+88h+pDataOut.pbData]
0x18004668c  mov     r9d, [rsp+88h+pDataOut.cbData]
0x180046691  jmp     short loc_1800466AD
0x180046693  mov     bl, sil
0x180046696  lea     r8, qword_180057BE0
0x18004669d  mov     [rsp+88h+pDataOut.pbData], r8
0x1800466a2  mov     r9d, 2
0x1800466a8  mov     [rsp+88h+pDataOut.cbData], r9d
0x1800466ad  mov     [rsp+88h+pdwType], rsi; int
0x1800466b2  lea     rdx, a1234; "1234"
0x1800466b9  mov     rcx, [rsp+88h+StringSid]
0x1800466c1  call    cs:__imp_NgcLocalAddCredentialSilent
0x1800466c7  mov     edi, eax
0x1800466c9  test    eax, eax
0x1800466cb  jns     short loc_180046726
0x1800466cd  mov     rcx, [rsp+88h]; this
0x1800466d5  mov     r9d, eax; char *
0x1800466d8  lea     r8, aPcshellShellRe_22; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800466df  mov     edx, 4Ah ; 'J'; void *
0x1800466e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800466e9  xor     edx, edx
0x1800466eb  lea     rcx, [rsp+88h+var_48]
0x1800466f0  call    ?reset@?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(void *)
0x1800466f5  test    bl, bl
0x1800466f7  jz      short loc_180046713
0x1800466f9  mov     eax, [rsp+88h+pDataOut.cbData]
0x1800466fd  mov     rcx, [rsp+88h+pDataOut.pbData]
0x180046702  test    rax, rax
0x180046705  jz      short loc_180046713
0x180046707  mov     [rcx], sil
0x18004670a  inc     rcx
0x18004670d  sub     rax, 1
0x180046711  jnz     short loc_180046707
0x180046713  mov     ebx, edi
0x180046715  lea     rcx, [rsp+88h+StringSid]
0x18004671d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180046722  mov     eax, ebx
0x180046724  jmp     short loc_180046775
0x180046726  xor     edx, edx
0x180046728  lea     rcx, [rsp+88h+var_48]
0x18004672d  call    ?reset@?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(void *)
0x180046732  test    bl, bl
0x180046734  jz      short loc_180046750
0x180046736  mov     eax, [rsp+88h+pDataOut.cbData]
0x18004673a  mov     rcx, [rsp+88h+pDataOut.pbData]
0x18004673f  test    rax, rax
0x180046742  jz      short loc_180046750
0x180046744  mov     [rcx], sil
0x180046747  inc     rcx
0x18004674a  sub     rax, 1
0x18004674e  jnz     short loc_180046744
0x180046750  lea     rcx, [rsp+88h+StringSid]
0x180046758  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004675d  xor     eax, eax
0x18004675f  jmp     short loc_180046775
0x180046761  lea     rcx, [rsp+88h+StringSid]
0x180046769  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004676e  mov     eax, [rsp+88h+arg_8]
0x180046775  add     rsp, 70h
0x180046779  pop     rdi
0x18004677a  pop     rsi
0x18004677b  pop     rbx
0x18004677c  retn
```
