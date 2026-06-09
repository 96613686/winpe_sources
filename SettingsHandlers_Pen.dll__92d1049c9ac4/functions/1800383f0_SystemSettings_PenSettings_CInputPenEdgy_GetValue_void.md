# SystemSettings::PenSettings::CInputPenEdgy::GetValue(void)

- ea: `0x1800383f0`
- end: `0x180038462`
- name: `?GetValue@CInputPenEdgy@PenSettings@SystemSettings@@UEAA_NXZ`
- size: `114`
- prototype: `bool __fastcall(SystemSettings::PenSettings::CInputPenEdgy *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800030e0`
- `0x1800383f0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003842a`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003842a`

## pseudocode

```c
bool __fastcall SystemSettings::PenSettings::CInputPenEdgy::GetValue(SystemSettings::PenSettings::CInputPenEdgy *this)
{
  _OWORD pvParam[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v4; // [rsp+40h] [rbp-18h]

  v4 = 0;
  memset(pvParam, 0, sizeof(pvParam));
  if ( SystemParametersInfoW(0x94u, 0x28u, pvParam, 0) )
    return (*(__int64 (__fastcall **)(SystemSettings::PenSettings::CInputPenEdgy *, _OWORD *))(*(_QWORD *)this + 280LL))(
             this,
             pvParam);
  else
    return 0;
}

```

## disassembly

```asm
0x1800383f0  push    rbx
0x1800383f2  sub     rsp, 50h
0x1800383f6  mov     rax, cs:__security_cookie
0x1800383fd  xor     rax, rsp
0x180038400  mov     [rsp+58h+var_10], rax
0x180038405  xor     eax, eax
0x180038407  lea     r8, [rsp+58h+pvParam]; pvParam
0x18003840c  xorps   xmm0, xmm0
0x18003840f  mov     [rsp+58h+var_18], rax
0x180038414  mov     rbx, rcx
0x180038417  xor     r9d, r9d; fWinIni
0x18003841a  movups  [rsp+58h+pvParam], xmm0
0x18003841f  lea     edx, [rax+28h]; uiParam
0x180038422  lea     ecx, [rdx+6Ch]; uiAction
0x180038425  movups  [rsp+58h+var_28], xmm0
0x18003842a  call    cs:__imp_SystemParametersInfoW
0x180038430  test    eax, eax
0x180038432  jz      short loc_18003844D
0x180038434  mov     rax, [rbx]
0x180038437  lea     rdx, [rsp+58h+pvParam]
0x18003843c  mov     rcx, rbx
0x18003843f  mov     rax, [rax+118h]
0x180038446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003844b  jmp     short loc_18003844F
0x18003844d  xor     al, al
0x18003844f  mov     rcx, [rsp+58h+var_10]
0x180038454  xor     rcx, rsp; StackCookie
0x180038457  call    __security_check_cookie
0x18003845c  add     rsp, 50h
0x180038460  pop     rbx
0x180038461  retn
```
