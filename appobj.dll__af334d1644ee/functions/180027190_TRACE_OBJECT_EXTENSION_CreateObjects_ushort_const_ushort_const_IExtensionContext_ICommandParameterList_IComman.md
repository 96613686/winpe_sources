# TRACE_OBJECT_EXTENSION::CreateObjects(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180027190`
- end: `0x18002798d`
- name: `?CreateObjects@TRACE_OBJECT_EXTENSION@@UEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `2045`
- prototype: `__int64 __fastcall(TRACE_OBJECT_EXTENSION *this, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e60`
- `0x180002e90`
- `0x180026f78`
- `0x180027190`
- `0x180028944`
- `0x18002b564`
- `0x18002b860`
- `0x18002bb20`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18002779d`
- `msvcrt!wcsstr` at `0x18002779d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002765f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002765f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002792b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002792b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180027650`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180027650`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180027832`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180027832`

## string_xrefs

- `0x18002762f`: `\fr*.xml`

## pseudocode

```c
__int64 __fastcall TRACE_OBJECT_EXTENSION::CreateObjects(
        TRACE_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IExtensionContext *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  unsigned __int16 *v9; // r14
  struct TRACE_OBJECT *v10; // rsi
  __int64 FirstFileW; // r13
  __int64 v12; // rcx
  int FrebLogDirectory; // ebx
  int v14; // eax
  int v15; // eax
  APP_OBJECT_UTILS *v16; // rcx
  APP_OBJECT_UTILS *v17; // rcx
  unsigned int v18; // r15d
  wchar_t *v19; // r12
  TRACE_OBJECT_EXTENSION *v20; // rcx
  const unsigned __int8 *v21; // rdx
  signed int LastError; // eax
  TRACE_OBJECT_EXTENSION *v23; // rcx
  int v24; // eax
  APP_OBJECT_UTILS *v25; // rcx
  wchar_t *v26; // rax
  struct SITE_OBJECT *v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-B8h] BYREF
  struct TRACE_OBJECT *v30; // [rsp+50h] [rbp-B0h] BYREF
  struct ICommandParameterList *v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *Str; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v35; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *SubStr; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v37; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v38; // [rsp+90h] [rbp-70h] BYREF
  struct ICommandObjectList *v39; // [rsp+98h] [rbp-68h]
  const unsigned __int8 *v40[5]; // [rsp+A0h] [rbp-60h] BYREF
  int v41; // [rsp+C8h] [rbp-38h]
  __int16 v42; // [rsp+CCh] [rbp-34h]
  int v43; // [rsp+D0h] [rbp-30h]
  _BYTE v44[32]; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+F8h] [rbp-8h]
  int v46; // [rsp+100h] [rbp+0h]
  __int16 v47; // [rsp+104h] [rbp+4h]
  int v48; // [rsp+108h] [rbp+8h]
  _BYTE v49[32]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v50; // [rsp+130h] [rbp+30h]
  int v51; // [rsp+138h] [rbp+38h]
  __int16 v52; // [rsp+13Ch] [rbp+3Ch]
  int v53; // [rsp+140h] [rbp+40h]
  _BYTE v54[32]; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int16 *v55; // [rsp+168h] [rbp+68h]
  int v56; // [rsp+170h] [rbp+70h]
  __int16 v57; // [rsp+174h] [rbp+74h]
  int v58; // [rsp+178h] [rbp+78h]
  _BYTE v59[32]; // [rsp+180h] [rbp+80h] BYREF
  const unsigned __int16 *v60; // [rsp+1A0h] [rbp+A0h]
  int v61; // [rsp+1A8h] [rbp+A8h]
  __int16 v62; // [rsp+1ACh] [rbp+ACh]
  int v63; // [rsp+1B0h] [rbp+B0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+1C0h] [rbp+C0h] BYREF
  __int16 v65; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v66[510]; // [rsp+412h] [rbp+312h] BYREF
  __int16 v67; // [rsp+610h] [rbp+510h] BYREF
  _BYTE v68[510]; // [rsp+612h] [rbp+512h] BYREF
  __int16 v69; // [rsp+810h] [rbp+710h] BYREF
  _BYTE v70[510]; // [rsp+812h] [rbp+712h] BYREF
  __int16 v71; // [rsp+A10h] [rbp+910h] BYREF
  _BYTE v72[526]; // [rsp+A12h] [rbp+912h] BYREF
  __int16 v73; // [rsp+C20h] [rbp+B20h] BYREF
  _BYTE v74[526]; // [rsp+C22h] [rbp+B22h] BYREF

  v39 = a6;
  memset_0(v66, 0, sizeof(v66));
  v62 = 256;
  v60 = (const unsigned __int16 *)&v65;
  v63 = 0;
  v61 = 512;
  v65 = 0;
  memset_0(v68, 0, sizeof(v68));
  v51 = 512;
  v50 = (unsigned __int16 *)&v67;
  v52 = 256;
  v53 = 0;
  v67 = 0;
  memset_0(v72, 0, 0x206u);
  v42 = 256;
  v40[4] = (const unsigned __int8 *)&v71;
  v41 = 520;
  v43 = 0;
  v71 = 0;
  memset_0(v74, 0, 0x206u);
  v46 = 520;
  lpFileName = (LPCWSTR)&v73;
  v47 = 256;
  v48 = 0;
  v73 = 0;
  v9 = 0;
  v33 = 0;
  v31 = 0;
  v32 = 0;
  v28 = 0;
  v35 = 0;
  v37 = 0;
  v29 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v10 = 0;
  v30 = 0;
  FirstFileW = -1;
  memset_0(v70, 0, sizeof(v70));
  v56 = 512;
  v58 = 0;
  v55 = (unsigned __int16 *)&v69;
  v69 = 0;
  SubStr = 0;
  Str = 0;
  v38 = 0;
  v57 = 256;
  if ( !a2 || !a3 || !a4 || !a5 || !v39 )
  {
LABEL_68:
    FrebLogDirectory = -2147024809;
    goto LABEL_69;
  }
  FrebLogDirectory = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a5 + 80LL))(
                       a5,
                       &v31);
  if ( FrebLogDirectory < 0 )
    goto LABEL_69;
  if ( *a3 )
    goto LABEL_19;
  v14 = APP_OBJECT_UTILS::PopParameter((APP_OBJECT_UTILS *)v12, a4, v31, L"TRACE.NAME", (struct STRU *)v59, 0, 1);
  v12 = 0x80000000LL;
  FrebLogDirectory = v14;
  if ( (int)(v14 + 0x80000000) >= 0 && v14 != -2147023483 )
    goto LABEL_69;
  a3 = v60;
  if ( *v60 )
  {
LABEL_19:
    FrebLogDirectory = APP_OBJECT_UTILS::ValidateEmptyParameters((APP_OBJECT_UTILS *)v12, a4, v31);
    if ( FrebLogDirectory < 0 )
      goto LABEL_69;
    FrebLogDirectory = APP_OBJECT_UTILS::ResolveConfigPath(
                         v17,
                         a4,
                         a3,
                         (struct STRU *)v49,
                         (const unsigned __int16 **)&v35,
                         &v28);
    if ( FrebLogDirectory < 0 || !v28 || !v35 || !*v35 )
      goto LABEL_69;
    v9 = v35 + 1;
  }
  else
  {
    v15 = APP_OBJECT_UTILS::PopParameter((APP_OBJECT_UTILS *)0x80000000LL, a4, v31, L"url", (struct STRU *)v54, 0, 1);
    FrebLogDirectory = v15;
    if ( v15 < 0 )
    {
      if ( v15 != -2147023483 )
        goto LABEL_69;
    }
    else
    {
      FrebLogDirectory = APP_OBJECT_UTILS::ResolveUrl(v16, v55, 0, (const unsigned __int16 **)&SubStr, 0);
      if ( FrebLogDirectory < 0 )
        goto LABEL_69;
    }
    FrebLogDirectory = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a4 + 192LL))(
                         a4,
                         &v33);
    if ( FrebLogDirectory < 0 )
      goto LABEL_69;
    FrebLogDirectory = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a4 + 184LL))(
                         a4,
                         &v32);
    if ( FrebLogDirectory < 0 )
      goto LABEL_69;
    FrebLogDirectory = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, unsigned __int16 *, __int64, __int64, _DWORD))(*(_QWORD *)a4 + 56LL))(
                         a4,
                         L"SITE",
                         v55,
                         v33,
                         v32,
                         0);
    if ( FrebLogDirectory < 0 )
      goto LABEL_69;
  }
  if ( v9 )
  {
    if ( !v28 )
    {
      FrebLogDirectory = -2147418113;
      goto LABEL_69;
    }
    v29 = 1;
  }
  else
  {
    FrebLogDirectory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 32LL))(v32, &v29);
    if ( FrebLogDirectory < 0 )
      goto LABEL_69;
    if ( !v29 )
    {
      FrebLogDirectory = 1;
      goto LABEL_69;
    }
    FrebLogDirectory = (*(__int64 (__fastcall **)(__int64, _QWORD, struct SITE_OBJECT **))(*(_QWORD *)v32 + 40LL))(
                         v32,
                         0,
                         &v28);
    if ( FrebLogDirectory < 0 )
      goto LABEL_69;
  }
  v18 = 0;
  v19 = SubStr;
  while ( 1 )
  {
    FrebLogDirectory = (*(__int64 (__fastcall **)(struct SITE_OBJECT *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v28 + 80LL))(
                         v28,
                         L"SITE.NAME",
                         &v37);
    if ( FrebLogDirectory < 0 )
      break;
    FrebLogDirectory = TRACE_OBJECT_EXTENSION::GetFrebLogDirectory(v20, a4, v28, (struct STRU *)v40);
    if ( FrebLogDirectory < 0 )
      break;
    FrebLogDirectory = STRU::Copy((STRU *)v44, v40);
    if ( FrebLogDirectory < 0 )
      break;
    if ( v9 )
    {
      FrebLogDirectory = STRU::Append((STRU *)v44, (const unsigned __int8 *)L"\\");
      if ( FrebLogDirectory < 0 )
        break;
      v21 = (const unsigned __int8 *)v9;
    }
    else
    {
      v21 = (const unsigned __int8 *)L"\\fr*.xml";
    }
    FrebLogDirectory = STRU::Append((STRU *)v44, v21);
    if ( FrebLogDirectory < 0 )
      break;
    FirstFileW = (__int64)FindFirstFileW(lpFileName, &FindFileData);
    if ( FirstFileW != -1 )
    {
      while ( 1 )
      {
        FrebLogDirectory = STRU::Copy((STRU *)v49, (const unsigned __int8 *)v37);
        if ( FrebLogDirectory < 0 )
          goto LABEL_69;
        FrebLogDirectory = STRU::Append((STRU *)v49, (const unsigned __int8 *)L"/");
        if ( FrebLogDirectory < 0 )
          goto LABEL_69;
        FrebLogDirectory = STRU::Append((STRU *)v49, (const unsigned __int8 *)FindFileData.cFileName);
        if ( FrebLogDirectory < 0 )
          goto LABEL_69;
        FrebLogDirectory = STRU::Copy((STRU *)v44, v40);
        if ( FrebLogDirectory < 0 )
          goto LABEL_69;
        FrebLogDirectory = STRU::Append((STRU *)v44, (const unsigned __int8 *)L"\\");
        if ( FrebLogDirectory < 0 )
          goto LABEL_69;
        FrebLogDirectory = STRU::Append((STRU *)v44, (const unsigned __int8 *)FindFileData.cFileName);
        if ( FrebLogDirectory < 0 )
          goto LABEL_69;
        v24 = TRACE_OBJECT_EXTENSION::CreateFrebLogObject(v23, a4, v50, lpFileName, &v30);
        v10 = v30;
        FrebLogDirectory = v24;
        if ( v24 < 0 )
          goto LABEL_69;
        if ( !v19 )
          goto LABEL_57;
        FrebLogDirectory = (*(__int64 (__fastcall **)(struct TRACE_OBJECT *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v30 + 80LL))(
                             v30,
                             L"URL",
                             &v38);
        if ( FrebLogDirectory < 0 )
          goto LABEL_69;
        FrebLogDirectory = APP_OBJECT_UTILS::ResolveUrl(v25, v38, 0, (const unsigned __int16 **)&Str, 0);
        if ( FrebLogDirectory < 0 )
          goto LABEL_69;
        v26 = wcsstr(Str, v19);
        if ( v26 == Str )
        {
LABEL_57:
          LODWORD(v30) = 1;
          if ( !v10 || !v31 )
            goto LABEL_68;
          FrebLogDirectory = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct TRACE_OBJECT *, struct ICommandParameterList *, struct TRACE_OBJECT **))(*(_QWORD *)a4 + 152LL))(
                               a4,
                               v10,
                               v31,
                               &v30);
          if ( FrebLogDirectory < 0 )
            goto LABEL_69;
          if ( (_DWORD)v30 )
          {
            FrebLogDirectory = (*(__int64 (__fastcall **)(struct ICommandObjectList *, struct TRACE_OBJECT *))(*(_QWORD *)v39 + 24LL))(
                                 v39,
                                 v10);
            if ( FrebLogDirectory < 0 )
              goto LABEL_69;
          }
        }
        (*(void (__fastcall **)(struct TRACE_OBJECT *))(*(_QWORD *)v10 + 16LL))(v10);
        v10 = 0;
        v30 = 0;
        if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
          goto LABEL_63;
      }
    }
    LastError = GetLastError();
    if ( ((LastError - 2) & 0xFFFFFFEE) != 0 || LastError == 19 )
    {
      if ( LastError > 0 )
        FrebLogDirectory = (unsigned __int16)LastError | 0x80070000;
      else
        FrebLogDirectory = LastError;
      break;
    }
LABEL_63:
    (*(void (__fastcall **)(struct SITE_OBJECT *))(*(_QWORD *)v28 + 16LL))(v28);
    ++v18;
    v28 = 0;
    if ( v18 < v29 )
    {
      FrebLogDirectory = (*(__int64 (__fastcall **)(__int64, _QWORD, struct SITE_OBJECT **))(*(_QWORD *)v32 + 40LL))(
                           v32,
                           v18,
                           &v28);
      if ( FrebLogDirectory >= 0 )
        continue;
    }
    break;
  }
LABEL_69:
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(struct SITE_OBJECT *))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(struct TRACE_OBJECT *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( FirstFileW )
    FindClose((HANDLE)FirstFileW);
  BUFFER::~BUFFER((BUFFER *)v54);
  BUFFER::~BUFFER((BUFFER *)v44);
  BUFFER::~BUFFER((BUFFER *)v40);
  BUFFER::~BUFFER((BUFFER *)v49);
  BUFFER::~BUFFER((BUFFER *)v59);
  return (unsigned int)FrebLogDirectory;
}

```

## disassembly

```asm
0x180027190  mov     [rsp-8+arg_0], rbx
0x180027195  push    rbp
0x180027196  push    rsi
0x180027197  push    rdi
0x180027198  push    r12
0x18002719a  push    r13
0x18002719c  push    r14
0x18002719e  push    r15
0x1800271a0  lea     rbp, [rsp-0D40h]
0x1800271a8  sub     rsp, 0E40h
0x1800271af  mov     rax, cs:__security_cookie
0x1800271b6  xor     rax, rsp
0x1800271b9  mov     [rbp+0D70h+var_40], rax
0x1800271c0  mov     rax, [rbp+0D70h+arg_28]
0x1800271c7  lea     rcx, [rbp+0D70h+var_A5E]; void *
0x1800271ce  mov     r12, [rbp+0D70h+arg_20]
0x1800271d5  mov     r15, r8
0x1800271d8  mov     rbx, rdx
0x1800271db  mov     [rbp+0D70h+var_DD8], rax
0x1800271df  mov     r14d, 1FEh
0x1800271e5  xor     edx, edx; Val
0x1800271e7  mov     r8d, r14d; Size
0x1800271ea  mov     rdi, r9
0x1800271ed  call    memset_0
0x1800271f2  lea     rax, [rbp+0D70h+var_A60]
0x1800271f9  mov     [rbp+0D70h+var_CC4], 100h
0x180027202  xor     r13d, r13d
0x180027205  mov     [rbp+0D70h+var_CD0], rax
0x18002720c  lea     esi, [r14+2]
0x180027210  mov     [rbp+0D70h+var_CC0], r13d
0x180027217  mov     r8d, r14d; Size
0x18002721a  mov     [rbp+0D70h+var_CC8], esi
0x180027220  xor     edx, edx; Val
0x180027222  mov     [rbp+0D70h+var_A60], r13w
0x18002722a  lea     rcx, [rbp+0D70h+var_85E]; void *
0x180027231  call    memset_0
0x180027236  lea     rax, [rbp+0D70h+var_860]
0x18002723d  mov     [rbp+0D70h+var_D38], esi
0x180027240  lea     r14d, [rsi+6]
0x180027244  mov     [rbp+0D70h+var_D40], rax
0x180027248  mov     r8d, r14d; Size
0x18002724b  mov     [rbp+0D70h+var_D34], 100h
0x180027251  xor     edx, edx; Val
0x180027253  mov     [rbp+0D70h+var_D30], r13d
0x180027257  lea     rcx, [rbp+0D70h+var_45E]; void *
0x18002725e  mov     [rbp+0D70h+var_860], r13w
0x180027266  call    memset_0
0x18002726b  lea     rax, [rbp+0D70h+var_460]
0x180027272  mov     [rbp+0D70h+var_DA4], 100h
0x180027278  lea     esi, [r14+2]
0x18002727c  mov     [rbp+0D70h+var_DB0], rax
0x180027280  mov     r8d, r14d; Size
0x180027283  mov     [rbp+0D70h+var_DA8], esi
0x180027286  xor     edx, edx; Val
0x180027288  mov     [rbp+0D70h+var_DA0], r13d
0x18002728c  lea     rcx, [rbp+0D70h+var_24E]; void *
0x180027293  mov     [rbp+0D70h+var_460], r13w
0x18002729b  call    memset_0
0x1800272a0  lea     rax, [rbp+0D70h+var_250]
0x1800272a7  mov     [rbp+0D70h+var_D70], esi
0x1800272aa  xor     edx, edx; Val
0x1800272ac  mov     [rbp+0D70h+lpFileName], rax
0x1800272b0  lea     r8d, [rsi+48h]; Size
0x1800272b4  mov     [rbp+0D70h+var_D6C], 100h
0x1800272ba  lea     rcx, [rbp+0D70h+FindFileData]; void *
0x1800272c1  mov     [rbp+0D70h+var_D68], r13d
0x1800272c5  mov     [rbp+0D70h+var_250], r13w
0x1800272cd  mov     r14d, r13d
0x1800272d0  mov     [rsp+0E70h+var_E08], r13
0x1800272d5  mov     [rsp+0E70h+var_E18], r13
0x1800272da  mov     [rsp+0E70h+var_E10], r13
0x1800272df  mov     [rsp+0E70h+var_E30], r13
0x1800272e4  mov     [rsp+0E70h+var_DF8], r13
0x1800272e9  mov     [rbp+0D70h+var_DE8], r13
0x1800272ed  mov     [rsp+0E70h+var_E28], r13d
0x1800272f2  call    memset_0
0x1800272f7  xor     esi, esi
0x1800272f9  lea     rcx, [rbp+0D70h+var_65E]; void *
0x180027300  xor     edx, edx; Val
0x180027302  mov     [rsp+0E70h+var_E20], rsi
0x180027307  mov     r8d, 1FEh; Size
0x18002730d  or      r13, 0FFFFFFFFFFFFFFFFh
0x180027311  call    memset_0
0x180027316  xor     ecx, ecx
0x180027318  mov     [rbp+0D70h+var_D00], 200h
0x18002731f  lea     rax, [rbp+0D70h+var_660]
0x180027326  mov     [rbp+0D70h+var_CF8], ecx
0x180027329  mov     [rbp+0D70h+var_D08], rax
0x18002732d  test    rbx, rbx
0x180027330  mov     [rbp+0D70h+var_660], cx
0x180027337  mov     [rbp+0D70h+SubStr], rcx
0x18002733b  mov     [rsp+0E70h+Str], rcx
0x180027340  mov     [rbp+0D70h+var_DE0], rcx
0x180027344  mov     [rbp+0D70h+var_CFC], 100h
0x18002734a  jz      loc_18002789B
0x180027350  test    r15, r15
0x180027353  jz      loc_18002789B
0x180027359  test    rdi, rdi
0x18002735c  jz      loc_18002789B
0x180027362  test    r12, r12
0x180027365  jz      loc_18002789B
0x18002736b  cmp     [rbp+0D70h+var_DD8], rcx
0x18002736f  jz      loc_18002789B
0x180027375  mov     rax, [r12]
0x180027379  lea     rdx, [rsp+0E70h+var_E18]
0x18002737e  mov     rcx, r12
0x180027381  mov     rax, [rax+50h]
0x180027385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002738a  xor     r12d, r12d
0x18002738d  mov     ebx, eax
0x18002738f  test    eax, eax
0x180027391  js      loc_1800278A3
0x180027397  cmp     [r15], r12w
0x18002739b  jnz     loc_1800274D0
0x1800273a1  mov     r8, [rsp+0E70h+var_E18]; struct ICommandParameterList *
0x1800273a6  lea     rax, [rbp+0D70h+var_CF0]
0x1800273ad  mov     [rsp+0E70h+var_E40], 1; int
0x1800273b5  lea     r9, aTraceName; "TRACE.NAME"
0x1800273bc  mov     dword ptr [rsp+0E70h+var_E48], r12d; int
0x1800273c1  mov     rdx, rdi; struct IExtensionContext *
0x1800273c4  mov     [rsp+0E70h+var_E50], rax; struct STRU *
0x1800273c9  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x1800273ce  mov     ecx, 80000000h; this
0x1800273d3  mov     ebx, eax
0x1800273d5  add     eax, ecx
0x1800273d7  test    ecx, eax
0x1800273d9  jnz     short loc_1800273E7
0x1800273db  cmp     ebx, 80070585h
0x1800273e1  jnz     loc_1800278A3
0x1800273e7  mov     r15, [rbp+0D70h+var_CD0]
0x1800273ee  cmp     [r15], r12w
0x1800273f2  jnz     loc_1800274D0
0x1800273f8  mov     r8, [rsp+0E70h+var_E18]; struct ICommandParameterList *
0x1800273fd  lea     rax, [rbp+0D70h+var_D28]
0x180027401  mov     [rsp+0E70h+var_E40], 1; int
0x180027409  lea     r9, aUrl_1; "url"
0x180027410  mov     dword ptr [rsp+0E70h+var_E48], r12d; int
0x180027415  mov     rdx, rdi; struct IExtensionContext *
0x180027418  mov     [rsp+0E70h+var_E50], rax; struct STRU *
0x18002741d  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180027422  mov     ebx, eax
0x180027424  test    eax, eax
0x180027426  js      short loc_180027449
0x180027428  mov     rdx, [rbp+0D70h+var_D08]; unsigned __int16 *
0x18002742c  lea     r9, [rbp+0D70h+SubStr]; unsigned __int16 **
0x180027430  xor     r8d, r8d; struct STRU *
0x180027433  mov     [rsp+0E70h+var_E50], r12; int *
0x180027438  call    ?ResolveUrl@APP_OBJECT_UTILS@@QEAAJPEBGPEAVSTRU@@PEAPEBGPEAH@Z; APP_OBJECT_UTILS::ResolveUrl(ushort const *,STRU *,ushort const * *,int *)
0x18002743d  mov     ebx, eax
0x18002743f  test    eax, eax
0x180027441  js      loc_1800278A3
0x180027447  jmp     short loc_180027454
0x180027449  cmp     eax, 80070585h
0x18002744e  jnz     loc_1800278A3
0x180027454  mov     rax, [rdi]
0x180027457  lea     rdx, [rsp+0E70h+var_E08]
0x18002745c  mov     rcx, rdi
0x18002745f  mov     rax, [rax+0C0h]
0x180027466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002746b  mov     ebx, eax
0x18002746d  test    eax, eax
0x18002746f  js      loc_1800278A3
0x180027475  mov     rax, [rdi]
0x180027478  lea     rdx, [rsp+0E70h+var_E10]
0x18002747d  mov     rcx, rdi
0x180027480  mov     rax, [rax+0B8h]
0x180027487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002748c  mov     ebx, eax
0x18002748e  test    eax, eax
0x180027490  js      loc_1800278A3
0x180027496  mov     rcx, [rsp+0E70h+var_E10]
0x18002749b  lea     rdx, aSite_0; "SITE"
0x1800274a2  mov     rax, [rdi]
0x1800274a5  mov     r9, [rsp+0E70h+var_E08]
0x1800274aa  mov     r8, [rbp+0D70h+var_D08]
0x1800274ae  mov     dword ptr [rsp+0E70h+var_E48], r12d
0x1800274b3  mov     rax, [rax+38h]
0x1800274b7  mov     [rsp+0E70h+var_E50], rcx
0x1800274bc  mov     rcx, rdi
0x1800274bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274c4  mov     ebx, eax
0x1800274c6  test    eax, eax
0x1800274c8  js      loc_1800278A3
0x1800274ce  jmp     short loc_18002753B
0x1800274d0  mov     r8, [rsp+0E70h+var_E18]; struct ICommandParameterList *
0x1800274d5  mov     rdx, rdi; struct IExtensionContext *
0x1800274d8  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x1800274dd  mov     ebx, eax
0x1800274df  test    eax, eax
0x1800274e1  js      loc_1800278A3
0x1800274e7  lea     rax, [rsp+0E70h+var_E30]
0x1800274ec  mov     r8, r15; unsigned __int16 *
0x1800274ef  mov     [rsp+0E70h+var_E48], rax; struct SITE_OBJECT **
0x1800274f4  lea     r9, [rbp+0D70h+var_D60]; struct STRU *
0x1800274f8  lea     rax, [rsp+0E70h+var_DF8]
0x1800274fd  mov     rdx, rdi; struct IExtensionContext *
0x180027500  mov     [rsp+0E70h+var_E50], rax; unsigned __int16 **
0x180027505  call    ?ResolveConfigPath@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAVSTRU@@PEAPEBGPEAPEAVSITE_OBJECT@@@Z; APP_OBJECT_UTILS::ResolveConfigPath(IExtensionContext *,ushort const *,STRU *,ushort const * *,SITE_OBJECT * *)
0x18002750a  mov     ebx, eax
0x18002750c  test    eax, eax
0x18002750e  js      loc_1800278A3
0x180027514  cmp     [rsp+0E70h+var_E30], r12
0x180027519  jz      loc_1800278A3
0x18002751f  mov     r14, [rsp+0E70h+var_DF8]
0x180027524  test    r14, r14
0x180027527  jz      loc_1800278A3
0x18002752d  cmp     [r14], r12w
0x180027531  jz      loc_1800278A3
0x180027537  add     r14, 2
0x18002753b  test    r14, r14
0x18002753e  jz      short loc_18002755B
0x180027540  cmp     [rsp+0E70h+var_E30], r12
0x180027545  jnz     short loc_180027551
0x180027547  mov     ebx, 8000FFFFh
0x18002754c  jmp     loc_1800278A3
0x180027551  mov     [rsp+0E70h+var_E28], 1
0x180027559  jmp     short loc_1800275A8
0x18002755b  mov     rcx, [rsp+0E70h+var_E10]
0x180027560  lea     rdx, [rsp+0E70h+var_E28]
0x180027565  mov     rax, [rcx]
0x180027568  mov     rax, [rax+20h]
0x18002756c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027571  mov     ebx, eax
0x180027573  test    eax, eax
0x180027575  js      loc_1800278A3
0x18002757b  cmp     [rsp+0E70h+var_E28], 1
0x180027580  jb      loc_180027894
0x180027586  mov     rcx, [rsp+0E70h+var_E10]
0x18002758b  lea     r8, [rsp+0E70h+var_E30]
0x180027590  xor     edx, edx
0x180027592  mov     rax, [rcx]
0x180027595  mov     rax, [rax+28h]
0x180027599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002759e  mov     ebx, eax
0x1800275a0  test    eax, eax
0x1800275a2  js      loc_1800278A3
0x1800275a8  mov     r15d, r12d
0x1800275ab  mov     r12, [rbp+0D70h+SubStr]
0x1800275af  mov     rcx, [rsp+0E70h+var_E30]
0x1800275b4  lea     r8, [rbp+0D70h+var_DE8]
0x1800275b8  lea     rdx, aSiteName; "SITE.NAME"
0x1800275bf  mov     rax, [rcx]
0x1800275c2  mov     rax, [rax+50h]
0x1800275c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275cb  mov     ebx, eax
0x1800275cd  test    eax, eax
0x1800275cf  js      loc_1800278A0
0x1800275d5  mov     r8, [rsp+0E70h+var_E30]; struct SITE_OBJECT *
0x1800275da  lea     r9, [rbp+0D70h+var_DD0]; struct STRU *
0x1800275de  mov     rdx, rdi; struct IExtensionContext *
0x1800275e1  call    ?GetFrebLogDirectory@TRACE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVSITE_OBJECT@@PEAVSTRU@@@Z; TRACE_OBJECT_EXTENSION::GetFrebLogDirectory(IExtensionContext *,SITE_OBJECT *,STRU *)
0x1800275e6  mov     ebx, eax
0x1800275e8  test    eax, eax
0x1800275ea  js      loc_1800278A0
0x1800275f0  lea     rdx, [rbp+0D70h+var_DD0]; struct STRU *
0x1800275f4  lea     rcx, [rbp+0D70h+var_D98]; this
0x1800275f8  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800275fd  mov     ebx, eax
0x1800275ff  test    eax, eax
0x180027601  js      loc_1800278A0
0x180027607  lea     rcx, [rbp+0D70h+var_D98]; this
0x18002760b  test    r14, r14
0x18002760e  jz      short loc_18002762F
0x180027610  lea     rdx, asc_180039420; "\\"
0x180027617  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002761c  mov     ebx, eax
0x18002761e  test    eax, eax
0x180027620  js      loc_1800278A0
0x180027626  mov     rdx, r14
0x180027629  lea     rcx, [rbp+0D70h+var_D98]
0x18002762d  jmp     short loc_180027636
0x18002762f  lea     rdx, aFrXml; "\\fr*.xml"
0x180027636  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002763b  mov     ebx, eax
0x18002763d  test    eax, eax
0x18002763f  js      loc_1800278A0
0x180027645  mov     rcx, [rbp+0D70h+lpFileName]; lpFileName
0x180027649  lea     rdx, [rbp+0D70h+FindFileData]; lpFindFileData
0x180027650  call    cs:__imp_FindFirstFileW
0x180027656  mov     r13, rax
0x180027659  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002765d  jnz     short loc_18002768B
0x18002765f  call    cs:__imp_GetLastError
0x180027665  lea     ecx, [rax-2]
0x180027668  test    ecx, 0FFFFFFEEh
0x18002766e  jnz     short loc_180027679
0x180027670  cmp     eax, 13h
0x180027673  jnz     loc_180027840
0x180027679  xor     r12d, r12d
0x18002767c  test    eax, eax
0x18002767e  jg      loc_180027889
0x180027684  mov     ebx, eax
0x180027686  jmp     loc_1800278A3
0x18002768b  mov     rdx, [rbp+0D70h+var_DE8]; unsigned __int16 *
0x18002768f  lea     rcx, [rbp+0D70h+var_D60]; this
0x180027693  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180027698  mov     ebx, eax
0x18002769a  test    eax, eax
0x18002769c  js      loc_1800278A0
0x1800276a2  lea     rdx, SubStr; "/"
  ... truncated ...
```
