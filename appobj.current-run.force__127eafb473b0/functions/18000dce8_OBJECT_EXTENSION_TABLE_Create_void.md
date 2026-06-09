# OBJECT_EXTENSION_TABLE::Create(void)

- ea: `0x18000dce8`
- end: `0x18000e050`
- name: `?Create@OBJECT_EXTENSION_TABLE@@QEAAJXZ`
- size: `872`
- prototype: `__int64 __fastcall(OBJECT_EXTENSION_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800067c8`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x18000dce8`
- `0x180033954`
- `0x180033a4c`
- `0x180034cbe`
- `0x180034d00`
- `0x180034d90`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000decc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000decc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000df88`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000df88`
- `OLEAUT32!__imp_SysAllocString` at `0x18000de6f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000df4b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000de6f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000df4b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dfed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dfed`
- `OLEAUT32!__imp_VariantInit` at `0x18000ddac`
- `OLEAUT32!__imp_VariantInit` at `0x18000ddac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000ddbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000ddbe`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000df17`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000df17`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000debd`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000debd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000de59`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000de59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e017`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e017`

## string_xrefs

- `0x18000de68`: `<appcmd>\n    <object name="site" alias="sites" classId="DefaultSiteObject" >\n        <verb name="list" classId="DefaultSiteObject" />    </object>\n</appcmd>\n`
- `0x18000de1a`: `appcmd.xml`

## pseudocode

```c
__int64 __fastcall OBJECT_EXTENSION_TABLE::Create(OBJECT_EXTENSION_TABLE *this)
{
  __int64 FileW; // rsi
  signed int LastError; // eax
  int v4; // ebx
  OLECHAR *v5; // rdi
  DWORD FileSize; // eax
  signed int v7; // eax
  __int64 v8; // rax
  __int64 (__fastcall *v9)(LPVOID, __int128 *); // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+50h] [rbp-B0h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-A0h]
  LPVOID lpBuffer; // [rsp+70h] [rbp-90h]
  unsigned int cbMultiByte; // [rsp+78h] [rbp-88h]
  __int16 v17; // [rsp+7Ch] [rbp-84h]
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v19[32]; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpFileName; // [rsp+B8h] [rbp-48h]
  int v21; // [rsp+C0h] [rbp-40h]
  __int16 v22; // [rsp+C4h] [rbp-3Ch]
  int v23; // [rsp+C8h] [rbp-38h]
  _BYTE v24[32]; // [rsp+D0h] [rbp-30h] BYREF
  OLECHAR *psz; // [rsp+F0h] [rbp-10h]
  int v26; // [rsp+F8h] [rbp-8h]
  __int16 v27; // [rsp+FCh] [rbp-4h]
  int v28; // [rsp+100h] [rbp+0h]
  char v29; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v30[1023]; // [rsp+111h] [rbp+11h] BYREF
  __int16 v31; // [rsp+510h] [rbp+410h] BYREF
  _BYTE v32[510]; // [rsp+512h] [rbp+412h] BYREF
  WCHAR Buffer[264]; // [rsp+710h] [rbp+610h] BYREF
  __int16 v34; // [rsp+920h] [rbp+820h] BYREF
  _BYTE v35[2046]; // [rsp+922h] [rbp+822h] BYREF

  NumberOfBytesRead = 0;
  FileW = -1;
  memset_0(v32, 0, sizeof(v32));
  v21 = 512;
  lpFileName = (LPCWSTR)&v31;
  v22 = 256;
  v23 = 0;
  v31 = 0;
  memset_0(v35, 0, sizeof(v35));
  v26 = 2048;
  psz = (OLECHAR *)&v34;
  v27 = 256;
  v28 = 0;
  v34 = 0;
  ppv = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_24;
  }
  v4 = STRU::Copy((STRU *)v19, Buffer);
  if ( v4 < 0 )
    goto LABEL_24;
  v4 = STRU::Append((STRU *)v19, L"\\inetsrv\\");
  if ( v4 < 0 )
    goto LABEL_24;
  v4 = STRU::Append((STRU *)v19, L"appcmd.xml");
  if ( v4 < 0 )
    goto LABEL_24;
  FileW = (__int64)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == -1 )
  {
    v5 = SysAllocString(
           L"<appcmd>\n"
            "    <object name=\"site\" alias=\"sites\" classId=\"DefaultSiteObject\" >\n"
            "        <verb name=\"list\" classId=\"DefaultSiteObject\" />    </object>\n"
            "</appcmd>\n");
    if ( !v5 )
    {
      v4 = -2147024888;
      goto LABEL_24;
    }
    goto LABEL_20;
  }
  memset_0(v30, 0, sizeof(v30));
  v29 = 0;
  lpBuffer = &v29;
  cbMultiByte = 1024;
  v17 = 256;
  FileSize = GetFileSize((HANDLE)FileW, 0);
  NumberOfBytesRead = FileSize;
  if ( FileSize == -1
    || !BUFFER::Resize((BUFFER *)&v13, FileSize)
    || !ReadFile((HANDLE)FileW, lpBuffer, NumberOfBytesRead, &NumberOfBytesRead, 0) )
  {
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_13;
  }
  v4 = STRU::AuxAppendA((STRU *)v24, (LPCCH)lpBuffer, cbMultiByte, 0, 1, 0);
  if ( v4 < 0 )
  {
LABEL_13:
    BUFFER::~BUFFER((BUFFER *)&v13);
    goto LABEL_24;
  }
  v5 = SysAllocString(psz);
  if ( !v5 )
  {
    v4 = -2147024888;
    goto LABEL_13;
  }
  BUFFER::~BUFFER((BUFFER *)&v13);
LABEL_20:
  v4 = CoCreateInstance(
         &GUID_88d96a0c_f192_11d4_a65f_0040963251e5,
         0,
         0x17u,
         &GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802,
         &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, OBJECT_EXTENSION_TABLE *))(*(_QWORD *)ppv + 80LL))(ppv, this);
    if ( v4 >= 0 )
    {
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)v5;
      v8 = *(_QWORD *)ppv;
      pRecInfo = pvarg.pRecInfo;
      v9 = *(__int64 (__fastcall **)(LPVOID, __int128 *))(v8 + 152);
      v13 = *(_OWORD *)&pvarg.vt;
      v4 = v9(ppv, &v13);
    }
  }
  SysFreeString(v5);
LABEL_24:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  BUFFER::~BUFFER((BUFFER *)v24);
  BUFFER::~BUFFER((BUFFER *)v19);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000dce8  push    rbp
0x18000dcea  push    rbx
0x18000dceb  push    rsi
0x18000dcec  push    rdi
0x18000dced  push    r14
0x18000dcef  push    r15
0x18000dcf1  lea     rbp, [rsp-1038h]
0x18000dcf9  mov     eax, 1138h
0x18000dcfe  call    _alloca_probe
0x18000dd03  sub     rsp, rax
0x18000dd06  mov     rax, cs:__security_cookie
0x18000dd0d  xor     rax, rsp
0x18000dd10  mov     [rbp+1060h+var_40], rax
0x18000dd17  mov     r14, rcx
0x18000dd1a  xor     r15d, r15d
0x18000dd1d  lea     rcx, [rbp+1060h+var_C4E]; void *
0x18000dd24  mov     [rsp+1160h+NumberOfBytesRead], r15d
0x18000dd29  xor     edx, edx; Val
0x18000dd2b  mov     r8d, 1FEh; Size
0x18000dd31  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000dd35  call    memset_0
0x18000dd3a  lea     rax, [rbp+1060h+var_C50]
0x18000dd41  mov     [rbp+1060h+var_10A0], 200h
0x18000dd48  xor     edx, edx; Val
0x18000dd4a  mov     [rbp+1060h+lpFileName], rax
0x18000dd4e  mov     r8d, 7FEh; Size
0x18000dd54  mov     [rbp+1060h+var_109C], 100h
0x18000dd5a  lea     rcx, [rbp+1060h+var_83E]; void *
0x18000dd61  mov     [rbp+1060h+var_1098], r15d
0x18000dd65  mov     [rbp+1060h+var_C50], r15w
0x18000dd6d  call    memset_0
0x18000dd72  lea     rax, [rbp+1060h+var_840]
0x18000dd79  mov     [rbp+1060h+var_1068], 800h
0x18000dd80  mov     [rbp+1060h+psz], rax
0x18000dd84  lea     rcx, [rbp+1060h+pvarg]; pvarg
0x18000dd88  xor     eax, eax
0x18000dd8a  mov     [rbp+1060h+var_1064], 100h
0x18000dd90  xorps   xmm0, xmm0
0x18000dd93  mov     qword ptr [rbp+1060h+pvarg+10h], rax
0x18000dd97  mov     [rbp+1060h+var_1060], r15d
0x18000dd9b  mov     [rbp+1060h+var_840], r15w
0x18000dda3  mov     [rsp+1160h+ppv], r15
0x18000dda8  movups  xmmword ptr [rbp+1060h+pvarg], xmm0
0x18000ddac  call    cs:__imp_VariantInit
0x18000ddb2  mov     edx, 104h; uSize
0x18000ddb7  lea     rcx, [rbp+1060h+Buffer]; lpBuffer
0x18000ddbe  call    cs:__imp_GetSystemDirectoryW
0x18000ddc4  test    eax, eax
0x18000ddc6  jnz     short loc_18000DDE6
0x18000ddc8  call    cs:__imp_GetLastError
0x18000ddce  mov     ebx, eax
0x18000ddd0  test    eax, eax
0x18000ddd2  jle     loc_18000DFF3
0x18000ddd8  movzx   ebx, ax
0x18000dddb  or      ebx, 80070000h
0x18000dde1  jmp     loc_18000DFF3
0x18000dde6  lea     rdx, [rbp+1060h+Buffer]; unsigned __int16 *
0x18000dded  lea     rcx, [rbp+1060h+var_10C8]; this
0x18000ddf1  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000ddf6  mov     ebx, eax
0x18000ddf8  test    eax, eax
0x18000ddfa  js      loc_18000DFF3
0x18000de00  lea     rdx, aInetsrv; "\\inetsrv\\"
0x18000de07  lea     rcx, [rbp+1060h+var_10C8]; this
0x18000de0b  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000de10  mov     ebx, eax
0x18000de12  test    eax, eax
0x18000de14  js      loc_18000DFF3
0x18000de1a  lea     rdx, aAppcmdXml; "appcmd.xml"
0x18000de21  lea     rcx, [rbp+1060h+var_10C8]; this
0x18000de25  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000de2a  mov     ebx, eax
0x18000de2c  test    eax, eax
0x18000de2e  js      loc_18000DFF3
0x18000de34  mov     rcx, [rbp+1060h+lpFileName]; lpFileName
0x18000de38  xor     r9d, r9d; lpSecurityAttributes
0x18000de3b  mov     [rsp+1160h+hTemplateFile], r15; hTemplateFile
0x18000de40  mov     edx, 80000000h; dwDesiredAccess
0x18000de45  mov     [rsp+1160h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000de4d  mov     [rsp+1160h+dwCreationDisposition], 3; dwCreationDisposition
0x18000de55  lea     r8d, [r9+1]; dwShareMode
0x18000de59  call    cs:__imp_CreateFileW
0x18000de5f  mov     rsi, rax
0x18000de62  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000de66  jnz     short loc_18000DE8B
0x18000de68  lea     rcx, aAppcmdObjectNa; "<appcmd>\n    <object name=\"site\" ali"...
0x18000de6f  call    cs:__imp_SysAllocString
0x18000de75  mov     rdi, rax
0x18000de78  test    rax, rax
0x18000de7b  jnz     loc_18000DF6A
0x18000de81  mov     ebx, 80070008h
0x18000de86  jmp     loc_18000DFF3
0x18000de8b  xor     edx, edx; Val
0x18000de8d  lea     rcx, [rbp+1060h+var_104F]; void *
0x18000de91  mov     r8d, 3FFh; Size
0x18000de97  call    memset_0
0x18000de9c  lea     rax, [rbp+1060h+var_1050]
0x18000dea0  mov     [rbp+1060h+var_1050], r15b
0x18000dea4  xor     edx, edx; lpFileSizeHigh
0x18000dea6  mov     [rsp+1160h+lpBuffer], rax
0x18000deab  mov     rcx, rsi; hFile
0x18000deae  mov     [rsp+1160h+cbMultiByte], 400h
0x18000deb6  mov     [rsp+1160h+var_10E4], 100h
0x18000debd  call    cs:__imp_GetFileSize
0x18000dec3  mov     [rsp+1160h+NumberOfBytesRead], eax
0x18000dec7  cmp     eax, 0FFFFFFFFh
0x18000deca  jnz     short loc_18000DEF0
0x18000decc  call    cs:__imp_GetLastError
0x18000ded2  mov     ebx, eax
0x18000ded4  test    eax, eax
0x18000ded6  jle     short loc_18000DEE1
0x18000ded8  movzx   ebx, ax
0x18000dedb  or      ebx, 80070000h
0x18000dee1  lea     rcx, [rsp+1160h+var_1110]; this
0x18000dee6  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000deeb  jmp     loc_18000DFF3
0x18000def0  mov     edx, eax; unsigned int
0x18000def2  lea     rcx, [rsp+1160h+var_1110]; this
0x18000def7  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000defc  test    al, al
0x18000defe  jz      short loc_18000DECC
0x18000df00  mov     r8d, [rsp+1160h+NumberOfBytesRead]; nNumberOfBytesToRead
0x18000df05  lea     r9, [rsp+1160h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000df0a  mov     rdx, [rsp+1160h+lpBuffer]; lpBuffer
0x18000df0f  mov     rcx, rsi; hFile
0x18000df12  mov     qword ptr [rsp+1160h+dwCreationDisposition], r15; lpOverlapped
0x18000df17  call    cs:__imp_ReadFile
0x18000df1d  test    eax, eax
0x18000df1f  jz      short loc_18000DECC
0x18000df21  mov     r8d, [rsp+1160h+cbMultiByte]; cbMultiByte
0x18000df26  lea     rcx, [rbp+1060h+var_1090]; this
0x18000df2a  mov     rdx, [rsp+1160h+lpBuffer]; lpMultiByteStr
0x18000df2f  xor     r9d, r9d; unsigned int
0x18000df32  mov     byte ptr [rsp+1160h+dwFlagsAndAttributes], r15b; bool
0x18000df37  mov     byte ptr [rsp+1160h+dwCreationDisposition], 1; bool
0x18000df3c  call    ?AuxAppendA@STRU@@AEAAJPEBEKK_N1@Z; STRU::AuxAppendA(uchar const *,ulong,ulong,bool,bool)
0x18000df41  mov     ebx, eax
0x18000df43  test    eax, eax
0x18000df45  js      short loc_18000DEE1
0x18000df47  mov     rcx, [rbp+1060h+psz]; psz
0x18000df4b  call    cs:__imp_SysAllocString
0x18000df51  lea     rcx, [rsp+1160h+var_1110]; this
0x18000df56  mov     rdi, rax
0x18000df59  test    rax, rax
0x18000df5c  jnz     short loc_18000DF65
0x18000df5e  mov     ebx, 80070008h
0x18000df63  jmp     short loc_18000DEE6
0x18000df65  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000df6a  xor     edx, edx; pUnkOuter
0x18000df6c  lea     rax, [rsp+1160h+ppv]
0x18000df71  lea     r9, _GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802; riid
0x18000df78  mov     qword ptr [rsp+1160h+dwCreationDisposition], rax; ppv
0x18000df7d  lea     rcx, _GUID_88d96a0c_f192_11d4_a65f_0040963251e5; rclsid
0x18000df84  lea     r8d, [rdx+17h]; dwClsContext
0x18000df88  call    cs:__imp_CoCreateInstance
0x18000df8e  mov     ebx, eax
0x18000df90  test    eax, eax
0x18000df92  js      short loc_18000DFEA
0x18000df94  mov     rcx, [rsp+1160h+ppv]
0x18000df99  mov     rdx, r14
0x18000df9c  mov     rax, [rcx]
0x18000df9f  mov     rax, [rax+50h]
0x18000dfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfa8  mov     ebx, eax
0x18000dfaa  test    eax, eax
0x18000dfac  js      short loc_18000DFEA
0x18000dfae  mov     rcx, [rsp+1160h+ppv]
0x18000dfb3  lea     rdx, [rsp+1160h+var_1110]
0x18000dfb8  movsd   xmm1, qword ptr [rbp+1060h+pvarg+10h]
0x18000dfbd  mov     eax, 8
0x18000dfc2  mov     word ptr [rbp+1060h+pvarg], ax
0x18000dfc6  mov     qword ptr [rbp+1060h+pvarg+8], rdi
0x18000dfca  mov     rax, [rcx]
0x18000dfcd  movups  xmm0, xmmword ptr [rbp+1060h+pvarg]
0x18000dfd1  movsd   [rsp+1160h+var_1100], xmm1
0x18000dfd7  mov     rax, [rax+98h]
0x18000dfde  movaps  [rsp+1160h+var_1110], xmm0
0x18000dfe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfe8  mov     ebx, eax
0x18000dfea  mov     rcx, rdi; bstrString
0x18000dfed  call    cs:__imp_SysFreeString
0x18000dff3  mov     rcx, [rsp+1160h+ppv]
0x18000dff8  test    rcx, rcx
0x18000dffb  jz      short loc_18000E00E
0x18000dffd  mov     rax, [rcx]
0x18000e000  mov     rax, [rax+10h]
0x18000e004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e009  mov     [rsp+1160h+ppv], r15
0x18000e00e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000e012  jz      short loc_18000E01D
0x18000e014  mov     rcx, rsi; hObject
0x18000e017  call    cs:__imp_CloseHandle
0x18000e01d  lea     rcx, [rbp+1060h+var_1090]; this
0x18000e021  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e026  lea     rcx, [rbp+1060h+var_10C8]; this
0x18000e02a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e02f  mov     eax, ebx
0x18000e031  mov     rcx, [rbp+1060h+var_40]
0x18000e038  xor     rcx, rsp; StackCookie
0x18000e03b  call    __security_check_cookie
0x18000e040  add     rsp, 1138h
0x18000e047  pop     r15
0x18000e049  pop     r14
0x18000e04b  pop     rdi
0x18000e04c  pop     rsi
0x18000e04d  pop     rbx
0x18000e04e  pop     rbp
0x18000e04f  retn
```
