# WaasMedic::TimeHelper::SyncSystemTime(void)

- ea: `0x140010f14`
- end: `0x140011121`
- name: `?SyncSystemTime@TimeHelper@WaasMedic@@SAJXZ`
- size: `525`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x14000f744`

## callees

- `0x14000198c`
- `0x140002a30`
- `0x14000885c`
- `0x14000b470`
- `0x140010f14`
- `0x140011244`
- `0x140011508`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010fc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010fc0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400110c0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400110c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110c8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140010fa4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140010fa4`

## string_xrefs

- `0x140010f44`: `Attempting to enable and start service %s`
- `0x140010f70`: `Failed to enable service %s, hr = 0x%08X.`
- `0x140010f9d`: `w32time.DLL`
- `0x1400110e0`: `w32time.DLL`
- `0x1400110e7`: `Failed to load library: %s.  TimeSyncPlugin may not supported in this SKU, , hr = 0x%08X.`

## pseudocode

```c
__int64 WaasMedic::TimeHelper::SyncSystemTime(void)
{
  const unsigned __int16 *v0; // rcx
  unsigned int v1; // ebx
  unsigned int v2; // edi
  __int64 v3; // rdx
  const unsigned __int16 *v4; // rcx
  bool *v5; // r8
  HMODULE LibraryW; // rax
  HMODULE v7; // rsi
  FARPROC ProcAddress; // rax
  int v9; // eax
  const struct _tlgProvider_t *v10; // rax
  const struct _tlgProvider_t *v11; // r10
  __int64 v12; // rax
  __int64 v13; // rax
  signed int LastError; // eax
  unsigned int v16; // [rsp+30h] [rbp-39h] BYREF
  __int64 v17; // [rsp+38h] [rbp-31h] BYREF
  char v18[32]; // [rsp+40h] [rbp-29h] BYREF
  __int64 *v19; // [rsp+60h] [rbp-9h]
  __int64 v20; // [rsp+68h] [rbp-1h]
  unsigned __int16 near **v21; // [rsp+70h] [rbp+7h]
  int v22; // [rsp+78h] [rbp+Fh]
  int v23; // [rsp+7Ch] [rbp+13h]
  unsigned int *v24; // [rsp+80h] [rbp+17h]
  __int64 v25; // [rsp+88h] [rbp+1Fh]

  LogLevelW(4u, L"Attempting to enable and start service %s", L"w32time");
  v1 = WaasMedic::CSvcUtil::EnableService(v0);
  v2 = v1;
  if ( (int)(v1 + 0x80000000) >= 0 && v1 != -2147023840 )
  {
    LogLevelW(3u, L"Failed to enable service %s, hr = 0x%08X.", L"w32time", v1);
LABEL_21:
    WaasMedic::CSvcUtil::ServiceStop(v4, v3, v5);
    return v1;
  }
  LogLevelW(4u, L"%s was successfully enabled.", L"w32time");
  LibraryW = LoadLibraryW(L"w32time.DLL");
  v7 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x19);
    if ( ProcAddress )
    {
      v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 1, 18);
      v1 = v9;
      if ( v9 > 0 )
        v1 = (unsigned __int16)v9 | 0x80070000;
      if ( (v1 & 0x80000000) != 0 )
      {
        LogLevelW(3u, L"Failed to call W32TimeSyncNow() with hr = 0x%08X.", v1);
        v10 = WaasMedic::TelemetryProvider::Provider();
        v11 = v10;
        if ( *(_DWORD *)v10 > 5u )
        {
          v12 = *((_QWORD *)v10 + 3);
          if ( (*((_QWORD *)v11 + 2) & 0x400000000000LL) != 0 && (v12 & 0x400000000000LL) == v12 )
          {
            v16 = v1;
            v24 = &v16;
            v13 = -1;
            v17 = 0x1000000;
            v25 = 4;
            do
              ++v13;
            while ( *((_WORD *)&gc_pszVersionString + v13) );
            v21 = &gc_pszVersionString;
            v22 = 2 * v13 + 2;
            v23 = 0;
            v19 = &v17;
            v20 = 8;
            tlgWriteTransfer_EventWriteTransfer(v11, &word_14001A2B6, 0, 0, 5, v18);
          }
        }
        v1 = 0;
      }
    }
    FreeLibrary(v7);
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(
      3u,
      L"Failed to load library: %s.  TimeSyncPlugin may not supported in this SKU, , hr = 0x%08X.",
      L"w32time.DLL",
      v1);
  }
  if ( v2 != -2147023840 )
    goto LABEL_21;
  return v1;
}

```

## disassembly

```asm
0x140010f14  push    rbp
0x140010f16  push    rbx
0x140010f17  push    rsi
0x140010f18  push    rdi
0x140010f19  push    r14
0x140010f1b  lea     rbp, [rsp-37h]
0x140010f20  sub     rsp, 0A0h
0x140010f27  mov     rax, cs:__security_cookie
0x140010f2e  xor     rax, rsp
0x140010f31  mov     [rbp+57h+var_30], rax
0x140010f35  lea     rsi, ServiceName; "w32time"
0x140010f3c  mov     ecx, 4; unsigned __int8
0x140010f41  mov     r8, rsi
0x140010f44  lea     rdx, aAttemptingToEn; "Attempting to enable and start service "...
0x140010f4b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140010f50  call    ?EnableService@CSvcUtil@WaasMedic@@SAJPEBG_N@Z; WaasMedic::CSvcUtil::EnableService(ushort const *,bool)
0x140010f55  mov     ebx, eax
0x140010f57  mov     edi, eax
0x140010f59  mov     eax, 80000000h
0x140010f5e  lea     ecx, [rbx+rax]
0x140010f61  test    eax, ecx
0x140010f63  jnz     short loc_140010F89
0x140010f65  cmp     ebx, 80070420h
0x140010f6b  jz      short loc_140010F89
0x140010f6d  mov     r9d, ebx
0x140010f70  lea     rdx, aFailedToEnable; "Failed to enable service %s, hr = 0x%08"...
0x140010f77  mov     r8, rsi
0x140010f7a  mov     ecx, 3; unsigned __int8
0x140010f7f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140010f84  jmp     loc_140011100
0x140010f89  mov     r8, rsi
0x140010f8c  lea     rdx, aSWasSuccessful; "%s was successfully enabled."
0x140010f93  mov     ecx, 4; unsigned __int8
0x140010f98  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140010f9d  lea     rcx, LibFileName; "w32time.DLL"
0x140010fa4  call    cs:__imp_LoadLibraryW
0x140010faa  xor     r14d, r14d
0x140010fad  mov     rsi, rax
0x140010fb0  test    rax, rax
0x140010fb3  jz      loc_1400110C8
0x140010fb9  lea     edx, [r14+19h]; lpProcName
0x140010fbd  mov     rcx, rax; hModule
0x140010fc0  call    cs:__imp_GetProcAddress
0x140010fc6  test    rax, rax
0x140010fc9  jz      loc_1400110BD
0x140010fcf  lea     edx, [r14+1]
0x140010fd3  xor     ecx, ecx
0x140010fd5  lea     r8d, [r14+12h]
0x140010fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010fde  mov     ebx, eax
0x140010fe0  test    eax, eax
0x140010fe2  jle     short loc_140010FED
0x140010fe4  movzx   ebx, ax
0x140010fe7  or      ebx, 80070000h
0x140010fed  test    ebx, ebx
0x140010fef  jns     loc_1400110BD
0x140010ff5  mov     r8d, ebx
0x140010ff8  lea     rdx, aFailedToCallW3; "Failed to call W32TimeSyncNow() with hr"...
0x140010fff  mov     ecx, 3; unsigned __int8
0x140011004  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140011009  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x14001100e  mov     r10, rax
0x140011011  mov     ecx, [rax]
0x140011013  cmp     ecx, 5
0x140011016  jbe     loc_1400110BA
0x14001101c  mov     rax, [rax+18h]
0x140011020  mov     rdx, 400000000000h
0x14001102a  mov     rcx, [r10+10h]
0x14001102e  test    rdx, rcx
0x140011031  jz      loc_1400110BA
0x140011037  mov     rcx, rax
0x14001103a  and     rcx, rdx
0x14001103d  cmp     rcx, rax
0x140011040  jnz     short loc_1400110BA
0x140011042  lea     rax, [rbp+57h+var_90]
0x140011046  mov     [rbp+57h+var_90], ebx
0x140011049  mov     [rbp+57h+var_40], rax
0x14001104d  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x140011054  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011058  mov     [rbp+57h+var_88], 1000000h
0x140011060  mov     [rbp+57h+var_38], 4
0x140011068  inc     rax
0x14001106b  cmp     [rcx+rax*2], r14w
0x140011070  jnz     short loc_140011068
0x140011072  lea     eax, ds:2[rax*2]
0x140011079  mov     [rbp+57h+var_50], rcx
0x14001107d  mov     [rbp+57h+var_48], eax
0x140011080  lea     rdx, word_14001A2B6
0x140011087  lea     rax, [rbp+57h+var_88]
0x14001108b  mov     [rbp+57h+var_44], r14d
0x14001108f  mov     [rbp+57h+var_60], rax
0x140011093  xor     r9d, r9d
0x140011096  lea     rax, [rbp+57h+var_80]
0x14001109a  mov     [rbp+57h+var_58], 8
0x1400110a2  mov     [rsp+0C0h+var_98], rax
0x1400110a7  xor     r8d, r8d
0x1400110aa  mov     rcx, r10
0x1400110ad  mov     [rsp+0C0h+var_A0], 5
0x1400110b5  call    _tlgWriteTransfer_EventWriteTransfer
0x1400110ba  mov     ebx, r14d
0x1400110bd  mov     rcx, rsi; hLibModule
0x1400110c0  call    cs:__imp_FreeLibrary
0x1400110c6  jmp     short loc_1400110F8
0x1400110c8  call    cs:__imp_GetLastError
0x1400110ce  mov     ebx, eax
0x1400110d0  test    eax, eax
0x1400110d2  jle     short loc_1400110DD
0x1400110d4  movzx   ebx, ax
0x1400110d7  or      ebx, 80070000h
0x1400110dd  mov     r9d, ebx
0x1400110e0  lea     r8, LibFileName; "w32time.DLL"
0x1400110e7  lea     rdx, aFailedToLoadLi; "Failed to load library: %s.  TimeSyncPl"...
0x1400110ee  mov     ecx, 3; unsigned __int8
0x1400110f3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1400110f8  cmp     edi, 80070420h
0x1400110fe  jz      short loc_140011105
0x140011100  call    ?ServiceStop@CSvcUtil@WaasMedic@@SAJPEBG_NPEA_N@Z; WaasMedic::CSvcUtil::ServiceStop(ushort const *,bool,bool *)
0x140011105  mov     eax, ebx
0x140011107  mov     rcx, [rbp+57h+var_30]
0x14001110b  xor     rcx, rsp; StackCookie
0x14001110e  call    __security_check_cookie
0x140011113  add     rsp, 0A0h
0x14001111a  pop     r14
0x14001111c  pop     rdi
0x14001111d  pop     rsi
0x14001111e  pop     rbx
0x14001111f  pop     rbp
0x140011120  retn
```
