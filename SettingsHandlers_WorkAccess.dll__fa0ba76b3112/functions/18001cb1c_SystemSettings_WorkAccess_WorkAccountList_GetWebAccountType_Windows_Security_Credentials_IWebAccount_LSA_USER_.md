# SystemSettings::WorkAccess::WorkAccountList::GetWebAccountType(Windows::Security::Credentials::IWebAccount *,_LSA_USER_ACCOUNT_TYPE *)

- ea: `0x18001cb1c`
- end: `0x18001cdca`
- name: `?GetWebAccountType@WorkAccountList@WorkAccess@SystemSettings@@AEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEAW4_LSA_USER_ACCOUNT_TYPE@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::WorkAccountList *__hidden this, struct Windows::Security::Credentials::IWebAccount *, enum _LSA_USER_ACCOUNT_TYPE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d5c0`

## callees

- `0x1800096cc`
- `0x1800096ec`
- `0x18001bf08`
- `0x18001cb1c`
- `0x18001f198`
- `0x18001f6b8`
- `0x18001f81c`
- `0x180020584`
- `0x1800208f8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cbb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cbb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cb82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cdab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cb82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cdab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cbf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cc11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cd79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cd8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cbf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cc11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cd79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cd8e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001cc46`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001cd0d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001cc46`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001cd0d`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18001cd40`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18001cd40`

## string_xrefs

- `0x18001cbde`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001cd21`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::GetWebAccountType(
        SystemSettings::WorkAccess::WorkAccountList *this,
        struct Windows::Security::Credentials::IWebAccount *a2,
        enum _LSA_USER_ACCOUNT_TYPE *a3)
{
  __int64 (__fastcall *v5)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *); // rbx
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rdx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // rdi
  void *v12; // rcx
  void *v13; // rcx
  const char *v14; // r9
  int LastError; // eax
  int v16; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  unsigned __int16 **ReferencedDomainName; // [rsp+20h] [rbp-49h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-49h]
  unsigned __int64 *cchReferencedDomainName; // [rsp+28h] [rbp-41h]
  unsigned int peUse; // [rsp+30h] [rbp-39h]
  HLOCAL Sid; // [rsp+40h] [rbp-29h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v26; // [rsp+50h] [rbp-19h] BYREF
  LPCWSTR lpAccountName[5]; // [rsp+58h] [rbp-11h] BYREF
  char v28; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD cbSid; // [rsp+D0h] [rbp+67h] BYREF
  int v31; // [rsp+D4h] [rbp+6Bh]
  DWORD v32; // [rsp+D8h] [rbp+6Fh] BYREF
  enum _SID_NAME_USE v33; // [rsp+E0h] [rbp+77h] BYREF
  HLOCAL hMem; // [rsp+E8h] [rbp+7Fh] BYREF

  v31 = HIDWORD(this);
  *(_DWORD *)a3 = 0;
  string = 0;
  memset(lpAccountName, 0, 24);
  Sid = 0;
  cbSid = 0;
  hMem = 0;
  v32 = 0;
  v33 = 0;
  lpAccountName[3] = (LPCWSTR)&hMem;
  lpAccountName[4] = (LPCWSTR)&Sid;
  v28 = 1;
  v5 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(a2, &string);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 659;
LABEL_5:
    v10 = (unsigned int)v6;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)v10,
      (int)ReferencedDomainName);
LABEL_7:
    if ( hMem )
      LocalFree(hMem);
    if ( Sid )
      LocalFree(Sid);
    goto LABEL_31;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         lpAccountName,
         StringRawBuffer,
         -1);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 660;
    goto LABEL_5;
  }
  if ( LookupAccountNameW(0, lpAccountName[0], 0, &cbSid, 0, &v32, &v33) || !cbSid )
    goto LABEL_26;
  v11 = 2LL * v32;
  hMem = 0;
  if ( v11 + 1 < v11 )
  {
    v7 = -2147024362;
LABEL_25:
    v10 = (unsigned int)v7;
    v8 = 664;
    goto LABEL_6;
  }
  v26 = 0;
  v7 = ULongLongMult(v11 + 1, 2u, &v26);
  if ( v7 >= 0 )
    v7 = CTLocalAllocPolicy::Alloc(v12, 0, v26, &hMem);
  if ( v7 < 0 )
    goto LABEL_25;
  StringCchCopyNExW((unsigned __int16 *)hMem, v11 + 1, 0, v11, ReferencedDomainName, cchReferencedDomainName, peUse);
  v6 = CTLocalAllocPolicy::Alloc(v13, 0x40u, cbSid, &Sid);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 665;
    goto LABEL_5;
  }
  if ( !LookupAccountNameW(0, lpAccountName[0], Sid, &cbSid, (LPWSTR)hMem, &v32, &v33) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x29A,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
                  v14);
LABEL_21:
    v7 = LastError;
    goto LABEL_7;
  }
  v16 = LsaLookupUserAccountType(Sid, a3);
  if ( v16 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  v17,
                  v18,
                  (const char *)(unsigned int)v16,
                  ReferencedDomainNamea);
    goto LABEL_21;
  }
LABEL_26:
  if ( hMem )
    LocalFree(hMem);
  if ( Sid )
    LocalFree(Sid);
  v7 = 0;
LABEL_31:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpAccountName);
  WindowsDeleteString(string);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001cb1c  mov     qword ptr [rsp-8+cbSid], rcx
0x18001cb21  push    rbp
0x18001cb22  push    rbx
0x18001cb23  push    rsi
0x18001cb24  push    rdi
0x18001cb25  push    r14
0x18001cb27  push    r15
0x18001cb29  lea     rbp, [rsp-2Fh]
0x18001cb2e  sub     rsp, 98h
0x18001cb35  mov     r14, r8
0x18001cb38  mov     rdi, rdx
0x18001cb3b  xor     r15d, r15d
0x18001cb3e  mov     [r8], r15d
0x18001cb41  mov     [rbp+57h+string], r15
0x18001cb45  mov     [rbp+57h+lpAccountName], r15
0x18001cb49  mov     [rbp+57h+var_60], r15
0x18001cb4d  mov     [rbp+57h+var_58], r15
0x18001cb51  mov     [rbp+57h+Sid], r15
0x18001cb55  mov     [rbp+57h+cbSid], r15d
0x18001cb59  mov     [rbp+57h+hMem], r15
0x18001cb5d  mov     [rbp+57h+arg_8], r15d
0x18001cb61  mov     [rbp+57h+arg_10], r15d
0x18001cb65  lea     rax, [rbp+57h+hMem]
0x18001cb69  mov     [rbp+57h+var_50], rax
0x18001cb6d  lea     rax, [rbp+57h+Sid]
0x18001cb71  mov     [rbp+57h+var_48], rax
0x18001cb75  mov     [rbp+57h+var_40], 1
0x18001cb79  mov     rax, [rdx]
0x18001cb7c  mov     rbx, [rax+38h]
0x18001cb80  xor     ecx, ecx; string
0x18001cb82  call    cs:__imp_WindowsDeleteString
0x18001cb89  nop     dword ptr [rax+rax+00h]
0x18001cb8e  mov     [rbp+57h+string], r15
0x18001cb92  lea     rdx, [rbp+57h+string]
0x18001cb96  mov     rcx, rdi
0x18001cb99  mov     rax, rbx
0x18001cb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cba1  mov     ebx, eax
0x18001cba3  test    eax, eax
0x18001cba5  jns     short loc_18001CBAE
0x18001cba7  mov     edx, 293h
0x18001cbac  jmp     short loc_18001CBDB
0x18001cbae  xor     edx, edx; length
0x18001cbb0  mov     rcx, [rbp+57h+string]; string
0x18001cbb4  call    cs:__imp_WindowsGetStringRawBuffer
0x18001cbbb  nop     dword ptr [rax+rax+00h]
0x18001cbc0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001cbc4  mov     rdx, rax
0x18001cbc7  lea     rcx, [rbp+57h+lpAccountName]
0x18001cbcb  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001cbd0  mov     ebx, eax
0x18001cbd2  test    eax, eax
0x18001cbd4  jns     short loc_18001CC22
0x18001cbd6  mov     edx, 294h; void *
0x18001cbdb  mov     r9d, eax; char *
0x18001cbde  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001cbe5  mov     rcx, [rbp+5Fh]; this
0x18001cbe9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cbee  nop
0x18001cbef  mov     rcx, [rbp+57h+hMem]; hMem
0x18001cbf3  test    rcx, rcx
0x18001cbf6  jz      short loc_18001CC04
0x18001cbf8  call    cs:__imp_LocalFree
0x18001cbff  nop     dword ptr [rax+rax+00h]
0x18001cc04  mov     rcx, [rbp+57h+Sid]; hMem
0x18001cc08  test    rcx, rcx
0x18001cc0b  jz      loc_18001CD9D
0x18001cc11  call    cs:__imp_LocalFree
0x18001cc18  nop     dword ptr [rax+rax+00h]
0x18001cc1d  jmp     loc_18001CD9D
0x18001cc22  lea     rax, [rbp+57h+arg_10]
0x18001cc26  mov     qword ptr [rsp+0C0h+peUse], rax; unsigned int
0x18001cc2b  lea     rax, [rbp+57h+arg_8]
0x18001cc2f  mov     [rsp+0C0h+cchReferencedDomainName], rax; unsigned __int64 *
0x18001cc34  mov     [rsp+0C0h+ReferencedDomainName], r15; unsigned __int16 **
0x18001cc39  lea     r9, [rbp+57h+cbSid]; cbSid
0x18001cc3d  xor     r8d, r8d; Sid
0x18001cc40  mov     rdx, [rbp+57h+lpAccountName]; lpAccountName
0x18001cc44  xor     ecx, ecx; lpSystemName
0x18001cc46  call    cs:__imp_LookupAccountNameW
0x18001cc4d  nop     dword ptr [rax+rax+00h]
0x18001cc52  test    eax, eax
0x18001cc54  jnz     loc_18001CD70
0x18001cc5a  cmp     [rbp+57h+cbSid], r15d
0x18001cc5e  jbe     loc_18001CD70
0x18001cc64  mov     eax, [rbp+57h+arg_8]
0x18001cc67  lea     rdi, [rax+rax]
0x18001cc6b  mov     [rbp+57h+hMem], r15
0x18001cc6f  lea     rsi, [rdi+1]
0x18001cc73  cmp     rsi, rdi
0x18001cc76  jb      loc_18001CD5E
0x18001cc7c  mov     [rbp+57h+var_70], r15
0x18001cc80  lea     r8, [rbp+57h+var_70]; unsigned __int64 *
0x18001cc84  mov     edx, 2; unsigned __int64
0x18001cc89  mov     rcx, rsi; unsigned __int64
0x18001cc8c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001cc91  mov     ebx, eax
0x18001cc93  test    eax, eax
0x18001cc95  js      short loc_18001CCA8
0x18001cc97  lea     r9, [rbp+57h+hMem]; void **
0x18001cc9b  mov     r8, [rbp+57h+var_70]; unsigned __int64
0x18001cc9f  xor     edx, edx; unsigned int
0x18001cca1  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001cca6  mov     ebx, eax
0x18001cca8  test    ebx, ebx
0x18001ccaa  js      loc_18001CD63
0x18001ccb0  mov     r9, rdi; unsigned __int64
0x18001ccb3  xor     r8d, r8d; unsigned __int16 *
0x18001ccb6  mov     rdx, rsi; unsigned __int64
0x18001ccb9  mov     rcx, [rbp+57h+hMem]; unsigned __int16 *
0x18001ccbd  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18001ccc2  mov     r8d, [rbp+57h+cbSid]; unsigned __int64
0x18001ccc6  lea     r9, [rbp+57h+Sid]; void **
0x18001ccca  mov     edx, 40h ; '@'; unsigned int
0x18001cccf  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001ccd4  mov     ebx, eax
0x18001ccd6  test    eax, eax
0x18001ccd8  jns     short loc_18001CCE4
0x18001ccda  mov     edx, 299h
0x18001ccdf  jmp     loc_18001CBDB
0x18001cce4  mov     rax, [rbp+57h+hMem]
0x18001cce8  lea     rcx, [rbp+57h+arg_10]
0x18001ccec  mov     qword ptr [rsp+0C0h+peUse], rcx; peUse
0x18001ccf1  lea     rcx, [rbp+57h+arg_8]
0x18001ccf5  mov     [rsp+0C0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18001ccfa  mov     [rsp+0C0h+ReferencedDomainName], rax; int
0x18001ccff  lea     r9, [rbp+57h+cbSid]; cbSid
0x18001cd03  mov     r8, [rbp+57h+Sid]; Sid
0x18001cd07  mov     rdx, [rbp+57h+lpAccountName]; lpAccountName
0x18001cd0b  xor     ecx, ecx; lpSystemName
0x18001cd0d  call    cs:__imp_LookupAccountNameW
0x18001cd14  nop     dword ptr [rax+rax+00h]
0x18001cd19  test    eax, eax
0x18001cd1b  jnz     short loc_18001CD39
0x18001cd1d  mov     rcx, [rbp+5Fh]; this
0x18001cd21  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001cd28  mov     edx, 29Ah; void *
0x18001cd2d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001cd32  mov     ebx, eax
0x18001cd34  jmp     loc_18001CBEF
0x18001cd39  mov     rdx, r14
0x18001cd3c  mov     rcx, [rbp+57h+Sid]
0x18001cd40  call    cs:__imp_LsaLookupUserAccountType
0x18001cd47  nop     dword ptr [rax+rax+00h]
0x18001cd4c  test    eax, eax
0x18001cd4e  jns     short loc_18001CD70
0x18001cd50  mov     rcx, [rbp+5Fh]; this
0x18001cd54  mov     r9d, eax; char *
0x18001cd57  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001cd5c  jmp     short loc_18001CD32
0x18001cd5e  mov     ebx, 80070216h
0x18001cd63  mov     r9d, ebx
0x18001cd66  mov     edx, 298h
0x18001cd6b  jmp     loc_18001CBDE
0x18001cd70  mov     rcx, [rbp+57h+hMem]; hMem
0x18001cd74  test    rcx, rcx
0x18001cd77  jz      short loc_18001CD85
0x18001cd79  call    cs:__imp_LocalFree
0x18001cd80  nop     dword ptr [rax+rax+00h]
0x18001cd85  mov     rcx, [rbp+57h+Sid]; hMem
0x18001cd89  test    rcx, rcx
0x18001cd8c  jz      short loc_18001CD9A
0x18001cd8e  call    cs:__imp_LocalFree
0x18001cd95  nop     dword ptr [rax+rax+00h]
0x18001cd9a  mov     ebx, r15d
0x18001cd9d  lea     rcx, [rbp+57h+lpAccountName]
0x18001cda1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001cda6  nop
0x18001cda7  mov     rcx, [rbp+57h+string]; string
0x18001cdab  call    cs:__imp_WindowsDeleteString
0x18001cdb2  nop     dword ptr [rax+rax+00h]
0x18001cdb7  mov     eax, ebx
0x18001cdb9  add     rsp, 98h
0x18001cdc0  pop     r15
0x18001cdc2  pop     r14
0x18001cdc4  pop     rdi
0x18001cdc5  pop     rsi
0x18001cdc6  pop     rbx
0x18001cdc7  pop     rbp
0x18001cdc8  retn
```
