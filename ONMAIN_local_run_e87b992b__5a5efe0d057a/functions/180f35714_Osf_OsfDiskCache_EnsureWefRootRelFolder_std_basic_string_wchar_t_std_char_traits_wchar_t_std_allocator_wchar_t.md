# Osf::OsfDiskCache::EnsureWefRootRelFolder(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180f35714`
- end: `0x180f35a58`
- name: `?EnsureWefRootRelFolder@OsfDiskCache@Osf@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV34@@Z`
- size: `836`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180f368f4`
- `0x180f36de4`

## callees

- `0x18002d954`
- `0x18002e214`
- `0x18002e308`
- `0x180094038`
- `0x1800943d4`
- `0x180094440`
- `0x180264dbc`
- `0x180292a00`
- `0x1802e2190`
- `0x1802e2210`
- `0x1802e5170`
- `0x1803897a0`
- `0x1805deb34`
- `0x180bd4604`
- `0x180f35714`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x180f35a26`
- `MSVCP140!_Mtx_unlock` at `0x180f35a26`
- `Mso30Win32Client!__imp_?VersionToString@@YAJAEBUAppVersion@@PEA_W_KK@Z` at `0x180f35916`
- `Mso30Win32Client!__imp_?VersionToString@@YAJAEBUAppVersion@@PEA_W_KK@Z` at `0x180f35916`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f35879`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f35972`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f35879`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180f35972`
- `Mso20Win32Client!__imp_?MsoFDirExist@@YAHPEB_W@Z` at `0x180f35980`
- `Mso20Win32Client!__imp_?MsoFDirExist@@YAHPEB_W@Z` at `0x180f359a2`
- `Mso20Win32Client!__imp_?MsoFDirExist@@YAHPEB_W@Z` at `0x180f35980`
- `Mso20Win32Client!__imp_?MsoFDirExist@@YAHPEB_W@Z` at `0x180f359a2`
- `Mso20Win32Client!__imp_?MsoFCreateFullLocalDirectory@@YA_NPEB_W@Z` at `0x180f3598e`
- `Mso20Win32Client!__imp_?MsoFCreateFullLocalDirectory@@YA_NPEB_W@Z` at `0x180f359b0`
- `Mso20Win32Client!__imp_?MsoFCreateFullLocalDirectory@@YA_NPEB_W@Z` at `0x180f3598e`
- `Mso20Win32Client!__imp_?MsoFCreateFullLocalDirectory@@YA_NPEB_W@Z` at `0x180f359b0`
- `Mso20Win32Client!__imp_?MsoHrGetAppDataFolderEx@@YAJPEA_WHW4MSOADF@@KW4AppDataFolderType@@@Z` at `0x180f3584e`
- `Mso20Win32Client!__imp_?MsoHrGetAppDataFolderEx@@YAJPEA_WHW4MSOADF@@KW4AppDataFolderType@@@Z` at `0x180f3584e`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x180f358c1`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x180f35928`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x180f3593c`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x180f35956`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x180f358c1`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x180f35928`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x180f3593c`
- `Mso20Win32Client!__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z` at `0x180f35956`
- `Mso20Win32Client!__imp_?GetExeVersion@Process@Mso@@YAAEBUVersionNumbers@@XZ` at `0x180f358cf`
- `Mso20Win32Client!__imp_?GetExeVersion@Process@Mso@@YAAEBUVersionNumbers@@XZ` at `0x180f358cf`

## pseudocode

```c
__int64 __fastcall Osf::OsfDiskCache::EnsureWefRootRelFolder(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  int AppDataFolder; // eax
  bool v6; // r8
  unsigned int v7; // ebx
  int v8; // edx
  unsigned int v9; // ecx
  bool v10; // al
  Mso::Process *v11; // rcx
  unsigned __int16 *ExeVersion; // rax
  const wchar_t *v13; // rcx
  bool v14; // al
  bool v15; // r8
  __int64 v16; // rbx
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  __int128 v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v21; // [rsp+40h] [rbp-C0h]
  _BYTE v22[16]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v24[20]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t v25[264]; // [rsp+A0h] [rbp-60h] BYREF

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_1815BA380 > *(_DWORD *)(v4 + 16) )
  {
    Init_thread_header(&dword_1815BA380);
    if ( dword_1815BA380 == -1 )
    {
      std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(&qword_1815BA390);
      atexit(sub_1803580E0);
      Init_thread_footer(&dword_1815BA380);
    }
  }
  if ( dword_1815BA3D0 > *(_DWORD *)(v4 + 16) )
  {
    Init_thread_header(&dword_1815BA3D0);
    if ( dword_1815BA3D0 == -1 )
    {
      std::_Mutex_base::_Mutex_base((_Mtx_t)qword_1815BA3E0, 0);
      Init_thread_footer(&dword_1815BA3D0);
    }
  }
  v21 = qword_1815BA3E0;
  std::_Mutex_base::lock((std::_Mutex_base *)qword_1815BA3E0);
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                    &qword_1815BA390,
                    &v20,
                    a1) != qword_1815BA398
    && *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                                &qword_1815BA390,
                                &v20,
                                a1)
                 + 64LL) )
  {
    goto LABEL_36;
  }
  AppDataFolder = MsoHrGetAppDataFolderEx(v25, 260, 1);
  v7 = AppDataFolder;
  if ( AppDataFolder >= 0 )
  {
    if ( byte_18154C5D0 < 0 )
      v10 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18154C5D0);
    else
      v10 = byte_18154C5D0 != 0;
    v7 = -2147467259;
    if ( v10 )
    {
      if ( !v25[0] )
      {
        v9 = 504906504;
LABEL_17:
        v8 = -2147467259;
        goto LABEL_18;
      }
    }
    else if ( !v25[0] )
    {
      SendTraceEvent(0x1E48A0CBu, -2147467259, v6);
    }
    MsoAppendToPath(L"Office", v25, 260);
    v20 = 0;
    ExeVersion = (unsigned __int16 *)Mso::Process::GetExeVersion(v11);
    LODWORD(v20) = ExeVersion[1];
    HIDWORD(v20) = ExeVersion[2];
    DWORD1(v20) = *ExeVersion;
    DWORD2(v20) = ExeVersion[3];
    if ( !ExeVersion[1] )
    {
      v9 = 508379281;
      goto LABEL_17;
    }
    VersionToString((const struct AppVersion *)&v20, v24, 0xDu, 2u);
    MsoAppendToPath(v24, v25, 260);
    MsoAppendToPath(L"Wef", v25, 260);
    v13 = (const wchar_t *)a1;
    if ( *(_QWORD *)(a1 + 24) > 7u )
      v13 = *(const wchar_t **)a1;
    MsoAppendToPath(v13, v25, 260);
    if ( byte_18154C5D0 < 0 )
      v14 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18154C5D0);
    else
      v14 = byte_18154C5D0 != 0;
    if ( v14 )
    {
      if ( !MsoFDirExist(v25) && !MsoFCreateFullLocalDirectory(v25) )
      {
        v9 = 504906503;
        goto LABEL_17;
      }
    }
    else if ( MsoFDirExist(v25) || MsoFCreateFullLocalDirectory(v25) )
    {
      SendTraceEvent(0x1E48A0CAu, -2147467259, v15);
    }
    v16 = std::wstring::wstring(v23, v25);
    v17 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                      &qword_1815BA390,
                      v22,
                      a1);
    std::wstring::operator=(*v17 + 48LL, v16);
    std::wstring::~wstring(v23);
LABEL_36:
    v18 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                      &qword_1815BA390,
                      v22,
                      a1);
    std::wstring::operator=(a2, *v18 + 48LL);
    v7 = 0;
    goto LABEL_37;
  }
  v8 = AppDataFolder;
  v9 = 508379282;
LABEL_18:
  SendTraceEvent(v9, v8, v6);
LABEL_37:
  _Mtx_unlock((_Mtx_t)qword_1815BA3E0);
  return v7;
}

```

## disassembly

```asm
0x180f35714  mov     [rsp-8+arg_10], rbx
0x180f35719  push    rbp
0x180f3571a  push    rsi
0x180f3571b  push    rdi
0x180f3571c  push    r12
0x180f3571e  push    r13
0x180f35720  push    r14
0x180f35722  push    r15
0x180f35724  lea     rbp, [rsp-1C0h]
0x180f3572c  sub     rsp, 2C0h
0x180f35733  mov     rax, cs:__security_cookie
0x180f3573a  xor     rax, rsp
0x180f3573d  mov     [rbp+1F0h+var_40], rax
0x180f35744  mov     rsi, rdx
0x180f35747  mov     rdi, rcx
0x180f3574a  mov     r14d, 10h
0x180f35750  mov     ecx, cs:_tls_index
0x180f35756  mov     rax, gs:58h
0x180f3575f  mov     rbx, [rax+rcx*8]
0x180f35763  lea     r13, qword_1815BA390
0x180f3576a  mov     eax, [rbx+r14]
0x180f3576e  cmp     cs:dword_1815BA380, eax
0x180f35774  jle     short loc_180F357AB
0x180f35776  lea     rcx, dword_1815BA380
0x180f3577d  call    _Init_thread_header
0x180f35782  cmp     cs:dword_1815BA380, 0FFFFFFFFh
0x180f35789  jnz     short loc_180F357AB
0x180f3578b  mov     rcx, r13
0x180f3578e  call    ??0?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x180f35793  lea     rcx, sub_1803580E0; void (__cdecl *)()
0x180f3579a  call    atexit
0x180f3579f  lea     rcx, dword_1815BA380
0x180f357a6  call    _Init_thread_footer
0x180f357ab  lea     r15, qword_1815BA3E0
0x180f357b2  mov     eax, [rbx+r14]
0x180f357b6  cmp     cs:dword_1815BA3D0, eax
0x180f357bc  jle     short loc_180F357E9
0x180f357be  lea     rcx, dword_1815BA3D0
0x180f357c5  call    _Init_thread_header
0x180f357ca  cmp     cs:dword_1815BA3D0, 0FFFFFFFFh
0x180f357d1  jnz     short loc_180F357E9
0x180f357d3  xor     edx, edx; int
0x180f357d5  mov     rcx, r15; this
0x180f357d8  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x180f357dd  lea     rcx, dword_1815BA3D0
0x180f357e4  call    _Init_thread_footer
0x180f357e9  mov     [rsp+2F0h+var_2B0], r15
0x180f357ee  mov     rcx, r15; this
0x180f357f1  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180f357f6  mov     r8, rdi
0x180f357f9  lea     rdx, [rsp+2F0h+var_2C0]
0x180f357fe  mov     rcx, r13
0x180f35801  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180f35806  xor     r14d, r14d
0x180f35809  mov     rcx, cs:qword_1815BA398
0x180f35810  cmp     [rax], rcx
0x180f35813  jz      short loc_180F35832
0x180f35815  mov     r8, rdi
0x180f35818  lea     rdx, [rsp+2F0h+var_2C0]
0x180f3581d  mov     rcx, r13
0x180f35820  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180f35825  mov     rcx, [rax]
0x180f35828  cmp     [rcx+40h], r14
0x180f3582c  jnz     loc_180F35A01
0x180f35832  mov     [rsp+2F0h+var_2D0], 2
0x180f3583a  xor     r9d, r9d
0x180f3583d  lea     r8d, [r9+1]
0x180f35841  mov     r12d, 104h
0x180f35847  mov     edx, r12d
0x180f3584a  lea     rcx, [rbp+1F0h+var_250]
0x180f3584e  call    cs:__imp_?MsoHrGetAppDataFolderEx@@YAJPEA_WHW4MSOADF@@KW4AppDataFolderType@@@Z; MsoHrGetAppDataFolderEx(wchar_t *,int,MSOADF,ulong,AppDataFolderType)
0x180f35854  mov     ebx, eax
0x180f35856  test    eax, eax
0x180f35858  jns     short loc_180F35863
0x180f3585a  mov     edx, eax
0x180f3585c  mov     ecx, 1E4D4092h
0x180f35861  jmp     short loc_180F35896
0x180f35863  mov     al, cs:byte_18154C5D0
0x180f35869  test    al, al
0x180f3586b  js      short loc_180F35872
0x180f3586d  setnz   al
0x180f35870  jmp     short loc_180F3587F
0x180f35872  lea     rcx, byte_18154C5D0
0x180f35879  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x180f3587f  mov     ebx, 80004005h
0x180f35884  test    al, al
0x180f35886  jz      short loc_180F358A0
0x180f35888  cmp     [rbp+1F0h+var_250], r14w
0x180f3588d  jnz     short loc_180F358B3
0x180f3588f  mov     ecx, 1E184308h; unsigned int
0x180f35894  mov     edx, ebx; int
0x180f35896  call    ?SendTraceEvent@@YAXKJ_N@Z; SendTraceEvent(ulong,long,bool)
0x180f3589b  jmp     loc_180F35A23
0x180f358a0  cmp     [rbp+1F0h+var_250], r14w
0x180f358a5  jnz     short loc_180F358B3
0x180f358a7  mov     edx, ebx; int
0x180f358a9  mov     ecx, 1E48A0CBh; unsigned int
0x180f358ae  call    ?SendTraceEvent@@YAXKJ_N@Z; SendTraceEvent(ulong,long,bool)
0x180f358b3  mov     r8d, r12d
0x180f358b6  lea     rdx, [rbp+1F0h+var_250]
0x180f358ba  lea     rcx, aOffice; "Office"
0x180f358c1  call    cs:__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z; MsoAppendToPath(wchar_t const *,wchar_t *,int)
0x180f358c7  xorps   xmm0, xmm0
0x180f358ca  movups  [rsp+2F0h+var_2C0], xmm0
0x180f358cf  call    cs:__imp_?GetExeVersion@Process@Mso@@YAAEBUVersionNumbers@@XZ; Mso::Process::GetExeVersion(void)
0x180f358d5  movzx   ecx, word ptr [rax+2]
0x180f358d9  mov     dword ptr [rsp+2F0h+var_2C0], ecx
0x180f358dd  movzx   ecx, word ptr [rax+4]
0x180f358e1  mov     dword ptr [rsp+2F0h+var_2C0+0Ch], ecx
0x180f358e5  movzx   ecx, word ptr [rax]
0x180f358e8  mov     dword ptr [rsp+2F0h+var_2C0+4], ecx
0x180f358ec  movzx   ecx, word ptr [rax+6]
0x180f358f0  mov     dword ptr [rsp+2F0h+var_2C0+8], ecx
0x180f358f4  cmp     [rax+2], r14w
0x180f358f9  jnz     short loc_180F35902
0x180f358fb  mov     ecx, 1E4D4091h
0x180f35900  jmp     short loc_180F35894
0x180f35902  mov     r9d, 2
0x180f35908  lea     r8d, [r9+0Bh]
0x180f3590c  lea     rdx, [rsp+2F0h+var_278]
0x180f35911  lea     rcx, [rsp+2F0h+var_2C0]
0x180f35916  call    cs:__imp_?VersionToString@@YAJAEBUAppVersion@@PEA_W_KK@Z; VersionToString(AppVersion const &,wchar_t *,unsigned __int64,ulong)
0x180f3591c  mov     r8d, r12d
0x180f3591f  lea     rdx, [rbp+1F0h+var_250]
0x180f35923  lea     rcx, [rsp+2F0h+var_278]
0x180f35928  call    cs:__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z; MsoAppendToPath(wchar_t const *,wchar_t *,int)
0x180f3592e  mov     r8d, r12d
0x180f35931  lea     rdx, [rbp+1F0h+var_250]
0x180f35935  lea     rcx, aWef_0; "Wef"
0x180f3593c  call    cs:__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z; MsoAppendToPath(wchar_t const *,wchar_t *,int)
0x180f35942  mov     rcx, rdi
0x180f35945  cmp     qword ptr [rdi+18h], 7
0x180f3594a  jbe     short loc_180F3594F
0x180f3594c  mov     rcx, [rdi]
0x180f3594f  mov     r8d, r12d
0x180f35952  lea     rdx, [rbp+1F0h+var_250]
0x180f35956  call    cs:__imp_?MsoAppendToPath@@YAPEA_WPEB_WPEA_WH@Z; MsoAppendToPath(wchar_t const *,wchar_t *,int)
0x180f3595c  mov     al, cs:byte_18154C5D0
0x180f35962  test    al, al
0x180f35964  js      short loc_180F3596B
0x180f35966  setnz   al
0x180f35969  jmp     short loc_180F35978
0x180f3596b  lea     rcx, byte_18154C5D0
0x180f35972  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x180f35978  lea     rcx, [rbp+1F0h+var_250]
0x180f3597c  test    al, al
0x180f3597e  jz      short loc_180F359A2
0x180f35980  call    cs:__imp_?MsoFDirExist@@YAHPEB_W@Z; MsoFDirExist(wchar_t const *)
0x180f35986  test    eax, eax
0x180f35988  jnz     short loc_180F359C6
0x180f3598a  lea     rcx, [rbp+1F0h+var_250]
0x180f3598e  call    cs:__imp_?MsoFCreateFullLocalDirectory@@YA_NPEB_W@Z; MsoFCreateFullLocalDirectory(wchar_t const *)
0x180f35994  test    al, al
0x180f35996  jnz     short loc_180F359C6
0x180f35998  mov     ecx, 1E184307h
0x180f3599d  jmp     loc_180F35894
0x180f359a2  call    cs:__imp_?MsoFDirExist@@YAHPEB_W@Z; MsoFDirExist(wchar_t const *)
0x180f359a8  test    eax, eax
0x180f359aa  jnz     short loc_180F359BA
0x180f359ac  lea     rcx, [rbp+1F0h+var_250]
0x180f359b0  call    cs:__imp_?MsoFCreateFullLocalDirectory@@YA_NPEB_W@Z; MsoFCreateFullLocalDirectory(wchar_t const *)
0x180f359b6  test    al, al
0x180f359b8  jz      short loc_180F359C6
0x180f359ba  mov     edx, ebx; int
0x180f359bc  mov     ecx, 1E48A0CAh; unsigned int
0x180f359c1  call    ?SendTraceEvent@@YAXKJ_N@Z; SendTraceEvent(ulong,long,bool)
0x180f359c6  lea     rdx, [rbp+1F0h+var_250]
0x180f359ca  lea     rcx, [rsp+2F0h+var_298]
0x180f359cf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180f359d4  mov     rbx, rax
0x180f359d7  mov     r8, rdi
0x180f359da  lea     rdx, [rsp+2F0h+var_2A8]
0x180f359df  mov     rcx, r13
0x180f359e2  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180f359e7  mov     rcx, [rax]
0x180f359ea  add     rcx, 30h ; '0'
0x180f359ee  mov     rdx, rbx
0x180f359f1  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180f359f6  nop
0x180f359f7  lea     rcx, [rsp+2F0h+var_298]; void *
0x180f359fc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180f35a01  mov     r8, rdi
0x180f35a04  lea     rdx, [rsp+2F0h+var_2A8]
0x180f35a09  mov     rcx, r13
0x180f35a0c  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180f35a11  mov     rdx, [rax]
0x180f35a14  add     rdx, 30h ; '0'
0x180f35a18  mov     rcx, rsi
0x180f35a1b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180f35a20  mov     ebx, r14d
0x180f35a23  mov     rcx, r15; _Mtx_t
0x180f35a26  call    cs:__imp__Mtx_unlock
0x180f35a2c  mov     eax, ebx
0x180f35a2e  mov     rcx, [rbp+1F0h+var_40]
0x180f35a35  xor     rcx, rsp; StackCookie
0x180f35a38  call    __security_check_cookie
0x180f35a3d  mov     rbx, [rsp+2F0h+arg_10]
0x180f35a45  add     rsp, 2C0h
0x180f35a4c  pop     r15
0x180f35a4e  pop     r14
0x180f35a50  pop     r13
0x180f35a52  pop     r12
0x180f35a54  pop     rdi
0x180f35a55  pop     rsi
0x180f35a56  pop     rbp
0x180f35a57  retn
```
