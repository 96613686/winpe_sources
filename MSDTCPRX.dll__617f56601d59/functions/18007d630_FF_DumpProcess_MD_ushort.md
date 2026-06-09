# FF_DumpProcess_MD(ushort *)

- ea: `0x18007d630`
- end: `0x18007d8d5`
- name: `?FF_DumpProcess_MD@@YAJPEAG@Z`
- size: `677`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007d554`

## callees

- `0x18000c6bc`
- `0x18007d630`
- `0x18007d8dc`
- `0x18007dad8`
- `0x18007dcc8`
- `0x180081d86`
- `0x180081d9e`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007d713`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007d713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d738`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007d869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007d869`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007d863`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007d863`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007d72e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18007d72e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18007d7c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18007d7c5`
- `msvcrt!_waccess` at `0x18007d89f`
- `msvcrt!_waccess` at `0x18007d89f`

## string_xrefs

- `0x18007d879`: `RunDll32 comsvcs.dll,MiniDump`

## pseudocode

```c
__int64 __fastcall FF_DumpProcess_MD(unsigned __int16 *a1)
{
  int DumpProperties; // ebx
  __int64 v2; // rax
  DWORD v3; // eax
  signed int LastError; // eax
  DWORD CurrentProcessId; // eax
  __int64 v7; // [rsp+0h] [rbp-318h] BYREF
  __int64 v8; // [rsp+28h] [rbp-2F0h]
  __int64 v9; // [rsp+30h] [rbp-2E8h]
  __int64 v10; // [rsp+38h] [rbp-2E0h]
  __int64 v11; // [rsp+40h] [rbp-2D8h]
  __int64 v12; // [rsp+48h] [rbp-2D0h]
  __int64 v13; // [rsp+50h] [rbp-2C8h]
  int v14; // [rsp+60h] [rbp-2B8h]
  int v15; // [rsp+64h] [rbp-2B4h] BYREF
  unsigned int v16; // [rsp+68h] [rbp-2B0h]
  unsigned int v17; // [rsp+6Ch] [rbp-2ACh] BYREF
  GUID *rguid; // [rsp+70h] [rbp-2A8h] BYREF
  LPCWSTR lpSrc; // [rsp+78h] [rbp-2A0h] BYREF
  signed int v20; // [rsp+80h] [rbp-298h]
  int v21; // [rsp+84h] [rbp-294h]
  __int64 *v22; // [rsp+88h] [rbp-290h]
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-288h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-278h] BYREF
  WCHAR Dst[264]; // [rsp+F0h] [rbp-228h] BYREF

  v22 = &v7;
  memset_0(sz, 0, sizeof(sz));
  memset_0(Dst, 0, 0x20Au);
  lpSrc = 0;
  SystemTime = 0;
  v17 = 10;
  v15 = 1;
  rguid = 0;
  DumpProperties = FF_GetDumpProperties(&rguid, &v15, (unsigned __int16 **)&lpSrc, &v17);
  v14 = DumpProperties;
  if ( DumpProperties )
    return (unsigned int)DumpProperties;
  if ( !v15 )
    goto LABEL_3;
  if ( rguid )
  {
    v2 = *(_QWORD *)&rguid->Data1 - APPLID_SystemApplication;
    if ( *(_QWORD *)&rguid->Data1 == APPLID_SystemApplication )
      v2 = *(_QWORD *)rguid->Data4 - 0x3592C75F80000D96LL;
    if ( !v2 )
    {
LABEL_3:
      DumpProperties = 1;
LABEL_18:
      v14 = DumpProperties;
      return (unsigned int)DumpProperties;
    }
  }
  StringFromGUID2(rguid, sz, 40);
  v3 = ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u);
  if ( v3 )
  {
    if ( v3 > 0x104 )
    {
      v21 = -2147024785;
      local_unwind_0(v22, &loc_18007D799);
      return 2147942511LL;
    }
    FF_RemoveLegacyDump(sz, Dst, v17);
    GetLocalTime(&SystemTime);
    word_1800D9628 = 0;
    LODWORD(v13) = SystemTime.wSecond;
    LODWORD(v12) = SystemTime.wMinute;
    LODWORD(v11) = SystemTime.wHour;
    LODWORD(v10) = SystemTime.wDay;
    LODWORD(v9) = SystemTime.wMonth;
    LODWORD(v8) = SystemTime.wYear;
    DumpProperties = StringCchPrintfW(
                       &word_1800D9420,
                       0x104u,
                       L"%s\\%s_%04d_%02d_%02d_%02d_%02d_%02d.dmp",
                       Dst,
                       sz,
                       v8,
                       v9,
                       v10,
                       v11,
                       v12,
                       v13);
    v14 = DumpProperties;
    if ( DumpProperties < 0 )
      return (unsigned int)DumpProperties;
    CreateDirectoryW(Dst, 0);
    CurrentProcessId = GetCurrentProcessId();
    DumpProperties = FF_RunCmd(L"%s %d %s full", L"RunDll32 comsvcs.dll,MiniDump", CurrentProcessId, &word_1800D9420);
    v14 = DumpProperties;
    if ( DumpProperties < 0 )
      return (unsigned int)DumpProperties;
    if ( _waccess(&word_1800D9420, 0) )
      DumpProperties = -2147467259;
    goto LABEL_18;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v16 = LastError;
  v20 = LastError;
  local_unwind_0(v22, &loc_18007D76B);
  return v16;
}

```

## disassembly

```asm
0x18007d630  push    rbx
0x18007d632  sub     rsp, 310h
0x18007d639  mov     rax, cs:__security_cookie
0x18007d640  xor     rax, rsp
0x18007d643  mov     [rsp+318h+var_18], rax
0x18007d64b  mov     [rsp+318h+var_290], rsp
0x18007d653  xor     edx, edx; Val
0x18007d655  lea     r8d, [rdx+50h]; Size
0x18007d659  lea     rcx, [rsp+318h+sz]; void *
0x18007d661  call    memset_0
0x18007d666  xor     edx, edx; Val
0x18007d668  mov     r8d, 20Ah; Size
0x18007d66e  lea     rcx, [rsp+318h+Dst]; void *
0x18007d676  call    memset_0
0x18007d67b  mov     [rsp+318h+lpSrc], 0
0x18007d684  xorps   xmm0, xmm0
0x18007d687  movups  xmmword ptr [rsp+318h+SystemTime.wYear], xmm0
0x18007d68f  mov     [rsp+318h+var_2AC], 0Ah
0x18007d697  mov     [rsp+318h+var_2B4], 1
0x18007d69f  mov     [rsp+318h+rguid], 0
0x18007d6a8  lea     r9, [rsp+318h+var_2AC]; unsigned int *
0x18007d6ad  lea     r8, [rsp+318h+lpSrc]; unsigned __int16 **
0x18007d6b2  lea     rdx, [rsp+318h+var_2B4]; int *
0x18007d6b7  lea     rcx, [rsp+318h+rguid]; struct _GUID **
0x18007d6bc  call    ?FF_GetDumpProperties@@YAJPEAPEAU_GUID@@PEAHPEAPEAGPEAK@Z; FF_GetDumpProperties(_GUID * *,int *,ushort * *,ulong *)
0x18007d6c1  mov     ebx, eax
0x18007d6c3  mov     [rsp+318h+var_2B8], eax
0x18007d6c7  test    eax, eax
0x18007d6c9  jnz     loc_18007D8B3
0x18007d6cf  cmp     [rsp+318h+var_2B4], eax
0x18007d6d3  jnz     short loc_18007D6DF
0x18007d6d5  mov     ebx, 1
0x18007d6da  jmp     loc_18007D8AF
0x18007d6df  mov     rcx, [rsp+318h+rguid]; rguid
0x18007d6e4  test    rcx, rcx
0x18007d6e7  jz      short loc_18007D705
0x18007d6e9  mov     rax, [rcx]
0x18007d6ec  sub     rax, cs:APPLID_SystemApplication
0x18007d6f3  jnz     short loc_18007D700
0x18007d6f5  mov     rax, [rcx+8]
0x18007d6f9  sub     rax, cs:qword_1800C70A8
0x18007d700  test    rax, rax
0x18007d703  jz      short loc_18007D6D5
0x18007d705  mov     r8d, 28h ; '('; cchMax
0x18007d70b  lea     rdx, [rsp+318h+sz]; lpsz
0x18007d713  call    cs:__imp_StringFromGUID2
0x18007d719  mov     ebx, 104h
0x18007d71e  mov     r8d, ebx; nSize
0x18007d721  lea     rdx, [rsp+318h+Dst]; lpDst
0x18007d729  mov     rcx, [rsp+318h+lpSrc]; lpSrc
0x18007d72e  call    cs:__imp_ExpandEnvironmentStringsW
0x18007d734  test    eax, eax
0x18007d736  jnz     short loc_18007D774
0x18007d738  call    cs:__imp_GetLastError
0x18007d73e  test    eax, eax
0x18007d740  jle     short loc_18007D74A
0x18007d742  movzx   eax, ax
0x18007d745  or      eax, 80070000h
0x18007d74a  mov     [rsp+318h+var_2B0], eax
0x18007d74e  mov     [rsp+318h+var_298], eax
0x18007d755  lea     rdx, loc_18007D76B
0x18007d75c  mov     rcx, [rsp+318h+var_290]
0x18007d764  call    _local_unwind_0
0x18007d769  nop
0x18007d76a  nop
0x18007d76b  mov     eax, [rsp+318h+var_2B0]
0x18007d76f  jmp     loc_18007D8BC
0x18007d774  cmp     eax, ebx
0x18007d776  jbe     short loc_18007D7A3
0x18007d778  mov     [rsp+318h+var_294], 8007006Fh
0x18007d783  lea     rdx, loc_18007D799
0x18007d78a  mov     rcx, [rsp+318h+var_290]
0x18007d792  call    _local_unwind_0
0x18007d797  nop
0x18007d798  nop
0x18007d799  mov     eax, 8007006Fh
0x18007d79e  jmp     loc_18007D8BC
0x18007d7a3  mov     r8d, [rsp+318h+var_2AC]; unsigned int
0x18007d7a8  lea     rdx, [rsp+318h+Dst]; unsigned __int16 *
0x18007d7b0  lea     rcx, [rsp+318h+sz]; unsigned __int16 *
0x18007d7b8  call    ?FF_RemoveLegacyDump@@YAXPEBG0K@Z; FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)
0x18007d7bd  lea     rcx, [rsp+318h+SystemTime]; lpSystemTime
0x18007d7c5  call    cs:__imp_GetLocalTime
0x18007d7cb  xor     eax, eax
0x18007d7cd  mov     cs:word_1800D9628, ax
0x18007d7d4  movzx   eax, [rsp+318h+SystemTime.wSecond]
0x18007d7dc  movzx   ecx, [rsp+318h+SystemTime.wMinute]
0x18007d7e4  movzx   r8d, [rsp+318h+SystemTime.wHour]
0x18007d7ed  movzx   r9d, [rsp+318h+SystemTime.wDay]
0x18007d7f6  movzx   r10d, [rsp+318h+SystemTime.wMonth]
0x18007d7ff  movzx   r11d, [rsp+318h+SystemTime.wYear]
0x18007d808  mov     dword ptr [rsp+318h+var_2C8], eax
0x18007d80c  mov     dword ptr [rsp+318h+var_2D0], ecx
0x18007d810  mov     dword ptr [rsp+318h+var_2D8], r8d
0x18007d815  mov     dword ptr [rsp+318h+var_2E0], r9d
0x18007d81a  mov     dword ptr [rsp+318h+var_2E8], r10d
0x18007d81f  mov     dword ptr [rsp+318h+var_2F0], r11d
0x18007d824  lea     rax, [rsp+318h+sz]
0x18007d82c  mov     [rsp+318h+var_2F8], rax
0x18007d831  lea     r9, [rsp+318h+Dst]
0x18007d839  lea     r8, aSS04d02d02d02d; "%s\\%s_%04d_%02d_%02d_%02d_%02d_%02d.dm"...
0x18007d840  mov     rdx, rbx; unsigned __int64
0x18007d843  lea     rcx, word_1800D9420; unsigned __int16 *
0x18007d84a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007d84f  mov     ebx, eax
0x18007d851  mov     [rsp+318h+var_2B8], eax
0x18007d855  test    eax, eax
0x18007d857  js      short loc_18007D8B3
0x18007d859  xor     edx, edx; lpSecurityAttributes
0x18007d85b  lea     rcx, [rsp+318h+Dst]; lpPathName
0x18007d863  call    cs:__imp_CreateDirectoryW
0x18007d869  call    cs:__imp_GetCurrentProcessId
0x18007d86f  mov     r8d, eax
0x18007d872  lea     r9, word_1800D9420
0x18007d879  lea     rdx, aRundll32Comsvc; "RunDll32 comsvcs.dll,MiniDump"
0x18007d880  lea     rcx, aSDSFull; "%s %d %s full"
0x18007d887  call    ?FF_RunCmd@@YAJPEBGZZ; FF_RunCmd(ushort const *,...)
0x18007d88c  mov     ebx, eax
0x18007d88e  mov     [rsp+318h+var_2B8], eax
0x18007d892  test    eax, eax
0x18007d894  js      short loc_18007D8B3
0x18007d896  xor     edx, edx; AccessMode
0x18007d898  lea     rcx, word_1800D9420; FileName
0x18007d89f  call    cs:__imp__waccess
0x18007d8a5  mov     ecx, 80004005h
0x18007d8aa  test    eax, eax
0x18007d8ac  cmovnz  ebx, ecx
0x18007d8af  mov     [rsp+318h+var_2B8], ebx
0x18007d8b3  jmp     short loc_18007D8BA
0x18007d8b5  mov     ebx, 8000FFFFh
0x18007d8ba  mov     eax, ebx
0x18007d8bc  mov     rcx, [rsp+318h+var_18]
0x18007d8c4  xor     rcx, rsp; StackCookie
0x18007d8c7  call    __security_check_cookie
0x18007d8cc  add     rsp, 310h
0x18007d8d3  pop     rbx
0x18007d8d4  retn
0x1800838ea  push    rbp
0x1800838ec  sub     rsp, 60h
0x1800838f0  mov     rbp, rdx
0x1800838f3  add     rsp, 60h
0x1800838f7  pop     rbp
0x1800838f8  retn
```
