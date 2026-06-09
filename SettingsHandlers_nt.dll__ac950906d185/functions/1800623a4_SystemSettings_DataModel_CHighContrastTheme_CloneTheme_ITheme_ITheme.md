# SystemSettings::DataModel::CHighContrastTheme::CloneTheme(ITheme *,ITheme * *)

- ea: `0x1800623a4`
- end: `0x1800627f4`
- name: `?CloneTheme@CHighContrastTheme@DataModel@SystemSettings@@QEAAJPEAUITheme@@PEAPEAU4@@Z`
- size: `1104`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CHighContrastTheme *__hidden this, struct ITheme *, struct ITheme **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180063f90`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x180011bb0`
- `0x180013d14`
- `0x180013d4c`
- `0x1800167a8`
- `0x1800167dc`
- `0x18001a64c`
- `0x18004e5f0`
- `0x1800623a4`
- `0x180065a5c`
- `0x1800660b8`
- `0x180066350`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062775`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062775`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180062619`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180062619`
- `OLEAUT32!__imp_SysAllocString` at `0x1800625d3`
- `OLEAUT32!__imp_SysAllocString` at `0x180062679`
- `OLEAUT32!__imp_SysAllocString` at `0x1800625d3`
- `OLEAUT32!__imp_SysAllocString` at `0x180062679`
- `OLEAUT32!__imp_SysFreeString` at `0x1800625ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800626a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800626bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800625ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800626a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800626bc`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18006259e`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18006259e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180062553`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180062553`
- `SHELL32!__imp_SHCreateDirectory` at `0x1800624ec`
- `SHELL32!__imp_SHCreateDirectory` at `0x1800624ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::DataModel::CHighContrastTheme::CloneTheme(
        SystemSettings::DataModel::CHighContrastTheme *this,
        struct ITheme *a2,
        struct ITheme **a3)
{
  signed int CustomThemePath; // edi
  char *v7; // r14
  OLECHAR *v8; // r12
  SystemSettings::DataModel::CHighContrastHelper *v9; // rcx
  __int64 (__fastcall *v10)(struct ITheme *, struct ITheme **); // rbx
  SystemSettings::DataModel::CHighContrastTheme *v11; // rcx
  unsigned __int64 v12; // r8
  int v13; // eax
  int v14; // ebx
  OLECHAR *v15; // rsi
  OLECHAR *v16; // rbx
  __int64 v17; // rsi
  int v18; // ebx
  unsigned int v19; // r15d
  struct ITheme *v20; // rax
  __int64 i; // rbx
  __int64 v23; // [rsp+28h] [rbp-D8h]
  struct ITheme *v24; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+38h] [rbp-C8h] BYREF
  char v26[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct ITheme **v27; // [rsp+48h] [rbp-B8h]
  OLECHAR *v28; // [rsp+50h] [rbp-B0h]
  GUID pguid; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR NewFileName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+280h] [rbp+180h] BYREF

  v27 = a3;
  CustomThemePath = -2147467259;
  v7 = (char *)this + 352;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(v26, (char *)this + 352);
  v8 = (OLECHAR *)*((_QWORD *)this + 34);
  v28 = v8;
  *((_QWORD *)this + 34) = 0;
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v26);
  *a3 = 0;
  if ( SystemSettings::DataModel::CHighContrastTheme::_IsModified(this)
    && !(unsigned int)SystemSettings::DataModel::CHighContrastHelper::ValidateThemeName(v9, v8) )
  {
    v24 = 0;
    v10 = *(__int64 (__fastcall **)(struct ITheme *, struct ITheme **))(*(_QWORD *)a2 + 584LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    CustomThemePath = v10(a2, &v24);
    if ( CustomThemePath >= 0 )
    {
      memset_0(NewFileName, 0, 0x208u);
      lpExistingFileName = 0;
      CustomThemePath = (*(__int64 (__fastcall **)(struct ITheme *, __int64, LPCWSTR *))(*(_QWORD *)a2 + 288LL))(
                          a2,
                          0xFFFFFFFFLL,
                          &lpExistingFileName);
      if ( CustomThemePath >= 0 )
      {
        memset_0(pszPath, 0, 0x208u);
        CustomThemePath = SystemSettings::DataModel::CHighContrastTheme::_GetCustomThemePath(v11, pszPath, v12);
        if ( CustomThemePath >= 0 )
        {
          v13 = SHCreateDirectory(0, pszPath);
          CustomThemePath = v13;
          if ( v13 > 0 )
            CustomThemePath = (unsigned __int16)v13 | 0x80070000;
          if ( (int)(CustomThemePath + 0x80000000) < 0 || CustomThemePath == -2147024713 )
          {
            CustomThemePath = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s.theme", pszPath, v8);
            if ( CustomThemePath >= 0 )
            {
              v14 = 2;
              while ( PathFileExistsW(NewFileName) )
              {
                LODWORD(v23) = v14;
                CustomThemePath = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s (%d).theme", pszPath, v8, v23);
                ++v14;
                if ( CustomThemePath < 0 )
                  goto LABEL_17;
              }
              if ( !CopyFileW(lpExistingFileName, NewFileName, 0) )
                CustomThemePath = ResultFromKnownLastError();
            }
          }
        }
LABEL_17:
        SysFreeString((BSTR)lpExistingFileName);
        if ( CustomThemePath >= 0 )
        {
          v15 = SysAllocString(NewFileName);
          if ( v15 )
          {
            CustomThemePath = (*(__int64 (__fastcall **)(struct ITheme *, OLECHAR *))(*(_QWORD *)v24 + 296LL))(v24, v15);
            if ( CustomThemePath >= 0 )
            {
              pguid = 0;
              if ( CoCreateGuid(&pguid) >= 0 )
                (*(void (__fastcall **)(struct ITheme *, GUID *))(*(_QWORD *)v24 + 128LL))(v24, &pguid);
              CustomThemePath = (*(__int64 (__fastcall **)(struct ITheme *))(*(_QWORD *)v24 + 408LL))(v24);
              if ( CustomThemePath >= 0 )
              {
                CustomThemePath = (*(__int64 (__fastcall **)(struct ITheme *))(*(_QWORD *)v24 + 552LL))(v24);
                if ( CustomThemePath >= 0 )
                {
                  v16 = SysAllocString(v8);
                  if ( v16 )
                  {
                    CustomThemePath = (*(__int64 (__fastcall **)(struct ITheme *, OLECHAR *))(*(_QWORD *)v24 + 32LL))(
                                        v24,
                                        v16);
                    SysFreeString(v16);
                  }
                  else
                  {
                    CustomThemePath = -2147024882;
                  }
                }
              }
            }
            SysFreeString(v15);
            v17 = 0;
            if ( CustomThemePath >= 0 )
            {
              while ( (unsigned int)v17 < 8 )
              {
                Microsoft::WRL::Wrappers::SRWLock::LockShared(&pguid, (char *)this + 352);
                v18 = *((_DWORD *)this + 2 * v17 + 71);
                v19 = *((_DWORD *)this + 2 * v17 + 70);
                Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&pguid);
                if ( v18 != v19 )
                  (*(void (__fastcall **)(struct ITheme *, wchar_t *, _QWORD))(*(_QWORD *)v24 + 592LL))(
                    v24,
                    (&off_1802BC310)[2 * (unsigned int)v17],
                    v19);
                Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&pguid);
                v17 = (unsigned int)(v17 + 1);
              }
              v20 = v24;
              v24 = 0;
              *v27 = v20;
              v8 = v28;
              v7 = (char *)this + 352;
            }
          }
          else
          {
            CustomThemePath = -2147024882;
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  }
  CoTaskMemFree(v8);
  for ( i = 0; i != 8; ++i )
  {
    wil::AcquireSRWLockExclusive(&pguid, v7);
    *((_DWORD *)this + 2 * i + 70) = *((_DWORD *)this + 2 * i + 71);
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&pguid);
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&pguid);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v26);
  return (unsigned int)CustomThemePath;
}

```

## disassembly

```asm
0x1800623a4  mov     [rsp-8+arg_18], rbx
0x1800623a9  push    rbp
0x1800623aa  push    rsi
0x1800623ab  push    rdi
0x1800623ac  push    r12
0x1800623ae  push    r13
0x1800623b0  push    r14
0x1800623b2  push    r15
0x1800623b4  lea     rbp, [rsp-3A0h]
0x1800623bc  sub     rsp, 4A0h
0x1800623c3  mov     rax, cs:__security_cookie
0x1800623ca  xor     rax, rsp
0x1800623cd  mov     [rbp+3D0h+var_40], rax
0x1800623d4  mov     r15, r8
0x1800623d7  mov     [rsp+4D0h+var_488], r8
0x1800623dc  mov     rsi, rdx
0x1800623df  mov     r13, rcx
0x1800623e2  mov     edi, 80004005h
0x1800623e7  lea     r14, [rcx+160h]
0x1800623ee  mov     rdx, r14
0x1800623f1  lea     rcx, [rsp+4D0h+var_490]
0x1800623f6  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800623fb  nop
0x1800623fc  mov     r12, [r13+110h]
0x180062403  mov     [rsp+4D0h+var_480], r12
0x180062408  mov     qword ptr [r13+110h], 0
0x180062413  lea     rcx, [rsp+4D0h+var_490]; this
0x180062418  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x18006241d  mov     qword ptr [r15], 0
0x180062424  mov     rcx, r13; this
0x180062427  call    ?_IsModified@CHighContrastTheme@DataModel@SystemSettings@@AEAA_NXZ; SystemSettings::DataModel::CHighContrastTheme::_IsModified(void)
0x18006242c  test    al, al
0x18006242e  jz      loc_180062772
0x180062434  mov     rdx, r12; unsigned __int16 *
0x180062437  call    ?ValidateThemeName@CHighContrastHelper@DataModel@SystemSettings@@QEAAJPEBG@Z; SystemSettings::DataModel::CHighContrastHelper::ValidateThemeName(ushort const *)
0x18006243c  test    eax, eax
0x18006243e  jnz     loc_180062772
0x180062444  mov     [rsp+4D0h+var_4A0], 0
0x18006244d  mov     rax, [rsi]
0x180062450  mov     rbx, [rax+248h]
0x180062457  lea     rcx, [rsp+4D0h+var_4A0]
0x18006245c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062461  lea     rdx, [rsp+4D0h+var_4A0]
0x180062466  mov     rcx, rsi
0x180062469  mov     rax, rbx
0x18006246c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062471  mov     edi, eax
0x180062473  test    eax, eax
0x180062475  js      loc_180062768
0x18006247b  mov     ebx, 208h
0x180062480  mov     r8d, ebx; Size
0x180062483  xor     edx, edx; Val
0x180062485  lea     rcx, [rsp+4D0h+NewFileName]; void *
0x18006248a  call    memset_0
0x18006248f  mov     [rsp+4D0h+lpExistingFileName], 0
0x180062498  mov     rax, [rsi]
0x18006249b  or      edx, 0FFFFFFFFh
0x18006249e  lea     r8, [rsp+4D0h+lpExistingFileName]
0x1800624a3  mov     rcx, rsi
0x1800624a6  mov     rax, [rax+120h]
0x1800624ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624b2  mov     edi, eax
0x1800624b4  test    eax, eax
0x1800624b6  js      loc_180062768
0x1800624bc  mov     r8d, ebx; Size
0x1800624bf  xor     edx, edx; Val
0x1800624c1  lea     rcx, [rbp+3D0h+pszPath]; void *
0x1800624c8  call    memset_0
0x1800624cd  lea     rdx, [rbp+3D0h+pszPath]; unsigned __int16 *
0x1800624d4  call    ?_GetCustomThemePath@CHighContrastTheme@DataModel@SystemSettings@@AEAAJPEAG_K@Z; SystemSettings::DataModel::CHighContrastTheme::_GetCustomThemePath(ushort *,unsigned __int64)
0x1800624d9  mov     edi, eax
0x1800624db  test    eax, eax
0x1800624dd  js      loc_1800625B5
0x1800624e3  lea     rdx, [rbp+3D0h+pszPath]; pszPath
0x1800624ea  xor     ecx, ecx; hwnd
0x1800624ec  call    cs:__imp_SHCreateDirectory
0x1800624f3  nop     dword ptr [rax+rax+00h]
0x1800624f8  mov     edi, eax
0x1800624fa  test    eax, eax
0x1800624fc  jle     short loc_180062507
0x1800624fe  movzx   edi, ax
0x180062501  or      edi, 80070000h
0x180062507  mov     ecx, 80000000h
0x18006250c  lea     eax, [rdi+rcx]
0x18006250f  test    ecx, eax
0x180062511  jnz     short loc_18006251F
0x180062513  cmp     edi, 800700B7h
0x180062519  jnz     loc_1800625B5
0x18006251f  mov     [rsp+4D0h+var_4B0], r12
0x180062524  lea     r9, [rbp+3D0h+pszPath]
0x18006252b  lea     r8, aSSTheme; "%s\\%s.theme"
0x180062532  mov     esi, 104h
0x180062537  mov     edx, esi; unsigned __int64
0x180062539  lea     rcx, [rsp+4D0h+NewFileName]; unsigned __int16 *
0x18006253e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180062543  mov     edi, eax
0x180062545  test    eax, eax
0x180062547  js      short loc_1800625B5
0x180062549  mov     ebx, 2
0x18006254e  lea     rcx, [rsp+4D0h+NewFileName]; pszPath
0x180062553  call    cs:__imp_PathFileExistsW
0x18006255a  nop     dword ptr [rax+rax+00h]
0x18006255f  test    eax, eax
0x180062561  jz      short loc_180062591
0x180062563  mov     dword ptr [rsp+4D0h+var_4A8], ebx
0x180062567  mov     [rsp+4D0h+var_4B0], r12
0x18006256c  lea     r9, [rbp+3D0h+pszPath]
0x180062573  lea     r8, aSSDTheme; "%s\\%s (%d).theme"
0x18006257a  mov     rdx, rsi; unsigned __int64
0x18006257d  lea     rcx, [rsp+4D0h+NewFileName]; unsigned __int16 *
0x180062582  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180062587  mov     edi, eax
0x180062589  inc     ebx
0x18006258b  test    eax, eax
0x18006258d  jns     short loc_18006254E
0x18006258f  jmp     short loc_1800625B5
0x180062591  xor     r8d, r8d; bFailIfExists
0x180062594  lea     rdx, [rsp+4D0h+NewFileName]; lpNewFileName
0x180062599  mov     rcx, [rsp+4D0h+lpExistingFileName]; lpExistingFileName
0x18006259e  call    cs:__imp_CopyFileW
0x1800625a5  nop     dword ptr [rax+rax+00h]
0x1800625aa  test    eax, eax
0x1800625ac  jnz     short loc_1800625B5
0x1800625ae  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800625b3  mov     edi, eax
0x1800625b5  mov     rcx, [rsp+4D0h+lpExistingFileName]; bstrString
0x1800625ba  call    cs:__imp_SysFreeString
0x1800625c1  nop     dword ptr [rax+rax+00h]
0x1800625c6  test    edi, edi
0x1800625c8  js      loc_180062768
0x1800625ce  lea     rcx, [rsp+4D0h+NewFileName]; psz
0x1800625d3  call    cs:__imp_SysAllocString
0x1800625da  nop     dword ptr [rax+rax+00h]
0x1800625df  mov     rsi, rax
0x1800625e2  test    rax, rax
0x1800625e5  jz      loc_180062763
0x1800625eb  mov     rcx, [rsp+4D0h+var_4A0]
0x1800625f0  mov     rdx, [rcx]
0x1800625f3  mov     rax, [rdx+128h]
0x1800625fa  mov     rdx, rsi
0x1800625fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062602  mov     edi, eax
0x180062604  test    eax, eax
0x180062606  js      loc_1800626B9
0x18006260c  xorps   xmm0, xmm0
0x18006260f  movups  xmmword ptr [rsp+4D0h+pguid.Data1], xmm0
0x180062614  lea     rcx, [rsp+4D0h+pguid]; pguid
0x180062619  call    cs:__imp_CoCreateGuid
0x180062620  nop     dword ptr [rax+rax+00h]
0x180062625  test    eax, eax
0x180062627  js      short loc_180062642
0x180062629  mov     rcx, [rsp+4D0h+var_4A0]
0x18006262e  mov     rax, [rcx]
0x180062631  lea     rdx, [rsp+4D0h+pguid]
0x180062636  mov     rax, [rax+80h]
0x18006263d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062642  mov     rcx, [rsp+4D0h+var_4A0]
0x180062647  mov     rax, [rcx]
0x18006264a  mov     rax, [rax+198h]
0x180062651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062656  mov     edi, eax
0x180062658  test    eax, eax
0x18006265a  js      short loc_1800626B9
0x18006265c  mov     rcx, [rsp+4D0h+var_4A0]
0x180062661  mov     rax, [rcx]
0x180062664  mov     rax, [rax+228h]
0x18006266b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062670  mov     edi, eax
0x180062672  test    eax, eax
0x180062674  js      short loc_1800626B9
0x180062676  mov     rcx, r12; psz
0x180062679  call    cs:__imp_SysAllocString
0x180062680  nop     dword ptr [rax+rax+00h]
0x180062685  mov     rbx, rax
0x180062688  test    rax, rax
0x18006268b  jz      short loc_1800626B4
0x18006268d  mov     rcx, [rsp+4D0h+var_4A0]
0x180062692  mov     rdx, [rcx]
0x180062695  mov     rax, [rdx+20h]
0x180062699  mov     rdx, rbx
0x18006269c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626a1  mov     edi, eax
0x1800626a3  mov     rcx, rbx; bstrString
0x1800626a6  call    cs:__imp_SysFreeString
0x1800626ad  nop     dword ptr [rax+rax+00h]
0x1800626b2  jmp     short loc_1800626B9
0x1800626b4  mov     edi, 8007000Eh
0x1800626b9  mov     rcx, rsi; bstrString
0x1800626bc  call    cs:__imp_SysFreeString
0x1800626c3  nop     dword ptr [rax+rax+00h]
0x1800626c8  xor     esi, esi
0x1800626ca  test    edi, edi
0x1800626cc  js      loc_180062768
0x1800626d2  cmp     esi, 8
0x1800626d5  jnb     short loc_18006273F
0x1800626d7  lea     rdx, [r13+160h]
0x1800626de  lea     rcx, [rsp+4D0h+pguid]
0x1800626e3  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800626e8  nop
0x1800626e9  mov     r14d, esi
0x1800626ec  mov     ebx, [r13+rsi*8+11Ch]
0x1800626f4  mov     r15d, [r13+rsi*8+118h]
0x1800626fc  lea     rcx, [rsp+4D0h+pguid]; this
0x180062701  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x180062706  cmp     ebx, r15d
0x180062709  jz      short loc_180062731
0x18006270b  mov     rcx, [rsp+4D0h+var_4A0]
0x180062710  mov     rax, [rcx]
0x180062713  add     r14, r14
0x180062716  lea     rdx, off_1802BC310; "Window"
0x18006271d  mov     r8d, r15d
0x180062720  mov     rdx, [rdx+r14*8]
0x180062724  mov     rax, [rax+250h]
0x18006272b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062730  nop
0x180062731  lea     rcx, [rsp+4D0h+pguid]; this
0x180062736  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x18006273b  inc     esi
0x18006273d  jmp     short loc_1800626D2
0x18006273f  mov     rax, [rsp+4D0h+var_4A0]
0x180062744  mov     [rsp+4D0h+var_4A0], 0
0x18006274d  mov     rcx, [rsp+4D0h+var_488]
0x180062752  mov     [rcx], rax
0x180062755  mov     r12, [rsp+4D0h+var_480]
0x18006275a  lea     r14, [r13+160h]
0x180062761  jmp     short loc_180062768
0x180062763  mov     edi, 8007000Eh
0x180062768  lea     rcx, [rsp+4D0h+var_4A0]
0x18006276d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062772  mov     rcx, r12; pv
0x180062775  call    cs:__imp_CoTaskMemFree
0x18006277c  nop     dword ptr [rax+rax+00h]
0x180062781  xor     ebx, ebx
0x180062783  mov     rdx, r14
0x180062786  lea     rcx, [rsp+4D0h+pguid]
0x18006278b  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180062790  mov     eax, [r13+rbx*8+11Ch]
0x180062798  mov     [r13+rbx*8+118h], eax
0x1800627a0  lea     rcx, [rsp+4D0h+pguid]; this
0x1800627a5  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800627aa  lea     rcx, [rsp+4D0h+pguid]; this
0x1800627af  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800627b4  inc     rbx
0x1800627b7  cmp     rbx, 8
0x1800627bb  jnz     short loc_180062783
0x1800627bd  lea     rcx, [rsp+4D0h+var_490]; this
0x1800627c2  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800627c7  mov     eax, edi
0x1800627c9  mov     rcx, [rbp+3D0h+var_40]
0x1800627d0  xor     rcx, rsp; StackCookie
0x1800627d3  call    __security_check_cookie
0x1800627d8  mov     rbx, [rsp+4D0h+arg_18]
0x1800627e0  add     rsp, 4A0h
0x1800627e7  pop     r15
0x1800627e9  pop     r14
0x1800627eb  pop     r13
0x1800627ed  pop     r12
0x1800627ef  pop     rdi
0x1800627f0  pop     rsi
0x1800627f1  pop     rbp
0x1800627f2  retn
```
