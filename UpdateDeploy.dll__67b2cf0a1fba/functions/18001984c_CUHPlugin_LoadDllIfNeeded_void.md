# CUHPlugin::LoadDllIfNeeded(void)

- ea: `0x18001984c`
- end: `0x180019a0a`
- name: `?LoadDllIfNeeded@CUHPlugin@@QEAAJXZ`
- size: `446`
- prototype: `__int64 __fastcall(CUHPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800174a0`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000dce4`
- `0x1800110fc`
- `0x18001984c`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180019991`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180019991`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800198a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800198a5`

## string_xrefs

- `0x180019936`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x1800199a5`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x18001995d`: `Loading handler module for handler URI %ws from %ws`

## pseudocode

```c
__int64 __fastcall CUHPlugin::LoadDllIfNeeded(CUHPlugin *this)
{
  FARPROC ProcAddress; // rbx
  const char *v4; // r9
  __int64 v5; // rdx
  int v6; // eax
  unsigned int LastError; // ebx
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD, int *, LPCWSTR *); // rsi
  HMODULE Library; // rax
  int v12; // [rsp+20h] [rbp-40h]
  __int64 v13; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpLibFileName; // [rsp+48h] [rbp-18h] BYREF
  int v15; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  if ( *((_QWORD *)this + 7) )
    return 0;
  lpLibFileName = 0;
  v15 = 0;
  v13 = 0;
  ProcAddress = GetProcAddress(g_hInstance, (LPCSTR)4);
  if ( !ProcAddress )
  {
    v5 = 1324;
LABEL_14:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
                  v4);
    goto LABEL_16;
  }
  v6 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v13);
  LastError = v6;
  if ( v6 >= 0 )
  {
    v9 = v13;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, LPCWSTR *))(*(_QWORD *)v13 + 40LL);
    if ( lpLibFileName )
    {
      SusFree((void *)lpLibFileName);
      lpLibFileName = 0;
    }
    v6 = v10(v9, *((_QWORD *)this + 2), &v15, &lpLibFileName);
    LastError = v6;
    if ( v6 >= 0 )
    {
      WUTrace(0, 0, 0x1000000, 4);
      Library = LoadLibraryExW(lpLibFileName, 0, 0x88u);
      *((_QWORD *)this + 7) = Library;
      if ( Library )
      {
        LastError = 0;
        goto LABEL_16;
      }
      v5 = 1341;
      goto LABEL_14;
    }
    v8 = 1330;
  }
  else
  {
    v8 = 1326;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
    (const char *)(unsigned int)v6,
    v12);
LABEL_16:
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( lpLibFileName )
    SusFree((void *)lpLibFileName);
  return LastError;
}

```

## disassembly

```asm
0x18001984c  mov     [rsp-8+arg_8], rbx
0x180019851  mov     [rsp-8+arg_10], rsi
0x180019856  mov     [rsp-8+arg_18], rdi
0x18001985b  push    rbp
0x18001985c  mov     rbp, rsp
0x18001985f  sub     rsp, 60h
0x180019863  mov     rax, cs:__security_cookie
0x18001986a  xor     rax, rsp
0x18001986d  mov     [rbp+var_8], rax
0x180019871  mov     rdi, rcx
0x180019874  cmp     qword ptr [rcx+38h], 0
0x180019879  jz      short loc_180019882
0x18001987b  xor     eax, eax
0x18001987d  jmp     loc_1800199E8
0x180019882  mov     [rbp+lpLibFileName], 0
0x18001988a  mov     [rbp+var_10], 0
0x180019891  mov     [rbp+var_20], 0
0x180019899  mov     edx, 4; lpProcName
0x18001989e  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800198a5  call    cs:__imp_GetProcAddress
0x1800198ab  mov     rbx, rax
0x1800198ae  test    rax, rax
0x1800198b1  jnz     short loc_1800198BD
0x1800198b3  mov     edx, 52Ch
0x1800198b8  jmp     loc_1800199A5
0x1800198bd  mov     rcx, [rbp+var_20]
0x1800198c1  test    rcx, rcx
0x1800198c4  jz      short loc_1800198DA
0x1800198c6  mov     rax, [rcx]
0x1800198c9  mov     rax, [rax+10h]
0x1800198cd  call    _guard_dispatch_icall
0x1800198d2  mov     [rbp+var_20], 0
0x1800198da  lea     rcx, [rbp+var_20]
0x1800198de  mov     rax, rbx
0x1800198e1  call    _guard_dispatch_icall
0x1800198e6  mov     ebx, eax
0x1800198e8  test    eax, eax
0x1800198ea  jns     short loc_1800198F3
0x1800198ec  mov     edx, 52Eh
0x1800198f1  jmp     short loc_180019936
0x1800198f3  mov     rbx, [rbp+var_20]
0x1800198f7  mov     rax, [rbx]
0x1800198fa  mov     rsi, [rax+28h]
0x1800198fe  mov     rcx, [rbp+lpLibFileName]; lpMem
0x180019902  test    rcx, rcx
0x180019905  jz      short loc_180019914
0x180019907  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18001990c  mov     [rbp+lpLibFileName], 0
0x180019914  lea     r9, [rbp+lpLibFileName]
0x180019918  lea     r8, [rbp+var_10]
0x18001991c  mov     rdx, [rdi+10h]
0x180019920  mov     rcx, rbx
0x180019923  mov     rax, rsi
0x180019926  call    _guard_dispatch_icall
0x18001992b  mov     ebx, eax
0x18001992d  test    eax, eax
0x18001992f  jns     short loc_18001994B
0x180019931  mov     edx, 532h; void *
0x180019936  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001993d  mov     r9d, eax; char *
0x180019940  mov     rcx, [rbp+8]; this
0x180019944  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019949  jmp     short loc_1800199BB
0x18001994b  mov     rax, [rbp+lpLibFileName]
0x18001994f  mov     [rsp+60h+var_28], rax
0x180019954  mov     rax, [rdi+10h]
0x180019958  mov     [rsp+60h+var_30], rax
0x18001995d  lea     rax, aLoadingHandler; "Loading handler module for handler URI "...
0x180019964  mov     [rsp+60h+var_38], rax
0x180019969  mov     [rsp+60h+var_40], 0
0x180019972  xor     edx, edx
0x180019974  xor     ecx, ecx
0x180019976  lea     r9d, [rdx+4]
0x18001997a  mov     r8d, 1000000h
0x180019980  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180019985  xor     edx, edx; hFile
0x180019987  mov     r8d, 88h; dwFlags
0x18001998d  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180019991  call    cs:__imp_LoadLibraryExW
0x180019997  mov     [rdi+38h], rax
0x18001999b  test    rax, rax
0x18001999e  jnz     short loc_1800199B9
0x1800199a0  mov     edx, 53Dh; void *
0x1800199a5  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800199ac  mov     rcx, [rbp+8]; this
0x1800199b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800199b5  mov     ebx, eax
0x1800199b7  jmp     short loc_1800199BB
0x1800199b9  xor     ebx, ebx
0x1800199bb  mov     rcx, [rbp+var_20]
0x1800199bf  test    rcx, rcx
0x1800199c2  jz      short loc_1800199D8
0x1800199c4  mov     rax, [rcx]
0x1800199c7  mov     rax, [rax+10h]
0x1800199cb  call    _guard_dispatch_icall
0x1800199d0  mov     [rbp+var_20], 0
0x1800199d8  mov     rcx, [rbp+lpLibFileName]; lpMem
0x1800199dc  test    rcx, rcx
0x1800199df  jz      short loc_1800199E6
0x1800199e1  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800199e6  mov     eax, ebx
0x1800199e8  mov     rcx, [rbp+var_8]
0x1800199ec  xor     rcx, rsp; StackCookie
0x1800199ef  call    __security_check_cookie
0x1800199f4  lea     r11, [rsp+60h+var_s0]
0x1800199f9  mov     rbx, [r11+18h]
0x1800199fd  mov     rsi, [r11+20h]
0x180019a01  mov     rdi, [r11+28h]
0x180019a05  mov     rsp, r11
0x180019a08  pop     rbp
0x180019a09  retn
```
