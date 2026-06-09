# Common::Deployment::Configuration::IsAuditBoot(int *)

- ea: `0x180006758`
- end: `0x18000686a`
- name: `?IsAuditBoot@Configuration@Deployment@Common@@YAJPEAH@Z`
- size: `274`
- prototype: `__int64 __fastcall(Common::Deployment::Configuration *__hidden this, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800110cc`
- `0x18002f200`

## callees

- `0x180004968`
- `0x180006758`
- `0x180007860`
- `0x180017f50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800067ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800067ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000679d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000679d`

## string_xrefs

- `0x180006822`: `onecore\admin\appmodel\common\configuration.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::Configuration::IsAuditBoot(Common::Deployment::Configuration *this, int *a2)
{
  int v3; // edi
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  HKEY v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  *(_DWORD *)this = 0;
  v3 = 0;
  hKey = 0;
  Common::AutoHandleCloseHKEY<HKEY__ *>(0);
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Status", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    if ( v5 != -2147024894 && v5 != -2147024893 )
      goto LABEL_14;
    goto LABEL_13;
  }
  Data = 0;
  cbData = 4;
  v6 = RegQueryValueExW(hKey, L"AuditBoot", 0, 0, (LPBYTE)&Data, &cbData);
  v5 = v6;
  if ( v6 > 0 )
    v5 = (unsigned __int16)v6 | 0x80070000;
  if ( v5 >= 0 )
  {
    if ( Data )
      v3 = 1;
    goto LABEL_14;
  }
  if ( (unsigned int)(v5 + 2147024894) <= 1 )
  {
LABEL_13:
    v5 = 0;
LABEL_14:
    v7 = hKey;
    *(_DWORD *)this = v3;
    Common::AutoHandleCloseHKEY<HKEY__ *>(v7);
    return (unsigned int)v5;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x25C,
    (int)"onecore\\admin\\appmodel\\common\\configuration.cpp",
    (const char *)(unsigned int)v5);
  Common::RegistryKey::~RegistryKey(&hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180006758  push    rbx
0x18000675a  push    rsi
0x18000675b  push    rdi
0x18000675c  sub     rsp, 30h
0x180006760  mov     rsi, rcx
0x180006763  mov     dword ptr [rcx], 0
0x180006769  xor     edi, edi
0x18000676b  xor     ecx, ecx
0x18000676d  mov     [rsp+48h+hKey], rdi
0x180006772  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180006777  lea     rax, [rsp+48h+hKey]
0x18000677c  mov     [rsp+48h+hKey], rdi
0x180006781  mov     r9d, 20019h; samDesired
0x180006787  mov     [rsp+48h+phkResult], rax; phkResult
0x18000678c  xor     r8d, r8d; ulOptions
0x18000678f  lea     rdx, SubKey; "System\\Setup\\Status"
0x180006796  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000679d  call    cs:__imp_RegOpenKeyExW
0x1800067a3  mov     ebx, eax
0x1800067a5  test    eax, eax
0x1800067a7  jle     short loc_1800067B2
0x1800067a9  movzx   ebx, ax
0x1800067ac  or      ebx, 80070000h
0x1800067b2  test    ebx, ebx
0x1800067b4  js      loc_180006842
0x1800067ba  mov     rcx, [rsp+48h+hKey]; hKey
0x1800067bf  lea     rax, [rsp+48h+cbData]
0x1800067c4  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800067c9  lea     rdx, aAuditboot; "AuditBoot"
0x1800067d0  lea     rax, [rsp+48h+Data]
0x1800067d5  mov     [rsp+48h+Data], edi
0x1800067d9  xor     r9d, r9d; lpType
0x1800067dc  mov     [rsp+48h+phkResult], rax; int
0x1800067e1  xor     r8d, r8d; lpReserved
0x1800067e4  mov     [rsp+48h+cbData], 4
0x1800067ec  call    cs:__imp_RegQueryValueExW
0x1800067f2  mov     ebx, eax
0x1800067f4  test    eax, eax
0x1800067f6  jle     short loc_180006801
0x1800067f8  movzx   ebx, ax
0x1800067fb  or      ebx, 80070000h
0x180006801  test    ebx, ebx
0x180006803  js      short loc_180006812
0x180006805  cmp     [rsp+48h+Data], edi
0x180006809  jz      short loc_180006854
0x18000680b  mov     edi, 1
0x180006810  jmp     short loc_180006854
0x180006812  lea     eax, [rbx+7FF8FFFEh]
0x180006818  cmp     eax, 1
0x18000681b  jbe     short loc_180006852
0x18000681d  mov     rcx, [rsp+48h]; this
0x180006822  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\common\\confi"...
0x180006829  mov     r9d, ebx; char *
0x18000682c  mov     edx, 25Ch; void *
0x180006831  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006836  lea     rcx, [rsp+48h+hKey]; this
0x18000683b  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180006840  jmp     short loc_180006860
0x180006842  cmp     ebx, 80070002h
0x180006848  jz      short loc_180006852
0x18000684a  cmp     ebx, 80070003h
0x180006850  jnz     short loc_180006854
0x180006852  xor     ebx, ebx
0x180006854  mov     rcx, [rsp+48h+hKey]
0x180006859  mov     [rsi], edi
0x18000685b  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180006860  mov     eax, ebx
0x180006862  add     rsp, 30h
0x180006866  pop     rdi
0x180006867  pop     rsi
0x180006868  pop     rbx
0x180006869  retn
```
