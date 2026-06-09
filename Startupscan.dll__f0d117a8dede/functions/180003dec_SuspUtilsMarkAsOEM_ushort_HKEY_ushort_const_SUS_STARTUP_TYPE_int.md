# SuspUtilsMarkAsOEM(ushort *,HKEY__ *,ushort const *,_SUS_STARTUP_TYPE,int)

- ea: `0x180003dec`
- end: `0x180003f1e`
- name: `?SuspUtilsMarkAsOEM@@YAJPEAGPEAUHKEY__@@PEBGW4_SUS_STARTUP_TYPE@@H@Z`
- size: `306`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY, const WCHAR *, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002c64`
- `0x180003164`

## callees

- `0x180003a28`
- `0x180003ac4`
- `0x180003c04`
- `0x180003dec`
- `0x180004130`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003ecc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003ecc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ef9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ef9`

## pseudocode

```c
__int64 __fastcall SuspUtilsMarkAsOEM(const unsigned __int16 *a1, HKEY a2, const WCHAR *a3, int a4, int a5)
{
  bool v9; // zf
  const WCHAR *v10; // r9
  const WCHAR *v11; // rax
  int BlockedItemInfo; // eax
  unsigned int v13; // ebx
  bool v14; // cc
  LSTATUS v15; // eax
  unsigned int lpData; // [rsp+20h] [rbp-58h]
  HKEY hKey[2]; // [rsp+30h] [rbp-48h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-38h] BYREF
  int v20; // [rsp+48h] [rbp-30h]

  StartupDB::StartupApproval::StartupApproval((StartupDB::StartupApproval *)hKey);
  *(_QWORD *)Data = 0;
  v20 = 0;
  if ( a4 )
  {
    v10 = L"StartupFolder";
    v9 = a4 == 1;
    v11 = &dword_180006DB4;
  }
  else
  {
    v9 = a5 == 1;
    v10 = L"Run32";
    v11 = L"Run";
  }
  if ( !v9 )
    v10 = v11;
  BlockedItemInfo = StartupDB::StartupApproval::Initialize(hKey, a2, a3, v10, lpData);
  v13 = BlockedItemInfo;
  v14 = BlockedItemInfo <= 0;
  if ( BlockedItemInfo )
    goto LABEL_7;
  BlockedItemInfo = StartupDB::StartupApproval::GetBlockedItemInfo(
                      (StartupDB::StartupApproval *)hKey,
                      a1,
                      (struct StartupDB::BLOCKEDITEMINFO *)Data);
  v13 = BlockedItemInfo;
  if ( BlockedItemInfo != 2 && BlockedItemInfo && BlockedItemInfo != 1630 )
  {
    v14 = BlockedItemInfo <= 0;
LABEL_7:
    if ( v14 )
      goto LABEL_21;
    v13 = (unsigned __int16)BlockedItemInfo;
    goto LABEL_20;
  }
  *(_DWORD *)Data |= 4u;
  if ( hKey[0] <= (HKEY)2 )
  {
    LOWORD(v13) = 5;
  }
  else
  {
    v15 = RegSetValueExW(hKey[0], a1, 0, 3u, Data, 0xCu);
    v13 = v15;
    if ( !v15 )
    {
      v13 = 0;
      goto LABEL_21;
    }
    if ( v15 <= 0 )
      goto LABEL_21;
  }
  v13 = (unsigned __int16)v13;
LABEL_20:
  v13 |= 0x80070000;
LABEL_21:
  if ( hKey[0] > (HKEY)2 )
    RegCloseKey(hKey[0]);
  return v13;
}

```

## disassembly

```asm
0x180003dec  mov     [rsp+arg_18], rbx
0x180003df1  push    rbp
0x180003df2  push    rsi
0x180003df3  push    rdi
0x180003df4  sub     rsp, 60h
0x180003df8  mov     rax, cs:__security_cookie
0x180003dff  xor     rax, rsp
0x180003e02  mov     [rsp+78h+var_28], rax
0x180003e07  mov     rdi, rcx
0x180003e0a  mov     ebx, r9d
0x180003e0d  lea     rcx, [rsp+78h+hKey]; this
0x180003e12  mov     rbp, r8
0x180003e15  mov     rsi, rdx
0x180003e18  call    ??0StartupApproval@StartupDB@@QEAA@XZ; StartupDB::StartupApproval::StartupApproval(void)
0x180003e1d  xor     eax, eax
0x180003e1f  mov     qword ptr [rsp+78h+Data], rax
0x180003e24  mov     [rsp+78h+var_30], eax
0x180003e28  test    ebx, ebx
0x180003e2a  jnz     short loc_180003E44
0x180003e2c  cmp     [rsp+78h+arg_20], 1
0x180003e34  lea     r9, aRun32; "Run32"
0x180003e3b  lea     rax, aRun; "Run"
0x180003e42  jmp     short loc_180003E55
0x180003e44  lea     r9, aStartupfolder; "StartupFolder"
0x180003e4b  cmp     ebx, 1
0x180003e4e  lea     rax, dword_180006DB4
0x180003e55  cmovnz  r9, rax; LPCWSTR
0x180003e59  lea     rcx, [rsp+78h+hKey]; phkResult
0x180003e5e  mov     r8, rbp; lpSubKey
0x180003e61  mov     rdx, rsi; hKey
0x180003e64  call    ?Initialize@StartupApproval@StartupDB@@QEAAJPEAUHKEY__@@PEBG1K@Z; StartupDB::StartupApproval::Initialize(HKEY__ *,ushort const *,ushort const *,ulong)
0x180003e69  mov     ebx, eax
0x180003e6b  test    eax, eax
0x180003e6d  jz      short loc_180003E76
0x180003e6f  jle     short loc_180003EEE
0x180003e71  movzx   ebx, ax
0x180003e74  jmp     short loc_180003EE8
0x180003e76  lea     r8, [rsp+78h+Data]; struct StartupDB::BLOCKEDITEMINFO *
0x180003e7b  mov     rdx, rdi; unsigned __int16 *
0x180003e7e  lea     rcx, [rsp+78h+hKey]; this
0x180003e83  call    ?GetBlockedItemInfo@StartupApproval@StartupDB@@QEAAJPEBGPEAUBLOCKEDITEMINFO@2@@Z; StartupDB::StartupApproval::GetBlockedItemInfo(ushort const *,StartupDB::BLOCKEDITEMINFO *)
0x180003e88  mov     ebx, eax
0x180003e8a  cmp     eax, 2
0x180003e8d  jz      short loc_180003E9E
0x180003e8f  test    eax, eax
0x180003e91  jz      short loc_180003E9E
0x180003e93  cmp     eax, 65Eh
0x180003e98  jz      short loc_180003E9E
0x180003e9a  test    eax, eax
0x180003e9c  jmp     short loc_180003E6F
0x180003e9e  or      dword ptr [rsp+78h+Data], 4
0x180003ea3  mov     rcx, [rsp+78h+hKey]; hKey
0x180003ea8  cmp     rcx, 2
0x180003eac  jbe     short loc_180003EE0
0x180003eae  lea     rax, [rsp+78h+Data]
0x180003eb3  mov     [rsp+78h+cbData], 0Ch; cbData
0x180003ebb  mov     r9d, 3; dwType
0x180003ec1  mov     [rsp+78h+lpData], rax; lpData
0x180003ec6  xor     r8d, r8d; Reserved
0x180003ec9  mov     rdx, rdi; lpValueName
0x180003ecc  call    cs:__imp_RegSetValueExW
0x180003ed2  mov     ebx, eax
0x180003ed4  test    eax, eax
0x180003ed6  jz      short loc_180003EDC
0x180003ed8  jle     short loc_180003EEE
0x180003eda  jmp     short loc_180003EE5
0x180003edc  xor     ebx, ebx
0x180003ede  jmp     short loc_180003EEE
0x180003ee0  mov     ebx, 5
0x180003ee5  movzx   ebx, bx
0x180003ee8  or      ebx, 80070000h
0x180003eee  mov     rcx, [rsp+78h+hKey]; hKey
0x180003ef3  cmp     rcx, 2
0x180003ef7  jbe     short loc_180003EFF
0x180003ef9  call    cs:__imp_RegCloseKey
0x180003eff  mov     eax, ebx
0x180003f01  mov     rcx, [rsp+78h+var_28]
0x180003f06  xor     rcx, rsp; StackCookie
0x180003f09  call    __security_check_cookie
0x180003f0e  mov     rbx, [rsp+78h+arg_18]
0x180003f16  add     rsp, 60h
0x180003f1a  pop     rdi
0x180003f1b  pop     rsi
0x180003f1c  pop     rbp
0x180003f1d  retn
```
