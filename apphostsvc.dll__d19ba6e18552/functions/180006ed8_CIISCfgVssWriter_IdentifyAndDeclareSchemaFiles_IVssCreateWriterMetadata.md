# CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles(IVssCreateWriterMetadata *)

- ea: `0x180006ed8`
- end: `0x180007117`
- name: `?IdentifyAndDeclareSchemaFiles@CIISCfgVssWriter@@AEAAJPEAVIVssCreateWriterMetadata@@@Z`
- size: `575`
- prototype: `__int64 __fastcall(CIISCfgVssWriter *__hidden this, struct IVssCreateWriterMetadata *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800074c0`

## callees

- `0x180006ed8`
- `0x180008c1f`
- `0x180008c50`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800070d2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800070d2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180007064`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180007064`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180006f8e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180006f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007073`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800070de`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800070e9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800070de`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800070e9`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x1800070f4`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x1800070f4`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x180006f43`
- `iisutil!?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z` at `0x180006f43`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006f5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006fce`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006f5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006fce`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006f76`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006fe7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006f76`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006fe7`
- `iisutil!PuDbgPrint` at `0x1800070ba`
- `iisutil!PuDbgPrint` at `0x1800070ba`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180006f1a`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x180006f1a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006f25`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006f31`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006f25`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006f31`
- `ext-ms-win-wrp-sfc-l1-1-0!SfcIsFileProtected` at `0x180006ffe`
- `ext-ms-win-wrp-sfc-l1-1-0!SfcIsFileProtected` at `0x180006ffe`

## string_xrefs

- `0x1800070ac`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\cfgwriter.cxx`
- `0x180007042`: `IISCONFIG`
- `0x180006f38`: `%windir%\system32\inetsrv\config\schema\`
- `0x18000703b`: `%windir%\system32\inetsrv\config\schema\`
- `0x180006f6b`: `*.xml`
- `0x18000709f`: `CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles`

## pseudocode

```c
__int64 __fastcall CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles(
        CIISCfgVssWriter *this,
        struct IVssCreateWriterMetadata *a2)
{
  signed int v3; // ebx
  HANDLE FirstFileW; // rdi
  signed int LastError; // eax
  signed int v6; // eax
  int v7; // eax
  __int64 v9; // [rsp+28h] [rbp-D8h]
  __int64 v10; // [rsp+38h] [rbp-C8h]
  _BYTE v11[32]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR ProtFileName; // [rsp+70h] [rbp-90h]
  _BYTE v13[32]; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpFileName; // [rsp+A8h] [rbp-58h]
  _BYTE v15[32]; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v16; // [rsp+E0h] [rbp-20h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+100h] [rbp+0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  STRU_PATH::STRU_PATH((STRU_PATH *)v15, 0x5Cu);
  STRU::STRU((STRU *)v13);
  STRU::STRU((STRU *)v11);
  v3 = STRU_PATH::ExpandEnvironmentVariables((STRU_PATH *)v15, L"%windir%\\system32\\inetsrv\\config\\schema\\");
  if ( v3 >= 0 )
  {
    v3 = STRU::Copy((STRU *)v13, v16);
    if ( v3 >= 0 )
    {
      v3 = STRU::Append((STRU *)v13, L"*.xml");
      if ( v3 >= 0 )
      {
        FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
        if ( FirstFileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          if ( LastError != 2 )
          {
            if ( LastError > 0 )
              v3 = (unsigned __int16)LastError | 0x80070000;
            else
              v3 = LastError;
          }
        }
        else
        {
          while ( 1 )
          {
            v3 = STRU::Copy((STRU *)v11, v16);
            if ( v3 < 0 )
              goto LABEL_22;
            v3 = STRU::Append((STRU *)v11, FindFileData.cFileName);
            if ( v3 < 0 )
              goto LABEL_22;
            if ( !SfcIsFileProtected(0, ProtFileName) )
            {
              v6 = GetLastError();
              v3 = v6;
              if ( v6 != 2 )
              {
                if ( v6 <= 0 )
                  goto LABEL_22;
                goto LABEL_21;
              }
              LODWORD(v10) = 3855;
              LOBYTE(v9) = 0;
              v7 = (*(__int64 (**)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, const wchar_t *, ...))(*(_QWORD *)a2 + 40LL))(
                     a2,
                     0,
                     L"IISCONFIG",
                     L"%windir%\\system32\\inetsrv\\config\\schema\\",
                     FindFileData.cFileName,
                     v9,
                     0,
                     v10);
              v3 = v7;
              if ( v7 < 0 )
                break;
            }
            if ( !FindNextFileW(FirstFileW, &FindFileData) )
            {
              v6 = GetLastError();
              if ( v6 == 18 )
                goto LABEL_22;
              if ( v6 <= 0 )
              {
                v3 = v6;
                goto LABEL_22;
              }
LABEL_21:
              v3 = (unsigned __int16)v6 | 0x80070000;
              goto LABEL_22;
            }
          }
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\cfgwriter.cxx",
              440,
              "CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles",
              "Error AddFilesToFileGroup().  hr = %x\n",
              v7);
LABEL_22:
          FindClose(FirstFileW);
        }
      }
    }
  }
  STRU::~STRU((STRU *)v11);
  STRU::~STRU((STRU *)v13);
  STRU_PATH::~STRU_PATH((STRU_PATH *)v15);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006ed8  push    rbp
0x180006eda  push    rbx
0x180006edb  push    rsi
0x180006edc  push    rdi
0x180006edd  lea     rbp, [rsp-268h]
0x180006ee5  sub     rsp, 368h
0x180006eec  mov     rax, cs:__security_cookie
0x180006ef3  xor     rax, rsp
0x180006ef6  mov     [rbp+280h+var_30], rax
0x180006efd  mov     rsi, rdx
0x180006f00  xor     edx, edx; Val
0x180006f02  mov     r8d, 250h; Size
0x180006f08  lea     rcx, [rbp+280h+FindFileData]; void *
0x180006f0c  call    memset_0
0x180006f11  mov     edx, 5Ch ; '\'
0x180006f16  lea     rcx, [rbp+280h+var_2C0]
0x180006f1a  call    cs:__imp_??0STRU_PATH@@QEAA@G@Z; STRU_PATH::STRU_PATH(ushort)
0x180006f20  nop
0x180006f21  lea     rcx, [rbp+280h+var_2F8]
0x180006f25  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006f2b  nop
0x180006f2c  lea     rcx, [rsp+380h+var_330]
0x180006f31  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006f37  nop
0x180006f38  lea     rdx, aWindirSystem32; "%windir%\\system32\\inetsrv\\config\\sc"...
0x180006f3f  lea     rcx, [rbp+280h+var_2C0]
0x180006f43  call    cs:__imp_?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z; STRU_PATH::ExpandEnvironmentVariables(ushort *)
0x180006f49  mov     ebx, eax
0x180006f4b  test    eax, eax
0x180006f4d  js      loc_1800070D9
0x180006f53  mov     rdx, [rbp+280h+var_2A0]
0x180006f57  lea     rcx, [rbp+280h+var_2F8]
0x180006f5b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006f61  mov     ebx, eax
0x180006f63  test    eax, eax
0x180006f65  js      loc_1800070D9
0x180006f6b  lea     rdx, aXml_0; "*.xml"
0x180006f72  lea     rcx, [rbp+280h+var_2F8]
0x180006f76  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180006f7c  mov     ebx, eax
0x180006f7e  test    eax, eax
0x180006f80  js      loc_1800070D9
0x180006f86  lea     rdx, [rbp+280h+FindFileData]; lpFindFileData
0x180006f8a  mov     rcx, [rbp+280h+lpFileName]; lpFileName
0x180006f8e  call    cs:__imp_FindFirstFileW
0x180006f94  mov     rdi, rax
0x180006f97  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006f9b  jnz     short loc_180006FC5
0x180006f9d  call    cs:__imp_GetLastError
0x180006fa3  cmp     eax, 2
0x180006fa6  jz      loc_1800070D9
0x180006fac  test    eax, eax
0x180006fae  jg      short loc_180006FB7
0x180006fb0  mov     ebx, eax
0x180006fb2  jmp     loc_1800070D9
0x180006fb7  movzx   ebx, ax
0x180006fba  or      ebx, 80070000h
0x180006fc0  jmp     loc_1800070D9
0x180006fc5  mov     rdx, [rbp+280h+var_2A0]
0x180006fc9  lea     rcx, [rsp+380h+var_330]
0x180006fce  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006fd4  mov     ebx, eax
0x180006fd6  test    eax, eax
0x180006fd8  js      loc_1800070CF
0x180006fde  lea     rdx, [rbp+280h+FindFileData.cFileName]
0x180006fe2  lea     rcx, [rsp+380h+var_330]
0x180006fe7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180006fed  mov     ebx, eax
0x180006fef  test    eax, eax
0x180006ff1  js      loc_1800070CF
0x180006ff7  mov     rdx, [rsp+380h+ProtFileName]; ProtFileName
0x180006ffc  xor     ecx, ecx; RpcHandle
0x180006ffe  call    cs:__imp_SfcIsFileProtected
0x180007004  test    eax, eax
0x180007006  jnz     short loc_18000705D
0x180007008  call    cs:__imp_GetLastError
0x18000700e  mov     ebx, eax
0x180007010  cmp     eax, 2
0x180007013  jnz     loc_1800070C2
0x180007019  mov     rax, [rsi]
0x18000701c  mov     dword ptr [rsp+380h+var_348], 0F0Fh
0x180007024  mov     [rsp+380h+var_350], 0
0x18000702d  mov     byte ptr [rsp+380h+var_358], 0
0x180007032  lea     rcx, [rbp+280h+FindFileData.cFileName]
0x180007036  mov     [rsp+380h+var_360], rcx
0x18000703b  lea     r9, aWindirSystem32; "%windir%\\system32\\inetsrv\\config\\sc"...
0x180007042  lea     r8, aIisconfig; "IISCONFIG"
0x180007049  xor     edx, edx
0x18000704b  mov     rcx, rsi
0x18000704e  mov     rax, [rax+28h]
0x180007052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007057  mov     ebx, eax
0x180007059  test    eax, eax
0x18000705b  js      short loc_180007086
0x18000705d  lea     rdx, [rbp+280h+FindFileData]; lpFindFileData
0x180007061  mov     rcx, rdi; hFindFile
0x180007064  call    cs:__imp_FindNextFileW
0x18000706a  cmp     eax, 1
0x18000706d  jz      loc_180006FC5
0x180007073  call    cs:__imp_GetLastError
0x180007079  cmp     eax, 12h
0x18000707c  jz      short loc_1800070CF
0x18000707e  test    eax, eax
0x180007080  jg      short loc_1800070C6
0x180007082  mov     ebx, eax
0x180007084  jmp     short loc_1800070CF
0x180007086  test    byte ptr cs:g_dwDebugFlags, 3
0x18000708d  jz      short loc_1800070CF
0x18000708f  mov     dword ptr [rsp+380h+var_358], eax
0x180007093  lea     rax, aErrorAddfilest; "Error AddFilesToFileGroup().  hr = %x\n"
0x18000709a  mov     [rsp+380h+var_360], rax
0x18000709f  lea     r9, aCiiscfgvsswrit_0; "CIISCfgVssWriter::IdentifyAndDeclareSch"...
0x1800070a6  mov     r8d, 1B8h
0x1800070ac  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800070b3  mov     rcx, cs:g_pDebug
0x1800070ba  call    cs:__imp_PuDbgPrint
0x1800070c0  jmp     short loc_1800070CF
0x1800070c2  test    eax, eax
0x1800070c4  jle     short loc_1800070CF
0x1800070c6  movzx   ebx, ax
0x1800070c9  or      ebx, 80070000h
0x1800070cf  mov     rcx, rdi; hFindFile
0x1800070d2  call    cs:__imp_FindClose
0x1800070d8  nop
0x1800070d9  lea     rcx, [rsp+380h+var_330]
0x1800070de  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800070e4  nop
0x1800070e5  lea     rcx, [rbp+280h+var_2F8]
0x1800070e9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800070ef  nop
0x1800070f0  lea     rcx, [rbp+280h+var_2C0]
0x1800070f4  call    cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
0x1800070fa  mov     eax, ebx
0x1800070fc  mov     rcx, [rbp+280h+var_30]
0x180007103  xor     rcx, rsp; StackCookie
0x180007106  call    __security_check_cookie
0x18000710b  add     rsp, 368h
0x180007112  pop     rdi
0x180007113  pop     rsi
0x180007114  pop     rbx
0x180007115  pop     rbp
0x180007116  retn
```
