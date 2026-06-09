# AIXPolicyHelper::GetCurrentBuildRevision(void)

- ea: `0x180018758`
- end: `0x1800187f8`
- name: `?GetCurrentBuildRevision@AIXPolicyHelper@@YAKXZ`
- size: `160`
- prototype: `unsigned int __fastcall(AIXPolicyHelper *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a038`
- `0x18001b7fc`
- `0x18002d050`

## callees

- `0x1800122f0`
- `0x180018758`
- `0x18002062c`
- `0x1800233ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800187d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800187ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800187d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800187ea`

## string_xrefs

- `0x1800187b9`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
__int64 __fastcall AIXPolicyHelper::GetCurrentBuildRevision(AIXPolicyHelper *this)
{
  LSTATUS value_dword; // eax
  __int64 v2; // rdx
  unsigned int v4; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+38h] [rbp+10h] BYREF

  hKey = 0;
  value_dword = wil::reg::open_unique_key_nothrow(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                  &hKey,
                  0);
  if ( value_dword < 0 )
  {
    v2 = 716;
LABEL_5:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v2,
      (int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)value_dword);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  v6 = 0;
  value_dword = wil::reg::get_value_dword_nothrow<unsigned long,0>(hKey, L"UBR", &v6);
  if ( value_dword < 0 )
  {
    v2 = 719;
    goto LABEL_5;
  }
  v4 = v6;
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180018758  push    rbx; int
0x18001875a  sub     rsp, 20h
0x18001875e  xor     r9d, r9d
0x180018761  mov     [rsp+28h+hKey], 0
0x18001876a  lea     r8, [rsp+28h+hKey]; phkResult
0x18001876f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018776  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001877d  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180018782  test    eax, eax
0x180018784  jns     short loc_18001878D
0x180018786  mov     edx, 2CCh
0x18001878b  jmp     short loc_1800187B4
0x18001878d  mov     rcx, [rsp+28h+hKey]
0x180018792  lea     r8, [rsp+28h+arg_0]
0x180018797  lea     rdx, aUbr; "UBR"
0x18001879e  mov     [rsp+28h+arg_0], 0
0x1800187a6  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBGPEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ulong *)
0x1800187ab  test    eax, eax
0x1800187ad  jns     short loc_1800187DC
0x1800187af  mov     edx, 2CFh; void *
0x1800187b4  mov     rcx, [rsp+28h]; this
0x1800187b9  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x1800187c0  mov     r9d, eax; char *
0x1800187c3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800187c8  mov     rcx, [rsp+28h+hKey]; hKey
0x1800187cd  test    rcx, rcx
0x1800187d0  jz      short loc_1800187D8
0x1800187d2  call    cs:__imp_RegCloseKey
0x1800187d8  xor     eax, eax
0x1800187da  jmp     short loc_1800187F2
0x1800187dc  mov     rcx, [rsp+28h+hKey]; hKey
0x1800187e1  mov     ebx, [rsp+28h+arg_0]
0x1800187e5  test    rcx, rcx
0x1800187e8  jz      short loc_1800187F0
0x1800187ea  call    cs:__imp_RegCloseKey
0x1800187f0  mov     eax, ebx
0x1800187f2  add     rsp, 20h
0x1800187f6  pop     rbx
0x1800187f7  retn
```
