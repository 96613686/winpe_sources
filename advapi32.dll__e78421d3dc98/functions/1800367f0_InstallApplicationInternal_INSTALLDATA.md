# InstallApplicationInternal(_INSTALLDATA *)

- ea: `0x1800367f0`
- end: `0x180037025`
- name: `?InstallApplicationInternal@@YAKPEAU_INSTALLDATA@@@Z`
- size: `2101`
- prototype: `DWORD __fastcall(struct _INSTALLDATA *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800432d0`

## callees

- `0x18002eff0`
- `0x18002f164`
- `0x1800367f0`
- `0x18003702c`
- `0x180039d28`
- `0x180042e6c`
- `0x180042f00`
- `0x18004332c`
- `0x1800434bc`
- `0x180044814`
- `0x180044b04`
- `0x180044b3c`
- `0x180044b70`
- `0x180044f5c`
- `0x18006505a`
- `0x180065090`
- `0x180066010`

## import_xrefs

- `msvcrt!wcschr` at `0x180036dba`
- `msvcrt!wcschr` at `0x180036ddb`
- `msvcrt!wcschr` at `0x180036dba`
- `msvcrt!wcschr` at `0x180036ddb`
- `msvcrt!wcsrchr` at `0x180036dff`
- `msvcrt!wcsrchr` at `0x180036dff`
- `KERNEL32!LocalFree` at `0x180036e9a`
- `KERNEL32!LocalFree` at `0x180036ff1`
- `KERNEL32!LocalFree` at `0x180036e9a`
- `KERNEL32!LocalFree` at `0x180036ff1`
- `KERNEL32!GetLastError` at `0x180036d94`
- `KERNEL32!GetLastError` at `0x180036e8f`
- `KERNEL32!GetLastError` at `0x180036f7a`
- `KERNEL32!GetLastError` at `0x180036d94`
- `KERNEL32!GetLastError` at `0x180036e8f`
- `KERNEL32!GetLastError` at `0x180036f7a`
- `KERNEL32!GetProcAddress` at `0x180036d81`
- `KERNEL32!GetProcAddress` at `0x180036d81`
- `KERNEL32!FreeLibrary` at `0x180036eab`
- `KERNEL32!FreeLibrary` at `0x180036eab`
- `KERNEL32!LoadLibraryExW` at `0x180036d69`
- `KERNEL32!LoadLibraryExW` at `0x180036d69`
- `KERNEL32!CloseHandle` at `0x180036f6b`
- `KERNEL32!CloseHandle` at `0x180036f6b`
- `KERNEL32!GetCommandLineW` at `0x180036892`
- `KERNEL32!GetCommandLineW` at `0x180036892`
- `RPCRT4!NdrClientCall3` at `0x1800369af`
- `RPCRT4!NdrClientCall3` at `0x180036fc3`
- `RPCRT4!NdrClientCall3` at `0x1800369af`
- `RPCRT4!NdrClientCall3` at `0x180036fc3`
- `SspiCli!GetUserNameExW` at `0x18003688c`
- `SspiCli!GetUserNameExW` at `0x18003688c`

## string_xrefs

- `0x180036d62`: `shell32.dll`

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
                             (MIDL_STUBLESS_PROXY_INFO *)&stru_180067750,
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
              NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180067750, 4u, 0, LastError == 0, &v38);
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
0x1800367f0  push    rbp
0x1800367f2  push    rbx
0x1800367f3  push    rsi
0x1800367f4  push    rdi
0x1800367f5  push    r12
0x1800367f7  push    r13
0x1800367f9  push    r14
0x1800367fb  push    r15
0x1800367fd  lea     rbp, [rsp-0A8h]
0x180036805  sub     rsp, 1A8h
0x18003680c  mov     rax, cs:__security_cookie
0x180036813  xor     rax, rsp
0x180036816  mov     [rbp+0E0h+var_50], rax
0x18003681d  xorps   xmm0, xmm0
0x180036820  xor     r15d, r15d
0x180036823  xor     eax, eax
0x180036825  mov     [rsp+1E0h+var_198], r15
0x18003682a  movups  [rbp+0E0h+var_B0], xmm0
0x18003682e  mov     [rbp+0E0h+var_140], rax
0x180036832  mov     rbx, rcx
0x180036835  movups  [rbp+0E0h+var_A0], xmm0
0x180036839  mov     byte ptr [rsp+1E0h+var_1A0], r15b
0x18003683e  movups  xmmword ptr [rsp+1E0h+var_170], xmm0
0x180036843  mov     [rbp+0E0h+var_138], r15
0x180036847  movups  xmmword ptr [rbp+0E0h+var_160], xmm0
0x18003684b  movups  xmmword ptr [rbp+0E0h+Str], xmm0
0x18003684f  movups  xmmword ptr [rsp+1E0h+hMem], xmm0
0x180036854  call    ?Bind@@YAKXZ; Bind(void)
0x180036859  test    eax, eax
0x18003685b  jnz     loc_180037002
0x180036861  lea     r14d, [r15+4]
0x180036865  mov     ecx, r14d; unsigned int
0x180036868  call    ?DebugLevelOn@@YAHK@Z; DebugLevelOn(ulong)
0x18003686d  test    eax, eax
0x18003686f  jz      short loc_1800368C0
0x180036871  lea     r8, [rsp+1E0h+nSize]; nSize
0x180036876  mov     [rsp+1E0h+nSize], 20h ; ' '
0x18003687e  lea     rdx, [rbp+0E0h+NameBuffer]; lpNameBuffer
0x180036882  mov     [rbp+0E0h+NameBuffer], r15w
0x180036887  mov     ecx, 10002h; NameFormat
0x18003688c  call    cs:__imp_GetUserNameExW
0x180036892  call    cs:__imp_GetCommandLineW
0x180036898  test    rax, rax
0x18003689b  lea     r8, P
0x1800368a2  cmovnz  r8, rax
0x1800368a6  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x1800368ad  jz      short loc_1800368C0
0x1800368af  lea     r9, [rbp+0E0h+NameBuffer]
0x1800368b3  mov     edx, 7D5h; unsigned int
0x1800368b8  mov     ecx, r14d; unsigned int
0x1800368bb  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800368c0  mov     ecx, [rbx]
0x1800368c2  cmp     ecx, 5
0x1800368c5  jnz     short loc_1800368E7
0x1800368c7  mov     r13, [rbx+20h]
0x1800368cb  mov     sil, 1
0x1800368ce  test    r13, r13
0x1800368d1  jz      short loc_1800368E0
0x1800368d3  mov     dword ptr [rbx], 1
0x1800368d9  mov     ecx, 1
0x1800368de  jmp     short loc_1800368ED
0x1800368e0  mov     ecx, 5
0x1800368e5  jmp     short loc_1800368ED
0x1800368e7  mov     sil, r15b
0x1800368ea  mov     r13, r15
0x1800368ed  mov     dword ptr [rbp+0E0h+var_B0], ecx
0x1800368f0  mov     dword ptr [rbp+0E0h+var_B0+4], 9
0x1800368f7  sub     ecx, 1
0x1800368fa  jz      short loc_180036937
0x1800368fc  sub     ecx, 1
0x1800368ff  jz      short loc_18003692D
0x180036901  sub     ecx, 1
0x180036904  jz      short loc_18003692D
0x180036906  cmp     ecx, 1
0x180036909  jz      short loc_180036915
0x18003690b  mov     eax, 57h ; 'W'
0x180036910  jmp     loc_180037002
0x180036915  mov     rax, [rbx+8]
0x180036919  mov     qword ptr [rbp+0E0h+var_B0+8], rax
0x18003691d  mov     rax, [rbx+10h]
0x180036921  mov     qword ptr [rbp+0E0h+var_A0], rax
0x180036925  mov     eax, [rbx+18h]
0x180036928  mov     dword ptr [rbp+0E0h+var_A0+8], eax
0x18003692b  jmp     short loc_180036953
0x18003692d  mov     rax, [rbx+8]
0x180036931  mov     qword ptr [rbp+0E0h+var_B0+8], rax
0x180036935  jmp     short loc_180036953
0x180036937  mov     rax, [rbx+8]
0x18003693b  mov     qword ptr [rbp+0E0h+var_B0+8], rax
0x18003693f  mov     rax, [rbx+10h]
0x180036943  mov     qword ptr [rbp+0E0h+var_A0], rax
0x180036947  mov     eax, [rbx+18h]
0x18003694a  mov     dword ptr [rbp+0E0h+var_A0+8], eax
0x18003694d  mov     eax, [rbx+1Ch]
0x180036950  mov     dword ptr [rbp+0E0h+var_A0+0Ch], eax
0x180036953  mov     r9, cs:?ghRpc@@3PEAXEA; void * ghRpc
0x18003695a  lea     rcx, stru_180067750; pProxyInfo
0x180036961  xor     eax, eax
0x180036963  mov     [rsp+1E0h+var_198], r15
0x180036968  mov     [rbp+0E0h+var_140], rax
0x18003696c  xorps   xmm0, xmm0
0x18003696f  lea     rax, [rsp+1E0h+hMem]
0x180036974  xor     r8d, r8d; pReturnValue
0x180036977  mov     [rsp+1E0h+var_1A8], rax
0x18003697c  lea     rax, [rsp+1E0h+var_170]
0x180036981  mov     [rsp+1E0h+var_1B0], rax
0x180036986  lea     rax, [rsp+1E0h+var_198]
0x18003698b  mov     [rsp+1E0h+var_1B8], rax
0x180036990  lea     rax, [rbp+0E0h+var_B0]
0x180036994  lea     edx, [r8+1]; nProcNum
0x180036998  mov     [rsp+1E0h+var_1C0], rax
0x18003699d  movups  xmmword ptr [rsp+1E0h+var_170], xmm0
0x1800369a2  movups  xmmword ptr [rbp+0E0h+var_160], xmm0
0x1800369a6  movups  xmmword ptr [rbp+0E0h+Str], xmm0
0x1800369aa  movups  xmmword ptr [rsp+1E0h+hMem], xmm0
0x1800369af  call    cs:__imp_NdrClientCall3
0x1800369b5  mov     [rsp+1E0h+nSize], eax
0x1800369b9  test    eax, eax
0x1800369bb  jnz     loc_180037002
0x1800369c1  lea     rdx, [rsp+1E0h+nSize]; unsigned int *
0x1800369c6  lea     rcx, [rbp+0E0h+var_130]; this
0x1800369ca  call    ??0CLoadMsi@@QEAA@AEAK@Z; CLoadMsi::CLoadMsi(ulong &)
0x1800369cf  mov     edi, [rsp+1E0h+nSize]
0x1800369d3  test    edi, edi
0x1800369d5  jnz     loc_180036F9B
0x1800369db  cmp     [rbp+0E0h+Str+8], r15
0x1800369df  jnz     loc_180036D46
0x1800369e5  test    sil, sil
0x1800369e8  jz      short loc_1800369F4
0x1800369ea  mov     edi, 57h ; 'W'
0x1800369ef  jmp     loc_180036F9B
0x1800369f4  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x1800369fb  xor     edx, edx
0x1800369fd  xor     ecx, ecx
0x1800369ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a04  mov     r12d, eax
0x180036a07  cmp     dword ptr [rsp+1E0h+hMem], r15d
0x180036a0c  jbe     short loc_180036A1F
0x180036a0e  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x180036a15  xor     edx, edx
0x180036a17  lea     ecx, [rdx+3]
0x180036a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a1f  mov     esi, r15d
0x180036a22  mov     r13d, 0BC2h
0x180036a28  cmp     esi, dword ptr [rsp+1E0h+hMem]
0x180036a2c  jnb     loc_180036BD1
0x180036a32  mov     r8, [rsp+1E0h+hMem+8]
0x180036a37  mov     eax, esi
0x180036a39  imul    r15, rax, 38h ; '8'
0x180036a3d  test    byte ptr [r8+r15+30h], 10h
0x180036a43  jz      loc_180036BBF
0x180036a49  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180036a50  jz      short loc_180036A69
0x180036a52  mov     r9, [r8+r15+10h]
0x180036a57  mov     edx, 0BE3h; unsigned int
0x180036a5c  mov     r8, [r8+r15+8]
0x180036a61  mov     ecx, r14d; unsigned int
0x180036a64  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180036a69  mov     rcx, [rsp+1E0h+hMem+8]
0x180036a6e  lea     rdx, aPackagecode; "PackageCode"
0x180036a75  mov     rax, cs:?gpfnMsiGetProductInfo@@3P6AIPEBG0PEAGPEAK@ZEA; uint (*gpfnMsiGetProductInfo)(ushort const *,ushort const *,ushort *,ulong *)
0x180036a7c  xor     r9d, r9d
0x180036a7f  xor     r8d, r8d
0x180036a82  mov     rcx, [rcx+r15+18h]
0x180036a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a8c  mov     edi, eax
0x180036a8e  test    eax, eax
0x180036a90  jz      short loc_180036AA2
0x180036a92  cmp     eax, 64Ah
0x180036a97  jz      short loc_180036AA2
0x180036a99  cmp     eax, 645h
0x180036a9e  jz      short loc_180036ACB
0x180036aa0  jmp     short loc_180036AF8
0x180036aa2  mov     rcx, [rsp+1E0h+hMem+8]
0x180036aa7  xor     r9d, r9d
0x180036aaa  mov     rax, cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x180036ab1  mov     edx, 0FFFFh
0x180036ab6  mov     rcx, [rcx+r15+18h]
0x180036abb  lea     r8d, [r9+2]
0x180036abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ac4  mov     edi, eax
0x180036ac6  cmp     eax, r13d
0x180036ac9  jnz     short loc_180036AD2
0x180036acb  xor     edi, edi
0x180036acd  xor     r14d, r14d
0x180036ad0  jmp     short loc_180036AFB
0x180036ad2  cmp     eax, 659h
0x180036ad7  jz      short loc_180036AE0
0x180036ad9  cmp     eax, 66Ch
0x180036ade  jnz     short loc_180036AF8
0x180036ae0  mov     rdx, [rsp+1E0h+hMem+8]
0x180036ae5  mov     r8b, 1
0x180036ae8  mov     rcx, [rsp+1E0h+var_198]
0x180036aed  mov     rdx, [rdx+r15]
0x180036af1  call    InstallUnmanageApp
0x180036af6  mov     edi, eax
0x180036af8  mov     r14d, eax
0x180036afb  mov     r9, [rsp+1E0h+hMem+8]
0x180036b00  mov     r8d, 1
0x180036b06  mov     rcx, [rsp+1E0h+var_198]
0x180036b0b  mov     edx, edi
0x180036b0d  mov     rax, [r9+r15]
0x180036b11  mov     [rsp+1E0h+var_1B8], rax
0x180036b16  mov     rax, [r9+r15+10h]
0x180036b1b  mov     r9, [r9+r15+8]
0x180036b20  mov     [rsp+1E0h+var_1C0], rax
0x180036b25  call    ReportInstallStatus
0x180036b2a  xor     r15d, r15d
0x180036b2d  test    r14d, r14d
0x180036b30  jz      loc_180036BC4
0x180036b36  mov     ebx, r15d
0x180036b39  test    esi, esi
0x180036b3b  jz      loc_180036F9B
0x180036b41  mov     r14, r15
0x180036b44  mov     rdx, [rsp+1E0h+hMem+8]
0x180036b49  lea     r9, [rsp+1E0h+var_1A0]
0x180036b4e  mov     rcx, [rsp+1E0h+var_198]
0x180036b53  mov     r8d, edi
0x180036b56  mov     byte ptr [rsp+1E0h+var_1A0], r15b
0x180036b5b  imul    r15, r14, 38h ; '8'
0x180036b5f  mov     rdx, [r15+rdx]
0x180036b63  call    InstallManageApp
0x180036b68  test    eax, eax
0x180036b6a  jnz     short loc_180036BAB
0x180036b6c  cmp     byte ptr [rsp+1E0h+var_1A0], al
0x180036b70  jz      short loc_180036BAB
0x180036b72  mov     rcx, [rsp+1E0h+hMem+8]
0x180036b77  lea     r8d, [rax+5]
0x180036b7b  mov     rax, cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x180036b82  xor     r9d, r9d
0x180036b85  xor     edx, edx
0x180036b87  mov     rcx, [r15+rcx+18h]
0x180036b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b91  mov     r8, [rsp+1E0h+hMem+8]
0x180036b96  lea     rcx, [rbp+0E0h+var_138]; this
0x180036b9a  mov     edx, edi; unsigned int
0x180036b9c  mov     r9, [r15+r8+10h]; unsigned __int16 *
0x180036ba1  mov     r8, [r15+r8+8]; unsigned __int16 *
0x180036ba6  call    ?Install@CEventsBase@@QEAAXKPEBG0@Z; CEventsBase::Install(ulong,ushort const *,ushort const *)
0x180036bab  inc     ebx
0x180036bad  inc     r14
0x180036bb0  mov     r15d, 0
0x180036bb6  cmp     ebx, esi
0x180036bb8  jb      short loc_180036B44
0x180036bba  jmp     loc_180036F9B
0x180036bbf  xor     r15d, r15d
0x180036bc2  jmp     short loc_180036BCA
0x180036bc4  mov     r14d, 4
0x180036bca  inc     esi
0x180036bcc  jmp     loc_180036A28
0x180036bd1  mov     rdx, [rsp+1E0h+var_170]
0x180036bd6  lea     r9, [rsp+1E0h+var_1A0]
0x180036bdb  mov     rcx, [rsp+1E0h+var_198]
0x180036be0  xor     r8d, r8d
0x180036be3  call    InstallManageApp
0x180036be8  mov     edi, eax
0x180036bea  test    eax, eax
0x180036bec  jnz     loc_180036B36
0x180036bf2  mov     eax, dword ptr [rbp+0E0h+var_140]
0x180036bf5  and     al, 2
0x180036bf7  neg     al
0x180036bf9  sbb     ecx, ecx
0x180036bfb  and     ecx, 2
0x180036bfe  add     ecx, 3
0x180036c01  cmp     dword ptr [rbx], 1
0x180036c04  jnz     short loc_180036C10
0x180036c06  test    byte ptr [rbp+0E0h+var_140], 1
0x180036c0a  jz      short loc_180036C10
0x180036c0c  bts     ecx, 7
0x180036c10  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x180036c17  xor     edx, edx
0x180036c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c1e  mov     rcx, [rbp+0E0h+Str]
0x180036c22  test    rcx, rcx
0x180036c25  jz      short loc_180036C60
0x180036c27  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x180036c2e  jz      short loc_180036C4A
0x180036c30  mov     r9, [rbp+0E0h+var_160]
0x180036c34  mov     edx, 7D2h; unsigned int
0x180036c39  mov     r8, [rsp+1E0h+var_170+8]
0x180036c3e  mov     ecx, r14d; unsigned int
0x180036c41  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180036c46  mov     rcx, [rbp+0E0h+Str]
0x180036c4a  mov     rax, cs:?gpfnMsiProvideComponentFromDescriptor@@3P6AIPEBGPEAGPEAK2@ZEA; uint (*gpfnMsiProvideComponentFromDescriptor)(ushort const *,ushort *,ulong *,ulong *)
0x180036c51  xor     r9d, r9d
0x180036c54  xor     r8d, r8d
0x180036c57  xor     edx, edx
0x180036c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c5e  jmp     short loc_180036C98
0x180036c60  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x180036c67  jz      short loc_180036C7F
0x180036c69  mov     r9, [rbp+0E0h+var_160]
0x180036c6d  mov     edx, 7D1h; unsigned int
0x180036c72  mov     r8, [rsp+1E0h+var_170+8]
0x180036c77  mov     ecx, r14d; unsigned int
0x180036c7a  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180036c7f  mov     rcx, [rbp+0E0h+var_160+8]
0x180036c83  xor     r9d, r9d
0x180036c86  mov     rax, cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x180036c8d  xor     edx, edx
  ... truncated ...
```
