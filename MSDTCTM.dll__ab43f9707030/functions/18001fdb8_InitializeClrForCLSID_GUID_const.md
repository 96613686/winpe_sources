# InitializeClrForCLSID(_GUID const &)

- ea: `0x18001fdb8`
- end: `0x18001ffae`
- name: `?InitializeClrForCLSID@@YAJAEBU_GUID@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008356c`

## callees

- `0x1800063b0`
- `0x18001fdb8`
- `0x180023600`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fef2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001fe0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001fe0e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ff88`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ff88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fe76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fee7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fe76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fee7`

## string_xrefs

- `0x18001fe43`: `com\complus\dtc\dtc\msdtc\src\initbridge.cpp`
- `0x18001fe53`: `InitializeClrForCLSID`
- `0x18001fe31`: `LoadLibraryExW(mscoree)`
- `0x18001fe05`: `mscoree.dll`
- `0x18001fe6c`: `GetRequestedRuntimeVersionForCLSID`

## pseudocode

```c
__int64 __fastcall InitializeClrForCLSID(struct _GUID *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  signed int LastError; // eax
  signed int v5; // ebx
  const wchar_t *v6; // rax
  __int64 v7; // r9
  FARPROC ProcAddress; // rax
  signed int v9; // eax
  FARPROC v10; // rax
  signed int v11; // eax
  __int64 v13; // [rsp+28h] [rbp-60h]
  int v14; // [rsp+40h] [rbp-48h] BYREF
  __int64 v15; // [rsp+48h] [rbp-40h] BYREF
  _OWORD v16[2]; // [rsp+50h] [rbp-38h] BYREF

  v14 = 0;
  memset(v16, 0, sizeof(v16));
  v15 = 0;
  if ( IsManagedCLSID(a1) )
  {
    Library = LoadLibraryExW(L"mscoree.dll", 0, 0);
    v3 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v6 = L"LoadLibraryExW(mscoree)";
      v7 = 303;
      goto LABEL_6;
    }
    ProcAddress = GetProcAddress(Library, "GetRequestedRuntimeVersionForCLSID");
    if ( !ProcAddress )
    {
      v9 = GetLastError();
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      v6 = L"GetProcAddress(GetRRV)";
      v7 = 313;
      goto LABEL_6;
    }
    v5 = ((__int64 (__fastcall *)(struct _GUID *, _OWORD *, __int64, int *, _DWORD))ProcAddress)(a1, v16, 16, &v14, 0);
    if ( v5 < 0 )
    {
      v6 = L"GetRequestedRuntimeVersion";
      v7 = 324;
LABEL_6:
      LODWORD(v13) = v5;
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\initbridge.cpp",
        v7,
        L"InitializeClrForCLSID",
        v13,
        v6);
      goto LABEL_20;
    }
    v10 = GetProcAddress(v3, "CorBindToRuntimeEx");
    if ( !v10 )
    {
      v11 = GetLastError();
      v5 = v11;
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      v6 = L"GetProcAddress(CBREx)";
      v7 = 332;
      goto LABEL_6;
    }
    v5 = ((__int64 (__fastcall *)(_OWORD *, const wchar_t *, _QWORD, GUID *, GUID *, __int64 *))v10)(
           v16,
           L"svr",
           0,
           &CLSID_CorRuntimeHost,
           &IID_ICorRuntimeHost,
           &v15);
    if ( v5 < 0 )
    {
      v6 = L"CorBindToRuntimeEx";
      v7 = 344;
      goto LABEL_6;
    }
  }
  else
  {
    v5 = 0;
    v3 = 0;
  }
LABEL_20:
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v5 < 0 && v3 )
    FreeLibrary(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001fdb8  mov     [rsp+arg_8], rbx
0x18001fdbd  push    rdi
0x18001fdbe  sub     rsp, 80h
0x18001fdc5  mov     rax, cs:__security_cookie
0x18001fdcc  xor     rax, rsp
0x18001fdcf  mov     [rsp+88h+var_18], rax
0x18001fdd4  xorps   xmm0, xmm0
0x18001fdd7  mov     [rsp+88h+var_48], 0
0x18001fddf  movups  [rsp+88h+var_38], xmm0
0x18001fde4  mov     rbx, rcx
0x18001fde7  mov     [rsp+88h+var_40], 0
0x18001fdf0  movups  [rsp+88h+var_28], xmm0
0x18001fdf5  call    ?IsManagedCLSID@@YA_NAEBU_GUID@@@Z; IsManagedCLSID(_GUID const &)
0x18001fdfa  test    al, al
0x18001fdfc  jz      loc_18001FF62
0x18001fe02  xor     r8d, r8d; dwFlags
0x18001fe05  lea     rcx, aMscoreeDll; "mscoree.dll"
0x18001fe0c  xor     edx, edx; hFile
0x18001fe0e  call    cs:__imp_LoadLibraryExW
0x18001fe14  mov     rdi, rax
0x18001fe17  test    rax, rax
0x18001fe1a  jnz     short loc_18001FE6C
0x18001fe1c  call    cs:__imp_GetLastError
0x18001fe22  mov     ebx, eax
0x18001fe24  test    eax, eax
0x18001fe26  jle     short loc_18001FE31
0x18001fe28  movzx   ebx, ax
0x18001fe2b  or      ebx, 80070000h
0x18001fe31  lea     rax, aLoadlibraryexw_0; "LoadLibraryExW(mscoree)"
0x18001fe38  mov     r9d, 12Fh
0x18001fe3e  mov     [rsp+88h+var_58], rax
0x18001fe43  lea     r8, aComComplusDtcD_31; "com\\complus\\dtc\\dtc\\msdtc\\src\\ini"...
0x18001fe4a  mov     edx, 1
0x18001fe4f  mov     dword ptr [rsp+88h+var_60], ebx
0x18001fe53  lea     rax, aInitializeclrf; "InitializeClrForCLSID"
0x18001fe5a  mov     [rsp+88h+var_68], rax
0x18001fe5f  lea     ecx, [rdx+2]
0x18001fe62  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001fe67  jmp     loc_18001FF66
0x18001fe6c  lea     rdx, aGetrequestedru; "GetRequestedRuntimeVersionForCLSID"
0x18001fe73  mov     rcx, rdi; hModule
0x18001fe76  call    cs:__imp_GetProcAddress
0x18001fe7c  test    rax, rax
0x18001fe7f  jnz     short loc_18001FEA5
0x18001fe81  call    cs:__imp_GetLastError
0x18001fe87  mov     ebx, eax
0x18001fe89  test    eax, eax
0x18001fe8b  jle     short loc_18001FE96
0x18001fe8d  movzx   ebx, ax
0x18001fe90  or      ebx, 80070000h
0x18001fe96  lea     rax, aGetprocaddress_1; "GetProcAddress(GetRRV)"
0x18001fe9d  mov     r9d, 139h
0x18001fea3  jmp     short loc_18001FE3E
0x18001fea5  lea     r9, [rsp+88h+var_48]
0x18001feaa  mov     dword ptr [rsp+88h+var_68], 0
0x18001feb2  mov     r8d, 10h
0x18001feb8  lea     rdx, [rsp+88h+var_38]
0x18001febd  mov     rcx, rbx
0x18001fec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fec5  mov     ebx, eax
0x18001fec7  test    eax, eax
0x18001fec9  jns     short loc_18001FEDD
0x18001fecb  lea     rax, aGetrequestedru_0; "GetRequestedRuntimeVersion"
0x18001fed2  mov     r9d, 144h
0x18001fed8  jmp     loc_18001FE3E
0x18001fedd  lea     rdx, aCorbindtorunti; "CorBindToRuntimeEx"
0x18001fee4  mov     rcx, rdi; hModule
0x18001fee7  call    cs:__imp_GetProcAddress
0x18001feed  test    rax, rax
0x18001fef0  jnz     short loc_18001FF19
0x18001fef2  call    cs:__imp_GetLastError
0x18001fef8  mov     ebx, eax
0x18001fefa  test    eax, eax
0x18001fefc  jle     short loc_18001FF07
0x18001fefe  movzx   ebx, ax
0x18001ff01  or      ebx, 80070000h
0x18001ff07  lea     rax, aGetprocaddress_0; "GetProcAddress(CBREx)"
0x18001ff0e  mov     r9d, 14Ch
0x18001ff14  jmp     loc_18001FE3E
0x18001ff19  lea     rcx, [rsp+88h+var_40]
0x18001ff1e  xor     r8d, r8d
0x18001ff21  mov     [rsp+88h+var_60], rcx
0x18001ff26  lea     r9, CLSID_CorRuntimeHost
0x18001ff2d  lea     rcx, IID_ICorRuntimeHost
0x18001ff34  mov     [rsp+88h+var_68], rcx
0x18001ff39  lea     rdx, aSvr; "svr"
0x18001ff40  lea     rcx, [rsp+88h+var_38]
0x18001ff45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff4a  mov     ebx, eax
0x18001ff4c  test    eax, eax
0x18001ff4e  jns     short loc_18001FF66
0x18001ff50  lea     rax, aCorbindtorunti_0; "CorBindToRuntimeEx"
0x18001ff57  mov     r9d, 158h
0x18001ff5d  jmp     loc_18001FE3E
0x18001ff62  xor     ebx, ebx
0x18001ff64  xor     edi, edi
0x18001ff66  mov     rcx, [rsp+88h+var_40]
0x18001ff6b  test    rcx, rcx
0x18001ff6e  jz      short loc_18001FF7C
0x18001ff70  mov     rax, [rcx]
0x18001ff73  mov     rax, [rax+10h]
0x18001ff77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff7c  test    ebx, ebx
0x18001ff7e  jns     short loc_18001FF8E
0x18001ff80  test    rdi, rdi
0x18001ff83  jz      short loc_18001FF8E
0x18001ff85  mov     rcx, rdi; hLibModule
0x18001ff88  call    cs:__imp_FreeLibrary
0x18001ff8e  mov     eax, ebx
0x18001ff90  mov     rcx, [rsp+88h+var_18]
0x18001ff95  xor     rcx, rsp; StackCookie
0x18001ff98  call    __security_check_cookie
0x18001ff9d  mov     rbx, [rsp+88h+arg_8]
0x18001ffa5  add     rsp, 80h
0x18001ffac  pop     rdi
0x18001ffad  retn
```
