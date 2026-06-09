# RetailDemoStartup::StartupAppManager::ManageRegistryItem(RetailDemoStartup::StartupAppInfo const &,bool)

- ea: `0x180045bc8`
- end: `0x180045cdb`
- name: `?ManageRegistryItem@StartupAppManager@RetailDemoStartup@@AEAAJAEBUStartupAppInfo@2@_N@Z`
- size: `275`
- prototype: `__int64 __fastcall(RetailDemoStartup::StartupAppManager *__hidden this, const struct RetailDemoStartup::StartupAppInfo *, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180045ce4`

## callees

- `0x180003390`
- `0x18001092c`
- `0x1800445d0`
- `0x180044638`
- `0x1800446f8`
- `0x180045bc8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180045c6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180045c6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045ca5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045ca5`

## pseudocode

```c
LSTATUS __fastcall RetailDemoStartup::StartupAppManager::ManageRegistryItem(
        RetailDemoStartup::StartupAppManager *this,
        const struct RetailDemoStartup::StartupAppInfo *a2,
        char a3)
{
  unsigned __int64 DataKeyForItem; // rax
  RetailDemoStartup::StartupAppManager *v6; // rcx
  LSTATUS result; // eax
  struct RetailDemoStartup::StartupApproval *StartupApprovalObject; // rbx
  const unsigned __int16 *v9; // rax
  const WCHAR *v10; // rax
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+30h] [rbp-28h] BYREF

  DataKeyForItem = RetailDemoStartup::StartupAppManager::GetDataKeyForItem(this, a2);
  if ( !DataKeyForItem )
    return -2147024809;
  StartupApprovalObject = RetailDemoStartup::StartupAppManager::GetStartupApprovalObject(v6, DataKeyForItem);
  if ( !StartupApprovalObject )
    return -2147467259;
  memset(SystemTimeAsFileTime, 0, 12);
  v9 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  result = RetailDemoStartup::StartupApproval::GetBlockedItemInfo(
             StartupApprovalObject,
             v9,
             (struct RetailDemoStartup::BLOCKEDITEMINFO *)SystemTimeAsFileTime);
  if ( result != 2 && result && result != 1630 )
  {
LABEL_14:
    if ( result <= 0 )
      return result;
    return (unsigned __int16)result | 0x80070000;
  }
  if ( a3 )
  {
    SystemTimeAsFileTime[0].dwLowDateTime &= ~1u;
    *(_QWORD *)&SystemTimeAsFileTime[0].dwHighDateTime = 0;
  }
  else
  {
    SystemTimeAsFileTime[0].dwLowDateTime |= 1u;
    GetSystemTimeAsFileTime((LPFILETIME)&SystemTimeAsFileTime[0].dwHighDateTime);
  }
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( *(_BYTE *)StartupApprovalObject && (*((_BYTE *)StartupApprovalObject + 16) & 2) != 0 )
  {
    result = RegSetValueExW(*((HKEY *)StartupApprovalObject + 1), v10, 0, 3u, (const BYTE *)SystemTimeAsFileTime, 0xCu);
    goto LABEL_14;
  }
  LOWORD(result) = 87;
  return (unsigned __int16)result | 0x80070000;
}

```

## disassembly

```asm
0x180045bc8  mov     [rsp+arg_0], rbx
0x180045bcd  mov     [rsp+arg_10], rsi
0x180045bd2  push    rdi
0x180045bd3  sub     rsp, 50h
0x180045bd7  mov     rax, cs:__security_cookie
0x180045bde  xor     rax, rsp
0x180045be1  mov     [rsp+58h+var_18], rax
0x180045be6  mov     sil, r8b
0x180045be9  mov     rdi, rdx
0x180045bec  call    ?GetDataKeyForItem@StartupAppManager@RetailDemoStartup@@AEAA_KAEBUStartupAppInfo@2@@Z; RetailDemoStartup::StartupAppManager::GetDataKeyForItem(RetailDemoStartup::StartupAppInfo const &)
0x180045bf1  test    rax, rax
0x180045bf4  jnz     short loc_180045C00
0x180045bf6  mov     eax, 80070057h
0x180045bfb  jmp     loc_180045CBE
0x180045c00  mov     rdx, rax; unsigned __int64
0x180045c03  call    ?GetStartupApprovalObject@StartupAppManager@RetailDemoStartup@@AEAAPEAVStartupApproval@2@_K@Z; RetailDemoStartup::StartupAppManager::GetStartupApprovalObject(unsigned __int64)
0x180045c08  mov     rbx, rax
0x180045c0b  test    rax, rax
0x180045c0e  jnz     short loc_180045C1A
0x180045c10  mov     eax, 80004005h
0x180045c15  jmp     loc_180045CBE
0x180045c1a  xor     eax, eax
0x180045c1c  mov     rcx, rdi
0x180045c1f  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180045c24  mov     [rsp+58h+var_20], eax
0x180045c28  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045c2d  mov     rdx, rax; unsigned __int16 *
0x180045c30  lea     r8, [rsp+58h+SystemTimeAsFileTime]; struct RetailDemoStartup::BLOCKEDITEMINFO *
0x180045c35  mov     rcx, rbx; this
0x180045c38  call    ?GetBlockedItemInfo@StartupApproval@RetailDemoStartup@@QEAAJPEBGPEAUBLOCKEDITEMINFO@2@@Z; RetailDemoStartup::StartupApproval::GetBlockedItemInfo(ushort const *,RetailDemoStartup::BLOCKEDITEMINFO *)
0x180045c3d  cmp     eax, 2
0x180045c40  jz      short loc_180045C4D
0x180045c42  test    eax, eax
0x180045c44  jz      short loc_180045C4D
0x180045c46  cmp     eax, 65Eh
0x180045c4b  jnz     short loc_180045CAB
0x180045c4d  test    sil, sil
0x180045c50  jz      short loc_180045C60
0x180045c52  and     [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0FFFFFFFEh
0x180045c57  xor     eax, eax
0x180045c59  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwHighDateTime], rax
0x180045c5e  jmp     short loc_180045C70
0x180045c60  or      [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 1
0x180045c65  lea     rcx, [rsp+58h+SystemTimeAsFileTime.dwHighDateTime]; lpSystemTimeAsFileTime
0x180045c6a  call    cs:__imp_GetSystemTimeAsFileTime
0x180045c70  mov     rcx, rdi
0x180045c73  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045c78  cmp     byte ptr [rbx], 0
0x180045c7b  jz      short loc_180045CB1
0x180045c7d  test    byte ptr [rbx+10h], 2
0x180045c81  jz      short loc_180045CB1
0x180045c83  lea     rcx, [rsp+58h+SystemTimeAsFileTime]
0x180045c88  mov     [rsp+58h+cbData], 0Ch; cbData
0x180045c90  mov     [rsp+58h+lpData], rcx; lpData
0x180045c95  mov     r9d, 3; dwType
0x180045c9b  mov     rcx, [rbx+8]; hKey
0x180045c9f  xor     r8d, r8d; Reserved
0x180045ca2  mov     rdx, rax; lpValueName
0x180045ca5  call    cs:__imp_RegSetValueExW
0x180045cab  test    eax, eax
0x180045cad  jle     short loc_180045CBE
0x180045caf  jmp     short loc_180045CB6
0x180045cb1  mov     eax, 57h ; 'W'
0x180045cb6  movzx   eax, ax
0x180045cb9  or      eax, 80070000h
0x180045cbe  mov     rcx, [rsp+58h+var_18]
0x180045cc3  xor     rcx, rsp; StackCookie
0x180045cc6  call    __security_check_cookie
0x180045ccb  mov     rbx, [rsp+58h+arg_0]
0x180045cd0  mov     rsi, [rsp+58h+arg_10]
0x180045cd5  add     rsp, 50h
0x180045cd9  pop     rdi
0x180045cda  retn
```
