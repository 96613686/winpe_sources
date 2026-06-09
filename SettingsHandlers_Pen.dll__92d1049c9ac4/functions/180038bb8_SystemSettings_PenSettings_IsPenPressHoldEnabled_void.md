# SystemSettings::PenSettings::IsPenPressHoldEnabled(void)

- ea: `0x180038bb8`
- end: `0x180038c07`
- name: `?IsPenPressHoldEnabled@PenSettings@SystemSettings@@YA_NXZ`
- size: `79`
- prototype: `bool __fastcall(SystemSettings::PenSettings *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800384f0`
- `0x18003aad0`

## callees

- `0x1800030e0`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180038be7`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180038be7`

## pseudocode

```c
bool __fastcall SystemSettings::PenSettings::IsPenPressHoldEnabled(SystemSettings::PenSettings *this)
{
  _DWORD pvParam[8]; // [rsp+20h] [rbp-38h] BYREF

  memset(pvParam, 0, 28);
  SystemParametersInfoW(0x96u, 0x1Cu, pvParam, 0);
  return pvParam[1] == 1;
}

```

## disassembly

```asm
0x180038bb8  sub     rsp, 58h
0x180038bbc  mov     rax, cs:__security_cookie
0x180038bc3  xor     rax, rsp
0x180038bc6  mov     [rsp+58h+var_18], rax
0x180038bcb  xorps   xmm0, xmm0
0x180038bce  lea     r8, [rsp+58h+pvParam]; pvParam
0x180038bd3  xor     r9d, r9d; fWinIni
0x180038bd6  movups  xmmword ptr [rsp+58h+pvParam], xmm0
0x180038bdb  movups  xmmword ptr [rsp+58h+pvParam+0Ch], xmm0
0x180038be0  lea     edx, [r9+1Ch]; uiParam
0x180038be4  lea     ecx, [rdx+7Ah]; uiAction
0x180038be7  call    cs:__imp_SystemParametersInfoW
0x180038bed  cmp     [rsp+58h+pvParam+4], 1
0x180038bf2  setz    al
0x180038bf5  mov     rcx, [rsp+58h+var_18]
0x180038bfa  xor     rcx, rsp; StackCookie
0x180038bfd  call    __security_check_cookie
0x180038c02  add     rsp, 58h
0x180038c06  retn
```
