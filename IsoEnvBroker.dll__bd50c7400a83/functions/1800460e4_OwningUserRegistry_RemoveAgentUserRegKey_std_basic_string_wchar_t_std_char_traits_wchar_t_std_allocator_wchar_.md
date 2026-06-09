# OwningUserRegistry::RemoveAgentUserRegKey(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800460e4`
- end: `0x1800461c9`
- name: `?RemoveAgentUserRegKey@OwningUserRegistry@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180040d30`
- `0x1800414dc`

## callees

- `0x1800075e4`
- `0x180011e18`
- `0x1800460e4`
- `0x180047498`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800460ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800460ff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004611f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004611f`

## string_xrefs

- `0x1800461b7`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x180046159`: `Failed to delete reg key for AU %s: %#x`

## pseudocode

```c
void __fastcall OwningUserRegistry::RemoveAgentUserRegKey(HKEY *a1, const WCHAR *a2)
{
  int v2; // ebx
  const char *v5; // r9
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  __int64 *v8; // r8
  __int64 *v9; // r8
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = dword_1800B9160;
  if ( v2 != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x15D,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v5);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v6 = a2;
  else
    v6 = *(const WCHAR **)a2;
  v7 = RegDeleteTreeW(*a1, v6);
  if ( v7 == 2 )
  {
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v8 = (__int64 *)a2;
    else
      v8 = *(__int64 **)a2;
    Log(3u, L"Reg key not found for AU %s", v8);
LABEL_18:
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::erase(
      a1 + 13,
      a2);
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::erase(
      a1 + 5,
      a2);
    return;
  }
  if ( !v7 )
  {
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v9 = (__int64 *)a2;
    else
      v9 = *(__int64 **)a2;
    Log(4u, L"Cleared reg key for %s", v9);
    goto LABEL_18;
  }
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  Log(2u, L"Failed to delete reg key for AU %s: %#x", a2, v7);
}

```

## disassembly

```asm
0x1800460e4  mov     [rsp+arg_0], rbx
0x1800460e9  mov     [rsp+arg_8], rsi
0x1800460ee  push    rdi
0x1800460ef  sub     rsp, 20h
0x1800460f3  mov     ebx, cs:dword_1800B9160
0x1800460f9  mov     rdi, rdx
0x1800460fc  mov     rsi, rcx
0x1800460ff  call    cs:__imp_GetCurrentThreadId
0x180046105  cmp     ebx, eax
0x180046107  jnz     loc_1800461B2
0x18004610d  cmp     qword ptr [rdi+18h], 7
0x180046112  jbe     short loc_180046119
0x180046114  mov     rdx, [rdi]
0x180046117  jmp     short loc_18004611C
0x180046119  mov     rdx, rdi; lpSubKey
0x18004611c  mov     rcx, [rsi]; hKey
0x18004611f  call    cs:__imp_RegDeleteTreeW
0x180046125  mov     ecx, 2; unsigned __int8
0x18004612a  cmp     eax, ecx
0x18004612c  jnz     short loc_180046148
0x18004612e  cmp     qword ptr [rdi+18h], 7
0x180046133  jbe     short loc_18004613A
0x180046135  mov     r8, [rdi]
0x180046138  jmp     short loc_18004613D
0x18004613a  mov     r8, rdi
0x18004613d  mov     al, 3
0x18004613f  lea     rdx, aRegKeyNotFound; "Reg key not found for AU %s"
0x180046146  jmp     short loc_180046182
0x180046148  test    eax, eax
0x18004614a  jz      short loc_18004616A
0x18004614c  cmp     qword ptr [rdi+18h], 7
0x180046151  jbe     short loc_180046156
0x180046153  mov     rdi, [rdi]
0x180046156  mov     r9d, eax
0x180046159  lea     rdx, aFailedToDelete; "Failed to delete reg key for AU %s: %#x"
0x180046160  mov     r8, rdi
0x180046163  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180046168  jmp     short loc_1800461A2
0x18004616a  cmp     qword ptr [rdi+18h], 7
0x18004616f  jbe     short loc_180046176
0x180046171  mov     r8, [rdi]
0x180046174  jmp     short loc_180046179
0x180046176  mov     r8, rdi
0x180046179  mov     al, 4
0x18004617b  lea     rdx, aClearedRegKeyF; "Cleared reg key for %s"
0x180046182  movzx   ecx, al; unsigned __int8
0x180046185  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004618a  lea     rcx, [rsi+68h]
0x18004618e  mov     rdx, rdi
0x180046191  call    ?erase@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::erase(std::wstring const &)
0x180046196  lea     rcx, [rsi+28h]
0x18004619a  mov     rdx, rdi
0x18004619d  call    ?erase@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::erase(std::wstring const &)
0x1800461a2  mov     rbx, [rsp+28h+arg_0]
0x1800461a7  mov     rsi, [rsp+28h+arg_8]
0x1800461ac  add     rsp, 20h
0x1800461b0  pop     rdi
0x1800461b1  retn
0x1800461b2  mov     rcx, [rsp+28h]; this
0x1800461b7  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800461be  mov     edx, 15Dh; void *
0x1800461c3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
