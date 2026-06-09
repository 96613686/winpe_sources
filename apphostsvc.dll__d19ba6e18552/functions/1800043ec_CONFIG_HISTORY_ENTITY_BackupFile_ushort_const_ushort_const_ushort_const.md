# CONFIG_HISTORY_ENTITY::BackupFile(ushort const *,ushort const *,ushort const *)

- ea: `0x1800043ec`
- end: `0x180004520`
- name: `?BackupFile@CONFIG_HISTORY_ENTITY@@QEAAJPEBG00@Z`
- size: `308`
- prototype: `__int64 __fastcall(CONFIG_HISTORY_ENTITY *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004b0c`

## callees

- `0x1800043ec`
- `0x180008c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000447f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000447f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004489`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180004475`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180004475`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800044fd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800044fd`
- `iisutil!PuDbgPrintError` at `0x1800044f1`
- `iisutil!PuDbgPrintError` at `0x1800044f1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004426`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004426`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004442`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000445a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004442`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000445a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004417`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004417`

## string_xrefs

- `0x1800044e3`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history_entity.cxx`
- `0x1800044c6`: `CopyFile(%S, %S, %d) failed.\n`
- `0x1800044d6`: `CONFIG_HISTORY_ENTITY::BackupFile`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY_ENTITY::BackupFile(
        CONFIG_HISTORY_ENTITY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  signed int v7; // ebx
  signed int LastError; // eax
  _BYTE v10[32]; // [rsp+50h] [rbp-58h] BYREF
  LPCWSTR lpNewFileName; // [rsp+70h] [rbp-38h]

  STRU::STRU((STRU *)v10);
  v7 = STRU::Copy((STRU *)v10, a2);
  if ( v7 >= 0 )
  {
    v7 = STRU::Append((STRU *)v10, L"\\");
    if ( v7 >= 0 )
    {
      v7 = STRU::Append((STRU *)v10, a4);
      if ( v7 >= 0 && !CopyFileW(a3, lpNewFileName, 0) )
      {
        if ( GetLastError() )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v7 = -2147467259;
        }
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history_entity.cxx",
            883,
            "CONFIG_HISTORY_ENTITY::BackupFile",
            v7,
            "CopyFile(%S, %S, %d) failed.\n",
            a3,
            lpNewFileName,
            0);
      }
    }
  }
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800043ec  push    rbx
0x1800043ee  push    rsi
0x1800043ef  push    rdi
0x1800043f0  sub     rsp, 90h
0x1800043f7  mov     rax, cs:__security_cookie
0x1800043fe  xor     rax, rsp
0x180004401  mov     [rsp+0A8h+var_20], rax
0x180004409  mov     rsi, r9
0x18000440c  mov     rdi, r8
0x18000440f  mov     rbx, rdx
0x180004412  lea     rcx, [rsp+0A8h+var_58]
0x180004417  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000441d  nop
0x18000441e  mov     rdx, rbx
0x180004421  lea     rcx, [rsp+0A8h+var_58]
0x180004426  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000442c  mov     ebx, eax
0x18000442e  test    eax, eax
0x180004430  js      loc_1800044F8
0x180004436  lea     rdx, asc_18000BAE0; "\\"
0x18000443d  lea     rcx, [rsp+0A8h+var_58]
0x180004442  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004448  mov     ebx, eax
0x18000444a  test    eax, eax
0x18000444c  js      loc_1800044F8
0x180004452  mov     rdx, rsi
0x180004455  lea     rcx, [rsp+0A8h+var_58]
0x18000445a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004460  mov     ebx, eax
0x180004462  test    eax, eax
0x180004464  js      loc_1800044F8
0x18000446a  xor     r8d, r8d; bFailIfExists
0x18000446d  mov     rdx, [rsp+0A8h+lpNewFileName]; lpNewFileName
0x180004472  mov     rcx, rdi; lpExistingFileName
0x180004475  call    cs:__imp_CopyFileW
0x18000447b  test    eax, eax
0x18000447d  jnz     short loc_1800044F8
0x18000447f  call    cs:__imp_GetLastError
0x180004485  test    eax, eax
0x180004487  jz      short loc_1800044A0
0x180004489  call    cs:__imp_GetLastError
0x18000448f  mov     ebx, eax
0x180004491  test    eax, eax
0x180004493  jle     short loc_1800044A5
0x180004495  movzx   ebx, ax
0x180004498  or      ebx, 80070000h
0x18000449e  jmp     short loc_1800044A5
0x1800044a0  mov     ebx, 80004005h
0x1800044a5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800044ac  jz      short loc_1800044F8
0x1800044ae  mov     [rsp+0A8h+var_68], 0
0x1800044b7  mov     rax, [rsp+0A8h+lpNewFileName]
0x1800044bc  mov     [rsp+0A8h+var_70], rax
0x1800044c1  mov     [rsp+0A8h+var_78], rdi
0x1800044c6  lea     rax, aCopyfileSSDFai; "CopyFile(%S, %S, %d) failed.\n"
0x1800044cd  mov     [rsp+0A8h+var_80], rax
0x1800044d2  mov     [rsp+0A8h+var_88], ebx
0x1800044d6  lea     r9, aConfigHistoryE_0; "CONFIG_HISTORY_ENTITY::BackupFile"
0x1800044dd  mov     r8d, 373h
0x1800044e3  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800044ea  mov     rcx, cs:g_pDebug
0x1800044f1  call    cs:__imp_PuDbgPrintError
0x1800044f7  nop
0x1800044f8  lea     rcx, [rsp+0A8h+var_58]
0x1800044fd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004503  mov     eax, ebx
0x180004505  mov     rcx, [rsp+0A8h+var_20]
0x18000450d  xor     rcx, rsp; StackCookie
0x180004510  call    __security_check_cookie
0x180004515  add     rsp, 90h
0x18000451c  pop     rdi
0x18000451d  pop     rsi
0x18000451e  pop     rbx
0x18000451f  retn
```
