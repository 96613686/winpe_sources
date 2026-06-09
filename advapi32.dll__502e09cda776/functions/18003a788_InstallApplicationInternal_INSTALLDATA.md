# InstallApplicationInternal(_INSTALLDATA *)

- ea: `0x18003a788`
- end: `0x18003b01e`
- name: `?InstallApplicationInternal@@YAKPEAU_INSTALLDATA@@@Z`
- size: `2198`
- prototype: `DWORD __fastcall(struct _INSTALLDATA *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800487c0`

## callees

- `0x180032eb8`
- `0x180033064`
- `0x18003a788`
- `0x18003b024`
- `0x18003e0e4`
- `0x1800482ec`
- `0x180048388`
- `0x180048824`
- `0x180048a08`
- `0x180049e60`
- `0x18004a1a8`
- `0x18004a1e4`
- `0x18004a220`
- `0x18004a610`
- `0x18007205a`
- `0x1800720b0`
- `0x180074010`

## import_xrefs

- `msvcrt!wcschr` at `0x18003ad76`
- `msvcrt!wcschr` at `0x18003ad9d`
- `msvcrt!wcschr` at `0x18003ad76`
- `msvcrt!wcschr` at `0x18003ad9d`
- `msvcrt!wcsrchr` at `0x18003adc7`
- `msvcrt!wcsrchr` at `0x18003adc7`
- `KERNEL32!LocalFree` at `0x18003ae6e`
- `KERNEL32!LocalFree` at `0x18003afe3`
- `KERNEL32!LocalFree` at `0x18003ae6e`
- `KERNEL32!LocalFree` at `0x18003afe3`
- `KERNEL32!GetLastError` at `0x18003ad4a`
- `KERNEL32!GetLastError` at `0x18003ae5d`
- `KERNEL32!GetLastError` at `0x18003af60`
- `KERNEL32!GetLastError` at `0x18003ad4a`
- `KERNEL32!GetLastError` at `0x18003ae5d`
- `KERNEL32!GetLastError` at `0x18003af60`
- `KERNEL32!GetProcAddress` at `0x18003ad31`
- `KERNEL32!GetProcAddress` at `0x18003ad31`
- `KERNEL32!FreeLibrary` at `0x18003ae85`
- `KERNEL32!FreeLibrary` at `0x18003ae85`
- `KERNEL32!LoadLibraryExW` at `0x18003ad13`
- `KERNEL32!LoadLibraryExW` at `0x18003ad13`
- `KERNEL32!CloseHandle` at `0x18003af4b`
- `KERNEL32!CloseHandle` at `0x18003af4b`
- `KERNEL32!GetCommandLineW` at `0x18003a830`
- `KERNEL32!GetCommandLineW` at `0x18003a830`
- `RPCRT4!NdrClientCall3` at `0x18003a953`
- `RPCRT4!NdrClientCall3` at `0x18003afaf`
- `RPCRT4!NdrClientCall3` at `0x18003a953`
- `RPCRT4!NdrClientCall3` at `0x18003afaf`
- `SspiCli!GetUserNameExW` at `0x18003a824`
- `SspiCli!GetUserNameExW` at `0x18003a824`

## string_xrefs

- `0x18003ad0c`: `shell32.dll`

## pseudocode

```c
DWORD __fastcall InstallApplicationInternal(struct _INSTALLDATA *a1)
{
  unsigned __int16 *v1; // r15
  DWORD result; // eax
  LPWSTR CommandLineW; // rax
  const wchar_t *v5; // r8
  INSTALLSPECTYPE Type; // ecx
  __int64 v7; // r13
  char v8; // si
  __int32 v9; // ecx
  __int32 v10; // ecx
  __int32 v11; // ecx
  DWORD LastError; // edi
  unsigned int v13; // r12d
  unsigned int i; // esi
  __int64 v15; // r15
  DWORD v16; // eax
  __int64 v17; // r8
  DWORD v18; // r14d
  unsigned int v19; // ebx
  __int64 v20; // r14
  __int64 v21; // r15
  __int64 v22; // rcx
  wchar_t *v23; // rcx
  DWORD v24; // eax
  DWORD v25; // ebx
  unsigned int j; // ebx
  HMODULE Library; // rax
  HMODULE v28; // r12
  const wchar_t *v29; // r14
  wchar_t *v30; // rbx
  wchar_t *v31; // rax
  wchar_t *v32; // rsi
  wchar_t *v33; // rbx
  unsigned __int16 *v34; // rax
  int v35; // ebx
  unsigned __int16 **k; // rcx
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  ULONG nSize[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v42[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v43[2]; // [rsp+80h] [rbp-80h]
  wchar_t *Str[2]; // [rsp+90h] [rbp-70h]
  __int64 v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v47[16]; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v48[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h]
  __int64 v50; // [rsp+D0h] [rbp-30h]
  const wchar_t *v51; // [rsp+D8h] [rbp-28h]
  wchar_t *v52; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v53; // [rsp+E8h] [rbp-18h]
  int v54; // [rsp+F0h] [rbp-10h]
  HANDLE hObject; // [rsp+128h] [rbp+28h]
  __int128 v56; // [rsp+130h] [rbp+30h] BYREF
  __int128 v57; // [rsp+140h] [rbp+40h]
  WCHAR NameBuffer[8]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v59; // [rsp+160h] [rbp+60h]
  __int128 v60; // [rsp+170h] [rbp+70h]

  v1 = 0;
  v38 = 0;
  v56 = 0;
  v45 = 0;
  v57 = 0;
  LOBYTE(v37) = 0;
  *(_OWORD *)v42 = 0;
  v46 = 0;
  *(_OWORD *)v43 = 0;
  *(_OWORD *)Str = 0;
  *(_OWORD *)hMem = 0;
  result = Bind();
  if ( !result )
  {
    if ( (unsigned int)DebugLevelOn(4u) )
    {
      nSize[0] = 32;
      NameBuffer[0] = 0;
      GetUserNameExW((EXTENDED_NAME_FORMAT)65538, NameBuffer, nSize);
      CommandLineW = GetCommandLineW();
      v5 = &P;
      if ( CommandLineW )
        v5 = CommandLineW;
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4u, 0x7D5u, v5, NameBuffer);
    }
    Type = a1->Type;
    if ( a1->Type == (COMCLASS|APPNAME) )
    {
      v7 = *(_QWORD *)&a1[1].Type;
      v8 = 1;
      if ( v7 )
      {
        a1->Type = APPNAME;
        Type = APPNAME;
      }
      else
      {
        Type = COMCLASS|APPNAME;
      }
    }
    else
    {
      v8 = 0;
      v7 = 0;
    }
    *(_QWORD *)&v56 = (unsigned int)Type | 0x900000000LL;
    v9 = Type - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 && (v11 = v10 - 1) != 0 )
      {
        if ( v11 != 1 )
          return 87;
        *((_QWORD *)&v56 + 1) = a1->Spec.AppName.Name;
        *(_QWORD *)&v57 = *(_QWORD *)a1->Spec.COMClass.Clsid.Data4;
        DWORD2(v57) = a1->Spec.COMClass.ClsCtx;
      }
      else
      {
        *((_QWORD *)&v56 + 1) = a1->Spec.AppName.Name;
      }
    }
    else
    {
      *((_QWORD *)&v56 + 1) = a1->Spec.AppName.Name;
      v57 = *(_OWORD *)a1->Spec.COMClass.Clsid.Data4;
    }
    v38 = 0;
    v45 = 0;
    *(_OWORD *)v42 = 0;
    *(_OWORD *)v43 = 0;
    *(_OWORD *)Str = 0;
    *(_OWORD *)hMem = 0;
    result = (unsigned int)NdrClientCall3(
                             (MIDL_STUBLESS_PROXY_INFO *)&stru_180075750,
                             1u,
                             0,
                             ghRpc,
                             &v56,
                             &v38,
                             v42,
                             hMem,
                             v37).Pointer;
    nSize[0] = result;
    if ( !result )
    {
      CLoadMsi::CLoadMsi((CLoadMsi *)v47, nSize);
      LastError = nSize[0];
      if ( nSize[0] )
        goto LABEL_105;
      if ( !Str[1] )
      {
        if ( v8 )
        {
          LastError = 87;
          goto LABEL_105;
        }
        v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD))gpfnMsiSetInternalUI)(0, 0);
        if ( LODWORD(hMem[0]) )
          ((void (__fastcall *)(__int64))gpfnMsiSetInternalUI)(3);
        for ( i = 0; ; ++i )
        {
          if ( i >= LODWORD(hMem[0]) )
          {
            LastError = InstallManageApp(v38, v42[0], 0, &v37);
            if ( LastError )
            {
LABEL_43:
              v19 = 0;
              if ( i )
              {
                v20 = 0;
                do
                {
                  LOBYTE(v37) = 0;
                  v21 = 56 * v20;
                  if ( !(unsigned int)InstallManageApp(v38, *((_QWORD *)hMem[1] + 7 * v20), LastError, &v37)
                    && (_BYTE)v37 )
                  {
                    ((void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))gpfnMsiConfigureProductEx)(
                      *(_QWORD *)((char *)hMem[1] + v21 + 24),
                      0,
                      5,
                      0);
                    CEventsBase::Install(
                      (CEventsBase *)&v46,
                      LastError,
                      *(const unsigned __int16 **)((char *)hMem[1] + v21 + 8),
                      *(const unsigned __int16 **)((char *)hMem[1] + v21 + 16));
                  }
                  ++v19;
                  ++v20;
                }
                while ( v19 < i );
              }
              goto LABEL_105;
            }
            v22 = (v45 & 2) != 0 ? 5 : 3;
            if ( a1->Type == APPNAME && (v45 & 1) != 0 )
              LODWORD(v22) = v22 | 0x80;
            ((void (__fastcall *)(__int64, _QWORD))gpfnMsiSetInternalUI)(v22, 0);
            v23 = Str[0];
            if ( Str[0] )
            {
              if ( *(_DWORD *)&gDebugLevel )
              {
                _DebugMsg(4u, 0x7D2u, v42[1], v43[0]);
                v23 = Str[0];
              }
              v24 = ((__int64 (__fastcall *)(wchar_t *, _QWORD, _QWORD, _QWORD))gpfnMsiProvideComponentFromDescriptor)(
                      v23,
                      0,
                      0,
                      0);
            }
            else
            {
              if ( *(_DWORD *)&gDebugLevel )
                _DebugMsg(4u, 0x7D1u, v42[1], v43[0]);
              v24 = ((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, __int64))gpfnMsiConfigureProductEx)(
                      v43[1],
                      0,
                      5);
            }
            LastError = v24;
            if ( v24 == 1641 || v24 == 3010 || v24 == 1604 )
            {
              LastError = 0;
              v25 = 0;
            }
            else
            {
              v25 = v24;
            }
            ReportInstallStatus(v38, LastError, 0, v42[1], v43[0], v42[0]);
            ((void (__fastcall *)(_QWORD, _QWORD))gpfnMsiSetInternalUI)(v13, 0);
            if ( v25 )
            {
              if ( (v45 & 4) != 0 )
                goto LABEL_105;
              InstallUnmanageApp(v38, v42[0], 0);
              goto LABEL_43;
            }
            for ( j = 0; j < i; ++j )
              InstallUnmanageApp(v38, *((_QWORD *)hMem[1] + 7 * j), 0);
LABEL_105:
            if ( v38 )
              NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180075750, 4u, 0, LastError == 0, &v38);
            for ( k = v42; ; k = (unsigned __int16 **)((char *)hMem[1] + 56 * LODWORD(hMem[0])) )
            {
              FreeApplicationInfo((struct __MIDL_appmgmt_0004 *)k);
              if ( !LODWORD(hMem[0]) )
                break;
              --LODWORD(hMem[0]);
            }
            LocalFree(hMem[1]);
            CLoadMsi::~CLoadMsi((CLoadMsi *)v47);
            return LastError;
          }
          v15 = 56LL * i;
          if ( (*((_BYTE *)hMem[1] + v15 + 48) & 0x10) != 0 )
            break;
LABEL_50:
          ;
        }
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4u, 0xBE3u, *(_QWORD *)((char *)hMem[1] + v15 + 8), *(_QWORD *)((char *)hMem[1] + v15 + 16));
        v16 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD, _QWORD))gpfnMsiGetProductInfo)(
                *(_QWORD *)((char *)hMem[1] + v15 + 24),
                L"PackageCode",
                0,
                0);
        LastError = v16;
        if ( !v16 || v16 == 1610 )
        {
          v16 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))gpfnMsiConfigureProductEx)(
                  *(_QWORD *)((char *)hMem[1] + v15 + 24),
                  0xFFFF,
                  2);
          LastError = v16;
          if ( v16 != 3010 )
          {
            if ( v16 == 1625 || v16 == 1644 )
            {
              LOBYTE(v17) = 1;
              v16 = InstallUnmanageApp(v38, *((_QWORD *)hMem[1] + 7 * i), v17);
              LastError = v16;
            }
            goto LABEL_41;
          }
        }
        else if ( v16 != 1605 )
        {
LABEL_41:
          v18 = v16;
LABEL_42:
          ReportInstallStatus(
            v38,
            LastError,
            1,
            *((_QWORD *)hMem[1] + 7 * i + 1),
            *((_QWORD *)hMem[1] + 7 * i + 2),
            *((_QWORD *)hMem[1] + 7 * i));
          if ( v18 )
            goto LABEL_43;
          goto LABEL_50;
        }
        LastError = 0;
        v18 = 0;
        goto LABEL_42;
      }
      memset_0(v48, 0, 0x70u);
      *(_QWORD *)nSize = 0;
      Library = LoadLibraryExW(L"shell32.dll", 0, 0x800u);
      v28 = Library;
      if ( Library && (*(_QWORD *)nSize = GetProcAddress(Library, "ShellExecuteExW")) != 0
        || (v29 = 0, (LastError = GetLastError()) == 0) )
      {
        v29 = Str[1];
        if ( *Str[1] == 34 )
        {
          v30 = Str[1] + 1;
          v31 = wcschr(Str[1] + 1, 0x22u);
          if ( !v31 )
            v30 = (wchar_t *)v29;
          v29 = v30;
        }
        else
        {
          v31 = wcschr(Str[1], 0x20u);
        }
        v32 = v31;
        if ( v31 )
        {
          *v31 = 0;
          do
            ++v32;
          while ( *v32 == 32 );
        }
        v33 = wcsrchr(v29, 0x5Cu);
        if ( !v33 )
          goto LABEL_87;
        v34 = StringDuplicate(v29);
        v1 = v34;
        if ( v34 )
        {
          v34[v33 - v29] = 0;
LABEL_87:
          v48[0] = 112;
          v48[1] = 64;
          v49 = v7;
          v50 = 0;
          v51 = v29;
          v52 = v32;
          v53 = v1;
          v54 = 1;
          hObject = 0;
          if ( *(_DWORD *)&gDebugLevel )
            _DebugMsg(4u, 0x7D4u, v29);
          if ( !(*(unsigned int (__fastcall **)(_DWORD *))nSize)(v48) )
            LastError = GetLastError();
          goto LABEL_91;
        }
        LastError = 14;
      }
LABEL_91:
      LocalFree(v1);
      if ( v28 )
        FreeLibrary(v28);
      if ( !LastError && hObject )
      {
        v35 = 0;
        if ( (unsigned int)LoadUser32Funcs() )
        {
          *(_OWORD *)NameBuffer = 0;
          *(_QWORD *)nSize = hObject;
          v59 = 0;
          v41 = 0;
          v60 = 0;
          while ( 1 )
          {
            v35 = ((__int64 (__fastcall *)(__int64, ULONG *, _QWORD, __int64, int))pfnMsgWaitForMultipleObjects)(
                    1,
                    nSize,
                    0,
                    0xFFFFFFFFLL,
                    7423);
            if ( v35 != 1 )
              break;
            if ( (unsigned int)((__int64 (__fastcall *)(WCHAR *, _QWORD, _QWORD, _QWORD, int))pfnPeekMessageW)(
                                 NameBuffer,
                                 0,
                                 0,
                                 0,
                                 1) )
            {
              ((void (__fastcall *)(WCHAR *))pfnTranslateMessage)(NameBuffer);
              ((void (__fastcall *)(WCHAR *))pfnDispatchMessageW)(NameBuffer);
            }
          }
        }
        CloseHandle(hObject);
        if ( v35 )
          LastError = GetLastError();
        else
          LastError = 0;
      }
      CEvents::ZAPInstall((CEvents *)&v46, LastError, v42[1], v43[0], v29);
      goto LABEL_105;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003a788  push    rbp
0x18003a78a  push    rbx
0x18003a78b  push    rsi
0x18003a78c  push    rdi
0x18003a78d  push    r12
0x18003a78f  push    r13
0x18003a791  push    r14
0x18003a793  push    r15
0x18003a795  lea     rbp, [rsp-0A8h]
0x18003a79d  sub     rsp, 1A8h
0x18003a7a4  mov     rax, cs:__security_cookie
0x18003a7ab  xor     rax, rsp
0x18003a7ae  mov     [rbp+0E0h+var_50], rax
0x18003a7b5  xorps   xmm0, xmm0
0x18003a7b8  xor     r15d, r15d
0x18003a7bb  xor     eax, eax
0x18003a7bd  mov     [rsp+1E0h+var_198], r15
0x18003a7c2  movups  [rbp+0E0h+var_B0], xmm0
0x18003a7c6  mov     [rbp+0E0h+var_140], rax
0x18003a7ca  mov     rbx, rcx
0x18003a7cd  movups  [rbp+0E0h+var_A0], xmm0
0x18003a7d1  mov     byte ptr [rsp+1E0h+var_1A0], r15b
0x18003a7d6  movups  xmmword ptr [rsp+1E0h+var_170], xmm0
0x18003a7db  mov     [rbp+0E0h+var_138], r15
0x18003a7df  movups  xmmword ptr [rbp+0E0h+var_160], xmm0
0x18003a7e3  movups  xmmword ptr [rbp+0E0h+Str], xmm0
0x18003a7e7  movups  xmmword ptr [rsp+1E0h+hMem], xmm0
0x18003a7ec  call    ?Bind@@YAKXZ; Bind(void)
0x18003a7f1  test    eax, eax
0x18003a7f3  jnz     loc_18003AFFA
0x18003a7f9  lea     r14d, [r15+4]
0x18003a7fd  mov     ecx, r14d; unsigned int
0x18003a800  call    ?DebugLevelOn@@YAHK@Z; DebugLevelOn(ulong)
0x18003a805  test    eax, eax
0x18003a807  jz      short loc_18003A864
0x18003a809  lea     r8, [rsp+1E0h+nSize]; nSize
0x18003a80e  mov     [rsp+1E0h+nSize], 20h ; ' '
0x18003a816  lea     rdx, [rbp+0E0h+NameBuffer]; lpNameBuffer
0x18003a81a  mov     [rbp+0E0h+NameBuffer], r15w
0x18003a81f  mov     ecx, 10002h; NameFormat
0x18003a824  call    cs:__imp_GetUserNameExW
0x18003a82b  nop     dword ptr [rax+rax+00h]
0x18003a830  call    cs:__imp_GetCommandLineW
0x18003a837  nop     dword ptr [rax+rax+00h]
0x18003a83c  test    rax, rax
0x18003a83f  lea     r8, P
0x18003a846  cmovnz  r8, rax
0x18003a84a  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18003a851  jz      short loc_18003A864
0x18003a853  lea     r9, [rbp+0E0h+NameBuffer]
0x18003a857  mov     edx, 7D5h; unsigned int
0x18003a85c  mov     ecx, r14d; unsigned int
0x18003a85f  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18003a864  mov     ecx, [rbx]
0x18003a866  cmp     ecx, 5
0x18003a869  jnz     short loc_18003A88B
0x18003a86b  mov     r13, [rbx+20h]
0x18003a86f  mov     sil, 1
0x18003a872  test    r13, r13
0x18003a875  jz      short loc_18003A884
0x18003a877  mov     dword ptr [rbx], 1
0x18003a87d  mov     ecx, 1
0x18003a882  jmp     short loc_18003A891
0x18003a884  mov     ecx, 5
0x18003a889  jmp     short loc_18003A891
0x18003a88b  mov     sil, r15b
0x18003a88e  mov     r13, r15
0x18003a891  mov     dword ptr [rbp+0E0h+var_B0], ecx
0x18003a894  mov     dword ptr [rbp+0E0h+var_B0+4], 9
0x18003a89b  sub     ecx, 1
0x18003a89e  jz      short loc_18003A8DB
0x18003a8a0  sub     ecx, 1
0x18003a8a3  jz      short loc_18003A8D1
0x18003a8a5  sub     ecx, 1
0x18003a8a8  jz      short loc_18003A8D1
0x18003a8aa  cmp     ecx, 1
0x18003a8ad  jz      short loc_18003A8B9
0x18003a8af  mov     eax, 57h ; 'W'
0x18003a8b4  jmp     loc_18003AFFA
0x18003a8b9  mov     rax, [rbx+8]
0x18003a8bd  mov     qword ptr [rbp+0E0h+var_B0+8], rax
0x18003a8c1  mov     rax, [rbx+10h]
0x18003a8c5  mov     qword ptr [rbp+0E0h+var_A0], rax
0x18003a8c9  mov     eax, [rbx+18h]
0x18003a8cc  mov     dword ptr [rbp+0E0h+var_A0+8], eax
0x18003a8cf  jmp     short loc_18003A8F7
0x18003a8d1  mov     rax, [rbx+8]
0x18003a8d5  mov     qword ptr [rbp+0E0h+var_B0+8], rax
0x18003a8d9  jmp     short loc_18003A8F7
0x18003a8db  mov     rax, [rbx+8]
0x18003a8df  mov     qword ptr [rbp+0E0h+var_B0+8], rax
0x18003a8e3  mov     rax, [rbx+10h]
0x18003a8e7  mov     qword ptr [rbp+0E0h+var_A0], rax
0x18003a8eb  mov     eax, [rbx+18h]
0x18003a8ee  mov     dword ptr [rbp+0E0h+var_A0+8], eax
0x18003a8f1  mov     eax, [rbx+1Ch]
0x18003a8f4  mov     dword ptr [rbp+0E0h+var_A0+0Ch], eax
0x18003a8f7  mov     r9, cs:?ghRpc@@3PEAXEA; void * ghRpc
0x18003a8fe  lea     rcx, stru_180075750; pProxyInfo
0x18003a905  xor     eax, eax
0x18003a907  mov     [rsp+1E0h+var_198], r15
0x18003a90c  mov     [rbp+0E0h+var_140], rax
0x18003a910  xorps   xmm0, xmm0
0x18003a913  lea     rax, [rsp+1E0h+hMem]
0x18003a918  xor     r8d, r8d; pReturnValue
0x18003a91b  mov     [rsp+1E0h+var_1A8], rax
0x18003a920  lea     rax, [rsp+1E0h+var_170]
0x18003a925  mov     [rsp+1E0h+var_1B0], rax
0x18003a92a  lea     rax, [rsp+1E0h+var_198]
0x18003a92f  mov     [rsp+1E0h+var_1B8], rax
0x18003a934  lea     rax, [rbp+0E0h+var_B0]
0x18003a938  lea     edx, [r8+1]; nProcNum
0x18003a93c  mov     [rsp+1E0h+var_1C0], rax
0x18003a941  movups  xmmword ptr [rsp+1E0h+var_170], xmm0
0x18003a946  movups  xmmword ptr [rbp+0E0h+var_160], xmm0
0x18003a94a  movups  xmmword ptr [rbp+0E0h+Str], xmm0
0x18003a94e  movups  xmmword ptr [rsp+1E0h+hMem], xmm0
0x18003a953  call    cs:__imp_NdrClientCall3
0x18003a95a  nop     dword ptr [rax+rax+00h]
0x18003a95f  mov     [rsp+1E0h+nSize], eax
0x18003a963  test    eax, eax
0x18003a965  jnz     loc_18003AFFA
0x18003a96b  lea     rdx, [rsp+1E0h+nSize]; unsigned int *
0x18003a970  lea     rcx, [rbp+0E0h+var_130]; this
0x18003a974  call    ??0CLoadMsi@@QEAA@AEAK@Z; CLoadMsi::CLoadMsi(ulong &)
0x18003a979  mov     edi, [rsp+1E0h+nSize]
0x18003a97d  test    edi, edi
0x18003a97f  jnz     loc_18003AF87
0x18003a985  cmp     [rbp+0E0h+Str+8], r15
0x18003a989  jnz     loc_18003ACF0
0x18003a98f  test    sil, sil
0x18003a992  jz      short loc_18003A99E
0x18003a994  mov     edi, 57h ; 'W'
0x18003a999  jmp     loc_18003AF87
0x18003a99e  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x18003a9a5  xor     edx, edx
0x18003a9a7  xor     ecx, ecx
0x18003a9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9ae  mov     r12d, eax
0x18003a9b1  cmp     dword ptr [rsp+1E0h+hMem], r15d
0x18003a9b6  jbe     short loc_18003A9C9
0x18003a9b8  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x18003a9bf  xor     edx, edx
0x18003a9c1  lea     ecx, [rdx+3]
0x18003a9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9c9  mov     esi, r15d
0x18003a9cc  mov     r13d, 0BC2h
0x18003a9d2  cmp     esi, dword ptr [rsp+1E0h+hMem]
0x18003a9d6  jnb     loc_18003AB7B
0x18003a9dc  mov     r8, [rsp+1E0h+hMem+8]
0x18003a9e1  mov     eax, esi
0x18003a9e3  imul    r15, rax, 38h ; '8'
0x18003a9e7  test    byte ptr [r8+r15+30h], 10h
0x18003a9ed  jz      loc_18003AB69
0x18003a9f3  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18003a9fa  jz      short loc_18003AA13
0x18003a9fc  mov     r9, [r8+r15+10h]
0x18003aa01  mov     edx, 0BE3h; unsigned int
0x18003aa06  mov     r8, [r8+r15+8]
0x18003aa0b  mov     ecx, r14d; unsigned int
0x18003aa0e  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18003aa13  mov     rcx, [rsp+1E0h+hMem+8]
0x18003aa18  lea     rdx, aPackagecode; "PackageCode"
0x18003aa1f  mov     rax, cs:?gpfnMsiGetProductInfo@@3P6AIPEBG0PEAGPEAK@ZEA; uint (*gpfnMsiGetProductInfo)(ushort const *,ushort const *,ushort *,ulong *)
0x18003aa26  xor     r9d, r9d
0x18003aa29  xor     r8d, r8d
0x18003aa2c  mov     rcx, [rcx+r15+18h]
0x18003aa31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa36  mov     edi, eax
0x18003aa38  test    eax, eax
0x18003aa3a  jz      short loc_18003AA4C
0x18003aa3c  cmp     eax, 64Ah
0x18003aa41  jz      short loc_18003AA4C
0x18003aa43  cmp     eax, 645h
0x18003aa48  jz      short loc_18003AA75
0x18003aa4a  jmp     short loc_18003AAA2
0x18003aa4c  mov     rcx, [rsp+1E0h+hMem+8]
0x18003aa51  xor     r9d, r9d
0x18003aa54  mov     rax, cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x18003aa5b  mov     edx, 0FFFFh
0x18003aa60  mov     rcx, [rcx+r15+18h]
0x18003aa65  lea     r8d, [r9+2]
0x18003aa69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa6e  mov     edi, eax
0x18003aa70  cmp     eax, r13d
0x18003aa73  jnz     short loc_18003AA7C
0x18003aa75  xor     edi, edi
0x18003aa77  xor     r14d, r14d
0x18003aa7a  jmp     short loc_18003AAA5
0x18003aa7c  cmp     eax, 659h
0x18003aa81  jz      short loc_18003AA8A
0x18003aa83  cmp     eax, 66Ch
0x18003aa88  jnz     short loc_18003AAA2
0x18003aa8a  mov     rdx, [rsp+1E0h+hMem+8]
0x18003aa8f  mov     r8b, 1
0x18003aa92  mov     rcx, [rsp+1E0h+var_198]
0x18003aa97  mov     rdx, [rdx+r15]
0x18003aa9b  call    InstallUnmanageApp
0x18003aaa0  mov     edi, eax
0x18003aaa2  mov     r14d, eax
0x18003aaa5  mov     r9, [rsp+1E0h+hMem+8]
0x18003aaaa  mov     r8d, 1
0x18003aab0  mov     rcx, [rsp+1E0h+var_198]
0x18003aab5  mov     edx, edi
0x18003aab7  mov     rax, [r9+r15]
0x18003aabb  mov     [rsp+1E0h+var_1B8], rax
0x18003aac0  mov     rax, [r9+r15+10h]
0x18003aac5  mov     r9, [r9+r15+8]
0x18003aaca  mov     [rsp+1E0h+var_1C0], rax
0x18003aacf  call    ReportInstallStatus
0x18003aad4  xor     r15d, r15d
0x18003aad7  test    r14d, r14d
0x18003aada  jz      loc_18003AB6E
0x18003aae0  mov     ebx, r15d
0x18003aae3  test    esi, esi
0x18003aae5  jz      loc_18003AF87
0x18003aaeb  mov     r14, r15
0x18003aaee  mov     rdx, [rsp+1E0h+hMem+8]
0x18003aaf3  lea     r9, [rsp+1E0h+var_1A0]
0x18003aaf8  mov     rcx, [rsp+1E0h+var_198]
0x18003aafd  mov     r8d, edi
0x18003ab00  mov     byte ptr [rsp+1E0h+var_1A0], r15b
0x18003ab05  imul    r15, r14, 38h ; '8'
0x18003ab09  mov     rdx, [r15+rdx]
0x18003ab0d  call    InstallManageApp
0x18003ab12  test    eax, eax
0x18003ab14  jnz     short loc_18003AB55
0x18003ab16  cmp     byte ptr [rsp+1E0h+var_1A0], al
0x18003ab1a  jz      short loc_18003AB55
0x18003ab1c  mov     rcx, [rsp+1E0h+hMem+8]
0x18003ab21  lea     r8d, [rax+5]
0x18003ab25  mov     rax, cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x18003ab2c  xor     r9d, r9d
0x18003ab2f  xor     edx, edx
0x18003ab31  mov     rcx, [r15+rcx+18h]
0x18003ab36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab3b  mov     r8, [rsp+1E0h+hMem+8]
0x18003ab40  lea     rcx, [rbp+0E0h+var_138]; this
0x18003ab44  mov     edx, edi; unsigned int
0x18003ab46  mov     r9, [r15+r8+10h]; unsigned __int16 *
0x18003ab4b  mov     r8, [r15+r8+8]; unsigned __int16 *
0x18003ab50  call    ?Install@CEventsBase@@QEAAXKPEBG0@Z; CEventsBase::Install(ulong,ushort const *,ushort const *)
0x18003ab55  inc     ebx
0x18003ab57  inc     r14
0x18003ab5a  mov     r15d, 0
0x18003ab60  cmp     ebx, esi
0x18003ab62  jb      short loc_18003AAEE
0x18003ab64  jmp     loc_18003AF87
0x18003ab69  xor     r15d, r15d
0x18003ab6c  jmp     short loc_18003AB74
0x18003ab6e  mov     r14d, 4
0x18003ab74  inc     esi
0x18003ab76  jmp     loc_18003A9D2
0x18003ab7b  mov     rdx, [rsp+1E0h+var_170]
0x18003ab80  lea     r9, [rsp+1E0h+var_1A0]
0x18003ab85  mov     rcx, [rsp+1E0h+var_198]
0x18003ab8a  xor     r8d, r8d
0x18003ab8d  call    InstallManageApp
0x18003ab92  mov     edi, eax
0x18003ab94  test    eax, eax
0x18003ab96  jnz     loc_18003AAE0
0x18003ab9c  mov     eax, dword ptr [rbp+0E0h+var_140]
0x18003ab9f  and     al, 2
0x18003aba1  neg     al
0x18003aba3  sbb     ecx, ecx
0x18003aba5  and     ecx, 2
0x18003aba8  add     ecx, 3
0x18003abab  cmp     dword ptr [rbx], 1
0x18003abae  jnz     short loc_18003ABBA
0x18003abb0  test    byte ptr [rbp+0E0h+var_140], 1
0x18003abb4  jz      short loc_18003ABBA
0x18003abb6  bts     ecx, 7
0x18003abba  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x18003abc1  xor     edx, edx
0x18003abc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abc8  mov     rcx, [rbp+0E0h+Str]
0x18003abcc  test    rcx, rcx
0x18003abcf  jz      short loc_18003AC0A
0x18003abd1  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18003abd8  jz      short loc_18003ABF4
0x18003abda  mov     r9, [rbp+0E0h+var_160]
0x18003abde  mov     edx, 7D2h; unsigned int
0x18003abe3  mov     r8, [rsp+1E0h+var_170+8]
0x18003abe8  mov     ecx, r14d; unsigned int
0x18003abeb  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18003abf0  mov     rcx, [rbp+0E0h+Str]
0x18003abf4  mov     rax, cs:?gpfnMsiProvideComponentFromDescriptor@@3P6AIPEBGPEAGPEAK2@ZEA; uint (*gpfnMsiProvideComponentFromDescriptor)(ushort const *,ushort *,ulong *,ulong *)
0x18003abfb  xor     r9d, r9d
0x18003abfe  xor     r8d, r8d
0x18003ac01  xor     edx, edx
0x18003ac03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac08  jmp     short loc_18003AC42
0x18003ac0a  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18003ac11  jz      short loc_18003AC29
0x18003ac13  mov     r9, [rbp+0E0h+var_160]
0x18003ac17  mov     edx, 7D1h; unsigned int
0x18003ac1c  mov     r8, [rsp+1E0h+var_170+8]
0x18003ac21  mov     ecx, r14d; unsigned int
0x18003ac24  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18003ac29  mov     rcx, [rbp+0E0h+var_160+8]
  ... truncated ...
```
