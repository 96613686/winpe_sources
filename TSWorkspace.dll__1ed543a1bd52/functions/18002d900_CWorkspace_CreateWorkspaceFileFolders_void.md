# CWorkspace::CreateWorkspaceFileFolders(void)

- ea: `0x18002d900`
- end: `0x18002dfa2`
- name: `?CreateWorkspaceFileFolders@CWorkspace@@QEAAJXZ`
- size: `1698`
- prototype: `__int64 __fastcall(CWorkspace *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d994`

## callees

- `0x180002b28`
- `0x180004970`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e41c`
- `0x18001e5d8`
- `0x18001e610`
- `0x18001e92c`
- `0x18001e974`
- `0x180020bf0`
- `0x180025824`
- `0x180025950`
- `0x18002d900`
- `0x18002ee98`
- `0x18009a520`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002df71`
- `ole32!CoTaskMemFree` at `0x18002df71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002deb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002deb4`
- `KERNEL32!CreateDirectoryExW` at `0x18002de51`
- `KERNEL32!CreateDirectoryExW` at `0x18002de51`
- `SHELL32!SHCreateDirectoryExW` at `0x18002da77`
- `SHELL32!SHCreateDirectoryExW` at `0x18002da77`
- `SHELL32!SHGetKnownFolderPath` at `0x18002d966`
- `SHELL32!SHGetKnownFolderPath` at `0x18002d966`

## string_xrefs

- `0x18002d9a3`: `SHGetKnownFolderPath failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWorkspace::CreateWorkspaceFileFolders(CWorkspace *this)
{
  int v2; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  int v8; // eax
  unsigned int v9; // edi
  unsigned int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned int i; // esi
  __int64 v27; // rbx
  unsigned int v28; // eax
  const WCHAR *v29; // rax
  signed int LastError; // eax
  unsigned int v31; // ebx
  unsigned int v32; // eax
  signed int v33; // eax
  PWSTR ppszPath; // [rsp+38h] [rbp-200h] BYREF
  unsigned int v36; // [rsp+40h] [rbp-1F8h]
  CWorkspace *v37; // [rsp+48h] [rbp-1F0h]
  __int64 v38; // [rsp+50h] [rbp-1E8h]
  _BYTE v39[32]; // [rsp+58h] [rbp-1E0h] BYREF
  _BYTE v40[32]; // [rsp+78h] [rbp-1C0h] BYREF
  _BYTE v41[32]; // [rsp+98h] [rbp-1A0h] BYREF
  _BYTE v42[32]; // [rsp+B8h] [rbp-180h] BYREF
  _BYTE v43[40]; // [rsp+D8h] [rbp-160h] BYREF
  _OWORD v44[2]; // [rsp+100h] [rbp-138h] BYREF
  _BYTE v45[32]; // [rsp+120h] [rbp-118h] BYREF
  _BYTE v46[32]; // [rsp+140h] [rbp-F8h] BYREF
  _BYTE v47[32]; // [rsp+160h] [rbp-D8h] BYREF
  _BYTE v48[32]; // [rsp+180h] [rbp-B8h] BYREF
  _BYTE v49[32]; // [rsp+1A0h] [rbp-98h] BYREF
  _BYTE v50[32]; // [rsp+1C0h] [rbp-78h] BYREF
  _BYTE v51[40]; // [rsp+1E0h] [rbp-58h] BYREF

  v38 = -2;
  v37 = this;
  ppszPath = 0;
  std::wstring::wstring(v42);
  std::wstring::wstring(v40);
  v2 = SHGetKnownFolderPath(&FOLDERID_RoamingAppData, 0x8000u, 0, &ppszPath);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        121,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"SHGetKnownFolderPath failed",
        v2,
        v2);
    }
LABEL_18:
    std::wstring::~wstring(v40);
    std::wstring::~wstring(v42);
    goto LABEL_37;
  }
  v4 = std::wstring::wstring(v39, ppszPath);
  v5 = std::operator+<unsigned short>(v41, v4, L"\\");
  v6 = std::operator+<unsigned short>(v43, v5, L"Microsoft\\Workspaces");
  std::wstring::operator=(v42, v6);
  std::wstring::~wstring(v43);
  std::wstring::~wstring(v41);
  std::wstring::~wstring(v39);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
  v8 = SHCreateDirectoryExW(0, v7, 0);
  v2 = v8;
  if ( v8 && v8 != 183 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      else
        v9 = v8;
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v10, v9);
    }
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    goto LABEL_18;
  }
  v11 = std::operator+<unsigned short>(v41, v42, L"\\");
  v12 = std::operator+<unsigned short>(v39, v11, (char *)this + 64);
  std::wstring::operator=(v40, v12);
  std::wstring::~wstring(v39);
  std::wstring::~wstring(v41);
  std::wstring::wstring(v44, v40);
  v13 = std::operator+<unsigned short>(v39, v40, L"\\");
  std::operator+<unsigned short>(v45, v13, L"XML");
  std::wstring::~wstring(v39);
  v14 = std::operator+<unsigned short>(v39, v40, L"\\");
  std::operator+<unsigned short>(v46, v14, L"Resource");
  std::wstring::~wstring(v39);
  v15 = std::operator+<unsigned short>(v39, v40, L"\\");
  std::operator+<unsigned short>(v47, v15, L"Icons");
  std::wstring::~wstring(v39);
  v16 = std::operator+<unsigned short>(v39, v40, L"\\");
  std::operator+<unsigned short>(v48, v16, L"Downloaded Files");
  std::wstring::~wstring(v39);
  v17 = std::operator+<unsigned short>(v43, v40, L"\\");
  v18 = std::operator+<unsigned short>(v41, v17, L"Downloaded Files");
  v19 = std::operator+<unsigned short>(v39, v18, L"\\");
  std::operator+<unsigned short>(v49, v19, L"XML");
  std::wstring::~wstring(v39);
  std::wstring::~wstring(v41);
  std::wstring::~wstring(v43);
  v20 = std::operator+<unsigned short>(v43, v40, L"\\");
  v21 = std::operator+<unsigned short>(v41, v20, L"Downloaded Files");
  v22 = std::operator+<unsigned short>(v39, v21, L"\\");
  std::operator+<unsigned short>(v50, v22, L"Resource");
  std::wstring::~wstring(v39);
  std::wstring::~wstring(v41);
  std::wstring::~wstring(v43);
  v23 = std::operator+<unsigned short>(v43, v40, L"\\");
  v24 = std::operator+<unsigned short>(v41, v23, L"Downloaded Files");
  v25 = std::operator+<unsigned short>(v39, v24, L"\\");
  std::operator+<unsigned short>(v51, v25, L"Icons");
  std::wstring::~wstring(v39);
  std::wstring::~wstring(v41);
  std::wstring::~wstring(v43);
  for ( i = 0; ; ++i )
  {
    v36 = i;
    if ( i >= 8 )
    {
      `eh vector destructor iterator'(v44, 0x20u, 8u, std::wstring::~wstring);
      std::wstring::operator=((char *)this + 424, v40);
      v2 = 0;
      std::wstring::~wstring(v40);
      std::wstring::~wstring(v42);
      goto LABEL_37;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v44[2 * i]);
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        123,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v28,
        v27);
    }
    v29 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v44[2 * i]);
    if ( !CreateDirectoryExW(ppszPath, v29, 0) )
      break;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v31 = LastError;
    if ( LastError > 0 )
      v31 = (unsigned __int16)LastError | 0x80070000;
    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v32, v31);
  }
  v33 = GetLastError();
  v2 = v33;
  if ( v33 > 0 )
    v2 = (unsigned __int16)v33 | 0x80070000;
  `eh vector destructor iterator'(v44, 0x20u, 8u, std::wstring::~wstring);
  std::wstring::~wstring(v40);
  std::wstring::~wstring(v42);
LABEL_37:
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  if ( v2 < 0 )
    CWorkspace::DeleteWorkspaceFileFolders(this);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002d900  push    rbx
0x18002d902  push    rsi
0x18002d903  push    rdi
0x18002d904  push    r14
0x18002d906  sub     rsp, 218h
0x18002d90d  mov     [rsp+238h+var_1E8], 0FFFFFFFFFFFFFFFEh
0x18002d916  mov     rax, cs:__security_cookie
0x18002d91d  xor     rax, rsp
0x18002d920  mov     [rsp+238h+var_30], rax
0x18002d928  mov     r14, rcx
0x18002d92b  mov     [rsp+238h+var_1F0], rcx
0x18002d930  mov     [rsp+238h+ppszPath], 0
0x18002d939  lea     rcx, [rsp+238h+var_180]
0x18002d941  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d946  nop
0x18002d947  lea     rcx, [rsp+238h+var_1C0]
0x18002d94c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d951  nop
0x18002d952  lea     r9, [rsp+238h+ppszPath]; ppszPath
0x18002d957  xor     r8d, r8d; hToken
0x18002d95a  mov     edx, 8000h; dwFlags
0x18002d95f  lea     rcx, FOLDERID_RoamingAppData; rfid
0x18002d966  call    cs:__imp_SHGetKnownFolderPath
0x18002d96c  mov     ebx, eax
0x18002d96e  mov     [rsp+238h+var_208], eax
0x18002d972  test    eax, eax
0x18002d974  jns     short loc_18002D9E8
0x18002d976  lea     rdi, WPP_GLOBAL_Control
0x18002d97d  mov     rax, cs:WPP_GLOBAL_Control
0x18002d984  cmp     rax, rdi
0x18002d987  jz      short loc_18002D9CA
0x18002d989  test    byte ptr [rax+1Ch], 8
0x18002d98d  jz      short loc_18002D9CA
0x18002d98f  cmp     byte ptr [rax+19h], 2
0x18002d993  jb      short loc_18002D9CA
0x18002d995  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002d99a  mov     edx, 79h ; 'y'
0x18002d99f  mov     [rsp+238h+var_210], ebx
0x18002d9a3  lea     rcx, aShgetknownfold_0; "SHGetKnownFolderPath failed"
0x18002d9aa  mov     [rsp+238h+var_218], rcx
0x18002d9af  mov     r9d, eax
0x18002d9b2  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002d9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9c0  mov     rcx, [rcx+10h]
0x18002d9c4  call    WPP_SF_DsD
0x18002d9c9  nop
0x18002d9ca  lea     rcx, [rsp+238h+var_1C0]; void *
0x18002d9cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d9d4  nop
0x18002d9d5  lea     rcx, [rsp+238h+var_180]; void *
0x18002d9dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d9e2  nop
0x18002d9e3  jmp     loc_18002DF67
0x18002d9e8  mov     rdx, [rsp+238h+ppszPath]
0x18002d9ed  lea     rcx, [rsp+238h+var_1E0]
0x18002d9f2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002d9f7  nop
0x18002d9f8  lea     rdi, SubStr; "\\"
0x18002d9ff  mov     r8, rdi
0x18002da02  mov     rdx, rax
0x18002da05  lea     rcx, [rsp+238h+var_1A0]
0x18002da0d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002da12  nop
0x18002da13  lea     r8, aMicrosoftWorks; "Microsoft\\Workspaces"
0x18002da1a  mov     rdx, rax
0x18002da1d  lea     rcx, [rsp+238h+var_160]
0x18002da25  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002da2a  nop
0x18002da2b  mov     rdx, rax
0x18002da2e  lea     rcx, [rsp+238h+var_180]
0x18002da36  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002da3b  nop
0x18002da3c  lea     rcx, [rsp+238h+var_160]; void *
0x18002da44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002da49  nop
0x18002da4a  lea     rcx, [rsp+238h+var_1A0]; void *
0x18002da52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002da57  nop
0x18002da58  lea     rcx, [rsp+238h+var_1E0]; void *
0x18002da5d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002da62  lea     rcx, [rsp+238h+var_180]
0x18002da6a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002da6f  mov     rdx, rax; pszPath
0x18002da72  xor     r8d, r8d; psa
0x18002da75  xor     ecx, ecx; hwnd
0x18002da77  call    cs:__imp_SHCreateDirectoryExW
0x18002da7d  mov     ebx, eax
0x18002da7f  test    eax, eax
0x18002da81  jz      loc_18002DB19
0x18002da87  cmp     eax, 0B7h
0x18002da8c  jz      loc_18002DB19
0x18002da92  lea     rdi, WPP_GLOBAL_Control
0x18002da99  mov     rax, cs:WPP_GLOBAL_Control
0x18002daa0  cmp     rax, rdi
0x18002daa3  jz      short loc_18002DAEA
0x18002daa5  test    byte ptr [rax+1Ch], 8
0x18002daa9  jz      short loc_18002DAEA
0x18002daab  cmp     byte ptr [rax+19h], 2
0x18002daaf  jb      short loc_18002DAEA
0x18002dab1  test    ebx, ebx
0x18002dab3  jg      short loc_18002DAB9
0x18002dab5  mov     edi, ebx
0x18002dab7  jmp     short loc_18002DAC2
0x18002dab9  movzx   edi, bx
0x18002dabc  or      edi, 80070000h
0x18002dac2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002dac7  mov     edx, 7Ah ; 'z'
0x18002dacc  mov     dword ptr [rsp+238h+var_218], edi
0x18002dad0  mov     r9d, eax
0x18002dad3  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002dada  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dae1  mov     rcx, [rcx+10h]
0x18002dae5  call    WPP_SF_Dd
0x18002daea  test    ebx, ebx
0x18002daec  jle     short loc_18002DAF7
0x18002daee  movzx   ebx, bx
0x18002daf1  or      ebx, 80070000h
0x18002daf7  mov     [rsp+238h+var_208], ebx
0x18002dafb  lea     rcx, [rsp+238h+var_1C0]; void *
0x18002db00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002db05  nop
0x18002db06  lea     rcx, [rsp+238h+var_180]; void *
0x18002db0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002db13  nop
0x18002db14  jmp     loc_18002DF67
0x18002db19  mov     r8, rdi
0x18002db1c  lea     rdx, [rsp+238h+var_180]
0x18002db24  lea     rcx, [rsp+238h+var_1A0]
0x18002db2c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x18002db31  nop
0x18002db32  lea     r8, [r14+40h]
0x18002db36  mov     rdx, rax
0x18002db39  lea     rcx, [rsp+238h+var_1E0]
0x18002db3e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18002db43  nop
0x18002db44  mov     rdx, rax
0x18002db47  lea     rcx, [rsp+238h+var_1C0]
0x18002db4c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002db51  nop
0x18002db52  lea     rcx, [rsp+238h+var_1E0]; void *
0x18002db57  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002db5c  nop
0x18002db5d  lea     rcx, [rsp+238h+var_1A0]; void *
0x18002db65  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002db6a  lea     rdx, [rsp+238h+var_1C0]
0x18002db6f  lea     rcx, [rsp+238h+var_138]
0x18002db77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002db7c  nop
0x18002db7d  mov     r8, rdi
0x18002db80  lea     rdx, [rsp+238h+var_1C0]
0x18002db85  lea     rcx, [rsp+238h+var_1E0]
0x18002db8a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x18002db8f  nop
0x18002db90  lea     r8, aXml; "XML"
0x18002db97  mov     rdx, rax
0x18002db9a  lea     rcx, [rsp+238h+var_118]
0x18002dba2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dba7  nop
0x18002dba8  lea     rcx, [rsp+238h+var_1E0]; void *
0x18002dbad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dbb2  mov     r8, rdi
0x18002dbb5  lea     rdx, [rsp+238h+var_1C0]
0x18002dbba  lea     rcx, [rsp+238h+var_1E0]
0x18002dbbf  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x18002dbc4  nop
0x18002dbc5  lea     r8, aResource; "Resource"
0x18002dbcc  mov     rdx, rax
0x18002dbcf  lea     rcx, [rsp+238h+var_F8]
0x18002dbd7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dbdc  nop
0x18002dbdd  lea     rcx, [rsp+238h+var_1E0]; void *
0x18002dbe2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dbe7  mov     r8, rdi
0x18002dbea  lea     rdx, [rsp+238h+var_1C0]
0x18002dbef  lea     rcx, [rsp+238h+var_1E0]
0x18002dbf4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x18002dbf9  nop
0x18002dbfa  lea     r8, aIcons; "Icons"
0x18002dc01  mov     rdx, rax
0x18002dc04  lea     rcx, [rsp+238h+var_D8]
0x18002dc0c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dc11  nop
0x18002dc12  lea     rcx, [rsp+238h+var_1E0]; void *
0x18002dc17  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dc1c  mov     r8, rdi
0x18002dc1f  lea     rdx, [rsp+238h+var_1C0]
0x18002dc24  lea     rcx, [rsp+238h+var_1E0]
0x18002dc29  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x18002dc2e  nop
0x18002dc2f  lea     rbx, aDownloadedFile; "Downloaded Files"
0x18002dc36  mov     r8, rbx
0x18002dc39  mov     rdx, rax
0x18002dc3c  lea     rcx, [rsp+238h+var_B8]
0x18002dc44  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dc49  nop
0x18002dc4a  lea     rcx, [rsp+238h+var_1E0]; void *
0x18002dc4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dc54  mov     r8, rdi
0x18002dc57  lea     rdx, [rsp+238h+var_1C0]
0x18002dc5c  lea     rcx, [rsp+238h+var_160]
0x18002dc64  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x18002dc69  nop
0x18002dc6a  mov     r8, rbx
0x18002dc6d  mov     rdx, rax
0x18002dc70  lea     rcx, [rsp+238h+var_1A0]
0x18002dc78  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dc7d  nop
0x18002dc7e  mov     r8, rdi
0x18002dc81  mov     rdx, rax
0x18002dc84  lea     rcx, [rsp+238h+var_1E0]
0x18002dc89  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dc8e  nop
0x18002dc8f  lea     r8, aXml; "XML"
0x18002dc96  mov     rdx, rax
0x18002dc99  lea     rcx, [rsp+238h+var_98]
0x18002dca1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dca6  nop
0x18002dca7  lea     rcx, [rsp+238h+var_1E0]; void *
0x18002dcac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dcb1  nop
0x18002dcb2  lea     rcx, [rsp+238h+var_1A0]; void *
0x18002dcba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dcbf  nop
0x18002dcc0  lea     rcx, [rsp+238h+var_160]; void *
0x18002dcc8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dccd  mov     r8, rdi
0x18002dcd0  lea     rdx, [rsp+238h+var_1C0]
0x18002dcd5  lea     rcx, [rsp+238h+var_160]
0x18002dcdd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x18002dce2  nop
0x18002dce3  mov     r8, rbx
0x18002dce6  mov     rdx, rax
0x18002dce9  lea     rcx, [rsp+238h+var_1A0]
0x18002dcf1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dcf6  nop
0x18002dcf7  mov     r8, rdi
0x18002dcfa  mov     rdx, rax
0x18002dcfd  lea     rcx, [rsp+238h+var_1E0]
0x18002dd02  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dd07  nop
0x18002dd08  lea     r8, aResource; "Resource"
0x18002dd0f  mov     rdx, rax
0x18002dd12  lea     rcx, [rsp+238h+var_78]
0x18002dd1a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dd1f  nop
0x18002dd20  lea     rcx, [rsp+238h+var_1E0]; void *
0x18002dd25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dd2a  nop
0x18002dd2b  lea     rcx, [rsp+238h+var_1A0]; void *
0x18002dd33  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dd38  nop
0x18002dd39  lea     rcx, [rsp+238h+var_160]; void *
0x18002dd41  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dd46  mov     r8, rdi
0x18002dd49  lea     rdx, [rsp+238h+var_1C0]
0x18002dd4e  lea     rcx, [rsp+238h+var_160]
0x18002dd56  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x18002dd5b  nop
0x18002dd5c  mov     r8, rbx
0x18002dd5f  mov     rdx, rax
0x18002dd62  lea     rcx, [rsp+238h+var_1A0]
0x18002dd6a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dd6f  nop
0x18002dd70  mov     r8, rdi
0x18002dd73  mov     rdx, rax
0x18002dd76  lea     rcx, [rsp+238h+var_1E0]
0x18002dd7b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dd80  nop
0x18002dd81  lea     r8, aIcons; "Icons"
0x18002dd88  mov     rdx, rax
0x18002dd8b  lea     rcx, [rsp+238h+var_58]
0x18002dd93  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18002dd98  nop
0x18002dd99  lea     rcx, [rsp+238h+var_1E0]; void *
0x18002dd9e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dda3  nop
0x18002dda4  lea     rcx, [rsp+238h+var_1A0]; void *
0x18002ddac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ddb1  nop
0x18002ddb2  lea     rcx, [rsp+238h+var_160]; void *
0x18002ddba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ddbf  nop
0x18002ddc0  xor     esi, esi
0x18002ddc2  lea     rdi, WPP_GLOBAL_Control
0x18002ddc9  mov     [rsp+238h+var_1F8], esi
0x18002ddcd  cmp     esi, 8
0x18002ddd0  jnb     loc_18002DF0D
0x18002ddd6  mov     rax, cs:WPP_GLOBAL_Control
0x18002dddd  cmp     rax, rdi
0x18002dde0  jz      short loc_18002DE30
0x18002dde2  test    byte ptr [rax+1Ch], 1
0x18002dde6  jz      short loc_18002DE30
0x18002dde8  cmp     byte ptr [rax+19h], 4
0x18002ddec  jb      short loc_18002DE30
0x18002ddee  mov     eax, esi
0x18002ddf0  shl     rax, 5
0x18002ddf4  lea     rcx, [rsp+238h+var_138]
0x18002ddfc  add     rcx, rax
0x18002ddff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002de04  mov     rbx, rax
  ... truncated ...
```
