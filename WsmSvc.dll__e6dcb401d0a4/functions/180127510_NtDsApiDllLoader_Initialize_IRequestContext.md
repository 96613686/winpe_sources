# NtDsApiDllLoader::Initialize(IRequestContext &)

- ea: `0x180127510`
- end: `0x1801276df`
- name: `?Initialize@NtDsApiDllLoader@@UEAA_NAEAVIRequestContext@@@Z`
- size: `463`
- prototype: `char __fastcall(NtDsApiDllLoader *this, struct IRequestContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180014990`
- `0x1800870f0`
- `0x180112380`
- `0x180127510`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180127587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180127587`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180127633`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180127650`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18012766d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18012768a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801276a7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180127633`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180127650`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18012766d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18012768a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801276a7`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18012760b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18012760b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180127574`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180127574`

## string_xrefs

- `0x1801275c6`: `Ntdsapi.dll`
- `0x1801275b9`: `\Ntdsapi.dll`
- `0x180127666`: `DsWriteAccountSpnW`

## pseudocode

```c
char __fastcall NtDsApiDllLoader::Initialize(NtDsApiDllLoader *this, struct IRequestContext *a2)
{
  void (__fastcall *v4)(struct IRequestContext *, __int64); // rbx
  __int64 LastError; // rdx
  __int64 v7; // rax
  const unsigned __int16 *v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  HMODULE Library; // rax
  HMODULE *v12; // rsi
  FARPROC ProcAddress; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_98aa05c4e0903ffb820b490c0a8da906_Traceguids);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_5;
  v7 = -1;
  do
    ++v7;
  while ( Buffer[v7] );
  v8 = L"Ntdsapi.dll";
  if ( Buffer[v7 - 1] != 92 )
    v8 = L"\\Ntdsapi.dll";
  v9 = StringCchCatW(Buffer, 0x104u, v8);
  v10 = (unsigned int)v9;
  if ( v9 < 0 )
  {
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v10 = (unsigned __int16)v9;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v10);
    return 0;
  }
  Library = LoadLibraryExW(Buffer, 0, 0);
  v12 = (HMODULE *)((char *)this + 8);
  AutoCleanup<AutoLibrary,HINSTANCE__ *>::operator=((char *)this + 8, Library);
  if ( !*((_QWORD *)this + 1) )
    goto LABEL_5;
  ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "DsBindW");
  *((_QWORD *)this + 2) = ProcAddress;
  if ( !ProcAddress )
    goto LABEL_5;
  v14 = GetProcAddress(*v12, "DsCrackNamesW");
  *((_QWORD *)this + 3) = v14;
  if ( !v14
    || (v15 = GetProcAddress(*v12, "DsWriteAccountSpnW"), (*((_QWORD *)this + 4) = v15) == 0)
    || (v16 = GetProcAddress(*v12, "DsFreeNameResultW"), (*((_QWORD *)this + 5) = v16) == 0)
    || (v17 = GetProcAddress(*v12, "DsUnBindW"), (*((_QWORD *)this + 6) = v17) == 0) )
  {
LABEL_5:
    v4 = *(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL);
    LastError = GetLastError();
    v4(a2, LastError);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180127510  mov     [rsp+arg_10], rbx
0x180127515  push    rbp
0x180127516  push    rsi
0x180127517  push    rdi
0x180127518  sub     rsp, 240h
0x18012751f  mov     rax, cs:__security_cookie
0x180127526  xor     rax, rsp
0x180127529  mov     [rsp+258h+var_28], rax
0x180127531  mov     rdi, rdx
0x180127534  mov     rbx, rcx
0x180127537  mov     rcx, cs:WPP_GLOBAL_Control
0x18012753e  lea     rax, WPP_GLOBAL_Control
0x180127545  cmp     rcx, rax
0x180127548  jz      short loc_180127568
0x18012754a  test    dword ptr [rcx+1Ch], 1000000h
0x180127551  jz      short loc_180127568
0x180127553  mov     rcx, [rcx+10h]
0x180127557  lea     r8, WPP_98aa05c4e0903ffb820b490c0a8da906_Traceguids
0x18012755e  mov     edx, 63h ; 'c'
0x180127563  call    WPP_SF_
0x180127568  mov     esi, 104h
0x18012756d  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180127572  mov     edx, esi; uSize
0x180127574  call    cs:__imp_GetSystemDirectoryW
0x18012757a  xor     ebp, ebp
0x18012757c  test    eax, eax
0x18012757e  jnz     short loc_1801275A1
0x180127580  mov     rax, [rdi]
0x180127583  mov     rbx, [rax+48h]
0x180127587  call    cs:__imp_GetLastError
0x18012758d  mov     edx, eax
0x18012758f  mov     rax, rbx
0x180127592  mov     rcx, rdi
0x180127595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012759a  xor     al, al
0x18012759c  jmp     loc_1801276BC
0x1801275a1  lea     rcx, [rsp+258h+Buffer]
0x1801275a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801275aa  inc     rax
0x1801275ad  cmp     [rcx+rax*2], bp
0x1801275b1  jnz     short loc_1801275AA
0x1801275b3  mov     r9d, 5Ch ; '\'
0x1801275b9  lea     rcx, aNtdsapiDll; "\\Ntdsapi.dll"
0x1801275c0  cmp     r9w, [rsp+rax*2+258h+var_23A]
0x1801275c6  lea     r8, aNtdsapiDll_0; "Ntdsapi.dll"
0x1801275cd  mov     rdx, rsi; unsigned __int64
0x1801275d0  cmovnz  r8, rcx; unsigned __int16 *
0x1801275d4  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x1801275d9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801275de  mov     edx, eax
0x1801275e0  test    eax, eax
0x1801275e2  jns     short loc_180127601
0x1801275e4  mov     rax, [rdi]
0x1801275e7  mov     r8, [rax+48h]
0x1801275eb  mov     eax, edx
0x1801275ed  and     eax, 1FFF0000h
0x1801275f2  cmp     eax, 70000h
0x1801275f7  jnz     short loc_1801275FC
0x1801275f9  movzx   edx, dx
0x1801275fc  mov     rax, r8
0x1801275ff  jmp     short loc_180127592
0x180127601  xor     r8d, r8d; dwFlags
0x180127604  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x180127609  xor     edx, edx; hFile
0x18012760b  call    cs:__imp_LoadLibraryExW
0x180127611  lea     rsi, [rbx+8]
0x180127615  mov     rdx, rax
0x180127618  mov     rcx, rsi
0x18012761b  call    ??4?$AutoCleanup@VAutoLibrary@@PEAUHINSTANCE__@@@@QEAAAEAVAutoLibrary@@PEAUHINSTANCE__@@@Z; AutoCleanup<AutoLibrary,HINSTANCE__ *>::operator=(HINSTANCE__ *)
0x180127620  mov     rcx, [rsi]; hModule
0x180127623  test    rcx, rcx
0x180127626  jz      loc_180127580
0x18012762c  lea     rdx, aDsbindw; "DsBindW"
0x180127633  call    cs:__imp_GetProcAddress
0x180127639  mov     [rbx+10h], rax
0x18012763d  test    rax, rax
0x180127640  jz      loc_180127580
0x180127646  mov     rcx, [rsi]; hModule
0x180127649  lea     rdx, aDscracknamesw; "DsCrackNamesW"
0x180127650  call    cs:__imp_GetProcAddress
0x180127656  mov     [rbx+18h], rax
0x18012765a  test    rax, rax
0x18012765d  jz      loc_180127580
0x180127663  mov     rcx, [rsi]; hModule
0x180127666  lea     rdx, aDswriteaccount; "DsWriteAccountSpnW"
0x18012766d  call    cs:__imp_GetProcAddress
0x180127673  mov     [rbx+20h], rax
0x180127677  test    rax, rax
0x18012767a  jz      loc_180127580
0x180127680  mov     rcx, [rsi]; hModule
0x180127683  lea     rdx, aDsfreenameresu; "DsFreeNameResultW"
0x18012768a  call    cs:__imp_GetProcAddress
0x180127690  mov     [rbx+28h], rax
0x180127694  test    rax, rax
0x180127697  jz      loc_180127580
0x18012769d  mov     rcx, [rsi]; hModule
0x1801276a0  lea     rdx, aDsunbindw; "DsUnBindW"
0x1801276a7  call    cs:__imp_GetProcAddress
0x1801276ad  mov     [rbx+30h], rax
0x1801276b1  test    rax, rax
0x1801276b4  jz      loc_180127580
0x1801276ba  mov     al, 1
0x1801276bc  mov     rcx, [rsp+258h+var_28]
0x1801276c4  xor     rcx, rsp; StackCookie
0x1801276c7  call    __security_check_cookie
0x1801276cc  mov     rbx, [rsp+258h+arg_10]
0x1801276d4  add     rsp, 240h
0x1801276db  pop     rdi
0x1801276dc  pop     rsi
0x1801276dd  pop     rbp
0x1801276de  retn
```
