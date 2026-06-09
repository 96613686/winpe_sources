# CReportStore::InitMachineStore(void)

- ea: `0x180009990`
- end: `0x180009acc`
- name: `?InitMachineStore@CReportStore@@UEAAJXZ`
- size: `316`
- prototype: `__int64 __fastcall(CReportStore *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008a20`
- `0x180009590`

## callees

- `0x180009758`
- `0x180009990`
- `0x18000b1f4`
- `0x18003db78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009aae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009aae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009a3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009a3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009a12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009a12`

## string_xrefs

- `0x180009a8c`: `StoreDontForceCompression`
- `0x180009a63`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`

## pseudocode

```c
__int64 __fastcall CReportStore::InitMachineStore(CReportStore *this)
{
  int Settings; // ebx
  LSTATUS v3; // eax
  bool v4; // sf
  bool v5; // cc
  int v6; // ebx
  __int64 v8; // rdx
  LSTATUS ValueW; // eax
  int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  Settings = CSettings::LoadSettings((CReportStore *)((char *)this + 72), 0, 0, WerConsentNotAsked);
  if ( Settings < 0 )
  {
    v8 = 141;
    goto LABEL_12;
  }
  Settings = CReportStore::GetMachineStoreDir((__int64 (__fastcall ***)(_QWORD))this, (_QWORD *)this + 2);
  if ( Settings < 0 )
  {
    v8 = 143;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)(unsigned int)Settings,
      phkResult);
    return (unsigned int)Settings;
  }
  *((_DWORD *)this + 2) = 3;
  pvData = 0;
  pcbData = 4;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
         0,
         0x101u,
         &hKey);
  v4 = v3 < 0;
  v5 = v3 <= 0;
  if ( !v3 )
  {
    ValueW = RegGetValueW(hKey, 0, L"StoreDontForceCompression", 0x10u, 0, &pvData, &pcbData);
    v4 = ValueW < 0;
    v5 = ValueW <= 0;
    if ( !ValueW )
      goto LABEL_7;
  }
  if ( !v5 )
    v4 = 1;
  if ( v4 )
  {
    v6 = 0;
    pvData = 0;
  }
  else
  {
LABEL_7:
    v6 = pvData;
  }
  if ( hKey )
    RegCloseKey(hKey);
  *((_DWORD *)this + 12) = v6 != 0;
  return 0;
}

```

## disassembly

```asm
0x180009990  mov     [rsp+arg_18], rbx
0x180009995  push    rdi
0x180009996  sub     rsp, 40h
0x18000999a  mov     rdi, rcx
0x18000999d  mov     r9d, 1; enum _WER_CONSENT
0x1800099a3  add     rcx, 48h ; 'H'; this
0x1800099a7  xor     r8d, r8d; wchar_t *
0x1800099aa  xor     edx, edx; wchar_t *
0x1800099ac  call    ?LoadSettings@CSettings@@QEAAJPEB_W0W4_WER_CONSENT@@@Z; CSettings::LoadSettings(wchar_t const *,wchar_t const *,_WER_CONSENT)
0x1800099b1  mov     ebx, eax
0x1800099b3  test    eax, eax
0x1800099b5  js      loc_180009A76
0x1800099bb  lea     rdx, [rdi+10h]
0x1800099bf  mov     rcx, rdi
0x1800099c2  call    ?GetMachineStoreDir@CReportStore@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::GetMachineStoreDir(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800099c7  mov     ebx, eax
0x1800099c9  test    eax, eax
0x1800099cb  js      loc_180009A59
0x1800099d1  lea     rax, [rsp+48h+hKey]
0x1800099d6  mov     dword ptr [rdi+8], 3
0x1800099dd  mov     r9d, 101h; samDesired
0x1800099e3  mov     [rsp+48h+phkResult], rax; phkResult
0x1800099e8  xor     r8d, r8d; ulOptions
0x1800099eb  mov     [rsp+48h+arg_0], 0
0x1800099f3  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1800099fa  mov     [rsp+48h+arg_8], 4
0x180009a02  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009a09  mov     [rsp+48h+hKey], 0
0x180009a12  call    cs:__imp_RegOpenKeyExW
0x180009a18  test    eax, eax
0x180009a1a  jz      short loc_180009A7D
0x180009a1c  jle     short loc_180009A28
0x180009a1e  movzx   eax, ax
0x180009a21  or      eax, 80070000h
0x180009a26  test    eax, eax
0x180009a28  js      loc_180009AC1
0x180009a2e  mov     ebx, [rsp+48h+arg_0]
0x180009a32  mov     rcx, [rsp+48h+hKey]; hKey
0x180009a37  test    rcx, rcx
0x180009a3a  jz      short loc_180009A42
0x180009a3c  call    cs:__imp_RegCloseKey
0x180009a42  xor     eax, eax
0x180009a44  test    ebx, ebx
0x180009a46  setnz   al
0x180009a49  mov     [rdi+30h], eax
0x180009a4c  xor     eax, eax
0x180009a4e  mov     rbx, [rsp+48h+arg_18]
0x180009a53  add     rsp, 40h
0x180009a57  pop     rdi
0x180009a58  retn
0x180009a59  mov     edx, 8Fh; void *
0x180009a5e  mov     rcx, [rsp+48h]; this
0x180009a63  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180009a6a  mov     r9d, ebx; char *
0x180009a6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a72  mov     eax, ebx
0x180009a74  jmp     short loc_180009A4E
0x180009a76  mov     edx, 8Dh
0x180009a7b  jmp     short loc_180009A5E
0x180009a7d  mov     rcx, [rsp+48h+hKey]; hkey
0x180009a82  lea     rax, [rsp+48h+arg_8]
0x180009a87  mov     [rsp+48h+pcbData], rax; pcbData
0x180009a8c  lea     r8, aStoredontforce; "StoreDontForceCompression"
0x180009a93  lea     rax, [rsp+48h+arg_0]
0x180009a98  mov     r9d, 10h; dwFlags
0x180009a9e  mov     [rsp+48h+pvData], rax; pvData
0x180009aa3  xor     edx, edx; lpSubKey
0x180009aa5  mov     [rsp+48h+phkResult], 0; pdwType
0x180009aae  call    cs:__imp_RegGetValueW
0x180009ab4  test    eax, eax
0x180009ab6  jz      loc_180009A2E
0x180009abc  jmp     loc_180009A1C
0x180009ac1  xor     ebx, ebx
0x180009ac3  mov     [rsp+48h+arg_0], ebx
0x180009ac7  jmp     loc_180009A32
```
