# CGlob::GlobInit(void)

- ea: `0x180003d0c`
- end: `0x180003dc7`
- name: `?GlobInit@CGlob@@QEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(CGlob *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003c54`

## callees

- `0x180003d0c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180025be3`
- `ADVAPI32!RegCloseKey` at `0x180025be3`
- `ADVAPI32!RegQueryValueExA` at `0x180025667`
- `ADVAPI32!RegQueryValueExA` at `0x1800256b3`
- `ADVAPI32!RegQueryValueExA` at `0x180025701`
- `ADVAPI32!RegQueryValueExA` at `0x18002574e`
- `ADVAPI32!RegQueryValueExA` at `0x18002579c`
- `ADVAPI32!RegQueryValueExA` at `0x1800257ea`
- `ADVAPI32!RegQueryValueExA` at `0x180025838`
- `ADVAPI32!RegQueryValueExA` at `0x180025886`
- `ADVAPI32!RegQueryValueExA` at `0x1800258d8`
- `ADVAPI32!RegQueryValueExA` at `0x18002592a`
- `ADVAPI32!RegQueryValueExA` at `0x18002597c`
- `ADVAPI32!RegQueryValueExA` at `0x1800259ce`
- `ADVAPI32!RegQueryValueExA` at `0x180025a20`
- `ADVAPI32!RegQueryValueExA` at `0x180025a72`
- `ADVAPI32!RegQueryValueExA` at `0x180025ac4`
- `ADVAPI32!RegQueryValueExA` at `0x180025b16`
- `ADVAPI32!RegQueryValueExA` at `0x180025b68`
- `ADVAPI32!RegQueryValueExA` at `0x180025bba`
- `ADVAPI32!RegQueryValueExA` at `0x180025667`
- `ADVAPI32!RegQueryValueExA` at `0x1800256b3`
- `ADVAPI32!RegQueryValueExA` at `0x180025701`
- `ADVAPI32!RegQueryValueExA` at `0x18002574e`
- `ADVAPI32!RegQueryValueExA` at `0x18002579c`
- `ADVAPI32!RegQueryValueExA` at `0x1800257ea`
- `ADVAPI32!RegQueryValueExA` at `0x180025838`
- `ADVAPI32!RegQueryValueExA` at `0x180025886`
- `ADVAPI32!RegQueryValueExA` at `0x1800258d8`
- `ADVAPI32!RegQueryValueExA` at `0x18002592a`
- `ADVAPI32!RegQueryValueExA` at `0x18002597c`
- `ADVAPI32!RegQueryValueExA` at `0x1800259ce`
- `ADVAPI32!RegQueryValueExA` at `0x180025a20`
- `ADVAPI32!RegQueryValueExA` at `0x180025a72`
- `ADVAPI32!RegQueryValueExA` at `0x180025ac4`
- `ADVAPI32!RegQueryValueExA` at `0x180025b16`
- `ADVAPI32!RegQueryValueExA` at `0x180025b68`
- `ADVAPI32!RegQueryValueExA` at `0x180025bba`
- `ADVAPI32!RegOpenKeyExA` at `0x180003d58`
- `ADVAPI32!RegOpenKeyExA` at `0x180003d58`
- `KERNEL32!GetLastError` at `0x180003d79`
- `KERNEL32!GetLastError` at `0x180003d79`
- `iisutil!IISInitializeCriticalSection` at `0x180003d6f`
- `iisutil!IISInitializeCriticalSection` at `0x180003d6f`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180003da8`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180003da8`

## string_xrefs

- `0x180003d4a`: `System\CurrentControlSet\Services\ASP\Parameters`
- `0x1800256f5`: `HangDetThreadHungThreshold`
- `0x180025a14`: `ThreadMax`
- `0x180025a66`: `DisableComPlusCpuMetric`
- `0x180025b5c`: `DisableCachedResponseOnUNCAccessFailure`

## pseudocode

```c
int __fastcall CGlob::GlobInit(CGlob *this)
{
  signed int v1; // edi
  signed int LastError; // eax
  int result; // eax
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  int v5; // [rsp+54h] [rbp+Ch]
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  v5 = HIDWORD(this);
  HIDWORD(qword_180079F70) = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\ASP\\Parameters", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "F5AttackDetectionEnabled", 0, &Type, &Data, &cbData) == 0)
                        | g_AspRegistryParams & 0xFFFFFFFE;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "HangDetRequestThreshold", 0, &Type, &dword_18007D838, &cbData) == 0
                         ? 2
                         : 0)
                        | g_AspRegistryParams & 0xFFFFFFFD;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "HangDetThreadHungThreshold", 0, &Type, &dword_18007D83C, &cbData) == 0
                         ? 4
                         : 0)
                        | g_AspRegistryParams & 0xFFFFFFFB;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(
                             hKey,
                             "HangDetConsecIllStatesThreshold",
                             0,
                             &Type,
                             &dword_18007D840,
                             &cbData) == 0
                         ? 8
                         : 0)
                        | g_AspRegistryParams & 0xFFFFFFF7;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "HangDetEnabled", 0, &Type, &dword_18007D844, &cbData) == 0 ? 0x10 : 0)
                        | g_AspRegistryParams & 0xFFFFFFEF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "EnableChangeNotificationForUNC", 0, &Type, &dword_18007D848, &cbData) == 0
                         ? 0x20
                         : 0)
                        | g_AspRegistryParams & 0xFFFFFFDF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "FileMonitoringEnabled", 0, &Type, &dword_18007D84C, &cbData) == 0
                         ? 0x40
                         : 0)
                        | g_AspRegistryParams & 0xFFFFFFBF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "FileMonitoringTimeoutSeconds", 0, &Type, &dword_18007D850, &cbData) == 0
                         ? 0x80
                         : 0)
                        | g_AspRegistryParams & 0xFFFFFF7F;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "MaxCSR", 0, &Type, &dword_18007D854, &cbData) == 0 ? 0x100 : 0)
                        | g_AspRegistryParams & 0xFFFFFEFF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "MaxCPU", 0, &Type, &dword_18007D858, &cbData) == 0 ? 0x200 : 0)
                        | g_AspRegistryParams & 0xFFFFFDFF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "DisableOOMRecycle", 0, &Type, &dword_18007D85C, &cbData) == 0
                         ? 0x400
                         : 0)
                        | g_AspRegistryParams & 0xFFFFFBFF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "DisableLazyContentPropagation", 0, &Type, &dword_18007D860, &cbData) == 0
                         ? 0x800
                         : 0)
                        | g_AspRegistryParams & 0xFFFFF7FF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "ThreadMax", 0, &Type, &dword_18007D864, &cbData) == 0 ? 0x1000 : 0)
                        | g_AspRegistryParams & 0xFFFFEFFF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "DisableComPlusCpuMetric", 0, &Type, &dword_18007D868, &cbData) == 0
                         ? 0x2000
                         : 0)
                        | g_AspRegistryParams & 0xFFFFDFFF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "AspMaxResponseHeaderLength", 0, &Type, &dword_18007D86C, &cbData) == 0
                         ? 0x8000
                         : 0)
                        | g_AspRegistryParams & 0xFFFF7FFF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(hKey, "AspMaxPropertyStringLength", 0, &Type, &dword_18007D870, &cbData) == 0
                         ? 0x10000
                         : 0)
                        | g_AspRegistryParams & 0xFFFEFFFF;
    cbData = 4;
    g_AspRegistryParams = (RegQueryValueExA(
                             hKey,
                             "DisableCachedResponseOnUNCAccessFailure",
                             0,
                             &Type,
                             &dword_18007D874,
                             &cbData) == 0
                         ? 0x20000
                         : 0)
                        | g_AspRegistryParams & 0xFFFDFFFF;
    cbData = 4;
    g_AspRegistryParams = g_AspRegistryParams & 0xFFFFBFFF
                        | (RegQueryValueExA(hKey, "DisableCertificateBlobAsArray", 0, &Type, &dword_18007D878, &cbData) == 0
                         ? 0x4000
                         : 0);
    RegCloseKey(hKey);
  }
  v1 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&stru_180079FC0) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v1 < 0 )
    return v1;
  result = GetDefaultNativeConfigurationSystem(&g_pConfigSystem);
  if ( result >= 0 )
    *(__int64 *)((char *)&qword_180079F70 + 4) = 1;
  return result;
}

```

## disassembly

```asm
0x180003d0c  mov     rax, rsp
0x180003d0f  mov     [rax+8], rcx
0x180003d13  push    rdi
0x180003d14  sub     rsp, 40h
0x180003d18  mov     dword ptr cs:qword_180079F70+4, 0
0x180003d22  mov     qword ptr [rax+18h], 0
0x180003d2a  mov     dword ptr [rax+10h], 0
0x180003d31  mov     dword ptr [rax+8], 0
0x180003d38  lea     rax, [rax+18h]
0x180003d3c  mov     [rsp+48h+phkResult], rax; phkResult
0x180003d41  mov     r9d, 20019h; samDesired
0x180003d47  xor     r8d, r8d; ulOptions
0x180003d4a  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\AS"...
0x180003d51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003d58  call    cs:__imp_RegOpenKeyExA
0x180003d5e  test    eax, eax
0x180003d60  jz      loc_180025634
0x180003d66  xor     edi, edi
0x180003d68  lea     rcx, stru_180079FC0
0x180003d6f  call    cs:__imp_IISInitializeCriticalSection
0x180003d75  test    eax, eax
0x180003d77  jnz     short loc_180003D92
0x180003d79  call    cs:__imp_GetLastError
0x180003d7f  mov     edi, eax
0x180003d81  test    eax, eax
0x180003d83  jle     short loc_180003D8E
0x180003d85  movzx   edi, ax
0x180003d88  or      edi, 80070000h
0x180003d8e  mov     [rsp+48h+var_18], edi
0x180003d92  jmp     short loc_180003D9D
0x180003d94  mov     edi, 8000FFFFh
0x180003d99  mov     [rsp+48h+var_18], edi
0x180003d9d  test    edi, edi
0x180003d9f  js      short loc_180003DC3
0x180003da1  lea     rcx, ?g_pConfigSystem@@3PEAVINativeConfigurationSystem@@EA; INativeConfigurationSystem * g_pConfigSystem
0x180003da8  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x180003dae  test    eax, eax
0x180003db0  js      short loc_180003DBD
0x180003db2  mov     cs:qword_180079F70+4, 1
0x180003dbd  add     rsp, 40h
0x180003dc1  pop     rdi
0x180003dc2  retn
0x180003dc3  mov     eax, edi
0x180003dc5  jmp     short loc_180003DBD
0x180025634  mov     edi, 4
0x180025639  mov     [rsp+48h+cbData], edi
0x18002563d  lea     rax, [rsp+48h+cbData]
0x180025642  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180025647  lea     rax, Data
0x18002564e  mov     [rsp+48h+phkResult], rax; lpData
0x180025653  lea     r9, [rsp+48h+Type]; lpType
0x180025658  xor     r8d, r8d; lpReserved
0x18002565b  lea     rdx, ValueName; "F5AttackDetectionEnabled"
0x180025662  mov     rcx, [rsp+48h+hKey]; hKey
0x180025667  call    cs:__imp_RegQueryValueExA
0x18002566d  xor     ecx, ecx
0x18002566f  test    eax, eax
0x180025671  setz    cl
0x180025674  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x18002567a  and     eax, 0FFFFFFFEh
0x18002567d  or      eax, ecx
0x18002567f  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x180025685  mov     [rsp+48h+cbData], edi
0x180025689  lea     rax, [rsp+48h+cbData]
0x18002568e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180025693  lea     rax, dword_18007D838
0x18002569a  mov     [rsp+48h+phkResult], rax; lpData
0x18002569f  lea     r9, [rsp+48h+Type]; lpType
0x1800256a4  xor     r8d, r8d; lpReserved
0x1800256a7  lea     rdx, aHangdetrequest; "HangDetRequestThreshold"
0x1800256ae  mov     rcx, [rsp+48h+hKey]; hKey
0x1800256b3  call    cs:__imp_RegQueryValueExA
0x1800256b9  neg     eax
0x1800256bb  sbb     ecx, ecx
0x1800256bd  not     ecx
0x1800256bf  and     ecx, 2
0x1800256c2  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x1800256c8  and     eax, 0FFFFFFFDh
0x1800256cb  or      eax, ecx
0x1800256cd  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x1800256d3  mov     [rsp+48h+cbData], edi
0x1800256d7  lea     rax, [rsp+48h+cbData]
0x1800256dc  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800256e1  lea     rax, dword_18007D83C
0x1800256e8  mov     [rsp+48h+phkResult], rax; lpData
0x1800256ed  lea     r9, [rsp+48h+Type]; lpType
0x1800256f2  xor     r8d, r8d; lpReserved
0x1800256f5  lea     rdx, aHangdetthreadh; "HangDetThreadHungThreshold"
0x1800256fc  mov     rcx, [rsp+48h+hKey]; hKey
0x180025701  call    cs:__imp_RegQueryValueExA
0x180025707  neg     eax
0x180025709  sbb     ecx, ecx
0x18002570b  not     ecx
0x18002570d  and     ecx, edi
0x18002570f  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x180025715  and     eax, 0FFFFFFFBh
0x180025718  or      eax, ecx
0x18002571a  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x180025720  mov     [rsp+48h+cbData], edi
0x180025724  lea     rax, [rsp+48h+cbData]
0x180025729  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002572e  lea     rax, dword_18007D840
0x180025735  mov     [rsp+48h+phkResult], rax; lpData
0x18002573a  lea     r9, [rsp+48h+Type]; lpType
0x18002573f  xor     r8d, r8d; lpReserved
0x180025742  lea     rdx, aHangdetconseci; "HangDetConsecIllStatesThreshold"
0x180025749  mov     rcx, [rsp+48h+hKey]; hKey
0x18002574e  call    cs:__imp_RegQueryValueExA
0x180025754  neg     eax
0x180025756  sbb     ecx, ecx
0x180025758  not     ecx
0x18002575a  and     ecx, 8
0x18002575d  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x180025763  and     eax, 0FFFFFFF7h
0x180025766  or      eax, ecx
0x180025768  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x18002576e  mov     [rsp+48h+cbData], edi
0x180025772  lea     rax, [rsp+48h+cbData]
0x180025777  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002577c  lea     rax, dword_18007D844
0x180025783  mov     [rsp+48h+phkResult], rax; lpData
0x180025788  lea     r9, [rsp+48h+Type]; lpType
0x18002578d  xor     r8d, r8d; lpReserved
0x180025790  lea     rdx, aHangdetenabled; "HangDetEnabled"
0x180025797  mov     rcx, [rsp+48h+hKey]; hKey
0x18002579c  call    cs:__imp_RegQueryValueExA
0x1800257a2  neg     eax
0x1800257a4  sbb     ecx, ecx
0x1800257a6  not     ecx
0x1800257a8  and     ecx, 10h
0x1800257ab  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x1800257b1  and     eax, 0FFFFFFEFh
0x1800257b4  or      eax, ecx
0x1800257b6  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x1800257bc  mov     [rsp+48h+cbData], edi
0x1800257c0  lea     rax, [rsp+48h+cbData]
0x1800257c5  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800257ca  lea     rax, dword_18007D848
0x1800257d1  mov     [rsp+48h+phkResult], rax; lpData
0x1800257d6  lea     r9, [rsp+48h+Type]; lpType
0x1800257db  xor     r8d, r8d; lpReserved
0x1800257de  lea     rdx, aEnablechangeno; "EnableChangeNotificationForUNC"
0x1800257e5  mov     rcx, [rsp+48h+hKey]; hKey
0x1800257ea  call    cs:__imp_RegQueryValueExA
0x1800257f0  neg     eax
0x1800257f2  sbb     ecx, ecx
0x1800257f4  not     ecx
0x1800257f6  and     ecx, 20h
0x1800257f9  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x1800257ff  and     eax, 0FFFFFFDFh
0x180025802  or      eax, ecx
0x180025804  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x18002580a  mov     [rsp+48h+cbData], edi
0x18002580e  lea     rax, [rsp+48h+cbData]
0x180025813  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180025818  lea     rax, dword_18007D84C
0x18002581f  mov     [rsp+48h+phkResult], rax; lpData
0x180025824  lea     r9, [rsp+48h+Type]; lpType
0x180025829  xor     r8d, r8d; lpReserved
0x18002582c  lea     rdx, aFilemonitoring; "FileMonitoringEnabled"
0x180025833  mov     rcx, [rsp+48h+hKey]; hKey
0x180025838  call    cs:__imp_RegQueryValueExA
0x18002583e  neg     eax
0x180025840  sbb     ecx, ecx
0x180025842  not     ecx
0x180025844  and     ecx, 40h
0x180025847  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x18002584d  and     eax, 0FFFFFFBFh
0x180025850  or      eax, ecx
0x180025852  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x180025858  mov     [rsp+48h+cbData], edi
0x18002585c  lea     rax, [rsp+48h+cbData]
0x180025861  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180025866  lea     rax, dword_18007D850
0x18002586d  mov     [rsp+48h+phkResult], rax; lpData
0x180025872  lea     r9, [rsp+48h+Type]; lpType
0x180025877  xor     r8d, r8d; lpReserved
0x18002587a  lea     rdx, aFilemonitoring_0; "FileMonitoringTimeoutSeconds"
0x180025881  mov     rcx, [rsp+48h+hKey]; hKey
0x180025886  call    cs:__imp_RegQueryValueExA
0x18002588c  neg     eax
0x18002588e  sbb     ecx, ecx
0x180025890  not     ecx
0x180025892  and     ecx, 80h
0x180025898  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x18002589e  btr     eax, 7
0x1800258a2  or      eax, ecx
0x1800258a4  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x1800258aa  mov     [rsp+48h+cbData], edi
0x1800258ae  lea     rax, [rsp+48h+cbData]
0x1800258b3  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800258b8  lea     rax, dword_18007D854
0x1800258bf  mov     [rsp+48h+phkResult], rax; lpData
0x1800258c4  lea     r9, [rsp+48h+Type]; lpType
0x1800258c9  xor     r8d, r8d; lpReserved
0x1800258cc  lea     rdx, aMaxcsr; "MaxCSR"
0x1800258d3  mov     rcx, [rsp+48h+hKey]; hKey
0x1800258d8  call    cs:__imp_RegQueryValueExA
0x1800258de  neg     eax
0x1800258e0  sbb     ecx, ecx
0x1800258e2  not     ecx
0x1800258e4  and     ecx, 100h
0x1800258ea  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x1800258f0  btr     eax, 8
0x1800258f4  or      eax, ecx
0x1800258f6  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x1800258fc  mov     [rsp+48h+cbData], edi
0x180025900  lea     rax, [rsp+48h+cbData]
0x180025905  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002590a  lea     rax, dword_18007D858
0x180025911  mov     [rsp+48h+phkResult], rax; lpData
0x180025916  lea     r9, [rsp+48h+Type]; lpType
0x18002591b  xor     r8d, r8d; lpReserved
0x18002591e  lea     rdx, aMaxcpu; "MaxCPU"
0x180025925  mov     rcx, [rsp+48h+hKey]; hKey
0x18002592a  call    cs:__imp_RegQueryValueExA
0x180025930  neg     eax
0x180025932  sbb     ecx, ecx
0x180025934  not     ecx
0x180025936  and     ecx, 200h
0x18002593c  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x180025942  btr     eax, 9
0x180025946  or      eax, ecx
0x180025948  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x18002594e  mov     [rsp+48h+cbData], edi
0x180025952  lea     rax, [rsp+48h+cbData]
0x180025957  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002595c  lea     rax, dword_18007D85C
0x180025963  mov     [rsp+48h+phkResult], rax; lpData
0x180025968  lea     r9, [rsp+48h+Type]; lpType
0x18002596d  xor     r8d, r8d; lpReserved
0x180025970  lea     rdx, aDisableoomrecy; "DisableOOMRecycle"
0x180025977  mov     rcx, [rsp+48h+hKey]; hKey
0x18002597c  call    cs:__imp_RegQueryValueExA
0x180025982  neg     eax
0x180025984  sbb     ecx, ecx
0x180025986  not     ecx
0x180025988  and     ecx, 400h
0x18002598e  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x180025994  btr     eax, 0Ah
0x180025998  or      eax, ecx
0x18002599a  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x1800259a0  mov     [rsp+48h+cbData], edi
0x1800259a4  lea     rax, [rsp+48h+cbData]
0x1800259a9  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800259ae  lea     rax, dword_18007D860
0x1800259b5  mov     [rsp+48h+phkResult], rax; lpData
0x1800259ba  lea     r9, [rsp+48h+Type]; lpType
0x1800259bf  xor     r8d, r8d; lpReserved
0x1800259c2  lea     rdx, aDisablelazycon; "DisableLazyContentPropagation"
0x1800259c9  mov     rcx, [rsp+48h+hKey]; hKey
0x1800259ce  call    cs:__imp_RegQueryValueExA
0x1800259d4  neg     eax
0x1800259d6  sbb     ecx, ecx
0x1800259d8  not     ecx
0x1800259da  and     ecx, 800h
0x1800259e0  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x1800259e6  btr     eax, 0Bh
0x1800259ea  or      eax, ecx
0x1800259ec  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x1800259f2  mov     [rsp+48h+cbData], edi
0x1800259f6  lea     rax, [rsp+48h+cbData]
0x1800259fb  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180025a00  lea     rax, dword_18007D864
0x180025a07  mov     [rsp+48h+phkResult], rax; lpData
0x180025a0c  lea     r9, [rsp+48h+Type]; lpType
0x180025a11  xor     r8d, r8d; lpReserved
0x180025a14  lea     rdx, aThreadmax; "ThreadMax"
0x180025a1b  mov     rcx, [rsp+48h+hKey]; hKey
0x180025a20  call    cs:__imp_RegQueryValueExA
0x180025a26  neg     eax
0x180025a28  sbb     ecx, ecx
0x180025a2a  not     ecx
0x180025a2c  and     ecx, 1000h
0x180025a32  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x180025a38  btr     eax, 0Ch
0x180025a3c  or      eax, ecx
0x180025a3e  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x180025a44  mov     [rsp+48h+cbData], edi
0x180025a48  lea     rax, [rsp+48h+cbData]
0x180025a4d  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180025a52  lea     rax, dword_18007D868
0x180025a59  mov     [rsp+48h+phkResult], rax; lpData
0x180025a5e  lea     r9, [rsp+48h+Type]; lpType
0x180025a63  xor     r8d, r8d; lpReserved
0x180025a66  lea     rdx, aDisablecomplus; "DisableComPlusCpuMetric"
0x180025a6d  mov     rcx, [rsp+48h+hKey]; hKey
0x180025a72  call    cs:__imp_RegQueryValueExA
0x180025a78  neg     eax
0x180025a7a  sbb     ecx, ecx
0x180025a7c  not     ecx
0x180025a7e  and     ecx, 2000h
0x180025a84  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x180025a8a  btr     eax, 0Dh
0x180025a8e  or      eax, ecx
0x180025a90  mov     cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, eax; CAspRegistryParams g_AspRegistryParams
0x180025a96  mov     [rsp+48h+cbData], edi
0x180025a9a  lea     rax, [rsp+48h+cbData]
0x180025a9f  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180025aa4  lea     rax, dword_18007D86C
  ... truncated ...
```
