# UXFrame::StartMessageLoop(void)

- ea: `0x18004b29c`
- end: `0x18004b3ee`
- name: `?StartMessageLoop@UXFrame@@QEAAXXZ`
- size: `338`
- prototype: `void __fastcall(UXFrame *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016660`

## callees

- `0x180002b20`
- `0x18001047c`
- `0x18001049c`
- `0x180017164`
- `0x180037e0c`
- `0x1800393c0`
- `0x18004b29c`

## import_xrefs

- `USER32!IsWindow` at `0x18004b346`
- `USER32!IsWindow` at `0x18004b346`
- `USER32!IsWindowVisible` at `0x18004b35b`
- `USER32!IsWindowVisible` at `0x18004b35b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004b2f3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004b2f3`

## string_xrefs

- `0x18004b37d`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x18004b394`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x18004b3ae`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x18004b3c5`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x18004b3dc`: `pcshell\shell\uxframe\dll\UXFrame.cpp`

## pseudocode

```c
void __fastcall UXFrame::StartMessageLoop(UXFrame *this)
{
  HRESULT v2; // eax
  const char *v3; // r9
  int v4; // eax
  HWND v5; // rcx
  const char *v6; // r9
  const char *v7; // r9
  int lpdwindex; // [rsp+20h] [rbp-38h]
  UXFrame *v9; // [rsp+30h] [rbp-28h] BYREF
  DWORD dwindex; // [rsp+38h] [rbp-20h] BYREF
  HANDLE pHandles; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v9 = this;
  UXFrameTelemetry::StartMessageLoop<UXFrame *>(&v9);
  pHandles = (HANDLE)*((_QWORD *)this + 33);
  dwindex = 0;
  v2 = CoWaitForMultipleHandles(0x18u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  if ( v2 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
      (const char *)(unsigned int)v2,
      lpdwindex);
  v9 = this;
  UXFrameTelemetry::EndMessageLoop<UXFrame *>(&v9);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
  {
    v4 = *((_DWORD *)this + 64);
    if ( v4 != 4 && v4 >= 2 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xAF,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
        v3);
    if ( *((_QWORD *)this + 26) )
    {
      v5 = (HWND)*((_QWORD *)this + 37);
      if ( !v5 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB4,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
          v3);
      if ( !IsWindow(v5) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB5,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
          v6);
      if ( IsWindowVisible(*((HWND *)this + 37)) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB9,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
          v7);
    }
  }
}

```

## disassembly

```asm
0x18004b29c  push    rbx
0x18004b29e  sub     rsp, 50h
0x18004b2a2  mov     rax, cs:__security_cookie
0x18004b2a9  xor     rax, rsp
0x18004b2ac  mov     [rsp+58h+var_10], rax
0x18004b2b1  mov     rbx, rcx
0x18004b2b4  mov     [rsp+58h+var_28], rcx
0x18004b2b9  lea     rcx, [rsp+58h+var_28]
0x18004b2be  call    ??$StartMessageLoop@PEAVUXFrame@@@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@@Z; UXFrameTelemetry::StartMessageLoop<UXFrame *>(UXFrame * &&)
0x18004b2c3  mov     rax, [rbx+108h]
0x18004b2ca  lea     r9, [rsp+58h+pHandles]; pHandles
0x18004b2cf  mov     r8d, 1; cHandles
0x18004b2d5  mov     [rsp+58h+pHandles], rax
0x18004b2da  lea     rax, [rsp+58h+dwindex]
0x18004b2df  mov     [rsp+58h+dwindex], 0
0x18004b2e7  or      edx, 0FFFFFFFFh; dwTimeout
0x18004b2ea  mov     qword ptr [rsp+58h+lpdwindex], rax; int
0x18004b2ef  lea     ecx, [r8+17h]; dwFlags
0x18004b2f3  call    cs:__imp_CoWaitForMultipleHandles
0x18004b2f9  test    eax, eax
0x18004b2fb  js      loc_18004B38F
0x18004b301  lea     rcx, [rsp+58h+var_28]
0x18004b306  mov     [rsp+58h+var_28], rbx
0x18004b30b  call    ??$EndMessageLoop@PEAVUXFrame@@@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@@Z; UXFrameTelemetry::EndMessageLoop<UXFrame *>(UXFrame * &&)
0x18004b310  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18004b317  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18004b31c  test    al, al
0x18004b31e  jz      short loc_18004B365
0x18004b320  mov     eax, [rbx+100h]
0x18004b326  cmp     eax, 4
0x18004b329  jz      short loc_18004B330
0x18004b32b  cmp     eax, 2
0x18004b32e  jge     short loc_18004B3A9
0x18004b330  cmp     qword ptr [rbx+0D0h], 0
0x18004b338  jz      short loc_18004B365
0x18004b33a  mov     rcx, [rbx+128h]; hWnd
0x18004b341  test    rcx, rcx
0x18004b344  jz      short loc_18004B3C0
0x18004b346  call    cs:__imp_IsWindow
0x18004b34c  test    eax, eax
0x18004b34e  jz      loc_18004B3D7
0x18004b354  mov     rcx, [rbx+128h]; hWnd
0x18004b35b  call    cs:__imp_IsWindowVisible
0x18004b361  test    eax, eax
0x18004b363  jnz     short loc_18004B378
0x18004b365  mov     rcx, [rsp+58h+var_10]
0x18004b36a  xor     rcx, rsp; StackCookie
0x18004b36d  call    __security_check_cookie
0x18004b372  add     rsp, 50h
0x18004b376  pop     rbx
0x18004b377  retn
0x18004b378  mov     rcx, [rsp+58h]; this
0x18004b37d  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004b384  mov     edx, 0B9h; void *
0x18004b389  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004b38f  mov     rcx, [rsp+58h]; this
0x18004b394  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004b39b  mov     r9d, eax; char *
0x18004b39e  mov     edx, 0A7h; void *
0x18004b3a3  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18004b3a9  mov     rcx, [rsp+58h]; this
0x18004b3ae  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004b3b5  mov     edx, 0AFh; void *
0x18004b3ba  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004b3c0  mov     rcx, [rsp+58h]; this
0x18004b3c5  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004b3cc  mov     edx, 0B4h; void *
0x18004b3d1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004b3d7  mov     rcx, [rsp+58h]; this
0x18004b3dc  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004b3e3  mov     edx, 0B5h; void *
0x18004b3e8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
