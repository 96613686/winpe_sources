# Container::Manager::Agent::Core::_anonymous_namespace_::UpdateUbrRegistryValue

- ea: `0x1800200e4`
- end: `0x18002018e`
- name: `Container::Manager::Agent::Core::_anonymous_namespace_::UpdateUbrRegistryValue`
- size: `170`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005050`
- `0x18001fb70`

## callees

- `0x1800045e4`
- `0x18000b5b0`
- `0x18000b820`
- `0x1800200e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020139`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020174`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020139`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020174`

## string_xrefs

- `0x180020120`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::_anonymous_namespace_::UpdateUbrRegistryValue(__int64 a1)
{
  int v1; // edi
  int v2; // ebx
  __int64 v3; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HKEY hKey; // [rsp+38h] [rbp+10h] BYREF

  hKey = 0;
  v1 = a1;
  v2 = Csl::OpenRegistryKey(a1, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0x2001Fu, (char *)&hKey);
  if ( v2 < 0 )
  {
    v3 = 332;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)(unsigned int)v2);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v2;
  }
  v2 = Csl::RegistryKey::SetDwordValue(&hKey, L"UBR", v1);
  if ( v2 < 0 )
  {
    v3 = 334;
    goto LABEL_3;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800200e4  mov     [rsp+arg_0], rbx
0x1800200e9  push    rdi; int
0x1800200ea  sub     rsp, 20h
0x1800200ee  lea     r9, [rsp+28h+hKey]
0x1800200f3  mov     [rsp+28h+hKey], 0
0x1800200fc  mov     r8d, 2001Fh
0x180020102  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180020109  mov     edi, ecx
0x18002010b  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180020110  mov     ebx, eax
0x180020112  test    eax, eax
0x180020114  jns     short loc_180020149
0x180020116  mov     edx, 14Ch; void *
0x18002011b  mov     rcx, [rsp+28h]; this
0x180020120  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180020127  mov     r9d, ebx; char *
0x18002012a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002012f  mov     rcx, [rsp+28h+hKey]; hKey
0x180020134  test    rcx, rcx
0x180020137  jz      short loc_180020145
0x180020139  call    cs:__imp_RegCloseKey
0x180020140  nop     dword ptr [rax+rax+00h]
0x180020145  mov     eax, ebx
0x180020147  jmp     short loc_180020182
0x180020149  mov     r8d, edi; unsigned int
0x18002014c  lea     rdx, aUbr; "UBR"
0x180020153  lea     rcx, [rsp+28h+hKey]; this
0x180020158  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x18002015d  mov     ebx, eax
0x18002015f  test    eax, eax
0x180020161  jns     short loc_18002016A
0x180020163  mov     edx, 14Eh
0x180020168  jmp     short loc_18002011B
0x18002016a  mov     rcx, [rsp+28h+hKey]; hKey
0x18002016f  test    rcx, rcx
0x180020172  jz      short loc_180020180
0x180020174  call    cs:__imp_RegCloseKey
0x18002017b  nop     dword ptr [rax+rax+00h]
0x180020180  xor     eax, eax
0x180020182  mov     rbx, [rsp+28h+arg_0]
0x180020187  add     rsp, 20h
0x18002018b  pop     rdi
0x18002018c  retn
```
