# UpdateReserveManager::RemovePendingHardReserveAdjustment(wchar_t const * const)

- ea: `0x18001d140`
- end: `0x18001d436`
- name: `?RemovePendingHardReserveAdjustment@UpdateReserveManager@@UEAAJQEB_W@Z`
- size: `758`
- prototype: `__int64 __fastcall(UpdateReserveManager *this, wchar_t *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x18001224c`
- `0x180015104`
- `0x180015d74`
- `0x180015f24`
- `0x18001a8f0`
- `0x18001a968`
- `0x18001d140`
- `0x18001e448`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d1aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d21d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d253`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d34d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d3c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d400`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d1aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d21d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d253`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d34d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d3c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d400`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d2bd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d2bd`

## string_xrefs

- `0x18001d2de`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001d2ea`: `UpdateReserveManager::RemovePendingHardReserveAdjustment`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::RemovePendingHardReserveAdjustment(UpdateReserveManager *this, wchar_t *a2)
{
  signed int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 result; // rax
  const WCHAR *v8; // rdx
  int v9; // ebx
  const char *v10; // r9
  const WCHAR *v11; // rdx
  int ValueW; // ebx
  unsigned __int64 v13; // r8
  const WCHAR *v14; // rdx
  int v15; // ebx
  bool v16; // [rsp+40h] [rbp-98h] BYREF
  HANDLE *v17; // [rsp+48h] [rbp-90h] BYREF
  char v18; // [rsp+50h] [rbp-88h]
  _QWORD v19[5]; // [rsp+58h] [rbp-80h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp-58h] BYREF
  unsigned __int64 pvData; // [rsp+88h] [rbp-50h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+90h] [rbp-48h] BYREF
  unsigned __int64 v23; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v19[4] = -2;
  v17 = (HANDLE *)((char *)this + 1192);
  v18 = 0;
  v4 = AutoMutexLocker::Lock(&v17);
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( v18 )
    {
      if ( *v17 )
        ReleaseMutex(*v17);
    }
    return v6;
  }
  try
  {
    UpdateReserveManager::GetAdjustmentKeyPath(v5, lpSubKey, a2);
    v16 = 0;
    v8 = (const WCHAR *)lpSubKey;
    if ( v23 > 7 )
      v8 = lpSubKey[0];
    v9 = DoesRegKeyExist(*((HKEY *)this + 13), v8, &v16);
    if ( v9 >= 0 )
    {
      if ( v16 )
      {
        pvData = 0;
        pcbData = 8;
        v11 = (const WCHAR *)lpSubKey;
        if ( v23 > 7 )
          v11 = lpSubKey[0];
        ValueW = RegGetValueW(*((HKEY *)this + 13), v11, L"IncreasedScratch", 0x40u, 0, &pvData, &pcbData);
        if ( ValueW == 2 )
        {
          v13 = 0;
          pvData = 0;
        }
        else
        {
          if ( ValueW )
          {
            v19[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v19[1] = "UpdateReserveManager::RemovePendingHardReserveAdjustment";
            v19[2] = 1104;
            v19[3] = "RetValue";
            if ( ValueW > 0 )
              ValueW = (unsigned __int16)ValueW | 0x80070000;
            RtlReportErrorOrigination(v19, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
            std::wstring::~wstring((char **)lpSubKey);
            if ( v18 && *v17 )
              ReleaseMutex(*v17);
            return (unsigned int)ValueW;
          }
          v13 = pvData;
        }
        if ( !*((_BYTE *)this + 1178) && v13 )
          UpdateReserveManager::ModifyUpdateScratchReserveSize((HANDLE *)this, 1, v13);
        v14 = (const WCHAR *)lpSubKey;
        if ( v23 > 7 )
          v14 = lpSubKey[0];
        v15 = UpdateReserveManager::FinishHardReserveAdjustment((HKEY *)this, v14);
        if ( v15 >= 0 )
        {
          CUpdateReserveManagerDiagnostics::ReportRemovePendingHardReserveAdjustment((const char *)this + 1200);
          std::wstring::~wstring((char **)lpSubKey);
          if ( v18 && *v17 )
            ReleaseMutex(*v17);
          result = 0;
        }
        else
        {
          std::wstring::~wstring((char **)lpSubKey);
          if ( v18 && *v17 )
            ReleaseMutex(*v17);
          result = (unsigned int)v15;
        }
      }
      else
      {
        std::wstring::~wstring((char **)lpSubKey);
        if ( v18 && *v17 )
          ReleaseMutex(*v17);
        result = 0;
      }
    }
    else
    {
      std::wstring::~wstring((char **)lpSubKey);
      if ( v18 && *v17 )
        ReleaseMutex(*v17);
      result = (unsigned int)v9;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x465,
                           (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18001d140  mov     rax, rsp
0x18001d143  push    rsi
0x18001d144  push    rdi
0x18001d145  push    r14
0x18001d147  sub     rsp, 0C0h
0x18001d14e  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x18001d156  mov     [rax+18h], rbx
0x18001d15a  mov     rax, cs:__security_cookie
0x18001d161  xor     rax, rsp
0x18001d164  mov     [rsp+0D8h+var_28], rax
0x18001d16c  mov     rsi, rdx
0x18001d16f  mov     rdi, rcx
0x18001d172  lea     rax, [rcx+4A8h]
0x18001d179  mov     [rsp+0D8h+var_90], rax
0x18001d17e  xor     r14d, r14d
0x18001d181  mov     [rsp+0D8h+var_88], r14b
0x18001d186  lea     rcx, [rsp+0D8h+var_90]; this
0x18001d18b  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x18001d190  mov     ebx, eax
0x18001d192  test    eax, eax
0x18001d194  jns     short loc_18001D1B7
0x18001d196  cmp     [rsp+0D8h+var_88], r14b
0x18001d19b  jz      short loc_18001D1B0
0x18001d19d  mov     rcx, [rsp+0D8h+var_90]
0x18001d1a2  mov     rcx, [rcx]; hMutex
0x18001d1a5  test    rcx, rcx
0x18001d1a8  jz      short loc_18001D1B0
0x18001d1aa  call    cs:__imp_ReleaseMutex
0x18001d1b0  mov     eax, ebx
0x18001d1b2  jmp     loc_18001D411
0x18001d1b7  mov     r8, rsi
0x18001d1ba  lea     rdx, [rsp+0D8h+lpSubKey]
0x18001d1c2  call    ?GetAdjustmentKeyPath@UpdateReserveManager@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; UpdateReserveManager::GetAdjustmentKeyPath(wchar_t const * const)
0x18001d1c7  nop
0x18001d1c8  mov     [rsp+0D8h+var_98], r14b
0x18001d1cd  lea     rdx, [rsp+0D8h+lpSubKey]
0x18001d1d5  cmp     [rsp+0D8h+var_30], 7
0x18001d1de  cmova   rdx, [rsp+0D8h+lpSubKey]; wchar_t *
0x18001d1e7  lea     r8, [rsp+0D8h+var_98]; bool *
0x18001d1ec  mov     rcx, [rdi+68h]; HKEY
0x18001d1f0  call    ?DoesRegKeyExist@@YAJQEAUHKEY__@@QEB_WPEA_N@Z; DoesRegKeyExist(HKEY__ * const,wchar_t const * const,bool *)
0x18001d1f5  mov     ebx, eax
0x18001d1f7  test    eax, eax
0x18001d1f9  jns     short loc_18001D22A
0x18001d1fb  lea     rcx, [rsp+0D8h+lpSubKey]
0x18001d203  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d208  nop
0x18001d209  cmp     [rsp+0D8h+var_88], r14b
0x18001d20e  jz      short loc_18001D223
0x18001d210  mov     rcx, [rsp+0D8h+var_90]
0x18001d215  mov     rcx, [rcx]; hMutex
0x18001d218  test    rcx, rcx
0x18001d21b  jz      short loc_18001D223
0x18001d21d  call    cs:__imp_ReleaseMutex
0x18001d223  mov     eax, ebx
0x18001d225  jmp     loc_18001D411
0x18001d22a  cmp     [rsp+0D8h+var_98], r14b
0x18001d22f  jnz     short loc_18001D260
0x18001d231  lea     rcx, [rsp+0D8h+lpSubKey]
0x18001d239  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d23e  nop
0x18001d23f  cmp     [rsp+0D8h+var_88], r14b
0x18001d244  jz      short loc_18001D259
0x18001d246  mov     rax, [rsp+0D8h+var_90]
0x18001d24b  mov     rcx, [rax]; hMutex
0x18001d24e  test    rcx, rcx
0x18001d251  jz      short loc_18001D259
0x18001d253  call    cs:__imp_ReleaseMutex
0x18001d259  xor     eax, eax
0x18001d25b  jmp     loc_18001D411
0x18001d260  mov     [rsp+0D8h+var_50], r14
0x18001d268  mov     [rsp+0D8h+var_58], 8
0x18001d273  lea     rdx, [rsp+0D8h+lpSubKey]
0x18001d27b  cmp     [rsp+0D8h+var_30], 7
0x18001d284  cmova   rdx, [rsp+0D8h+lpSubKey]; lpSubKey
0x18001d28d  lea     rax, [rsp+0D8h+var_58]
0x18001d295  mov     [rsp+0D8h+pcbData], rax; pcbData
0x18001d29a  lea     rax, [rsp+0D8h+var_50]
0x18001d2a2  mov     [rsp+0D8h+pvData], rax; pvData
0x18001d2a7  mov     [rsp+0D8h+pdwType], r14; pdwType
0x18001d2ac  mov     r9d, 40h ; '@'; dwFlags
0x18001d2b2  lea     r8, Value; "IncreasedScratch"
0x18001d2b9  mov     rcx, [rdi+68h]; hkey
0x18001d2bd  call    cs:__imp_RegGetValueW
0x18001d2c3  mov     ebx, eax
0x18001d2c5  cmp     eax, 2
0x18001d2c8  jnz     short loc_18001D2DA
0x18001d2ca  mov     r8, r14
0x18001d2cd  mov     [rsp+0D8h+var_50], r14
0x18001d2d5  jmp     loc_18001D362
0x18001d2da  test    ebx, ebx
0x18001d2dc  jz      short loc_18001D35A
0x18001d2de  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001d2e5  mov     [rsp+0D8h+var_80], rax
0x18001d2ea  lea     rax, aUpdatereservem_39; "UpdateReserveManager::RemovePendingHard"...
0x18001d2f1  mov     [rsp+0D8h+var_78], rax
0x18001d2f6  mov     [rsp+0D8h+var_70], 450h
0x18001d2ff  lea     rax, aRetvalue; "RetValue"
0x18001d306  mov     [rsp+0D8h+var_68], rax
0x18001d30b  jle     short loc_18001D316
0x18001d30d  movzx   ebx, bx
0x18001d310  or      ebx, 80070000h
0x18001d316  mov     r8d, ebx
0x18001d319  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001d320  lea     rcx, [rsp+0D8h+var_80]
0x18001d325  call    RtlReportErrorOrigination
0x18001d32a  nop
0x18001d32b  lea     rcx, [rsp+0D8h+lpSubKey]
0x18001d333  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d338  nop
0x18001d339  cmp     [rsp+0D8h+var_88], r14b
0x18001d33e  jz      short loc_18001D353
0x18001d340  mov     rcx, [rsp+0D8h+var_90]
0x18001d345  mov     rcx, [rcx]; hMutex
0x18001d348  test    rcx, rcx
0x18001d34b  jz      short loc_18001D353
0x18001d34d  call    cs:__imp_ReleaseMutex
0x18001d353  mov     eax, ebx
0x18001d355  jmp     loc_18001D411
0x18001d35a  mov     r8, [rsp+0D8h+var_50]
0x18001d362  cmp     [rdi+49Ah], r14b
0x18001d369  jnz     short loc_18001D37D
0x18001d36b  test    r8, r8
0x18001d36e  jz      short loc_18001D37D
0x18001d370  mov     edx, 1
0x18001d375  mov     rcx, rdi
0x18001d378  call    ?ModifyUpdateScratchReserveSize@UpdateReserveManager@@AEAAJW4UpdateSizeType@IUpdateReserveManagerCBS@@_K@Z; UpdateReserveManager::ModifyUpdateScratchReserveSize(IUpdateReserveManagerCBS::UpdateSizeType,unsigned __int64)
0x18001d37d  lea     rdx, [rsp+0D8h+lpSubKey]
0x18001d385  cmp     [rsp+0D8h+var_30], 7
0x18001d38e  cmova   rdx, [rsp+0D8h+lpSubKey]; wchar_t *
0x18001d397  mov     rcx, rdi; this
0x18001d39a  call    ?FinishHardReserveAdjustment@UpdateReserveManager@@AEAAJQEB_W@Z; UpdateReserveManager::FinishHardReserveAdjustment(wchar_t const * const)
0x18001d39f  mov     ebx, eax
0x18001d3a1  test    eax, eax
0x18001d3a3  jns     short loc_18001D3D1
0x18001d3a5  lea     rcx, [rsp+0D8h+lpSubKey]
0x18001d3ad  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d3b2  nop
0x18001d3b3  cmp     [rsp+0D8h+var_88], r14b
0x18001d3b8  jz      short loc_18001D3CD
0x18001d3ba  mov     rcx, [rsp+0D8h+var_90]
0x18001d3bf  mov     rcx, [rcx]; hMutex
0x18001d3c2  test    rcx, rcx
0x18001d3c5  jz      short loc_18001D3CD
0x18001d3c7  call    cs:__imp_ReleaseMutex
0x18001d3cd  mov     eax, ebx
0x18001d3cf  jmp     short loc_18001D411
0x18001d3d1  lea     rcx, [rdi+4B0h]; char *
0x18001d3d8  call    ?ReportRemovePendingHardReserveAdjustment@CUpdateReserveManagerDiagnostics@@SAXPEBD@Z; CUpdateReserveManagerDiagnostics::ReportRemovePendingHardReserveAdjustment(char const *)
0x18001d3dd  nop
0x18001d3de  lea     rcx, [rsp+0D8h+lpSubKey]
0x18001d3e6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d3eb  nop
0x18001d3ec  cmp     [rsp+0D8h+var_88], r14b
0x18001d3f1  jz      short loc_18001D406
0x18001d3f3  mov     rax, [rsp+0D8h+var_90]
0x18001d3f8  mov     rcx, [rax]; hMutex
0x18001d3fb  test    rcx, rcx
0x18001d3fe  jz      short loc_18001D406
0x18001d400  call    cs:__imp_ReleaseMutex
0x18001d406  xor     eax, eax
0x18001d408  jmp     short loc_18001D411
0x18001d40a  mov     eax, [rsp+0D8h+var_58]
0x18001d411  mov     rcx, [rsp+0D8h+var_28]
0x18001d419  xor     rcx, rsp; StackCookie
0x18001d41c  call    __security_check_cookie
0x18001d421  mov     rbx, [rsp+0D8h+arg_10]
0x18001d429  add     rsp, 0C0h
0x18001d430  pop     r14
0x18001d432  pop     rdi
0x18001d433  pop     rsi
0x18001d434  retn
```
