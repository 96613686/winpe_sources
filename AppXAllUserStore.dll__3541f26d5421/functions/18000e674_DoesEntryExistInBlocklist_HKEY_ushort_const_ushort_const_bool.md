# DoesEntryExistInBlocklist(HKEY__ *,ushort const *,ushort const *,bool *)

- ea: `0x18000e674`
- end: `0x18000e785`
- name: `?DoesEntryExistInBlocklist@@YAJPEAUHKEY__@@PEBG1PEA_N@Z`
- size: `273`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e58c`

## callees

- `0x180004968`
- `0x180007860`
- `0x18000e674`
- `0x180018248`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e70e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e70e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e6c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e6c6`

## string_xrefs

- `0x18000e744`: `onecore\base\appmodel\common\appxuninstallblocklist.cpp`
- `0x18000e6bc`: `Classes\CLSID\{AA00FB1F-4EC7-4b09-BDC1-E5D88D291440}`

## pseudocode

```c
__int64 __fastcall DoesEntryExistInBlocklist(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        bool *a4)
{
  LSTATUS v7; // eax
  signed int v8; // ebx
  __int64 v9; // rdx
  LSTATUS Value; // eax
  int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKeya; // [rsp+48h] [rbp+10h] BYREF

  hKeya = 0;
  Common::AutoHandleCloseHKEY<HKEY__ *>(0);
  hKeya = 0;
  v7 = RegOpenKeyExW(hKey, L"Classes\\CLSID\\{AA00FB1F-4EC7-4b09-BDC1-E5D88D291440}", 0, 0x20019u, &hKeya);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 < 0 )
  {
    if ( v8 != -2147024894 )
    {
      v9 = 79;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\appmodel\\common\\appxuninstallblocklist.cpp",
        (const char *)(unsigned int)v8,
        phkResult);
      Common::RegistryKey::~RegistryKey(&hKeya);
      return (unsigned int)v8;
    }
LABEL_14:
    *a4 = 0;
    goto LABEL_16;
  }
  Value = RegQueryValueExW(hKeya, a3, 0, 0, 0, 0);
  v8 = Value;
  if ( !Value || Value == 234 )
  {
    *a4 = 1;
    goto LABEL_16;
  }
  if ( (unsigned int)(Value - 2) <= 1 )
    goto LABEL_14;
  if ( Value > 0 )
    v8 = (unsigned __int16)Value | 0x80070000;
  if ( v8 < 0 )
  {
    v9 = 82;
    goto LABEL_13;
  }
LABEL_16:
  Common::AutoHandleCloseHKEY<HKEY__ *>(hKeya);
  return 0;
}

```

## disassembly

```asm
0x18000e674  mov     rax, rsp
0x18000e677  mov     [rax+8], rbx
0x18000e67b  mov     [rax+18h], rsi
0x18000e67f  mov     [rax+10h], rdx
0x18000e683  push    rdi
0x18000e684  sub     rsp, 30h
0x18000e688  mov     rbx, rcx
0x18000e68b  mov     qword ptr [rax+10h], 0
0x18000e693  xor     ecx, ecx
0x18000e695  mov     rdi, r9
0x18000e698  mov     rsi, r8
0x18000e69b  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000e6a0  lea     rax, [rsp+38h+hKey]
0x18000e6a5  mov     [rsp+38h+hKey], 0
0x18000e6ae  mov     r9d, 20019h; samDesired
0x18000e6b4  mov     [rsp+38h+phkResult], rax; phkResult
0x18000e6b9  xor     r8d, r8d; ulOptions
0x18000e6bc  lea     rdx, aClassesClsidAa; "Classes\\CLSID\\{AA00FB1F-4EC7-4b09-BDC"...
0x18000e6c3  mov     rcx, rbx; hKey
0x18000e6c6  call    cs:__imp_RegOpenKeyExW
0x18000e6cc  mov     ebx, eax
0x18000e6ce  test    eax, eax
0x18000e6d0  jle     short loc_18000E6DB
0x18000e6d2  movzx   ebx, ax
0x18000e6d5  or      ebx, 80070000h
0x18000e6db  test    ebx, ebx
0x18000e6dd  jns     short loc_18000E6EE
0x18000e6df  cmp     ebx, 80070002h
0x18000e6e5  jz      short loc_18000E761
0x18000e6e7  mov     edx, 4Fh ; 'O'
0x18000e6ec  jmp     short loc_18000E73F
0x18000e6ee  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e6f3  xor     r9d, r9d; lpType
0x18000e6f6  mov     [rsp+38h+lpcbData], 0; lpcbData
0x18000e6ff  xor     r8d, r8d; lpReserved
0x18000e702  mov     rdx, rsi; lpValueName
0x18000e705  mov     [rsp+38h+phkResult], 0; int
0x18000e70e  call    cs:__imp_RegQueryValueExW
0x18000e714  mov     ebx, eax
0x18000e716  test    eax, eax
0x18000e718  jz      short loc_18000E766
0x18000e71a  cmp     eax, 0EAh
0x18000e71f  jz      short loc_18000E766
0x18000e721  lea     ecx, [rax-2]
0x18000e724  cmp     ecx, 1
0x18000e727  jbe     short loc_18000E761
0x18000e729  test    eax, eax
0x18000e72b  jle     short loc_18000E736
0x18000e72d  movzx   ebx, ax
0x18000e730  or      ebx, 80070000h
0x18000e736  test    ebx, ebx
0x18000e738  jns     short loc_18000E769
0x18000e73a  mov     edx, 52h ; 'R'; void *
0x18000e73f  mov     rcx, [rsp+38h]; this
0x18000e744  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\appxun"...
0x18000e74b  mov     r9d, ebx; char *
0x18000e74e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e753  lea     rcx, [rsp+38h+hKey]; this
0x18000e758  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18000e75d  mov     eax, ebx
0x18000e75f  jmp     short loc_18000E775
0x18000e761  mov     byte ptr [rdi], 0
0x18000e764  jmp     short loc_18000E769
0x18000e766  mov     byte ptr [rdi], 1
0x18000e769  mov     rcx, [rsp+38h+hKey]
0x18000e76e  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000e773  xor     eax, eax
0x18000e775  mov     rbx, [rsp+38h+arg_0]
0x18000e77a  mov     rsi, [rsp+38h+arg_10]
0x18000e77f  add     rsp, 30h
0x18000e783  pop     rdi
0x18000e784  retn
```
