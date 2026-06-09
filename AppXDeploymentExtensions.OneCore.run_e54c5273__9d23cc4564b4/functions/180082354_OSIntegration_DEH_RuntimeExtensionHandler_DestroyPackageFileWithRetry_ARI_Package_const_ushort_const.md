# OSIntegration::DEH::RuntimeExtensionHandler::DestroyPackageFileWithRetry(ARI::Package const &,ushort const *)

- ea: `0x180082354`
- end: `0x1800824f9`
- name: `?DestroyPackageFileWithRetry@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAJAEBVPackage@ARI@@PEBG@Z`
- size: `421`
- prototype: `int(OSIntegration::DEH::RuntimeExtensionHandler *__hidden this, const struct ARI::Package *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001be1c`
- `0x180048920`

## callees

- `0x18000e6e0`
- `0x18007efc8`
- `0x180082354`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800a2854`
- `0x1800a3a28`
- `0x1800cd2f8`
- `0x180128894`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008238a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800823c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008238a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800823c8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180082373`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180082373`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008237c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800823ba`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008237c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800823ba`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800823ad`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800823ad`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18008239a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18008239a`

## string_xrefs

- `0x1800823f3`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18008243e`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x1800824d7`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::RuntimeExtensionHandler::DestroyPackageFileWithRetry(
        OSIntegration::DEH::RuntimeExtensionHandler *this,
        const struct ARI::Package *a2,
        const unsigned __int16 *a3)
{
  unsigned int i; // esi
  DWORD LastError; // eax
  DWORD FileAttributesW; // eax
  unsigned int v9; // ebx
  struct Common::StringBuffer *v10; // r8
  __int64 v11; // rdx
  int v12; // ecx
  unsigned int v14; // [rsp+20h] [rbp-68h]
  __int128 v15; // [rsp+40h] [rbp-48h] BYREF
  int v16; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  for ( i = 0; i < 5; ++i )
  {
    if ( i )
      Sleep(0x64u);
    if ( DeleteFileW(a3) )
      return 0;
    LastError = GetLastError();
    if ( LastError == 8398 )
    {
      FileAttributesW = GetFileAttributesW(a3);
      if ( FileAttributesW != -1 && SetFileAttributesW(a3, FileAttributesW & 0xFFFFFFFE) && DeleteFileW(a3) )
        return 0;
      LastError = GetLastError();
    }
    if ( LastError == 2 || LastError == 3 || !LastError )
      return 0;
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x9BD,
           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
           (const char *)LastError,
           v14);
    if ( (v9 & 0x80000000) == 0 )
      return v9;
  }
  v15 = 0;
  v16 = 0;
  OSIntegration::Tools::FormatMessageInternal(v9, (Common::StringBuffer *)&v15, v10);
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x98C,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
    (const char *)v9,
    v14);
  if ( (byte_1802E21C6 & 0x40) != 0 )
    McTemplateU0zzdz_EventWriteTransfer(
      v12,
      (unsigned int)RuntimeDestroyDMRFileError,
      *((_QWORD *)a2 + 8),
      (_DWORD)a3,
      v9,
      *((__int64 *)&v15 + 1));
  details::appxLog<_SID const *,unsigned short const *,unsigned short const *,long>(
    v9,
    v11,
    RuntimeDestroyDMRFileError,
    *((_QWORD *)a2 + 8));
  if ( v9 == -2147024864 || v9 == -2147023672 || v9 == -2147024891 )
    OSIntegration::DEH::RuntimeExtensionHandler::LogDestroyDMRFileErrorDueToSharingViolation(
      this,
      (const unsigned __int16 *)v9,
      a2,
      a3);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v15);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x995,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
    (const char *)v9,
    (int)a3);
  return v9;
}

```

## disassembly

```asm
0x180082354  push    rbx
0x180082356  push    rbp
0x180082357  push    rsi
0x180082358  push    rdi
0x180082359  push    r14
0x18008235b  sub     rsp, 60h
0x18008235f  mov     rdi, r8
0x180082362  mov     rbp, rdx
0x180082365  mov     r14, rcx
0x180082368  xor     esi, esi
0x18008236a  test    esi, esi
0x18008236c  jz      short loc_180082379
0x18008236e  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180082373  call    cs:__imp_Sleep
0x180082379  mov     rcx, rdi; lpFileName
0x18008237c  call    cs:__imp_DeleteFileW
0x180082382  test    eax, eax
0x180082384  jnz     loc_1800824EA
0x18008238a  call    cs:__imp_GetLastError
0x180082390  cmp     eax, 20CEh
0x180082395  jnz     short loc_1800823CE
0x180082397  mov     rcx, rdi; lpFileName
0x18008239a  call    cs:__imp_GetFileAttributesW
0x1800823a0  cmp     eax, 0FFFFFFFFh
0x1800823a3  jz      short loc_1800823C8
0x1800823a5  and     eax, 0FFFFFFFEh
0x1800823a8  mov     edx, eax; dwFileAttributes
0x1800823aa  mov     rcx, rdi; lpFileName
0x1800823ad  call    cs:__imp_SetFileAttributesW
0x1800823b3  test    eax, eax
0x1800823b5  jz      short loc_1800823C8
0x1800823b7  mov     rcx, rdi; lpFileName
0x1800823ba  call    cs:__imp_DeleteFileW
0x1800823c0  test    eax, eax
0x1800823c2  jnz     loc_1800824EA
0x1800823c8  call    cs:__imp_GetLastError
0x1800823ce  cmp     eax, 2
0x1800823d1  jz      loc_1800824EA
0x1800823d7  cmp     eax, 3
0x1800823da  jz      loc_1800824EA
0x1800823e0  test    eax, eax
0x1800823e2  jz      loc_1800824EA
0x1800823e8  mov     rcx, [rsp+88h]; this
0x1800823f0  mov     r9d, eax; char *
0x1800823f3  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800823fa  mov     edx, 9BDh; void *
0x1800823ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180082404  mov     ebx, eax
0x180082406  test    eax, eax
0x180082408  jns     loc_1800824EC
0x18008240e  inc     esi
0x180082410  cmp     esi, 5
0x180082413  jb      loc_18008236A
0x180082419  xor     eax, eax
0x18008241b  xorps   xmm0, xmm0
0x18008241e  movups  [rsp+88h+var_48], xmm0
0x180082423  mov     [rsp+88h+var_38], eax
0x180082427  lea     rdx, [rsp+88h+var_48]; this
0x18008242c  mov     ecx, ebx; dwMessageId
0x18008242e  call    ?FormatMessageInternal@Tools@OSIntegration@@YAJJPEAVStringBuffer@Common@@@Z; OSIntegration::Tools::FormatMessageInternal(long,Common::StringBuffer *)
0x180082433  mov     rcx, [rsp+88h]; this
0x18008243b  mov     r9d, ebx; char *
0x18008243e  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180082445  mov     edx, 98Ch; void *
0x18008244a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008244f  mov     rsi, qword ptr [rsp+88h+var_48+8]
0x180082454  test    cs:byte_1802E21C6, 40h
0x18008245b  jz      short loc_180082479
0x18008245d  mov     [rsp+88h+var_60], rsi
0x180082462  mov     [rsp+88h+var_68], ebx
0x180082466  mov     r9, rdi
0x180082469  mov     r8, [rbp+40h]
0x18008246d  lea     rdx, RuntimeDestroyDMRFileError
0x180082474  call    McTemplateU0zzdz_EventWriteTransfer
0x180082479  mov     [rsp+88h+var_58], rsi
0x18008247e  mov     dword ptr [rsp+88h+var_60], ebx
0x180082482  mov     qword ptr [rsp+88h+var_68], rdi; int
0x180082487  mov     r9, [rbp+40h]
0x18008248b  lea     r8, RuntimeDestroyDMRFileError
0x180082492  mov     ecx, ebx
0x180082494  call    ??$appxLog@PEBU_SID@@PEBGPEBGJ@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBU_SID@@PEBG3J@Z; details::appxLog<_SID const *,ushort const *,ushort const *,long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,_SID const *,ushort const *,ushort const *,long)
0x180082499  cmp     ebx, 80070020h
0x18008249f  jz      short loc_1800824B1
0x1800824a1  cmp     ebx, 800704C8h
0x1800824a7  jz      short loc_1800824B1
0x1800824a9  cmp     ebx, 80070005h
0x1800824af  jnz     short loc_1800824C2
0x1800824b1  mov     r9, rdi; unsigned __int16 *
0x1800824b4  mov     r8, rbp; struct ARI::Package *
0x1800824b7  mov     edx, ebx; int
0x1800824b9  mov     rcx, r14; this
0x1800824bc  call    ?LogDestroyDMRFileErrorDueToSharingViolation@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAXJAEBVPackage@ARI@@PEBG@Z; OSIntegration::DEH::RuntimeExtensionHandler::LogDestroyDMRFileErrorDueToSharingViolation(long,ARI::Package const &,ushort const *)
0x1800824c1  nop
0x1800824c2  lea     rcx, [rsp+88h+var_48]; this
0x1800824c7  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800824cc  mov     rcx, [rsp+88h]; this
0x1800824d4  mov     r9d, ebx; char *
0x1800824d7  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800824de  mov     edx, 995h; void *
0x1800824e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800824e8  jmp     short loc_1800824EC
0x1800824ea  xor     ebx, ebx
0x1800824ec  mov     eax, ebx
0x1800824ee  add     rsp, 60h
0x1800824f2  pop     r14
0x1800824f4  pop     rdi
0x1800824f5  pop     rsi
0x1800824f6  pop     rbp
0x1800824f7  pop     rbx
0x1800824f8  retn
```
