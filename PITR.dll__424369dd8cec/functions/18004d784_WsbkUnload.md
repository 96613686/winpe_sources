# WsbkUnload

- ea: `0x18004d784`
- end: `0x18004d977`
- name: `WsbkUnload`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004927c`

## callees

- `0x180009e04`
- `0x18003e794`
- `0x18004d784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d8d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d7ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d7ba`
- `WDSCORE!CurrentIP` at `0x18004d802`
- `WDSCORE!CurrentIP` at `0x18004d87f`
- `WDSCORE!CurrentIP` at `0x18004d8e0`
- `WDSCORE!CurrentIP` at `0x18004d802`
- `WDSCORE!CurrentIP` at `0x18004d87f`
- `WDSCORE!CurrentIP` at `0x18004d8e0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004d946`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004d946`
- `FLTLIB!FilterUnload` at `0x18004d7da`
- `FLTLIB!FilterUnload` at `0x18004d7da`

## string_xrefs

- `0x18004d79f`: `SeLoadDriverPrivilege`
- `0x18004d95e`: `SeLoadDriverPrivilege`
- `0x18004d888`: `WsbkUnload: Failed to close filter communication port; hr = 0x%08x`
- `0x18004d814`: `Filter %s not installed; nothing to unload`

## pseudocode

```c
__int64 WsbkUnload()
{
  int v0; // ebp
  HRESULT v1; // eax
  unsigned int v2; // esi
  DWORD LastError; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  signed int v6; // eax
  DWORD v7; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  DWORD v14; // [rsp+90h] [rbp+8h] BYREF

  v14 = 0;
  v0 = EnablePrivilegeEx(L"SeLoadDriverPrivilege", 1u, &v14);
  if ( hObject == (HANDLE)-1LL )
  {
LABEL_4:
    v1 = FilterUnload(L"WinSetupBak");
    v2 = v1;
    if ( v1 < 0 )
    {
      if ( v1 == -2145452013 )
      {
        v2 = 1;
        LastError = GetLastError();
        v4 = CurrentIP();
        v5 = ConstructPartialMsgW(0x4000000, "Filter %s not installed; nothing to unload", (const char *)L"WinSetupBak");
        WdsSetupLogMessageW(
          v5,
          0,
          L"D",
          0,
          551,
          L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
          L"WsbkUnload",
          v4,
          LastError,
          0,
          0);
      }
      else
      {
        v10 = GetLastError();
        v11 = CurrentIP();
        v12 = ConstructPartialMsgW(0x2000000, "WsbkUnload: Failed FilterUnload(); hr = 0x%x", v2);
        WdsSetupLogMessageW(
          v12,
          0,
          L"D",
          0,
          555,
          L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
          L"WsbkUnload",
          v11,
          v10,
          0,
          0);
      }
    }
    goto LABEL_11;
  }
  if ( CloseHandle(hObject) )
  {
    hObject = (HANDLE)-1LL;
    goto LABEL_4;
  }
  v6 = GetLastError();
  v2 = v6;
  if ( v6 > 0 )
    v2 = (unsigned __int16)v6 | 0x80070000;
  v7 = GetLastError();
  v8 = CurrentIP();
  v9 = ConstructPartialMsgW(0x2000000, "WsbkUnload: Failed to close filter communication port; hr = 0x%08x", v2);
  WdsSetupLogMessageW(
    v9,
    0,
    L"D",
    0,
    541,
    L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
    L"WsbkUnload",
    v8,
    v7,
    0,
    0);
LABEL_11:
  if ( v0 == 1 && !v14 )
    EnablePrivilegeEx(L"SeLoadDriverPrivilege", 0, 0);
  return v2;
}

```

## disassembly

```asm
0x18004d784  mov     rax, rsp
0x18004d787  push    rbx
0x18004d788  push    rbp
0x18004d789  push    rsi
0x18004d78a  push    rdi
0x18004d78b  sub     rsp, 68h
0x18004d78f  lea     r8, [rax+8]
0x18004d793  mov     dword ptr [rax+8], 0
0x18004d79a  mov     edx, 1
0x18004d79f  lea     rcx, aSeloaddriverpr; "SeLoadDriverPrivilege"
0x18004d7a6  call    EnablePrivilegeEx
0x18004d7ab  mov     rcx, cs:hObject; hObject
0x18004d7b2  mov     ebp, eax
0x18004d7b4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004d7b8  jz      short loc_18004D7D3
0x18004d7ba  call    cs:__imp_CloseHandle
0x18004d7c0  test    eax, eax
0x18004d7c2  jz      loc_18004D862
0x18004d7c8  mov     cs:hObject, 0FFFFFFFFFFFFFFFFh
0x18004d7d3  lea     rcx, aWinsetupbak; "WinSetupBak"
0x18004d7da  call    cs:__imp_FilterUnload
0x18004d7e0  mov     esi, eax
0x18004d7e2  test    eax, eax
0x18004d7e4  jns     loc_18004D94C
0x18004d7ea  cmp     eax, 801F0013h
0x18004d7ef  jnz     loc_18004D8D8
0x18004d7f5  mov     esi, 1
0x18004d7fa  call    cs:__imp_GetLastError
0x18004d800  mov     edi, eax
0x18004d802  call    cs:__imp_CurrentIP
0x18004d808  lea     r8, aWinsetupbak; "WinSetupBak"
0x18004d80f  mov     ecx, 4000000h; unsigned int
0x18004d814  lea     rdx, aFilterSNotInst; "Filter %s not installed; nothing to unl"...
0x18004d81b  mov     rbx, rax
0x18004d81e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004d823  mov     [rsp+88h+var_38], 0
0x18004d82b  lea     rcx, aWsbkunload; "WsbkUnload"
0x18004d832  mov     [rsp+88h+var_40], 0
0x18004d83b  mov     [rsp+88h+var_48], edi
0x18004d83f  mov     [rsp+88h+var_50], rbx
0x18004d844  mov     [rsp+88h+var_58], rcx
0x18004d849  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004d850  mov     [rsp+88h+var_60], rcx
0x18004d855  mov     [rsp+88h+var_68], 227h
0x18004d85d  jmp     loc_18004D937
0x18004d862  call    cs:__imp_GetLastError
0x18004d868  mov     esi, eax
0x18004d86a  test    eax, eax
0x18004d86c  jle     short loc_18004D877
0x18004d86e  movzx   esi, ax
0x18004d871  or      esi, 80070000h
0x18004d877  call    cs:__imp_GetLastError
0x18004d87d  mov     edi, eax
0x18004d87f  call    cs:__imp_CurrentIP
0x18004d885  mov     r8d, esi
0x18004d888  lea     rdx, aWsbkunloadFail_0; "WsbkUnload: Failed to close filter comm"...
0x18004d88f  mov     ecx, 2000000h; unsigned int
0x18004d894  mov     rbx, rax
0x18004d897  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004d89c  mov     [rsp+88h+var_38], 0
0x18004d8a4  lea     rcx, aWsbkunload; "WsbkUnload"
0x18004d8ab  mov     [rsp+88h+var_40], 0
0x18004d8b4  mov     [rsp+88h+var_48], edi
0x18004d8b8  mov     [rsp+88h+var_50], rbx
0x18004d8bd  mov     [rsp+88h+var_58], rcx
0x18004d8c2  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004d8c9  mov     [rsp+88h+var_60], rcx
0x18004d8ce  mov     [rsp+88h+var_68], 21Dh
0x18004d8d6  jmp     short loc_18004D937
0x18004d8d8  call    cs:__imp_GetLastError
0x18004d8de  mov     edi, eax
0x18004d8e0  call    cs:__imp_CurrentIP
0x18004d8e6  mov     r8d, esi
0x18004d8e9  lea     rdx, aWsbkunloadFail; "WsbkUnload: Failed FilterUnload(); hr ="...
0x18004d8f0  mov     ecx, 2000000h; unsigned int
0x18004d8f5  mov     rbx, rax
0x18004d8f8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004d8fd  mov     [rsp+88h+var_38], 0
0x18004d905  lea     rcx, aWsbkunload; "WsbkUnload"
0x18004d90c  mov     [rsp+88h+var_40], 0
0x18004d915  mov     [rsp+88h+var_48], edi
0x18004d919  mov     [rsp+88h+var_50], rbx
0x18004d91e  mov     [rsp+88h+var_58], rcx
0x18004d923  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004d92a  mov     [rsp+88h+var_60], rcx
0x18004d92f  mov     [rsp+88h+var_68], 22Bh
0x18004d937  xor     r9d, r9d
0x18004d93a  lea     r8, aD; "D"
0x18004d941  xor     edx, edx
0x18004d943  mov     rcx, rax
0x18004d946  call    cs:__imp_WdsSetupLogMessageW
0x18004d94c  cmp     ebp, 1
0x18004d94f  jnz     short loc_18004D96C
0x18004d951  cmp     [rsp+88h+arg_0], 0
0x18004d959  jnz     short loc_18004D96C
0x18004d95b  xor     r8d, r8d
0x18004d95e  lea     rcx, aSeloaddriverpr; "SeLoadDriverPrivilege"
0x18004d965  xor     edx, edx
0x18004d967  call    EnablePrivilegeEx
0x18004d96c  mov     eax, esi
0x18004d96e  add     rsp, 68h
0x18004d972  pop     rdi
0x18004d973  pop     rsi
0x18004d974  pop     rbp
0x18004d975  pop     rbx
0x18004d976  retn
```
