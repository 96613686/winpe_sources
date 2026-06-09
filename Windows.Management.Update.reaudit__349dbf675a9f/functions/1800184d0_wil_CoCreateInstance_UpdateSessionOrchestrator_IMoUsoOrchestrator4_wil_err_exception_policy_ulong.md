# wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(ulong)

- ea: `0x1800184d0`
- end: `0x18001853a`
- name: `??$CoCreateInstance@VUpdateSessionOrchestrator@@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@0@K@Z`
- size: `106`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001d150`
- `0x180023118`
- `0x18002499c`

## callees

- `0x1800184d0`
- `0x18001d9e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018506`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018506`

## string_xrefs

- `0x180018528`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(
        LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
               0,
               4u,
               &GUID_7aeb09a0_1dbe_4948_b385_116acfb34a2d,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x1800184d0  mov     rax, rsp
0x1800184d3  mov     [rax+8], rcx
0x1800184d7  push    rbx
0x1800184d8  sub     rsp, 40h
0x1800184dc  mov     rbx, rcx
0x1800184df  and     dword ptr [rax-18h], 0
0x1800184e3  mov     dword ptr [rax-18h], 2
0x1800184ea  and     qword ptr [rcx], 0
0x1800184ee  mov     [rax-28h], rcx
0x1800184f2  lea     r9, _GUID_7aeb09a0_1dbe_4948_b385_116acfb34a2d; riid
0x1800184f9  xor     edx, edx; pUnkOuter
0x1800184fb  lea     r8d, [rdx+4]; dwClsContext
0x1800184ff  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x180018506  call    cs:__imp_CoCreateInstance
0x18001850d  nop     dword ptr [rax+rax+00h]
0x180018512  mov     rcx, [rsp+48h]; this
0x180018517  test    eax, eax
0x180018519  js      short loc_180018525
0x18001851b  mov     rax, rbx
0x18001851e  add     rsp, 40h
0x180018522  pop     rbx
0x180018523  retn
0x180018525  mov     r9d, eax; char *
0x180018528  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001852f  mov     edx, 1C60h; void *
0x180018534  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
