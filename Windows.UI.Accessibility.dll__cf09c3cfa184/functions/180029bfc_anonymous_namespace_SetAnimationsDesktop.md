# _anonymous_namespace_::SetAnimationsDesktop

- ea: `0x180029bfc`
- end: `0x180029cf0`
- name: `_anonymous_namespace_::SetAnimationsDesktop`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180029d24`

## callees

- `0x18000ea34`
- `0x180029bfc`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180029c42`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180029c86`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180029cb3`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180029c42`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180029c86`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180029cb3`

## string_xrefs

- `0x180029c95`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`
- `0x180029cc2`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`
- `0x180029cd2`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
BOOL __fastcall anonymous_namespace_::SetAnimationsDesktop(unsigned __int8 a1)
{
  unsigned __int64 v1; // rdi
  char *v2; // rbx
  UINT v3; // ecx
  const char *v4; // r9
  const char *v5; // r9
  BOOL result; // eax
  const char *v7; // r9
  _DWORD v8[5]; // [rsp+20h] [rbp-48h] BYREF
  char v9; // [rsp+34h] [rbp-34h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int pvParam; // [rsp+78h] [rbp+10h] BYREF
  BOOL v12; // [rsp+7Ch] [rbp+14h]

  v1 = a1;
  v2 = (char *)v8;
  v3 = 4099;
  v8[1] = 4101;
  v8[0] = 4099;
  v8[2] = 4103;
  v8[3] = 4117;
  v8[4] = 4119;
  while ( 1 )
  {
    if ( !SystemParametersInfoW(v3, 0, (PVOID)v1, 3u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.u"
                      "isettingscontroller.cpp",
        v4);
    v2 += 4;
    if ( v2 == &v9 )
      break;
    v3 = *(_DWORD *)v2;
  }
  pvParam = 8;
  v12 = (_BYTE)v1 != 0;
  if ( !SystemParametersInfoW(0x49u, 0, &pvParam, 3u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.uis"
                    "ettingscontroller.cpp",
      v5);
  result = SystemParametersInfoW(0x1043u, 0, (PVOID)v1, 3u);
  if ( !result )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.uis"
                    "ettingscontroller.cpp",
      v7);
  return result;
}

```

## disassembly

```asm
0x180029bfc  mov     rax, rsp
0x180029bff  push    rbx
0x180029c00  push    rbp
0x180029c01  push    rsi
0x180029c02  push    rdi
0x180029c03  sub     rsp, 48h
0x180029c07  movzx   edi, cl
0x180029c0a  lea     rbx, [rax-48h]
0x180029c0e  mov     ecx, 1003h; uiAction
0x180029c13  mov     dword ptr [rax-44h], 1005h
0x180029c1a  mov     [rax-48h], ecx
0x180029c1d  mov     dword ptr [rax-40h], 1007h
0x180029c24  mov     dword ptr [rax-3Ch], 1015h
0x180029c2b  mov     dword ptr [rax-38h], 1017h
0x180029c32  mov     rbp, [rsp+68h]
0x180029c37  mov     r9d, 3; fWinIni
0x180029c3d  mov     r8, rdi; pvParam
0x180029c40  xor     edx, edx; uiParam
0x180029c42  call    cs:__imp_SystemParametersInfoW
0x180029c48  test    eax, eax
0x180029c4a  jz      loc_180029CD2
0x180029c50  add     rbx, 4
0x180029c54  lea     rax, [rsp+68h+var_34]
0x180029c59  cmp     rbx, rax
0x180029c5c  jz      short loc_180029C62
0x180029c5e  mov     ecx, [rbx]
0x180029c60  jmp     short loc_180029C32
0x180029c62  xor     eax, eax
0x180029c64  mov     [rsp+68h+pvParam], 8
0x180029c6c  test    dil, dil
0x180029c6f  lea     r8, [rsp+68h+pvParam]; pvParam
0x180029c74  mov     r9d, 3; fWinIni
0x180029c7a  setnz   al
0x180029c7d  xor     edx, edx; uiParam
0x180029c7f  mov     [rsp+68h+arg_C], eax
0x180029c83  lea     ecx, [rdx+49h]; uiAction
0x180029c86  call    cs:__imp_SystemParametersInfoW
0x180029c8c  test    eax, eax
0x180029c8e  jnz     short loc_180029CA5
0x180029c90  mov     rcx, [rsp+68h]; this
0x180029c95  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029c9c  lea     edx, [rax+31h]; void *
0x180029c9f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180029ca5  xor     edx, edx; uiParam
0x180029ca7  mov     r8, rdi; pvParam
0x180029caa  mov     ecx, 1043h; uiAction
0x180029caf  lea     r9d, [rdx+3]; fWinIni
0x180029cb3  call    cs:__imp_SystemParametersInfoW
0x180029cb9  test    eax, eax
0x180029cbb  jnz     short loc_180029CE7
0x180029cbd  mov     rcx, [rsp+68h]; this
0x180029cc2  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029cc9  lea     edx, [rax+37h]; void *
0x180029ccc  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180029cd2  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029cd9  mov     edx, 26h ; '&'; void *
0x180029cde  mov     rcx, rbp; this
0x180029ce1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180029ce7  add     rsp, 48h
0x180029ceb  pop     rdi
0x180029cec  pop     rsi
0x180029ced  pop     rbp
0x180029cee  pop     rbx
0x180029cef  retn
```
