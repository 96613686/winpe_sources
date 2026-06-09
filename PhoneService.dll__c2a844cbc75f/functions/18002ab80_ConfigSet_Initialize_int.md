# ConfigSet::Initialize(int)

- ea: `0x18002ab80`
- end: `0x18002b110`
- name: `?Initialize@ConfigSet@@QEAAJH@Z`
- size: `1424`
- prototype: `__int64 __fastcall(ConfigSet *this)`
- caller_count: `9`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002b120`
- `0x1800678cc`
- `0x18007a8c0`
- `0x18007bcb8`
- `0x180081bd0`
- `0x18008a1e0`
- `0x18008a2c0`
- `0x18008a3b0`
- `0x18008a890`

## callees

- `0x1800056a0`
- `0x18001db10`
- `0x18001db40`
- `0x18002a1bc`
- `0x18002ab80`
- `0x18002c574`
- `0x18002c580`
- `0x18002df34`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ada4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ada4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b09c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b09c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002adc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002adc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002acef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ad25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002af05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002af99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002acef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ad25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002af05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002af99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ad56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ad56`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002b044`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002b044`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002b092`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002b092`

## string_xrefs

- `0x18002aba8`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c
__int64 __fastcall ConfigSet::Initialize(ConfigSet *this)
{
  int v2; // ecx
  __int64 v3; // rcx
  int RegistryPath; // eax
  int v5; // ebx
  HKEY *v6; // r14
  HKEY *phkResult; // rax
  LSTATUS v8; // ecx
  __int16 *v9; // rax
  HKEY *v10; // rax
  HKEY v11; // rbx
  HKEY v12; // rcx
  HANDLE EventW; // rbx
  HANDLE v14; // rax
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  HKEY *v18; // rax
  LSTATUS v19; // eax
  WCHAR *v20; // rcx
  HKEY *v21; // rax
  signed int LastError; // eax
  HKEY v23; // rcx
  LSTATUS v24; // eax
  void *v25; // rbx
  void **v26; // rax
  signed int v27; // eax
  void *Block; // [rsp+30h] [rbp-69h] BYREF
  __int16 *v30; // [rsp+38h] [rbp-61h]
  __int16 v31; // [rsp+40h] [rbp-59h] BYREF
  __int64 v32; // [rsp+42h] [rbp-57h]
  int v33; // [rsp+4Ah] [rbp-4Fh]
  __int16 v34; // [rsp+4Eh] [rbp-4Bh]
  LPCWSTR v35; // [rsp+50h] [rbp-49h] BYREF
  const WCHAR *v36; // [rsp+58h] [rbp-41h]
  __int16 v37; // [rsp+60h] [rbp-39h] BYREF
  __int64 v38; // [rsp+62h] [rbp-37h]
  int v39; // [rsp+6Ah] [rbp-2Fh]
  __int16 v40; // [rsp+6Eh] [rbp-2Bh]
  LPCWSTR lpSubKey[2]; // [rsp+70h] [rbp-29h] BYREF
  __int16 v42; // [rsp+80h] [rbp-19h] BYREF
  __int64 v43; // [rsp+82h] [rbp-17h]
  int v44; // [rsp+8Ah] [rbp-Fh]
  __int16 v45; // [rsp+8Eh] [rbp-Bh]
  LPCWSTR v46[2]; // [rsp+90h] [rbp-9h] BYREF
  __int16 v47; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v48; // [rsp+A2h] [rbp+9h]
  int v49; // [rsp+AAh] [rbp+11h]
  __int16 v50; // [rsp+AEh] [rbp+15h]

  if ( (unsigned __int64)(*((_QWORD *)this + 13) + 0x80000000LL) > 3 )
  {
    Log_AssertionEvent_3(this, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 936);
    if ( (unsigned __int64)(*((_QWORD *)this + 13) + 0x80000000LL) > 3 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v2 = *((_DWORD *)this + 36);
  if ( !v2 )
  {
    v5 = ConfigSet::ReadWriteCreateKey(this);
    if ( v5 < 0 )
    {
      v15 = 941;
      goto LABEL_36;
    }
    goto LABEL_25;
  }
  v3 = (unsigned int)(v2 - 1);
  if ( (_DWORD)v3 )
  {
    if ( (_DWORD)v3 != 1 )
    {
      Log_AssertionEvent_3(v3, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 953);
      MicrosoftTelemetryAssertTriggeredNoArgs();
      goto LABEL_25;
    }
    v43 = 0;
    v45 = 0;
    v44 = 0;
    lpSubKey[0] = (LPCWSTR)&v42;
    lpSubKey[1] = (LPCWSTR)&v42;
    v42 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    Block = &v31;
    v30 = &v31;
    v31 = 0;
    RegistryPath = ConfigSet::GetRegistryPath(this, lpSubKey, &Block);
    v5 = RegistryPath;
    if ( RegistryPath < 0 )
    {
      Log_HREvent_7((unsigned int)RegistryPath, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 987);
      if ( Block != &v31 )
        operator delete(Block);
      if ( (__int16 *)lpSubKey[0] == &v42 )
        goto LABEL_35;
      goto LABEL_34;
    }
    v6 = (HKEY *)((char *)this + 80);
    phkResult = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((char *)this + 80);
    v5 = RegOpenKeyExW(*((HKEY *)this + 13), lpSubKey[0], 0, 0x11u, phkResult);
    v8 = 2;
    v9 = (__int16 *)Block;
    if ( Block != v30 )
    {
      v10 = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((char *)this + 88);
      v8 = RegOpenKeyExW(*((HKEY *)this + 13), (LPCWSTR)Block, 0, 0x11u, v10);
      v9 = (__int16 *)Block;
    }
    if ( v5 )
    {
      if ( v8 )
      {
        if ( v5 > 0 )
          v5 = (unsigned __int16)v5 | 0x80070000;
        Log_HREvent_7((unsigned int)v5, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1008);
        if ( Block != &v31 )
          operator delete(Block);
        if ( (__int16 *)lpSubKey[0] == &v42 )
          goto LABEL_35;
LABEL_34:
        operator delete((void *)lpSubKey[0]);
LABEL_35:
        v15 = 949;
        goto LABEL_36;
      }
      v11 = (HKEY)*((_QWORD *)this + 11);
      *((_QWORD *)this + 11) = 0;
      v12 = *v6;
      if ( v11 != *v6 )
      {
        if ( v12 )
        {
          RegCloseKey(v12);
          v9 = (__int16 *)Block;
        }
        *v6 = v11;
      }
    }
    if ( v9 != &v31 )
      operator delete(v9);
    if ( (__int16 *)lpSubKey[0] != &v42 )
      operator delete((void *)lpSubKey[0]);
    goto LABEL_25;
  }
  v48 = 0;
  v50 = 0;
  v49 = 0;
  v46[0] = (LPCWSTR)&v47;
  v46[1] = (LPCWSTR)&v47;
  v47 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v35 = (LPCWSTR)&v37;
  v36 = (const WCHAR *)&v37;
  v37 = 0;
  v17 = ConfigSet::GetRegistryPath(this, v46, &v35);
  v5 = v17;
  if ( v17 < 0 )
  {
    Log_HREvent_7((unsigned int)v17, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1018);
    if ( v35 != (LPCWSTR)&v37 )
      operator delete((void *)v35);
    if ( (__int16 *)v46[0] != &v47 )
      operator delete((void *)v46[0]);
    goto LABEL_50;
  }
  v18 = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((char *)this + 80);
  v19 = RegOpenKeyExW(*((HKEY *)this + 13), v46[0], 0, 0x13u, v18);
  v5 = v19;
  if ( !v19 )
  {
    v20 = (WCHAR *)v35;
    if ( v35 != v36 )
    {
      v21 = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((char *)this + 88);
      RegOpenKeyExW(*((HKEY *)this + 13), v35, 0, 0x11u, v21);
      v20 = (WCHAR *)v35;
    }
    if ( v20 != (WCHAR *)&v37 )
      operator delete(v20);
    if ( (__int16 *)v46[0] != &v47 )
      operator delete((void *)v46[0]);
    goto LABEL_25;
  }
  if ( v19 > 0 )
    v5 = (unsigned __int16)v19 | 0x80070000;
  Log_HREvent_7((unsigned int)v5, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1020);
  if ( v35 != (LPCWSTR)&v37 )
    operator delete((void *)v35);
  if ( (__int16 *)v46[0] != &v47 )
    operator delete((void *)v46[0]);
  if ( v5 < 0 )
  {
LABEL_50:
    v15 = 945;
    goto LABEL_36;
  }
LABEL_25:
  EventW = CreateEventW(0, 0, 0, 0);
  v14 = (HANDLE)*((_QWORD *)this + 9);
  if ( EventW == v14 )
  {
    EventW = (HANDLE)*((_QWORD *)this + 9);
  }
  else
  {
    if ( v14 )
      CloseHandle(*((HANDLE *)this + 9));
    *((_QWORD *)this + 9) = EventW;
  }
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v15 = 961;
    goto LABEL_77;
  }
  v23 = (HKEY)*((_QWORD *)this + 10);
  if ( (unsigned __int64)(v23 + 0x20000000) <= 3 )
  {
    v15 = 968;
    v5 = -2147418113;
LABEL_77:
    v16 = 0;
    goto LABEL_78;
  }
  v24 = RegNotifyChangeKeyValue(v23, 1, 0x10000004u, EventW, 1);
  v5 = v24;
  if ( v24 > 0 )
    v5 = (unsigned __int16)v24 | 0x80070000;
  if ( v5 >= 0 )
  {
    v25 = (void *)*((_QWORD *)this + 9);
    v26 = (void **)tlx::replace<void *,unsigned long (*)(void *),&private: static unsigned long ConfigSet::UnregisterWaitAndBlock(void *),0>((char *)this + 96);
    if ( !RegisterWaitForSingleObject(v26, v25, ConfigSet::RegistryNotificationCallback, this, 0xFFFFFFFF, 0) )
    {
      v27 = GetLastError();
      v5 = v27;
      if ( v27 > 0 )
        v5 = (unsigned __int16)v27 | 0x80070000;
      v15 = 975;
      goto LABEL_77;
    }
    v5 = (*(__int64 (__fastcall **)(ConfigSet *))(*(_QWORD *)this + 8LL))(this);
    if ( v5 >= 0 )
      return 0;
    v15 = 978;
  }
  else
  {
    v15 = 972;
  }
LABEL_36:
  v16 = 1;
LABEL_78:
  Log_HREvent_7((unsigned int)v5, v16, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002ab80  push    rbp
0x18002ab82  push    rbx
0x18002ab83  push    rdi
0x18002ab84  push    r12
0x18002ab86  push    r13
0x18002ab88  push    r14
0x18002ab8a  lea     rbp, [rsp-2Fh]
0x18002ab8f  sub     rsp, 0C8h
0x18002ab96  mov     rax, cs:__security_cookie
0x18002ab9d  xor     rax, rsp
0x18002aba0  mov     [rbp+57h+var_40], rax
0x18002aba4  mov     rax, [rcx+68h]
0x18002aba8  lea     r12, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18002abaf  mov     r14d, 80000000h
0x18002abb5  mov     rdi, rcx
0x18002abb8  add     rax, r14
0x18002abbb  cmp     rax, 3
0x18002abbf  jbe     short loc_18002ABE1
0x18002abc1  mov     r8d, 3A8h
0x18002abc7  mov     rdx, r12
0x18002abca  call    Log_AssertionEvent_3
0x18002abcf  mov     rax, [rdi+68h]
0x18002abd3  add     rax, r14
0x18002abd6  cmp     rax, 3
0x18002abda  jbe     short loc_18002ABE1
0x18002abdc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002abe1  mov     ecx, [rdi+90h]
0x18002abe7  mov     r13d, 80070000h
0x18002abed  test    ecx, ecx
0x18002abef  jz      loc_18002AFDA
0x18002abf5  sub     ecx, 1
0x18002abf8  jz      loc_18002AE37
0x18002abfe  cmp     ecx, 1
0x18002ac01  jz      short loc_18002AC1B
0x18002ac03  mov     r8d, 3B9h
0x18002ac09  mov     rdx, r12
0x18002ac0c  call    Log_AssertionEvent_3
0x18002ac11  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002ac16  jmp     loc_18002AD9A
0x18002ac1b  xor     eax, eax
0x18002ac1d  mov     [rbp+57h+var_6E], 0
0x18002ac25  mov     [rbp+57h+var_62], ax
0x18002ac29  lea     r8, [rbp+57h+Block]
0x18002ac2d  lea     rax, [rbp+57h+var_70]
0x18002ac31  mov     [rbp+57h+var_66], 0
0x18002ac38  mov     [rbp+57h+lpSubKey], rax
0x18002ac3c  lea     rdx, [rbp+57h+lpSubKey]
0x18002ac40  lea     rax, [rbp+57h+var_70]
0x18002ac44  mov     rcx, rdi
0x18002ac47  mov     [rbp+57h+var_78], rax
0x18002ac4b  xor     eax, eax
0x18002ac4d  mov     [rbp+57h+var_70], ax
0x18002ac51  mov     [rbp+57h+var_AE], rax
0x18002ac55  mov     [rbp+57h+var_A6], eax
0x18002ac58  mov     [rbp+57h+var_A2], ax
0x18002ac5c  lea     rax, [rbp+57h+var_B0]
0x18002ac60  mov     [rbp+57h+Block], rax
0x18002ac64  lea     rax, [rbp+57h+var_B0]
0x18002ac68  mov     [rbp+57h+var_B8], rax
0x18002ac6c  xor     eax, eax
0x18002ac6e  mov     [rbp+57h+var_B0], ax
0x18002ac72  call    ?GetRegistryPath@ConfigSet@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@0@Z; ConfigSet::GetRegistryPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18002ac77  mov     ebx, eax
0x18002ac79  test    eax, eax
0x18002ac7b  jns     short loc_18002ACCD
0x18002ac7d  mov     r9d, 3DBh
0x18002ac83  mov     r8, r12
0x18002ac86  mov     edx, 1
0x18002ac8b  mov     ecx, eax
0x18002ac8d  call    Log_HREvent_7
0x18002ac92  mov     rcx, [rbp+57h+Block]; Block
0x18002ac96  lea     rax, [rbp+57h+var_B0]
0x18002ac9a  cmp     rcx, rax
0x18002ac9d  jz      short loc_18002ACAB
0x18002ac9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002aca6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002acab  mov     rcx, [rbp+57h+lpSubKey]; Block
0x18002acaf  lea     rax, [rbp+57h+var_70]
0x18002acb3  cmp     rcx, rax
0x18002acb6  jz      loc_18002AE27
0x18002acbc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002acc3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002acc8  jmp     loc_18002AE27
0x18002accd  lea     r14, [rdi+50h]
0x18002acd1  mov     rcx, r14
0x18002acd4  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18002acd9  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18002acdd  mov     r9d, 11h; samDesired
0x18002ace3  mov     rcx, [rdi+68h]; hKey
0x18002ace7  xor     r8d, r8d; ulOptions
0x18002acea  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18002acef  call    cs:__imp_RegOpenKeyExW
0x18002acf5  mov     ebx, eax
0x18002acf7  mov     ecx, 2
0x18002acfc  mov     rax, [rbp+57h+Block]
0x18002ad00  cmp     rax, [rbp+57h+var_B8]
0x18002ad04  jz      short loc_18002AD31
0x18002ad06  lea     rcx, [rdi+58h]
0x18002ad0a  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18002ad0f  mov     rdx, [rbp+57h+Block]; lpSubKey
0x18002ad13  mov     r9d, 11h; samDesired
0x18002ad19  mov     rcx, [rdi+68h]; hKey
0x18002ad1d  xor     r8d, r8d; ulOptions
0x18002ad20  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18002ad25  call    cs:__imp_RegOpenKeyExW
0x18002ad2b  mov     ecx, eax
0x18002ad2d  mov     rax, [rbp+57h+Block]
0x18002ad31  test    ebx, ebx
0x18002ad33  jz      short loc_18002AD63
0x18002ad35  test    ecx, ecx
0x18002ad37  jnz     loc_18002ADD1
0x18002ad3d  mov     rbx, [rdi+58h]
0x18002ad41  mov     qword ptr [rdi+58h], 0
0x18002ad49  mov     rcx, [r14]; hKey
0x18002ad4c  cmp     rbx, rcx
0x18002ad4f  jz      short loc_18002AD63
0x18002ad51  test    rcx, rcx
0x18002ad54  jz      short loc_18002AD60
0x18002ad56  call    cs:__imp_RegCloseKey
0x18002ad5c  mov     rax, [rbp+57h+Block]
0x18002ad60  mov     [r14], rbx
0x18002ad63  lea     rcx, [rbp+57h+var_B0]
0x18002ad67  cmp     rax, rcx
0x18002ad6a  jz      short loc_18002AD7B
0x18002ad6c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002ad73  mov     rcx, rax; Block
0x18002ad76  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ad7b  mov     rcx, [rbp+57h+lpSubKey]; Block
0x18002ad7f  lea     rax, [rbp+57h+var_70]
0x18002ad83  cmp     rcx, rax
0x18002ad86  jz      short loc_18002AD94
0x18002ad88  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002ad8f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ad94  mov     r14d, 80000000h
0x18002ad9a  xor     r9d, r9d; lpName
0x18002ad9d  xor     r8d, r8d; bInitialState
0x18002ada0  xor     edx, edx; bManualReset
0x18002ada2  xor     ecx, ecx; lpEventAttributes
0x18002ada4  call    cs:__imp_CreateEventW
0x18002adaa  mov     rbx, rax
0x18002adad  mov     rax, [rdi+48h]
0x18002adb1  cmp     rbx, rax
0x18002adb4  jz      loc_18002AFF7
0x18002adba  test    rax, rax
0x18002adbd  jz      short loc_18002ADC8
0x18002adbf  mov     rcx, rax; hObject
0x18002adc2  call    cs:__imp_CloseHandle
0x18002adc8  mov     [rdi+48h], rbx
0x18002adcc  jmp     loc_18002AFFA
0x18002add1  test    ebx, ebx
0x18002add3  jle     short loc_18002ADDB
0x18002add5  movzx   ebx, bx
0x18002add8  or      ebx, r13d
0x18002addb  mov     r9d, 3F0h
0x18002ade1  mov     r8, r12
0x18002ade4  xor     edx, edx
0x18002ade6  mov     ecx, ebx
0x18002ade8  call    Log_HREvent_7
0x18002aded  mov     rcx, [rbp+57h+Block]; Block
0x18002adf1  lea     rax, [rbp+57h+var_B0]
0x18002adf5  cmp     rcx, rax
0x18002adf8  jz      short loc_18002AE06
0x18002adfa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002ae01  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ae06  mov     rcx, [rbp+57h+lpSubKey]; Block
0x18002ae0a  lea     rax, [rbp+57h+var_70]
0x18002ae0e  cmp     rcx, rax
0x18002ae11  jz      short loc_18002AE1F
0x18002ae13  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002ae1a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ae1f  test    ebx, ebx
0x18002ae21  jns     loc_18002AD94
0x18002ae27  mov     r9d, 3B5h
0x18002ae2d  mov     edx, 1
0x18002ae32  jmp     loc_18002B0E7
0x18002ae37  xor     eax, eax
0x18002ae39  mov     [rbp+57h+var_4E], 0
0x18002ae41  mov     [rbp+57h+var_42], ax
0x18002ae45  lea     r8, [rbp+57h+var_A0]
0x18002ae49  lea     rax, [rbp+57h+var_50]
0x18002ae4d  mov     [rbp+57h+var_46], 0
0x18002ae54  mov     [rbp+57h+var_60], rax
0x18002ae58  lea     rdx, [rbp+57h+var_60]
0x18002ae5c  lea     rax, [rbp+57h+var_50]
0x18002ae60  mov     rcx, rdi
0x18002ae63  mov     [rbp+57h+var_58], rax
0x18002ae67  xor     eax, eax
0x18002ae69  mov     [rbp+57h+var_50], ax
0x18002ae6d  mov     [rbp+57h+var_8E], rax
0x18002ae71  mov     [rbp+57h+var_86], eax
0x18002ae74  mov     [rbp+57h+var_82], ax
0x18002ae78  lea     rax, [rbp+57h+var_90]
0x18002ae7c  mov     [rbp+57h+var_A0], rax
0x18002ae80  lea     rax, [rbp+57h+var_90]
0x18002ae84  mov     [rbp+57h+var_98], rax
0x18002ae88  xor     eax, eax
0x18002ae8a  mov     [rbp+57h+var_90], ax
0x18002ae8e  call    ?GetRegistryPath@ConfigSet@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@0@Z; ConfigSet::GetRegistryPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18002ae93  mov     ebx, eax
0x18002ae95  test    eax, eax
0x18002ae97  jns     short loc_18002AEE6
0x18002ae99  mov     r9d, 3FAh
0x18002ae9f  mov     r8, r12
0x18002aea2  mov     edx, 1
0x18002aea7  mov     ecx, eax
0x18002aea9  call    Log_HREvent_7
0x18002aeae  mov     rcx, [rbp+57h+var_A0]; Block
0x18002aeb2  lea     rax, [rbp+57h+var_90]
0x18002aeb6  cmp     rcx, rax
0x18002aeb9  jz      short loc_18002AEC7
0x18002aebb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002aec2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002aec7  mov     rcx, [rbp+57h+var_60]; Block
0x18002aecb  lea     rax, [rbp+57h+var_50]
0x18002aecf  cmp     rcx, rax
0x18002aed2  jz      loc_18002AF65
0x18002aed8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002aedf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002aee4  jmp     short loc_18002AF65
0x18002aee6  lea     rcx, [rdi+50h]
0x18002aeea  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18002aeef  mov     rdx, [rbp+57h+var_60]; lpSubKey
0x18002aef3  mov     r9d, 13h; samDesired
0x18002aef9  mov     rcx, [rdi+68h]; hKey
0x18002aefd  xor     r8d, r8d; ulOptions
0x18002af00  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18002af05  call    cs:__imp_RegOpenKeyExW
0x18002af0b  mov     ebx, eax
0x18002af0d  test    eax, eax
0x18002af0f  jz      short loc_18002AF70
0x18002af11  jle     short loc_18002AF19
0x18002af13  movzx   ebx, ax
0x18002af16  or      ebx, r13d
0x18002af19  mov     r9d, 3FCh
0x18002af1f  mov     r8, r12
0x18002af22  xor     edx, edx
0x18002af24  mov     ecx, ebx
0x18002af26  call    Log_HREvent_7
0x18002af2b  mov     rcx, [rbp+57h+var_A0]; Block
0x18002af2f  lea     rax, [rbp+57h+var_90]
0x18002af33  cmp     rcx, rax
0x18002af36  jz      short loc_18002AF44
0x18002af38  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002af3f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002af44  mov     rcx, [rbp+57h+var_60]; Block
0x18002af48  lea     rax, [rbp+57h+var_50]
0x18002af4c  cmp     rcx, rax
0x18002af4f  jz      short loc_18002AF5D
0x18002af51  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002af58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002af5d  test    ebx, ebx
0x18002af5f  jns     loc_18002AD9A
0x18002af65  mov     r9d, 3B1h
0x18002af6b  jmp     loc_18002AE2D
0x18002af70  mov     rcx, [rbp+57h+var_A0]
0x18002af74  cmp     rcx, [rbp+57h+var_98]
0x18002af78  jz      short loc_18002AFA3
0x18002af7a  lea     rcx, [rdi+58h]
0x18002af7e  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18002af83  mov     rdx, [rbp+57h+var_A0]; lpSubKey
0x18002af87  mov     r9d, 11h; samDesired
0x18002af8d  mov     rcx, [rdi+68h]; hKey
0x18002af91  xor     r8d, r8d; ulOptions
0x18002af94  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18002af99  call    cs:__imp_RegOpenKeyExW
0x18002af9f  mov     rcx, [rbp+57h+var_A0]; Block
0x18002afa3  lea     rax, [rbp+57h+var_90]
0x18002afa7  cmp     rcx, rax
0x18002afaa  jz      short loc_18002AFB8
0x18002afac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002afb3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002afb8  mov     rcx, [rbp+57h+var_60]; Block
0x18002afbc  lea     rax, [rbp+57h+var_50]
0x18002afc0  cmp     rcx, rax
0x18002afc3  jz      loc_18002AD9A
0x18002afc9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002afd0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002afd5  jmp     loc_18002AD9A
0x18002afda  mov     rcx, rdi; this
0x18002afdd  call    ?ReadWriteCreateKey@ConfigSet@@QEAAJXZ; ConfigSet::ReadWriteCreateKey(void)
0x18002afe2  mov     ebx, eax
0x18002afe4  test    eax, eax
0x18002afe6  jns     loc_18002AD9A
0x18002afec  mov     r9d, 3ADh
0x18002aff2  jmp     loc_18002AE2D
0x18002aff7  mov     rbx, rax
0x18002affa  test    rbx, rbx
0x18002affd  jnz     short loc_18002B01C
0x18002afff  call    cs:__imp_GetLastError
0x18002b005  mov     ebx, eax
0x18002b007  test    eax, eax
0x18002b009  jle     short loc_18002B011
0x18002b00b  movzx   ebx, ax
0x18002b00e  or      ebx, r13d
0x18002b011  mov     r9d, 3C1h
0x18002b017  jmp     loc_18002B0E5
0x18002b01c  mov     rcx, [rdi+50h]; hKey
0x18002b020  lea     rax, [rcx+r14]
0x18002b024  cmp     rax, 3
0x18002b028  jbe     loc_18002B0DA
  ... truncated ...
```
