# RunManager::CheckGroupPolicy(void)

- ea: `0x18000ab00`
- end: `0x18000ac60`
- name: `?CheckGroupPolicy@RunManager@@MEAAHXZ`
- size: `352`
- prototype: `_BOOL8 __fastcall(RunManager *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001720`
- `0x180001fec`
- `0x18000ab00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ab7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ab7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab90`

## pseudocode

```c
_BOOL8 __fastcall RunManager::CheckGroupPolicy(RunManager *this)
{
  BOOL v2; // ebx
  __int64 v3; // rdx
  HKEY v4; // rcx
  __int64 v5; // r8
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  HKEY hKey; // [rsp+60h] [rbp+17h] BYREF
  char *v11; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v12; // [rsp+70h] [rbp+27h] BYREF
  const char *v13; // [rsp+78h] [rbp+2Fh] BYREF
  const char *v14; // [rsp+80h] [rbp+37h] BYREF
  char *v15; // [rsp+88h] [rbp+3Fh] BYREF
  BOOL Data; // [rsp+B8h] [rbp+6Fh] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+77h] BYREF
  int v18; // [rsp+C8h] [rbp+7Fh] BYREF

  hKey = 0;
  v2 = 1;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows\\ScriptedDiagnostics",
          0,
          0x20019u,
          &hKey) )
  {
    v4 = hKey;
    if ( hKey )
    {
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"EnableDiagnostics", 0, 0, (LPBYTE)&Data, &cbData) )
        v2 = Data;
      RegCloseKey(hKey);
      hKey = 0;
    }
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v4, v3, v5) )
  {
    Data = v2;
    v11 = (char *)this + 112;
    cbData = 287;
    v12 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\runmanager\\lib\\runmanager.cpp";
    v13 = "RunManager::CheckGroupPolicy";
    v14 = "Check group policy";
    v15 = (char *)this + 241;
    v18 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)&unk_18002FD90,
      v7,
      v8,
      (__int64)&v15,
      (__int64)&v18,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&cbData,
      (__int64)&v11,
      (__int64)&Data);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ab00  push    rbp
0x18000ab02  push    rbx
0x18000ab03  push    rdi
0x18000ab04  lea     rbp, [rsp-47h]
0x18000ab09  sub     rsp, 90h
0x18000ab10  mov     rdi, rcx
0x18000ab13  mov     [rbp+57h+hKey], 0
0x18000ab1b  lea     rax, [rbp+57h+hKey]
0x18000ab1f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ab26  mov     r9d, 20019h; samDesired
0x18000ab2c  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18000ab31  xor     r8d, r8d; ulOptions
0x18000ab34  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x18000ab3b  mov     ebx, 1
0x18000ab40  call    cs:__imp_RegOpenKeyExW
0x18000ab46  test    eax, eax
0x18000ab48  jnz     short loc_18000AB9E
0x18000ab4a  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ab4e  test    rcx, rcx
0x18000ab51  jz      short loc_18000AB9E
0x18000ab53  mov     [rbp+57h+Data], eax
0x18000ab56  lea     rdx, ValueName; "EnableDiagnostics"
0x18000ab5d  lea     rax, [rbp+57h+cbData]
0x18000ab61  mov     [rbp+57h+cbData], 4
0x18000ab68  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18000ab6d  xor     r9d, r9d; lpType
0x18000ab70  lea     rax, [rbp+57h+Data]
0x18000ab74  xor     r8d, r8d; lpReserved
0x18000ab77  mov     [rsp+0A0h+phkResult], rax; lpData
0x18000ab7c  call    cs:__imp_RegQueryValueExW
0x18000ab82  test    eax, eax
0x18000ab84  jnz     short loc_18000AB8C
0x18000ab86  cmp     [rbp+57h+Data], eax
0x18000ab89  cmovz   ebx, eax
0x18000ab8c  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ab90  call    cs:__imp_RegCloseKey
0x18000ab96  mov     [rbp+57h+hKey], 0
0x18000ab9e  mov     eax, cs:dword_180039000
0x18000aba4  cmp     eax, 5
0x18000aba7  jbe     loc_18000AC53
0x18000abad  call    _tlgKeywordOn
0x18000abb2  test    al, al
0x18000abb4  jz      loc_18000AC53
0x18000abba  lea     rax, [rdi+70h]
0x18000abbe  mov     [rbp+57h+Data], ebx
0x18000abc1  mov     [rbp+57h+var_38], rax
0x18000abc5  lea     rdx, unk_18002FD90
0x18000abcc  lea     rax, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18000abd3  mov     [rbp+57h+cbData], 11Fh
0x18000abda  mov     [rbp+57h+var_30], rax
0x18000abde  lea     rax, aRunmanagerChec; "RunManager::CheckGroupPolicy"
0x18000abe5  mov     [rbp+57h+var_28], rax
0x18000abe9  lea     rax, aCheckGroupPoli; "Check group policy"
0x18000abf0  mov     [rbp+57h+var_20], rax
0x18000abf4  lea     rax, [rdi+0F1h]
0x18000abfb  mov     [rbp+57h+var_18], rax
0x18000abff  lea     rax, [rbp+57h+Data]
0x18000ac03  mov     [rsp+0A0h+var_48], rax
0x18000ac08  lea     rax, [rbp+57h+var_38]
0x18000ac0c  mov     [rsp+0A0h+var_50], rax
0x18000ac11  lea     rax, [rbp+57h+cbData]
0x18000ac15  mov     [rsp+0A0h+var_58], rax
0x18000ac1a  lea     rax, [rbp+57h+var_30]
0x18000ac1e  mov     [rsp+0A0h+var_60], rax
0x18000ac23  lea     rax, [rbp+57h+var_28]
0x18000ac27  mov     [rsp+0A0h+var_68], rax
0x18000ac2c  lea     rax, [rbp+57h+var_20]
0x18000ac30  mov     [rsp+0A0h+var_70], rax
0x18000ac35  lea     rax, [rbp+57h+arg_18]
0x18000ac39  mov     [rsp+0A0h+lpcbData], rax
0x18000ac3e  lea     rax, [rbp+57h+var_18]
0x18000ac42  mov     [rsp+0A0h+phkResult], rax
0x18000ac47  mov     [rbp+57h+arg_18], 0
0x18000ac4e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@333434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000ac53  mov     eax, ebx
0x18000ac55  add     rsp, 90h
0x18000ac5c  pop     rdi
0x18000ac5d  pop     rbx
0x18000ac5e  pop     rbp
0x18000ac5f  retn
```
