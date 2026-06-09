# OwningUserRegistry::AddAgentUserRegKey(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18004fecc`
- end: `0x18004ffb6`
- name: `?AddAgentUserRegKey@OwningUserRegistry@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800507a8`
- `0x180059200`

## callees

- `0x1800075e4`
- `0x180011e18`
- `0x180021564`
- `0x18003b4ec`
- `0x18003dce4`
- `0x18003e03c`
- `0x18004fecc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fef2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ff88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ff88`

## string_xrefs

- `0x18004ffa1`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall OwningUserRegistry::AddAgentUserRegKey(__int64 a1, WCHAR *a2, wchar_t *a3)
{
  int v6; // ebx
  const char *v7; // r9
  const WCHAR *v8; // r8
  const wchar_t *v9; // r9
  const wchar_t *v10; // r8
  WCHAR *v11; // r8
  _QWORD *v12; // rax
  __int64 v13; // r8
  LSTATUS result; // eax
  _BYTE v15[40]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v6 = dword_1800B9160;
  if ( v6 != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x15D,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v7);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v8 = a2;
  else
    v8 = *(const WCHAR **)a2;
  wil::reg::create_unique_key(&hKey, *(HKEY *)a1, v8);
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v10 = a3;
  else
    v10 = *(const wchar_t **)a3;
  wil::reg::set_value_string((wil::reg *)hKey, (HKEY)&stru_18009E488, v10, v9);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v11 = a2;
  else
    v11 = *(WCHAR **)a2;
  Log(4u, L"Added reg key for %s", v11);
  v12 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                    (float *)(a1 + 40),
                    (__int64)v15,
                    a2);
  result = std::wstring::operator=(*v12 + 48LL, a3, v13);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18004fecc  mov     [rsp+arg_0], rbx
0x18004fed1  mov     [rsp+arg_8], rbp
0x18004fed6  push    rsi
0x18004fed7  push    rdi
0x18004fed8  push    r14
0x18004feda  sub     rsp, 30h
0x18004fede  mov     rsi, r8
0x18004fee1  mov     rdi, rdx
0x18004fee4  mov     r14, rcx
0x18004fee7  mov     ebx, cs:dword_1800B9160
0x18004feed  mov     rbp, [rsp+48h]
0x18004fef2  call    cs:__imp_GetCurrentThreadId
0x18004fef8  cmp     ebx, eax
0x18004fefa  jnz     loc_18004FFA1
0x18004ff00  cmp     qword ptr [rdi+18h], 7
0x18004ff05  jbe     short loc_18004FF0C
0x18004ff07  mov     r8, [rdi]
0x18004ff0a  jmp     short loc_18004FF0F
0x18004ff0c  mov     r8, rdi
0x18004ff0f  mov     rdx, [r14]
0x18004ff12  lea     rcx, [rsp+48h+hKey]
0x18004ff17  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x18004ff1c  nop
0x18004ff1d  cmp     qword ptr [rsi+18h], 7
0x18004ff22  jbe     short loc_18004FF29
0x18004ff24  mov     r8, [rsi]
0x18004ff27  jmp     short loc_18004FF2C
0x18004ff29  mov     r8, rsi; wchar_t *
0x18004ff2c  lea     rdx, stru_18009E488; HKEY
0x18004ff33  mov     rcx, [rsp+48h+hKey]; this
0x18004ff38  call    ?set_value_string@reg@wil@@YAXPEAUHKEY__@@PEB_W1@Z; wil::reg::set_value_string(HKEY__ *,wchar_t const *,wchar_t const *)
0x18004ff3d  cmp     qword ptr [rdi+18h], 7
0x18004ff42  jbe     short loc_18004FF49
0x18004ff44  mov     r8, [rdi]
0x18004ff47  jmp     short loc_18004FF4C
0x18004ff49  mov     r8, rdi
0x18004ff4c  lea     rdx, aAddedRegKeyFor; "Added reg key for %s"
0x18004ff53  mov     ecx, 4; unsigned __int8
0x18004ff58  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004ff5d  lea     rcx, [r14+28h]
0x18004ff61  mov     r8, rdi
0x18004ff64  lea     rdx, [rsp+48h+var_28]
0x18004ff69  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18004ff6e  mov     rcx, [rax]
0x18004ff71  add     rcx, 30h ; '0'
0x18004ff75  mov     rdx, rsi
0x18004ff78  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004ff7d  nop
0x18004ff7e  mov     rcx, [rsp+48h+hKey]; hKey
0x18004ff83  test    rcx, rcx
0x18004ff86  jz      short loc_18004FF8E
0x18004ff88  call    cs:__imp_RegCloseKey
0x18004ff8e  mov     rbx, [rsp+48h+arg_0]
0x18004ff93  mov     rbp, [rsp+48h+arg_8]
0x18004ff98  add     rsp, 30h
0x18004ff9c  pop     r14
0x18004ff9e  pop     rdi
0x18004ff9f  pop     rsi
0x18004ffa0  retn
0x18004ffa1  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004ffa8  mov     edx, 15Dh; void *
0x18004ffad  mov     rcx, rbp; this
0x18004ffb0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
