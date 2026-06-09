# LogETagValue

- ea: `0x140033f60`
- end: `0x140034016`
- name: `LogETagValue`
- size: `182`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14003401c`

## callees

- `0x140017934`
- `0x140018170`
- `0x140033f60`
- `0x140045dc0`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140033fc5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140033fc5`

## string_xrefs

- `0x140033f8a`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x140033fe9`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x140033f94`: `SLSWriteETagToRegistry`

## pseudocode

```c
int __fastcall LogETagValue(GUID *rguid, const WCHAR *a2)
{
  int result; // eax
  const WCHAR *v5; // r9
  __int64 v6; // [rsp+20h] [rbp-88h]
  OLECHAR sz[40]; // [rsp+40h] [rbp-68h] BYREF

  result = RegQueryDwordValueWithDefaultAndRangeCheck(
             (int)rguid,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
             L"SLSWriteETagToRegistry",
             0,
             v6,
             0xFFFFFFFF);
  if ( result )
  {
    memset(sz, 0, 0x4Eu);
    result = StringFromGUID2(rguid, sz, 39);
    if ( result )
    {
      v5 = &OutputString;
      if ( a2 )
        v5 = a2;
      return RegSetStringValue(
               -2147483646,
               (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
               (__int64)sz,
               (__int64)v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140033f60  mov     [rsp+arg_10], rbx
0x140033f65  push    rdi
0x140033f66  sub     rsp, 0A0h
0x140033f6d  mov     rax, cs:__security_cookie
0x140033f74  xor     rax, rsp
0x140033f77  mov     [rsp+0A8h+var_18], rax
0x140033f7f  mov     rbx, rdx
0x140033f82  mov     [rsp+0A8h+var_80], 0FFFFFFFFh
0x140033f8a  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140033f91  xor     r9d, r9d
0x140033f94  lea     r8, aSlswriteetagto; "SLSWriteETagToRegistry"
0x140033f9b  mov     rdi, rcx
0x140033f9e  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140033fa3  test    eax, eax
0x140033fa5  jz      short loc_140033FF5
0x140033fa7  xor     edx, edx; Val
0x140033fa9  lea     rcx, [rsp+0A8h+sz]; void *
0x140033fae  lea     r8d, [rdx+4Eh]; Size
0x140033fb2  call    memset
0x140033fb7  mov     r8d, 27h ; '''; cchMax
0x140033fbd  lea     rdx, [rsp+0A8h+sz]; lpsz
0x140033fc2  mov     rcx, rdi; rguid
0x140033fc5  call    cs:__imp_StringFromGUID2
0x140033fcb  test    eax, eax
0x140033fcd  jz      short loc_140033FF5
0x140033fcf  test    rbx, rbx
0x140033fd2  lea     r9, OutputString
0x140033fd9  lea     r8, [rsp+0A8h+sz]
0x140033fde  mov     rcx, 0FFFFFFFF80000002h
0x140033fe5  cmovnz  r9, rbx
0x140033fe9  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140033ff0  call    ?RegSetStringValue@@YAJPEAUHKEY__@@PEB_W11W4RegistryHiveType@@@Z; RegSetStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x140033ff5  mov     rcx, [rsp+0A8h+var_18]
0x140033ffd  xor     rcx, rsp; StackCookie
0x140034000  call    __security_check_cookie
0x140034005  mov     rbx, [rsp+0A8h+arg_10]
0x14003400d  add     rsp, 0A0h
0x140034014  pop     rdi
0x140034015  retn
```
