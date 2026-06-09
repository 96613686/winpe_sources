# Registry::GetValue<Microsoft::WRL::Wrappers::HString>(HKEY__ *,ushort const *,ushort const *,Microsoft::WRL::Wrappers::HString &&)

- ea: `0x180019d84`
- end: `0x180019f08`
- name: `??$GetValue@VHString@Wrappers@WRL@Microsoft@@@Registry@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUHKEY__@@PEBG1$$QEAV1234@@Z`
- size: `388`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001cc98`

## callees

- `0x180019d84`
- `0x18001b650`
- `0x18001cafc`
- `0x18001cfc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019edb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019edb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019de6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019e7a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019de6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019e7a`

## string_xrefs

- `0x180019dd1`: `TaskWakeUpTriggerTimes`
- `0x180019e65`: `TaskWakeUpTriggerTimes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Registry::GetValue<Microsoft::WRL::Wrappers::HString>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  LSTATUS ValueW; // eax
  bool v7; // sf
  signed int v8; // eax
  _QWORD *v9; // rcx
  _QWORD *result; // rax
  LSTATUS v11; // eax
  bool v12; // sf
  _QWORD *v13; // rcx
  const char *v14; // r9
  _QWORD *v15; // rax
  _QWORD *v16; // rdx
  PVOID pvData; // [rsp+48h] [rbp-20h] BYREF
  int v18; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 pcbData; // [rsp+80h] [rbp+18h] BYREF
  HSTRING string; // [rsp+88h] [rbp+20h] BYREF

  HIDWORD(string) = HIDWORD(a4);
  pcbData = a3;
  pvData = 0;
  v18 = 0;
  LODWORD(string) = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             (LPCWSTR)"S\x00O\x00F\x00T\x00W\x00A\x00R\x00E\x00\\\x00M\x00i\x00c\x00r\x00o\x00s\x00o\x00f\x00t\x00\\\x00W\x00i\x00n\x00d\x00o\x00w\x00s\x00\\\x00C\x00u\x00r\x00r\x00e\x00n\x00t\x00V\x00e\x00r\x00s\x00i\x00o\x00n\x00\\\x00I\x00n\x00s\x00t\x00a\x00l\x00l\x00S\x00e\x00r\x00v\x00i\x00c\x00e\x00\\\x00C\x00o\x00n\x00f\x00i\x00g\x00u\x00r\x00a\x00t\x00i\x00o\x00n",
             L"TaskWakeUpTriggerTimes",
             2u,
             0,
             0,
             (LPDWORD)&string);
  v7 = ValueW < 0;
  if ( ValueW > 0 )
  {
    v8 = (unsigned __int16)ValueW | 0x80070000;
    v7 = v8 < 0;
  }
  if ( v7 )
  {
    v9 = a5;
    *a1 = *a5;
    *v9 = 0;
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&pvData);
    return a1;
  }
  else
  {
    try
    {
      Registry::RegValueReadTraits<Microsoft::WRL::Wrappers::HString>::InitializeBuffer();
      LODWORD(pcbData) = v18;
      v11 = RegGetValueW(
              HKEY_LOCAL_MACHINE,
              (LPCWSTR)"S\x00O\x00F\x00T\x00W\x00A\x00R\x00E\x00\\\x00M\x00i\x00c\x00r\x00o\x00s\x00o\x00f\x00t\x00\\\x00W\x00i\x00n\x00d\x00o\x00w\x00s\x00\\\x00C\x00u\x00r\x00r\x00e\x00n\x00t\x00V\x00e\x00r\x00s\x00i\x00o\x00n\x00\\\x00I\x00n\x00s\x00t\x00a\x00l\x00l\x00S\x00e\x00r\x00v\x00i\x00c\x00e\x00\\\x00C\x00o\x00n\x00f\x00i\x00g\x00u\x00r\x00a\x00t\x00i\x00o\x00n",
              L"TaskWakeUpTriggerTimes",
              2u,
              0,
              pvData,
              (LPDWORD)&pcbData);
      v12 = v11 < 0;
      if ( v11 > 0 )
        v12 = 1;
      if ( v12 )
      {
        v13 = a5;
        *a1 = *a5;
        *v13 = 0;
      }
      else
      {
        v15 = (_QWORD *)Registry::RegValueReadTraits<Microsoft::WRL::Wrappers::HString>::FinalizeAndRelease(
                          &pvData,
                          &string);
        *a1 = *v15;
        *v15 = 0;
        WindowsDeleteString(string);
        string = 0;
      }
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&pvData);
      result = a1;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xF7,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\RegHelpers.h",
        v14);
      v16 = a5;
      *a1 = *a5;
      *v16 = 0;
      return a1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019d84  mov     r11, rsp
0x180019d87  mov     [r11+20h], r9
0x180019d8b  mov     [r11+18h], r8
0x180019d8f  mov     [r11+8], rcx
0x180019d93  push    rbx
0x180019d94  sub     rsp, 60h
0x180019d98  mov     rbx, rcx
0x180019d9b  mov     qword ptr [r11-20h], 0
0x180019da3  mov     [rsp+68h+var_18], 0
0x180019dab  mov     dword ptr [r11+20h], 0
0x180019db3  lea     rax, [r11+20h]
0x180019db7  mov     [r11-38h], rax
0x180019dbb  mov     qword ptr [r11-40h], 0
0x180019dc3  mov     qword ptr [r11-48h], 0
0x180019dcb  mov     r9d, 2; dwFlags
0x180019dd1  lea     r8, aTaskwakeuptrig; "TaskWakeUpTriggerTimes"
0x180019dd8  lea     rdx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; lpSubKey
0x180019ddf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180019de6  call    cs:__imp_RegGetValueW
0x180019dec  test    eax, eax
0x180019dee  jle     short loc_180019DFA
0x180019df0  movzx   eax, ax
0x180019df3  or      eax, 80070000h
0x180019df8  test    eax, eax
0x180019dfa  jns     short loc_180019E23
0x180019dfc  mov     rcx, [rsp+68h+arg_20]
0x180019e04  mov     rax, [rcx]
0x180019e07  mov     [rbx], rax
0x180019e0a  mov     qword ptr [rcx], 0
0x180019e11  lea     rcx, [rsp+68h+var_20]
0x180019e16  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180019e1b  mov     rax, rbx
0x180019e1e  jmp     loc_180019F01
0x180019e23  mov     edx, dword ptr [rsp+68h+string]
0x180019e2a  lea     rcx, [rsp+68h+var_20]
0x180019e2f  call    ?InitializeBuffer@?$RegValueReadTraits@VHString@Wrappers@WRL@Microsoft@@@Registry@@QEAAXK@Z; Registry::RegValueReadTraits<Microsoft::WRL::Wrappers::HString>::InitializeBuffer(ulong)
0x180019e34  mov     eax, [rsp+68h+var_18]
0x180019e38  mov     dword ptr [rsp+68h+arg_10], eax
0x180019e3f  lea     rax, [rsp+68h+arg_10]
0x180019e47  mov     [rsp+68h+pcbData], rax; pcbData
0x180019e4c  mov     rax, [rsp+68h+var_20]
0x180019e51  mov     [rsp+68h+pvData], rax; pvData
0x180019e56  mov     [rsp+68h+pdwType], 0; pdwType
0x180019e5f  mov     r9d, 2; dwFlags
0x180019e65  lea     r8, aTaskwakeuptrig; "TaskWakeUpTriggerTimes"
0x180019e6c  lea     rdx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; lpSubKey
0x180019e73  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180019e7a  call    cs:__imp_RegGetValueW
0x180019e80  test    eax, eax
0x180019e82  jle     short loc_180019E8E
0x180019e84  movzx   eax, ax
0x180019e87  or      eax, 80070000h
0x180019e8c  test    eax, eax
0x180019e8e  jns     short loc_180019EB4
0x180019e90  mov     rcx, [rsp+68h+arg_20]
0x180019e98  mov     rax, [rcx]
0x180019e9b  mov     [rbx], rax
0x180019e9e  mov     qword ptr [rcx], 0
0x180019ea5  lea     rcx, [rsp+68h+var_20]
0x180019eaa  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180019eaf  mov     rax, rbx
0x180019eb2  jmp     short loc_180019F01
0x180019eb4  lea     rdx, [rsp+68h+string]
0x180019ebc  lea     rcx, [rsp+68h+var_20]
0x180019ec1  call    ?FinalizeAndRelease@?$RegValueReadTraits@VHString@Wrappers@WRL@Microsoft@@@Registry@@QEAA?AVHString@Wrappers@WRL@Microsoft@@XZ; Registry::RegValueReadTraits<Microsoft::WRL::Wrappers::HString>::FinalizeAndRelease(void)
0x180019ec6  mov     rcx, [rax]
0x180019ec9  mov     [rbx], rcx
0x180019ecc  mov     qword ptr [rax], 0
0x180019ed3  mov     rcx, [rsp+68h+string]; string
0x180019edb  call    cs:__imp_WindowsDeleteString
0x180019ee1  mov     [rsp+68h+string], 0
0x180019eed  lea     rcx, [rsp+68h+var_20]
0x180019ef2  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180019ef7  mov     rax, rbx
0x180019efa  jmp     short loc_180019F01
0x180019efc  mov     rax, [rsp+68h+arg_0]
0x180019f01  add     rsp, 60h
0x180019f05  pop     rbx
0x180019f06  retn
```
