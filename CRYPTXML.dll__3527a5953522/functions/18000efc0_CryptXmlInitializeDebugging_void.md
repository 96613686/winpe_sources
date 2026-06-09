# CryptXmlInitializeDebugging(void)

- ea: `0x18000efc0`
- end: `0x18000f0fa`
- name: `?CryptXmlInitializeDebugging@@YAXXZ`
- size: `314`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015c70`

## callees

- `0x18000efc0`
- `0x180018625`
- `0x180018640`

## import_xrefs

- `ntdll!EtwRegisterTraceGuidsW` at `0x18000f0c5`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18000f0c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000f07c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000f07c`

## string_xrefs

- `0x18000f031`: `Microsoft\CryptXml`

## pseudocode

```c
void CryptXmlInitializeDebugging(void)
{
  __int64 *v0; // rbx
  __int64 *v1; // rsi
  __int64 v2; // rdi
  _QWORD v3[2]; // [rsp+40h] [rbp-288h] BYREF
  __int128 v4; // [rsp+50h] [rbp-278h] BYREF
  _OWORD v5[2]; // [rsp+60h] [rbp-268h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-248h] BYREF

  qword_180022F88 = 1;
  qword_180022F80 = 0;
  v0 = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CryptXmlGlobalDebugTraceControlGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v1 = &WPP_REGISTRATION_GUIDS;
  memset_0(Filename, 0, 0x208u);
  v4 = *(_OWORD *)L"Microsoft\\CryptXml";
  v5[0] = *(_OWORD *)L"t\\CryptXml";
  *(_QWORD *)((char *)v5 + 14) = *(_QWORD *)L"Xml";
  do
  {
    v2 = *v1;
    v3[0] = v2;
    ++v1;
    v3[1] = 0;
    v0[4] = v2;
    GetModuleFileNameW(0, Filename, 0x104u);
    EtwRegisterTraceGuidsW(WppControlCallback, v0, v2, 1, v3, Filename, &v4, v0 + 1);
    v0 = (__int64 *)*v0;
  }
  while ( v0 );
}

```

## disassembly

```asm
0x18000efc0  push    rbx
0x18000efc2  push    rbp
0x18000efc3  push    rsi
0x18000efc4  push    rdi
0x18000efc5  sub     rsp, 2A8h
0x18000efcc  mov     rax, cs:__security_cookie
0x18000efd3  xor     rax, rsp
0x18000efd6  mov     [rsp+2C8h+var_38], rax
0x18000efde  xor     ebp, ebp
0x18000efe0  mov     cs:qword_180022F88, 1
0x18000efeb  lea     rax, WPP_ThisDir_CTLGUID_CryptXmlGlobalDebugTraceControlGuid
0x18000eff2  mov     cs:qword_180022F80, rbp
0x18000eff9  lea     rbx, WPP_MAIN_CB
0x18000f000  mov     cs:WPP_MAIN_CB, rbp
0x18000f007  xor     edx, edx; Val
0x18000f009  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000f010  mov     r8d, 208h; Size
0x18000f016  mov     cs:WPP_GLOBAL_Control, rbx
0x18000f01d  lea     rcx, [rsp+2C8h+Filename]; void *
0x18000f025  lea     rsi, WPP_REGISTRATION_GUIDS
0x18000f02c  call    memset_0
0x18000f031  movups  xmm0, xmmword ptr cs:aMicrosoftCrypt; "Microsoft\\CryptXml"
0x18000f038  movups  xmm1, xmmword ptr cs:aMicrosoftCrypt+10h; "t\\CryptXml"
0x18000f03f  movups  [rsp+2C8h+var_278], xmm0
0x18000f044  movsd   xmm0, qword ptr cs:aMicrosoftCrypt+1Eh; "Xml"
0x18000f04c  movups  xmmword ptr [rsp+2C8h+var_268], xmm1
0x18000f051  movsd   qword ptr [rsp+2C8h+var_268+0Eh], xmm0
0x18000f057  mov     rdi, [rsi]
0x18000f05a  lea     rdx, [rsp+2C8h+Filename]; lpFilename
0x18000f062  mov     [rsp+2C8h+var_288], rdi
0x18000f067  lea     rsi, [rsi+8]
0x18000f06b  mov     [rsp+2C8h+var_280], rbp
0x18000f070  mov     r8d, 104h; nSize
0x18000f076  xor     ecx, ecx; hModule
0x18000f078  mov     [rbx+20h], rdi
0x18000f07c  call    cs:__imp_GetModuleFileNameW
0x18000f083  nop     dword ptr [rax+rax+00h]
0x18000f088  lea     rax, [rbx+8]
0x18000f08c  mov     r9d, 1
0x18000f092  mov     [rsp+2C8h+var_290], rax
0x18000f097  lea     rcx, WppControlCallback
0x18000f09e  lea     rax, [rsp+2C8h+var_278]
0x18000f0a3  mov     r8, rdi
0x18000f0a6  mov     [rsp+2C8h+var_298], rax
0x18000f0ab  mov     rdx, rbx
0x18000f0ae  lea     rax, [rsp+2C8h+Filename]
0x18000f0b6  mov     [rsp+2C8h+var_2A0], rax
0x18000f0bb  lea     rax, [rsp+2C8h+var_288]
0x18000f0c0  mov     [rsp+2C8h+var_2A8], rax
0x18000f0c5  call    cs:__imp_EtwRegisterTraceGuidsW
0x18000f0cc  nop     dword ptr [rax+rax+00h]
0x18000f0d1  mov     rbx, [rbx]
0x18000f0d4  test    rbx, rbx
0x18000f0d7  jnz     loc_18000F057
0x18000f0dd  mov     rcx, [rsp+2C8h+var_38]
0x18000f0e5  xor     rcx, rsp; StackCookie
0x18000f0e8  call    __security_check_cookie
0x18000f0ed  add     rsp, 2A8h
0x18000f0f4  pop     rdi
0x18000f0f5  pop     rsi
0x18000f0f6  pop     rbp
0x18000f0f7  pop     rbx
0x18000f0f8  retn
```
