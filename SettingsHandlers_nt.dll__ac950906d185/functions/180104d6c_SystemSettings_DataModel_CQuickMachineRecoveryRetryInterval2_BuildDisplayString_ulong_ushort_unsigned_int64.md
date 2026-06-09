# SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval2::BuildDisplayString(ulong,ushort *,unsigned __int64)

- ea: `0x180104d6c`
- end: `0x180104f1b`
- name: `?BuildDisplayString@CQuickMachineRecoveryRetryInterval2@DataModel@SystemSettings@@AEAAJKPEAG_K@Z`
- size: `431`
- prototype: `int(SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval2 *__hidden this, unsigned int, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180106070`
- `0x180106bb0`

## callees

- `0x180019a20`
- `0x18001a57c`
- `0x18001a608`
- `0x18001a64c`
- `0x18004d1ac`
- `0x180104d6c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104d8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104e02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104e50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104efc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104d8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104e02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104e50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104efc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180104db8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180104ea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180104db8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180104ea0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval2::BuildDisplayString(
        SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval2 *this,
        unsigned int a2,
        unsigned __int16 *a3,
        HSTRING a4)
{
  HSTRING *v6; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // ebx
  HSTRING *v12; // r8
  int ResourceStringById; // edi
  __int64 v14; // rdx
  HSTRING *v15; // r8
  const unsigned __int16 *v16; // rax
  int v18; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+48h] [rbp+20h] BYREF

  string = a4;
  if ( !a2 )
  {
    WindowsDeleteString(0);
    string = 0;
    SystemSettings::DataModel::GetResourceStringById(
      (SystemSettings::DataModel *)L"SystemSettings_Misc_QuickMachineRecovery_RetryInterval_Once",
      &string,
      v6);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v8 = StringCchCopyW(a3, 0x104u, StringRawBuffer);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 919;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\quickmachinerecovery.cpp",
        (const char *)(unsigned int)v8,
        v18);
      goto LABEL_19;
    }
LABEL_18:
    v9 = 0;
    goto LABEL_19;
  }
  if ( a2 >= 0x3C && (v11 = a2 / 0x3C, a2 == 60 * (a2 / 0x3C)) )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Misc_QuickMachineRecovery_RetryInterval_HourlyValue",
                           &string,
                           v12);
    if ( ResourceStringById < 0 )
    {
      v14 = 935;
      goto LABEL_8;
    }
  }
  else
  {
    WindowsDeleteString(0);
    string = 0;
    v8 = SystemSettings::DataModel::GetResourceStringById(
           (SystemSettings::DataModel *)L"SystemSettings_Misc_QuickMachineRecovery_RetryInterval_MinuteValue",
           &string,
           v15);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 929;
      goto LABEL_11;
    }
    v11 = a2;
  }
  v16 = WindowsGetStringRawBuffer(string, 0);
  ResourceStringById = StringCchPrintfW(a3, 0x104u, v16, v11);
  if ( ResourceStringById >= 0 )
  {
    if ( v11 != 1 )
    {
      v8 = StringCchCatW(a3, 0x104u, L"s");
      v9 = v8;
      if ( v8 < 0 )
      {
        v10 = 944;
        goto LABEL_11;
      }
    }
    goto LABEL_18;
  }
  v14 = 939;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\quickmachinerecovery.cpp",
    (const char *)(unsigned int)ResourceStringById,
    v18);
  v9 = ResourceStringById;
LABEL_19:
  WindowsDeleteString(string);
  return v9;
}

```

## disassembly

```asm
0x180104d6c  mov     [rsp+arg_0], rbx
0x180104d71  mov     [rsp+arg_8], rbp
0x180104d76  mov     [rsp+string], r9
0x180104d7b  push    rdi; int
0x180104d7c  sub     rsp, 20h
0x180104d80  mov     rbp, r8
0x180104d83  mov     edi, edx
0x180104d85  test    edx, edx
0x180104d87  jnz     short loc_180104DE8
0x180104d89  xor     ecx, ecx; string
0x180104d8b  call    cs:__imp_WindowsDeleteString
0x180104d92  nop     dword ptr [rax+rax+00h]
0x180104d97  mov     [rsp+28h+string], 0
0x180104da0  lea     rdx, [rsp+28h+string]; HSTRING *
0x180104da5  lea     rcx, aSystemsettings_128; "SystemSettings_Misc_QuickMachineRecover"...
0x180104dac  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180104db1  xor     edx, edx; length
0x180104db3  mov     rcx, [rsp+28h+string]; string
0x180104db8  call    cs:__imp_WindowsGetStringRawBuffer
0x180104dbf  nop     dword ptr [rax+rax+00h]
0x180104dc4  mov     r8, rax; unsigned __int16 *
0x180104dc7  mov     edx, 104h; unsigned __int64
0x180104dcc  mov     rcx, rbp; unsigned __int16 *
0x180104dcf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180104dd4  mov     ebx, eax
0x180104dd6  test    eax, eax
0x180104dd8  jns     loc_180104EF5
0x180104dde  mov     edx, 397h
0x180104de3  jmp     loc_180104E81
0x180104de8  cmp     edi, 3Ch ; '<'
0x180104deb  jb      short loc_180104E4E
0x180104ded  mov     eax, 88888889h
0x180104df2  mul     edi
0x180104df4  mov     ebx, edx
0x180104df6  shr     ebx, 5
0x180104df9  imul    ecx, ebx, 3Ch ; '<'
0x180104dfc  cmp     edi, ecx
0x180104dfe  jnz     short loc_180104E4E
0x180104e00  xor     ecx, ecx; string
0x180104e02  call    cs:__imp_WindowsDeleteString
0x180104e09  nop     dword ptr [rax+rax+00h]
0x180104e0e  mov     [rsp+28h+string], 0
0x180104e17  lea     rdx, [rsp+28h+string]; HSTRING *
0x180104e1c  lea     rcx, aSystemsettings_958; "SystemSettings_Misc_QuickMachineRecover"...
0x180104e23  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180104e28  mov     edi, eax
0x180104e2a  test    eax, eax
0x180104e2c  jns     short loc_180104E99
0x180104e2e  mov     edx, 3A7h; void *
0x180104e33  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x180104e3a  mov     r9d, edi; char *
0x180104e3d  mov     rcx, [rsp+28h]; this
0x180104e42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104e47  mov     ebx, edi
0x180104e49  jmp     loc_180104EF7
0x180104e4e  xor     ecx, ecx; string
0x180104e50  call    cs:__imp_WindowsDeleteString
0x180104e57  nop     dword ptr [rax+rax+00h]
0x180104e5c  mov     [rsp+28h+string], 0
0x180104e65  lea     rdx, [rsp+28h+string]; HSTRING *
0x180104e6a  lea     rcx, aSystemsettings_678; "SystemSettings_Misc_QuickMachineRecover"...
0x180104e71  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180104e76  mov     ebx, eax
0x180104e78  test    eax, eax
0x180104e7a  jns     short loc_180104E97
0x180104e7c  mov     edx, 3A1h; void *
0x180104e81  mov     rcx, [rsp+28h]; this
0x180104e86  mov     r9d, eax; char *
0x180104e89  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x180104e90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104e95  jmp     short loc_180104EF7
0x180104e97  mov     ebx, edi
0x180104e99  xor     edx, edx; length
0x180104e9b  mov     rcx, [rsp+28h+string]; string
0x180104ea0  call    cs:__imp_WindowsGetStringRawBuffer
0x180104ea7  nop     dword ptr [rax+rax+00h]
0x180104eac  mov     r9d, ebx
0x180104eaf  mov     r8, rax; unsigned __int16 *
0x180104eb2  mov     edx, 104h; unsigned __int64
0x180104eb7  mov     rcx, rbp; unsigned __int16 *
0x180104eba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180104ebf  mov     edi, eax
0x180104ec1  test    eax, eax
0x180104ec3  jns     short loc_180104ECF
0x180104ec5  mov     edx, 3ABh
0x180104eca  jmp     loc_180104E33
0x180104ecf  cmp     ebx, 1
0x180104ed2  jz      short loc_180104EF5
0x180104ed4  lea     r8, aS_3; "s"
0x180104edb  mov     edx, 104h; unsigned __int64
0x180104ee0  mov     rcx, rbp; unsigned __int16 *
0x180104ee3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180104ee8  mov     ebx, eax
0x180104eea  test    eax, eax
0x180104eec  jns     short loc_180104EF5
0x180104eee  mov     edx, 3B0h
0x180104ef3  jmp     short loc_180104E81
0x180104ef5  xor     ebx, ebx
0x180104ef7  mov     rcx, [rsp+28h+string]; string
0x180104efc  call    cs:__imp_WindowsDeleteString
0x180104f03  nop     dword ptr [rax+rax+00h]
0x180104f08  mov     eax, ebx
0x180104f0a  mov     rbx, [rsp+28h+arg_0]
0x180104f0f  mov     rbp, [rsp+28h+arg_8]
0x180104f14  add     rsp, 20h
0x180104f18  pop     rdi
0x180104f19  retn
```
