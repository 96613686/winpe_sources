# MsiSIPPutSignedDataMsg(SIP_SUBJECTINFO_ *,ulong,ulong *,ulong,uchar *)

- ea: `0x180001f20`
- end: `0x18000229e`
- name: `?MsiSIPPutSignedDataMsg@@YAHPEAUSIP_SUBJECTINFO_@@KPEAKKPEAE@Z`
- size: `894`
- prototype: `__int64 __fastcall(struct SIP_SUBJECTINFO_ *, __int64, unsigned int *, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001f20`
- `0x180003340`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180001f95`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180002016`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000205f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180002089`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180002174`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180001f95`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180002016`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000205f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180002089`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180002174`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180001fd1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180002072`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180002187`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180001fd1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180002072`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180002187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002141`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001fc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001fe0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002042`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000212c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002269`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002292`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001fc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001fe0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002042`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000212c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002269`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002292`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021e9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180001f7d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180001f7d`

## string_xrefs

- `0x180001f76`: `ole32.dll`
- `0x18000207f`: `StgOpenStorage`

## pseudocode

```c
__int64 __fastcall MsiSIPPutSignedDataMsg(
        struct SIP_SUBJECTINFO_ *a1,
        __int64 a2,
        unsigned int *a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  HMODULE LibraryW; // rax
  HMODULE v9; // rdi
  FARPROC ProcAddress; // rax
  int v11; // esi
  DWORD LastError; // ebx
  DWORD v13; // ecx
  bool v15; // si
  GUID *pgSubjectType; // rbp
  FARPROC v17; // rax
  DWORD v18; // ebx
  void (*v19)(void); // rax
  FARPROC v20; // rax
  __int64 v21; // rbx
  DWORD v22; // ebp
  unsigned int v23; // r14d
  void (*v24)(void); // rax
  char *hFile; // rcx
  __int64 v26; // [rsp+40h] [rbp-48h] BYREF
  __int64 v27; // [rsp+48h] [rbp-40h]
  __int64 v28; // [rsp+50h] [rbp-38h]
  __int64 v29; // [rsp+90h] [rbp+8h] BYREF

  v28 = -2;
  if ( !a1 || !a3 || !a5 || !a4 || a1->cbSize < 0x58 )
  {
    v13 = 87;
    goto LABEL_13;
  }
  *a3 = 0;
  LibraryW = LoadLibraryW(L"ole32.dll");
  v9 = LibraryW;
  if ( !LibraryW )
    return 0;
  ProcAddress = GetProcAddress(LibraryW, "CoInitialize");
  if ( !ProcAddress )
  {
LABEL_11:
    LastError = GetLastError();
    FreeLibrary(v9);
    v13 = LastError;
LABEL_13:
    SetLastError(v13);
    return 0;
  }
  v11 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
  if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147417850 )
  {
    SetLastError((unsigned __int16)v11);
    goto LABEL_11;
  }
  v15 = v11 >= 0;
  pgSubjectType = a1->pgSubjectType;
  v17 = GetProcAddress(v9, "IsEqualGUID");
  if ( !v17 )
  {
LABEL_19:
    v18 = GetLastError();
    if ( v15 )
    {
      v19 = (void (*)(void))GetProcAddress(v9, "CoUninitialize");
      if ( v19 )
        v19();
    }
    FreeLibrary(v9);
    v13 = v18;
    goto LABEL_13;
  }
  if ( !pgSubjectType || !((unsigned int (__fastcall *)(GUID *, GUID *))v17)(pgSubjectType, &gMSI) )
  {
    SetLastError(0x800B0003);
    goto LABEL_19;
  }
  hFile = (char *)a1->hFile;
  if ( (unsigned __int64)(hFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(hFile);
    a1->hFile = 0;
  }
  v20 = GetProcAddress(v9, "StgOpenStorage");
  if ( !v20 )
    goto LABEL_39;
  v29 = 0;
  if ( ((int (__fastcall *)(LPCWSTR, _QWORD, __int64, _QWORD, _DWORD, __int64 *))v20)(
         a1->pwsFileName,
         0,
         65569,
         0,
         0,
         &v29) < 0
    || (v21 = v29) == 0 )
  {
    SetLastError(0xBu);
LABEL_39:
    v21 = 0;
  }
  v27 = v21;
  if ( !v21 )
    goto LABEL_30;
  *a3 = 0;
  v26 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64 *, __int64, _QWORD, _DWORD, __int64 *))(*(_QWORD *)v21 + 24LL))(
         v21,
         qword_18000F930,
         4113,
         0,
         0,
         &v26) < 0
    || !v26 )
  {
    SetLastError(0xBu);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
LABEL_30:
    v22 = GetLastError();
    v23 = 0;
    if ( !v21 )
      goto LABEL_32;
    goto LABEL_31;
  }
  LODWORD(v29) = 0;
  if ( (*(int (__fastcall **)(__int64, unsigned __int8 *, _QWORD, __int64 *))(*(_QWORD *)v26 + 32LL))(v26, a5, a4, &v29) < 0
    || a4 != (_DWORD)v29 )
  {
    SetLastError(0xBu);
    goto LABEL_50;
  }
  v23 = 1;
  if ( (*(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 64LL))(v26, 1) < 0 )
  {
LABEL_50:
    CComPointer<IStream>::~CComPointer<IStream>(&v26);
    goto LABEL_30;
  }
  CComPointer<IStream>::~CComPointer<IStream>(&v26);
  if ( (*(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 72LL))(v21, 1) < 0 )
    goto LABEL_30;
  v22 = 0;
LABEL_31:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_32:
  v27 = 0;
  if ( v15 )
  {
    v24 = (void (*)(void))GetProcAddress(v9, "CoUninitialize");
    if ( v24 )
      v24();
  }
  FreeLibrary(v9);
  if ( v22 )
    SetLastError(v22);
  return v23;
}

```

## disassembly

```asm
0x180001f20  mov     rax, rsp
0x180001f23  push    rsi
0x180001f24  push    rdi
0x180001f25  push    r12
0x180001f27  push    r13
0x180001f29  push    r14
0x180001f2b  sub     rsp, 60h
0x180001f2f  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001f37  mov     [rax+10h], rbx
0x180001f3b  mov     [rax+18h], rbp
0x180001f3f  mov     r12d, r9d
0x180001f42  mov     r14, r8
0x180001f45  mov     rbx, rcx
0x180001f48  test    rcx, rcx
0x180001f4b  jz      loc_180001FDB
0x180001f51  test    r8, r8
0x180001f54  jz      loc_180001FDB
0x180001f5a  cmp     [rsp+88h+arg_20], 0
0x180001f63  jz      short loc_180001FDB
0x180001f65  cmp     r9d, 1
0x180001f69  jb      short loc_180001FDB
0x180001f6b  cmp     dword ptr [rcx], 58h ; 'X'
0x180001f6e  jb      short loc_180001FDB
0x180001f70  xor     r13d, r13d
0x180001f73  mov     [r8], r13d
0x180001f76  lea     rcx, LibFileName; "ole32.dll"
0x180001f7d  call    cs:__imp_LoadLibraryW
0x180001f83  mov     rdi, rax
0x180001f86  test    rax, rax
0x180001f89  jz      short loc_180001FE6
0x180001f8b  lea     rdx, aCoinitialize; "CoInitialize"
0x180001f92  mov     rcx, rax; hModule
0x180001f95  call    cs:__imp_GetProcAddress
0x180001f9b  test    rax, rax
0x180001f9e  jz      short loc_180001FC6
0x180001fa0  xor     ecx, ecx
0x180001fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fa7  mov     esi, eax
0x180001fa9  mov     eax, 80000000h
0x180001fae  lea     ecx, [rsi+rax]
0x180001fb1  test    eax, ecx
0x180001fb3  jnz     short loc_180002001
0x180001fb5  cmp     esi, 80010106h
0x180001fbb  jz      short loc_180002001
0x180001fbd  movzx   ecx, si; dwErrCode
0x180001fc0  call    cs:__imp_SetLastError
0x180001fc6  call    cs:__imp_GetLastError
0x180001fcc  mov     ebx, eax
0x180001fce  mov     rcx, rdi; hLibModule
0x180001fd1  call    cs:__imp_FreeLibrary
0x180001fd7  mov     ecx, ebx
0x180001fd9  jmp     short loc_180001FE0
0x180001fdb  mov     ecx, 57h ; 'W'; dwErrCode
0x180001fe0  call    cs:__imp_SetLastError
0x180001fe6  xor     eax, eax
0x180001fe8  lea     r11, [rsp+88h+var_28]
0x180001fed  mov     rbx, [r11+38h]
0x180001ff1  mov     rbp, [r11+40h]
0x180001ff5  mov     rsp, r11
0x180001ff8  pop     r14
0x180001ffa  pop     r13
0x180001ffc  pop     r12
0x180001ffe  pop     rdi
0x180001fff  pop     rsi
0x180002000  retn
0x180002001  shr     esi, 1Fh
0x180002004  xor     sil, 1
0x180002008  mov     rbp, [rbx+8]
0x18000200c  lea     rdx, aIsequalguid; "IsEqualGUID"
0x180002013  mov     rcx, rdi; hModule
0x180002016  call    cs:__imp_GetProcAddress
0x18000201c  test    rax, rax
0x18000201f  jz      short loc_180002048
0x180002021  test    rbp, rbp
0x180002024  jz      short loc_18000203D
0x180002026  lea     rdx, ?gMSI@@3U_GUID@@A; _GUID gMSI
0x18000202d  mov     rcx, rbp
0x180002030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002035  test    eax, eax
0x180002037  jnz     loc_1800021D7
0x18000203d  mov     ecx, 800B0003h; dwErrCode
0x180002042  call    cs:__imp_SetLastError
0x180002048  call    cs:__imp_GetLastError
0x18000204e  mov     ebx, eax
0x180002050  test    sil, sil
0x180002053  jz      short loc_18000206F
0x180002055  lea     rdx, ProcName; "CoUninitialize"
0x18000205c  mov     rcx, rdi; hModule
0x18000205f  call    cs:__imp_GetProcAddress
0x180002065  test    rax, rax
0x180002068  jz      short loc_18000206F
0x18000206a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000206f  mov     rcx, rdi; hLibModule
0x180002072  call    cs:__imp_FreeLibrary
0x180002078  mov     ecx, ebx
0x18000207a  jmp     loc_180001FE0
0x18000207f  lea     rdx, aStgopenstorage; "StgOpenStorage"
0x180002086  mov     rcx, rdi; hModule
0x180002089  call    cs:__imp_GetProcAddress
0x18000208f  test    rax, rax
0x180002092  jz      loc_1800021A8
0x180002098  mov     [rsp+88h+arg_0], r13
0x1800020a0  lea     rcx, [rsp+88h+arg_0]
0x1800020a8  mov     [rsp+88h+var_60], rcx
0x1800020ad  mov     [rsp+88h+var_68], r13d
0x1800020b2  xor     r9d, r9d
0x1800020b5  xor     edx, edx
0x1800020b7  mov     r8d, 10021h
0x1800020bd  mov     rcx, [rbx+18h]
0x1800020c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c6  test    eax, eax
0x1800020c8  js      loc_18000219D
0x1800020ce  mov     rbx, [rsp+88h+arg_0]
0x1800020d6  test    rbx, rbx
0x1800020d9  jz      loc_18000219D
0x1800020df  mov     [rsp+88h+var_40], rbx
0x1800020e4  test    rbx, rbx
0x1800020e7  jz      short loc_180002141
0x1800020e9  mov     [r14], r13d
0x1800020ec  mov     [rsp+88h+var_48], r13
0x1800020f1  mov     rax, [rbx]
0x1800020f4  lea     rcx, [rsp+88h+var_48]
0x1800020f9  mov     [rsp+88h+var_60], rcx
0x1800020fe  mov     [rsp+88h+var_68], r13d
0x180002103  xor     r9d, r9d
0x180002106  mov     r8d, 1011h
0x18000210c  lea     rdx, qword_18000F930
0x180002113  mov     rcx, rbx
0x180002116  mov     rax, [rax+18h]
0x18000211a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000211f  test    eax, eax
0x180002121  jns     loc_1800021F8
0x180002127  mov     ecx, 0Bh; dwErrCode
0x18000212c  call    cs:__imp_SetLastError
0x180002132  nop
0x180002133  mov     rcx, [rsp+88h+var_48]
0x180002138  test    rcx, rcx
0x18000213b  jnz     loc_18000227F
0x180002141  call    cs:__imp_GetLastError
0x180002147  mov     ebp, eax
0x180002149  mov     r14d, r13d
0x18000214c  test    rbx, rbx
0x18000214f  jz      short loc_180002160
0x180002151  mov     rcx, [rbx]
0x180002154  mov     rax, [rcx+10h]
0x180002158  mov     rcx, rbx
0x18000215b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002160  mov     [rsp+88h+var_40], r13
0x180002165  test    sil, sil
0x180002168  jz      short loc_180002184
0x18000216a  lea     rdx, ProcName; "CoUninitialize"
0x180002171  mov     rcx, rdi; hModule
0x180002174  call    cs:__imp_GetProcAddress
0x18000217a  test    rax, rax
0x18000217d  jz      short loc_180002184
0x18000217f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002184  mov     rcx, rdi; hLibModule
0x180002187  call    cs:__imp_FreeLibrary
0x18000218d  test    ebp, ebp
0x18000218f  jnz     loc_180002290
0x180002195  mov     eax, r14d
0x180002198  jmp     loc_180001FE8
0x18000219d  mov     ecx, 0Bh; dwErrCode
0x1800021a2  call    cs:__imp_SetLastError
0x1800021a8  mov     rbx, r13
0x1800021ab  jmp     loc_1800020DF
0x1800021b0  call    ??1?$CComPointer@UIStream@@@@QEAA@XZ; CComPointer<IStream>::~CComPointer<IStream>(void)
0x1800021b5  mov     rax, [rbx]
0x1800021b8  mov     edx, r14d
0x1800021bb  mov     rcx, rbx
0x1800021be  mov     rax, [rax+48h]
0x1800021c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021c7  test    eax, eax
0x1800021c9  js      loc_180002141
0x1800021cf  mov     ebp, r13d
0x1800021d2  jmp     loc_180002151
0x1800021d7  mov     rcx, [rbx+10h]; hObject
0x1800021db  lea     rax, [rcx-1]
0x1800021df  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800021e3  ja      loc_18000207F
0x1800021e9  call    cs:__imp_CloseHandle
0x1800021ef  mov     [rbx+10h], r13
0x1800021f3  jmp     loc_18000207F
0x1800021f8  mov     rcx, [rsp+88h+var_48]
0x1800021fd  test    rcx, rcx
0x180002200  jz      loc_180002127
0x180002206  mov     dword ptr [rsp+88h+arg_0], r13d
0x18000220e  mov     rax, [rcx]
0x180002211  lea     r9, [rsp+88h+arg_0]
0x180002219  mov     r8d, r12d
0x18000221c  mov     rdx, [rsp+88h+arg_20]
0x180002224  mov     rax, [rax+20h]
0x180002228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000222d  test    eax, eax
0x18000222f  js      short loc_180002264
0x180002231  cmp     r12d, dword ptr [rsp+88h+arg_0]
0x180002239  jnz     short loc_180002264
0x18000223b  mov     rcx, [rsp+88h+var_48]
0x180002240  mov     rax, [rcx]
0x180002243  mov     r14d, 1
0x180002249  mov     edx, r14d
0x18000224c  mov     rax, [rax+40h]
0x180002250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002255  nop
0x180002256  lea     rcx, [rsp+88h+var_48]
0x18000225b  test    eax, eax
0x18000225d  js      short loc_180002275
0x18000225f  jmp     loc_1800021B0
0x180002264  mov     ecx, 0Bh; dwErrCode
0x180002269  call    cs:__imp_SetLastError
0x18000226f  nop
0x180002270  lea     rcx, [rsp+88h+var_48]
0x180002275  call    ??1?$CComPointer@UIStream@@@@QEAA@XZ; CComPointer<IStream>::~CComPointer<IStream>(void)
0x18000227a  jmp     loc_180002141
0x18000227f  mov     rax, [rcx]
0x180002282  mov     rax, [rax+10h]
0x180002286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000228b  jmp     loc_180002141
0x180002290  mov     ecx, ebp; dwErrCode
0x180002292  call    cs:__imp_SetLastError
0x180002298  jmp     loc_180002195
```
