# CManagedAppProcessor::CManagedAppProcessor(ulong,void *,HKEY__ *,ulong (*)(int,ushort *),int,int,CRsopAppContext *,ulong &)

- ea: `0x18000df00`
- end: `0x18000e4ea`
- name: `??0CManagedAppProcessor@@QEAA@KPEAXPEAUHKEY__@@P6AKHPEAG@ZHHPEAVCRsopAppContext@@AEAK@Z`
- size: `1514`
- prototype: `CManagedAppProcessor *__fastcall(CManagedAppProcessor *this, __int16, void *, HKEY, __int64 cbData, int, int, struct CRsopAppContext *, unsigned int *)`
- caller_count: `6`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000219c`
- `0x18000239c`
- `0x180002d40`
- `0x180003370`
- `0x18000b7e8`
- `0x18000bd38`

## callees

- `0x18000df00`
- `0x18000e8e8`
- `0x18000eeac`
- `0x18000ffdc`
- `0x180011268`
- `0x1800114b4`
- `0x1800119c4`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e1d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e21c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e25d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e25d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e29a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e2df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e29a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e2df`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e34b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e3d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e34b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e3d7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000e35c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000e35c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000e212`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000e212`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000e391`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000e391`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18000e37e`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18000e37e`

## pseudocode

```c
CManagedAppProcessor *__fastcall CManagedAppProcessor::CManagedAppProcessor(
        CManagedAppProcessor *this,
        __int16 a2,
        void *a3,
        HKEY a4,
        __int64 cbData,
        int a6,
        int a7,
        struct CRsopAppContext *a8,
        unsigned int *a9)
{
  char *v10; // r15
  char *v11; // rcx
  int v12; // ecx
  int v13; // eax
  _DWORD *v14; // rsi
  int v15; // ecx
  bool v16; // zf
  int v17; // edx
  int v18; // r12d
  struct CRsopAppContext *v19; // rdi
  signed int LastError; // eax
  signed int v21; // edi
  unsigned int *v22; // rdi
  LSTATUS v23; // eax
  LSTATUS Key; // eax
  LSTATUS v25; // eax
  int v26; // r14d
  HKEY *v27; // r12
  int v28; // eax
  LSTATUS Value; // eax
  void *v30; // rcx
  unsigned int ScriptDirPath; // eax
  BYTE v33[8]; // [rsp+58h] [rbp-41h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+60h] [rbp-39h] BYREF
  int Data; // [rsp+F0h] [rbp+57h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+F8h] [rbp+5Fh]
  HKEY hKey; // [rsp+100h] [rbp+67h]

  hKey = a4;
  ExistingTokenHandle = a3;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 1) = this;
  *(_QWORD *)this = this;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 11) = (char *)this + 80;
  *((_QWORD *)this + 10) = (char *)this + 80;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 4) = &CAppList::`vftable';
  *((_QWORD *)this + 14) = this;
  v10 = (char *)this + 360;
  *((_QWORD *)this + 15) = (char *)this + 360;
  *((_DWORD *)this + 32) = -2147467259;
  *((_DWORD *)this + 33) = 0;
  v11 = (char *)this + 136;
  *((_QWORD *)v11 + 8) = 0;
  *((_QWORD *)v11 + 9) = 0;
  *((_QWORD *)v11 + 7) = v11 + 48;
  *((_QWORD *)v11 + 6) = v11 + 48;
  *((_QWORD *)v11 + 1) = 0;
  *((_QWORD *)v11 + 2) = 0;
  *((_QWORD *)v11 + 3) = 0;
  *((_QWORD *)v11 + 4) = 0;
  *((_QWORD *)v11 + 5) = 0;
  *(_QWORD *)v11 = &CAppList::`vftable';
  *((_QWORD *)v11 + 10) = this;
  *((_QWORD *)v11 + 11) = 0;
  *((_DWORD *)v11 + 24) = -2147467259;
  *((_DWORD *)v11 + 25) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = cbData;
  *((_QWORD *)this + 43) = 0;
  *(_QWORD *)v10 = 0;
  *((_QWORD *)v10 + 1) = 0;
  *((_QWORD *)v10 + 2) = 0;
  *((_QWORD *)v10 + 3) = L"{c6dc5466-785a-11d2-84d0-00c04fb169f7}";
  *((_DWORD *)v10 + 8) = 0;
  *((_DWORD *)v10 + 9) = 2;
  *((_QWORD *)v10 + 5) = 0;
  *((_QWORD *)v10 + 6) = 0;
  *((_DWORD *)v10 + 14) = -2147024882;
  *((_QWORD *)v10 + 8) = 0;
  *((_QWORD *)v10 + 9) = 0;
  *((_DWORD *)v10 + 20) = 0;
  *((_DWORD *)v10 + 21) = 4;
  *((_QWORD *)v10 + 11) = 0;
  *((_QWORD *)v10 + 12) = 0;
  *((_QWORD *)v10 + 13) = 0;
  *((_DWORD *)v10 + 28) = 0;
  *((_QWORD *)v10 + 15) = 0;
  *((_DWORD *)v10 + 32) = 0;
  LODWORD(cbData) = 0;
  *(_DWORD *)v33 = 0;
  Data = 0;
  *((_DWORD *)this + 74) = (a2 & 1) == 0;
  if ( (a2 & 0x80u) == 0 || (gDebugLevel & 0x20) != 0 || (a2 & 0x200) != 0 )
  {
    v12 = 0;
    v13 = a2 & 0x200;
  }
  else
  {
    v12 = 1;
    v13 = 0;
  }
  v14 = (_DWORD *)((char *)this + 300);
  *((_DWORD *)this + 75) = v12;
  if ( (a2 & 0x1000) == 0 || (gDebugLevel & 0x20) != 0 || (v15 = 1, v13) )
    v15 = 0;
  *((_DWORD *)this + 76) = v15;
  if ( v15 || (v16 = (a2 & 0x10) == 0, v17 = 1, v16) )
    v17 = 0;
  *((_DWORD *)this + 84) = v17;
  *((_DWORD *)this + 77) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_DWORD *)this + 80) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_DWORD *)this + 81) = a6;
  *((_DWORD *)this + 82) = 0;
  v18 = a7;
  *((_DWORD *)this + 83) = a7;
  *((_DWORD *)this + 88) = 0;
  if ( (*(_WORD *)&gDebugLevel & 0x100) != 0 && v15 && !v18 )
  {
    *((_DWORD *)this + 88) = 4;
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4u, 0xCAAu);
    *a9 = 1274;
    return this;
  }
  v19 = a8;
  if ( *((_DWORD *)a8 + 20) == 1 )
  {
    if ( v15 )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4u, 0xCA8u);
    }
    else if ( v17 )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4u, 0xCA9u);
    }
    else if ( *(_DWORD *)&gDebugLevel )
    {
      _DebugMsg(4u, 0xCABu);
    }
  }
  LastError = CRsopAppContext::MoveAppContextState((CRsopAppContext *)v10, v19);
  v21 = LastError;
  if ( LastError < 0 )
  {
    if ( (LastError & 0x1FFF0000) == 0x70000 )
    {
      LastError = (unsigned __int16)LastError;
    }
    else
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = v21;
    }
    goto LABEL_33;
  }
  if ( *((_DWORD *)this + 74)
    && *((_DWORD *)this + 99) != 1
    && !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, (PHANDLE)this + 33) )
  {
    LastError = GetLastError();
LABEL_33:
    *a9 = LastError;
    return this;
  }
  *((_QWORD *)this + 43) = *((_QWORD *)this + 33);
  v22 = a9;
  if ( *((_DWORD *)this + 99) == 1 )
  {
    *v14 = 0;
  }
  else
  {
    v23 = RegOpenKeyExW(hKey, 0, 0, 0x2001Fu, (PHKEY)this + 34);
    *v22 = v23;
    if ( v23 )
      return this;
    Key = RegCreateKeyExW(
            *((HKEY *)this + 34),
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy",
            0,
            0,
            0,
            0x2001Fu,
            0,
            (PHKEY)this + 35,
            0);
    *v22 = Key;
    if ( Key )
      return this;
    v25 = RegCreateKeyExW(*((HKEY *)this + 35), L"AppMgmt", 0, 0, 0, 0x2001Fu, 0, (PHKEY)this + 36, 0);
    *v22 = v25;
    if ( v25 )
      return this;
  }
  v26 = 0;
  if ( v18 )
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    Data = 0;
    LODWORD(cbData) = 4;
    v27 = (HKEY *)((char *)this + 288);
    if ( *((_DWORD *)this + 99) == 1 )
    {
      v28 = 1;
      Data = 1;
    }
    else
    {
      RegQueryValueExW(*v27, L"FullPolicy", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData);
      RegDeleteValueW(*v27, L"FullPolicy");
      v28 = Data;
      if ( *v14 )
        v26 = Data;
    }
    if ( v28 )
      *v14 = 0;
    *((_DWORD *)this + 80) = GetSystemDefaultLangID();
    GetSystemInfo(&SystemInfo);
    *((_DWORD *)this + 80) |= SystemInfo.wProcessorArchitecture << 16;
    if ( *((_DWORD *)this + 99) != 1 )
    {
      LODWORD(cbData) = 4;
      Value = RegQueryValueExW(*v27, L"LastArchLang", 0, 0, v33, (LPDWORD)&cbData);
      *v22 = Value;
      if ( !Value )
      {
        if ( *v14 )
        {
          if ( *((_DWORD *)this + 80) != *(_DWORD *)v33 )
          {
            v26 = 1;
            *v14 = 0;
            if ( *((_DWORD *)this + 76) )
            {
              if ( *(_DWORD *)&gDebugLevel )
                _DebugMsg(4u, 0xCAAu);
            }
          }
        }
      }
    }
  }
  if ( *((_DWORD *)this + 74) )
    v30 = (void *)*((_QWORD *)this + 33);
  else
    v30 = 0;
  ScriptDirPath = GetScriptDirPath(v30, 0, (unsigned __int16 **)this + 32, 0);
  *v22 = ScriptDirPath;
  if ( ScriptDirPath
    || *((_DWORD *)this + 99) != 1
    && ((ScriptDirPath = CManagedAppProcessor::CreateAndSecureScriptDir(this), (*v22 = ScriptDirPath) != 0)
     || *((_DWORD *)this + 99) != 1
     && (ScriptDirPath = CManagedAppProcessor::GetLocalScriptAppList(this, (CManagedAppProcessor *)((char *)this + 136)),
         (*v22 = ScriptDirPath) != 0)) )
  {
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(2u, 0xBCCu, ScriptDirPath);
  }
  else
  {
    if ( *v14 && (unsigned int)CManagedAppProcessor::DetectLostApps(this) )
    {
      v26 = 1;
      *v14 = 0;
    }
    CRsopAppContext::InitializeRsopContext(
      (CRsopAppContext *)v10,
      *((void **)this + 33),
      *((HKEY *)this + 36),
      v26,
      (int *)this + 75);
  }
  return this;
}

```

## disassembly

```asm
0x18000df00  mov     rax, rsp
0x18000df03  mov     [rax+20h], r9
0x18000df07  mov     [rax+18h], r8
0x18000df0b  mov     [rax+8], rcx
0x18000df0f  push    rbp
0x18000df10  push    rbx
0x18000df11  push    rsi
0x18000df12  push    rdi
0x18000df13  push    r12
0x18000df15  push    r13
0x18000df17  push    r14
0x18000df19  push    r15
0x18000df1b  lea     rbp, [rax-47h]
0x18000df1f  sub     rsp, 98h
0x18000df26  mov     rbx, rcx
0x18000df29  xor     r10d, r10d
0x18000df2c  mov     [rcx+10h], r10
0x18000df30  mov     [rcx+18h], r10
0x18000df34  mov     [rcx+8], rcx
0x18000df38  mov     [rcx], rcx
0x18000df3b  lea     rax, [rcx+50h]
0x18000df3f  mov     [rax+10h], r10
0x18000df43  mov     [rax+18h], r10
0x18000df47  mov     [rax+8], rax
0x18000df4b  mov     [rax], rax
0x18000df4e  mov     [rcx+28h], r10
0x18000df52  mov     [rcx+30h], r10
0x18000df56  mov     [rcx+38h], r10
0x18000df5a  mov     [rcx+40h], r10
0x18000df5e  mov     [rcx+48h], r10
0x18000df62  lea     r9, ??_7CAppList@@6B@; const CAppList::`vftable'
0x18000df69  mov     [rcx+20h], r9
0x18000df6d  mov     [rcx+70h], rcx
0x18000df71  lea     r15, [rcx+168h]
0x18000df78  mov     [rcx+78h], r15
0x18000df7c  mov     r8d, 80004005h
0x18000df82  mov     [rcx+80h], r8d
0x18000df89  mov     [rcx+84h], r10d
0x18000df90  add     rcx, 88h
0x18000df97  lea     rax, [rcx+30h]
0x18000df9b  mov     [rax+10h], r10
0x18000df9f  mov     [rax+18h], r10
0x18000dfa3  mov     [rax+8], rax
0x18000dfa7  mov     [rax], rax
0x18000dfaa  mov     [rcx+8], r10
0x18000dfae  mov     [rcx+10h], r10
0x18000dfb2  mov     [rcx+18h], r10
0x18000dfb6  mov     [rcx+20h], r10
0x18000dfba  mov     [rcx+28h], r10
0x18000dfbe  mov     [rcx], r9
0x18000dfc1  mov     [rcx+50h], rbx
0x18000dfc5  mov     [rcx+58h], r10
0x18000dfc9  mov     [rcx+60h], r8d
0x18000dfcd  mov     [rcx+64h], r10d
0x18000dfd1  mov     [rbx+0F0h], r10
0x18000dfd8  mov     rax, [rbp+3Fh+cbData]
0x18000dfdc  mov     [rbx+0F8h], rax
0x18000dfe3  mov     [rbx+158h], r10
0x18000dfea  mov     [r15], r10
0x18000dfed  mov     [r15+8], r10
0x18000dff1  mov     [r15+10h], r10
0x18000dff5  lea     rax, aC6dc5466785a11; "{c6dc5466-785a-11d2-84d0-00c04fb169f7}"
0x18000dffc  mov     [r15+18h], rax
0x18000e000  mov     [r15+20h], r10d
0x18000e004  mov     dword ptr [r15+24h], 2
0x18000e00c  mov     [r15+28h], r10
0x18000e010  mov     [r15+30h], r10
0x18000e014  mov     dword ptr [r15+38h], 8007000Eh
0x18000e01c  mov     [r15+40h], r10
0x18000e020  mov     [r15+48h], r10
0x18000e024  mov     [r15+50h], r10d
0x18000e028  lea     r9d, [r10+4]
0x18000e02c  mov     [r15+54h], r9d
0x18000e030  mov     [r15+58h], r10
0x18000e034  mov     [r15+60h], r10
0x18000e038  mov     [r15+68h], r10
0x18000e03c  mov     [r15+70h], r10d
0x18000e040  mov     [r15+78h], r10
0x18000e044  mov     [r15+80h], r10d
0x18000e04b  mov     dword ptr [rbp+3Fh+cbData], r10d
0x18000e04f  mov     dword ptr [rbp+3Fh+var_80], r10d
0x18000e053  mov     [rbp+3Fh+Data], r10d
0x18000e057  mov     eax, edx
0x18000e059  not     eax
0x18000e05b  lea     r8d, [r10+1]
0x18000e05f  and     eax, r8d
0x18000e062  mov     [rbx+128h], eax
0x18000e068  mov     r11d, 200h
0x18000e06e  test    dl, dl
0x18000e070  jns     short loc_18000E088
0x18000e072  test    byte ptr cs:?gDebugLevel@@3KA, 20h; ulong gDebugLevel
0x18000e079  jnz     short loc_18000E088
0x18000e07b  test    r11d, edx
0x18000e07e  jnz     short loc_18000E088
0x18000e080  mov     ecx, r8d
0x18000e083  mov     eax, r10d
0x18000e086  jmp     short loc_18000E090
0x18000e088  mov     ecx, r10d
0x18000e08b  mov     eax, edx
0x18000e08d  and     eax, r11d
0x18000e090  lea     rsi, [rbx+12Ch]
0x18000e097  mov     [rsi], ecx
0x18000e099  bt      edx, 0Ch
0x18000e09d  jnb     short loc_18000E0AF
0x18000e09f  test    byte ptr cs:?gDebugLevel@@3KA, 20h; ulong gDebugLevel
0x18000e0a6  jnz     short loc_18000E0AF
0x18000e0a8  test    eax, eax
0x18000e0aa  mov     ecx, r8d
0x18000e0ad  jz      short loc_18000E0B2
0x18000e0af  mov     ecx, r10d
0x18000e0b2  mov     [rbx+130h], ecx
0x18000e0b8  test    ecx, ecx
0x18000e0ba  jnz     short loc_18000E0C4
0x18000e0bc  test    dl, 10h
0x18000e0bf  mov     edx, r8d
0x18000e0c2  jnz     short loc_18000E0C7
0x18000e0c4  mov     edx, r10d
0x18000e0c7  mov     [rbx+150h], edx
0x18000e0cd  mov     [rbx+134h], r10d
0x18000e0d4  lea     r14, [rbx+110h]
0x18000e0db  mov     [r14], r10
0x18000e0de  lea     r13, [rbx+118h]
0x18000e0e5  mov     [r13+0], r10
0x18000e0e9  mov     [rbx+120h], r10
0x18000e0f0  mov     [rbx+108h], r10
0x18000e0f7  mov     [rbx+138h], r10
0x18000e0fe  mov     [rbx+140h], r10d
0x18000e105  mov     [rbx+100h], r10
0x18000e10c  mov     eax, [rbp+3Fh+arg_28]
0x18000e10f  mov     [rbx+144h], eax
0x18000e115  mov     [rbx+148h], r10d
0x18000e11c  mov     r12d, [rbp+3Fh+arg_30]
0x18000e120  mov     [rbx+14Ch], r12d
0x18000e127  mov     [rbx+160h], r10d
0x18000e12e  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18000e134  bt      eax, 8
0x18000e138  jnb     short loc_18000E172
0x18000e13a  test    ecx, ecx
0x18000e13c  jz      short loc_18000E172
0x18000e13e  test    r12d, r12d
0x18000e141  jnz     short loc_18000E172
0x18000e143  mov     [rbx+160h], r9d
0x18000e14a  cmp     cs:?gDebugLevel@@3KA, r10d; ulong gDebugLevel
0x18000e151  jz      short loc_18000E160
0x18000e153  mov     edx, 0CAAh; unsigned int
0x18000e158  mov     ecx, r9d; unsigned int
0x18000e15b  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000e160  mov     rax, [rbp+3Fh+arg_40]
0x18000e167  mov     dword ptr [rax], 4FAh
0x18000e16d  jmp     loc_18000E4D3
0x18000e172  mov     rdi, [rbp+3Fh+arg_38]
0x18000e179  cmp     [rdi+50h], r8d
0x18000e17d  jnz     short loc_18000E1AE
0x18000e17f  test    ecx, ecx
0x18000e181  jz      short loc_18000E18E
0x18000e183  test    eax, eax
0x18000e185  jz      short loc_18000E1AE
0x18000e187  mov     edx, 0CA8h
0x18000e18c  jmp     short loc_18000E1A6
0x18000e18e  test    edx, edx
0x18000e190  jz      short loc_18000E19D
0x18000e192  test    eax, eax
0x18000e194  jz      short loc_18000E1AE
0x18000e196  mov     edx, 0CA9h
0x18000e19b  jmp     short loc_18000E1A6
0x18000e19d  test    eax, eax
0x18000e19f  jz      short loc_18000E1AE
0x18000e1a1  mov     edx, 0CABh; unsigned int
0x18000e1a6  mov     ecx, r9d; unsigned int
0x18000e1a9  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000e1ae  mov     rdx, rdi; struct CRsopAppContext *
0x18000e1b1  mov     rcx, r15; this
0x18000e1b4  call    ?MoveAppContextState@CRsopAppContext@@QEAAJPEAV1@@Z; CRsopAppContext::MoveAppContextState(CRsopAppContext *)
0x18000e1b9  mov     edi, eax
0x18000e1bb  test    eax, eax
0x18000e1bd  jns     short loc_18000E1ED
0x18000e1bf  mov     ecx, eax
0x18000e1c1  and     ecx, 1FFF0000h
0x18000e1c7  cmp     ecx, 70000h
0x18000e1cd  jnz     short loc_18000E1D4
0x18000e1cf  movzx   eax, di
0x18000e1d2  jmp     short loc_18000E1DF
0x18000e1d4  call    cs:__imp_GetLastError
0x18000e1da  test    eax, eax
0x18000e1dc  cmovz   eax, edi
0x18000e1df  mov     rcx, [rbp+3Fh+arg_40]
0x18000e1e6  mov     [rcx], eax
0x18000e1e8  jmp     loc_18000E4D3
0x18000e1ed  lea     rdi, [rbx+108h]
0x18000e1f4  cmp     dword ptr [rbx+128h], 0
0x18000e1fb  jz      short loc_18000E224
0x18000e1fd  cmp     dword ptr [rbx+18Ch], 1
0x18000e204  jz      short loc_18000E224
0x18000e206  mov     r8, rdi; DuplicateTokenHandle
0x18000e209  mov     edx, 2; ImpersonationLevel
0x18000e20e  mov     rcx, [rbp+3Fh+ExistingTokenHandle]; ExistingTokenHandle
0x18000e212  call    cs:__imp_DuplicateToken
0x18000e218  test    eax, eax
0x18000e21a  jnz     short loc_18000E224
0x18000e21c  call    cs:__imp_GetLastError
0x18000e222  jmp     short loc_18000E1DF
0x18000e224  mov     rax, [rdi]
0x18000e227  mov     [rbx+158h], rax
0x18000e22e  mov     rdi, [rbp+3Fh+arg_40]
0x18000e235  cmp     dword ptr [rbx+18Ch], 1
0x18000e23c  jnz     short loc_18000E249
0x18000e23e  xor     r13d, r13d
0x18000e241  mov     [rsi], r13d
0x18000e244  jmp     loc_18000E2F2
0x18000e249  mov     [rsp+0D0h+phkResult], r14; phkResult
0x18000e24e  mov     r9d, 2001Fh; samDesired
0x18000e254  xor     r8d, r8d; ulOptions
0x18000e257  xor     edx, edx; lpSubKey
0x18000e259  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18000e25d  call    cs:__imp_RegOpenKeyExW
0x18000e263  mov     [rdi], eax
0x18000e265  xor     ecx, ecx
0x18000e267  test    eax, eax
0x18000e269  jnz     loc_18000E4D3
0x18000e26f  mov     [rsp+40h], rcx; lpdwDisposition
0x18000e274  mov     [rsp+0D0h+var_98], r13; phkResult
0x18000e279  mov     [rsp+0D0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x18000e27e  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18000e286  mov     dword ptr [rsp+0D0h+phkResult], ecx; dwOptions
0x18000e28a  xor     r9d, r9d; lpClass
0x18000e28d  xor     r8d, r8d; Reserved
0x18000e290  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e297  mov     rcx, [r14]; hKey
0x18000e29a  call    cs:__imp_RegCreateKeyExW
0x18000e2a0  mov     [rdi], eax
0x18000e2a2  xor     ecx, ecx
0x18000e2a4  test    eax, eax
0x18000e2a6  jnz     loc_18000E4D3
0x18000e2ac  mov     [rsp+40h], rcx; lpdwDisposition
0x18000e2b1  lea     rax, [rbx+120h]
0x18000e2b8  mov     [rsp+0D0h+var_98], rax; phkResult
0x18000e2bd  mov     [rsp+0D0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x18000e2c2  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18000e2ca  mov     dword ptr [rsp+0D0h+phkResult], ecx; dwOptions
0x18000e2ce  xor     r9d, r9d; lpClass
0x18000e2d1  xor     r8d, r8d; Reserved
0x18000e2d4  lea     rdx, aAppmgmt; "AppMgmt"
0x18000e2db  mov     rcx, [r13+0]; hKey
0x18000e2df  call    cs:__imp_RegCreateKeyExW
0x18000e2e5  mov     [rdi], eax
0x18000e2e7  xor     r13d, r13d
0x18000e2ea  test    eax, eax
0x18000e2ec  jnz     loc_18000E4D3
0x18000e2f2  mov     r14d, r13d
0x18000e2f5  test    r12d, r12d
0x18000e2f8  jz      loc_18000E41C
0x18000e2fe  xorps   xmm0, xmm0
0x18000e301  movups  xmmword ptr [rbp+3Fh+SystemInfo], xmm0
0x18000e305  movups  xmmword ptr [rbp+3Fh+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000e309  movups  xmmword ptr [rbp+3Fh+SystemInfo.dwNumberOfProcessors], xmm0
0x18000e30d  mov     [rbp+3Fh+Data], r13d
0x18000e311  mov     dword ptr [rbp+3Fh+cbData], 4
0x18000e318  lea     r12, [rbx+120h]
0x18000e31f  cmp     dword ptr [rbx+18Ch], 1
0x18000e326  jz      short loc_18000E36F
0x18000e328  lea     rax, [rbp+3Fh+cbData]
0x18000e32c  mov     qword ptr [rsp+0D0h+samDesired], rax; lpcbData
0x18000e331  lea     rax, [rbp+3Fh+Data]
0x18000e335  mov     [rsp+0D0h+phkResult], rax; lpData
0x18000e33a  xor     r9d, r9d; lpType
0x18000e33d  xor     r8d, r8d; lpReserved
0x18000e340  lea     rdx, ValueName; "FullPolicy"
0x18000e347  mov     rcx, [r12]; hKey
0x18000e34b  call    cs:__imp_RegQueryValueExW
0x18000e351  lea     rdx, ValueName; "FullPolicy"
0x18000e358  mov     rcx, [r12]; hKey
0x18000e35c  call    cs:__imp_RegDeleteValueW
0x18000e362  mov     eax, [rbp+3Fh+Data]
0x18000e365  cmp     [rsi], r13d
0x18000e368  jz      short loc_18000E377
0x18000e36a  mov     r14d, eax
0x18000e36d  jmp     short loc_18000E377
0x18000e36f  mov     eax, 1
0x18000e374  mov     [rbp+3Fh+Data], eax
0x18000e377  test    eax, eax
0x18000e379  jz      short loc_18000E37E
0x18000e37b  mov     [rsi], r13d
0x18000e37e  call    cs:__imp_GetSystemDefaultLangID
0x18000e384  movzx   eax, ax
0x18000e387  mov     [rbx+140h], eax
0x18000e38d  lea     rcx, [rbp+3Fh+SystemInfo]; lpSystemInfo
0x18000e391  call    cs:__imp_GetSystemInfo
0x18000e397  movzx   eax, word ptr [rbp+3Fh+SystemInfo]
0x18000e39b  shl     eax, 10h
0x18000e39e  or      [rbx+140h], eax
0x18000e3a4  cmp     dword ptr [rbx+18Ch], 1
0x18000e3ab  jz      short loc_18000E41C
0x18000e3ad  mov     dword ptr [rbp+3Fh+cbData], 4
0x18000e3b4  lea     rax, [rbp+3Fh+cbData]
0x18000e3b8  mov     qword ptr [rsp+0D0h+samDesired], rax; lpcbData
0x18000e3bd  lea     rax, [rbp+3Fh+var_80]
0x18000e3c1  mov     [rsp+0D0h+phkResult], rax; lpData
0x18000e3c6  xor     r9d, r9d; lpType
0x18000e3c9  xor     r8d, r8d; lpReserved
0x18000e3cc  lea     rdx, aLastarchlang; "LastArchLang"
  ... truncated ...
```
