# PimIMService::OnBoot(void)

- ea: `0x180008720`
- end: `0x1800088a0`
- name: `?OnBoot@PimIMService@@QEAAJXZ`
- size: `384`
- prototype: `__int64 __fastcall(PimIMService *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180006070`

## callees

- `0x180002da8`
- `0x180003edc`
- `0x1800067c0`
- `0x1800082c4`
- `0x180008720`
- `0x18000a9bc`
- `0x18000c5b8`
- `0x18000c800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000887a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000888d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000887a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000888d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800087d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800087d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800087a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800087a6`

## string_xrefs

- `0x18000883a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000885e`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::OnBoot(PimIMService *this, __int64 a2)
{
  HKEY *phkResult; // rax
  void *v4; // rax
  int updated; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int inited; // eax
  unsigned int v9; // ebx
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+20h] BYREF
  DWORD Type; // [rsp+88h] [rbp+28h] BYREF

  Data = 0;
  hKey = 0;
  cbData = 4;
  Type = 4;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, a2, "OnBoot work starting");
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Poom\\Indexing", 0, 0, 0, 0xF003Fu, 0, phkResult, 0)
    && !RegQueryValueExW(hKey, L"BatchSize", 0, &Type, (LPBYTE)&Data, &cbData)
    && Data >= 0xA )
  {
    g_dwBatchSize = Data;
  }
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
  {
    v4 = _t_address();
    EtwTraceMessage(&ETWMESSAGE, v4, &g_dwBatchSize, 4, 0, -1);
  }
  updated = PimIMService::UpdateContactsSettingsForHungarian(this);
  if ( updated < 0 )
    Log_HREvent(
      (unsigned int)updated,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      405);
  inited = PimIMService::InitComponents(this, v6, v7);
  v9 = inited;
  if ( inited >= 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    Log_HREvent(
      (unsigned int)inited,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      407);
    if ( hKey )
      RegCloseKey(hKey);
    return v9;
  }
}

```

## disassembly

```asm
0x180008720  mov     [rsp-8+arg_0], rbx
0x180008725  push    rbp
0x180008726  mov     rbp, rsp
0x180008729  sub     rsp, 60h
0x18000872d  cmp     byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 0
0x180008734  mov     rbx, rcx
0x180008737  mov     [rbp+Data], 0
0x18000873e  mov     [rbp+hKey], 0
0x180008746  mov     [rbp+cbData], 4
0x18000874d  mov     [rbp+Type], 4
0x180008754  jge     short loc_180008762
0x180008756  lea     r8, aOnbootWorkStar; "OnBoot work starting"
0x18000875d  call    McTemplateU0s_EventWriteTransfer
0x180008762  lea     rcx, [rbp+hKey]
0x180008766  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18000876b  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180008774  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x18000877b  mov     [rsp+60h+phkResult], rax; phkResult
0x180008780  xor     r9d, r9d; lpClass
0x180008783  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000878c  xor     r8d, r8d; Reserved
0x18000878f  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180008797  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000879e  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1800087a6  call    cs:__imp_RegCreateKeyExW
0x1800087ac  test    eax, eax
0x1800087ae  jnz     short loc_1800087EC
0x1800087b0  mov     rcx, [rbp+hKey]; hKey
0x1800087b4  lea     rax, [rbp+cbData]
0x1800087b8  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x1800087bd  lea     r9, [rbp+Type]; lpType
0x1800087c1  lea     rax, [rbp+Data]
0x1800087c5  xor     r8d, r8d; lpReserved
0x1800087c8  lea     rdx, aBatchsize; "BatchSize"
0x1800087cf  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800087d4  call    cs:__imp_RegQueryValueExW
0x1800087da  test    eax, eax
0x1800087dc  jnz     short loc_1800087EC
0x1800087de  mov     eax, [rbp+Data]
0x1800087e1  cmp     eax, 0Ah
0x1800087e4  jb      short loc_1800087EC
0x1800087e6  mov     cs:?g_dwBatchSize@@3KA, eax; ulong g_dwBatchSize
0x1800087ec  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x1800087f3  jz      short loc_180008828
0x1800087f5  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x1800087fa  mov     rdx, rax; void *
0x1800087fd  mov     qword ptr [rsp+60h+samDesired], 0FFFFFFFFFFFFFFFFh
0x180008806  mov     r9d, 4
0x18000880c  mov     qword ptr [rsp+60h+dwOptions], 0
0x180008815  lea     r8, ?g_dwBatchSize@@3KA; ulong g_dwBatchSize
0x18000881c  lea     rcx, _ETWMESSAGE; EventDescriptor
0x180008823  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x180008828  mov     rcx, rbx; this
0x18000882b  call    ?UpdateContactsSettingsForHungarian@PimIMService@@QEAAJXZ; PimIMService::UpdateContactsSettingsForHungarian(void)
0x180008830  test    eax, eax
0x180008832  jns     short loc_18000884A
0x180008834  mov     r9d, 195h
0x18000883a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008841  xor     edx, edx
0x180008843  mov     ecx, eax
0x180008845  call    Log_HREvent
0x18000884a  mov     rcx, rbx; this
0x18000884d  call    ?InitComponents@PimIMService@@QEAAJXZ; PimIMService::InitComponents(void)
0x180008852  mov     ebx, eax
0x180008854  test    eax, eax
0x180008856  jns     short loc_180008884
0x180008858  mov     r9d, 197h
0x18000885e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008865  mov     edx, 1
0x18000886a  mov     ecx, eax
0x18000886c  call    Log_HREvent
0x180008871  mov     rcx, [rbp+hKey]; hKey
0x180008875  test    rcx, rcx
0x180008878  jz      short loc_180008880
0x18000887a  call    cs:__imp_RegCloseKey
0x180008880  mov     eax, ebx
0x180008882  jmp     short loc_180008895
0x180008884  mov     rcx, [rbp+hKey]; hKey
0x180008888  test    rcx, rcx
0x18000888b  jz      short loc_180008893
0x18000888d  call    cs:__imp_RegCloseKey
0x180008893  xor     eax, eax
0x180008895  mov     rbx, [rsp+60h+arg_0]
0x18000889a  add     rsp, 60h
0x18000889e  pop     rbp
0x18000889f  retn
```
