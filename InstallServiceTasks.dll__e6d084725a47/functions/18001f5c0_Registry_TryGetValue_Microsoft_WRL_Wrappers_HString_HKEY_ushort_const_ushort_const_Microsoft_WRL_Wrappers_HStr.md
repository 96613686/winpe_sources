# Registry::TryGetValue<Microsoft::WRL::Wrappers::HString>(HKEY__ *,ushort const *,ushort const *,Microsoft::WRL::Wrappers::HString &)

- ea: `0x18001f5c0`
- end: `0x18001f70a`
- name: `??$TryGetValue@VHString@Wrappers@WRL@Microsoft@@@Registry@@YA_NPEAUHKEY__@@PEBG1AEAVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `330`
- prototype: `char __fastcall(__int64, const WCHAR *, __int64, HSTRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180020fe4`

## callees

- `0x18001b650`
- `0x18001cafc`
- `0x18001cfc0`
- `0x18001f5c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f6c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f6e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f6c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f6e7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f61e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f68f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f61e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f68f`

## string_xrefs

- `0x18001f610`: `AutoUpdatePauseEndTime`
- `0x18001f67e`: `AutoUpdatePauseEndTime`

## pseudocode

```c
char __fastcall Registry::TryGetValue<Microsoft::WRL::Wrappers::HString>(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        HSTRING *a4)
{
  LSTATUS ValueW; // eax
  bool v7; // sf
  signed int v8; // eax
  char result; // al
  LSTATUS v10; // eax
  bool v11; // sf
  const char *v12; // r9
  HSTRING *v13; // rdi
  PVOID pvData; // [rsp+40h] [rbp-18h] BYREF
  int v15; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 pcbData; // [rsp+60h] [rbp+8h] BYREF
  HSTRING string; // [rsp+70h] [rbp+18h] BYREF

  HIDWORD(string) = HIDWORD(a3);
  pcbData = a1;
  pvData = 0;
  v15 = 0;
  LODWORD(string) = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a2, L"AutoUpdatePauseEndTime", 2u, 0, 0, (LPDWORD)&string);
  v7 = ValueW < 0;
  if ( ValueW > 0 )
  {
    v8 = (unsigned __int16)ValueW | 0x80070000;
    v7 = v8 < 0;
  }
  if ( v7 )
  {
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&pvData);
    return 0;
  }
  else
  {
    try
    {
      Registry::RegValueReadTraits<Microsoft::WRL::Wrappers::HString>::InitializeBuffer();
      LODWORD(pcbData) = v15;
      v10 = RegGetValueW(HKEY_LOCAL_MACHINE, a2, L"AutoUpdatePauseEndTime", 2u, 0, pvData, (LPDWORD)&pcbData);
      v11 = v10 < 0;
      if ( v10 > 0 )
        v11 = 1;
      if ( v11 )
      {
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&pvData);
        result = 0;
      }
      else
      {
        v13 = (HSTRING *)Registry::RegValueReadTraits<Microsoft::WRL::Wrappers::HString>::FinalizeAndRelease(
                           &pvData,
                           &string);
        WindowsDeleteString(*a4);
        *a4 = 0;
        *a4 = *v13;
        *v13 = 0;
        WindowsDeleteString(string);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&pvData);
        result = 1;
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x118,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\RegHelpers.h",
        v12);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001f5c0  mov     r11, rsp
0x18001f5c3  mov     [r11+10h], rbx
0x18001f5c7  mov     [r11+18h], r8
0x18001f5cb  mov     [r11+8], rcx
0x18001f5cf  push    rdi
0x18001f5d0  sub     rsp, 50h
0x18001f5d4  mov     rbx, r9
0x18001f5d7  mov     rdi, rdx
0x18001f5da  mov     qword ptr [r11-18h], 0
0x18001f5e2  mov     [rsp+58h+var_10], 0
0x18001f5ea  mov     dword ptr [rsp+58h+string], 0
0x18001f5f2  lea     rax, [r11+18h]
0x18001f5f6  mov     [r11-28h], rax
0x18001f5fa  mov     qword ptr [r11-30h], 0
0x18001f602  mov     qword ptr [r11-38h], 0
0x18001f60a  mov     r9d, 2; dwFlags
0x18001f610  lea     r8, ValueName; "AutoUpdatePauseEndTime"
0x18001f617  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001f61e  call    cs:__imp_RegGetValueW
0x18001f624  test    eax, eax
0x18001f626  jle     short loc_18001F632
0x18001f628  movzx   eax, ax
0x18001f62b  or      eax, 80070000h
0x18001f630  test    eax, eax
0x18001f632  jns     short loc_18001F645
0x18001f634  lea     rcx, [rsp+58h+var_18]
0x18001f639  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001f63e  xor     al, al
0x18001f640  jmp     loc_18001F6FE
0x18001f645  mov     edx, dword ptr [rsp+58h+string]
0x18001f649  lea     rcx, [rsp+58h+var_18]
0x18001f64e  call    ?InitializeBuffer@?$RegValueReadTraits@VHString@Wrappers@WRL@Microsoft@@@Registry@@QEAAXK@Z; Registry::RegValueReadTraits<Microsoft::WRL::Wrappers::HString>::InitializeBuffer(ulong)
0x18001f653  mov     eax, [rsp+58h+var_10]
0x18001f657  mov     dword ptr [rsp+58h+arg_0], eax
0x18001f65b  lea     rax, [rsp+58h+arg_0]
0x18001f660  mov     [rsp+58h+pcbData], rax; pcbData
0x18001f665  mov     rax, [rsp+58h+var_18]
0x18001f66a  mov     [rsp+58h+pvData], rax; pvData
0x18001f66f  mov     [rsp+58h+pdwType], 0; pdwType
0x18001f678  mov     r9d, 2; dwFlags
0x18001f67e  lea     r8, ValueName; "AutoUpdatePauseEndTime"
0x18001f685  mov     rdx, rdi; lpSubKey
0x18001f688  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001f68f  call    cs:__imp_RegGetValueW
0x18001f695  test    eax, eax
0x18001f697  jle     short loc_18001F6A3
0x18001f699  movzx   eax, ax
0x18001f69c  or      eax, 80070000h
0x18001f6a1  test    eax, eax
0x18001f6a3  jns     short loc_18001F6B3
0x18001f6a5  lea     rcx, [rsp+58h+var_18]
0x18001f6aa  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001f6af  xor     al, al
0x18001f6b1  jmp     short loc_18001F6FE
0x18001f6b3  lea     rdx, [rsp+58h+string]
0x18001f6b8  lea     rcx, [rsp+58h+var_18]
0x18001f6bd  call    ?FinalizeAndRelease@?$RegValueReadTraits@VHString@Wrappers@WRL@Microsoft@@@Registry@@QEAA?AVHString@Wrappers@WRL@Microsoft@@XZ; Registry::RegValueReadTraits<Microsoft::WRL::Wrappers::HString>::FinalizeAndRelease(void)
0x18001f6c2  mov     rdi, rax
0x18001f6c5  mov     rcx, [rbx]; string
0x18001f6c8  call    cs:__imp_WindowsDeleteString
0x18001f6ce  mov     qword ptr [rbx], 0
0x18001f6d5  mov     rcx, [rdi]
0x18001f6d8  mov     [rbx], rcx
0x18001f6db  mov     qword ptr [rdi], 0
0x18001f6e2  mov     rcx, [rsp+58h+string]; string
0x18001f6e7  call    cs:__imp_WindowsDeleteString
0x18001f6ed  nop
0x18001f6ee  lea     rcx, [rsp+58h+var_18]
0x18001f6f3  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001f6f8  mov     al, 1
0x18001f6fa  jmp     short loc_18001F6FE
0x18001f6fc  xor     al, al
0x18001f6fe  mov     rbx, [rsp+58h+arg_8]
0x18001f703  add     rsp, 50h
0x18001f707  pop     rdi
0x18001f708  retn
```
