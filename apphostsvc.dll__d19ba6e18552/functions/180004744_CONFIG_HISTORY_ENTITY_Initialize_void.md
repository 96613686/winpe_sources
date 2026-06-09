# CONFIG_HISTORY_ENTITY::Initialize(void)

- ea: `0x180004744`
- end: `0x18000488d`
- name: `?Initialize@CONFIG_HISTORY_ENTITY@@QEAAJXZ`
- size: `329`
- prototype: `__int64 __fastcall(CONFIG_HISTORY_ENTITY *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002e20`

## callees

- `0x180002cf0`
- `0x180004744`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180004801`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180004824`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180004801`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180004824`
- `iisutil!PuDbgPrintError` at `0x18000487a`
- `iisutil!PuDbgPrintError` at `0x18000487a`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x180004768`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x180004792`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x1800047b0`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x180004768`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x180004792`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x1800047b0`

## string_xrefs

- `0x1800047e4`: `administration.config`
- `0x1800047c7`: `applicationHost.config`
- `0x180004854`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\config_history_entity.cxx`
- `0x18000475e`: `%windir%\system32\inetsrv\config\applicationhost.config`
- `0x180004788`: `%windir%\system32\inetsrv\config\administration.config`
- `0x1800047a9`: `%windir%\system32\inetsrv\config\schema`
- `0x180004846`: `CONFIG_HISTORY_ENTITY::Initialize`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY_ENTITY::Initialize(CONFIG_HISTORY_ENTITY *this)
{
  _WORD *v1; // rdx
  STRU_PATH *v3; // rcx
  int v4; // ebx
  DWORD FileAttributesW; // eax
  BOOL v6; // eax
  const WCHAR *v7; // rcx
  DWORD v8; // eax

  v1 = (_WORD *)*((_QWORD *)this + 13);
  v3 = (CONFIG_HISTORY_ENTITY *)((char *)this + 72);
  *v1 = 0;
  *((_DWORD *)v3 + 12) = 0;
  v4 = STRU_PATH::ExpandEnvironmentVariables(v3, L"%windir%\\system32\\inetsrv\\config\\applicationhost.config");
  if ( v4 >= 0 )
  {
    **((_WORD **)this + 21) = 0;
    *((_DWORD *)this + 46) = 0;
    v4 = STRU_PATH::ExpandEnvironmentVariables(
           (CONFIG_HISTORY_ENTITY *)((char *)this + 136),
           L"%windir%\\system32\\inetsrv\\config\\administration.config");
    if ( v4 >= 0 )
    {
      v4 = STRU_PATH::ExpandEnvironmentVariables(
             (CONFIG_HISTORY_ENTITY *)((char *)this + 216),
             L"%windir%\\system32\\inetsrv\\config\\schema");
      if ( v4 >= 0 )
      {
        v4 = SMALL_STRU::Copy((CONFIG_HISTORY_ENTITY *)((char *)this + 208), L"applicationHost.config");
        if ( v4 >= 0 )
        {
          v4 = SMALL_STRU::Copy((CONFIG_HISTORY_ENTITY *)((char *)this + 200), L"administration.config");
          if ( v4 >= 0 )
          {
            FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 21));
            v6 = FileAttributesW != -1 && FileAttributesW != 16;
            v7 = (const WCHAR *)*((_QWORD *)this + 13);
            *((_DWORD *)this + 70) = v6;
            v8 = GetFileAttributesW(v7);
            if ( v8 == -1 || v8 == 16 )
            {
              v4 = -2147024894;
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\config_history_entity.cxx",
                  957,
                  "CONFIG_HISTORY_ENTITY::Initialize",
                  -2147024894,
                  "%S file doesn't exist !!!.\n",
                  *((const wchar_t **)this + 13));
            }
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004744  mov     [rsp+arg_0], rbx
0x180004749  push    rdi
0x18000474a  sub     rsp, 40h
0x18000474e  mov     rdx, [rcx+68h]
0x180004752  xor     eax, eax
0x180004754  mov     rdi, rcx
0x180004757  add     rcx, 48h ; 'H'
0x18000475b  mov     [rdx], ax
0x18000475e  lea     rdx, aWindirSystem32_0; "%windir%\\system32\\inetsrv\\config\\ap"...
0x180004765  mov     [rcx+30h], eax
0x180004768  call    cs:__imp_?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z; STRU_PATH::ExpandEnvironmentVariables(ushort *)
0x18000476e  mov     ebx, eax
0x180004770  test    eax, eax
0x180004772  js      loc_180004880
0x180004778  lea     rcx, [rdi+88h]
0x18000477f  xor     eax, eax
0x180004781  mov     rdx, [rcx+20h]
0x180004785  mov     [rdx], ax
0x180004788  lea     rdx, aWindirSystem32_2; "%windir%\\system32\\inetsrv\\config\\ad"...
0x18000478f  mov     [rcx+30h], eax
0x180004792  call    cs:__imp_?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z; STRU_PATH::ExpandEnvironmentVariables(ushort *)
0x180004798  mov     ebx, eax
0x18000479a  test    eax, eax
0x18000479c  js      loc_180004880
0x1800047a2  lea     rcx, [rdi+0D8h]
0x1800047a9  lea     rdx, aWindirSystem32_3; "%windir%\\system32\\inetsrv\\config\\sc"...
0x1800047b0  call    cs:__imp_?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z; STRU_PATH::ExpandEnvironmentVariables(ushort *)
0x1800047b6  mov     ebx, eax
0x1800047b8  test    eax, eax
0x1800047ba  js      loc_180004880
0x1800047c0  lea     rcx, [rdi+0D0h]; this
0x1800047c7  lea     rdx, aApplicationhos; "applicationHost.config"
0x1800047ce  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x1800047d3  mov     ebx, eax
0x1800047d5  test    eax, eax
0x1800047d7  js      loc_180004880
0x1800047dd  lea     rcx, [rdi+0C8h]; this
0x1800047e4  lea     rdx, aAdministration; "administration.config"
0x1800047eb  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x1800047f0  mov     ebx, eax
0x1800047f2  test    eax, eax
0x1800047f4  js      loc_180004880
0x1800047fa  mov     rcx, [rdi+0A8h]; lpFileName
0x180004801  call    cs:__imp_GetFileAttributesW
0x180004807  cmp     eax, 0FFFFFFFFh
0x18000480a  jz      short loc_180004818
0x18000480c  cmp     eax, 10h
0x18000480f  jz      short loc_180004818
0x180004811  mov     eax, 1
0x180004816  jmp     short loc_18000481A
0x180004818  xor     eax, eax
0x18000481a  mov     rcx, [rdi+68h]; lpFileName
0x18000481e  mov     [rdi+118h], eax
0x180004824  call    cs:__imp_GetFileAttributesW
0x18000482a  cmp     eax, 0FFFFFFFFh
0x18000482d  jz      short loc_180004834
0x18000482f  cmp     eax, 10h
0x180004832  jnz     short loc_180004880
0x180004834  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000483b  mov     ebx, 80070002h
0x180004840  jz      short loc_180004880
0x180004842  mov     rax, [rdi+68h]
0x180004846  lea     r9, aConfigHistoryE_2; "CONFIG_HISTORY_ENTITY::Initialize"
0x18000484d  mov     rcx, cs:g_pDebug
0x180004854  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000485b  mov     [rsp+48h+var_18], rax
0x180004860  mov     r8d, 3BDh
0x180004866  lea     rax, aSFileDoesnTExi; "%S file doesn't exist !!!.\n"
0x18000486d  mov     [rsp+48h+var_20], rax
0x180004872  mov     [rsp+48h+var_28], 80070002h
0x18000487a  call    cs:__imp_PuDbgPrintError
0x180004880  mov     eax, ebx
0x180004882  mov     rbx, [rsp+48h+arg_0]
0x180004887  add     rsp, 40h
0x18000488b  pop     rdi
0x18000488c  retn
```
