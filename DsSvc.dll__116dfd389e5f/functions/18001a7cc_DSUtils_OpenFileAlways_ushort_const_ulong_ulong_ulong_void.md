# DSUtils::OpenFileAlways(ushort const *,ulong,ulong,ulong,void * *)

- ea: `0x18001a7cc`
- end: `0x18001a934`
- name: `?OpenFileAlways@DSUtils@@YAJPEBGKKKPEAPEAX@Z`
- size: `360`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ca4c`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000c704`
- `0x18000f1a0`
- `0x18001a6f0`
- `0x18001a7cc`
- `0x18001ab6c`
- `0x18001afe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a851`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a851`

## string_xrefs

- `0x18001a8bd`: `Failed to open file %s, with DesiredAccess=0x%x, ShareMode=0x%x, FlagsAndAttributes=0x%x, HR=0x%x`
- `0x18001a890`: `Failed to create file %s, with DesiredAccess=0x%x, ShareMode=0x%x, FlagsAndAttributes=0x%x, HR=0x%x`
- `0x18001a8eb`: `DSUtils::OpenFileAlways`

## pseudocode

```c
__int64 __fastcall DSUtils::OpenFileAlways(
        const WCHAR *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5)
{
  __int64 *v6; // rdi
  signed int v7; // ebx
  _QWORD *v8; // rax
  int v9; // ebp
  HANDLE FileW; // rax
  signed int LastError; // eax
  DSLogger *v12; // rax
  const unsigned __int16 *v13; // r9
  unsigned int v14; // r8d
  signed int v15; // eax
  __int64 v16; // rax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-50h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-48h]
  __int64 v20; // [rsp+80h] [rbp+8h] BYREF

  if ( !this )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
  v6 = a5;
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2);
  v7 = 0;
  v20 = -1;
  v8 = (_QWORD *)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),-1>(&v20);
  v9 = DSUtils::OpenFile(this, (const unsigned __int16 *)0xC0000000LL, 3u, 0, v8);
  if ( v9 == -2147024894 )
  {
    FileW = CreateFileW(this, 0xC0000000, 3u, 0, 1u, 0, 0);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::reset(&v20, FileW);
    if ( v20 == -1 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v12 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
      v13 = L"Failed to create file %s, with DesiredAccess=0x%x, ShareMode=0x%x, FlagsAndAttributes=0x%x, HR=0x%x";
      v14 = 703;
      goto LABEL_14;
    }
  }
  else if ( v9 < 0 )
  {
    v15 = GetLastError();
    v7 = v15;
    if ( v15 > 0 )
      v7 = (unsigned __int16)v15 | 0x80070000;
    v12 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v13 = L"Failed to open file %s, with DesiredAccess=0x%x, ShareMode=0x%x, FlagsAndAttributes=0x%x, HR=0x%x";
    v14 = 711;
LABEL_14:
    LODWORD(hTemplateFile) = 3;
    LODWORD(dwFlagsAndAttributes) = -1073741824;
    DSLogger::LogError(v12, L"DSUtils::OpenFileAlways", v14, v13, this, dwFlagsAndAttributes, hTemplateFile, 0, v7);
    if ( v7 < 0 )
      goto LABEL_17;
  }
  if ( v6 )
  {
    v16 = v20;
    v20 = -1;
    *v6 = v16;
    v7 = v9;
  }
LABEL_17:
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&v20);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a7cc  push    rbx
0x18001a7ce  push    rbp
0x18001a7cf  push    rsi
0x18001a7d0  push    rdi
0x18001a7d1  sub     rsp, 58h
0x18001a7d5  mov     rsi, rcx
0x18001a7d8  test    rcx, rcx
0x18001a7db  jnz     short loc_18001A7E2
0x18001a7dd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a7e2  mov     rdi, [rsp+78h+arg_20]
0x18001a7ea  test    rdi, rdi
0x18001a7ed  jnz     short loc_18001A7F4
0x18001a7ef  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a7f4  xor     ebx, ebx
0x18001a7f6  mov     [rsp+78h+arg_0], 0FFFFFFFFFFFFFFFFh
0x18001a802  lea     rcx, [rsp+78h+arg_0]
0x18001a80a  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),-1>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1> &)
0x18001a80f  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; unsigned int
0x18001a814  xor     r9d, r9d; unsigned int
0x18001a817  mov     edx, 0C0000000h; unsigned __int16 *
0x18001a81c  lea     r8d, [rbx+3]; unsigned int
0x18001a820  mov     rcx, rsi; this
0x18001a823  call    ?OpenFile@DSUtils@@YAJPEBGKKKPEAPEAX@Z; DSUtils::OpenFile(ushort const *,ulong,ulong,ulong,void * *)
0x18001a828  mov     ebp, eax
0x18001a82a  cmp     eax, 80070002h
0x18001a82f  jnz     short loc_18001A89F
0x18001a831  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x18001a836  mov     dword ptr [rsp+78h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18001a83a  mov     [rsp+78h+dwCreationDisposition], 1; dwCreationDisposition
0x18001a842  xor     r9d, r9d; lpSecurityAttributes
0x18001a845  mov     edx, 0C0000000h; dwDesiredAccess
0x18001a84a  lea     r8d, [rbx+3]; dwShareMode
0x18001a84e  mov     rcx, rsi; lpFileName
0x18001a851  call    cs:__imp_CreateFileW
0x18001a857  mov     rdx, rax
0x18001a85a  lea     rcx, [rsp+78h+arg_0]
0x18001a862  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::reset(void *)
0x18001a867  cmp     [rsp+78h+arg_0], 0FFFFFFFFFFFFFFFFh
0x18001a870  jnz     loc_18001A8FE
0x18001a876  call    cs:__imp_GetLastError
0x18001a87c  mov     ebx, eax
0x18001a87e  test    eax, eax
0x18001a880  jle     short loc_18001A88B
0x18001a882  movzx   ebx, ax
0x18001a885  or      ebx, 80070000h
0x18001a88b  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a890  lea     r9, aFailedToCreate; "Failed to create file %s, with DesiredA"...
0x18001a897  mov     r8d, 2BFh
0x18001a89d  jmp     short loc_18001A8CA
0x18001a89f  test    ebp, ebp
0x18001a8a1  jns     short loc_18001A8FE
0x18001a8a3  call    cs:__imp_GetLastError
0x18001a8a9  mov     ebx, eax
0x18001a8ab  test    eax, eax
0x18001a8ad  jle     short loc_18001A8B8
0x18001a8af  movzx   ebx, ax
0x18001a8b2  or      ebx, 80070000h
0x18001a8b8  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a8bd  lea     r9, aFailedToOpenFi; "Failed to open file %s, with DesiredAcc"...
0x18001a8c4  mov     r8d, 2C7h; unsigned int
0x18001a8ca  mov     [rsp+78h+var_38], ebx
0x18001a8ce  mov     [rsp+78h+var_40], 0
0x18001a8d6  mov     dword ptr [rsp+78h+hTemplateFile], 3
0x18001a8de  mov     dword ptr [rsp+78h+dwFlagsAndAttributes], 0C0000000h
0x18001a8e6  mov     qword ptr [rsp+78h+dwCreationDisposition], rsi
0x18001a8eb  lea     rdx, aDsutilsOpenfil_0; "DSUtils::OpenFileAlways"
0x18001a8f2  mov     rcx, rax; this
0x18001a8f5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001a8fa  test    ebx, ebx
0x18001a8fc  js      short loc_18001A91C
0x18001a8fe  test    rdi, rdi
0x18001a901  jz      short loc_18001A91C
0x18001a903  mov     rax, [rsp+78h+arg_0]
0x18001a90b  mov     [rsp+78h+arg_0], 0FFFFFFFFFFFFFFFFh
0x18001a917  mov     [rdi], rax
0x18001a91a  mov     ebx, ebp
0x18001a91c  lea     rcx, [rsp+78h+arg_0]
0x18001a924  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x18001a929  mov     eax, ebx
0x18001a92b  add     rsp, 58h
0x18001a92f  pop     rdi
0x18001a930  pop     rsi
0x18001a931  pop     rbp
0x18001a932  pop     rbx
0x18001a933  retn
```
