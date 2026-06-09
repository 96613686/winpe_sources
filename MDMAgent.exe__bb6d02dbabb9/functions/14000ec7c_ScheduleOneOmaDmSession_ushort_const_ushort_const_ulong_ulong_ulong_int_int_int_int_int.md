# ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)

- ea: `0x14000ec7c`
- end: `0x14000ee3f`
- name: `?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z`
- size: `451`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140010cf0`
- `0x1400112b0`

## callees

- `0x1400029c0`
- `0x140007628`
- `0x140009268`
- `0x14000a03c`
- `0x14000a134`
- `0x14000ec7c`
- `0x14000ee48`
- `0x14000f220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000ee13`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000ee13`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ed07`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000eda8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ed07`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000eda8`

## string_xrefs

- `0x14000ed90`: `21CoCreateTaskScheduler`

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSession(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10)
{
  const wchar_t *v14; // rax
  const unsigned __int16 *v15; // r8
  char *v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  int lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  int v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+48h] [rbp-B8h]
  int Data; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+64h] [rbp-9Ch] BYREF
  LPVOID v27; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v28[264]; // [rsp+70h] [rbp-90h] BYREF

  Data = 0;
  v26 = 0;
  if ( !a4 )
    return 0;
  Data = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v26, (unsigned int)a2);
  if ( Data >= 0 )
  {
    if ( a3 )
    {
      v14 = L"/o \"%s\" /c /bu";
      v15 = L"/o \"%s\" /c";
    }
    else
    {
      v14 = L"/o \"%s\" /c /mu";
      v15 = L"/o \"%s\" /c /b";
    }
    if ( a10 )
      v15 = v14;
    Data = StringCchPrintfW(v28, 0x104u, v15, a1);
    if ( Data >= 0 )
    {
      v27 = 0;
      Data = CoCreateTaskScheduler(v17, v16, &v27);
      if ( Data >= 0 )
      {
        if ( a6 )
          v18 = ScheduleOneOmaDmSessionMaintenanceCycle(a2, a1, lpData, cbData);
        else
          v18 = ScheduleOneOmaDmSessionClient(a2, a1, a5, cbData, v28, v22, v23, v24, a9);
        Data = v18;
      }
      else
      {
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"21CoCreateTaskScheduler", 4u, &Data, 4u);
      }
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v27);
    }
  }
  else
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"CoInitializeEx", 4u, &Data, 4u);
  }
  v19 = Data;
  if ( v26 )
    CoUninitialize();
  return v19;
}

```

## disassembly

```asm
0x14000ec7c  push    rbp
0x14000ec7e  push    rbx
0x14000ec7f  push    rsi
0x14000ec80  push    rdi
0x14000ec81  push    r14
0x14000ec83  lea     rbp, [rsp-190h]
0x14000ec8b  sub     rsp, 290h
0x14000ec92  mov     rax, cs:__security_cookie
0x14000ec99  xor     rax, rsp
0x14000ec9c  mov     [rbp+1B0h+var_30], rax
0x14000eca3  mov     [rsp+2B0h+Data], 0
0x14000ecab  mov     r14d, r9d
0x14000ecae  mov     [rsp+2B0h+var_24C], 0
0x14000ecb6  mov     edi, r8d
0x14000ecb9  mov     rsi, rdx
0x14000ecbc  mov     rbx, rcx
0x14000ecbf  test    r9d, r9d
0x14000ecc2  jnz     short loc_14000ECCB
0x14000ecc4  xor     eax, eax
0x14000ecc6  jmp     loc_14000EE21
0x14000eccb  lea     rcx, [rsp+2B0h+var_24C]; this
0x14000ecd0  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000ecd5  mov     [rsp+2B0h+Data], eax
0x14000ecd9  test    eax, eax
0x14000ecdb  jns     short loc_14000ED18
0x14000ecdd  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14000ece4  lea     rax, [rsp+2B0h+Data]
0x14000ece9  mov     r9d, 4; dwType
0x14000ecef  lea     r8, aCoinitializeex; "CoInitializeEx"
0x14000ecf6  mov     [rsp+2B0h+cbData], r9d; cbData
0x14000ecfb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000ed02  mov     [rsp+2B0h+lpData], rax; lpData
0x14000ed07  call    cs:__imp_RegSetKeyValueW
0x14000ed0e  nop     dword ptr [rax+rax+00h]
0x14000ed13  jmp     loc_14000EE08
0x14000ed18  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x14000ed1d  mov     r9, rbx
0x14000ed20  mov     edx, 104h; unsigned __int64
0x14000ed25  test    edi, edi
0x14000ed27  jz      short loc_14000ED39
0x14000ed29  lea     rax, aOSCBu; "/o \"%s\" /c /bu"
0x14000ed30  lea     r8, aOSC; "/o \"%s\" /c"
0x14000ed37  jmp     short loc_14000ED47
0x14000ed39  lea     rax, aOSCMu; "/o \"%s\" /c /mu"
0x14000ed40  lea     r8, aOSCB; "/o \"%s\" /c /b"
0x14000ed47  cmp     [rbp+1B0h+arg_48], 0
0x14000ed4e  cmovnz  r8, rax; unsigned __int16 *
0x14000ed52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000ed57  mov     [rsp+2B0h+Data], eax
0x14000ed5b  test    eax, eax
0x14000ed5d  js      loc_14000EE08
0x14000ed63  lea     r8, [rsp+2B0h+var_248]
0x14000ed68  mov     [rsp+2B0h+var_248], 0
0x14000ed71  call    CoCreateTaskScheduler
0x14000ed76  mov     [rsp+2B0h+Data], eax
0x14000ed7a  test    eax, eax
0x14000ed7c  jns     short loc_14000EDB6
0x14000ed7e  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14000ed85  lea     rax, [rsp+2B0h+Data]
0x14000ed8a  mov     r9d, 4; dwType
0x14000ed90  lea     r8, a21cocreatetask; "21CoCreateTaskScheduler"
0x14000ed97  mov     [rsp+2B0h+cbData], r9d; cbData
0x14000ed9c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000eda3  mov     [rsp+2B0h+lpData], rax; lpData
0x14000eda8  call    cs:__imp_RegSetKeyValueW
0x14000edaf  nop     dword ptr [rax+rax+00h]
0x14000edb4  jmp     short loc_14000EDFE
0x14000edb6  cmp     [rbp+1B0h+arg_28], 0
0x14000edbd  mov     rdx, rbx; unsigned __int16 *
0x14000edc0  mov     rcx, rsi; unsigned __int16 *
0x14000edc3  jz      short loc_14000EDD1
0x14000edc5  lea     r9, [rsp+2B0h+var_240]
0x14000edca  call    ScheduleOneOmaDmSessionMaintenanceCycle
0x14000edcf  jmp     short loc_14000EDFA
0x14000edd1  mov     eax, [rbp+1B0h+arg_40]
0x14000edd7  mov     r9d, r14d
0x14000edda  mov     [rsp+2B0h+var_260], eax; int
0x14000edde  mov     r8d, edi
0x14000ede1  lea     rax, [rsp+2B0h+var_240]
0x14000ede6  mov     [rsp+2B0h+var_280], rax; unsigned __int16 *
0x14000edeb  mov     eax, [rbp+1B0h+arg_20]
0x14000edf1  mov     dword ptr [rsp+2B0h+lpData], eax; int
0x14000edf5  call    ScheduleOneOmaDmSessionClient
0x14000edfa  mov     [rsp+2B0h+Data], eax
0x14000edfe  lea     rcx, [rsp+2B0h+var_248]
0x14000ee03  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x14000ee08  cmp     [rsp+2B0h+var_24C], 0
0x14000ee0d  mov     ebx, [rsp+2B0h+Data]
0x14000ee11  jz      short loc_14000EE1F
0x14000ee13  call    cs:__imp_CoUninitialize
0x14000ee1a  nop     dword ptr [rax+rax+00h]
0x14000ee1f  mov     eax, ebx
0x14000ee21  mov     rcx, [rbp+1B0h+var_30]
0x14000ee28  xor     rcx, rsp; StackCookie
0x14000ee2b  call    __security_check_cookie
0x14000ee30  add     rsp, 290h
0x14000ee37  pop     r14
0x14000ee39  pop     rdi
0x14000ee3a  pop     rsi
0x14000ee3b  pop     rbx
0x14000ee3c  pop     rbp
0x14000ee3d  retn
```
