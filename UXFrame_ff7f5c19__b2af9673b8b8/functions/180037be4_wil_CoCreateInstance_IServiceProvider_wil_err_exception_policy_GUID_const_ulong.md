# wil::CoCreateInstance<IServiceProvider,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x180037be4`
- end: `0x180037c4e`
- name: `??$CoCreateInstance@UIServiceProvider@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIServiceProvider@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800436bc`

## callees

- `0x180017024`
- `0x180037be4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037c20`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037c20`

## string_xrefs

- `0x180037c32`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall wil::CoCreateInstance<IServiceProvider,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_6b3b8d23_fa8d_40b9_8dbd_b950333e2c52,
               0,
               4u,
               &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x180037be4  mov     rax, rsp
0x180037be7  mov     [rax+8], rcx
0x180037beb  push    rbx
0x180037bec  sub     rsp, 40h
0x180037bf0  mov     rbx, rcx
0x180037bf3  mov     dword ptr [rax-18h], 0
0x180037bfa  mov     dword ptr [rax-18h], 1
0x180037c01  mov     qword ptr [rcx], 0
0x180037c08  mov     [rax-28h], rcx
0x180037c0c  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180037c13  xor     edx, edx; pUnkOuter
0x180037c15  lea     r8d, [rdx+4]; dwClsContext
0x180037c19  lea     rcx, _GUID_6b3b8d23_fa8d_40b9_8dbd_b950333e2c52; rclsid
0x180037c20  call    cs:__imp_CoCreateInstance
0x180037c26  test    eax, eax
0x180037c28  jns     short loc_180037C44
0x180037c2a  mov     rcx, [rsp+48h]; this
0x180037c2f  mov     r9d, eax; char *
0x180037c32  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x180037c39  mov     edx, 1CBEh; void *
0x180037c3e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180037c44  mov     rax, rbx
0x180037c47  add     rsp, 40h
0x180037c4b  pop     rbx
0x180037c4c  retn
```
