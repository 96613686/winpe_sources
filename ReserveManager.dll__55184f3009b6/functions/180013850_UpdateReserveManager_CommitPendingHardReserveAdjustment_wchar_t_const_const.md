# UpdateReserveManager::CommitPendingHardReserveAdjustment(wchar_t const * const)

- ea: `0x180013850`
- end: `0x180013c36`
- name: `?CommitPendingHardReserveAdjustment@UpdateReserveManager@@UEAAJQEB_W@Z`
- size: `998`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this, const wchar_t *const)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x18001224c`
- `0x180013850`
- `0x180013c3c`
- `0x180015104`
- `0x180015d74`
- `0x180015f24`
- `0x18001a8f0`
- `0x18001d758`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800138ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001392d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013963`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013a46`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013aad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013b60`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013bb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013c00`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800138ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001392d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013963`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013a46`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013aad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013b60`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013bb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013c00`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800139b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800139b9`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180013ae3`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180013ae3`

## string_xrefs

- `0x1800139d7`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180013aef`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800139e3`: `UpdateReserveManager::CommitPendingHardReserveAdjustment`
- `0x180013afb`: `UpdateReserveManager::CommitPendingHardReserveAdjustment`
- `0x180013b10`: `::RegSetKeyValueW(m_SoftwareKey, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"HardReserveAdjustment", ( 11ul ), &NewHardReserveAdjustment, sizeof(NewHardReserveAdjustment))`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::CommitPendingHardReserveAdjustment(
        UpdateReserveManager *this,
        const wchar_t *const a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 result; // rax
  const wchar_t *v6; // rdx
  int v7; // ebx
  const char *v8; // r9
  int ValueW; // ebx
  const wchar_t *v10; // rdx
  int v11; // ebx
  int v12; // ebx
  const wchar_t *v13; // rdx
  int v14; // ebx
  bool v15; // [rsp+40h] [rbp-98h] BYREF
  HANDLE *v16; // [rsp+48h] [rbp-90h] BYREF
  char v17; // [rsp+50h] [rbp-88h]
  const char *v18; // [rsp+58h] [rbp-80h] BYREF
  const char *v19; // [rsp+60h] [rbp-78h]
  __int64 v20; // [rsp+68h] [rbp-70h]
  const char *v21; // [rsp+70h] [rbp-68h]
  __int64 v22; // [rsp+78h] [rbp-60h]
  DWORD pcbData; // [rsp+80h] [rbp-58h] BYREF
  wchar_t *v24[3]; // [rsp+88h] [rbp-50h] BYREF
  unsigned __int64 v25; // [rsp+A0h] [rbp-38h]
  unsigned __int64 Data; // [rsp+A8h] [rbp-30h] BYREF
  unsigned __int64 pvData; // [rsp+B0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v22 = -2;
  v16 = (HANDLE *)((char *)this + 1192);
  v17 = 0;
  v3 = AutoMutexLocker::Lock((AutoMutexLocker *)&v16, (unsigned int)a2);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( v17 )
    {
      if ( *v16 )
        ReleaseMutex(*v16);
    }
    return v4;
  }
  try
  {
    UpdateReserveManager::GetAdjustmentKeyPath();
    v15 = 0;
    v6 = (const wchar_t *)v24;
    if ( v25 > 7 )
      v6 = v24[0];
    v7 = DoesRegKeyExist(*((HKEY *)this + 13), v6, &v15);
    if ( v7 >= 0 )
    {
      if ( v15 )
      {
        pvData = 0;
        pcbData = 8;
        ValueW = RegGetValueW(
                   *((HKEY *)this + 13),
                   L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                   L"HardReserveAdjustment",
                   0x40u,
                   0,
                   &pvData,
                   &pcbData);
        if ( ValueW == 2 )
        {
          pvData = 0;
        }
        else if ( ValueW )
        {
          v18 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v19 = "UpdateReserveManager::CommitPendingHardReserveAdjustment";
          v20 = 1042;
          v21 = "RetValue";
          if ( ValueW > 0 )
            ValueW = (unsigned __int16)ValueW | 0x80070000;
          RtlReportErrorOrigination(&v18, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
          std::wstring::~wstring((char **)v24);
          if ( v17 && *v16 )
            ReleaseMutex(*v16);
          return (unsigned int)ValueW;
        }
        Data = 0;
        v10 = (const wchar_t *)v24;
        if ( v25 > 7 )
          v10 = v24[0];
        v11 = UpdateReserveManager::ComputeNewHardReserveAdjustment(this, v10, &Data);
        if ( v11 >= 0 )
        {
          v12 = RegSetKeyValueW(
                  *((HKEY *)this + 13),
                  L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                  L"HardReserveAdjustment",
                  0xBu,
                  &Data,
                  8u);
          if ( v12 )
          {
            v18 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v19 = "UpdateReserveManager::CommitPendingHardReserveAdjustment";
            v20 = 1057;
            v21 = "::RegSetKeyValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\", L\"Har"
                  "dReserveAdjustment\", ( 11ul ), &NewHardReserveAdjustment, sizeof(NewHardReserveAdjustment))";
            if ( v12 > 0 )
              v12 = (unsigned __int16)v12 | 0x80070000;
            RtlReportErrorOrigination(&v18, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v12);
            std::wstring::~wstring((char **)v24);
            if ( v17 && *v16 )
              ReleaseMutex(*v16);
            result = (unsigned int)v12;
          }
          else
          {
            v13 = (const wchar_t *)v24;
            if ( v25 > 7 )
              v13 = v24[0];
            v14 = UpdateReserveManager::FinishHardReserveAdjustment(this, v13);
            if ( v14 >= 0 )
            {
              CUpdateReserveManagerDiagnostics::ReportCommitPendingHardReserveAdjustment(
                (const char *)this + 1200,
                pvData,
                Data);
              std::wstring::~wstring((char **)v24);
              if ( v17 && *v16 )
                ReleaseMutex(*v16);
              result = 0;
            }
            else
            {
              std::wstring::~wstring((char **)v24);
              if ( v17 && *v16 )
                ReleaseMutex(*v16);
              result = (unsigned int)v14;
            }
          }
        }
        else
        {
          std::wstring::~wstring((char **)v24);
          if ( v17 && *v16 )
            ReleaseMutex(*v16);
          result = (unsigned int)v11;
        }
      }
      else
      {
        std::wstring::~wstring((char **)v24);
        if ( v17 && *v16 )
          ReleaseMutex(*v16);
        result = 0;
      }
    }
    else
    {
      std::wstring::~wstring((char **)v24);
      if ( v17 && *v16 )
        ReleaseMutex(*v16);
      result = (unsigned int)v7;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x42B,
                           (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180013850  mov     rax, rsp
0x180013853  push    rsi
0x180013854  push    rdi
0x180013855  push    r14
0x180013857  sub     rsp, 0C0h
0x18001385e  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x180013866  mov     [rax+18h], rbx
0x18001386a  mov     rax, cs:__security_cookie
0x180013871  xor     rax, rsp
0x180013874  mov     [rsp+0D8h+var_20], rax
0x18001387c  mov     rsi, rdx
0x18001387f  mov     rdi, rcx
0x180013882  lea     rax, [rcx+4A8h]
0x180013889  mov     [rsp+0D8h+var_90], rax
0x18001388e  xor     r14d, r14d
0x180013891  mov     [rsp+0D8h+var_88], r14b
0x180013896  lea     rcx, [rsp+0D8h+var_90]; this
0x18001389b  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x1800138a0  mov     ebx, eax
0x1800138a2  test    eax, eax
0x1800138a4  jns     short loc_1800138C7
0x1800138a6  cmp     [rsp+0D8h+var_88], r14b
0x1800138ab  jz      short loc_1800138C0
0x1800138ad  mov     rcx, [rsp+0D8h+var_90]
0x1800138b2  mov     rcx, [rcx]; hMutex
0x1800138b5  test    rcx, rcx
0x1800138b8  jz      short loc_1800138C0
0x1800138ba  call    cs:__imp_ReleaseMutex
0x1800138c0  mov     eax, ebx
0x1800138c2  jmp     loc_180013C11
0x1800138c7  mov     r8, rsi
0x1800138ca  lea     rdx, [rsp+0D8h+var_50]
0x1800138d2  call    ?GetAdjustmentKeyPath@UpdateReserveManager@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; UpdateReserveManager::GetAdjustmentKeyPath(wchar_t const * const)
0x1800138d7  nop
0x1800138d8  mov     [rsp+0D8h+var_98], r14b
0x1800138dd  lea     rdx, [rsp+0D8h+var_50]
0x1800138e5  cmp     [rsp+0D8h+var_38], 7
0x1800138ee  cmova   rdx, [rsp+0D8h+var_50]; wchar_t *
0x1800138f7  lea     r8, [rsp+0D8h+var_98]; bool *
0x1800138fc  mov     rcx, [rdi+68h]; HKEY
0x180013900  call    ?DoesRegKeyExist@@YAJQEAUHKEY__@@QEB_WPEA_N@Z; DoesRegKeyExist(HKEY__ * const,wchar_t const * const,bool *)
0x180013905  mov     ebx, eax
0x180013907  test    eax, eax
0x180013909  jns     short loc_18001393A
0x18001390b  lea     rcx, [rsp+0D8h+var_50]
0x180013913  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013918  nop
0x180013919  cmp     [rsp+0D8h+var_88], r14b
0x18001391e  jz      short loc_180013933
0x180013920  mov     rcx, [rsp+0D8h+var_90]
0x180013925  mov     rcx, [rcx]; hMutex
0x180013928  test    rcx, rcx
0x18001392b  jz      short loc_180013933
0x18001392d  call    cs:__imp_ReleaseMutex
0x180013933  mov     eax, ebx
0x180013935  jmp     loc_180013C11
0x18001393a  cmp     [rsp+0D8h+var_98], r14b
0x18001393f  jnz     short loc_180013970
0x180013941  lea     rcx, [rsp+0D8h+var_50]
0x180013949  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001394e  nop
0x18001394f  cmp     [rsp+0D8h+var_88], r14b
0x180013954  jz      short loc_180013969
0x180013956  mov     rax, [rsp+0D8h+var_90]
0x18001395b  mov     rcx, [rax]; hMutex
0x18001395e  test    rcx, rcx
0x180013961  jz      short loc_180013969
0x180013963  call    cs:__imp_ReleaseMutex
0x180013969  xor     eax, eax
0x18001396b  jmp     loc_180013C11
0x180013970  mov     [rsp+0D8h+var_28], r14
0x180013978  mov     esi, 8
0x18001397d  mov     [rsp+0D8h+var_58], esi
0x180013984  lea     rax, [rsp+0D8h+var_58]
0x18001398c  mov     [rsp+0D8h+pcbData], rax; pcbData
0x180013991  lea     rax, [rsp+0D8h+var_28]
0x180013999  mov     [rsp+0D8h+pvData], rax; pvData
0x18001399e  mov     [rsp+0D8h+pdwType], r14; pdwType
0x1800139a3  lea     r9d, [rsi+38h]; dwFlags
0x1800139a7  lea     r8, aHardreserveadj; "HardReserveAdjustment"
0x1800139ae  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x1800139b5  mov     rcx, [rdi+68h]; hkey
0x1800139b9  call    cs:__imp_RegGetValueW
0x1800139bf  mov     ebx, eax
0x1800139c1  cmp     eax, 2
0x1800139c4  jnz     short loc_1800139D3
0x1800139c6  mov     [rsp+0D8h+var_28], r14
0x1800139ce  jmp     loc_180013A53
0x1800139d3  test    ebx, ebx
0x1800139d5  jz      short loc_180013A53
0x1800139d7  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800139de  mov     [rsp+0D8h+var_80], rax
0x1800139e3  lea     rax, aUpdatereservem_8; "UpdateReserveManager::CommitPendingHard"...
0x1800139ea  mov     [rsp+0D8h+var_78], rax
0x1800139ef  mov     [rsp+0D8h+var_70], 412h
0x1800139f8  lea     rax, aRetvalue; "RetValue"
0x1800139ff  mov     [rsp+0D8h+var_68], rax
0x180013a04  jle     short loc_180013A0F
0x180013a06  movzx   ebx, bx
0x180013a09  or      ebx, 80070000h
0x180013a0f  mov     r8d, ebx
0x180013a12  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180013a19  lea     rcx, [rsp+0D8h+var_80]
0x180013a1e  call    RtlReportErrorOrigination
0x180013a23  nop
0x180013a24  lea     rcx, [rsp+0D8h+var_50]
0x180013a2c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013a31  nop
0x180013a32  cmp     [rsp+0D8h+var_88], r14b
0x180013a37  jz      short loc_180013A4C
0x180013a39  mov     rcx, [rsp+0D8h+var_90]
0x180013a3e  mov     rcx, [rcx]; hMutex
0x180013a41  test    rcx, rcx
0x180013a44  jz      short loc_180013A4C
0x180013a46  call    cs:__imp_ReleaseMutex
0x180013a4c  mov     eax, ebx
0x180013a4e  jmp     loc_180013C11
0x180013a53  mov     [rsp+0D8h+Data], r14
0x180013a5b  lea     rdx, [rsp+0D8h+var_50]
0x180013a63  cmp     [rsp+0D8h+var_38], 7
0x180013a6c  cmova   rdx, [rsp+0D8h+var_50]; wchar_t *
0x180013a75  lea     r8, [rsp+0D8h+Data]; unsigned __int64 *
0x180013a7d  mov     rcx, rdi; this
0x180013a80  call    ?ComputeNewHardReserveAdjustment@UpdateReserveManager@@AEAAJQEB_WPEA_K@Z; UpdateReserveManager::ComputeNewHardReserveAdjustment(wchar_t const * const,unsigned __int64 *)
0x180013a85  mov     ebx, eax
0x180013a87  test    eax, eax
0x180013a89  jns     short loc_180013ABA
0x180013a8b  lea     rcx, [rsp+0D8h+var_50]
0x180013a93  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013a98  nop
0x180013a99  cmp     [rsp+0D8h+var_88], r14b
0x180013a9e  jz      short loc_180013AB3
0x180013aa0  mov     rcx, [rsp+0D8h+var_90]
0x180013aa5  mov     rcx, [rcx]; hMutex
0x180013aa8  test    rcx, rcx
0x180013aab  jz      short loc_180013AB3
0x180013aad  call    cs:__imp_ReleaseMutex
0x180013ab3  mov     eax, ebx
0x180013ab5  jmp     loc_180013C11
0x180013aba  mov     dword ptr [rsp+0D8h+pvData], esi; cbData
0x180013abe  lea     rax, [rsp+0D8h+Data]
0x180013ac6  mov     [rsp+0D8h+pdwType], rax; lpData
0x180013acb  mov     r9d, 0Bh; dwType
0x180013ad1  lea     r8, aHardreserveadj; "HardReserveAdjustment"
0x180013ad8  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180013adf  mov     rcx, [rdi+68h]; hKey
0x180013ae3  call    cs:__imp_RegSetKeyValueW
0x180013ae9  mov     ebx, eax
0x180013aeb  test    eax, eax
0x180013aed  jz      short loc_180013B6D
0x180013aef  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180013af6  mov     [rsp+0D8h+var_80], rax
0x180013afb  lea     rax, aUpdatereservem_8; "UpdateReserveManager::CommitPendingHard"...
0x180013b02  mov     [rsp+0D8h+var_78], rax
0x180013b07  mov     [rsp+0D8h+var_70], 421h
0x180013b10  lea     rax, aRegsetkeyvalue_8; "::RegSetKeyValueW(m_SoftwareKey, L\"Mic"...
0x180013b17  mov     [rsp+0D8h+var_68], rax
0x180013b1c  test    ebx, ebx
0x180013b1e  jle     short loc_180013B29
0x180013b20  movzx   ebx, bx
0x180013b23  or      ebx, 80070000h
0x180013b29  mov     r8d, ebx
0x180013b2c  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180013b33  lea     rcx, [rsp+0D8h+var_80]
0x180013b38  call    RtlReportErrorOrigination
0x180013b3d  nop
0x180013b3e  lea     rcx, [rsp+0D8h+var_50]
0x180013b46  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013b4b  nop
0x180013b4c  cmp     [rsp+0D8h+var_88], r14b
0x180013b51  jz      short loc_180013B66
0x180013b53  mov     rcx, [rsp+0D8h+var_90]
0x180013b58  mov     rcx, [rcx]; hMutex
0x180013b5b  test    rcx, rcx
0x180013b5e  jz      short loc_180013B66
0x180013b60  call    cs:__imp_ReleaseMutex
0x180013b66  mov     eax, ebx
0x180013b68  jmp     loc_180013C11
0x180013b6d  lea     rdx, [rsp+0D8h+var_50]
0x180013b75  cmp     [rsp+0D8h+var_38], 7
0x180013b7e  cmova   rdx, [rsp+0D8h+var_50]; wchar_t *
0x180013b87  mov     rcx, rdi; this
0x180013b8a  call    ?FinishHardReserveAdjustment@UpdateReserveManager@@AEAAJQEB_W@Z; UpdateReserveManager::FinishHardReserveAdjustment(wchar_t const * const)
0x180013b8f  mov     ebx, eax
0x180013b91  test    eax, eax
0x180013b93  jns     short loc_180013BC1
0x180013b95  lea     rcx, [rsp+0D8h+var_50]
0x180013b9d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013ba2  nop
0x180013ba3  cmp     [rsp+0D8h+var_88], r14b
0x180013ba8  jz      short loc_180013BBD
0x180013baa  mov     rcx, [rsp+0D8h+var_90]
0x180013baf  mov     rcx, [rcx]; hMutex
0x180013bb2  test    rcx, rcx
0x180013bb5  jz      short loc_180013BBD
0x180013bb7  call    cs:__imp_ReleaseMutex
0x180013bbd  mov     eax, ebx
0x180013bbf  jmp     short loc_180013C11
0x180013bc1  lea     rcx, [rdi+4B0h]; char *
0x180013bc8  mov     r8, [rsp+0D8h+Data]; unsigned __int64
0x180013bd0  mov     rdx, [rsp+0D8h+var_28]; unsigned __int64
0x180013bd8  call    ?ReportCommitPendingHardReserveAdjustment@CUpdateReserveManagerDiagnostics@@SAXPEBD_K1@Z; CUpdateReserveManagerDiagnostics::ReportCommitPendingHardReserveAdjustment(char const *,unsigned __int64,unsigned __int64)
0x180013bdd  nop
0x180013bde  lea     rcx, [rsp+0D8h+var_50]
0x180013be6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013beb  nop
0x180013bec  cmp     [rsp+0D8h+var_88], r14b
0x180013bf1  jz      short loc_180013C06
0x180013bf3  mov     rax, [rsp+0D8h+var_90]
0x180013bf8  mov     rcx, [rax]; hMutex
0x180013bfb  test    rcx, rcx
0x180013bfe  jz      short loc_180013C06
0x180013c00  call    cs:__imp_ReleaseMutex
0x180013c06  xor     eax, eax
0x180013c08  jmp     short loc_180013C11
0x180013c0a  mov     eax, [rsp+0D8h+var_58]
0x180013c11  mov     rcx, [rsp+0D8h+var_20]
0x180013c19  xor     rcx, rsp; StackCookie
0x180013c1c  call    __security_check_cookie
0x180013c21  mov     rbx, [rsp+0D8h+arg_10]
0x180013c29  add     rsp, 0C0h
0x180013c30  pop     r14
0x180013c32  pop     rdi
0x180013c33  pop     rsi
0x180013c34  retn
```
