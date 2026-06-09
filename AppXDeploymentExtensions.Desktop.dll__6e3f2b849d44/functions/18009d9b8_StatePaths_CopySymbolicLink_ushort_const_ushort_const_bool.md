# StatePaths::CopySymbolicLink(ushort const *,ushort const *,bool)

- ea: `0x18009d9b8`
- end: `0x18009dd84`
- name: `?CopySymbolicLink@StatePaths@@YAJPEBG0_N@Z`
- size: `972`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008cf20`
- `0x1801890f0`
- `0x180189558`
- `0x18018a7b8`

## callees

- `0x18000669c`
- `0x180017ba0`
- `0x18001adb4`
- `0x1800225fc`
- `0x180050e60`
- `0x1800529ec`
- `0x18009d9b8`
- `0x18009dd8c`
- `0x1800af1bc`
- `0x1800af6f8`
- `0x180172e4c`
- `0x18017f324`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009da02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009dbd7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009da02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009dbd7`
- `KERNEL32!DeviceIoControl` at `0x18009da78`
- `KERNEL32!DeviceIoControl` at `0x18009da78`
- `KERNEL32!CreateSymbolicLinkW` at `0x18009dc9c`
- `KERNEL32!CreateSymbolicLinkW` at `0x18009dc9c`

## string_xrefs

- `0x18009da24`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009da8c`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009dae5`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009db2e`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009db8e`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009dbf6`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009dc6a`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009dcb0`: `onecore\admin\appmodel\common\statepaths.cpp`

## pseudocode

```c
__int64 __fastcall StatePaths::CopySymbolicLink(
        const WCHAR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  DWORD v3; // r15d
  HANDLE FileW; // rbx
  const char *v6; // r9
  unsigned int LastError; // ebx
  unsigned __int16 *v8; // rdi
  const char *v9; // r9
  int v10; // eax
  const struct std::nothrow_t *v11; // rdx
  WCHAR *v12; // rbx
  int v13; // eax
  int v14; // edi
  const struct std::nothrow_t *v15; // rdx
  int ParentFolderPath; // eax
  WCHAR *v17; // rdi
  const char *v18; // r9
  int v19; // esi
  const struct std::nothrow_t *v20; // rdx
  int v21; // eax
  WCHAR *v22; // rsi
  const char *v23; // r9
  unsigned int v24; // r14d
  const struct std::nothrow_t *v25; // rdx
  const struct std::nothrow_t *v26; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-49h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-49h]
  unsigned __int16 *v30; // [rsp+40h] [rbp-29h] BYREF
  HANDLE v31; // [rsp+48h] [rbp-21h] BYREF
  HANDLE v32; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v33[2]; // [rsp+58h] [rbp-11h] BYREF
  LPCWSTR lpTargetFileName[2]; // [rsp+68h] [rbp-1h] BYREF
  int v35; // [rsp+78h] [rbp+Fh]
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp+17h] BYREF
  int v37; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD BytesReturned; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = (unsigned __int8)a3;
  FileW = CreateFileW(this, 8u, 7u, 0, 3u, 0x2200000u, 0);
  v32 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1FA,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
                  v6);
    goto LABEL_50;
  }
  v8 = (unsigned __int16 *)operator new[](0x8000u);
  v30 = v8;
  BytesReturned = 0;
  if ( !DeviceIoControl(FileW, 0x900A8u, 0, 0, v8, 0x8000u, &BytesReturned, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x201,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
                  v9);
LABEL_5:
    wistd::unique_ptr<unsigned short,wistd::default_delete<unsigned short>>::reset(&v30);
    goto LABEL_50;
  }
  *(_OWORD *)lpFileName = 0;
  v37 = 0;
  v10 = Common::StringBuffer::SetValue(
          (Common::StringBuffer *)lpFileName,
          &v8[((unsigned __int64)v8[4] >> 1) + 10],
          v8[5] >> 1);
  LastError = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)(unsigned int)v10,
      dwCreationDisposition);
    if ( lpFileName[1] )
      operator delete((void *)lpFileName[1], v11);
    goto LABEL_5;
  }
  *(_OWORD *)lpTargetFileName = 0;
  v35 = 0;
  v12 = (WCHAR *)lpFileName[1];
  v13 = ConvertNtPathToDosPath(lpFileName[1], (struct Common::StringBuffer *)lpTargetFileName);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)(unsigned int)v13,
      dwCreationDisposition);
LABEL_11:
    if ( lpTargetFileName[1] )
      operator delete((void *)lpTargetFileName[1], v15);
    if ( v12 )
      operator delete(v12, v15);
    wistd::unique_ptr<unsigned short,wistd::default_delete<unsigned short>>::reset(&v30);
    LastError = v14;
    goto LABEL_50;
  }
  *(_OWORD *)lpFileName = 0;
  v37 = 0;
  ParentFolderPath = Common::PathHelpers::GetParentFolderPath(a2, (struct Common::StringBuffer *)lpFileName);
  v14 = ParentFolderPath;
  if ( ParentFolderPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20D,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)(unsigned int)ParentFolderPath,
      dwCreationDisposition);
    if ( lpFileName[1] )
      operator delete((void *)lpFileName[1], v15);
    goto LABEL_11;
  }
  v17 = (WCHAR *)lpFileName[1];
  v31 = CreateFileW(lpFileName[1], 0xC0000000, 1u, 0, 3u, 0x2000000u, 0);
  if ( (((unsigned __int64)v31 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v19 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x213,
            (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
            v18);
LABEL_21:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v31);
    if ( v17 )
      operator delete(v17, v20);
    if ( lpTargetFileName[1] )
      operator delete((void *)lpTargetFileName[1], v20);
    if ( v12 )
      operator delete(v12, v20);
    wistd::unique_ptr<unsigned short,wistd::default_delete<unsigned short>>::reset(&v30);
    LastError = v19;
    goto LABEL_50;
  }
  v33[0] = 0;
  v33[1] = 0;
  v21 = Common::ImpersonationContext::Impersonate((Common::ImpersonationContext *)v33, 0);
  v19 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x215,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)(unsigned int)v21,
      dwCreationDispositiona);
    if ( LODWORD(v33[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v33);
    goto LABEL_21;
  }
  v22 = (WCHAR *)lpTargetFileName[1];
  if ( CreateSymbolicLinkW(a2, lpTargetFileName[1], v3) )
  {
    if ( LODWORD(v33[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v33);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v31);
    if ( v17 )
      operator delete(v17, v26);
    if ( v22 )
      operator delete(v22, v26);
    if ( v12 )
      operator delete(v12, v26);
    wistd::unique_ptr<unsigned short,wistd::default_delete<unsigned short>>::reset(&v30);
    LastError = 0;
  }
  else
  {
    v24 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x217,
            (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
            v23);
    if ( LODWORD(v33[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v33);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v31);
    if ( v17 )
      operator delete(v17, v25);
    if ( v22 )
      operator delete(v22, v25);
    if ( v12 )
      operator delete(v12, v25);
    wistd::unique_ptr<unsigned short,wistd::default_delete<unsigned short>>::reset(&v30);
    LastError = v24;
  }
LABEL_50:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
  return LastError;
}

```

## disassembly

```asm
0x18009d9b8  mov     [rsp-8+arg_0], rbx
0x18009d9bd  mov     [rsp-8+arg_8], rsi
0x18009d9c2  push    rbp
0x18009d9c3  push    rdi
0x18009d9c4  push    r12
0x18009d9c6  push    r14
0x18009d9c8  push    r15
0x18009d9ca  lea     rbp, [rsp-37h]
0x18009d9cf  sub     rsp, 0A0h
0x18009d9d6  movzx   r15d, r8b
0x18009d9da  mov     r14, rdx
0x18009d9dd  xor     r12d, r12d
0x18009d9e0  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x18009d9e5  mov     [rsp+0C0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18009d9ed  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18009d9f5  xor     r9d, r9d; lpSecurityAttributes
0x18009d9f8  lea     edx, [r12+8]; dwDesiredAccess
0x18009d9fd  lea     r8d, [r12+7]; dwShareMode
0x18009da02  call    cs:__imp_CreateFileW
0x18009da09  nop     dword ptr [rax+rax+00h]
0x18009da0e  mov     rbx, rax
0x18009da11  mov     [rbp+57h+var_70], rax
0x18009da15  inc     rax
0x18009da18  test    rax, 0FFFFFFFFFFFFFFFEh
0x18009da1e  jnz     short loc_18009DA3C
0x18009da20  mov     rcx, [rbp+5Fh]; this
0x18009da24  lea     r8, aOnecoreAdminAp_56; "onecore\\admin\\appmodel\\common\\state"...
0x18009da2b  mov     edx, 1FAh; void *
0x18009da30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009da35  mov     ebx, eax
0x18009da37  jmp     loc_18009DD5C
0x18009da3c  mov     esi, 8000h
0x18009da41  mov     ecx, esi; unsigned __int64
0x18009da43  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009da48  mov     rdi, rax
0x18009da4b  mov     [rbp+57h+var_80], rax
0x18009da4f  mov     [rbp+57h+BytesReturned], r12d
0x18009da53  mov     [rsp+0C0h+lpOverlapped], r12; lpOverlapped
0x18009da58  lea     rax, [rbp+57h+BytesReturned]
0x18009da5c  mov     [rsp+0C0h+hTemplateFile], rax; lpBytesReturned
0x18009da61  mov     [rsp+0C0h+dwFlagsAndAttributes], esi; nOutBufferSize
0x18009da65  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdi; int
0x18009da6a  xor     r9d, r9d; nInBufferSize
0x18009da6d  xor     r8d, r8d; lpInBuffer
0x18009da70  mov     edx, 900A8h; dwIoControlCode
0x18009da75  mov     rcx, rbx; hDevice
0x18009da78  call    cs:__imp_DeviceIoControl
0x18009da7f  nop     dword ptr [rax+rax+00h]
0x18009da84  test    eax, eax
0x18009da86  jnz     short loc_18009DAAD
0x18009da88  mov     rcx, [rbp+5Fh]; this
0x18009da8c  lea     r8, aOnecoreAdminAp_56; "onecore\\admin\\appmodel\\common\\state"...
0x18009da93  mov     edx, 201h; void *
0x18009da98  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009da9d  mov     ebx, eax
0x18009da9f  lea     rcx, [rbp+57h+var_80]
0x18009daa3  call    ?reset@?$unique_ptr@GU?$default_delete@G@wistd@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wistd::default_delete<ushort>>::reset(ushort *)
0x18009daa8  jmp     loc_18009DD5C
0x18009daad  xorps   xmm0, xmm0
0x18009dab0  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18009dab4  mov     [rbp+57h+var_30], r12d
0x18009dab8  movzx   r8d, word ptr [rdi+0Ah]
0x18009dabd  shr     r8d, 1; unsigned int
0x18009dac0  movzx   eax, word ptr [rdi+8]
0x18009dac4  shr     rax, 1
0x18009dac7  add     rax, 0Ah
0x18009dacb  lea     rdx, [rdi+rax*2]; unsigned __int16 *
0x18009dacf  lea     rcx, [rbp+57h+lpFileName]; this
0x18009dad3  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18009dad8  mov     ebx, eax
0x18009dada  test    eax, eax
0x18009dadc  jns     short loc_18009DB06
0x18009dade  mov     rcx, [rbp+5Fh]; this
0x18009dae2  mov     r9d, eax; char *
0x18009dae5  lea     r8, aOnecoreAdminAp_56; "onecore\\admin\\appmodel\\common\\state"...
0x18009daec  mov     edx, 206h; void *
0x18009daf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009daf6  mov     rcx, [rbp+57h+lpFileName+8]; void *
0x18009dafa  test    rcx, rcx
0x18009dafd  jz      short loc_18009DA9F
0x18009daff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009db04  jmp     short loc_18009DA9F
0x18009db06  xorps   xmm0, xmm0
0x18009db09  movups  xmmword ptr [rbp+57h+lpTargetFileName], xmm0
0x18009db0d  mov     [rbp+57h+var_48], r12d
0x18009db11  lea     rdx, [rbp+57h+lpTargetFileName]; this
0x18009db15  mov     rbx, [rbp+57h+lpFileName+8]
0x18009db19  mov     rcx, rbx; SourceString
0x18009db1c  call    ?ConvertNtPathToDosPath@@YAJPEBGAEAVStringBuffer@Common@@@Z; ConvertNtPathToDosPath(ushort const *,Common::StringBuffer &)
0x18009db21  mov     edi, eax
0x18009db23  test    eax, eax
0x18009db25  jns     short loc_18009DB6A
0x18009db27  mov     rcx, [rbp+5Fh]; this
0x18009db2b  mov     r9d, eax; char *
0x18009db2e  lea     r8, aOnecoreAdminAp_56; "onecore\\admin\\appmodel\\common\\state"...
0x18009db35  mov     edx, 209h; void *
0x18009db3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009db3f  mov     rcx, [rbp+57h+lpTargetFileName+8]; void *
0x18009db43  test    rcx, rcx
0x18009db46  jz      short loc_18009DB4D
0x18009db48  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009db4d  test    rbx, rbx
0x18009db50  jz      short loc_18009DB5A
0x18009db52  mov     rcx, rbx; void *
0x18009db55  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009db5a  lea     rcx, [rbp+57h+var_80]
0x18009db5e  call    ?reset@?$unique_ptr@GU?$default_delete@G@wistd@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wistd::default_delete<ushort>>::reset(ushort *)
0x18009db63  mov     ebx, edi
0x18009db65  jmp     loc_18009DD5C
0x18009db6a  xorps   xmm0, xmm0
0x18009db6d  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18009db71  mov     [rbp+57h+var_30], r12d
0x18009db75  lea     rdx, [rbp+57h+lpFileName]; this
0x18009db79  mov     rcx, r14; unsigned __int16 *
0x18009db7c  call    ?GetParentFolderPath@PathHelpers@Common@@SAJPEBGPEAVStringBuffer@2@@Z; Common::PathHelpers::GetParentFolderPath(ushort const *,Common::StringBuffer *)
0x18009db81  mov     edi, eax
0x18009db83  test    eax, eax
0x18009db85  jns     short loc_18009DBAF
0x18009db87  mov     rcx, [rbp+5Fh]; this
0x18009db8b  mov     r9d, eax; char *
0x18009db8e  lea     r8, aOnecoreAdminAp_56; "onecore\\admin\\appmodel\\common\\state"...
0x18009db95  mov     edx, 20Dh; void *
0x18009db9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009db9f  mov     rcx, [rbp+57h+lpFileName+8]; void *
0x18009dba3  test    rcx, rcx
0x18009dba6  jz      short loc_18009DB3F
0x18009dba8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dbad  jmp     short loc_18009DB3F
0x18009dbaf  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x18009dbb4  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18009dbbc  mov     [rsp+0C0h+dwCreationDisposition], 3; int
0x18009dbc4  xor     r9d, r9d; lpSecurityAttributes
0x18009dbc7  mov     edx, 0C0000000h; dwDesiredAccess
0x18009dbcc  lea     r8d, [r9+1]; dwShareMode
0x18009dbd0  mov     rdi, [rbp+57h+lpFileName+8]
0x18009dbd4  mov     rcx, rdi; lpFileName
0x18009dbd7  call    cs:__imp_CreateFileW
0x18009dbde  nop     dword ptr [rax+rax+00h]
0x18009dbe3  mov     [rbp+57h+var_78], rax
0x18009dbe7  inc     rax
0x18009dbea  test    rax, 0FFFFFFFFFFFFFFFEh
0x18009dbf0  jnz     short loc_18009DC4A
0x18009dbf2  mov     rcx, [rbp+5Fh]; this
0x18009dbf6  lea     r8, aOnecoreAdminAp_56; "onecore\\admin\\appmodel\\common\\state"...
0x18009dbfd  mov     edx, 213h; void *
0x18009dc02  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009dc07  mov     esi, eax
0x18009dc09  lea     rcx, [rbp+57h+var_78]
0x18009dc0d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dc12  test    rdi, rdi
0x18009dc15  jz      short loc_18009DC1F
0x18009dc17  mov     rcx, rdi; void *
0x18009dc1a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dc1f  mov     rcx, [rbp+57h+lpTargetFileName+8]; void *
0x18009dc23  test    rcx, rcx
0x18009dc26  jz      short loc_18009DC2D
0x18009dc28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dc2d  test    rbx, rbx
0x18009dc30  jz      short loc_18009DC3A
0x18009dc32  mov     rcx, rbx; void *
0x18009dc35  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dc3a  lea     rcx, [rbp+57h+var_80]
0x18009dc3e  call    ?reset@?$unique_ptr@GU?$default_delete@G@wistd@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wistd::default_delete<ushort>>::reset(ushort *)
0x18009dc43  mov     ebx, esi
0x18009dc45  jmp     loc_18009DD5C
0x18009dc4a  mov     [rbp+57h+var_68], r12
0x18009dc4e  mov     [rbp+57h+var_60], r12
0x18009dc52  xor     edx, edx; void *
0x18009dc54  lea     rcx, [rbp+57h+var_68]; this
0x18009dc58  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x18009dc5d  mov     esi, eax
0x18009dc5f  test    eax, eax
0x18009dc61  jns     short loc_18009DC8F
0x18009dc63  mov     rcx, [rbp+5Fh]; this
0x18009dc67  mov     r9d, eax; char *
0x18009dc6a  lea     r8, aOnecoreAdminAp_56; "onecore\\admin\\appmodel\\common\\state"...
0x18009dc71  mov     edx, 215h; void *
0x18009dc76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009dc7b  cmp     dword ptr [rbp+57h+var_68], r12d
0x18009dc7f  jz      short loc_18009DC09
0x18009dc81  lea     rcx, [rbp+57h+var_68]; this
0x18009dc85  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18009dc8a  jmp     loc_18009DC09
0x18009dc8f  mov     r8d, r15d; dwFlags
0x18009dc92  mov     rsi, [rbp+57h+lpTargetFileName+8]
0x18009dc96  mov     rdx, rsi; lpTargetFileName
0x18009dc99  mov     rcx, r14; lpSymlinkFileName
0x18009dc9c  call    cs:__imp_CreateSymbolicLinkW
0x18009dca3  nop     dword ptr [rax+rax+00h]
0x18009dca8  test    al, al
0x18009dcaa  jnz     short loc_18009DD11
0x18009dcac  mov     rcx, [rbp+5Fh]; this
0x18009dcb0  lea     r8, aOnecoreAdminAp_56; "onecore\\admin\\appmodel\\common\\state"...
0x18009dcb7  mov     edx, 217h; void *
0x18009dcbc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009dcc1  mov     r14d, eax
0x18009dcc4  cmp     dword ptr [rbp+57h+var_68], r12d
0x18009dcc8  jz      short loc_18009DCD3
0x18009dcca  lea     rcx, [rbp+57h+var_68]; this
0x18009dcce  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18009dcd3  lea     rcx, [rbp+57h+var_78]
0x18009dcd7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dcdc  test    rdi, rdi
0x18009dcdf  jz      short loc_18009DCE9
0x18009dce1  mov     rcx, rdi; void *
0x18009dce4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dce9  test    rsi, rsi
0x18009dcec  jz      short loc_18009DCF6
0x18009dcee  mov     rcx, rsi; void *
0x18009dcf1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dcf6  test    rbx, rbx
0x18009dcf9  jz      short loc_18009DD03
0x18009dcfb  mov     rcx, rbx; void *
0x18009dcfe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dd03  lea     rcx, [rbp+57h+var_80]
0x18009dd07  call    ?reset@?$unique_ptr@GU?$default_delete@G@wistd@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wistd::default_delete<ushort>>::reset(ushort *)
0x18009dd0c  mov     ebx, r14d
0x18009dd0f  jmp     short loc_18009DD5C
0x18009dd11  cmp     dword ptr [rbp+57h+var_68], r12d
0x18009dd15  jz      short loc_18009DD20
0x18009dd17  lea     rcx, [rbp+57h+var_68]; this
0x18009dd1b  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18009dd20  lea     rcx, [rbp+57h+var_78]
0x18009dd24  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dd29  test    rdi, rdi
0x18009dd2c  jz      short loc_18009DD36
0x18009dd2e  mov     rcx, rdi; void *
0x18009dd31  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dd36  test    rsi, rsi
0x18009dd39  jz      short loc_18009DD43
0x18009dd3b  mov     rcx, rsi; void *
0x18009dd3e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dd43  test    rbx, rbx
0x18009dd46  jz      short loc_18009DD50
0x18009dd48  mov     rcx, rbx; void *
0x18009dd4b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009dd50  lea     rcx, [rbp+57h+var_80]
0x18009dd54  call    ?reset@?$unique_ptr@GU?$default_delete@G@wistd@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wistd::default_delete<ushort>>::reset(ushort *)
0x18009dd59  mov     ebx, r12d
0x18009dd5c  lea     rcx, [rbp+57h+var_70]
0x18009dd60  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dd65  mov     eax, ebx
0x18009dd67  lea     r11, [rsp+0C0h+var_20]
0x18009dd6f  mov     rbx, [r11+30h]
0x18009dd73  mov     rsi, [r11+38h]
0x18009dd77  mov     rsp, r11
0x18009dd7a  pop     r15
0x18009dd7c  pop     r14
0x18009dd7e  pop     r12
0x18009dd80  pop     rdi
0x18009dd81  pop     rbp
0x18009dd82  retn
```
