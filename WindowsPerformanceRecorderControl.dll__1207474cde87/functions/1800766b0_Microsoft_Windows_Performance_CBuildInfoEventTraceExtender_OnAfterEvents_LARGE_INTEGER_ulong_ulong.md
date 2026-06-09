# Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x1800766b0`
- end: `0x180076b2d`
- name: `?OnAfterEvents@CBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `1149`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008270`
- `0x1800259c4`
- `0x180025ab8`
- `0x180036bfc`
- `0x180038548`
- `0x180038a70`
- `0x18004ece0`
- `0x18004f964`
- `0x18005c460`
- `0x1800766b0`
- `0x180076b70`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800768c1`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800768c1`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x180076784`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x180076784`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800768b2`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800768b2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800768fe`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18007692a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800768fe`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18007692a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180076776`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180076792`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180076776`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180076792`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800769f6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800769f6`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800769e1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800769e1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800767f7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800767f7`

## string_xrefs

- `0x1800769d4`: `ntdll.dll`
- `0x180076753`: `InstallDate`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // r14d
  unsigned int v7; // r15d
  unsigned __int16 *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  WORD *v13; // rdi
  WORD v14; // dx
  WORD v15; // r11
  WORD v16; // ax
  WORD v17; // r10
  WORD v18; // r9
  WORD v19; // r8
  BOOL v20; // eax
  struct _FILETIME v21; // rcx
  unsigned int v22; // esi
  __int64 v23; // rdx
  __int64 first_of; // rax
  __int64 v25; // rdx
  __int64 v26; // rsi
  __int64 v27; // r14
  size_t v28; // rax
  size_t v29; // r15
  __int64 v30; // r12
  unsigned __int16 *v31; // rdi
  unsigned int v32; // esi
  unsigned int v33; // esi
  unsigned __int16 *v34; // rdi
  SYSTEMTIME *p_SystemTime; // rax
  int v36; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  unsigned int v42[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v43; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v45; // [rsp+48h] [rbp-B8h]
  unsigned int v46; // [rsp+4Ch] [rbp-B4h]
  _QWORD v47[4]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v48[2]; // [rsp+70h] [rbp-90h] BYREF
  char v49; // [rsp+74h] [rbp-8Ch]
  union _LARGE_INTEGER v50; // [rsp+80h] [rbp-80h]
  struct _GUID v51; // [rsp+88h] [rbp-78h]
  struct _FILETIME *v52; // [rsp+B8h] [rbp-48h]
  unsigned int v53; // [rsp+C0h] [rbp-40h]
  unsigned int v54; // [rsp+C4h] [rbp-3Ch]
  _WORD v55[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v56; // [rsp+D4h] [rbp-2Ch]
  union _LARGE_INTEGER v57; // [rsp+E0h] [rbp-20h]
  struct _GUID v58; // [rsp+E8h] [rbp-18h]
  _QWORD v59[4]; // [rsp+100h] [rbp+0h] BYREF
  int v60; // [rsp+120h] [rbp+20h]
  unsigned int v61; // [rsp+124h] [rbp+24h]
  SYSTEMTIME SystemTime; // [rsp+130h] [rbp+30h] BYREF
  __int64 v63; // [rsp+140h] [rbp+40h]
  unsigned __int64 v64; // [rsp+148h] [rbp+48h]
  __int128 v65; // [rsp+150h] [rbp+50h] BYREF
  struct _FILETIME v66; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v67; // [rsp+168h] [rbp+68h] BYREF
  char v68; // [rsp+16Ah] [rbp+6Ah] BYREF
  wchar_t Source[16]; // [rsp+970h] [rbp+870h] BYREF

  v4 = a3;
  v45 = a3;
  v46 = a4;
  v7 = a4;
  memset_0(&v66, 0, 0x80Cu);
  memset(v47, 0, 24);
  v8 = &v67;
  v65 = 0;
  if ( (unsigned int)ATL::CRegKey::Open(
                       (ATL::CRegKey *)v47,
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                       1u) )
    goto LABEL_26;
  v43 = 0;
  if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v47, L"InstallDate", &v43) )
  {
    *(_QWORD *)v42 = (int)v43;
    *(_DWORD *)_o__errno(v10, v9) = 0;
    v13 = (WORD *)_o__gmtime64(v42);
    if ( v13 )
    {
      if ( !*(_DWORD *)_o__errno(v12, v11) )
      {
        v14 = v13[12];
        v15 = *v13;
        v16 = v13[8] + 1;
        v17 = v13[2];
        v18 = v13[4];
        v19 = v13[6];
        SystemTime.wYear = v13[10] + 1900;
        SystemTime.wDayOfWeek = v14;
        SystemTime.wMonth = v16;
        SystemTime.wDay = v19;
        SystemTime.wHour = v18;
        SystemTime.wMinute = v17;
        SystemTime.wSecond = v15;
        SystemTime.wMilliseconds = 0;
        FileTime = 0;
        v20 = SystemTimeToFileTime(&SystemTime, &FileTime);
        v21 = v66;
        if ( v20 )
          v21 = FileTime;
        v66 = v21;
      }
    }
  }
  v22 = 1025;
  v42[0] = 1025;
  if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v47, L"BuildLabEx", &v67, v42) )
  {
    v42[0] = 1025;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v47, L"BuildLab", &v67, v42) )
    {
      v67 = 0;
      v8 = (unsigned __int16 *)&v68;
      goto LABEL_20;
    }
  }
  else
  {
    FileTime.dwLowDateTime = 0;
    if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v47, L"UBR", (unsigned int *)&FileTime) )
    {
      std::wstring::wstring(&SystemTime, &v67);
      first_of = std::wstring::find_first_of(&SystemTime, v23, 0);
      if ( first_of == -1
        || (v26 = first_of + 1, v27 = std::wstring::find_first_of(&SystemTime, v25, first_of + 1), v27 == -1)
        || (_o__ultow_s(FileTime.dwLowDateTime, Source, 16, 10),
            v28 = wcsnlen(Source, 0x10u),
            v29 = v28,
            v30 = v63 - v27 + 1,
            v28 + v30 + v26 > 0x402) )
      {
        std::wstring::~wstring(&SystemTime);
        v36 = -2147467259;
LABEL_28:
        ATL::CRegKey::Close((ATL::CRegKey *)v47);
        return (unsigned int)v36;
      }
      v31 = &v67 + v26;
      v32 = 1026 - v26;
      _o_wcsncpy_s(v31, v32, Source, v28);
      v33 = v32 - v29;
      v34 = &v31[v29];
      p_SystemTime = &SystemTime;
      *(_QWORD *)v42 = v34;
      if ( v64 > 7 )
        p_SystemTime = *(SYSTEMTIME **)&SystemTime.wYear;
      _o_wcsncpy_s(v34, v33, (char *)p_SystemTime + 2 * v27, v30);
      v22 = v33 - v30;
      v8 = &v34[v30];
      std::wstring::~wstring(&SystemTime);
      v4 = v45;
      v7 = v46;
      goto LABEL_20;
    }
  }
  v22 = 1026 - v42[0];
  v8 = &v67 + v42[0];
LABEL_20:
  v42[0] = v22;
  if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v47, L"ProductName", v8, v42) )
  {
    *v8 = 0;
    LODWORD(v8) = (_DWORD)v8 + 2;
  }
  else
  {
    LODWORD(v8) = (_DWORD)v8 + 2 * v42[0];
  }
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetDeviceFamilyInfoEnum");
    if ( ProcAddress )
      ((void (__fastcall *)(__int128 *, char *, char *))ProcAddress)(&v65, (char *)&v65 + 8, (char *)&v65 + 12);
  }
LABEL_26:
  ATL::CRegKey::Close((ATL::CRegKey *)v47);
  memset_0(v48, 0, 0x58u);
  v39 = *((_QWORD *)this + 2);
  v52 = &v66;
  v48[0] = v7;
  v50 = a2;
  v53 = (_DWORD)v8 - ((unsigned int)v59 + 96);
  v51 = SystemConfigExGuid;
  v49 = 32;
  v54 = v4;
  v36 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v39 + 192LL))(v39, v48, 0, 0);
  if ( v36 < 0 )
    goto LABEL_28;
  memset_0(v55, 0, 0x58u);
  v40 = *((_QWORD *)this + 2);
  v59[3] = &v65;
  v58 = SystemConfigExGuid;
  v55[0] = v7;
  v57 = a2;
  v56 = 37;
  v60 = 16;
  v61 = v4;
  v36 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _QWORD))(*(_QWORD *)v40 + 192LL))(v40, v55, 0, 0);
  if ( v36 < 0 )
    goto LABEL_28;
  ATL::CRegKey::Close((ATL::CRegKey *)v47);
  return Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(this, a2, v4, v7);
}

```

## disassembly

```asm
0x1800766b0  push    rbp
0x1800766b2  push    rbx
0x1800766b3  push    rsi
0x1800766b4  push    rdi
0x1800766b5  push    r12
0x1800766b7  push    r13
0x1800766b9  push    r14
0x1800766bb  push    r15
0x1800766bd  lea     rbp, [rsp-8A8h]
0x1800766c5  sub     rsp, 9A8h
0x1800766cc  mov     rax, cs:__security_cookie
0x1800766d3  xor     rax, rsp
0x1800766d6  mov     [rbp+8E0h+var_50], rax
0x1800766dd  mov     r14d, r8d
0x1800766e0  mov     [rsp+9E0h+var_998], r8d
0x1800766e5  mov     rbx, rdx
0x1800766e8  mov     [rsp+9E0h+var_994], r9d
0x1800766ed  mov     r13, rcx
0x1800766f0  xor     edx, edx; Val
0x1800766f2  mov     r8d, 80Ch; Size
0x1800766f8  lea     rcx, [rbp+8E0h+var_880]; void *
0x1800766fc  mov     r15d, r9d
0x1800766ff  call    memset_0
0x180076704  xor     r12d, r12d
0x180076707  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18007670e  xorps   xmm0, xmm0
0x180076711  mov     [rsp+9E0h+var_990], r12
0x180076716  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18007671d  mov     [rsp+9E0h+var_988], r12
0x180076722  lea     rcx, [rsp+9E0h+var_990]; this
0x180076727  mov     [rsp+9E0h+var_980], r12
0x18007672c  lea     esi, [r12+1]
0x180076731  mov     r9d, esi; unsigned int
0x180076734  lea     rdi, [rbp+8E0h+var_878]
0x180076738  movups  [rbp+8E0h+var_890], xmm0
0x18007673c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180076741  test    eax, eax
0x180076743  jnz     loc_180076A12
0x180076749  lea     r8, [rsp+9E0h+var_9A8]; unsigned int *
0x18007674e  mov     [rsp+9E0h+var_9A8], r12d
0x180076753  lea     rdx, aInstalldate; "InstallDate"
0x18007675a  lea     rcx, [rsp+9E0h+var_990]; this
0x18007675f  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180076764  test    eax, eax
0x180076766  jnz     loc_18007680D
0x18007676c  movsxd  rax, [rsp+9E0h+var_9A8]
0x180076771  mov     qword ptr [rsp+9E0h+var_9B0], rax
0x180076776  call    cs:__imp__o__errno
0x18007677c  lea     rcx, [rsp+9E0h+var_9B0]
0x180076781  mov     [rax], r12d
0x180076784  call    cs:__imp__o__gmtime64
0x18007678a  mov     rdi, rax
0x18007678d  test    rax, rax
0x180076790  jz      short loc_18007680D
0x180076792  call    cs:__imp__o__errno
0x180076798  cmp     [rax], r12d
0x18007679b  jnz     short loc_18007680D
0x18007679d  movzx   edx, word ptr [rdi+18h]
0x1800767a1  mov     ecx, 76Ch
0x1800767a6  add     cx, [rdi+14h]
0x1800767aa  movzx   eax, word ptr [rdi+10h]
0x1800767ae  movzx   r11d, word ptr [rdi]
0x1800767b2  add     ax, si
0x1800767b5  movzx   r10d, word ptr [rdi+4]
0x1800767ba  movzx   r9d, word ptr [rdi+8]
0x1800767bf  movzx   r8d, word ptr [rdi+0Ch]
0x1800767c4  mov     [rbp+8E0h+SystemTime.wYear], cx
0x1800767c8  lea     rcx, [rbp+8E0h+SystemTime]; lpSystemTime
0x1800767cc  mov     [rbp+8E0h+SystemTime.wDayOfWeek], dx
0x1800767d0  lea     rdx, [rsp+9E0h+FileTime]; lpFileTime
0x1800767d5  mov     [rbp+8E0h+SystemTime.wMonth], ax
0x1800767d9  mov     [rbp+8E0h+SystemTime.wDay], r8w
0x1800767de  mov     [rbp+8E0h+SystemTime.wHour], r9w
0x1800767e3  mov     [rbp+8E0h+SystemTime.wMinute], r10w
0x1800767e8  mov     [rbp+8E0h+SystemTime.wSecond], r11w
0x1800767ed  mov     [rbp+8E0h+SystemTime.wMilliseconds], r12w
0x1800767f2  mov     qword ptr [rsp+9E0h+FileTime.dwLowDateTime], r12
0x1800767f7  call    cs:__imp_SystemTimeToFileTime
0x1800767fd  mov     rcx, [rbp+8E0h+var_880]
0x180076801  test    eax, eax
0x180076803  cmovnz  rcx, qword ptr [rsp+9E0h+FileTime.dwLowDateTime]
0x180076809  mov     [rbp+8E0h+var_880], rcx
0x18007680d  mov     esi, 401h
0x180076812  lea     r9, [rsp+9E0h+var_9B0]; unsigned int *
0x180076817  lea     r8, [rbp+8E0h+var_878]; unsigned __int16 *
0x18007681b  mov     [rsp+9E0h+var_9B0], esi
0x18007681f  lea     rdx, aBuildlabex; "BuildLabEx"
0x180076826  lea     rcx, [rsp+9E0h+var_990]; this
0x18007682b  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180076830  lea     rcx, [rsp+9E0h+var_990]; this
0x180076835  test    eax, eax
0x180076837  jnz     loc_180076962
0x18007683d  lea     r8, [rsp+9E0h+FileTime]; unsigned int *
0x180076842  mov     [rsp+9E0h+FileTime.dwLowDateTime], r12d
0x180076847  lea     rdx, aUbr; "UBR"
0x18007684e  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180076853  test    eax, eax
0x180076855  jnz     loc_18007697F
0x18007685b  lea     rdx, [rbp+8E0h+var_878]
0x18007685f  lea     rcx, [rbp+8E0h+SystemTime]
0x180076863  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076868  xor     r8d, r8d
0x18007686b  lea     rcx, [rbp+8E0h+SystemTime]
0x18007686f  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_first_of(ushort,unsigned __int64)
0x180076874  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180076878  jz      loc_18007694F
0x18007687e  lea     rsi, [rax+1]
0x180076882  mov     r8, rsi
0x180076885  lea     rcx, [rbp+8E0h+SystemTime]
0x180076889  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_first_of(ushort,unsigned __int64)
0x18007688e  mov     r14, rax
0x180076891  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180076895  jz      loc_18007694F
0x18007689b  mov     ecx, [rsp+9E0h+FileTime.dwLowDateTime]
0x18007689f  lea     rdx, [rbp+8E0h+Source]
0x1800768a6  mov     edi, 10h
0x1800768ab  mov     r8d, edi
0x1800768ae  lea     r9d, [rdi-6]
0x1800768b2  call    cs:__imp__o__ultow_s
0x1800768b8  mov     edx, edi; MaxCount
0x1800768ba  lea     rcx, [rbp+8E0h+Source]; Source
0x1800768c1  call    cs:__imp_wcsnlen
0x1800768c7  mov     r12, [rbp+8E0h+var_8A0]
0x1800768cb  mov     edx, 402h
0x1800768d0  sub     r12, r14
0x1800768d3  mov     r15, rax
0x1800768d6  inc     r12
0x1800768d9  lea     rcx, [r12+rsi]
0x1800768dd  add     rcx, rax
0x1800768e0  cmp     rcx, rdx
0x1800768e3  ja      short loc_18007694F
0x1800768e5  sub     edx, esi
0x1800768e7  lea     rdi, [rbp+8E0h+var_878]
0x1800768eb  lea     rdi, [rdi+rsi*2]
0x1800768ef  mov     r9, rax
0x1800768f2  mov     rcx, rdi
0x1800768f5  mov     esi, edx
0x1800768f7  lea     r8, [rbp+8E0h+Source]
0x1800768fe  call    cs:__imp__o_wcsncpy_s
0x180076904  sub     esi, r15d
0x180076907  lea     rdi, [rdi+r15*2]
0x18007690b  cmp     [rbp+8E0h+var_898], 7
0x180076910  lea     rax, [rbp+8E0h+SystemTime]
0x180076914  mov     edx, esi
0x180076916  mov     qword ptr [rsp+9E0h+var_9B0], rdi
0x18007691b  cmova   rax, qword ptr [rbp+8E0h+SystemTime.wYear]
0x180076920  mov     r9, r12
0x180076923  mov     rcx, rdi
0x180076926  lea     r8, [rax+r14*2]
0x18007692a  call    cs:__imp__o_wcsncpy_s
0x180076930  lea     rcx, [rbp+8E0h+SystemTime]
0x180076934  sub     esi, r12d
0x180076937  lea     rdi, [rdi+r12*2]
0x18007693b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180076940  mov     r14d, [rsp+9E0h+var_998]
0x180076945  xor     r12d, r12d
0x180076948  mov     r15d, [rsp+9E0h+var_994]
0x18007694d  jmp     short loc_18007699F
0x18007694f  lea     rcx, [rbp+8E0h+SystemTime]
0x180076953  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180076958  mov     edi, 80004005h
0x18007695d  jmp     loc_180076AE1
0x180076962  lea     r9, [rsp+9E0h+var_9B0]; unsigned int *
0x180076967  mov     [rsp+9E0h+var_9B0], esi
0x18007696b  lea     r8, [rbp+8E0h+var_878]; unsigned __int16 *
0x18007696f  lea     rdx, aBuildlab; "BuildLab"
0x180076976  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18007697b  test    eax, eax
0x18007697d  jnz     short loc_180076996
0x18007697f  mov     eax, [rsp+9E0h+var_9B0]
0x180076983  lea     rdi, [rbp+8E0h+var_878]
0x180076987  mov     esi, 402h
0x18007698c  sub     esi, [rsp+9E0h+var_9B0]
0x180076990  lea     rdi, [rdi+rax*2]
0x180076994  jmp     short loc_18007699F
0x180076996  mov     [rbp+8E0h+var_878], r12w
0x18007699b  lea     rdi, [rbp+8E0h+var_876]
0x18007699f  lea     r9, [rsp+9E0h+var_9B0]; unsigned int *
0x1800769a4  mov     [rsp+9E0h+var_9B0], esi
0x1800769a8  mov     r8, rdi; unsigned __int16 *
0x1800769ab  lea     rdx, aProductname; "ProductName"
0x1800769b2  lea     rcx, [rsp+9E0h+var_990]; this
0x1800769b7  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1800769bc  test    eax, eax
0x1800769be  jnz     short loc_1800769CA
0x1800769c0  mov     eax, [rsp+9E0h+var_9B0]
0x1800769c4  lea     rdi, [rdi+rax*2]
0x1800769c8  jmp     short loc_1800769D2
0x1800769ca  mov     [rdi], r12w
0x1800769ce  add     rdi, 2
0x1800769d2  xor     edx, edx; hFile
0x1800769d4  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800769db  mov     r8d, 800h; dwFlags
0x1800769e1  call    cs:__imp_LoadLibraryExW
0x1800769e7  test    rax, rax
0x1800769ea  jz      short loc_180076A12
0x1800769ec  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x1800769f3  mov     rcx, rax; hModule
0x1800769f6  call    cs:__imp_GetProcAddress
0x1800769fc  test    rax, rax
0x1800769ff  jz      short loc_180076A12
0x180076a01  lea     r8, [rbp+8E0h+var_890+0Ch]
0x180076a05  lea     rdx, [rbp+8E0h+var_890+8]
0x180076a09  lea     rcx, [rbp+8E0h+var_890]
0x180076a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a12  lea     rcx, [rsp+9E0h+var_990]; this
0x180076a17  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180076a1c  mov     esi, 58h ; 'X'
0x180076a21  lea     rcx, [rsp+9E0h+var_970]; void *
0x180076a26  mov     r8d, esi; Size
0x180076a29  xor     edx, edx; Val
0x180076a2b  call    memset_0
0x180076a30  movups  xmm0, xmmword ptr cs:SystemConfigExGuid.Data1
0x180076a37  mov     rcx, [r13+10h]
0x180076a3b  lea     rax, [rbp+8E0h+var_880]
0x180076a3f  mov     [rbp+8E0h+var_928], rax
0x180076a43  lea     rdx, [rsp+9E0h+var_970]
0x180076a48  lea     rax, [rbp+8E0h+var_880]
0x180076a4c  mov     [rsp+9E0h+var_970], r15w
0x180076a52  sub     edi, eax
0x180076a54  mov     [rbp+8E0h+var_960], rbx
0x180076a58  mov     [rbp+8E0h+var_920], edi
0x180076a5b  xor     r9d, r9d
0x180076a5e  movdqu  [rbp+8E0h+var_958], xmm0
0x180076a63  mov     [rsp+9E0h+var_96C], 20h ; ' '
0x180076a68  xor     r8d, r8d
0x180076a6b  mov     [rbp+8E0h+var_91C], r14d
0x180076a6f  mov     rax, [rcx]
0x180076a72  mov     rax, [rax+0C0h]
0x180076a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a7e  mov     edi, eax
0x180076a80  test    eax, eax
0x180076a82  js      short loc_180076AE1
0x180076a84  mov     r8d, esi; Size
0x180076a87  lea     rcx, [rbp+8E0h+var_910]; void *
0x180076a8b  xor     edx, edx; Val
0x180076a8d  call    memset_0
0x180076a92  movups  xmm0, xmmword ptr cs:SystemConfigExGuid.Data1
0x180076a99  mov     rcx, [r13+10h]
0x180076a9d  lea     rax, [rbp+8E0h+var_890]
0x180076aa1  mov     [rbp+8E0h+var_8C8], rax
0x180076aa5  lea     rdx, [rbp+8E0h+var_910]
0x180076aa9  movdqu  [rbp+8E0h+var_8F8], xmm0
0x180076aae  mov     [rbp+8E0h+var_910], r15w
0x180076ab3  xor     r9d, r9d
0x180076ab6  mov     [rbp+8E0h+var_900], rbx
0x180076aba  xor     r8d, r8d
0x180076abd  mov     [rbp+8E0h+var_90C], 25h ; '%'
0x180076ac1  mov     [rbp+8E0h+var_8C0], 10h
0x180076ac8  mov     [rbp+8E0h+var_8BC], r14d
0x180076acc  mov     rax, [rcx]
0x180076acf  mov     rax, [rax+0C0h]
0x180076ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076adb  mov     edi, eax
0x180076add  test    eax, eax
0x180076adf  jns     short loc_180076AEF
0x180076ae1  lea     rcx, [rsp+9E0h+var_990]; this
0x180076ae6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180076aeb  mov     eax, edi
0x180076aed  jmp     short loc_180076B0A
0x180076aef  lea     rcx, [rsp+9E0h+var_990]; this
0x180076af4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180076af9  mov     r9d, r15d; unsigned int
0x180076afc  mov     r8d, r14d; unsigned int
0x180076aff  mov     rdx, rbx; union _LARGE_INTEGER
0x180076b02  mov     rcx, r13; this
0x180076b05  call    ?OnAfterEvents@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)
0x180076b0a  mov     rcx, [rbp+8E0h+var_50]
0x180076b11  xor     rcx, rsp; StackCookie
0x180076b14  call    __security_check_cookie
0x180076b19  add     rsp, 9A8h
0x180076b20  pop     r15
0x180076b22  pop     r14
0x180076b24  pop     r13
0x180076b26  pop     r12
0x180076b28  pop     rdi
0x180076b29  pop     rsi
0x180076b2a  pop     rbx
0x180076b2b  pop     rbp
0x180076b2c  retn
```
