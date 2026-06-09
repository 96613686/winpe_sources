# SystemSettings::PenSettings::GetPenSettings(void)

- ea: `0x180037984`
- end: `0x1800379b8`
- name: `?GetPenSettings@PenSettings@SystemSettings@@YA?AUtagPEN_PARAMETERS@@XZ`
- size: `52`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180038470`
- `0x1800384b0`
- `0x180038500`
- `0x18003a170`
- `0x18003a210`
- `0x18003a2f0`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800379a9`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800379a9`

## pseudocode

```c
_OWORD *__fastcall SystemSettings::PenSettings::GetPenSettings(_OWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  *((_QWORD *)a1 + 4) = 0;
  SystemParametersInfoW(0x94u, 0x28u, a1, 0);
  return a1;
}

```

## disassembly

```asm
0x180037984  push    rbx
0x180037986  sub     rsp, 20h
0x18003798a  xor     eax, eax
0x18003798c  xorps   xmm0, xmm0
0x18003798f  movups  xmmword ptr [rcx], xmm0
0x180037992  mov     rbx, rcx
0x180037995  mov     r8, rcx; pvParam
0x180037998  movups  xmmword ptr [rcx+10h], xmm0
0x18003799c  lea     edx, [rax+28h]; uiParam
0x18003799f  mov     [rcx+20h], rax
0x1800379a3  lea     ecx, [rdx+6Ch]; uiAction
0x1800379a6  xor     r9d, r9d; fWinIni
0x1800379a9  call    cs:__imp_SystemParametersInfoW
0x1800379af  mov     rax, rbx
0x1800379b2  add     rsp, 20h
0x1800379b6  pop     rbx
0x1800379b7  retn
```
