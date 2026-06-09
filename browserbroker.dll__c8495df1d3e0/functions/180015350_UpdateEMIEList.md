# UpdateEMIEList

- ea: `0x180015350`
- end: `0x180015476`
- name: `UpdateEMIEList`
- size: `294`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800152ac`

## callees

- `0x180002ce0`
- `0x180002d3c`
- `0x1800037ac`
- `0x180006cc4`
- `0x18000f800`
- `0x180014af0`
- `0x180014c9c`
- `0x180015350`
- `0x18002148c`
- `0x18002b4e0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180015432`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180015432`
- `urlmon!UrlmonCleanupCurrentThread` at `0x180015443`
- `urlmon!UrlmonCleanupCurrentThread` at `0x180015443`
- `urlmon!__imp_CreateDomainListBrowserEmulationFilter` at `0x180015409`
- `urlmon!__imp_CreateDomainListBrowserEmulationFilter` at `0x180015409`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 UpdateEMIEList()
{
  unsigned int String; // ebx
  CBrokerDownloadBindStatusCallback *v1; // rax
  int v2; // r8d
  __int64 v4; // [rsp+20h] [rbp-E0h] BYREF
  CBrokerDownloadBindStatusCallback *v5; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR FileName[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v7[2088]; // [rsp+240h] [rbp+140h] BYREF

  String = GetString((__int64 *)SettingStore::IEVALUE_Browser_EnterpriseMode_SiteList[0], v7);
  if ( !String )
  {
    memset_0(FileName, 0, 0x208u);
    v1 = (CBrokerDownloadBindStatusCallback *)operator new(0x28u);
    v5 = CBrokerDownloadBindStatusCallback::CBrokerDownloadBindStatusCallback(v1, 5242880);
    String = DownloadToTempFile(
               v7,
               FileName,
               v2,
               (struct IBindStatusCallback *)(((unsigned __int64)v5 + 16) & -(__int64)(v5 != 0)));
    if ( !String )
    {
      v4 = 0;
      String = CreateDomainListBrowserEmulationFilter(5, &v4);
      if ( !String )
        String = (*(__int64 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v4 + 72LL))(v4, FileName);
      DeleteFileW(FileName);
      ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(&v4);
    }
    UrlmonCleanupCurrentThread();
    ATL::CComPtrBase<CBrokerDownloadBindStatusCallback>::~CComPtrBase<CBrokerDownloadBindStatusCallback>((__int64 *)&v5);
  }
  return String;
}

```

## disassembly

```asm
0x180015350  mov     [rsp-8+arg_0], rbx
0x180015355  push    rbp
0x180015356  lea     rbp, [rsp-11A0h]
0x18001535e  mov     eax, 12A0h
0x180015363  call    _alloca_probe
0x180015368  sub     rsp, rax
0x18001536b  mov     rax, cs:__security_cookie
0x180015372  xor     rax, rsp
0x180015375  mov     [rbp+11A0h+var_10], rax
0x18001537c  lea     rdx, [rbp+11A0h+var_1060]
0x180015383  mov     rcx, cs:?IEVALUE_Browser_EnterpriseMode_SiteList@SettingStore@@3U?$VALUEID@PEAG@1@B; SettingStore::VALUEID<ushort *> const SettingStore::IEVALUE_Browser_EnterpriseMode_SiteList
0x18001538a  call    GetString
0x18001538f  mov     ebx, eax
0x180015391  test    eax, eax
0x180015393  jnz     loc_180015454
0x180015399  xor     edx, edx; Val
0x18001539b  mov     r8d, 208h; Size
0x1800153a1  lea     rcx, [rsp+12A0h+FileName]; void *
0x1800153a6  call    memset_0
0x1800153ab  mov     [rsp+12A0h+var_1278], 0
0x1800153b4  lea     ecx, [rbx+28h]; Size
0x1800153b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800153bc  mov     [rsp+12A0h+var_1278], rax
0x1800153c1  mov     edx, 500000h; unsigned int
0x1800153c6  mov     rcx, rax; this
0x1800153c9  call    ??0CBrokerDownloadBindStatusCallback@@QEAA@K@Z; CBrokerDownloadBindStatusCallback::CBrokerDownloadBindStatusCallback(ulong)
0x1800153ce  nop
0x1800153cf  mov     [rsp+12A0h+var_1278], rax
0x1800153d4  lea     rcx, [rax+10h]
0x1800153d8  neg     rax
0x1800153db  sbb     r9, r9
0x1800153de  and     r9, rcx; struct IBindStatusCallback *
0x1800153e1  lea     rdx, [rsp+12A0h+FileName]; unsigned __int16 *
0x1800153e6  lea     rcx, [rbp+11A0h+var_1060]; LPCWSTR
0x1800153ed  call    ?DownloadToTempFile@@YAJPEBGPEAGKPEAUIBindStatusCallback@@@Z; DownloadToTempFile(ushort const *,ushort *,ulong,IBindStatusCallback *)
0x1800153f2  mov     ebx, eax
0x1800153f4  test    eax, eax
0x1800153f6  jnz     short loc_180015443
0x1800153f8  mov     [rsp+12A0h+var_1280], 0
0x180015401  lea     rdx, [rsp+12A0h+var_1280]
0x180015406  lea     ecx, [rax+5]
0x180015409  call    cs:__imp_CreateDomainListBrowserEmulationFilter
0x18001540f  mov     ebx, eax
0x180015411  test    eax, eax
0x180015413  jnz     short loc_18001542D
0x180015415  mov     rcx, [rsp+12A0h+var_1280]
0x18001541a  mov     rax, [rcx]
0x18001541d  lea     rdx, [rsp+12A0h+FileName]
0x180015422  mov     rax, [rax+48h]
0x180015426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001542b  mov     ebx, eax
0x18001542d  lea     rcx, [rsp+12A0h+FileName]; lpFileName
0x180015432  call    cs:__imp_DeleteFileW
0x180015438  nop
0x180015439  lea     rcx, [rsp+12A0h+var_1280]
0x18001543e  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180015443  call    cs:__imp_UrlmonCleanupCurrentThread
0x180015449  nop
0x18001544a  lea     rcx, [rsp+12A0h+var_1278]
0x18001544f  call    ??1?$CComPtrBase@VCBrokerDownloadBindStatusCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CBrokerDownloadBindStatusCallback>::~CComPtrBase<CBrokerDownloadBindStatusCallback>(void)
0x180015454  mov     eax, ebx
0x180015456  mov     rcx, [rbp+11A0h+var_10]
0x18001545d  xor     rcx, rsp; StackCookie
0x180015460  call    __security_check_cookie
0x180015465  mov     rbx, [rsp+12A0h+arg_0]
0x18001546d  add     rsp, 12A0h
0x180015474  pop     rbp
0x180015475  retn
```
