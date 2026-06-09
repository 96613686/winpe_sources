# WsbkLoad

- ea: `0x18004c9cc`
- end: `0x18004cab9`
- name: `WsbkLoad`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18004927c`

## callees

- `0x180009e04`
- `0x18003e794`
- `0x18004c9cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca1a`
- `WDSCORE!CurrentIP` at `0x18004ca22`
- `WDSCORE!CurrentIP` at `0x18004ca22`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004ca88`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004ca88`
- `FLTLIB!FilterLoad` at `0x18004c9fc`
- `FLTLIB!FilterLoad` at `0x18004c9fc`

## string_xrefs

- `0x18004c9e7`: `SeLoadDriverPrivilege`
- `0x18004caa0`: `SeLoadDriverPrivilege`

## pseudocode

```c
__int64 WsbkLoad()
{
  int v0; // ebp
  HRESULT v1; // esi
  DWORD LastError; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax
  DWORD v6; // [rsp+90h] [rbp+8h] BYREF

  v6 = 0;
  v0 = EnablePrivilegeEx(L"SeLoadDriverPrivilege", 1u, &v6);
  v1 = FilterLoad(L"WinSetupBak");
  if ( v1 < 0 )
  {
    if ( v1 == -2147024894 )
      v1 = -2145452013;
    LastError = GetLastError();
    v3 = CurrentIP();
    v4 = ConstructPartialMsgW(0x2000000, "WsbkLoad: Failed FilterLoad(); hr = 0x%x", v1);
    WdsSetupLogMessageW(
      v4,
      0,
      L"D",
      0,
      513,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkLoad",
      v3,
      LastError,
      0,
      0);
  }
  if ( v0 == 1 && !v6 )
    EnablePrivilegeEx(L"SeLoadDriverPrivilege", 0, 0);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18004c9cc  mov     rax, rsp
0x18004c9cf  push    rbx
0x18004c9d0  push    rbp
0x18004c9d1  push    rsi
0x18004c9d2  push    rdi
0x18004c9d3  sub     rsp, 68h
0x18004c9d7  lea     r8, [rax+8]
0x18004c9db  mov     dword ptr [rax+8], 0
0x18004c9e2  mov     edx, 1
0x18004c9e7  lea     rcx, aSeloaddriverpr; "SeLoadDriverPrivilege"
0x18004c9ee  call    EnablePrivilegeEx
0x18004c9f3  lea     rcx, aWinsetupbak; "WinSetupBak"
0x18004c9fa  mov     ebp, eax
0x18004c9fc  call    cs:__imp_FilterLoad
0x18004ca02  mov     esi, eax
0x18004ca04  test    eax, eax
0x18004ca06  jns     loc_18004CA8E
0x18004ca0c  mov     eax, 801F0013h
0x18004ca11  cmp     esi, 80070002h
0x18004ca17  cmovz   esi, eax
0x18004ca1a  call    cs:__imp_GetLastError
0x18004ca20  mov     edi, eax
0x18004ca22  call    cs:__imp_CurrentIP
0x18004ca28  mov     r8d, esi
0x18004ca2b  lea     rdx, aWsbkloadFailed; "WsbkLoad: Failed FilterLoad(); hr = 0x%"...
0x18004ca32  mov     ecx, 2000000h; unsigned int
0x18004ca37  mov     rbx, rax
0x18004ca3a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004ca3f  mov     [rsp+88h+var_38], 0
0x18004ca47  lea     rcx, aWsbkload; "WsbkLoad"
0x18004ca4e  mov     [rsp+88h+var_40], 0
0x18004ca57  lea     r8, aD; "D"
0x18004ca5e  mov     [rsp+88h+var_48], edi
0x18004ca62  xor     r9d, r9d
0x18004ca65  mov     [rsp+88h+var_50], rbx
0x18004ca6a  xor     edx, edx
0x18004ca6c  mov     [rsp+88h+var_58], rcx
0x18004ca71  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004ca78  mov     [rsp+88h+var_60], rcx
0x18004ca7d  mov     rcx, rax
0x18004ca80  mov     [rsp+88h+var_68], 201h
0x18004ca88  call    cs:__imp_WdsSetupLogMessageW
0x18004ca8e  cmp     ebp, 1
0x18004ca91  jnz     short loc_18004CAAE
0x18004ca93  cmp     [rsp+88h+arg_0], 0
0x18004ca9b  jnz     short loc_18004CAAE
0x18004ca9d  xor     r8d, r8d
0x18004caa0  lea     rcx, aSeloaddriverpr; "SeLoadDriverPrivilege"
0x18004caa7  xor     edx, edx
0x18004caa9  call    EnablePrivilegeEx
0x18004caae  mov     eax, esi
0x18004cab0  add     rsp, 68h
0x18004cab4  pop     rdi
0x18004cab5  pop     rsi
0x18004cab6  pop     rbp
0x18004cab7  pop     rbx
0x18004cab8  retn
```
