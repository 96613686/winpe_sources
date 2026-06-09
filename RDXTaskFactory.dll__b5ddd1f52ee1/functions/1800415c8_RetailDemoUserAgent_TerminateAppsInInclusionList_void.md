# RetailDemoUserAgent::TerminateAppsInInclusionList(void)

- ea: `0x1800415c8`
- end: `0x1800416d1`
- name: `?TerminateAppsInInclusionList@RetailDemoUserAgent@@AEAAXXZ`
- size: `265`
- prototype: `void __fastcall(RetailDemoUserAgent *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180039b80`

## callees

- `0x180003390`
- `0x180003e00`
- `0x180006450`
- `0x180022ad8`
- `0x18002a8a4`
- `0x18002fa88`
- `0x18003def0`
- `0x1800415c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18004165b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18004165b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004164b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004164b`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x180041673`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x180041673`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180041604`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180041604`

## string_xrefs

- `0x1800415ee`: `ServiceReadWrite\ProcessCloseInclusionList`

## pseudocode

```c
void __fastcall RetailDemoUserAgent::TerminateAppsInInclusionList(RetailDemoUserAgent *this)
{
  void *v1; // rbx
  HANDLE v2; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE Toolhelp32Snapshot; // [rsp+28h] [rbp-D8h] BYREF
  void *v4[4]; // [rsp+30h] [rbp-D0h] BYREF
  PROCESSENTRY32W pe; // [rsp+50h] [rbp-B0h] BYREF

  RetailDemoUtil::EnumWin32AppListFromRegistry(v4, L"ServiceReadWrite\\ProcessCloseInclusionList");
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
  v1 = Toolhelp32Snapshot;
  memset_0(&pe.cntUsage, 0, 0x234u);
  pe.dwSize = 568;
  while ( Process32NextW(v1, &pe) )
  {
    if ( (unsigned __int8)RetailDemoUserAgent::IsAppInAppList(v4, pe.szExeFile) )
    {
      v2 = OpenProcess(1u, 0, pe.th32ProcessID);
      TerminateProcess(v2, 0);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v2);
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Toolhelp32Snapshot);
  if ( v4[0] )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v4[0], v4[1]);
    std::_Deallocate<16>(v4[0], ((char *)v4[2] - (char *)v4[0]) & 0xFFFFFFFFFFFFFFE0uLL);
  }
}

```

## disassembly

```asm
0x1800415c8  mov     [rsp-8+arg_0], rbx
0x1800415cd  push    rbp
0x1800415ce  lea     rbp, [rsp-1A0h]
0x1800415d6  sub     rsp, 2A0h
0x1800415dd  mov     rax, cs:__security_cookie
0x1800415e4  xor     rax, rsp
0x1800415e7  mov     [rbp+1A0h+var_10], rax
0x1800415ee  lea     rdx, c_retailDemoKeyProcessCloseInclusionListSubKey; "ServiceReadWrite\\ProcessCloseInclusion"...
0x1800415f5  lea     rcx, [rsp+2A0h+var_270]
0x1800415fa  call    ?EnumWin32AppListFromRegistry@RetailDemoUtil@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z; RetailDemoUtil::EnumWin32AppListFromRegistry(ushort const *)
0x1800415ff  xor     edx, edx; th32ProcessID
0x180041601  lea     ecx, [rdx+2]; dwFlags
0x180041604  call    cs:__imp_CreateToolhelp32Snapshot
0x18004160a  xor     edx, edx; Val
0x18004160c  lea     rcx, [rsp+2A0h+pe.cntUsage]; void *
0x180041611  mov     r8d, 234h; Size
0x180041617  mov     [rsp+2A0h+var_278], rax
0x18004161c  mov     rbx, rax
0x18004161f  call    memset_0
0x180041624  mov     [rsp+2A0h+pe.dwSize], 238h
0x18004162c  jmp     short loc_18004166B
0x18004162e  lea     rdx, [rsp+2A0h+pe.szExeFile]
0x180041633  lea     rcx, [rsp+2A0h+var_270]
0x180041638  call    ?IsAppInAppList@RetailDemoUserAgent@@CA_NAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z; RetailDemoUserAgent::IsAppInAppList(std::vector<std::wstring> const &,ushort const *)
0x18004163d  test    al, al
0x18004163f  jz      short loc_18004166B
0x180041641  mov     r8d, [rsp+2A0h+pe.th32ProcessID]; dwProcessId
0x180041646  xor     edx, edx; bInheritHandle
0x180041648  lea     ecx, [rdx+1]; dwDesiredAccess
0x18004164b  call    cs:__imp_OpenProcess
0x180041651  mov     rcx, rax; hProcess
0x180041654  mov     [rsp+2A0h+var_280], rax
0x180041659  xor     edx, edx; uExitCode
0x18004165b  call    cs:__imp_TerminateProcess
0x180041661  lea     rcx, [rsp+2A0h+var_280]
0x180041666  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004166b  lea     rdx, [rsp+2A0h+pe]; lppe
0x180041670  mov     rcx, rbx; hSnapshot
0x180041673  call    cs:__imp_Process32NextW
0x180041679  test    eax, eax
0x18004167b  jnz     short loc_18004162E
0x18004167d  lea     rcx, [rsp+2A0h+var_278]
0x180041682  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180041687  mov     rcx, [rsp+2A0h+var_270]
0x18004168c  test    rcx, rcx
0x18004168f  jz      short loc_1800416B1
0x180041691  mov     rdx, [rsp+2A0h+var_268]
0x180041696  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18004169b  mov     rcx, [rsp+2A0h+var_270]
0x1800416a0  mov     rdx, [rsp+2A0h+var_260]
0x1800416a5  sub     rdx, rcx
0x1800416a8  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800416ac  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800416b1  mov     rcx, [rbp+1A0h+var_10]
0x1800416b8  xor     rcx, rsp; StackCookie
0x1800416bb  call    __security_check_cookie
0x1800416c0  mov     rbx, [rsp+2A0h+arg_0]
0x1800416c8  add     rsp, 2A0h
0x1800416cf  pop     rbp
0x1800416d0  retn
```
