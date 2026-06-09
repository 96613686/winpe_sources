# COSInstaller::COSInstaller(IUnknown *)

- ea: `0x18003c41c`
- end: `0x18003c6d2`
- name: `??0COSInstaller@@AEAA@PEAUIUnknown@@@Z`
- size: `694`
- prototype: `COSInstaller *__fastcall(COSInstaller *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007840`

## callees

- `0x180003180`
- `0x18000ba5c`
- `0x1800110fc`
- `0x1800125b4`
- `0x18003c41c`
- `0x180068ea0`
- `0x180069960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003c548`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003c59c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003c548`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003c59c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003c578`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003c5cc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003c578`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003c5cc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003c4da`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003c4da`

## string_xrefs

- `0x18003c623`: `Software\Classes\CLSID`
- `0x18003c66a`: `Failed to Setup JIT COM Server for OSInstaller`
- `0x18003c68f`: `Successfully registered OSDeploymentInformationFactory COM server`
- `0x18003c5f0`: `Registering OSDeploymentInformationFactory COM server as CLSID %ws and APPID %ws`

## pseudocode

```c
COSInstaller *__fastcall COSInstaller::COSInstaller(COSInstaller *this, struct IUnknown *a2)
{
  HRESULT v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r9
  HRESULT Guid; // ebx
  __int64 v8; // rcx
  int v9; // ebx
  int v10; // ebx
  OLECHAR *v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)this = &CUHHandlerDeployBase::`vftable'{for `ISusUpdateDeploy'};
  *((_QWORD *)this + 1) = &CUHHandlerDeployBase::`vftable'{for `ISusUpdatePostRebootResult'};
  *((_QWORD *)this + 2) = &CUHHandlerDeployBase::`vftable'{for `ISusQueryDeploymentCustomReportingData'};
  *((_QWORD *)this + 3) = &CUHHandlerDeployBase::`vftable'{for `IUpdateDeploymentHandlerInfo'};
  *((_QWORD *)this + 4) = 1;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  *((_DWORD *)this + 9) = 7;
  *((_QWORD *)this + 5) = a2;
  *((_DWORD *)this + 8) = 1;
  *(_QWORD *)this = &COSInstaller::`vftable'{for `ISusUpdateDeploy'};
  *((_QWORD *)this + 1) = &COSInstaller::`vftable'{for `ISusUpdatePostRebootResult'};
  *((_QWORD *)this + 2) = &CUHHandlerDeployBase::`vftable'{for `ISusQueryDeploymentCustomReportingData'};
  *((_QWORD *)this + 3) = &CUHHandlerDeployBase::`vftable'{for `IUpdateDeploymentHandlerInfo'};
  *((_BYTE *)this + 56) = 0;
  *((_QWORD *)this + 8) = &CSusLock::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = &CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::`vftable';
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = &CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::`vftable';
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = 2;
  *((_BYTE *)this + 172) = 0;
  if ( !memcmp(&Buf1, &GUID_NULL, 0x10u) && (v4 = CoCreateGuid(&Buf1), v4 < 0) )
  {
    v5 = 304;
    v6 = (unsigned int)v4;
  }
  else if ( StringFromGUID2(&Buf1, &sz, 39) )
  {
    Guid = CoCreateGuid(&pguid);
    v6 = (unsigned int)Guid;
    if ( Guid >= 0 )
    {
      if ( StringFromGUID2(&pguid, &word_1800A2628, 39) )
      {
        WUTrace(0, 0, 4096, 4);
        v12 = &word_1800A2628;
        v9 = RegSetStringValueOnVolatileKey(v8, L"Software\\Classes\\CLSID", &sz, L"AppID");
        v6 = (unsigned int)v9;
        if ( v9 >= 0 )
        {
          v10 = CWuaClassFactoryBase::RegisterClassFactory((CWuaClassFactoryBase *)&g_OSDeploymentInformationCFForDeployment);
          v6 = (unsigned int)v10;
          if ( v10 >= 0 )
          {
            WUTrace(0, 0, 4096, 4);
            byte_1800A25C8 = 1;
            return this;
          }
          v5 = 328;
        }
        else
        {
          v5 = 326;
        }
      }
      else
      {
        v6 = 2147942522LL;
        v5 = 313;
      }
    }
    else
    {
      v5 = 311;
    }
  }
  else
  {
    v6 = 2147942522LL;
    v5 = 308;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInformationFactory.cpp",
    (const char *)v6,
    (int)v12);
  WUTrace(0, 0, 4096, 2);
  return this;
}

```

## disassembly

```asm
0x18003c41c  mov     rax, rsp
0x18003c41f  mov     [rax+10h], rbx
0x18003c423  mov     [rax+18h], rbp
0x18003c427  mov     [rax+20h], rsi
0x18003c42b  mov     [rax+8], rcx
0x18003c42f  push    rdi
0x18003c430  sub     rsp, 40h
0x18003c434  mov     rbx, rdx
0x18003c437  mov     rdi, rcx
0x18003c43a  lea     rax, ??_7CUHHandlerDeployBase@@6BISusUpdateDeploy@@@; const CUHHandlerDeployBase::`vftable'{for `ISusUpdateDeploy'}
0x18003c441  mov     [rcx], rax
0x18003c444  lea     rax, ??_7CUHHandlerDeployBase@@6BISusUpdatePostRebootResult@@@; const CUHHandlerDeployBase::`vftable'{for `ISusUpdatePostRebootResult'}
0x18003c44b  mov     [rcx+8], rax
0x18003c44f  lea     rax, ??_7CUHHandlerDeployBase@@6BISusQueryDeploymentCustomReportingData@@@; const CUHHandlerDeployBase::`vftable'{for `ISusQueryDeploymentCustomReportingData'}
0x18003c456  mov     [rcx+10h], rax
0x18003c45a  lea     rax, ??_7CUHHandlerDeployBase@@6BIUpdateDeploymentHandlerInfo@@@; const CUHHandlerDeployBase::`vftable'{for `IUpdateDeploymentHandlerInfo'}
0x18003c461  mov     [rcx+18h], rax
0x18003c465  mov     qword ptr [rcx+20h], 1
0x18003c46d  xor     esi, esi
0x18003c46f  mov     [rcx+28h], rsi
0x18003c473  mov     [rcx+30h], esi
0x18003c476  test    rdx, rdx
0x18003c479  jz      short loc_18003C48A
0x18003c47b  mov     rax, [rdx]
0x18003c47e  mov     rcx, rdx
0x18003c481  mov     rax, [rax+8]
0x18003c485  call    _guard_dispatch_icall
0x18003c48a  mov     dword ptr [rdi+24h], 7
0x18003c491  mov     [rdi+28h], rbx
0x18003c495  mov     dword ptr [rdi+20h], 1
0x18003c49c  lea     rax, ??_7COSInstaller@@6BISusUpdateDeploy@@@; const COSInstaller::`vftable'{for `ISusUpdateDeploy'}
0x18003c4a3  mov     [rdi], rax
0x18003c4a6  lea     rax, ??_7COSInstaller@@6BISusUpdatePostRebootResult@@@; const COSInstaller::`vftable'{for `ISusUpdatePostRebootResult'}
0x18003c4ad  mov     [rdi+8], rax
0x18003c4b1  lea     rax, ??_7CUHHandlerDeployBase@@6BISusQueryDeploymentCustomReportingData@@@; const CUHHandlerDeployBase::`vftable'{for `ISusQueryDeploymentCustomReportingData'}
0x18003c4b8  mov     [rdi+10h], rax
0x18003c4bc  lea     rax, ??_7CUHHandlerDeployBase@@6BIUpdateDeploymentHandlerInfo@@@; const CUHHandlerDeployBase::`vftable'{for `IUpdateDeploymentHandlerInfo'}
0x18003c4c3  mov     [rdi+18h], rax
0x18003c4c7  mov     [rdi+38h], sil
0x18003c4cb  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x18003c4d2  mov     [rdi+40h], rax
0x18003c4d6  lea     rcx, [rdi+48h]; lpCriticalSection
0x18003c4da  call    cs:__imp_InitializeCriticalSection
0x18003c4e0  nop
0x18003c4e1  mov     [rdi+70h], rsi
0x18003c4e5  lea     rax, ??_7?$CSusArrayList@UtagDSGlobalUpdateId@@V?$CSusArrayListItemOpNoop@UtagDSGlobalUpdateId@@@@@@6B@; const CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::`vftable'
0x18003c4ec  mov     [rdi+78h], rax
0x18003c4f0  mov     [rdi+80h], rsi
0x18003c4f7  mov     [rdi+88h], rsi
0x18003c4fe  mov     [rdi+90h], rax
0x18003c505  mov     [rdi+98h], rsi
0x18003c50c  mov     [rdi+0A0h], rsi
0x18003c513  mov     dword ptr [rdi+0A8h], 2
0x18003c51d  mov     [rdi+0ACh], sil
0x18003c524  mov     r8d, 10h; Size
0x18003c52a  lea     rdx, GUID_NULL; Buf2
0x18003c531  lea     rcx, Buf1; Buf1
0x18003c538  call    memcmp
0x18003c53d  test    eax, eax
0x18003c53f  jnz     short loc_18003C561
0x18003c541  lea     rcx, Buf1; pguid
0x18003c548  call    cs:__imp_CoCreateGuid
0x18003c54e  mov     ebx, eax
0x18003c550  test    eax, eax
0x18003c552  jns     short loc_18003C561
0x18003c554  mov     edx, 130h
0x18003c559  mov     r9d, eax
0x18003c55c  jmp     loc_18003C659
0x18003c561  mov     r8d, 27h ; '''; cchMax
0x18003c567  lea     rbp, sz
0x18003c56e  mov     rdx, rbp; lpsz
0x18003c571  lea     rcx, Buf1; rguid
0x18003c578  call    cs:__imp_StringFromGUID2
0x18003c57e  test    eax, eax
0x18003c580  jnz     short loc_18003C595
0x18003c582  mov     r9d, 8007007Ah
0x18003c588  mov     ebx, r9d
0x18003c58b  mov     edx, 134h
0x18003c590  jmp     loc_18003C659
0x18003c595  lea     rcx, pguid; pguid
0x18003c59c  call    cs:__imp_CoCreateGuid
0x18003c5a2  mov     ebx, eax
0x18003c5a4  mov     r9d, eax
0x18003c5a7  test    eax, eax
0x18003c5a9  jns     short loc_18003C5B5
0x18003c5ab  mov     edx, 137h
0x18003c5b0  jmp     loc_18003C659
0x18003c5b5  mov     r8d, 27h ; '''; cchMax
0x18003c5bb  lea     rbx, word_1800A2628
0x18003c5c2  mov     rdx, rbx; lpsz
0x18003c5c5  lea     rcx, pguid; rguid
0x18003c5cc  call    cs:__imp_StringFromGUID2
0x18003c5d2  test    eax, eax
0x18003c5d4  jnz     short loc_18003C5E6
0x18003c5d6  mov     r9d, 8007007Ah
0x18003c5dc  mov     ebx, r9d
0x18003c5df  mov     edx, 139h
0x18003c5e4  jmp     short loc_18003C659
0x18003c5e6  mov     [rsp+48h+var_10], rbx
0x18003c5eb  mov     [rsp+48h+var_18], rbp
0x18003c5f0  lea     rax, aRegisteringOsd; "Registering OSDeploymentInformationFact"...
0x18003c5f7  mov     [rsp+48h+var_20], rax
0x18003c5fc  mov     qword ptr [rsp+48h+var_28], rsi
0x18003c601  xor     edx, edx
0x18003c603  xor     ecx, ecx
0x18003c605  lea     r9d, [rdx+4]
0x18003c609  mov     r8d, 1000h
0x18003c60f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003c614  mov     qword ptr [rsp+48h+var_28], rbx; int
0x18003c619  lea     r9, aAppid; "AppID"
0x18003c620  mov     r8, rbp
0x18003c623  lea     rdx, aSoftwareClasse; "Software\\Classes\\CLSID"
0x18003c62a  call    ?RegSetStringValueOnVolatileKey@@YAJPEAUHKEY__@@PEB_W111W4RegistryHiveType@@@Z; RegSetStringValueOnVolatileKey(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x18003c62f  mov     ebx, eax
0x18003c631  mov     r9d, eax
0x18003c634  test    eax, eax
0x18003c636  jns     short loc_18003C63F
0x18003c638  mov     edx, 146h
0x18003c63d  jmp     short loc_18003C659
0x18003c63f  lea     rcx, ?g_OSDeploymentInformationCFForDeployment@@3VOSDeploymentInformationFactory@@A; this
0x18003c646  call    ?RegisterClassFactory@CWuaClassFactoryBase@@QEAAJXZ; CWuaClassFactoryBase::RegisterClassFactory(void)
0x18003c64b  mov     ebx, eax
0x18003c64d  mov     r9d, eax; char *
0x18003c650  test    eax, eax
0x18003c652  jns     short loc_18003C68F
0x18003c654  mov     edx, 148h; void *
0x18003c659  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003c660  mov     rcx, [rsp+48h]; this
0x18003c665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c66a  lea     rax, aFailedToSetupJ; "Failed to Setup JIT COM Server for OSIn"...
0x18003c671  mov     [rsp+48h+var_20], rax
0x18003c676  mov     [rsp+48h+var_28], ebx
0x18003c67a  xor     edx, edx
0x18003c67c  xor     ecx, ecx
0x18003c67e  lea     r9d, [rdx+2]
0x18003c682  mov     r8d, 1000h
0x18003c688  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003c68d  jmp     short loc_18003C6BA
0x18003c68f  lea     rax, aSuccessfullyRe_0; "Successfully registered OSDeploymentInf"...
0x18003c696  mov     [rsp+48h+var_20], rax
0x18003c69b  mov     qword ptr [rsp+48h+var_28], rsi
0x18003c6a0  xor     edx, edx
0x18003c6a2  xor     ecx, ecx
0x18003c6a4  lea     r9d, [rdx+4]
0x18003c6a8  mov     r8d, 1000h
0x18003c6ae  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003c6b3  mov     cs:byte_1800A25C8, 1
0x18003c6ba  mov     rax, rdi
0x18003c6bd  mov     rbx, [rsp+48h+arg_8]
0x18003c6c2  mov     rbp, [rsp+48h+arg_10]
0x18003c6c7  mov     rsi, [rsp+48h+arg_18]
0x18003c6cc  add     rsp, 40h
0x18003c6d0  pop     rdi
0x18003c6d1  retn
```
