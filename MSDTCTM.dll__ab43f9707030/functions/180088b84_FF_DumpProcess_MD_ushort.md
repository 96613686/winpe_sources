# FF_DumpProcess_MD(ushort *)

- ea: `0x180088b84`
- end: `0x180088e29`
- name: `?FF_DumpProcess_MD@@YAJPEAG@Z`
- size: `677`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180088aa8`

## callees

- `0x180008a50`
- `0x180088b84`
- `0x180088e30`
- `0x18008902c`
- `0x18008921c`
- `0x1800b83d6`
- `0x1800b83ee`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180088d19`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180088d19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180088dbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180088dbd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180088c67`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180088c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088c8c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180088c82`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180088c82`
- `msvcrt!_waccess` at `0x180088df3`
- `msvcrt!_waccess` at `0x180088df3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180088db7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180088db7`

## string_xrefs

- `0x180088dcd`: `RunDll32 comsvcs.dll,MiniDump`

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
      local_unwind_0(v22, &loc_180088CED);
      return 2147942511LL;
    }
    FF_RemoveLegacyDump(sz, Dst, v17);
    GetLocalTime(&SystemTime);
    word_180167FB8 = 0;
    LODWORD(v13) = SystemTime.wSecond;
    LODWORD(v12) = SystemTime.wMinute;
    LODWORD(v11) = SystemTime.wHour;
    LODWORD(v10) = SystemTime.wDay;
    LODWORD(v9) = SystemTime.wMonth;
    LODWORD(v8) = SystemTime.wYear;
    DumpProperties = StringCchPrintfW(
                       &word_180167DB0,
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
    DumpProperties = FF_RunCmd(L"%s %d %s full", L"RunDll32 comsvcs.dll,MiniDump", CurrentProcessId, &word_180167DB0);
    v14 = DumpProperties;
    if ( DumpProperties < 0 )
      return (unsigned int)DumpProperties;
    if ( _waccess(&word_180167DB0, 0) )
      DumpProperties = -2147467259;
    goto LABEL_18;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v16 = LastError;
  v20 = LastError;
  local_unwind_0(v22, &loc_180088CBF);
  return v16;
}

```

## disassembly

```asm
0x180088b84  push    rbx
0x180088b86  sub     rsp, 310h
0x180088b8d  mov     rax, cs:__security_cookie
0x180088b94  xor     rax, rsp
0x180088b97  mov     [rsp+318h+var_18], rax
0x180088b9f  mov     [rsp+318h+var_290], rsp
0x180088ba7  xor     edx, edx; Val
0x180088ba9  lea     r8d, [rdx+50h]; Size
0x180088bad  lea     rcx, [rsp+318h+sz]; void *
0x180088bb5  call    memset_0
0x180088bba  xor     edx, edx; Val
0x180088bbc  mov     r8d, 20Ah; Size
0x180088bc2  lea     rcx, [rsp+318h+Dst]; void *
0x180088bca  call    memset_0
0x180088bcf  mov     [rsp+318h+lpSrc], 0
0x180088bd8  xorps   xmm0, xmm0
0x180088bdb  movups  xmmword ptr [rsp+318h+SystemTime.wYear], xmm0
0x180088be3  mov     [rsp+318h+var_2AC], 0Ah
0x180088beb  mov     [rsp+318h+var_2B4], 1
0x180088bf3  mov     [rsp+318h+rguid], 0
0x180088bfc  lea     r9, [rsp+318h+var_2AC]; unsigned int *
0x180088c01  lea     r8, [rsp+318h+lpSrc]; unsigned __int16 **
0x180088c06  lea     rdx, [rsp+318h+var_2B4]; int *
0x180088c0b  lea     rcx, [rsp+318h+rguid]; struct _GUID **
0x180088c10  call    ?FF_GetDumpProperties@@YAJPEAPEAU_GUID@@PEAHPEAPEAGPEAK@Z; FF_GetDumpProperties(_GUID * *,int *,ushort * *,ulong *)
0x180088c15  mov     ebx, eax
0x180088c17  mov     [rsp+318h+var_2B8], eax
0x180088c1b  test    eax, eax
0x180088c1d  jnz     loc_180088E07
0x180088c23  cmp     [rsp+318h+var_2B4], eax
0x180088c27  jnz     short loc_180088C33
0x180088c29  mov     ebx, 1
0x180088c2e  jmp     loc_180088E03
0x180088c33  mov     rcx, [rsp+318h+rguid]; rguid
0x180088c38  test    rcx, rcx
0x180088c3b  jz      short loc_180088C59
0x180088c3d  mov     rax, [rcx]
0x180088c40  sub     rax, cs:APPLID_SystemApplication
0x180088c47  jnz     short loc_180088C54
0x180088c49  mov     rax, [rcx+8]
0x180088c4d  sub     rax, cs:qword_18013A5A8
0x180088c54  test    rax, rax
0x180088c57  jz      short loc_180088C29
0x180088c59  mov     r8d, 28h ; '('; cchMax
0x180088c5f  lea     rdx, [rsp+318h+sz]; lpsz
0x180088c67  call    cs:__imp_StringFromGUID2
0x180088c6d  mov     ebx, 104h
0x180088c72  mov     r8d, ebx; nSize
0x180088c75  lea     rdx, [rsp+318h+Dst]; lpDst
0x180088c7d  mov     rcx, [rsp+318h+lpSrc]; lpSrc
0x180088c82  call    cs:__imp_ExpandEnvironmentStringsW
0x180088c88  test    eax, eax
0x180088c8a  jnz     short loc_180088CC8
0x180088c8c  call    cs:__imp_GetLastError
0x180088c92  test    eax, eax
0x180088c94  jle     short loc_180088C9E
0x180088c96  movzx   eax, ax
0x180088c99  or      eax, 80070000h
0x180088c9e  mov     [rsp+318h+var_2B0], eax
0x180088ca2  mov     [rsp+318h+var_298], eax
0x180088ca9  lea     rdx, loc_180088CBF
0x180088cb0  mov     rcx, [rsp+318h+var_290]
0x180088cb8  call    _local_unwind_0
0x180088cbd  nop
0x180088cbe  nop
0x180088cbf  mov     eax, [rsp+318h+var_2B0]
0x180088cc3  jmp     loc_180088E10
0x180088cc8  cmp     eax, ebx
0x180088cca  jbe     short loc_180088CF7
0x180088ccc  mov     [rsp+318h+var_294], 8007006Fh
0x180088cd7  lea     rdx, loc_180088CED
0x180088cde  mov     rcx, [rsp+318h+var_290]
0x180088ce6  call    _local_unwind_0
0x180088ceb  nop
0x180088cec  nop
0x180088ced  mov     eax, 8007006Fh
0x180088cf2  jmp     loc_180088E10
0x180088cf7  mov     r8d, [rsp+318h+var_2AC]; unsigned int
0x180088cfc  lea     rdx, [rsp+318h+Dst]; unsigned __int16 *
0x180088d04  lea     rcx, [rsp+318h+sz]; unsigned __int16 *
0x180088d0c  call    ?FF_RemoveLegacyDump@@YAXPEBG0K@Z; FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)
0x180088d11  lea     rcx, [rsp+318h+SystemTime]; lpSystemTime
0x180088d19  call    cs:__imp_GetLocalTime
0x180088d1f  xor     eax, eax
0x180088d21  mov     cs:word_180167FB8, ax
0x180088d28  movzx   eax, [rsp+318h+SystemTime.wSecond]
0x180088d30  movzx   ecx, [rsp+318h+SystemTime.wMinute]
0x180088d38  movzx   r8d, [rsp+318h+SystemTime.wHour]
0x180088d41  movzx   r9d, [rsp+318h+SystemTime.wDay]
0x180088d4a  movzx   r10d, [rsp+318h+SystemTime.wMonth]
0x180088d53  movzx   r11d, [rsp+318h+SystemTime.wYear]
0x180088d5c  mov     dword ptr [rsp+318h+var_2C8], eax
0x180088d60  mov     dword ptr [rsp+318h+var_2D0], ecx
0x180088d64  mov     dword ptr [rsp+318h+var_2D8], r8d
0x180088d69  mov     dword ptr [rsp+318h+var_2E0], r9d
0x180088d6e  mov     dword ptr [rsp+318h+var_2E8], r10d
0x180088d73  mov     dword ptr [rsp+318h+var_2F0], r11d
0x180088d78  lea     rax, [rsp+318h+sz]
0x180088d80  mov     [rsp+318h+var_2F8], rax
0x180088d85  lea     r9, [rsp+318h+Dst]
0x180088d8d  lea     r8, aSS04d02d02d02d; "%s\\%s_%04d_%02d_%02d_%02d_%02d_%02d.dm"...
0x180088d94  mov     rdx, rbx; unsigned __int64
0x180088d97  lea     rcx, word_180167DB0; unsigned __int16 *
0x180088d9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180088da3  mov     ebx, eax
0x180088da5  mov     [rsp+318h+var_2B8], eax
0x180088da9  test    eax, eax
0x180088dab  js      short loc_180088E07
0x180088dad  xor     edx, edx; lpSecurityAttributes
0x180088daf  lea     rcx, [rsp+318h+Dst]; lpPathName
0x180088db7  call    cs:__imp_CreateDirectoryW
0x180088dbd  call    cs:__imp_GetCurrentProcessId
0x180088dc3  mov     r8d, eax
0x180088dc6  lea     r9, word_180167DB0
0x180088dcd  lea     rdx, aRundll32Comsvc; "RunDll32 comsvcs.dll,MiniDump"
0x180088dd4  lea     rcx, aSDSFull; "%s %d %s full"
0x180088ddb  call    ?FF_RunCmd@@YAJPEBGZZ; FF_RunCmd(ushort const *,...)
0x180088de0  mov     ebx, eax
0x180088de2  mov     [rsp+318h+var_2B8], eax
0x180088de6  test    eax, eax
0x180088de8  js      short loc_180088E07
0x180088dea  xor     edx, edx; AccessMode
0x180088dec  lea     rcx, word_180167DB0; FileName
0x180088df3  call    cs:__imp__waccess
0x180088df9  mov     ecx, 80004005h
0x180088dfe  test    eax, eax
0x180088e00  cmovnz  ebx, ecx
0x180088e03  mov     [rsp+318h+var_2B8], ebx
0x180088e07  jmp     short loc_180088E0E
0x180088e09  mov     ebx, 8000FFFFh
0x180088e0e  mov     eax, ebx
0x180088e10  mov     rcx, [rsp+318h+var_18]
0x180088e18  xor     rcx, rsp; StackCookie
0x180088e1b  call    __security_check_cookie
0x180088e20  add     rsp, 310h
0x180088e27  pop     rbx
0x180088e28  retn
0x1800b98c0  push    rbp
0x1800b98c2  sub     rsp, 60h
0x1800b98c6  mov     rbp, rdx
0x1800b98c9  add     rsp, 60h
0x1800b98cd  pop     rbp
0x1800b98ce  retn
```
