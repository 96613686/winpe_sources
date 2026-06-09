# ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)

- ea: `0x14000e530`
- end: `0x14000e6e0`
- name: `?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z`
- size: `432`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, unsigned int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400104c0`
- `0x140010a68`

## callees

- `0x140002930`
- `0x140007368`
- `0x140008e48`
- `0x140009bfc`
- `0x140009cd8`
- `0x14000e530`
- `0x14000e6e8`
- `0x14000eaa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e6bb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e6bb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000e5bb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000e656`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000e5bb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000e656`

## string_xrefs

- `0x14000e63e`: `21CoCreateTaskScheduler`

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSession(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10)
{
  const wchar_t *v15; // rax
  const unsigned __int16 *v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  int v20; // eax
  unsigned int v21; // ebx
  LPCVOID lpData; // [rsp+20h] [rbp-E0h]
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  int v25; // [rsp+40h] [rbp-C0h]
  int v26; // [rsp+48h] [rbp-B8h]
  int Data; // [rsp+60h] [rbp-A0h] BYREF
  int v28; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v30[264]; // [rsp+70h] [rbp-90h] BYREF

  Data = 0;
  v28 = 0;
  if ( !a4 )
    return 0;
  Data = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v28, (unsigned int)a2);
  if ( Data >= 0 )
  {
    if ( a3 )
    {
      v15 = L"/o \"%s\" /c /bu";
      v16 = L"/o \"%s\" /c";
    }
    else
    {
      v15 = L"/o \"%s\" /c /mu";
      v16 = L"/o \"%s\" /c /b";
    }
    if ( a10 )
      v16 = v15;
    Data = StringCchPrintfW(v30, 0x104u, v16, a1);
    if ( Data >= 0 )
    {
      v29 = 0;
      Data = CoCreateTaskScheduler(v18, v17, &v29);
      if ( Data >= 0 )
      {
        if ( a6 )
          v20 = ScheduleOneOmaDmSessionMaintenanceCycle(a2, a1, v19, v30, (__int64)lpData, cbData);
        else
          v20 = ScheduleOneOmaDmSessionClient(a2, a1, a3, a4, a5, cbData, v30, v24, v25, v26, a9);
        Data = v20;
      }
      else
      {
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"21CoCreateTaskScheduler", 4u, &Data, 4u);
      }
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v29);
    }
  }
  else
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"CoInitializeEx", 4u, &Data, 4u);
  }
  v21 = Data;
  if ( v28 )
    CoUninitialize();
  return v21;
}

```

## disassembly

```asm
0x14000e530  push    rbp
0x14000e532  push    rbx
0x14000e533  push    rsi
0x14000e534  push    rdi
0x14000e535  push    r14
0x14000e537  lea     rbp, [rsp-190h]
0x14000e53f  sub     rsp, 290h
0x14000e546  mov     rax, cs:__security_cookie
0x14000e54d  xor     rax, rsp
0x14000e550  mov     [rbp+1B0h+var_30], rax
0x14000e557  mov     [rsp+2B0h+Data], 0
0x14000e55f  mov     r14d, r9d
0x14000e562  mov     [rsp+2B0h+var_24C], 0
0x14000e56a  mov     edi, r8d
0x14000e56d  mov     rsi, rdx
0x14000e570  mov     rbx, rcx
0x14000e573  test    r9d, r9d
0x14000e576  jnz     short loc_14000E57F
0x14000e578  xor     eax, eax
0x14000e57a  jmp     loc_14000E6C3
0x14000e57f  lea     rcx, [rsp+2B0h+var_24C]; this
0x14000e584  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000e589  mov     [rsp+2B0h+Data], eax
0x14000e58d  test    eax, eax
0x14000e58f  jns     short loc_14000E5C6
0x14000e591  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14000e598  lea     rax, [rsp+2B0h+Data]
0x14000e59d  mov     r9d, 4; dwType
0x14000e5a3  lea     r8, aCoinitializeex; "CoInitializeEx"
0x14000e5aa  mov     dword ptr [rsp+2B0h+cbData], r9d; cbData
0x14000e5af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e5b6  mov     [rsp+2B0h+lpData], rax; lpData
0x14000e5bb  call    cs:__imp_RegSetKeyValueW
0x14000e5c1  jmp     loc_14000E6B0
0x14000e5c6  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x14000e5cb  mov     r9, rbx
0x14000e5ce  mov     edx, 104h; unsigned __int64
0x14000e5d3  test    edi, edi
0x14000e5d5  jz      short loc_14000E5E7
0x14000e5d7  lea     rax, aOSCBu; "/o \"%s\" /c /bu"
0x14000e5de  lea     r8, aOSC; "/o \"%s\" /c"
0x14000e5e5  jmp     short loc_14000E5F5
0x14000e5e7  lea     rax, aOSCMu; "/o \"%s\" /c /mu"
0x14000e5ee  lea     r8, aOSCB; "/o \"%s\" /c /b"
0x14000e5f5  cmp     [rbp+1B0h+arg_48], 0
0x14000e5fc  cmovnz  r8, rax; unsigned __int16 *
0x14000e600  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000e605  mov     [rsp+2B0h+Data], eax
0x14000e609  test    eax, eax
0x14000e60b  js      loc_14000E6B0
0x14000e611  lea     r8, [rsp+2B0h+var_248]
0x14000e616  mov     [rsp+2B0h+var_248], 0
0x14000e61f  call    CoCreateTaskScheduler
0x14000e624  mov     [rsp+2B0h+Data], eax
0x14000e628  test    eax, eax
0x14000e62a  jns     short loc_14000E65E
0x14000e62c  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14000e633  lea     rax, [rsp+2B0h+Data]
0x14000e638  mov     r9d, 4; dwType
0x14000e63e  lea     r8, a21cocreatetask; "21CoCreateTaskScheduler"
0x14000e645  mov     dword ptr [rsp+2B0h+cbData], r9d; cbData
0x14000e64a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e651  mov     [rsp+2B0h+lpData], rax; lpData
0x14000e656  call    cs:__imp_RegSetKeyValueW
0x14000e65c  jmp     short loc_14000E6A6
0x14000e65e  cmp     [rbp+1B0h+arg_28], 0
0x14000e665  mov     rdx, rbx; unsigned __int16 *
0x14000e668  mov     rcx, rsi; unsigned __int16 *
0x14000e66b  jz      short loc_14000E679
0x14000e66d  lea     r9, [rsp+2B0h+var_240]
0x14000e672  call    ScheduleOneOmaDmSessionMaintenanceCycle
0x14000e677  jmp     short loc_14000E6A2
0x14000e679  mov     eax, [rbp+1B0h+arg_40]
0x14000e67f  mov     r9d, r14d
0x14000e682  mov     [rsp+2B0h+var_260], eax; int
0x14000e686  mov     r8d, edi
0x14000e689  lea     rax, [rsp+2B0h+var_240]
0x14000e68e  mov     [rsp+2B0h+var_280], rax; unsigned __int16 *
0x14000e693  mov     eax, [rbp+1B0h+arg_20]
0x14000e699  mov     dword ptr [rsp+2B0h+lpData], eax; int
0x14000e69d  call    ScheduleOneOmaDmSessionClient
0x14000e6a2  mov     [rsp+2B0h+Data], eax
0x14000e6a6  lea     rcx, [rsp+2B0h+var_248]
0x14000e6ab  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000e6b0  cmp     [rsp+2B0h+var_24C], 0
0x14000e6b5  mov     ebx, [rsp+2B0h+Data]
0x14000e6b9  jz      short loc_14000E6C1
0x14000e6bb  call    cs:__imp_CoUninitialize
0x14000e6c1  mov     eax, ebx
0x14000e6c3  mov     rcx, [rbp+1B0h+var_30]
0x14000e6ca  xor     rcx, rsp; StackCookie
0x14000e6cd  call    __security_check_cookie
0x14000e6d2  add     rsp, 290h
0x14000e6d9  pop     r14
0x14000e6db  pop     rdi
0x14000e6dc  pop     rsi
0x14000e6dd  pop     rbx
0x14000e6de  pop     rbp
0x14000e6df  retn
```
