# UpdateReserveManager::PrepareForUninstall(void)

- ea: `0x18001b8f0`
- end: `0x18001bd24`
- name: `?PrepareForUninstall@UpdateReserveManager@@UEAAJXZ`
- size: `1076`
- prototype: `__int64 __fastcall(HANDLE *this, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update`

## callees

- `0x180003870`
- `0x180003c84`
- `0x1800044e0`
- `0x18000fafc`
- `0x180010ea4`
- `0x180010fe0`
- `0x1800133f8`
- `0x180015ad0`
- `0x18001a8f0`
- `0x18001b8f0`
- `0x180020778`
- `0x1800248e0`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18001bc28`
- `ntdll!NtFsControlFile` at `0x18001bc28`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b957`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b9c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b9f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ba8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bacf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bb11`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bb53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bb95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bcbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bcf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b957`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b9c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b9f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ba8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bacf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bb11`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bb53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bb95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bcbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bcf0`

## string_xrefs

- `0x18001b96d`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001bc38`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001b979`: `UpdateReserveManager::PrepareForUninstall`
- `0x18001bc47`: `UpdateReserveManager::PrepareForUninstall`
- `0x18001bc62`: `::NtFsControlFile(m_VolumePathHandle, nullptr, nullptr, nullptr, &IoStatusBlock, ( ((0x00000009) << 16) | ((0) << 14) | ((262) << 2) | (0) ), DeleteInput.Get(), DeleteInputBufferSize, nullptr, 0)`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::PrepareForUninstall(HANDLE *this, unsigned int a2)
{
  int v3; // eax
  unsigned int v4; // edi
  __int64 result; // rax
  const char *v6; // r9
  int v7; // edi
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // edi
  char *InputBuffer; // rdi
  unsigned __int64 v15; // rdx
  int v16; // ecx
  unsigned int v17; // ebx
  unsigned __int64 v18; // rdx
  HANDLE *v19; // [rsp+50h] [rbp-98h] BYREF
  char v20; // [rsp+58h] [rbp-90h]
  const char *v21; // [rsp+60h] [rbp-88h] BYREF
  __int64 v22; // [rsp+68h] [rbp-80h]
  __int64 v23; // [rsp+70h] [rbp-78h]
  const char *v24; // [rsp+78h] [rbp-70h]
  _QWORD v25[5]; // [rsp+80h] [rbp-68h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-40h] BYREF
  char v27; // [rsp+B0h] [rbp-38h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-30h] BYREF
  _DWORD v29[4]; // [rsp+C8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v25[4] = -2;
  v19 = this + 149;
  v20 = 0;
  v3 = AutoMutexLocker::Lock((AutoMutexLocker *)&v19, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    try
    {
      if ( *((_BYTE *)this + 1176) )
      {
        v7 = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)this);
        if ( v7 >= 0 )
        {
          v29[0] = 28;
          v29[1] = 17;
          v29[2] = 18;
          v26 = 0;
          v27 = 0;
          v21 = (const char *)v29;
          v22 = 3;
          v8 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v26, &v21);
          if ( v8 >= 0 )
          {
            v10 = UpdateReserveManager::ClearReserve((UpdateReserveManager *)this, 1u);
            if ( v10 >= 0 )
            {
              v11 = UpdateReserveManager::UntagFilesInReserve((UpdateReserveManager *)this, StorageReserveIdHard);
              if ( v11 >= 0 )
              {
                v12 = UpdateReserveManager::UntagFilesInReserve((UpdateReserveManager *)this, StorageReserveIdSoft);
                if ( v12 >= 0 )
                {
                  v13 = UpdateReserveManager::UntagFilesInReserve((UpdateReserveManager *)this, StorageReserveIdMax);
                  if ( v13 >= 0 )
                  {
                    v21 = 0;
                    InputBuffer = (char *)operator new[](0x1Cu);
                    v21 = InputBuffer;
                    *(_QWORD *)InputBuffer = 1;
                    *((_DWORD *)InputBuffer + 2) = 16;
                    *((_DWORD *)InputBuffer + 3) = 3;
                    *((_DWORD *)InputBuffer + 4) = 1;
                    *((_DWORD *)InputBuffer + 5) = 2;
                    *((_DWORD *)InputBuffer + 6) = 3;
                    IoStatusBlock = 0;
                    v16 = NtFsControlFile(this[16], 0, 0, 0, &IoStatusBlock, 0x90418u, InputBuffer, 0x1Cu, 0, 0);
                    if ( v16 >= 0 )
                    {
                      operator delete(InputBuffer, v15);
                      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v26);
                      if ( v20 && *v19 )
                        ReleaseMutex(*v19);
                      result = 0;
                    }
                    else
                    {
                      v25[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
                      v25[1] = "UpdateReserveManager::PrepareForUninstall";
                      v25[2] = 1452;
                      v25[3] = "::NtFsControlFile(m_VolumePathHandle, nullptr, nullptr, nullptr, &IoStatusBlock, ( ((0x00"
                               "000009) << 16) | ((0) << 14) | ((262) << 2) | (0) ), DeleteInput.Get(), DeleteInputBuffer"
                               "Size, nullptr, 0)";
                      v17 = ConvertNtStatusToHResult(v16);
                      RtlReportErrorOrigination(v25, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v17);
                      operator delete(InputBuffer, v18);
                      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v26);
                      if ( v20 && *v19 )
                        ReleaseMutex(*v19);
                      result = v17;
                    }
                  }
                  else
                  {
                    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v26);
                    if ( v20 && *v19 )
                      ReleaseMutex(*v19);
                    result = (unsigned int)v13;
                  }
                }
                else
                {
                  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v26);
                  if ( v20 && *v19 )
                    ReleaseMutex(*v19);
                  result = (unsigned int)v12;
                }
              }
              else
              {
                RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v26);
                if ( v20 && *v19 )
                  ReleaseMutex(*v19);
                result = (unsigned int)v11;
              }
            }
            else
            {
              RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v26);
              if ( v20 && *v19 )
                ReleaseMutex(*v19);
              result = (unsigned int)v10;
            }
          }
          else
          {
            v9 = ConvertNtStatusToHResult(v8);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v26);
            if ( v20 && *v19 )
              ReleaseMutex(*v19);
            result = v9;
          }
        }
        else
        {
          if ( v20 && *v19 )
            ReleaseMutex(*v19);
          result = (unsigned int)v7;
        }
      }
      else
      {
        v21 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v22 = (__int64)"UpdateReserveManager::PrepareForUninstall";
        v23 = 1388;
        v24 = "static_cast<DWORD>(50L)";
        RtlReportErrorOrigination(&v21, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942450LL);
        if ( v20 && *v19 )
          ReleaseMutex(*v19);
        result = 2147942450LL;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x5B0,
                             (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                             v6);
    }
  }
  else
  {
    if ( v20 )
    {
      if ( *v19 )
        ReleaseMutex(*v19);
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18001b8f0  mov     rax, rsp
0x18001b8f3  push    rdi
0x18001b8f4  sub     rsp, 0E0h
0x18001b8fb  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18001b903  mov     [rax+10h], rbx
0x18001b907  mov     [rax+18h], rsi
0x18001b90b  mov     rax, cs:__security_cookie
0x18001b912  xor     rax, rsp
0x18001b915  mov     [rsp+0E8h+var_10], rax
0x18001b91d  mov     rbx, rcx
0x18001b920  lea     rax, [rcx+4A8h]
0x18001b927  mov     [rsp+0E8h+var_98], rax
0x18001b92c  xor     esi, esi
0x18001b92e  mov     [rsp+0E8h+var_90], sil
0x18001b933  lea     rcx, [rsp+0E8h+var_98]; this
0x18001b938  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x18001b93d  mov     edi, eax
0x18001b93f  test    eax, eax
0x18001b941  jns     short loc_18001B964
0x18001b943  cmp     [rsp+0E8h+var_90], sil
0x18001b948  jz      short loc_18001B95D
0x18001b94a  mov     rcx, [rsp+0E8h+var_98]
0x18001b94f  mov     rcx, [rcx]; hMutex
0x18001b952  test    rcx, rcx
0x18001b955  jz      short loc_18001B95D
0x18001b957  call    cs:__imp_ReleaseMutex
0x18001b95d  mov     eax, edi
0x18001b95f  jmp     loc_18001BCFE
0x18001b964  cmp     [rbx+498h], sil
0x18001b96b  jnz     short loc_18001B9D6
0x18001b96d  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001b974  mov     [rsp+0E8h+var_88], rax
0x18001b979  lea     rax, aUpdatereservem_12; "UpdateReserveManager::PrepareForUninsta"...
0x18001b980  mov     [rsp+0E8h+var_80], rax
0x18001b985  mov     [rsp+0E8h+var_78], 56Ch
0x18001b98e  lea     rax, aStaticCastDwor; "static_cast<DWORD>(50L)"
0x18001b995  mov     [rsp+0E8h+var_70], rax
0x18001b99a  mov     r8d, 80070032h
0x18001b9a0  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001b9a7  lea     rcx, [rsp+0E8h+var_88]
0x18001b9ac  call    RtlReportErrorOrigination
0x18001b9b1  nop
0x18001b9b2  cmp     [rsp+0E8h+var_90], sil
0x18001b9b7  jz      short loc_18001B9CC
0x18001b9b9  mov     rax, [rsp+0E8h+var_98]
0x18001b9be  mov     rcx, [rax]; hMutex
0x18001b9c1  test    rcx, rcx
0x18001b9c4  jz      short loc_18001B9CC
0x18001b9c6  call    cs:__imp_ReleaseMutex
0x18001b9cc  mov     eax, 80070032h
0x18001b9d1  jmp     loc_18001BCFE
0x18001b9d6  mov     rcx, rbx; this
0x18001b9d9  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001b9de  mov     edi, eax
0x18001b9e0  test    eax, eax
0x18001b9e2  jns     short loc_18001BA05
0x18001b9e4  cmp     [rsp+0E8h+var_90], sil
0x18001b9e9  jz      short loc_18001B9FE
0x18001b9eb  mov     rcx, [rsp+0E8h+var_98]
0x18001b9f0  mov     rcx, [rcx]; hMutex
0x18001b9f3  test    rcx, rcx
0x18001b9f6  jz      short loc_18001B9FE
0x18001b9f8  call    cs:__imp_ReleaseMutex
0x18001b9fe  mov     eax, edi
0x18001ba00  jmp     loc_18001BCFE
0x18001ba05  mov     [rsp+0E8h+var_20], 1Ch
0x18001ba10  mov     [rsp+0E8h+var_1C], 11h
0x18001ba1b  mov     [rsp+0E8h+var_18], 12h
0x18001ba26  mov     [rsp+0E8h+var_40], rsi
0x18001ba2e  mov     [rsp+0E8h+var_38], sil
0x18001ba36  lea     rax, [rsp+0E8h+var_20]
0x18001ba3e  mov     [rsp+0E8h+var_88], rax
0x18001ba43  mov     [rsp+0E8h+var_80], 3
0x18001ba4c  lea     rdx, [rsp+0E8h+var_88]
0x18001ba51  lea     rcx, [rsp+0E8h+var_40]
0x18001ba59  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x18001ba5e  test    eax, eax
0x18001ba60  jns     short loc_18001BA9A
0x18001ba62  mov     ecx, eax; Status
0x18001ba64  call    ConvertNtStatusToHResult
0x18001ba69  mov     ebx, eax
0x18001ba6b  lea     rcx, [rsp+0E8h+var_40]; this
0x18001ba73  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001ba78  nop
0x18001ba79  cmp     [rsp+0E8h+var_90], sil
0x18001ba7e  jz      short loc_18001BA93
0x18001ba80  mov     rcx, [rsp+0E8h+var_98]
0x18001ba85  mov     rcx, [rcx]; hMutex
0x18001ba88  test    rcx, rcx
0x18001ba8b  jz      short loc_18001BA93
0x18001ba8d  call    cs:__imp_ReleaseMutex
0x18001ba93  mov     eax, ebx
0x18001ba95  jmp     loc_18001BCFE
0x18001ba9a  mov     edx, 1; enum _STORAGE_RESERVE_ID
0x18001ba9f  mov     rcx, rbx; this
0x18001baa2  call    ?ClearReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@@Z; UpdateReserveManager::ClearReserve(_STORAGE_RESERVE_ID)
0x18001baa7  mov     edi, eax
0x18001baa9  test    eax, eax
0x18001baab  jns     short loc_18001BADC
0x18001baad  lea     rcx, [rsp+0E8h+var_40]; this
0x18001bab5  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001baba  nop
0x18001babb  cmp     [rsp+0E8h+var_90], sil
0x18001bac0  jz      short loc_18001BAD5
0x18001bac2  mov     rcx, [rsp+0E8h+var_98]
0x18001bac7  mov     rcx, [rcx]; hMutex
0x18001baca  test    rcx, rcx
0x18001bacd  jz      short loc_18001BAD5
0x18001bacf  call    cs:__imp_ReleaseMutex
0x18001bad5  mov     eax, edi
0x18001bad7  jmp     loc_18001BCFE
0x18001badc  mov     edx, 1; enum _STORAGE_RESERVE_ID
0x18001bae1  mov     rcx, rbx; this
0x18001bae4  call    ?UntagFilesInReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@@Z; UpdateReserveManager::UntagFilesInReserve(_STORAGE_RESERVE_ID)
0x18001bae9  mov     edi, eax
0x18001baeb  test    eax, eax
0x18001baed  jns     short loc_18001BB1E
0x18001baef  lea     rcx, [rsp+0E8h+var_40]; this
0x18001baf7  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001bafc  nop
0x18001bafd  cmp     [rsp+0E8h+var_90], sil
0x18001bb02  jz      short loc_18001BB17
0x18001bb04  mov     rcx, [rsp+0E8h+var_98]
0x18001bb09  mov     rcx, [rcx]; hMutex
0x18001bb0c  test    rcx, rcx
0x18001bb0f  jz      short loc_18001BB17
0x18001bb11  call    cs:__imp_ReleaseMutex
0x18001bb17  mov     eax, edi
0x18001bb19  jmp     loc_18001BCFE
0x18001bb1e  mov     edx, 2; enum _STORAGE_RESERVE_ID
0x18001bb23  mov     rcx, rbx; this
0x18001bb26  call    ?UntagFilesInReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@@Z; UpdateReserveManager::UntagFilesInReserve(_STORAGE_RESERVE_ID)
0x18001bb2b  mov     edi, eax
0x18001bb2d  test    eax, eax
0x18001bb2f  jns     short loc_18001BB60
0x18001bb31  lea     rcx, [rsp+0E8h+var_40]; this
0x18001bb39  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001bb3e  nop
0x18001bb3f  cmp     [rsp+0E8h+var_90], sil
0x18001bb44  jz      short loc_18001BB59
0x18001bb46  mov     rcx, [rsp+0E8h+var_98]
0x18001bb4b  mov     rcx, [rcx]; hMutex
0x18001bb4e  test    rcx, rcx
0x18001bb51  jz      short loc_18001BB59
0x18001bb53  call    cs:__imp_ReleaseMutex
0x18001bb59  mov     eax, edi
0x18001bb5b  jmp     loc_18001BCFE
0x18001bb60  mov     edx, 3; enum _STORAGE_RESERVE_ID
0x18001bb65  mov     rcx, rbx; this
0x18001bb68  call    ?UntagFilesInReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@@Z; UpdateReserveManager::UntagFilesInReserve(_STORAGE_RESERVE_ID)
0x18001bb6d  mov     edi, eax
0x18001bb6f  test    eax, eax
0x18001bb71  jns     short loc_18001BBA2
0x18001bb73  lea     rcx, [rsp+0E8h+var_40]; this
0x18001bb7b  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001bb80  nop
0x18001bb81  cmp     [rsp+0E8h+var_90], sil
0x18001bb86  jz      short loc_18001BB9B
0x18001bb88  mov     rcx, [rsp+0E8h+var_98]
0x18001bb8d  mov     rcx, [rcx]; hMutex
0x18001bb90  test    rcx, rcx
0x18001bb93  jz      short loc_18001BB9B
0x18001bb95  call    cs:__imp_ReleaseMutex
0x18001bb9b  mov     eax, edi
0x18001bb9d  jmp     loc_18001BCFE
0x18001bba2  mov     [rsp+0E8h+var_88], rsi
0x18001bba7  mov     ecx, 1Ch; unsigned __int64
0x18001bbac  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001bbb1  mov     rdi, rax
0x18001bbb4  mov     [rsp+0E8h+var_88], rax
0x18001bbb9  mov     qword ptr [rax], 1
0x18001bbc0  mov     dword ptr [rax+8], 10h
0x18001bbc7  mov     dword ptr [rax+0Ch], 3
0x18001bbce  mov     dword ptr [rax+10h], 1
0x18001bbd5  mov     dword ptr [rax+14h], 2
0x18001bbdc  mov     dword ptr [rax+18h], 3
0x18001bbe3  xorps   xmm0, xmm0
0x18001bbe6  movups  xmmword ptr [rsp+0E8h+var_30], xmm0
0x18001bbee  mov     [rsp+0E8h+OutputBufferLength], esi; OutputBufferLength
0x18001bbf2  mov     [rsp+0E8h+OutputBuffer], rsi; OutputBuffer
0x18001bbf7  mov     [rsp+0E8h+InputBufferLength], 1Ch; InputBufferLength
0x18001bbff  mov     [rsp+0E8h+InputBuffer], rax; InputBuffer
0x18001bc04  mov     [rsp+0E8h+FsControlCode], 90418h; FsControlCode
0x18001bc0c  lea     rax, [rsp+0E8h+var_30]
0x18001bc14  mov     [rsp+0E8h+IoStatusBlock], rax; IoStatusBlock
0x18001bc19  xor     r9d, r9d; ApcContext
0x18001bc1c  xor     r8d, r8d; ApcRoutine
0x18001bc1f  xor     edx, edx; Event
0x18001bc21  mov     rcx, [rbx+80h]; FileHandle
0x18001bc28  call    cs:__imp_NtFsControlFile
0x18001bc2e  mov     ecx, eax; Status
0x18001bc30  test    eax, eax
0x18001bc32  jns     loc_18001BCC5
0x18001bc38  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001bc3f  mov     [rsp+0E8h+var_68], rax
0x18001bc47  lea     rax, aUpdatereservem_12; "UpdateReserveManager::PrepareForUninsta"...
0x18001bc4e  mov     [rsp+0E8h+var_60], rax
0x18001bc56  mov     [rsp+0E8h+var_58], 5ACh
0x18001bc62  lea     rax, aNtfscontrolfil_0; "::NtFsControlFile(m_VolumePathHandle, n"...
0x18001bc69  mov     [rsp+0E8h+var_50], rax
0x18001bc71  call    ConvertNtStatusToHResult
0x18001bc76  mov     ebx, eax
0x18001bc78  mov     r8d, eax
0x18001bc7b  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001bc82  lea     rcx, [rsp+0E8h+var_68]
0x18001bc8a  call    RtlReportErrorOrigination
0x18001bc8f  nop
0x18001bc90  mov     rcx, rdi; void *
0x18001bc93  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bc98  nop
0x18001bc99  lea     rcx, [rsp+0E8h+var_40]; this
0x18001bca1  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001bca6  nop
0x18001bca7  cmp     [rsp+0E8h+var_90], sil
0x18001bcac  jz      short loc_18001BCC1
0x18001bcae  mov     rax, [rsp+0E8h+var_98]
0x18001bcb3  mov     rcx, [rax]; hMutex
0x18001bcb6  test    rcx, rcx
0x18001bcb9  jz      short loc_18001BCC1
0x18001bcbb  call    cs:__imp_ReleaseMutex
0x18001bcc1  mov     eax, ebx
0x18001bcc3  jmp     short loc_18001BCFE
0x18001bcc5  mov     rcx, rdi; void *
0x18001bcc8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bccd  nop
0x18001bcce  lea     rcx, [rsp+0E8h+var_40]; this
0x18001bcd6  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001bcdb  nop
0x18001bcdc  cmp     [rsp+0E8h+var_90], sil
0x18001bce1  jz      short loc_18001BCF6
0x18001bce3  mov     rax, [rsp+0E8h+var_98]
0x18001bce8  mov     rcx, [rax]; hMutex
0x18001bceb  test    rcx, rcx
0x18001bcee  jz      short loc_18001BCF6
0x18001bcf0  call    cs:__imp_ReleaseMutex
0x18001bcf6  xor     eax, eax
0x18001bcf8  jmp     short loc_18001BCFE
0x18001bcfa  mov     eax, dword ptr [rsp+0E8h+var_88]
0x18001bcfe  mov     rcx, [rsp+0E8h+var_10]
0x18001bd06  xor     rcx, rsp; StackCookie
0x18001bd09  call    __security_check_cookie
0x18001bd0e  lea     r11, [rsp+0E8h+var_8]
0x18001bd16  mov     rbx, [r11+18h]
0x18001bd1a  mov     rsi, [r11+20h]
0x18001bd1e  mov     rsp, r11
0x18001bd21  pop     rdi
0x18001bd22  retn
```
