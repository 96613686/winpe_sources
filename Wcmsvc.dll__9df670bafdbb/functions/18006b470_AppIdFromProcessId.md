# AppIdFromProcessId

- ea: `0x18006b470`
- end: `0x18006b687`
- name: `AppIdFromProcessId`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180062c50`

## callees

- `0x180012440`
- `0x1800137a0`
- `0x180013afc`
- `0x18001c11c`
- `0x18003a540`
- `0x18003ecdc`
- `0x180047e70`
- `0x18006adc0`
- `0x18006b470`
- `0x18006be98`
- `0x180084f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b625`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006b4a0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006b4a0`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x18006b51a`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x18006b51a`

## string_xrefs

- `0x18006b4ee`: `onecoreuap\net\wcm\service\base\server\rpcsrv.cpp`
- `0x18006b5e4`: `onecoreuap\net\wcm\service\base\server\rpcsrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall AppIdFromProcessId(__int64 a1, DWORD a2)
{
  char *v3; // rbx
  int v4; // eax
  DWORD v5; // esi
  WCHAR *v6; // rdx
  DWORD ProcessImageFileNameW; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  DWORD v11; // eax
  __int64 v12; // r8
  DWORD v13; // edx
  unsigned int v14; // eax
  const char *v15; // r9
  DWORD LastError; // eax
  DWORD nSize; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v18[3]; // [rsp+28h] [rbp-50h] BYREF
  LPWSTR lpImageFileName[4]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v18[1] = a1;
  v3 = (char *)OpenProcess(0x1000u, 0, a2);
  v18[0] = v3;
  if ( (unsigned __int64)(v3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 148, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, LastError);
    }
    std::wstring::wstring(a1);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
    return a1;
  }
  else
  {
    std::wstring::wstring(lpImageFileName, 260);
    while ( 1 )
    {
      nSize = 0;
      v4 = LongLongToULong((__int64)lpImageFileName[2], &nSize);
      if ( v4 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x9B6,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\rpcsrv.cpp",
          (const char *)(unsigned int)v4,
          nSize);
      v5 = nSize;
      v6 = (WCHAR *)lpImageFileName;
      if ( lpImageFileName[3] > (LPWSTR)7 )
        v6 = lpImageFileName[0];
      ProcessImageFileNameW = K32GetProcessImageFileNameW(v3, v6, nSize);
      if ( ProcessImageFileNameW )
      {
        std::wstring::resize(lpImageFileName, ProcessImageFileNameW, v8, v9);
        std::wstring::wstring(a1, lpImageFileName);
        ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)lpImageFileName);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
        return a1;
      }
      v11 = GetLastError();
      if ( v11 != 122 )
        break;
      v13 = v5 + (v5 >> 1);
      v14 = -1;
      if ( v13 >= v5 )
        v14 = v5 + (v5 >> 1);
      v15 = v13 < v5 ? (const char *)0x80070216LL : 0LL;
      if ( v13 < v5 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x9C6,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\rpcsrv.cpp",
          v15,
          nSize);
      std::wstring::resize(lpImageFileName, v14, v12, v15);
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 149, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, v11);
    }
    std::wstring::wstring(a1);
    ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)lpImageFileName);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v18);
    return a1;
  }
}

```

## disassembly

```asm
0x18006b470  mov     [rsp+arg_10], rbx
0x18006b475  mov     [rsp+arg_18], rsi
0x18006b47a  push    rdi
0x18006b47b  sub     rsp, 70h
0x18006b47f  mov     rax, cs:__security_cookie
0x18006b486  xor     rax, rsp
0x18006b489  mov     [rsp+78h+var_18], rax
0x18006b48e  mov     rdi, rcx
0x18006b491  mov     [rsp+78h+var_48], rcx
0x18006b496  mov     r8d, edx; dwProcessId
0x18006b499  xor     edx, edx; bInheritHandle
0x18006b49b  mov     ecx, 1000h; dwDesiredAccess
0x18006b4a0  call    cs:__imp_OpenProcess
0x18006b4a6  mov     rbx, rax
0x18006b4a9  mov     [rsp+78h+var_50], rax
0x18006b4ae  dec     rax
0x18006b4b1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006b4b5  ja      loc_18006B606
0x18006b4bb  mov     edx, 104h
0x18006b4c0  lea     rcx, [rsp+78h+lpImageFileName]
0x18006b4c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18006b4ca  nop
0x18006b4cb  mov     [rsp+78h+nSize], 0; int
0x18006b4d3  lea     rdx, [rsp+78h+nSize]; unsigned int *
0x18006b4d8  mov     rcx, [rsp+78h+var_28]; __int64
0x18006b4dd  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18006b4e2  mov     rcx, [rsp+78h]; this
0x18006b4e7  test    eax, eax
0x18006b4e9  jns     short loc_18006B4FF
0x18006b4eb  mov     r9d, eax; char *
0x18006b4ee  lea     r8, aOnecoreuapNetW_39; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006b4f5  mov     edx, 9B6h; void *
0x18006b4fa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006b4ff  mov     esi, [rsp+78h+nSize]
0x18006b503  lea     rdx, [rsp+78h+lpImageFileName]
0x18006b508  cmp     [rsp+78h+var_20], 7
0x18006b50e  cmova   rdx, [rsp+78h+lpImageFileName]; lpImageFileName
0x18006b514  mov     r8d, esi; nSize
0x18006b517  mov     rcx, rbx; hProcess
0x18006b51a  call    cs:__imp_K32GetProcessImageFileNameW
0x18006b520  test    eax, eax
0x18006b522  jz      short loc_18006B55B
0x18006b524  mov     edx, eax
0x18006b526  lea     rcx, [rsp+78h+lpImageFileName]
0x18006b52b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18006b530  lea     rdx, [rsp+78h+lpImageFileName]
0x18006b535  mov     rcx, rdi
0x18006b538  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18006b53d  nop
0x18006b53e  lea     rcx, [rsp+78h+lpImageFileName]; this
0x18006b543  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x18006b548  nop
0x18006b549  lea     rcx, [rsp+78h+var_50]
0x18006b54e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b553  mov     rax, rdi
0x18006b556  jmp     loc_18006B667
0x18006b55b  call    cs:__imp_GetLastError
0x18006b561  cmp     eax, 7Ah ; 'z'
0x18006b564  jz      short loc_18006B5C3
0x18006b566  lea     rdx, WPP_GLOBAL_Control
0x18006b56d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b574  cmp     rcx, rdx
0x18006b577  jz      short loc_18006B59D
0x18006b579  cmp     byte ptr [rcx+19h], 1
0x18006b57d  jb      short loc_18006B59D
0x18006b57f  test    byte ptr [rcx+1Ch], 1
0x18006b583  jz      short loc_18006B59D
0x18006b585  mov     edx, 95h
0x18006b58a  mov     r9d, eax
0x18006b58d  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x18006b594  mov     rcx, [rcx+10h]
0x18006b598  call    WPP_SF_d
0x18006b59d  mov     rcx, rdi
0x18006b5a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006b5a5  nop
0x18006b5a6  lea     rcx, [rsp+78h+lpImageFileName]; this
0x18006b5ab  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x18006b5b0  nop
0x18006b5b1  lea     rcx, [rsp+78h+var_50]
0x18006b5b6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b5bb  mov     rax, rdi
0x18006b5be  jmp     loc_18006B667
0x18006b5c3  mov     edx, esi
0x18006b5c5  shr     edx, 1
0x18006b5c7  add     edx, esi
0x18006b5c9  or      eax, 0FFFFFFFFh
0x18006b5cc  cmp     edx, esi
0x18006b5ce  cmovnb  eax, edx
0x18006b5d1  sbb     r9d, r9d
0x18006b5d4  and     r9d, 80070216h; char *
0x18006b5db  mov     rcx, [rsp+78h]; this
0x18006b5e0  cmp     edx, esi
0x18006b5e2  jnb     short loc_18006B5F5
0x18006b5e4  lea     r8, aOnecoreuapNetW_39; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006b5eb  mov     edx, 9C6h; void *
0x18006b5f0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006b5f5  mov     edx, eax
0x18006b5f7  lea     rcx, [rsp+78h+lpImageFileName]
0x18006b5fc  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18006b601  jmp     loc_18006B4CB
0x18006b606  lea     rdx, WPP_GLOBAL_Control
0x18006b60d  mov     rax, cs:WPP_GLOBAL_Control
0x18006b614  cmp     rax, rdx
0x18006b617  jz      short loc_18006B64A
0x18006b619  cmp     byte ptr [rax+19h], 3
0x18006b61d  jb      short loc_18006B64A
0x18006b61f  test    byte ptr [rax+1Ch], 1
0x18006b623  jz      short loc_18006B64A
0x18006b625  call    cs:__imp_GetLastError
0x18006b62b  mov     edx, 94h
0x18006b630  mov     r9d, eax
0x18006b633  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x18006b63a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b641  mov     rcx, [rcx+10h]
0x18006b645  call    WPP_SF_d
0x18006b64a  mov     rcx, rdi
0x18006b64d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006b652  nop
0x18006b653  lea     rcx, [rsp+78h+var_50]
0x18006b658  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b65d  mov     rax, rdi
0x18006b660  jmp     short loc_18006B667
0x18006b662  mov     rax, [rsp+78h+var_48]
0x18006b667  mov     rcx, [rsp+78h+var_18]
0x18006b66c  xor     rcx, rsp; StackCookie
0x18006b66f  call    __security_check_cookie
0x18006b674  lea     r11, [rsp+78h+var_8]
0x18006b679  mov     rbx, [r11+20h]
0x18006b67d  mov     rsi, [r11+28h]
0x18006b681  mov     rsp, r11
0x18006b684  pop     rdi
0x18006b685  retn
```
