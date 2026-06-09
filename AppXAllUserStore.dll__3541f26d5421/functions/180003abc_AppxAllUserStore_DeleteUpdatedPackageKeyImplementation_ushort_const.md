# AppxAllUserStore::DeleteUpdatedPackageKeyImplementation(ushort const *)

- ea: `0x180003abc`
- end: `0x180003be7`
- name: `?DeleteUpdatedPackageKeyImplementation@AppxAllUserStore@@YAJPEBG@Z`
- size: `299`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, __int64, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f970`

## callees

- `0x180003abc`
- `0x180004920`
- `0x180004968`
- `0x180006d40`
- `0x180007860`
- `0x180007a10`
- `0x180017f50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180003bb8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180003bb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b49`

## string_xrefs

- `0x180003ad7`: `UpdatedApplications`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::DeleteUpdatedPackageKeyImplementation(
        LPCWSTR lpSubKey,
        const unsigned __int16 *a2,
        __int64 a3,
        struct Common::StringBuffer *a4)
{
  int AllUserChildStorePath; // eax
  unsigned int v6; // ebx
  const WCHAR *v7; // rbx
  LSTATUS v8; // eax
  int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKeya[2]; // [rsp+30h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF

  v13 = 0;
  LOBYTE(a2) = 1;
  *(_OWORD *)lpSubKeya = 0;
  AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                            (AppxAllUserStore *)L"UpdatedApplications",
                            a2,
                            (unsigned int *)lpSubKeya,
                            a4);
  v6 = AllUserChildStorePath;
  if ( AllUserChildStorePath < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xEEF,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)(unsigned int)AllUserChildStorePath,
      phkResult);
    goto LABEL_11;
  }
  v7 = lpSubKeya[1];
  hKey = 0;
  Common::AutoHandleCloseHKEY<HKEY__ *>(0);
  hKey = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey);
  v6 = v8;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  if ( v6 != -2147024894 )
  {
    if ( (v6 & 0x80000000) == 0 )
    {
      RegDeleteTreeW(hKey, lpSubKey);
      Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
      if ( lpSubKeya[1] )
        Common::GlobalHeap::Free((void *)lpSubKeya[1]);
      return v6;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xEF5,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)v6,
      phkResulta);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
LABEL_11:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKeya);
    return v6;
  }
  Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
  if ( lpSubKeya[1] )
    Common::GlobalHeap::Free((void *)lpSubKeya[1]);
  return 0;
}

```

## disassembly

```asm
0x180003abc  mov     [rsp-8+arg_0], rbx
0x180003ac1  mov     [rsp-8+arg_10], rdi
0x180003ac6  push    rbp
0x180003ac7  mov     rbp, rsp
0x180003aca  sub     rsp, 50h
0x180003ace  mov     rdi, rcx
0x180003ad1  lea     r8, [rbp+lpSubKey]; bool
0x180003ad5  xor     eax, eax
0x180003ad7  lea     rcx, ?updatedApplicationsString@AppxAllUserStore@@3QBGB; "UpdatedApplications"
0x180003ade  xorps   xmm0, xmm0
0x180003ae1  mov     [rbp+var_10], eax
0x180003ae4  mov     dl, 1; unsigned __int16 *
0x180003ae6  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180003aea  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x180003aef  mov     ebx, eax
0x180003af1  test    eax, eax
0x180003af3  jns     short loc_180003B12
0x180003af5  mov     rcx, [rbp+8]; this
0x180003af9  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180003b00  mov     r9d, eax; char *
0x180003b03  mov     edx, 0EEFh; void *
0x180003b08  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003b0d  jmp     loc_180003BA6
0x180003b12  mov     rbx, [rbp+lpSubKey+8]
0x180003b16  xor     ecx, ecx
0x180003b18  mov     [rbp+hKey], 0
0x180003b20  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180003b25  lea     rax, [rbp+hKey]
0x180003b29  mov     [rbp+hKey], 0
0x180003b31  mov     r9d, 20019h; samDesired
0x180003b37  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180003b3c  xor     r8d, r8d; ulOptions
0x180003b3f  mov     rdx, rbx; lpSubKey
0x180003b42  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003b49  call    cs:__imp_RegOpenKeyExW
0x180003b4f  mov     ebx, eax
0x180003b51  test    eax, eax
0x180003b53  jle     short loc_180003B5E
0x180003b55  movzx   ebx, ax
0x180003b58  or      ebx, 80070000h
0x180003b5e  cmp     ebx, 80070002h
0x180003b64  jnz     short loc_180003B81
0x180003b66  mov     rcx, [rbp+hKey]
0x180003b6a  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180003b6f  mov     rcx, [rbp+lpSubKey+8]; void *
0x180003b73  test    rcx, rcx
0x180003b76  jz      short loc_180003B7D
0x180003b78  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180003b7d  xor     eax, eax
0x180003b7f  jmp     short loc_180003BD7
0x180003b81  test    ebx, ebx
0x180003b83  jns     short loc_180003BB1
0x180003b85  mov     rcx, [rbp+8]; this
0x180003b89  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180003b90  mov     r9d, ebx; char *
0x180003b93  mov     edx, 0EF5h; void *
0x180003b98  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003b9d  lea     rcx, [rbp+hKey]; this
0x180003ba1  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180003ba6  lea     rcx, [rbp+lpSubKey]; this
0x180003baa  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180003baf  jmp     short loc_180003BD5
0x180003bb1  mov     rcx, [rbp+hKey]; hKey
0x180003bb5  mov     rdx, rdi; lpSubKey
0x180003bb8  call    cs:__imp_RegDeleteTreeW
0x180003bbe  mov     rcx, [rbp+hKey]
0x180003bc2  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180003bc7  mov     rcx, [rbp+lpSubKey+8]; void *
0x180003bcb  test    rcx, rcx
0x180003bce  jz      short loc_180003BD5
0x180003bd0  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180003bd5  mov     eax, ebx
0x180003bd7  mov     rbx, [rsp+50h+arg_0]
0x180003bdc  mov     rdi, [rsp+50h+arg_10]
0x180003be1  add     rsp, 50h
0x180003be5  pop     rbp
0x180003be6  retn
```
