# LocalVersionOK(HKEY__ *,CLocalComponentInfo *,_GUID *,ulong,ulong,int)

- ea: `0x180077584`
- end: `0x180077962`
- name: `?LocalVersionOK@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@PEAU_GUID@@KKH@Z`
- size: `990`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, struct CLocalComponentInfo *@<rdx>, struct _GUID *@<r8>, unsigned int@<r9d>, unsigned int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180076470`
- `0x180076ef0`

## callees

- `0x1800150e0`
- `0x180030880`
- `0x180072b54`
- `0x180077584`
- `0x180088be8`
- `0x18009b9dc`
- `0x1800c8e44`
- `0x1800c925c`
- `0x18010dc58`
- `0x18011ba26`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800777ba`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800777ba`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800777d7`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1800777d7`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180077796`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180077796`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800776d6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800776d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180077693`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180077693`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077930`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077734`

## pseudocode

```c
__int64 __fastcall LocalVersionOK(
        HKEY hKey,
        struct CLocalComponentInfo *a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  const struct _GUID *v7; // rsi
  signed int FileVersionFromCache; // ebx
  void *v11; // rcx
  unsigned int v12; // ebx
  char *v13; // rax
  signed int LastError; // eax
  const char *v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // ecx
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v20; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v23[2]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKeya; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v19 = 0;
  v7 = (const struct _GUID *)a3;
  v20 = 0;
  v22[0] = 0;
  v21[0] = 0;
  v23[0] = 0;
  hKeya = 0;
  if ( a3 )
    v7 = (const struct _GUID *)(-(__int64)(memcmp_0((const void *)a3, &GUID_NULL, 0x10u) != 0) & a3);
  FileVersionFromCache = 0;
  if ( *(_BYTE *)a2 )
  {
    v11 = (void *)*((_QWORD *)a2 + 34);
    v12 = *((_DWORD *)a2 + 66) - (_DWORD)a2;
    if ( v11 )
    {
      operator delete(v11);
      *((_QWORD *)a2 + 34) = 0;
    }
    v13 = (char *)operator new(v12 + 1);
    *((_QWORD *)a2 + 34) = v13;
    if ( !v13 )
    {
      FileVersionFromCache = -2147024882;
      goto LABEL_49;
    }
    FileVersionFromCache = StringCchCopyNA(v13, v12, (const char *)a2, v12 - 1);
  }
  if ( FileVersionFromCache >= 0
    && (a4 || a5 || hKey && !RegOpenKeyExA(hKey, "LanguageCheckPeriod", 0, 0x20019u, &hKeya)) )
  {
    WideCharStr[0] = 0;
    if ( !v7 )
      goto LABEL_22;
    if ( !*(_BYTE *)a2 )
      goto LABEL_34;
    if ( MultiByteToWideChar(0, 0, (LPCCH)a2, -1, WideCharStr, 260) )
    {
      FileVersionFromCache = Ext_GetFileVersionFromCache(v7, WideCharStr, &v19, &v20, v22, v21, v23);
      if ( FileVersionFromCache >= 0 )
      {
        *((_DWORD *)a2 + 76) = v23[0];
        goto LABEL_34;
      }
    }
    else
    {
      LastError = GetLastError();
      FileVersionFromCache = LastError;
      if ( LastError > 0 )
        FileVersionFromCache = (unsigned __int16)LastError | 0x80070000;
    }
    if ( FileVersionFromCache < 0 )
    {
LABEL_22:
      FileVersionFromCache = GetFileVersion(a2, &v19, &v20, v22, v21);
      if ( FileVersionFromCache >= 0 && v7 && WideCharStr[0] )
      {
        if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x759,
            (unsigned int)"onecoreuap\\inetcore\\urlmon\\download\\isctrl.cxx",
            v15);
        if ( IsProtectedModeProcess() )
        {
          Ext_SetFileVersionInCache(v7, WideCharStr, v19, v20, v22[0], v21[0], *((_DWORD *)a2 + 76));
        }
        else
        {
          *(_QWORD *)v21 = 0;
          *(_QWORD *)v22 = 0;
          FileVersionFromCache = CoCreateUserBroker((struct IEUserBroker **)v22);
          if ( FileVersionFromCache >= 0 )
          {
            *(_QWORD *)v23 = 0;
            FileVersionFromCache = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, unsigned int *))(**(_QWORD **)v22 + 48LL))(
                                     *(_QWORD *)v22,
                                     &CLSID_CShdocvwBroker,
                                     &IID_IUnknown,
                                     v23);
            if ( FileVersionFromCache >= 0 )
            {
              FileVersionFromCache = (***(__int64 (__fastcall ****)(_QWORD, GUID *, unsigned int *))v23)(
                                       *(_QWORD *)v23,
                                       &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                                       v21);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 16LL))(*(_QWORD *)v23);
            }
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v22 + 16LL))(*(_QWORD *)v22);
            if ( FileVersionFromCache >= 0 )
            {
              FileVersionFromCache = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, WCHAR *))(**(_QWORD **)v21 + 152LL))(
                                       *(_QWORD *)v21,
                                       v7,
                                       WideCharStr);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 16LL))(*(_QWORD *)v21);
            }
          }
        }
      }
    }
LABEL_34:
    if ( FileVersionFromCache )
      goto LABEL_39;
    v16 = v19;
    v17 = v20;
    *((_DWORD *)a2 + 70) = v19;
    *((_DWORD *)a2 + 71) = v17;
    if ( a6 )
    {
      if ( a4 != v16 || a5 != v17 )
      {
LABEL_38:
        FileVersionFromCache = 1;
        goto LABEL_39;
      }
    }
    else if ( a4 > v19 || a4 == v19 && a5 > v20 )
    {
      goto LABEL_38;
    }
    IsRightLanguageLocallyInstalled(a2);
LABEL_39:
    if ( a4 )
    {
      if ( a4 == -1 && a5 == -1 )
        FileVersionFromCache = 1;
    }
    else if ( !a5 )
    {
      FileVersionFromCache = 0;
    }
  }
LABEL_49:
  if ( hKeya )
    RegCloseKey(hKeya);
  return (unsigned int)FileVersionFromCache;
}

```

## disassembly

```asm
0x180077584  mov     [rsp-8+arg_18], rbx
0x180077589  push    rbp
0x18007758a  push    rsi
0x18007758b  push    rdi
0x18007758c  push    r12
0x18007758e  push    r13
0x180077590  push    r14
0x180077592  push    r15
0x180077594  lea     rbp, [rsp-190h]
0x18007759c  sub     rsp, 290h
0x1800775a3  mov     rax, cs:__security_cookie
0x1800775aa  xor     rax, rsp
0x1800775ad  mov     [rbp+1C0h+var_40], rax
0x1800775b4  xor     r13d, r13d
0x1800775b7  mov     r15d, r9d
0x1800775ba  mov     [rsp+2C0h+var_280], r13d
0x1800775bf  mov     rsi, r8
0x1800775c2  mov     [rsp+2C0h+var_27C], r13d
0x1800775c7  mov     rdi, rdx
0x1800775ca  mov     [rsp+2C0h+var_270], r13d
0x1800775cf  mov     r12, rcx
0x1800775d2  mov     [rsp+2C0h+var_278], r13d
0x1800775d7  mov     [rsp+2C0h+var_268], r13d
0x1800775dc  mov     [rsp+2C0h+hKey], r13
0x1800775e1  test    r8, r8
0x1800775e4  jz      short loc_180077601
0x1800775e6  lea     r8d, [r13+10h]; Size
0x1800775ea  mov     rcx, rsi; Buf1
0x1800775ed  lea     rdx, GUID_NULL; Buf2
0x1800775f4  call    memcmp_0
0x1800775f9  neg     eax
0x1800775fb  sbb     rcx, rcx
0x1800775fe  and     rsi, rcx
0x180077601  mov     ebx, r13d
0x180077604  cmp     [rdi], r13b
0x180077607  jz      short loc_180077654
0x180077609  mov     ebx, [rdi+108h]
0x18007760f  mov     rcx, [rdi+110h]; void *
0x180077616  sub     ebx, edi
0x180077618  test    rcx, rcx
0x18007761b  jz      short loc_180077629
0x18007761d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180077622  mov     [rdi+110h], r13
0x180077629  lea     ecx, [rbx+1]; Size
0x18007762c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077631  mov     [rdi+110h], rax
0x180077638  test    rax, rax
0x18007763b  jz      loc_18007772A
0x180077641  lea     r9d, [rbx-1]; unsigned __int64
0x180077645  mov     edx, ebx; unsigned __int64
0x180077647  mov     r8, rdi; char *
0x18007764a  mov     rcx, rax; char *
0x18007764d  call    ?StringCchCopyNA@@YAJPEAD_KPEBD1@Z; StringCchCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x180077652  mov     ebx, eax
0x180077654  test    ebx, ebx
0x180077656  js      loc_180077926
0x18007765c  mov     r14d, [rbp+1C0h+arg_20]
0x180077663  test    r15d, r15d
0x180077666  jnz     short loc_1800776A1
0x180077668  test    r14d, r14d
0x18007766b  jnz     short loc_1800776A1
0x18007766d  test    r12, r12
0x180077670  jz      loc_180077926
0x180077676  lea     rax, [rsp+2C0h+hKey]
0x18007767b  mov     r9d, 20019h; samDesired
0x180077681  xor     r8d, r8d; ulOptions
0x180077684  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180077689  lea     rdx, aLanguagecheckp; "LanguageCheckPeriod"
0x180077690  mov     rcx, r12; hKey
0x180077693  call    cs:__imp_RegOpenKeyExA
0x180077699  test    eax, eax
0x18007769b  jnz     loc_180077926
0x1800776a1  mov     [rsp+2C0h+WideCharStr], r13w
0x1800776a7  test    rsi, rsi
0x1800776aa  jz      loc_180077751
0x1800776b0  cmp     [rdi], r13b
0x1800776b3  jz      loc_1800778BC
0x1800776b9  lea     rax, [rsp+2C0h+WideCharStr]
0x1800776be  mov     [rsp+2C0h+cchWideChar], 104h; cchWideChar
0x1800776c6  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800776ca  mov     [rsp+2C0h+phkResult], rax; lpWideCharStr
0x1800776cf  mov     r8, rdi; lpMultiByteStr
0x1800776d2  xor     edx, edx; dwFlags
0x1800776d4  xor     ecx, ecx; CodePage
0x1800776d6  call    cs:__imp_MultiByteToWideChar
0x1800776dc  test    eax, eax
0x1800776de  jz      short loc_180077734
0x1800776e0  lea     rax, [rsp+2C0h+var_268]
0x1800776e5  mov     rcx, rsi; struct _GUID *
0x1800776e8  mov     [rsp+2C0h+var_290], rax; unsigned int *
0x1800776ed  lea     r9, [rsp+2C0h+var_27C]; unsigned int *
0x1800776f2  lea     rax, [rsp+2C0h+var_278]
0x1800776f7  mov     qword ptr [rsp+2C0h+cchWideChar], rax; unsigned int *
0x1800776fc  lea     r8, [rsp+2C0h+var_280]; unsigned int *
0x180077701  lea     rax, [rsp+2C0h+var_270]
0x180077706  lea     rdx, [rsp+2C0h+WideCharStr]; unsigned __int16 *
0x18007770b  mov     [rsp+2C0h+phkResult], rax; unsigned int *
0x180077710  call    ?Ext_GetFileVersionFromCache@@YAJAEBU_GUID@@PEBGPEAK2222@Z; Ext_GetFileVersionFromCache(_GUID const &,ushort const *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x180077715  mov     ebx, eax
0x180077717  test    eax, eax
0x180077719  js      short loc_180077749
0x18007771b  mov     ecx, [rsp+2C0h+var_268]
0x18007771f  mov     [rdi+130h], ecx
0x180077725  jmp     loc_1800778BC
0x18007772a  mov     ebx, 8007000Eh
0x18007772f  jmp     loc_180077926
0x180077734  call    cs:__imp_GetLastError
0x18007773a  mov     ebx, eax
0x18007773c  test    eax, eax
0x18007773e  jle     short loc_180077749
0x180077740  movzx   ebx, ax
0x180077743  or      ebx, 80070000h
0x180077749  test    ebx, ebx
0x18007774b  jns     loc_1800778BC
0x180077751  lea     rax, [rsp+2C0h+var_278]
0x180077756  mov     rcx, rdi; struct CLocalComponentInfo *
0x180077759  lea     r9, [rsp+2C0h+var_270]; unsigned int *
0x18007775e  mov     [rsp+2C0h+phkResult], rax; unsigned int *
0x180077763  lea     r8, [rsp+2C0h+var_27C]; unsigned int *
0x180077768  lea     rdx, [rsp+2C0h+var_280]; unsigned int *
0x18007776d  call    ?GetFileVersion@@YAJPEAVCLocalComponentInfo@@PEAK111@Z; GetFileVersion(CLocalComponentInfo *,ulong *,ulong *,ulong *,ulong *)
0x180077772  mov     ebx, eax
0x180077774  test    eax, eax
0x180077776  js      loc_1800778BC
0x18007777c  test    rsi, rsi
0x18007777f  jz      loc_1800778BC
0x180077785  cmp     [rsp+2C0h+WideCharStr], r13w
0x18007778b  jz      loc_1800778BC
0x180077791  mov     ecx, 1000002Dh
0x180077796  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18007779c  cmp     eax, 2
0x18007779f  jnz     short loc_1800777BA
0x1800777a1  mov     rcx, [rbp+1C8h]; this
0x1800777a8  lea     r8, aOnecoreuapInet_21; "onecoreuap\\inetcore\\urlmon\\download"...
0x1800777af  mov     edx, 759h; void *
0x1800777b4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800777ba  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1800777c0  test    eax, eax
0x1800777c2  jnz     loc_18007788B
0x1800777c8  lea     rcx, [rsp+2C0h+var_270]
0x1800777cd  mov     qword ptr [rsp+2C0h+var_278], r13
0x1800777d2  mov     qword ptr [rsp+2C0h+var_270], r13
0x1800777d7  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1800777dd  mov     ebx, eax
0x1800777df  test    eax, eax
0x1800777e1  js      loc_1800778BC
0x1800777e7  mov     rcx, qword ptr [rsp+2C0h+var_270]
0x1800777ec  lea     r9, [rsp+2C0h+var_268]
0x1800777f1  mov     qword ptr [rsp+2C0h+var_268], r13
0x1800777f6  lea     r8, IID_IUnknown
0x1800777fd  lea     rdx, CLSID_CShdocvwBroker
0x180077804  mov     rax, [rcx]
0x180077807  mov     rax, [rax+30h]
0x18007780b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077810  mov     ebx, eax
0x180077812  test    eax, eax
0x180077814  js      short loc_180077845
0x180077816  mov     rcx, qword ptr [rsp+2C0h+var_268]
0x18007781b  lea     r8, [rsp+2C0h+var_278]
0x180077820  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180077827  mov     rax, [rcx]
0x18007782a  mov     rax, [rax]
0x18007782d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077832  mov     rcx, qword ptr [rsp+2C0h+var_268]
0x180077837  mov     ebx, eax
0x180077839  mov     rax, [rcx]
0x18007783c  mov     rax, [rax+10h]
0x180077840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077845  mov     rcx, qword ptr [rsp+2C0h+var_270]
0x18007784a  mov     rax, [rcx]
0x18007784d  mov     rax, [rax+10h]
0x180077851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077856  test    ebx, ebx
0x180077858  js      short loc_1800778BC
0x18007785a  mov     rcx, qword ptr [rsp+2C0h+var_278]
0x18007785f  lea     r8, [rsp+2C0h+WideCharStr]
0x180077864  mov     rdx, rsi
0x180077867  mov     rax, [rcx]
0x18007786a  mov     rax, [rax+98h]
0x180077871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077876  mov     rcx, qword ptr [rsp+2C0h+var_278]
0x18007787b  mov     ebx, eax
0x18007787d  mov     rax, [rcx]
0x180077880  mov     rax, [rax+10h]
0x180077884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077889  jmp     short loc_1800778BC
0x18007788b  mov     eax, [rdi+130h]
0x180077891  lea     rdx, [rsp+2C0h+WideCharStr]; unsigned __int16 *
0x180077896  mov     r9d, [rsp+2C0h+var_27C]; unsigned int
0x18007789b  mov     rcx, rsi; struct _GUID *
0x18007789e  mov     r8d, [rsp+2C0h+var_280]; unsigned int
0x1800778a3  mov     dword ptr [rsp+2C0h+var_290], eax; unsigned int
0x1800778a7  mov     eax, [rsp+2C0h+var_278]
0x1800778ab  mov     [rsp+2C0h+cchWideChar], eax; unsigned int
0x1800778af  mov     eax, [rsp+2C0h+var_270]
0x1800778b3  mov     dword ptr [rsp+2C0h+phkResult], eax; unsigned int
0x1800778b7  call    ?Ext_SetFileVersionInCache@@YAJAEBU_GUID@@PEBGKKKKK@Z; Ext_SetFileVersionInCache(_GUID const &,ushort const *,ulong,ulong,ulong,ulong,ulong)
0x1800778bc  mov     esi, 1
0x1800778c1  test    ebx, ebx
0x1800778c3  jnz     short loc_1800778EE
0x1800778c5  mov     eax, [rsp+2C0h+var_280]
0x1800778c9  mov     ecx, [rsp+2C0h+var_27C]
0x1800778cd  mov     [rdi+118h], eax
0x1800778d3  mov     [rdi+11Ch], ecx
0x1800778d9  cmp     [rbp+1C0h+arg_28], r13d
0x1800778e0  jz      short loc_1800778FD
0x1800778e2  cmp     r15d, eax
0x1800778e5  jnz     short loc_1800778EC
0x1800778e7  cmp     r14d, ecx
0x1800778ea  jz      short loc_18007790D
0x1800778ec  mov     ebx, esi
0x1800778ee  test    r15d, r15d
0x1800778f1  jnz     short loc_180077917
0x1800778f3  test    r14d, r14d
0x1800778f6  jnz     short loc_180077926
0x1800778f8  mov     ebx, r13d
0x1800778fb  jmp     short loc_180077926
0x1800778fd  cmp     r15d, [rsp+2C0h+var_280]
0x180077902  ja      short loc_1800778EC
0x180077904  jnz     short loc_18007790D
0x180077906  cmp     r14d, [rsp+2C0h+var_27C]
0x18007790b  ja      short loc_1800778EC
0x18007790d  mov     rcx, rdi; struct CLocalComponentInfo *
0x180077910  call    ?IsRightLanguageLocallyInstalled@@YAJPEAVCLocalComponentInfo@@@Z; IsRightLanguageLocallyInstalled(CLocalComponentInfo *)
0x180077915  jmp     short loc_1800778EE
0x180077917  or      eax, 0FFFFFFFFh
0x18007791a  cmp     r15d, eax
0x18007791d  jnz     short loc_180077926
0x18007791f  cmp     r14d, eax
0x180077922  jnz     short loc_180077926
0x180077924  mov     ebx, esi
0x180077926  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18007792b  test    rcx, rcx
0x18007792e  jz      short loc_180077936
0x180077930  call    cs:__imp_RegCloseKey
0x180077936  mov     eax, ebx
0x180077938  mov     rcx, [rbp+1C0h+var_40]
0x18007793f  xor     rcx, rsp; StackCookie
0x180077942  call    __security_check_cookie
0x180077947  mov     rbx, [rsp+2C0h+arg_18]
0x18007794f  add     rsp, 290h
0x180077956  pop     r15
0x180077958  pop     r14
0x18007795a  pop     r13
0x18007795c  pop     r12
0x18007795e  pop     rdi
0x18007795f  pop     rsi
0x180077960  pop     rbp
0x180077961  retn
```
