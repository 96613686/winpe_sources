# Microsoft::Diagnostics::AppIdMetadata::QueryRunningProcessInfo(ProcessKey const &,Microsoft::Diagnostics::AppIdMetadata::ProcessInfo &,Microsoft::Diagnostics::AppIdKey &)

- ea: `0x1800e65f4`
- end: `0x1800e68ab`
- name: `?QueryRunningProcessInfo@AppIdMetadata@Diagnostics@Microsoft@@CA_NAEBUProcessKey@@AEAUProcessInfo@123@AEAVAppIdKey@23@@Z`
- size: `695`
- prototype: `bool __fastcall(const struct ProcessKey *, struct Microsoft::Diagnostics::AppIdMetadata::ProcessInfo *, struct Microsoft::Diagnostics::AppIdKey *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002b01c`
- `0x1800585f8`
- `0x180058b18`

## callees

- `0x18001b510`
- `0x18002abec`
- `0x18002b318`
- `0x180064e34`
- `0x1800bc658`
- `0x1800e65f4`
- `0x1800e68b4`
- `0x1800e6994`
- `0x1801b7bd0`
- `0x1801c2380`
- `0x1801d2b8c`
- `0x18020aac0`
- `0x18020afa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e664d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e664d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e68a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e68a0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e6634`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e684e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e6634`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800e684e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e681f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e681f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800e67f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800e67f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Microsoft::Diagnostics::AppIdMetadata::QueryRunningProcessInfo(
        DWORD *a1,
        struct Microsoft::Diagnostics::AppIdMetadata::ProcessInfo *a2,
        struct Microsoft::Diagnostics::AppIdKey *a3)
{
  char *v6; // rsi
  const struct std::nothrow_t *v7; // rdx
  _BYTE *v8; // rdi
  void *v9; // rbx
  __int64 v10; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  HANDLE v18; // rax
  LPWSTR StringSid; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h]
  char *v21; // [rsp+30h] [rbp-D0h] BYREF
  void *v22; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE ProcessInformation[2048]; // [rsp+40h] [rbp-C0h] BYREF

  v6 = (char *)OpenProcess(0x1000u, 0, *a1);
  v21 = v6;
  if ( ((unsigned __int64)(v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( GetLastError() == 5 )
    {
      StringSid = 0;
      LOBYTE(v20) = 0;
      if ( Microsoft::Diagnostics::ThreadPrivilegeManager::UpdatePrivilege((void **)&StringSid) >= 0 )
      {
        v18 = OpenProcess(0x1000u, 0, *a1);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v21,
          v18);
        v6 = v21;
      }
      Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager((Microsoft::Diagnostics::ThreadPrivilegeManager *)&StringSid);
    }
    if ( ((unsigned __int64)(v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      goto LABEL_12;
  }
  v22 = 0;
  if ( (int)Microsoft::Diagnostics::Utils::Os::GetTelemetryProcessInformation(v6, ProcessInformation) < 0 )
  {
    std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v22, v7);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
    return 0;
  }
  v8 = ProcessInformation;
  v9 = v22;
  if ( v22 )
    v8 = v22;
  v10 = *((_QWORD *)a1 + 1);
  if ( v10 && v10 != *((_QWORD *)v8 + 1) && v10 != *((_QWORD *)v8 + 2) )
  {
    if ( v22 )
      operator delete(v22, v7);
LABEL_12:
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v6);
    return 0;
  }
  *((_DWORD *)a2 + 1) = *a1;
  *((_DWORD *)a2 + 2) = *((_DWORD *)v8 + 14);
  *((_QWORD *)a2 + 2) = *((_QWORD *)v8 + 6);
  *((_QWORD *)a2 + 3) = *((_QWORD *)v8 + 1);
  *((_QWORD *)a2 + 4) = *((_QWORD *)v8 + 2);
  *((_DWORD *)a2 + 3) = 0;
  if ( *((_DWORD *)v8 + 22) )
  {
    StringSid = (LPWSTR)&v8[*((unsigned int *)v8 + 22)];
    v20 = std::_WChar_traits<wchar_t>::length(StringSid);
    *((_DWORD *)a2 + 3) = Microsoft::Diagnostics::AppIdMetadata::CalculateCommandLineHash(&StringSid);
  }
  if ( *((_DWORD *)v8 + 18) )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(&v8[*((unsigned int *)v8 + 18)], &StringSid) )
      std::wstring::assign((char *)a2 + 56, StringSid);
    if ( StringSid )
      LocalFree(StringSid);
  }
  *((_DWORD *)a3 + 24) = *((_DWORD *)v8 + 16);
  *((_DWORD *)a3 + 25) = *((_DWORD *)v8 + 17);
  if ( *((_DWORD *)v8 + 19) )
  {
    v12 = std::_WChar_traits<wchar_t>::length(&v8[*((unsigned int *)v8 + 19)]);
    std::wstring::_Assign<wchar_t>(a3, v13, v12);
  }
  if ( *((_DWORD *)v8 + 20) )
  {
    v14 = std::_WChar_traits<wchar_t>::length(&v8[*((unsigned int *)v8 + 20)]);
    std::wstring::_Assign<wchar_t>((char *)a3 + 32, v15, v14);
  }
  if ( *((_DWORD *)v8 + 21) )
  {
    v16 = std::_WChar_traits<wchar_t>::length(&v8[*((unsigned int *)v8 + 21)]);
    std::wstring::_Assign<wchar_t>((char *)a3 + 64, v17, v16);
  }
  if ( v9 )
    operator delete(v9, v7);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return 1;
}

```

## disassembly

```asm
0x1800e65f4  push    rbp
0x1800e65f6  push    rbx
0x1800e65f7  push    rsi
0x1800e65f8  push    rdi
0x1800e65f9  push    r12
0x1800e65fb  push    r14
0x1800e65fd  push    r15
0x1800e65ff  lea     rbp, [rsp-750h]
0x1800e6607  sub     rsp, 850h
0x1800e660e  mov     rax, cs:__security_cookie
0x1800e6615  xor     rax, rsp
0x1800e6618  mov     [rbp+780h+var_40], rax
0x1800e661f  mov     r15, r8
0x1800e6622  mov     r14, rdx
0x1800e6625  mov     r12, rcx
0x1800e6628  mov     r8d, [rcx]; dwProcessId
0x1800e662b  xor     edx, edx; bInheritHandle
0x1800e662d  mov     ebx, 1000h
0x1800e6632  mov     ecx, ebx; dwDesiredAccess
0x1800e6634  call    cs:__imp_OpenProcess
0x1800e663a  mov     rsi, rax
0x1800e663d  mov     [rsp+880h+var_850], rax
0x1800e6642  inc     rax
0x1800e6645  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e664b  jnz     short loc_1800E6668
0x1800e664d  call    cs:__imp_GetLastError
0x1800e6653  cmp     eax, 5
0x1800e6656  jz      loc_1800E682A
0x1800e665c  lea     rax, [rsi+1]
0x1800e6660  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e6666  jz      short loc_1800E66C0
0x1800e6668  mov     [rsp+880h+var_848], 0
0x1800e6671  lea     r9, [rsp+880h+var_848]
0x1800e6676  lea     rdx, [rsp+880h+ProcessInformation]; ProcessInformation
0x1800e667b  mov     rcx, rsi; ProcessHandle
0x1800e667e  call    ?GetTelemetryProcessInformation@Os@Utils@Diagnostics@Microsoft@@SAJPEAXPEAW4byte@gsl@@KAEAV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@@Z; Microsoft::Diagnostics::Utils::Os::GetTelemetryProcessInformation(void *,gsl::byte *,ulong,std::unique_ptr<gsl::byte [0]> &)
0x1800e6683  test    eax, eax
0x1800e6685  js      loc_1800E6875
0x1800e668b  lea     rdi, [rsp+880h+ProcessInformation]
0x1800e6690  mov     rbx, [rsp+880h+var_848]
0x1800e6695  test    rbx, rbx
0x1800e6698  cmovnz  rdi, rbx
0x1800e669c  mov     rax, [r12+8]
0x1800e66a1  test    rax, rax
0x1800e66a4  jz      short loc_1800E66F1
0x1800e66a6  cmp     rax, [rdi+8]
0x1800e66aa  jz      short loc_1800E66F1
0x1800e66ac  cmp     rax, [rdi+10h]
0x1800e66b0  jz      short loc_1800E66F1
0x1800e66b2  test    rbx, rbx
0x1800e66b5  jz      short loc_1800E66C0
0x1800e66b7  mov     rcx, rbx; void *
0x1800e66ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e66bf  nop
0x1800e66c0  lea     rax, [rsi-1]
0x1800e66c4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e66c8  jbe     loc_1800E688F
0x1800e66ce  xor     al, al
0x1800e66d0  mov     rcx, [rbp+780h+var_40]
0x1800e66d7  xor     rcx, rsp; StackCookie
0x1800e66da  call    __security_check_cookie
0x1800e66df  add     rsp, 850h
0x1800e66e6  pop     r15
0x1800e66e8  pop     r14
0x1800e66ea  pop     r12
0x1800e66ec  pop     rdi
0x1800e66ed  pop     rsi
0x1800e66ee  pop     rbx
0x1800e66ef  pop     rbp
0x1800e66f0  retn
0x1800e66f1  mov     eax, [r12]
0x1800e66f5  mov     [r14+4], eax
0x1800e66f9  mov     eax, [rdi+38h]
0x1800e66fc  mov     [r14+8], eax
0x1800e6700  mov     rax, [rdi+30h]
0x1800e6704  mov     [r14+10h], rax
0x1800e6708  mov     rax, [rdi+8]
0x1800e670c  mov     [r14+18h], rax
0x1800e6710  mov     rax, [rdi+10h]
0x1800e6714  mov     [r14+20h], rax
0x1800e6718  mov     dword ptr [r14+0Ch], 0
0x1800e6720  cmp     dword ptr [rdi+58h], 0
0x1800e6724  jz      short loc_1800E6749
0x1800e6726  mov     ecx, [rdi+58h]
0x1800e6729  add     rcx, rdi
0x1800e672c  mov     [rsp+880h+StringSid], rcx
0x1800e6731  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800e6736  mov     [rsp+880h+var_858], rax
0x1800e673b  lea     rcx, [rsp+880h+StringSid]
0x1800e6740  call    ?CalculateCommandLineHash@AppIdMetadata@Diagnostics@Microsoft@@SAKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::AppIdMetadata::CalculateCommandLineHash(std::wstring_view)
0x1800e6745  mov     [r14+0Ch], eax
0x1800e6749  cmp     dword ptr [rdi+48h], 0
0x1800e674d  jnz     loc_1800E67E4
0x1800e6753  mov     eax, [rdi+40h]
0x1800e6756  mov     [r15+60h], eax
0x1800e675a  mov     eax, [rdi+44h]
0x1800e675d  mov     [r15+64h], eax
0x1800e6761  cmp     dword ptr [rdi+4Ch], 0
0x1800e6765  jz      short loc_1800E6780
0x1800e6767  mov     ecx, [rdi+4Ch]
0x1800e676a  add     rcx, rdi
0x1800e676d  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800e6772  mov     r8, rax
0x1800e6775  mov     rdx, rcx
0x1800e6778  mov     rcx, r15
0x1800e677b  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800e6780  cmp     dword ptr [rdi+50h], 0
0x1800e6784  jz      short loc_1800E67A0
0x1800e6786  mov     edx, [rdi+50h]
0x1800e6789  add     rdx, rdi
0x1800e678c  mov     rcx, rdx
0x1800e678f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800e6794  mov     r8, rax
0x1800e6797  lea     rcx, [r15+20h]
0x1800e679b  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800e67a0  cmp     dword ptr [rdi+54h], 0
0x1800e67a4  jz      short loc_1800E67C1
0x1800e67a6  mov     edx, [rdi+54h]
0x1800e67a9  add     rdx, rdi
0x1800e67ac  mov     rcx, rdx
0x1800e67af  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800e67b4  mov     r8, rax
0x1800e67b7  lea     rcx, [r15+40h]
0x1800e67bb  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800e67c0  nop
0x1800e67c1  test    rbx, rbx
0x1800e67c4  jz      short loc_1800E67CF
0x1800e67c6  mov     rcx, rbx; void *
0x1800e67c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e67ce  nop
0x1800e67cf  lea     rax, [rsi-1]
0x1800e67d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e67d7  jbe     loc_1800E689D
0x1800e67dd  mov     al, 1
0x1800e67df  jmp     loc_1800E66D0
0x1800e67e4  mov     [rsp+880h+StringSid], 0
0x1800e67ed  mov     ecx, [rdi+48h]
0x1800e67f0  add     rcx, rdi; Sid
0x1800e67f3  lea     rdx, [rsp+880h+StringSid]; StringSid
0x1800e67f8  call    cs:__imp_ConvertSidToStringSidW
0x1800e67fe  test    eax, eax
0x1800e6800  jz      short loc_1800E6811
0x1800e6802  lea     rcx, [r14+38h]
0x1800e6806  mov     rdx, [rsp+880h+StringSid]
0x1800e680b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800e6810  nop
0x1800e6811  mov     rcx, [rsp+880h+StringSid]; hMem
0x1800e6816  test    rcx, rcx
0x1800e6819  jz      loc_1800E6753
0x1800e681f  call    cs:__imp_LocalFree
0x1800e6825  jmp     loc_1800E6753
0x1800e682a  mov     [rsp+880h+StringSid], 0
0x1800e6833  mov     byte ptr [rsp+880h+var_858], 0
0x1800e6838  lea     rcx, [rsp+880h+StringSid]; TokenHandle
0x1800e683d  call    ?UpdatePrivilege@ThreadPrivilegeManager@Diagnostics@Microsoft@@QEAAJK_N@Z; Microsoft::Diagnostics::ThreadPrivilegeManager::UpdatePrivilege(ulong,bool)
0x1800e6842  test    eax, eax
0x1800e6844  js      short loc_1800E6866
0x1800e6846  mov     r8d, [r12]; dwProcessId
0x1800e684a  xor     edx, edx; bInheritHandle
0x1800e684c  mov     ecx, ebx; dwDesiredAccess
0x1800e684e  call    cs:__imp_OpenProcess
0x1800e6854  mov     rdx, rax
0x1800e6857  lea     rcx, [rsp+880h+var_850]
0x1800e685c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800e6861  mov     rsi, [rsp+880h+var_850]
0x1800e6866  lea     rcx, [rsp+880h+StringSid]; this
0x1800e686b  call    ??1ThreadPrivilegeManager@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ThreadPrivilegeManager::~ThreadPrivilegeManager(void)
0x1800e6870  jmp     loc_1800E665C
0x1800e6875  lea     rcx, [rsp+880h+var_848]
0x1800e687a  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1800e687f  nop
0x1800e6880  lea     rcx, [rsp+880h+var_850]
0x1800e6885  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e688a  jmp     loc_1800E66CE
0x1800e688f  mov     rcx, rsi; hObject
0x1800e6892  call    cs:__imp_CloseHandle
0x1800e6898  jmp     loc_1800E66CE
0x1800e689d  mov     rcx, rsi; hObject
0x1800e68a0  call    cs:__imp_CloseHandle
0x1800e68a6  jmp     loc_1800E67DD
```
