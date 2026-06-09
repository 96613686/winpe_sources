# WaasMedic::TaskProtector::RestoreProtectedTasks(bool,bool &,ulong &)

- ea: `0x18005acb8`
- end: `0x18005b092`
- name: `?RestoreProtectedTasks@TaskProtector@WaasMedic@@QEAAJ_NAEA_NAEAK@Z`
- size: `986`
- prototype: `int(WaasMedic::TaskProtector *__hidden this, bool, bool *, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180050b60`
- `0x1800510d0`

## callees

- `0x180024fc4`
- `0x1800251a8`
- `0x18002543c`
- `0x18005ac4c`
- `0x18005acb8`
- `0x18005c504`
- `0x18005f37c`
- `0x18005f9bc`
- `0x18005fc80`
- `0x180060440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005addb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005addb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18005ae7a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18005af5e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18005ae7a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18005af5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ad57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ad57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005af8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005af8c`

## string_xrefs

- `0x18005ad22`: `Failed to get the task store. Error code: 0x%08x`
- `0x18005ad6f`: `No tasks definitions stored.  Skipping.`
- `0x18005aeef`: `Found task with folder\name\definition: \n%s\n%s\n%s`
- `0x18005ad94`: `Failed to open tasks definition key. Error code: 0x%08x`
- `0x18005adff`: `Found %d tasks to restore.`
- `0x18005b00e`: `Failed to inspect the task: %s. Error code: 0x%08x`
- `0x18005af1a`: `Failed to initialize TasksHelper with the task folder: %s. Error code: 0x%08x`
- `0x18005afd1`: `Encountered failure while looking for task %s. hr=0x%08x`
- `0x18005b07e`: `Failed to create or update the task: %s. Error code: 0x%08x`
- `0x18005b033`: `Task '%s' was found to %s correctly configured.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::TaskProtector::RestoreProtectedTasks(
        WaasMedic::TaskProtector *this,
        char a2,
        bool *a3,
        unsigned int *a4)
{
  BYTE *v5; // r14
  WCHAR *v6; // rsi
  int TaskStore; // eax
  unsigned int v8; // ebx
  void *v9; // rdx
  DWORD v10; // r15d
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  unsigned __int64 v13; // rdx
  bool v14; // r8
  bool v15; // r8
  LSTATUS i; // eax
  __int64 v17; // rax
  const unsigned __int16 *v18; // r13
  int IsTaskConfiguredProperly; // r15d
  DWORD v20; // edx
  void *v21; // rdx
  int v23; // eax
  const unsigned __int16 *v24; // r9
  const wchar_t *v25; // r9
  int updated; // eax
  PHKEY phkResult; // [rsp+28h] [rbp-59h]
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-19h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-15h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-11h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-Dh] BYREF
  DWORD dwIndex; // [rsp+78h] [rbp-9h]
  HKEY hKey; // [rsp+80h] [rbp-1h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp+7h] BYREF
  LPVOID ppv[2]; // [rsp+90h] [rbp+Fh] BYREF
  __int64 v36; // [rsp+A0h] [rbp+1Fh]
  WaasMedic::TaskProtector *v37; // [rsp+E8h] [rbp+67h] BYREF
  char v38; // [rsp+F0h] [rbp+6Fh]
  bool *v39; // [rsp+F8h] [rbp+77h]
  bool v40; // [rsp+100h] [rbp+7Fh] BYREF

  v39 = a3;
  v38 = a2;
  v37 = this;
  hKey = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v5 = 0;
  v6 = 0;
  v36 = 0;
  *(_OWORD *)ppv = 0;
  lpSubKey = 0;
  *a3 = 0;
  *a4 = 0;
  TaskStore = WaasMedic::TaskProtector::GetTaskStore((unsigned __int16 **)&lpSubKey);
  v8 = TaskStore;
  if ( TaskStore < 0 )
  {
    LogLevelW(2u, L"Failed to get the task store. Error code: 0x%08x", (unsigned int)TaskStore);
    goto LABEL_29;
  }
  v10 = 1;
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hKey);
  if ( v11 )
  {
    if ( v11 > 0 )
    {
      if ( v11 == 2 )
      {
        LogLevelW(4u, L"No tasks definitions stored.  Skipping.");
        v8 = 0;
        goto LABEL_29;
      }
      v8 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v8 = v11;
    }
    LogLevelW(2u, L"Failed to open tasks definition key. Error code: 0x%08x", v8);
    goto LABEL_29;
  }
  v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, a4, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v12 )
  {
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    else
      v8 = v12;
    goto LABEL_29;
  }
  LogLevelW(4u, L"Found %d tasks to restore.", *a4);
  v6 = (WCHAR *)WaasMedic::SafeAlloc((WaasMedic *)(2LL * ++cbMaxValueNameLen), v13, v14);
  if ( !v6 || (v5 = (BYTE *)WaasMedic::SafeAlloc((WaasMedic *)cbMaxValueLen, (unsigned __int64)v9, v15)) == 0 )
  {
    v8 = -2147024882;
    goto LABEL_29;
  }
  cchValueName = cbMaxValueNameLen;
  cbData = cbMaxValueLen;
  dwIndex = 1;
  for ( i = RegEnumValueW(hKey, 0, v6, &cchValueName, 0, 0, v5, &cbData); i != 259; v10 = dwIndex )
  {
    cchValueName = cbMaxValueNameLen;
    cbData = cbMaxValueLen;
    if ( i )
    {
      if ( i > 0 )
        v8 = (unsigned __int16)i | 0x80070000;
      else
        v8 = i;
      LODWORD(phkResult) = v8;
      LogLevelW(
        2u,
        L"Could not enumerate the values under %s, index = %d. Error was: 0x%08x",
        lpSubKey,
        v10 - 1,
        phkResult);
      goto LABEL_28;
    }
    LOBYTE(v37) = 0;
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)&v5[2 * v17] );
    v18 = (const unsigned __int16 *)&v5[2 * v17 + 2];
    LogLevelW(4u, L"Found task with folder\\name\\definition: \n%s\n%s\n%s", v5, v6, v18);
    IsTaskConfiguredProperly = WaasMedic::TasksHelper::Initialize(ppv, (OLECHAR *)v5);
    if ( IsTaskConfiguredProperly >= 0 )
    {
      v40 = 0;
      v23 = WaasMedic::TasksHelper::TaskExists((WaasMedic::TasksHelper *)ppv, v6, &v40);
      if ( v23 < 0 )
      {
        LogLevelW(3u, L"Encountered failure while looking for task %s. hr=0x%08x", v6, (unsigned int)v23);
        goto LABEL_28;
      }
      if ( !v40 )
        goto LABEL_40;
      IsTaskConfiguredProperly = WaasMedic::TasksHelper::IsTaskConfiguredProperly(
                                   (WaasMedic::TasksHelper *)ppv,
                                   v6,
                                   v18,
                                   (int)v24,
                                   (bool *)&v37);
      if ( IsTaskConfiguredProperly >= 0 )
      {
        v25 = L"be";
        if ( !(_BYTE)v37 )
          v25 = L"not be";
        LogLevelW(4u, L"Task '%s' was found to %s correctly configured.", v6, v25);
        if ( (_BYTE)v37 )
          goto LABEL_28;
LABEL_40:
        *v39 = 1;
        if ( v38 )
        {
          updated = WaasMedic::TasksHelper::CreateOrUpdateTask((WaasMedic::TasksHelper *)ppv, v6, v18, v24);
          if ( updated < 0 )
            LogLevelW(2u, L"Failed to create or update the task: %s. Error code: 0x%08x", v6, (unsigned int)updated);
        }
        goto LABEL_28;
      }
      LogLevelW(2u, L"Failed to inspect the task: %s. Error code: 0x%08x", v6, (unsigned int)IsTaskConfiguredProperly);
    }
    else
    {
      LogLevelW(
        2u,
        L"Failed to initialize TasksHelper with the task folder: %s. Error code: 0x%08x",
        v5,
        (unsigned int)IsTaskConfiguredProperly);
    }
    v8 = IsTaskConfiguredProperly;
LABEL_28:
    v20 = dwIndex++;
    i = RegEnumValueW(hKey, v20, v6, &cchValueName, 0, 0, v5, &cbData);
  }
LABEL_29:
  WaasMedic::SafeFree((WaasMedic *)v6, v9);
  WaasMedic::SafeFree((WaasMedic *)v5, v21);
  if ( hKey )
    RegCloseKey(hKey);
  WaasMedic::TasksHelper::~TasksHelper((WaasMedic::TasksHelper *)ppv);
  return v8;
}

```

## disassembly

```asm
0x18005acb8  mov     rax, rsp
0x18005acbb  mov     [rax+18h], r8
0x18005acbf  mov     [rax+10h], dl
0x18005acc2  mov     [rax+8], rcx
0x18005acc6  push    rbp
0x18005acc7  push    rbx
0x18005acc8  push    rsi
0x18005acc9  push    rdi
0x18005acca  push    r13
0x18005accc  push    r14
0x18005acce  push    r15
0x18005acd0  lea     rbp, [rax-5Fh]
0x18005acd4  sub     rsp, 0A0h
0x18005acdb  mov     rdi, r9
0x18005acde  xor     r13d, r13d
0x18005ace1  mov     [rbp+57h+hKey], r13
0x18005ace5  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x18005ace9  mov     [rbp+57h+cbMaxValueLen], r13d
0x18005aced  mov     r14d, r13d
0x18005acf0  mov     esi, r13d
0x18005acf3  xor     ecx, ecx
0x18005acf5  mov     [rbp+57h+var_38], rcx
0x18005acf9  xorps   xmm1, xmm1
0x18005acfc  movdqu  xmmword ptr [rbp+57h+ppv], xmm1
0x18005ad01  mov     word ptr [rbp+57h+var_38], r13w
0x18005ad06  mov     [rbp+57h+lpSubKey], r13
0x18005ad0a  mov     [r8], r13b
0x18005ad0d  mov     [r9], r13d
0x18005ad10  lea     rcx, [rbp+57h+lpSubKey]; unsigned __int16 **
0x18005ad14  call    ?GetTaskStore@TaskProtector@WaasMedic@@CAJPEAPEAG@Z; WaasMedic::TaskProtector::GetTaskStore(ushort * *)
0x18005ad19  mov     ebx, eax
0x18005ad1b  test    eax, eax
0x18005ad1d  jns     short loc_18005AD37
0x18005ad1f  mov     r8d, eax
0x18005ad22  lea     rdx, aFailedToGetThe; "Failed to get the task store. Error cod"...
0x18005ad29  lea     ecx, [r13+2]; unsigned __int8
0x18005ad2d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005ad32  jmp     loc_18005AF73
0x18005ad37  lea     rax, [rbp+57h+hKey]
0x18005ad3b  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18005ad40  mov     r15d, 1
0x18005ad46  mov     r9d, r15d; samDesired
0x18005ad49  xor     r8d, r8d; ulOptions
0x18005ad4c  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18005ad50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ad57  call    cs:__imp_RegOpenKeyExW
0x18005ad5d  test    eax, eax
0x18005ad5f  jz      short loc_18005AD9F
0x18005ad61  lea     edi, [r15+1]
0x18005ad65  jg      short loc_18005AD6B
0x18005ad67  mov     ebx, eax
0x18005ad69  jmp     short loc_18005AD91
0x18005ad6b  cmp     eax, edi
0x18005ad6d  jnz     short loc_18005AD88
0x18005ad6f  lea     rdx, aNoTasksDefinit; "No tasks definitions stored.  Skipping."
0x18005ad76  mov     ecx, 4; unsigned __int8
0x18005ad7b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005ad80  mov     ebx, r13d
0x18005ad83  jmp     loc_18005AF73
0x18005ad88  movzx   ebx, ax
0x18005ad8b  or      ebx, 80070000h
0x18005ad91  mov     r8d, ebx
0x18005ad94  lea     rdx, aFailedToOpenTa; "Failed to open tasks definition key. Er"...
0x18005ad9b  mov     ecx, edi
0x18005ad9d  jmp     short loc_18005AD2D
0x18005ad9f  mov     [rsp+58h], r13; lpftLastWriteTime
0x18005ada4  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18005ada9  lea     rax, [rbp+57h+cbMaxValueLen]
0x18005adad  mov     [rsp+0D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18005adb2  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18005adb6  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18005adbb  mov     [rsp+0D0h+lpcValues], rdi; lpcValues
0x18005adc0  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18005adc5  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18005adca  mov     [rsp+0D0h+phkResult], r13; lpcSubKeys
0x18005adcf  xor     r9d, r9d; lpReserved
0x18005add2  xor     r8d, r8d; lpcchClass
0x18005add5  xor     edx, edx; lpClass
0x18005add7  mov     rcx, [rbp+57h+hKey]; hKey
0x18005addb  call    cs:__imp_RegQueryInfoKeyW
0x18005ade1  test    eax, eax
0x18005ade3  jz      short loc_18005ADFC
0x18005ade5  jg      short loc_18005ADEE
0x18005ade7  mov     ebx, eax
0x18005ade9  jmp     loc_18005AF73
0x18005adee  movzx   ebx, ax
0x18005adf1  or      ebx, 80070000h
0x18005adf7  jmp     loc_18005AF73
0x18005adfc  mov     r8d, [rdi]
0x18005adff  lea     rdx, aFoundDTasksToR; "Found %d tasks to restore."
0x18005ae06  mov     ecx, 4; unsigned __int8
0x18005ae0b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005ae10  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18005ae13  add     eax, r15d
0x18005ae16  mov     [rbp+57h+cbMaxValueNameLen], eax
0x18005ae19  mov     ecx, eax
0x18005ae1b  add     rcx, rcx; this
0x18005ae1e  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x18005ae23  mov     rsi, rax
0x18005ae26  test    rax, rax
0x18005ae29  jnz     short loc_18005AE35
0x18005ae2b  mov     ebx, 8007000Eh
0x18005ae30  jmp     loc_18005AF73
0x18005ae35  mov     ecx, [rbp+57h+cbMaxValueLen]; this
0x18005ae38  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x18005ae3d  mov     r14, rax
0x18005ae40  test    rax, rax
0x18005ae43  jz      short loc_18005AE2B
0x18005ae45  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18005ae48  mov     [rbp+57h+cchValueName], eax
0x18005ae4b  mov     eax, [rbp+57h+cbMaxValueLen]
0x18005ae4e  mov     [rbp+57h+cbData], eax
0x18005ae51  mov     [rbp+57h+dwIndex], r15d
0x18005ae55  lea     rax, [rbp+57h+cbData]
0x18005ae59  mov     [rsp+0D0h+lpcValues], rax; lpcbData
0x18005ae5e  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpData
0x18005ae63  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpType
0x18005ae68  mov     [rsp+0D0h+phkResult], r13; lpReserved
0x18005ae6d  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18005ae71  mov     r8, rsi; lpValueName
0x18005ae74  xor     edx, edx; dwIndex
0x18005ae76  mov     rcx, [rbp+57h+hKey]; hKey
0x18005ae7a  call    cs:__imp_RegEnumValueW
0x18005ae80  cmp     eax, 103h
0x18005ae85  jz      loc_18005AF73
0x18005ae8b  mov     edi, 2
0x18005ae90  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18005ae93  mov     [rbp+57h+cchValueName], ecx
0x18005ae96  mov     ecx, [rbp+57h+cbMaxValueLen]
0x18005ae99  mov     [rbp+57h+cbData], ecx
0x18005ae9c  test    eax, eax
0x18005ae9e  jz      short loc_18005AECB
0x18005aea0  jg      short loc_18005AEA6
0x18005aea2  mov     ebx, eax
0x18005aea4  jmp     short loc_18005AEAF
0x18005aea6  movzx   ebx, ax
0x18005aea9  or      ebx, 80070000h
0x18005aeaf  lea     r9d, [r15-1]
0x18005aeb3  mov     dword ptr [rsp+0D0h+phkResult], ebx
0x18005aeb7  mov     r8, [rbp+57h+lpSubKey]
0x18005aebb  lea     rdx, aCouldNotEnumer; "Could not enumerate the values under %s"...
0x18005aec2  mov     ecx, edi; unsigned __int8
0x18005aec4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005aec9  jmp     short loc_18005AF31
0x18005aecb  mov     byte ptr [rbp+57h+arg_0], r13b
0x18005aecf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005aed3  inc     rax
0x18005aed6  cmp     [r14+rax*2], r13w
0x18005aedb  jnz     short loc_18005AED3
0x18005aedd  inc     rax
0x18005aee0  lea     r13, [r14+rax*2]
0x18005aee4  mov     [rsp+0D0h+phkResult], r13
0x18005aee9  mov     r9, rsi
0x18005aeec  mov     r8, r14
0x18005aeef  lea     rdx, aFoundTaskWithF; "Found task with folder\\name\\definitio"...
0x18005aef6  mov     ecx, 4; unsigned __int8
0x18005aefb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005af00  mov     rdx, r14; psz
0x18005af03  lea     rcx, [rbp+57h+ppv]; ppv
0x18005af07  call    ?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::Initialize(ushort const *)
0x18005af0c  mov     r15d, eax
0x18005af0f  test    eax, eax
0x18005af11  jns     loc_18005AFB0
0x18005af17  mov     r8, r14
0x18005af1a  lea     rdx, aFailedToInitia_1; "Failed to initialize TasksHelper with t"...
0x18005af21  mov     r9d, r15d
0x18005af24  mov     ecx, edi; unsigned __int8
0x18005af26  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005af2b  mov     ebx, r15d
0x18005af2e  xor     r13d, r13d
0x18005af31  mov     eax, [rbp+57h+dwIndex]
0x18005af34  mov     edx, eax; dwIndex
0x18005af36  inc     eax
0x18005af38  mov     [rbp+57h+dwIndex], eax
0x18005af3b  lea     rcx, [rbp+57h+cbData]
0x18005af3f  mov     [rsp+0D0h+lpcValues], rcx; lpcbData
0x18005af44  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpData
0x18005af49  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpType
0x18005af4e  mov     [rsp+0D0h+phkResult], r13; lpReserved
0x18005af53  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18005af57  mov     r8, rsi; lpValueName
0x18005af5a  mov     rcx, [rbp+57h+hKey]; hKey
0x18005af5e  call    cs:__imp_RegEnumValueW
0x18005af64  cmp     eax, 103h
0x18005af69  mov     r15d, [rbp+57h+dwIndex]
0x18005af6d  jnz     loc_18005AE90
0x18005af73  mov     rcx, rsi; this
0x18005af76  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18005af7b  mov     rcx, r14; this
0x18005af7e  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18005af83  mov     rcx, [rbp+57h+hKey]; hKey
0x18005af87  test    rcx, rcx
0x18005af8a  jz      short loc_18005AF93
0x18005af8c  call    cs:__imp_RegCloseKey
0x18005af92  nop
0x18005af93  lea     rcx, [rbp+57h+ppv]; this
0x18005af97  call    ??1TasksHelper@WaasMedic@@QEAA@XZ; WaasMedic::TasksHelper::~TasksHelper(void)
0x18005af9c  mov     eax, ebx
0x18005af9e  add     rsp, 0A0h
0x18005afa5  pop     r15
0x18005afa7  pop     r14
0x18005afa9  pop     r13
0x18005afab  pop     rdi
0x18005afac  pop     rsi
0x18005afad  pop     rbx
0x18005afae  pop     rbp
0x18005afaf  retn
0x18005afb0  xor     r15d, r15d
0x18005afb3  mov     [rbp+57h+arg_18], r15b
0x18005afb7  lea     r8, [rbp+57h+arg_18]; bool *
0x18005afbb  mov     rdx, rsi; unsigned __int16 *
0x18005afbe  lea     rcx, [rbp+57h+ppv]; this
0x18005afc2  call    ?TaskExists@TasksHelper@WaasMedic@@QEAAJPEBGPEA_N@Z; WaasMedic::TasksHelper::TaskExists(ushort const *,bool *)
0x18005afc7  test    eax, eax
0x18005afc9  jns     short loc_18005AFE6
0x18005afcb  mov     r9d, eax
0x18005afce  mov     r8, rsi
0x18005afd1  lea     rdx, aEncounteredFai; "Encountered failure while looking for t"...
0x18005afd8  lea     ecx, [r15+3]; unsigned __int8
0x18005afdc  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005afe1  jmp     loc_18005AF2E
0x18005afe6  cmp     [rbp+57h+arg_18], r15b
0x18005afea  jz      short loc_18005B04D
0x18005afec  lea     rax, [rbp+57h+arg_0]
0x18005aff0  mov     [rsp+0D0h+phkResult], rax; bool *
0x18005aff5  mov     r8, r13; unsigned __int16 *
0x18005aff8  mov     rdx, rsi; unsigned __int16 *
0x18005affb  lea     rcx, [rbp+57h+ppv]; this
0x18005afff  call    ?IsTaskConfiguredProperly@TasksHelper@WaasMedic@@QEAAJPEBG0HPEA_N@Z; WaasMedic::TasksHelper::IsTaskConfiguredProperly(ushort const *,ushort const *,int,bool *)
0x18005b004  mov     r15d, eax
0x18005b007  mov     r8, rsi
0x18005b00a  test    eax, eax
0x18005b00c  jns     short loc_18005B01A
0x18005b00e  lea     rdx, aFailedToInspec; "Failed to inspect the task: %s. Error c"...
0x18005b015  jmp     loc_18005AF21
0x18005b01a  lea     r9, aBe; "be"
0x18005b021  lea     rax, aNotBe; "not be"
0x18005b028  xor     r15d, r15d
0x18005b02b  cmp     byte ptr [rbp+57h+arg_0], r15b
0x18005b02f  cmovz   r9, rax
0x18005b033  lea     rdx, aTaskSWasFoundT; "Task '%s' was found to %s correctly con"...
0x18005b03a  lea     ecx, [r15+4]; unsigned __int8
0x18005b03e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005b043  cmp     byte ptr [rbp+57h+arg_0], r15b
0x18005b047  jnz     loc_18005AF2E
0x18005b04d  mov     rax, [rbp+57h+arg_10]
0x18005b051  mov     byte ptr [rax], 1
0x18005b054  cmp     [rbp+57h+arg_8], r15b
0x18005b058  jz      loc_18005AF2E
0x18005b05e  mov     r8, r13; unsigned __int16 *
0x18005b061  mov     rdx, rsi; unsigned __int16 *
0x18005b064  lea     rcx, [rbp+57h+ppv]; this
0x18005b068  call    ?CreateOrUpdateTask@TasksHelper@WaasMedic@@QEAAJPEBG00@Z; WaasMedic::TasksHelper::CreateOrUpdateTask(ushort const *,ushort const *,ushort const *)
0x18005b06d  xor     r13d, r13d
0x18005b070  test    eax, eax
0x18005b072  jns     loc_18005AF31
0x18005b078  mov     r9d, eax
0x18005b07b  mov     r8, rsi
0x18005b07e  lea     rdx, aFailedToCreate_22; "Failed to create or update the task: %s"...
0x18005b085  mov     ecx, edi; unsigned __int8
0x18005b087  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005b08c  jmp     loc_18005AF31
```
