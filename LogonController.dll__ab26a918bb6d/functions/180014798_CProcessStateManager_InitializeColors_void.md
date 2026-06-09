# CProcessStateManager::_InitializeColors(void)

- ea: `0x180014798`
- end: `0x180014a2d`
- name: `?_InitializeColors@CProcessStateManager@@AEAAXXZ`
- size: `661`
- prototype: `void __fastcall(CProcessStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180061420`

## callees

- `0x18000df10`
- `0x1800128e8`
- `0x1800140c8`
- `0x180014798`
- `0x180014a34`
- `0x180014b74`
- `0x180014ce4`
- `0x180014d24`
- `0x180014f54`
- `0x180014f9c`
- `0x1800170c4`
- `0x18006f0d8`
- `0x18009b0b4`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180014958`
- `KERNEL32!LocalFree` at `0x180014958`
- `KERNEL32!GetLastError` at `0x1800149cc`
- `KERNEL32!GetLastError` at `0x1800149cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014904`
- `GDI32!GdiWaitForTextReady` at `0x1800147b8`
- `GDI32!GdiWaitForTextReady` at `0x1800147b8`
- `UxTheme!__imp_InitializeImmersiveColorSetSharedMemory` at `0x1800147b2`
- `UxTheme!__imp_InitializeImmersiveColorSetSharedMemory` at `0x1800147b2`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800147e4`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180014936`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180014a22`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800147e4`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180014936`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180014a22`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180014911`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180014911`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CProcessStateManager::_InitializeColors(CProcessStateManager *this)
{
  char v2; // si
  HSTRING *v3; // r13
  HSTRING v4; // r15
  char IsHighContrast; // r12
  CUserColorData **v6; // r14
  CUserColorData *v7; // rax
  CUserColorData *v8; // rdi
  __int64 v9; // rdx
  CUserColorData **v10; // rdx
  CUserColorData *v11; // rcx
  HSTRING v12; // rcx
  const WCHAR *StringRawBuffer; // rax
  __int64 v14; // rdx
  DWORD LastError; // eax
  __int64 v16; // rcx
  int v17; // eax
  _QWORD pvParam[2]; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v19[2]; // [rsp+40h] [rbp-10h] BYREF
  CUserColorData *v20; // [rsp+90h] [rbp+40h] BYREF
  PSID Sid; // [rsp+98h] [rbp+48h] BYREF

  InitializeImmersiveColorSetSharedMemory();
  if ( !(unsigned int)GdiWaitForTextReady() )
  {
    LastError = GetLastError();
    MicrosoftTelemetryAssertTriggeredArgs(v16, LastError);
  }
  v2 = 0;
  pvParam[0] = 16;
  pvParam[1] = 0;
  if ( SystemParametersInfoW(0x42u, 0x10u, pvParam, 0) )
    v2 = BYTE4(pvParam[0]) & 1;
  v3 = (HSTRING *)((char *)this + 424);
  v4 = (HSTRING)*((_QWORD *)this + 53);
  if ( v4 )
  {
    IsHighContrast = 0;
    v6 = (CUserColorData **)((char *)this + 208);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 208);
    *((_QWORD *)this + 26) = 0;
    v7 = (CUserColorData *)operator new(0xB0u, (const struct std::nothrow_t *)std::nothrow);
    if ( v7 )
    {
      v8 = CUserColorData::CUserColorData(v7);
      v20 = v8;
      Sid = 0;
      if ( (int)CUserColorData::RuntimeClassInitialize(v8, v4) < 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v20);
        Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&Sid);
      }
      else
      {
        if ( v8 )
          (*(void (__fastcall **)(CUserColorData *))(*(_QWORD *)v8 + 8LL))(v8);
        *v6 = v8;
        if ( v8 )
          (*(void (__fastcall **)(CUserColorData *))(*(_QWORD *)v8 + 16LL))(v8);
        v9 = *((_QWORD *)this + 23);
        if ( v9 != *((_QWORD *)this + 25)
          || (int)CTSimpleArray<Microsoft::WRL::ComPtr<CUserColorData>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<CUserColorData>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CUserColorData>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CUserColorData>>>::_EnsureCapacity(
                    (char *)this + 176,
                    v9 + 1) >= 0 )
        {
          v10 = (CUserColorData **)(*((_QWORD *)this + 22) + 8 * (*((_QWORD *)this + 23))++);
          if ( v10 )
          {
            v11 = *v6;
            *v10 = *v6;
            if ( v11 )
              (*(void (__fastcall **)(CUserColorData *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
        IsHighContrast = CUserColorData::IsHighContrast(*v6);
      }
    }
    if ( v2 == IsHighContrast )
    {
      if ( !v2 )
      {
LABEL_19:
        v12 = *v3;
        if ( *v3 )
        {
          Sid = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(v12, 0);
          if ( ConvertStringSidToSidW(StringRawBuffer, &Sid) )
          {
            v19[0] = 16;
            v19[1] = 0;
            SystemParametersInfoW(0x42u, 0x10u, v19, 0);
            _WriteSystemDataRegistryDWORDForUser(Sid, v14, L"HighContrastEnabledNew");
            LocalFree(Sid);
          }
        }
        goto LABEL_22;
      }
      v17 = HIDWORD(pvParam[0]);
    }
    else
    {
      v17 = HIDWORD(pvParam[0]) ^ 1;
    }
    HIDWORD(pvParam[0]) = v17 | 0x1000;
    SystemParametersInfoW(0x43u, 0x10u, pvParam, 0);
    goto LABEL_19;
  }
LABEL_22:
  CProcessStateManager::_SetPerUserColors(this);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 240);
  if ( (int)Microsoft::WRL::Details::MakeAndInitialize<CUserSettingChangeMonitor,CUserSettingChangeMonitor,>((char *)this + 240) >= 0 )
    CUserSettingChangeMonitor::StartListening(
      *((CUserSettingChangeMonitor **)this + 30),
      (struct IUserSettingChangeCallback *)(((unsigned __int64)this + 40) & -(__int64)(this != 0)),
      *v3);
}

```

## disassembly

```asm
0x180014798  mov     [rsp-38h+arg_10], rbx
0x18001479d  push    rbp
0x18001479e  push    rsi
0x18001479f  push    rdi
0x1800147a0  push    r12
0x1800147a2  push    r13
0x1800147a4  push    r14
0x1800147a6  push    r15
0x1800147a8  mov     rbp, rsp
0x1800147ab  sub     rsp, 50h
0x1800147af  mov     rbx, rcx
0x1800147b2  call    cs:__imp_InitializeImmersiveColorSetSharedMemory
0x1800147b8  call    cs:__imp_GdiWaitForTextReady
0x1800147be  test    eax, eax
0x1800147c0  jz      loc_1800149CC
0x1800147c6  xor     sil, sil
0x1800147c9  mov     [rbp+pvParam], 10h
0x1800147d1  xor     eax, eax
0x1800147d3  mov     [rbp+var_18], rax
0x1800147d7  xor     r9d, r9d; fWinIni
0x1800147da  lea     r8, [rbp+pvParam]; pvParam
0x1800147de  lea     edx, [rax+10h]; uiParam
0x1800147e1  lea     ecx, [rax+42h]; uiAction
0x1800147e4  call    cs:__imp_SystemParametersInfoW
0x1800147ea  test    eax, eax
0x1800147ec  jnz     loc_1800149DE
0x1800147f2  lea     r13, [rbx+1A8h]
0x1800147f9  mov     r15, [r13+0]
0x1800147fd  test    r15, r15
0x180014800  jz      loc_18001495E
0x180014806  xor     r12b, r12b
0x180014809  lea     r14, [rbx+0D0h]
0x180014810  mov     rcx, r14
0x180014813  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180014818  mov     qword ptr [r14], 0
0x18001481f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014826  mov     ecx, 0B0h; unsigned __int64
0x18001482b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014830  test    rax, rax
0x180014833  jz      loc_1800148DF
0x180014839  mov     rcx, rax; this
0x18001483c  call    ??0CUserColorData@@QEAA@XZ; CUserColorData::CUserColorData(void)
0x180014841  mov     rdi, rax
0x180014844  mov     [rbp+arg_0], rax
0x180014848  mov     [rbp+Sid], 0
0x180014850  mov     rdx, r15; HSTRING
0x180014853  mov     rcx, rax; this
0x180014856  call    ?RuntimeClassInitialize@CUserColorData@@QEAAJPEAUHSTRING__@@@Z; CUserColorData::RuntimeClassInitialize(HSTRING__ *)
0x18001485b  test    eax, eax
0x18001485d  js      loc_1800149EB
0x180014863  test    rdi, rdi
0x180014866  jz      short loc_180014878
0x180014868  mov     rax, [rdi]
0x18001486b  mov     rcx, rdi
0x18001486e  mov     rax, [rax+8]
0x180014872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014877  nop
0x180014878  mov     [r14], rdi
0x18001487b  test    rdi, rdi
0x18001487e  jz      short loc_180014890
0x180014880  mov     rax, [rdi]
0x180014883  mov     rcx, rdi
0x180014886  mov     rax, [rax+10h]
0x18001488a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001488f  nop
0x180014890  lea     rdi, [rbx+0B0h]
0x180014897  mov     rdx, [rdi+8]
0x18001489b  cmp     rdx, [rdi+18h]
0x18001489f  jz      loc_1800149B4
0x1800148a5  inc     qword ptr [rdi+8]
0x1800148a9  mov     rdx, [rdi+8]
0x1800148ad  mov     rax, [rdi]
0x1800148b0  dec     rdx
0x1800148b3  lea     rdx, [rax+rdx*8]
0x1800148b7  test    rdx, rdx
0x1800148ba  jz      short loc_1800148D4
0x1800148bc  mov     rcx, [r14]
0x1800148bf  mov     [rdx], rcx
0x1800148c2  test    rcx, rcx
0x1800148c5  jz      short loc_1800148D4
0x1800148c7  mov     rax, [rcx]
0x1800148ca  mov     rax, [rax+8]
0x1800148ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148d3  nop
0x1800148d4  mov     rcx, [r14]; this
0x1800148d7  call    ?IsHighContrast@CUserColorData@@QEAA_NXZ; CUserColorData::IsHighContrast(void)
0x1800148dc  mov     r12b, al
0x1800148df  cmp     sil, r12b
0x1800148e2  jnz     loc_180014A02
0x1800148e8  test    sil, sil
0x1800148eb  jnz     loc_180014A0A
0x1800148f1  mov     rcx, [r13+0]; string
0x1800148f5  test    rcx, rcx
0x1800148f8  jz      short loc_18001495E
0x1800148fa  mov     [rbp+Sid], 0
0x180014902  xor     edx, edx; length
0x180014904  call    cs:__imp_WindowsGetStringRawBuffer
0x18001490a  lea     rdx, [rbp+Sid]; Sid
0x18001490e  mov     rcx, rax; StringSid
0x180014911  call    cs:__imp_ConvertStringSidToSidW
0x180014917  test    eax, eax
0x180014919  jz      short loc_18001495E
0x18001491b  mov     [rbp+var_10], 10h
0x180014923  xor     eax, eax
0x180014925  mov     [rbp+var_8], rax
0x180014929  xor     r9d, r9d; fWinIni
0x18001492c  lea     r8, [rbp+var_10]; pvParam
0x180014930  lea     edx, [rax+10h]; uiParam
0x180014933  lea     ecx, [rax+42h]; uiAction
0x180014936  call    cs:__imp_SystemParametersInfoW
0x18001493c  mov     [rsp+50h+var_30], 0FFFFFFFFh
0x180014944  lea     r8, aHighcontrasten_0; "HighContrastEnabledNew"
0x18001494b  mov     rcx, [rbp+Sid]
0x18001494f  call    ?_WriteSystemDataRegistryDWORDForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@K_N@Z; _WriteSystemDataRegistryDWORDForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ulong,bool)
0x180014954  mov     rcx, [rbp+Sid]; hMem
0x180014958  call    cs:__imp_LocalFree
0x18001495e  mov     rcx, rbx; this
0x180014961  call    ?_SetPerUserColors@CProcessStateManager@@AEAAXXZ; CProcessStateManager::_SetPerUserColors(void)
0x180014966  lea     rdi, [rbx+0F0h]
0x18001496d  mov     rcx, rdi
0x180014970  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180014975  mov     rcx, rdi
0x180014978  call    ??$MakeAndInitialize@VCUserSettingChangeMonitor@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCUserSettingChangeMonitor@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CUserSettingChangeMonitor,CUserSettingChangeMonitor,>(CUserSettingChangeMonitor * *)
0x18001497d  test    eax, eax
0x18001497f  jns     short loc_180014999
0x180014981  mov     rbx, [rsp+50h+arg_10]
0x180014989  add     rsp, 50h
0x18001498d  pop     r15
0x18001498f  pop     r14
0x180014991  pop     r13
0x180014993  pop     r12
0x180014995  pop     rdi
0x180014996  pop     rsi
0x180014997  pop     rbp
0x180014998  retn
0x180014999  lea     rax, [rbx+28h]
0x18001499d  neg     rbx
0x1800149a0  sbb     rdx, rdx
0x1800149a3  and     rdx, rax; struct IUserSettingChangeCallback *
0x1800149a6  mov     r8, [r13+0]; HSTRING
0x1800149aa  mov     rcx, [rdi]; this
0x1800149ad  call    ?StartListening@CUserSettingChangeMonitor@@QEAAXPEAUIUserSettingChangeCallback@@PEAUHSTRING__@@@Z; CUserSettingChangeMonitor::StartListening(IUserSettingChangeCallback *,HSTRING__ *)
0x1800149b2  jmp     short loc_180014981
0x1800149b4  inc     rdx
0x1800149b7  mov     rcx, rdi
0x1800149ba  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@VCUserColorData@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@VCUserColorData@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VCUserColorData@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@VCUserColorData@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<CUserColorData>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<CUserColorData>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CUserColorData>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CUserColorData>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800149bf  test    eax, eax
0x1800149c1  js      loc_1800148D4
0x1800149c7  jmp     loc_1800148A5
0x1800149cc  call    cs:__imp_GetLastError
0x1800149d2  mov     edx, eax
0x1800149d4  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800149d9  jmp     loc_1800147C6
0x1800149de  mov     sil, byte ptr [rbp+pvParam+4]
0x1800149e2  and     sil, 1
0x1800149e6  jmp     loc_1800147F2
0x1800149eb  lea     rcx, [rbp+arg_0]
0x1800149ef  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800149f4  lea     rcx, [rbp+Sid]
0x1800149f8  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x1800149fd  jmp     loc_1800148DF
0x180014a02  mov     eax, dword ptr [rbp+pvParam+4]
0x180014a05  xor     eax, 1
0x180014a08  jmp     short loc_180014A0D
0x180014a0a  mov     eax, dword ptr [rbp+pvParam+4]
0x180014a0d  bts     eax, 0Ch
0x180014a11  mov     dword ptr [rbp+pvParam+4], eax
0x180014a14  xor     r9d, r9d; fWinIni
0x180014a17  lea     r8, [rbp+pvParam]; pvParam
0x180014a1b  lea     edx, [r9+10h]; uiParam
0x180014a1f  lea     ecx, [rdx+33h]; uiAction
0x180014a22  call    cs:__imp_SystemParametersInfoW
0x180014a28  jmp     loc_1800148F1
```
