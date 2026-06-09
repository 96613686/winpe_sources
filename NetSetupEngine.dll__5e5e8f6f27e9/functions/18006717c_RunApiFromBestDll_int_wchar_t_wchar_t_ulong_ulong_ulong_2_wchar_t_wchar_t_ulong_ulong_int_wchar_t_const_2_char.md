# RunApiFromBestDll<int (wchar_t *,wchar_t *,ulong,ulong *,ulong),2,wchar_t * &,wchar_t *,ulong &,ulong *,int>(wchar_t const * (&)[2],char const *,FailurePolicy,wchar_t * &,wchar_t * &&,ulong &,ulong * &&,int &&)

- ea: `0x18006717c`
- end: `0x18006736d`
- name: `??$RunApiFromBestDll@$$A6AHPEA_W0KPEAKK@Z$01AEAPEA_WPEA_WAEAKPEAKH@@YAHAEAY01QEB_WPEBDW4FailurePolicy@@AEAPEA_W$$QEAPEA_WAEAK$$QEAPEAK$$QEAH@Z`
- size: `497`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *, _QWORD *, unsigned int *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001e110`

## callees

- `0x18001dee8`
- `0x18005097c`
- `0x18005b188`
- `0x180065035`
- `0x18006717c`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800672fb`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800672fb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180067275`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180067275`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800671e1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800671e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800671ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800671ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067236`

## pseudocode

```c
__int64 __fastcall RunApiFromBestDll<int (wchar_t *,wchar_t *,unsigned long,unsigned long *,unsigned long),2,wchar_t * &,wchar_t *,unsigned long &,unsigned long *,int>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        unsigned int *a6,
        _QWORD *a7,
        _DWORD *a8)
{
  wchar_t **i; // rbx
  wchar_t *v10; // rsi
  HMODULE Library; // rax
  HMODULE v12; // rdi
  DWORD LastError; // eax
  signed int v14; // eax
  FARPROC ProcAddress; // rax
  unsigned int v16; // ebx
  _BYTE pExceptionObject[280]; // [rsp+40h] [rbp-118h] BYREF

  for ( i = off_180090140; ; ++i )
  {
    if ( i == off_180090150 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids,
          "SpInfGetIndirectString");
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024770);
      throw (HResultException *)pExceptionObject;
    }
    v10 = *i;
    Library = LoadLibraryExW(*i, 0, 0x800u);
    v12 = Library;
    if ( Library )
      break;
    LastError = GetLastError();
    if ( LastError != 2 && LastError != 126 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids, v10);
      v14 = GetLastError();
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, v14);
      throw (HResultException *)pExceptionObject;
    }
  }
  ProcAddress = GetProcAddress(Library, "SpInfGetIndirectString");
  if ( !ProcAddress )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids,
        "SpInfGetIndirectString");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024769);
    throw (HResultException *)pExceptionObject;
  }
  v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))ProcAddress)(*a4, *a5, *a6, *a7, *a8);
  FreeLibrary(v12);
  return v16;
}

```

## disassembly

```asm
0x18006717c  push    rbx
0x18006717e  push    rbp
0x18006717f  push    rsi
0x180067180  push    rdi
0x180067181  push    r12
0x180067183  push    r13
0x180067185  push    r14
0x180067187  push    r15
0x180067189  sub     rsp, 118h
0x180067190  mov     [rsp+158h+var_128], 0FFFFFFFFFFFFFFFEh
0x180067199  mov     r14, r9
0x18006719c  mov     r15, [rsp+158h+arg_20]
0x1800671a4  mov     rbp, [rsp+158h+arg_28]
0x1800671ac  mov     r12, [rsp+158h+arg_30]
0x1800671b4  mov     r13, [rsp+158h+arg_38]
0x1800671bc  lea     rbx, off_180090140; "ext-ms-win-spinf-inf-l1-1-0.dll"
0x1800671c3  lea     rax, off_180090150; "api-ms-win-core-localization-private-l1"...
0x1800671ca  cmp     rbx, rax
0x1800671cd  jz      loc_180067317
0x1800671d3  mov     rsi, [rbx]
0x1800671d6  xor     edx, edx; hFile
0x1800671d8  mov     r8d, 800h; dwFlags
0x1800671de  mov     rcx, rsi; lpLibFileName
0x1800671e1  call    cs:__imp_LoadLibraryExW
0x1800671e7  mov     rdi, rax
0x1800671ea  test    rax, rax
0x1800671ed  jnz     short loc_180067266
0x1800671ef  call    cs:__imp_GetLastError
0x1800671f5  cmp     eax, 2
0x1800671f8  jz      short loc_1800671FF
0x1800671fa  cmp     eax, 7Eh ; '~'
0x1800671fd  jnz     short loc_180067205
0x1800671ff  add     rbx, 8
0x180067203  jmp     short loc_1800671C3
0x180067205  lea     rax, WPP_GLOBAL_Control
0x18006720c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067213  cmp     rcx, rax
0x180067216  jz      short loc_180067236
0x180067218  cmp     byte ptr [rcx+19h], 2
0x18006721c  jb      short loc_180067236
0x18006721e  mov     edx, 0Ch
0x180067223  mov     r9, rsi
0x180067226  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x18006722d  mov     rcx, [rcx+10h]
0x180067231  call    WPP_SF_S
0x180067236  call    cs:__imp_GetLastError
0x18006723c  test    eax, eax
0x18006723e  jle     short loc_180067248
0x180067240  movzx   eax, ax
0x180067243  or      eax, 80070000h
0x180067248  mov     edx, eax; int
0x18006724a  lea     rcx, [rsp+158h+pExceptionObject]; this
0x18006724f  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180067254  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18006725b  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180067260  call    _CxxThrowException_0
0x180067266  mov     [rsp+158h+var_120], rdi
0x18006726b  lea     rdx, aSpinfgetindire; "SpInfGetIndirectString"
0x180067272  mov     rcx, rdi; hModule
0x180067275  call    cs:__imp_GetProcAddress
0x18006727b  mov     r10, rax
0x18006727e  test    rax, rax
0x180067281  jnz     short loc_1800672D8
0x180067283  lea     rax, WPP_GLOBAL_Control
0x18006728a  mov     rcx, cs:WPP_GLOBAL_Control
0x180067291  cmp     rcx, rax
0x180067294  jz      short loc_1800672B7
0x180067296  cmp     byte ptr [rcx+19h], 2
0x18006729a  jb      short loc_1800672B7
0x18006729c  lea     edx, [r10+0Bh]
0x1800672a0  lea     r9, aSpinfgetindire; "SpInfGetIndirectString"
0x1800672a7  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x1800672ae  mov     rcx, [rcx+10h]
0x1800672b2  call    WPP_SF_s
0x1800672b7  mov     edx, 8007007Fh; int
0x1800672bc  lea     rcx, [rsp+158h+pExceptionObject]; this
0x1800672c1  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800672c6  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800672cd  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x1800672d2  call    _CxxThrowException_0
0x1800672d8  mov     eax, [r13+0]
0x1800672dc  mov     [rsp+158h+var_138], eax
0x1800672e0  mov     r9, [r12]
0x1800672e4  mov     r8d, [rbp+0]
0x1800672e8  mov     rdx, [r15]
0x1800672eb  mov     rcx, [r14]
0x1800672ee  mov     rax, r10
0x1800672f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672f6  mov     ebx, eax
0x1800672f8  mov     rcx, rdi; hLibModule
0x1800672fb  call    cs:__imp_FreeLibrary
0x180067301  mov     eax, ebx
0x180067303  add     rsp, 118h
0x18006730a  pop     r15
0x18006730c  pop     r14
0x18006730e  pop     r13
0x180067310  pop     r12
0x180067312  pop     rdi
0x180067313  pop     rsi
0x180067314  pop     rbp
0x180067315  pop     rbx
0x180067316  retn
0x180067317  lea     rax, WPP_GLOBAL_Control
0x18006731e  mov     rcx, cs:WPP_GLOBAL_Control
0x180067325  cmp     rcx, rax
0x180067328  jz      short loc_18006734C
0x18006732a  cmp     byte ptr [rcx+19h], 2
0x18006732e  jb      short loc_18006734C
0x180067330  mov     edx, 0Dh
0x180067335  lea     r9, aSpinfgetindire; "SpInfGetIndirectString"
0x18006733c  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x180067343  mov     rcx, [rcx+10h]
0x180067347  call    WPP_SF_s
0x18006734c  mov     edx, 8007007Eh; int
0x180067351  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180067356  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18006735b  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180067362  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180067367  call    _CxxThrowException_0
```
