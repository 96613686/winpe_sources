# WppInitUm

- ea: `0x18000a378`
- end: `0x18000a471`
- name: `WppInitUm`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a0c0`
- `0x18000a1b0`

## callees

- `0x18000a378`
- `0x18000c4a4`
- `0x18000c560`

## import_xrefs

- `ntdll!EtwRegisterTraceGuidsW` at `0x18000a43e`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18000a43e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a3fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a3fe`

## pseudocode

```c
void *WppInitUm()
{
  _QWORD *v0; // rdi
  __int64 *v1; // rsi
  void *result; // rax
  __int64 v3; // rbx
  _QWORD v4[2]; // [rsp+40h] [rbp-258h] BYREF
  _OWORD v5[2]; // [rsp+50h] [rbp-248h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-228h] BYREF

  v0 = WPP_GLOBAL_Control;
  v1 = &WPP_REGISTRATION_GUIDS;
  result = memset_0(Filename, 0, 0x208u);
  v5[0] = *(_OWORD *)L"NtlmShared";
  *(_QWORD *)((char *)v5 + 14) = *(_QWORD *)L"red";
  while ( v0 )
  {
    v3 = *v1;
    v4[0] = v3;
    ++v1;
    v4[1] = 0;
    v0[4] = v3;
    GetModuleFileNameW(0, Filename, 0x104u);
    result = (void *)EtwRegisterTraceGuidsW(WppControlCallback, v0, v3, 1, v4, Filename, v5, v0 + 1);
    v0 = (_QWORD *)*v0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a378  mov     [rsp+arg_0], rbx
0x18000a37d  mov     [rsp+arg_8], rsi
0x18000a382  push    rdi
0x18000a383  sub     rsp, 290h
0x18000a38a  mov     rax, cs:__security_cookie
0x18000a391  xor     rax, rsp
0x18000a394  mov     [rsp+298h+var_18], rax
0x18000a39c  mov     rdi, cs:WPP_GLOBAL_Control
0x18000a3a3  lea     rcx, [rsp+298h+Filename]; void *
0x18000a3a8  xor     edx, edx; Val
0x18000a3aa  lea     rsi, WPP_REGISTRATION_GUIDS
0x18000a3b1  mov     r8d, 208h; Size
0x18000a3b7  call    memset_0
0x18000a3bc  movups  xmm0, xmmword ptr cs:aNtlmshared; "NtlmShared"
0x18000a3c3  movsd   xmm1, qword ptr cs:aNtlmshared+0Eh; "red"
0x18000a3cb  movups  xmmword ptr [rsp+298h+var_248], xmm0
0x18000a3d0  movsd   qword ptr [rsp+298h+var_248+0Eh], xmm1
0x18000a3d6  jmp     short loc_18000A447
0x18000a3d8  mov     rbx, [rsi]
0x18000a3db  lea     rdx, [rsp+298h+Filename]; lpFilename
0x18000a3e0  mov     [rsp+298h+var_258], rbx
0x18000a3e5  lea     rsi, [rsi+8]
0x18000a3e9  mov     [rsp+298h+var_250], 0
0x18000a3f2  mov     r8d, 104h; nSize
0x18000a3f8  xor     ecx, ecx; hModule
0x18000a3fa  mov     [rdi+20h], rbx
0x18000a3fe  call    cs:__imp_GetModuleFileNameW
0x18000a404  lea     rax, [rdi+8]
0x18000a408  mov     r9d, 1
0x18000a40e  mov     [rsp+298h+var_260], rax
0x18000a413  lea     rcx, WppControlCallback
0x18000a41a  lea     rax, [rsp+298h+var_248]
0x18000a41f  mov     r8, rbx
0x18000a422  mov     [rsp+298h+var_268], rax
0x18000a427  mov     rdx, rdi
0x18000a42a  lea     rax, [rsp+298h+Filename]
0x18000a42f  mov     [rsp+298h+var_270], rax
0x18000a434  lea     rax, [rsp+298h+var_258]
0x18000a439  mov     [rsp+298h+var_278], rax
0x18000a43e  call    cs:__imp_EtwRegisterTraceGuidsW
0x18000a444  mov     rdi, [rdi]
0x18000a447  test    rdi, rdi
0x18000a44a  jnz     short loc_18000A3D8
0x18000a44c  mov     rcx, [rsp+298h+var_18]
0x18000a454  xor     rcx, rsp; StackCookie
0x18000a457  call    __security_check_cookie
0x18000a45c  lea     r11, [rsp+298h+var_8]
0x18000a464  mov     rbx, [r11+10h]
0x18000a468  mov     rsi, [r11+18h]
0x18000a46c  mov     rsp, r11
0x18000a46f  pop     rdi
0x18000a470  retn
```
