# CVolumeIdGetter::VolumeIdFromCurrentDriveLetter(wchar_t,wchar_t *,uint)

- ea: `0x18020d5a0`
- end: `0x18020d803`
- name: `?VolumeIdFromCurrentDriveLetter@CVolumeIdGetter@@UEAAJ_WPEA_WI@Z`
- size: `611`
- prototype: `int(CVolumeIdGetter *__hidden this, wchar_t, wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x18005c09c`
- `0x180101db0`
- `0x18010ff58`
- `0x1801244c0`
- `0x18020d448`
- `0x18020d5a0`
- `0x18020d80c`
- `0x18020d864`
- `0x18020d8e0`
- `0x18020d95c`
- `0x18020db4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18020d773`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18020d785`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18020d773`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18020d785`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18020d673`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18020d730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18020d673`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18020d730`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18020d706`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18020d706`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18020d755`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18020d755`

## string_xrefs

- `0x18020d7b9`: `onecoreuap\base\appmodel\search\common\volumeidurl\volumeid.cxx`

## pseudocode

```c
__int64 __fastcall CVolumeIdGetter::VolumeIdFromCurrentDriveLetter(
        CVolumeIdGetter *this,
        wchar_t a2,
        wchar_t *a3,
        unsigned int a4)
{
  __int64 result; // rax
  int VolumeGuidFileHandle; // ebx
  unsigned int v9; // r8d
  __int64 v10; // rdi
  wchar_t *v11; // rbx
  wchar_t *v12; // rax
  bool v13; // [rsp+30h] [rbp-89h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-81h] BYREF
  HANDLE hFile; // [rsp+40h] [rbp-79h] BYREF
  LPCVOID lpBuffer; // [rsp+48h] [rbp-71h] BYREF
  __int64 v17; // [rsp+50h] [rbp-69h]
  __int64 v18; // [rsp+58h] [rbp-61h]
  WCHAR szVolumeMountPoint; // [rsp+60h] [rbp-59h] BYREF
  int v20; // [rsp+62h] [rbp-57h]
  wchar_t v21; // [rsp+66h] [rbp-53h]
  WCHAR szVolumeName[56]; // [rsp+70h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v13 = 0;
  result = CVolumeIdGetter::IsPrimaryDriveLetter(this, a2, &v13);
  if ( (int)result >= 0 )
  {
    if ( v13 )
    {
      v20 = *(_DWORD *)L":\\";
      v21 = asc_180288D08[3];
      szVolumeMountPoint = a2;
      VolumeGuidFileHandle = _EnsureSystemVolumeInformationDirectory(&szVolumeMountPoint);
      if ( VolumeGuidFileHandle >= 0 )
      {
        hObject = 0;
        VolumeGuidFileHandle = _GetVolumeGuidFileHandle(&szVolumeMountPoint, 0x80000000, 3u, &hObject);
        if ( VolumeGuidFileHandle < 0 )
          goto LABEL_27;
        VolumeGuidFileHandle = _GetRawGuidStringFromFile(hObject, szVolumeName, v9);
        if ( VolumeGuidFileHandle >= 0 )
          VolumeGuidFileHandle = _SanitizedVolumeIdFromRawVolumeId(szVolumeName, a3, a4);
        CloseHandle(hObject);
        if ( VolumeGuidFileHandle < 0 )
        {
LABEL_27:
          if ( VolumeGuidFileHandle != -2147024735 )
          {
            hFile = 0;
            if ( (int)_GetVolumeGuidFileHandle(&szVolumeMountPoint, 0x40000000u, 2u, &hFile) < 0 )
              goto LABEL_28;
            lpBuffer = 0;
            v17 = 0;
            v18 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(&lpBuffer);
            v10 = -1;
            v17 = -1;
            v18 = -1;
            VolumeGuidFileHandle = _CreateRawGuidString((LPOLESTR *)&lpBuffer);
            if ( VolumeGuidFileHandle >= 0 )
            {
              LODWORD(hObject) = 0;
              do
                ++v10;
              while ( *((_WORD *)lpBuffer + v10) );
              if ( WriteFile(hFile, lpBuffer, 2 * v10, (LPDWORD)&hObject, 0)
                || (VolumeGuidFileHandle = ResultFromKnownLastError(), VolumeGuidFileHandle >= 0) )
              {
                VolumeGuidFileHandle = _SanitizedVolumeIdFromRawVolumeId((const wchar_t *)lpBuffer, a3, a4);
              }
            }
            CloseHandle(hFile);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(&lpBuffer);
            if ( VolumeGuidFileHandle < 0 )
            {
LABEL_28:
              if ( GetVolumeNameForVolumeMountPointW(&szVolumeMountPoint, szVolumeName, 0x32u)
                || (VolumeGuidFileHandle = ResultFromKnownLastError(), VolumeGuidFileHandle >= 0) )
              {
                v11 = wcschr(szVolumeName, 0x7Bu);
                v12 = wcschr(szVolumeName, 0x7Du);
                if ( v11 && v12 )
                {
                  v12[1] = 0;
                  return (unsigned int)_SanitizedVolumeIdFromRawVolumeId(v11, a3, a4);
                }
                else
                {
                  VolumeGuidFileHandle = -2147467259;
                  wil::details::in1diag3::Log_HrMsg(
                    retaddr,
                    (void *)0x15D,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\volumeidurl\\volumeid.cxx",
                    (const char *)0x80004005LL,
                    (int)"Failed to get volume id for: %ls",
                    (const char *)&szVolumeMountPoint);
                }
              }
            }
          }
        }
      }
      return (unsigned int)VolumeGuidFileHandle;
    }
    else
    {
      return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18020d5a0  mov     [rsp-8+arg_0], rbx
0x18020d5a5  push    rbp
0x18020d5a6  push    rsi
0x18020d5a7  push    rdi
0x18020d5a8  push    r14
0x18020d5aa  push    r15
0x18020d5ac  lea     rbp, [rsp-37h]
0x18020d5b1  sub     rsp, 0F0h
0x18020d5b8  mov     rax, cs:__security_cookie
0x18020d5bf  xor     rax, rsp
0x18020d5c2  mov     [rbp+57h+var_30], rax
0x18020d5c6  mov     rsi, r8
0x18020d5c9  xor     r15d, r15d
0x18020d5cc  lea     r8, [rsp+110h+var_E0]; bool *
0x18020d5d1  mov     [rsp+110h+var_E0], r15b
0x18020d5d6  mov     r14d, r9d
0x18020d5d9  movzx   ebx, dx
0x18020d5dc  call    ?IsPrimaryDriveLetter@CVolumeIdGetter@@AEAAJ_WAEA_N@Z; CVolumeIdGetter::IsPrimaryDriveLetter(wchar_t,bool &)
0x18020d5e1  test    eax, eax
0x18020d5e3  js      loc_18020D7E0
0x18020d5e9  cmp     [rsp+110h+var_E0], r15b
0x18020d5ee  jnz     short loc_18020D5FA
0x18020d5f0  mov     eax, 80070057h
0x18020d5f5  jmp     loc_18020D7E0
0x18020d5fa  mov     eax, dword ptr cs:asc_180288D08+2; ":\\"
0x18020d600  lea     rcx, [rbp+57h+szVolumeMountPoint]; wchar_t *
0x18020d604  mov     [rbp+57h+var_AE], eax
0x18020d607  movzx   eax, word ptr cs:asc_180288D08+6; ""
0x18020d60e  mov     [rbp+57h+var_AA], ax
0x18020d612  mov     [rbp+57h+szVolumeMountPoint], bx
0x18020d616  call    ?_EnsureSystemVolumeInformationDirectory@@YAJPEB_W@Z; _EnsureSystemVolumeInformationDirectory(wchar_t const *)
0x18020d61b  mov     ebx, eax
0x18020d61d  test    eax, eax
0x18020d61f  js      loc_18020D7DE
0x18020d625  lea     r9, [rsp+110h+hObject]; void **
0x18020d62a  mov     [rsp+110h+hObject], r15
0x18020d62f  mov     edx, 80000000h; dwDesiredAccess
0x18020d634  lea     rcx, [rbp+57h+szVolumeMountPoint]; pszPathIn
0x18020d638  mov     r8d, 3; dwCreationDisposition
0x18020d63e  call    ?_GetVolumeGuidFileHandle@@YAJPEB_WKKPEAPEAX@Z; _GetVolumeGuidFileHandle(wchar_t const *,ulong,ulong,void * *)
0x18020d643  mov     ebx, eax
0x18020d645  test    eax, eax
0x18020d647  js      short loc_18020D681
0x18020d649  mov     rcx, [rsp+110h+hObject]; void *
0x18020d64e  lea     rdx, [rbp+57h+szVolumeName]; wchar_t *
0x18020d652  call    ?_GetRawGuidStringFromFile@@YAJPEAXPEA_WI@Z; _GetRawGuidStringFromFile(void *,wchar_t *,uint)
0x18020d657  mov     ebx, eax
0x18020d659  test    eax, eax
0x18020d65b  js      short loc_18020D66E
0x18020d65d  mov     r8d, r14d; unsigned int
0x18020d660  lea     rcx, [rbp+57h+szVolumeName]; wchar_t *
0x18020d664  mov     rdx, rsi; wchar_t *
0x18020d667  call    ?_SanitizedVolumeIdFromRawVolumeId@@YAJPEB_WPEA_WI@Z; _SanitizedVolumeIdFromRawVolumeId(wchar_t const *,wchar_t *,uint)
0x18020d66c  mov     ebx, eax
0x18020d66e  mov     rcx, [rsp+110h+hObject]; hObject
0x18020d673  call    cs:__imp_CloseHandle
0x18020d679  test    ebx, ebx
0x18020d67b  jns     loc_18020D7DE
0x18020d681  cmp     ebx, 800700A1h
0x18020d687  jz      loc_18020D7DE
0x18020d68d  lea     r9, [rbp+57h+hFile]; void **
0x18020d691  mov     [rbp+57h+hFile], r15
0x18020d695  mov     edx, 40000000h; dwDesiredAccess
0x18020d69a  lea     rcx, [rbp+57h+szVolumeMountPoint]; pszPathIn
0x18020d69e  mov     r8d, 2; dwCreationDisposition
0x18020d6a4  call    ?_GetVolumeGuidFileHandle@@YAJPEB_WKKPEAPEAX@Z; _GetVolumeGuidFileHandle(wchar_t const *,ulong,ulong,void * *)
0x18020d6a9  test    eax, eax
0x18020d6ab  js      loc_18020D747
0x18020d6b1  lea     rcx, [rbp+57h+lpBuffer]
0x18020d6b5  mov     [rbp+57h+lpBuffer], r15
0x18020d6b9  mov     [rbp+57h+var_C0], r15
0x18020d6bd  mov     [rbp+57h+var_B8], r15
0x18020d6c1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(void)
0x18020d6c6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18020d6ca  lea     rcx, [rbp+57h+lpBuffer]; lplpsz
0x18020d6ce  mov     [rbp+57h+var_C0], rdi
0x18020d6d2  mov     [rbp+57h+var_B8], rdi
0x18020d6d6  call    ?_CreateRawGuidString@@YAJPEAPEA_W@Z; _CreateRawGuidString(wchar_t * *)
0x18020d6db  mov     ebx, eax
0x18020d6dd  test    eax, eax
0x18020d6df  js      short loc_18020D72C
0x18020d6e1  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x18020d6e5  mov     dword ptr [rsp+110h+hObject], r15d
0x18020d6ea  inc     rdi
0x18020d6ed  cmp     [rdx+rdi*2], r15w
0x18020d6f2  jnz     short loc_18020D6EA
0x18020d6f4  mov     rcx, [rbp+57h+hFile]; hFile
0x18020d6f8  lea     r8d, [rdi+rdi]; nNumberOfBytesToWrite
0x18020d6fc  lea     r9, [rsp+110h+hObject]; lpNumberOfBytesWritten
0x18020d701  mov     [rsp+110h+lpOverlapped], r15; lpOverlapped
0x18020d706  call    cs:__imp_WriteFile
0x18020d70c  test    eax, eax
0x18020d70e  jnz     short loc_18020D71B
0x18020d710  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18020d715  mov     ebx, eax
0x18020d717  test    eax, eax
0x18020d719  js      short loc_18020D72C
0x18020d71b  mov     rcx, [rbp+57h+lpBuffer]; wchar_t *
0x18020d71f  mov     r8d, r14d; unsigned int
0x18020d722  mov     rdx, rsi; wchar_t *
0x18020d725  call    ?_SanitizedVolumeIdFromRawVolumeId@@YAJPEB_WPEA_WI@Z; _SanitizedVolumeIdFromRawVolumeId(wchar_t const *,wchar_t *,uint)
0x18020d72a  mov     ebx, eax
0x18020d72c  mov     rcx, [rbp+57h+hFile]; hObject
0x18020d730  call    cs:__imp_CloseHandle
0x18020d736  lea     rcx, [rbp+57h+lpBuffer]
0x18020d73a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(void)
0x18020d73f  test    ebx, ebx
0x18020d741  jns     loc_18020D7DE
0x18020d747  mov     r8d, 32h ; '2'; cchBufferLength
0x18020d74d  lea     rdx, [rbp+57h+szVolumeName]; lpszVolumeName
0x18020d751  lea     rcx, [rbp+57h+szVolumeMountPoint]; lpszVolumeMountPoint
0x18020d755  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18020d75b  test    eax, eax
0x18020d75d  jnz     short loc_18020D76A
0x18020d75f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18020d764  mov     ebx, eax
0x18020d766  test    eax, eax
0x18020d768  js      short loc_18020D7DE
0x18020d76a  mov     edx, 7Bh ; '{'; Ch
0x18020d76f  lea     rcx, [rbp+57h+szVolumeName]; Str
0x18020d773  call    cs:__imp_wcschr
0x18020d779  mov     edx, 7Dh ; '}'; Ch
0x18020d77e  lea     rcx, [rbp+57h+szVolumeName]; Str
0x18020d782  mov     rbx, rax
0x18020d785  call    cs:__imp_wcschr
0x18020d78b  test    rbx, rbx
0x18020d78e  jz      short loc_18020D7AC
0x18020d790  test    rax, rax
0x18020d793  jz      short loc_18020D7AC
0x18020d795  mov     r8d, r14d; unsigned int
0x18020d798  mov     [rax+2], r15w
0x18020d79d  mov     rdx, rsi; wchar_t *
0x18020d7a0  mov     rcx, rbx; wchar_t *
0x18020d7a3  call    ?_SanitizedVolumeIdFromRawVolumeId@@YAJPEB_WPEA_WI@Z; _SanitizedVolumeIdFromRawVolumeId(wchar_t const *,wchar_t *,uint)
0x18020d7a8  mov     ebx, eax
0x18020d7aa  jmp     short loc_18020D7DE
0x18020d7ac  mov     rcx, [rbp+5Fh]; this
0x18020d7b0  lea     rax, [rbp+57h+szVolumeMountPoint]
0x18020d7b4  mov     [rsp+110h+var_E8], rax; char *
0x18020d7b9  lea     r8, aOnecoreuapBase_226; "onecoreuap\\base\\appmodel\\search\\com"...
0x18020d7c0  lea     rax, aFailedToGetVol; "Failed to get volume id for: %ls"
0x18020d7c7  mov     ebx, 80004005h
0x18020d7cc  mov     r9d, ebx; char *
0x18020d7cf  mov     [rsp+110h+lpOverlapped], rax; int
0x18020d7d4  mov     edx, 15Dh; void *
0x18020d7d9  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18020d7de  mov     eax, ebx
0x18020d7e0  mov     rcx, [rbp+57h+var_30]
0x18020d7e4  xor     rcx, rsp; StackCookie
0x18020d7e7  call    __security_check_cookie
0x18020d7ec  mov     rbx, [rsp+110h+arg_0]
0x18020d7f4  add     rsp, 0F0h
0x18020d7fb  pop     r15
0x18020d7fd  pop     r14
0x18020d7ff  pop     rdi
0x18020d800  pop     rsi
0x18020d801  pop     rbp
0x18020d802  retn
```
