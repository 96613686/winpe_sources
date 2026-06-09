# SystemSettings::PenSettings::CPenDblClickDistance::SetValue(ulong)

- ea: `0x18003a170`
- end: `0x18003a206`
- name: `?SetValue@CPenDblClickDistance@PenSettings@SystemSettings@@EEAAJK@Z`
- size: `150`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CPenDblClickDistance *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800030e0`
- `0x180037984`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003a1e0`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003a1e0`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CPenDblClickDistance::SetValue(
        SystemSettings::PenSettings::CPenDblClickDistance *this,
        int a2)
{
  _OWORD *PenSettings; // rax
  int v5; // edi
  __int128 v7; // [rsp+20h] [rbp-68h] BYREF
  _OWORD pvParam[2]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v9; // [rsp+68h] [rbp-20h]

  PenSettings = SystemSettings::PenSettings::GetPenSettings(&v7);
  v5 = *((_DWORD *)this + 52) + *((_DWORD *)this + 56) * (a2 - *((_DWORD *)this + 54));
  pvParam[0] = *PenSettings;
  pvParam[1] = PenSettings[1];
  v9 = *((_QWORD *)PenSettings + 4);
  DWORD1(pvParam[0]) = v5;
  SystemParametersInfoW(0x95u, 0x28u, pvParam, 3u);
  return 0;
}

```

## disassembly

```asm
0x18003a170  mov     [rsp+arg_10], rbx
0x18003a175  push    rdi
0x18003a176  sub     rsp, 80h
0x18003a17d  mov     rax, cs:__security_cookie
0x18003a184  xor     rax, rsp
0x18003a187  mov     [rsp+88h+var_18], rax
0x18003a18c  mov     rbx, rcx
0x18003a18f  mov     edi, edx
0x18003a191  lea     rcx, [rsp+88h+var_68]
0x18003a196  call    ?GetPenSettings@PenSettings@SystemSettings@@YA?AUtagPEN_PARAMETERS@@XZ; SystemSettings::PenSettings::GetPenSettings(void)
0x18003a19b  sub     edi, [rbx+0D8h]
0x18003a1a1  lea     r8, [rsp+88h+pvParam]; pvParam
0x18003a1a6  imul    edi, [rbx+0E0h]
0x18003a1ad  mov     r9d, 3; fWinIni
0x18003a1b3  movups  xmm0, xmmword ptr [rax]
0x18003a1b6  lea     edx, [r9+25h]; uiParam
0x18003a1ba  add     edi, [rbx+0D0h]
0x18003a1c0  lea     ecx, [rdx+6Dh]; uiAction
0x18003a1c3  movups  [rsp+88h+pvParam], xmm0
0x18003a1c8  movups  xmm1, xmmword ptr [rax+10h]
0x18003a1cc  movups  [rsp+88h+var_30], xmm1
0x18003a1d1  movsd   xmm0, qword ptr [rax+20h]
0x18003a1d6  movsd   [rsp+88h+var_20], xmm0
0x18003a1dc  mov     dword ptr [rsp+88h+pvParam+4], edi
0x18003a1e0  call    cs:__imp_SystemParametersInfoW
0x18003a1e6  xor     eax, eax
0x18003a1e8  mov     rcx, [rsp+88h+var_18]
0x18003a1ed  xor     rcx, rsp; StackCookie
0x18003a1f0  call    __security_check_cookie
0x18003a1f5  mov     rbx, [rsp+88h+arg_10]
0x18003a1fd  add     rsp, 80h
0x18003a204  pop     rdi
0x18003a205  retn
```
