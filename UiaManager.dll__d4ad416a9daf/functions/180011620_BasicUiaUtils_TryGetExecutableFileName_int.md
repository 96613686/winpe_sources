# BasicUiaUtils::TryGetExecutableFileName(int)

- ea: `0x180011620`
- end: `0x18001177b`
- name: `?TryGetExecutableFileName@BasicUiaUtils@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z`
- size: `347`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180066550`
- `0x18006ef3c`
- `0x18006f800`

## callees

- `0x180010f78`
- `0x180011620`
- `0x180011784`
- `0x180012240`
- `0x180026768`
- `0x18002c958`
- `0x180043680`
- `0x1800441ac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800116f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800116f8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800116a5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800116a5`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011729`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011729`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x180011738`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x180011738`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x18001167b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x18001167b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall BasicUiaUtils::TryGetExecutableFileName(_QWORD *a1, DWORD a2)
{
  char *v4; // rbx
  char *v5; // rsi
  HANDLE hObject; // [rsp+20h] [rbp-E0h] BYREF
  DWORD dwSize; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR ExeName[264]; // [rsp+30h] [rbp-D0h] BYREF

  hObject = a1;
  if ( BasicUiaUtils::IsHoloLens() || BasicUiaUtils::IsOneCore() )
  {
    hObject = 0;
    if ( (int)UMgrOpenProcessHandleForAccess(4096, a2, &hObject) >= 0 )
    {
      v4 = (char *)hObject;
      v5 = (char *)hObject;
      goto LABEL_7;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
  }
  v4 = (char *)OpenProcess(0x1000u, 0, a2);
  hObject = v4;
  v5 = v4;
LABEL_7:
  if ( ((unsigned __int64)(v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    dwSize = 260;
    memset_0(ExeName, 0, 0x20Au);
    if ( QueryFullProcessImageNameW(v4, 0, ExeName, &dwSize) )
      PathStripPathW(ExeName);
    std::wstring::wstring(a1, ExeName);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
  }
  else
  {
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 0;
    std::wstring::_Construct<1,unsigned short const *>(a1, &qword_1800A2748, 0);
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v4);
  }
  return a1;
}

```

## disassembly

```asm
0x180011620  mov     [rsp-8+arg_10], rbx
0x180011625  push    rbp
0x180011626  push    rsi
0x180011627  push    rdi
0x180011628  lea     rbp, [rsp-150h]
0x180011630  sub     rsp, 250h
0x180011637  mov     rax, cs:__security_cookie
0x18001163e  xor     rax, rsp
0x180011641  mov     [rbp+160h+var_20], rax
0x180011648  mov     ebx, edx
0x18001164a  mov     rdi, rcx
0x18001164d  mov     [rsp+260h+hObject], rcx
0x180011652  call    ?IsHoloLens@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsHoloLens(void)
0x180011657  mov     esi, 1000h
0x18001165c  test    al, al
0x18001165e  jnz     short loc_180011669
0x180011660  call    ?IsOneCore@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsOneCore(void)
0x180011665  test    al, al
0x180011667  jz      short loc_18001169E
0x180011669  mov     [rsp+260h+hObject], 0
0x180011672  lea     r8, [rsp+260h+hObject]
0x180011677  mov     edx, ebx
0x180011679  mov     ecx, esi
0x18001167b  call    cs:__imp_UMgrOpenProcessHandleForAccess
0x180011681  test    eax, eax
0x180011683  js      short loc_180011694
0x180011685  mov     rbx, [rsp+260h+hObject]
0x18001168a  mov     [rsp+260h+hObject], rbx
0x18001168f  mov     rsi, rbx
0x180011692  jmp     short loc_1800116B6
0x180011694  lea     rcx, [rsp+260h+hObject]
0x180011699  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001169e  mov     r8d, ebx; dwProcessId
0x1800116a1  xor     edx, edx; bInheritHandle
0x1800116a3  mov     ecx, esi; dwDesiredAccess
0x1800116a5  call    cs:__imp_OpenProcess
0x1800116ab  mov     rbx, rax
0x1800116ae  mov     [rsp+260h+hObject], rax
0x1800116b3  mov     rsi, rax
0x1800116b6  lea     rax, [rsi+1]
0x1800116ba  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800116c0  jnz     short loc_180011700
0x1800116c2  xorps   xmm0, xmm0
0x1800116c5  movups  xmmword ptr [rdi], xmm0
0x1800116c8  mov     qword ptr [rdi+10h], 0
0x1800116d0  mov     qword ptr [rdi+18h], 0
0x1800116d8  xor     r8d, r8d
0x1800116db  lea     rdx, qword_1800A2748
0x1800116e2  mov     rcx, rdi
0x1800116e5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800116ea  nop
0x1800116eb  lea     rcx, [rsi-1]
0x1800116ef  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800116f3  ja      short loc_180011756
0x1800116f5  mov     rcx, rbx; hObject
0x1800116f8  call    cs:__imp_CloseHandle
0x1800116fe  jmp     short loc_180011756
0x180011700  mov     [rsp+260h+dwSize], 104h
0x180011708  xor     edx, edx; Val
0x18001170a  mov     r8d, 20Ah; Size
0x180011710  lea     rcx, [rsp+260h+ExeName]; void *
0x180011715  call    memset_0
0x18001171a  lea     r9, [rsp+260h+dwSize]; lpdwSize
0x18001171f  lea     r8, [rsp+260h+ExeName]; lpExeName
0x180011724  xor     edx, edx; dwFlags
0x180011726  mov     rcx, rbx; hProcess
0x180011729  call    cs:__imp_QueryFullProcessImageNameW
0x18001172f  test    eax, eax
0x180011731  jz      short loc_18001173E
0x180011733  lea     rcx, [rsp+260h+ExeName]; pszPath
0x180011738  call    cs:__imp_PathStripPathW
0x18001173e  lea     rdx, [rsp+260h+ExeName]
0x180011743  mov     rcx, rdi
0x180011746  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001174b  nop
0x18001174c  lea     rcx, [rsp+260h+hObject]
0x180011751  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180011756  mov     rax, rdi
0x180011759  mov     rcx, [rbp+160h+var_20]
0x180011760  xor     rcx, rsp; StackCookie
0x180011763  call    __security_check_cookie
0x180011768  mov     rbx, [rsp+260h+arg_10]
0x180011770  add     rsp, 250h
0x180011777  pop     rdi
0x180011778  pop     rsi
0x180011779  pop     rbp
0x18001177a  retn
```
