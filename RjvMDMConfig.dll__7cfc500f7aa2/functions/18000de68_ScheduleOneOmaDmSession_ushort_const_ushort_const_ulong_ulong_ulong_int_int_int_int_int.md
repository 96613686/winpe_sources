# ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)

- ea: `0x18000de68`
- end: `0x18000e02b`
- name: `?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z`
- size: `451`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010340`
- `0x180010804`

## callees

- `0x180001c60`
- `0x1800051d8`
- `0x180007364`
- `0x1800085c8`
- `0x1800086c4`
- `0x18000de68`
- `0x18000e034`
- `0x18000e40c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000def3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000df94`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000def3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000df94`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000dfff`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000dfff`

## string_xrefs

- `0x18000df7c`: `21CoCreateTaskScheduler`

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSession(
        const unsigned __int16 *a1,
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
  LPCVOID lpData; // [rsp+20h] [rbp-E0h]
  __int64 cbData; // [rsp+28h] [rbp-D8h]
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
          v18 = ScheduleOneOmaDmSessionMaintenanceCycle(a2, (__int64)lpData, cbData);
        else
          v18 = ScheduleOneOmaDmSessionClient(a2, a5, cbData, (__int64)v28, v22, v23, v24, a9);
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
0x18000de68  push    rbp
0x18000de6a  push    rbx
0x18000de6b  push    rsi
0x18000de6c  push    rdi
0x18000de6d  push    r14
0x18000de6f  lea     rbp, [rsp-190h]
0x18000de77  sub     rsp, 290h
0x18000de7e  mov     rax, cs:__security_cookie
0x18000de85  xor     rax, rsp
0x18000de88  mov     [rbp+1B0h+var_30], rax
0x18000de8f  mov     [rsp+2B0h+Data], 0
0x18000de97  mov     r14d, r9d
0x18000de9a  mov     [rsp+2B0h+var_24C], 0
0x18000dea2  mov     edi, r8d
0x18000dea5  mov     rsi, rdx
0x18000dea8  mov     rbx, rcx
0x18000deab  test    r9d, r9d
0x18000deae  jnz     short loc_18000DEB7
0x18000deb0  xor     eax, eax
0x18000deb2  jmp     loc_18000E00D
0x18000deb7  lea     rcx, [rsp+2B0h+var_24C]; this
0x18000debc  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x18000dec1  mov     [rsp+2B0h+Data], eax
0x18000dec5  test    eax, eax
0x18000dec7  jns     short loc_18000DF04
0x18000dec9  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18000ded0  lea     rax, [rsp+2B0h+Data]
0x18000ded5  mov     r9d, 4; dwType
0x18000dedb  lea     r8, aCoinitializeex; "CoInitializeEx"
0x18000dee2  mov     dword ptr [rsp+2B0h+cbData], r9d; cbData
0x18000dee7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000deee  mov     [rsp+2B0h+lpData], rax; lpData
0x18000def3  call    cs:__imp_RegSetKeyValueW
0x18000defa  nop     dword ptr [rax+rax+00h]
0x18000deff  jmp     loc_18000DFF4
0x18000df04  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x18000df09  mov     r9, rbx
0x18000df0c  mov     edx, 104h; unsigned __int64
0x18000df11  test    edi, edi
0x18000df13  jz      short loc_18000DF25
0x18000df15  lea     rax, aOSCBu; "/o \"%s\" /c /bu"
0x18000df1c  lea     r8, aOSC; "/o \"%s\" /c"
0x18000df23  jmp     short loc_18000DF33
0x18000df25  lea     rax, aOSCMu; "/o \"%s\" /c /mu"
0x18000df2c  lea     r8, aOSCB; "/o \"%s\" /c /b"
0x18000df33  cmp     [rbp+1B0h+arg_48], 0
0x18000df3a  cmovnz  r8, rax; unsigned __int16 *
0x18000df3e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000df43  mov     [rsp+2B0h+Data], eax
0x18000df47  test    eax, eax
0x18000df49  js      loc_18000DFF4
0x18000df4f  lea     r8, [rsp+2B0h+var_248]
0x18000df54  mov     [rsp+2B0h+var_248], 0
0x18000df5d  call    CoCreateTaskScheduler
0x18000df62  mov     [rsp+2B0h+Data], eax
0x18000df66  test    eax, eax
0x18000df68  jns     short loc_18000DFA2
0x18000df6a  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18000df71  lea     rax, [rsp+2B0h+Data]
0x18000df76  mov     r9d, 4; dwType
0x18000df7c  lea     r8, a21cocreatetask; "21CoCreateTaskScheduler"
0x18000df83  mov     dword ptr [rsp+2B0h+cbData], r9d; cbData
0x18000df88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000df8f  mov     [rsp+2B0h+lpData], rax; lpData
0x18000df94  call    cs:__imp_RegSetKeyValueW
0x18000df9b  nop     dword ptr [rax+rax+00h]
0x18000dfa0  jmp     short loc_18000DFEA
0x18000dfa2  cmp     [rbp+1B0h+arg_28], 0
0x18000dfa9  mov     rdx, rbx
0x18000dfac  mov     rcx, rsi; unsigned __int16 *
0x18000dfaf  jz      short loc_18000DFBD
0x18000dfb1  lea     r9, [rsp+2B0h+var_240]
0x18000dfb6  call    ScheduleOneOmaDmSessionMaintenanceCycle
0x18000dfbb  jmp     short loc_18000DFE6
0x18000dfbd  mov     eax, [rbp+1B0h+arg_40]
0x18000dfc3  mov     r9d, r14d
0x18000dfc6  mov     [rsp+2B0h+var_260], eax; int
0x18000dfca  mov     r8d, edi
0x18000dfcd  lea     rax, [rsp+2B0h+var_240]
0x18000dfd2  mov     [rsp+2B0h+var_280], rax; __int64
0x18000dfd7  mov     eax, [rbp+1B0h+arg_20]
0x18000dfdd  mov     dword ptr [rsp+2B0h+lpData], eax; int
0x18000dfe1  call    ScheduleOneOmaDmSessionClient
0x18000dfe6  mov     [rsp+2B0h+Data], eax
0x18000dfea  lea     rcx, [rsp+2B0h+var_248]
0x18000dfef  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x18000dff4  cmp     [rsp+2B0h+var_24C], 0
0x18000dff9  mov     ebx, [rsp+2B0h+Data]
0x18000dffd  jz      short loc_18000E00B
0x18000dfff  call    cs:__imp_CoUninitialize
0x18000e006  nop     dword ptr [rax+rax+00h]
0x18000e00b  mov     eax, ebx
0x18000e00d  mov     rcx, [rbp+1B0h+var_30]
0x18000e014  xor     rcx, rsp; StackCookie
0x18000e017  call    __security_check_cookie
0x18000e01c  add     rsp, 290h
0x18000e023  pop     r14
0x18000e025  pop     rdi
0x18000e026  pop     rsi
0x18000e027  pop     rbx
0x18000e028  pop     rbp
0x18000e029  retn
```
