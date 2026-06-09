# SystemSettings::PenSettings::CPenPressHoldTime::SetValue(ulong)

- ea: `0x18003a2f0`
- end: `0x18003a386`
- name: `?SetValue@CPenPressHoldTime@PenSettings@SystemSettings@@EEAAJK@Z`
- size: `150`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CPenPressHoldTime *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800030e0`
- `0x180037984`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003a360`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003a360`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CPenPressHoldTime::SetValue(
        SystemSettings::PenSettings::CPenPressHoldTime *this,
        int a2)
{
  _OWORD *PenSettings; // rax
  int v5; // edi
  __int128 v7; // [rsp+20h] [rbp-68h] BYREF
  __int128 pvParam; // [rsp+48h] [rbp-40h] BYREF
  __int128 v9; // [rsp+58h] [rbp-30h]
  __int64 v10; // [rsp+68h] [rbp-20h]

  PenSettings = SystemSettings::PenSettings::GetPenSettings(&v7);
  v5 = *((_DWORD *)this + 60) + *((_DWORD *)this + 64) * (a2 - *((_DWORD *)this + 62));
  pvParam = *PenSettings;
  v9 = PenSettings[1];
  v10 = *((_QWORD *)PenSettings + 4);
  LODWORD(v9) = v5;
  SystemParametersInfoW(0x95u, 0x28u, &pvParam, 3u);
  return 0;
}

```

## disassembly

```asm
0x18003a2f0  mov     [rsp+arg_10], rbx
0x18003a2f5  push    rdi
0x18003a2f6  sub     rsp, 80h
0x18003a2fd  mov     rax, cs:__security_cookie
0x18003a304  xor     rax, rsp
0x18003a307  mov     [rsp+88h+var_18], rax
0x18003a30c  mov     rbx, rcx
0x18003a30f  mov     edi, edx
0x18003a311  lea     rcx, [rsp+88h+var_68]
0x18003a316  call    ?GetPenSettings@PenSettings@SystemSettings@@YA?AUtagPEN_PARAMETERS@@XZ; SystemSettings::PenSettings::GetPenSettings(void)
0x18003a31b  sub     edi, [rbx+0F8h]
0x18003a321  lea     r8, [rsp+88h+pvParam]; pvParam
0x18003a326  imul    edi, [rbx+100h]
0x18003a32d  mov     r9d, 3; fWinIni
0x18003a333  movups  xmm0, xmmword ptr [rax]
0x18003a336  lea     edx, [r9+25h]; uiParam
0x18003a33a  add     edi, [rbx+0F0h]
0x18003a340  lea     ecx, [rdx+6Dh]; uiAction
0x18003a343  movups  [rsp+88h+pvParam], xmm0
0x18003a348  movups  xmm1, xmmword ptr [rax+10h]
0x18003a34c  movups  [rsp+88h+var_30], xmm1
0x18003a351  movsd   xmm0, qword ptr [rax+20h]
0x18003a356  movsd   [rsp+88h+var_20], xmm0
0x18003a35c  mov     dword ptr [rsp+88h+var_30], edi
0x18003a360  call    cs:__imp_SystemParametersInfoW
0x18003a366  xor     eax, eax
0x18003a368  mov     rcx, [rsp+88h+var_18]
0x18003a36d  xor     rcx, rsp; StackCookie
0x18003a370  call    __security_check_cookie
0x18003a375  mov     rbx, [rsp+88h+arg_10]
0x18003a37d  add     rsp, 80h
0x18003a384  pop     rdi
0x18003a385  retn
```
