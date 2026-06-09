# SuspUtilsCheckFlags(ulong *,ushort *,HKEY__ *,ushort const *,_SUS_STARTUP_TYPE,int)

- ea: `0x180003cfc`
- end: `0x180003de4`
- name: `?SuspUtilsCheckFlags@@YAJPEAKPEAGPEAUHKEY__@@PEBGW4_SUS_STARTUP_TYPE@@H@Z`
- size: `232`
- prototype: `__int64 __fastcall(_DWORD *, const unsigned __int16 *, HKEY, const WCHAR *, int, int)`
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
- `0x180003cfc`
- `0x180004130`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003dc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003dc6`

## pseudocode

```c
__int64 __fastcall SuspUtilsCheckFlags(
        _DWORD *a1,
        const unsigned __int16 *a2,
        HKEY a3,
        const WCHAR *a4,
        int a5,
        int a6)
{
  const WCHAR *v10; // r9
  int BlockedItemInfo; // eax
  unsigned int v12; // ebx
  bool v13; // cc
  unsigned int v15; // [rsp+20h] [rbp-68h]
  HKEY hKey[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v17; // [rsp+40h] [rbp-48h] BYREF
  int v18; // [rsp+48h] [rbp-40h]

  StartupDB::StartupApproval::StartupApproval((StartupDB::StartupApproval *)hKey);
  v17 = 0;
  v18 = 0;
  *a1 = 0;
  if ( a5 )
  {
    v10 = L"StartupFolder";
    if ( a5 != 1 )
      v10 = &dword_180006DB4;
  }
  else
  {
    v10 = L"Run32";
    if ( a6 != 1 )
      v10 = L"Run";
  }
  BlockedItemInfo = StartupDB::StartupApproval::Initialize(hKey, a3, a4, v10, v15);
  v12 = BlockedItemInfo;
  v13 = BlockedItemInfo <= 0;
  if ( BlockedItemInfo )
    goto LABEL_8;
  BlockedItemInfo = StartupDB::StartupApproval::GetBlockedItemInfo(
                      (StartupDB::StartupApproval *)hKey,
                      a2,
                      (struct StartupDB::BLOCKEDITEMINFO *)&v17);
  v12 = BlockedItemInfo;
  if ( BlockedItemInfo == 2 )
  {
LABEL_13:
    v12 = 0;
    goto LABEL_14;
  }
  v13 = BlockedItemInfo <= 0;
  if ( !BlockedItemInfo )
  {
    *a1 = v17;
    goto LABEL_13;
  }
LABEL_8:
  if ( !v13 )
    v12 = (unsigned __int16)BlockedItemInfo | 0x80070000;
LABEL_14:
  if ( hKey[0] > (HKEY)2 )
    RegCloseKey(hKey[0]);
  return v12;
}

```

## disassembly

```asm
0x180003cfc  push    rbx
0x180003cfe  push    rbp
0x180003cff  push    rsi
0x180003d00  push    rdi
0x180003d01  sub     rsp, 68h
0x180003d05  mov     rax, cs:__security_cookie
0x180003d0c  xor     rax, rsp
0x180003d0f  mov     [rsp+88h+var_38], rax
0x180003d14  mov     rdi, rcx
0x180003d17  mov     rbp, r9
0x180003d1a  lea     rcx, [rsp+88h+hKey]; this
0x180003d1f  mov     rbx, r8
0x180003d22  mov     rsi, rdx
0x180003d25  call    ??0StartupApproval@StartupDB@@QEAA@XZ; StartupDB::StartupApproval::StartupApproval(void)
0x180003d2a  xor     eax, eax
0x180003d2c  mov     [rsp+88h+var_48], rax
0x180003d31  mov     [rsp+88h+var_40], eax
0x180003d35  mov     [rdi], eax
0x180003d37  mov     eax, [rsp+88h+arg_20]
0x180003d3e  test    eax, eax
0x180003d40  jnz     short loc_180003D5E
0x180003d42  cmp     [rsp+88h+arg_28], 1
0x180003d4a  lea     r9, aRun32; "Run32"
0x180003d51  lea     rax, aRun; "Run"
0x180003d58  cmovnz  r9, rax
0x180003d5c  jmp     short loc_180003D73
0x180003d5e  cmp     eax, 1
0x180003d61  lea     r9, aStartupfolder; "StartupFolder"
0x180003d68  lea     rcx, dword_180006DB4
0x180003d6f  cmovnz  r9, rcx; LPCWSTR
0x180003d73  mov     r8, rbp; lpSubKey
0x180003d76  lea     rcx, [rsp+88h+hKey]; phkResult
0x180003d7b  mov     rdx, rbx; hKey
0x180003d7e  call    ?Initialize@StartupApproval@StartupDB@@QEAAJPEAUHKEY__@@PEBG1K@Z; StartupDB::StartupApproval::Initialize(HKEY__ *,ushort const *,ushort const *,ulong)
0x180003d83  mov     ebx, eax
0x180003d85  test    eax, eax
0x180003d87  jz      short loc_180003D96
0x180003d89  jle     short loc_180003DBB
0x180003d8b  movzx   ebx, ax
0x180003d8e  or      ebx, 80070000h
0x180003d94  jmp     short loc_180003DBB
0x180003d96  lea     r8, [rsp+88h+var_48]; struct StartupDB::BLOCKEDITEMINFO *
0x180003d9b  mov     rdx, rsi; unsigned __int16 *
0x180003d9e  lea     rcx, [rsp+88h+hKey]; this
0x180003da3  call    ?GetBlockedItemInfo@StartupApproval@StartupDB@@QEAAJPEBGPEAUBLOCKEDITEMINFO@2@@Z; StartupDB::StartupApproval::GetBlockedItemInfo(ushort const *,StartupDB::BLOCKEDITEMINFO *)
0x180003da8  mov     ebx, eax
0x180003daa  cmp     eax, 2
0x180003dad  jz      short loc_180003DB9
0x180003daf  test    eax, eax
0x180003db1  jnz     short loc_180003D89
0x180003db3  mov     eax, dword ptr [rsp+88h+var_48]
0x180003db7  mov     [rdi], eax
0x180003db9  xor     ebx, ebx
0x180003dbb  mov     rcx, [rsp+88h+hKey]; hKey
0x180003dc0  cmp     rcx, 2
0x180003dc4  jbe     short loc_180003DCC
0x180003dc6  call    cs:__imp_RegCloseKey
0x180003dcc  mov     eax, ebx
0x180003dce  mov     rcx, [rsp+88h+var_38]
0x180003dd3  xor     rcx, rsp; StackCookie
0x180003dd6  call    __security_check_cookie
0x180003ddb  add     rsp, 68h
0x180003ddf  pop     rdi
0x180003de0  pop     rsi
0x180003de1  pop     rbp
0x180003de2  pop     rbx
0x180003de3  retn
```
