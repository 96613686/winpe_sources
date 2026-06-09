# wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(ulong)

- ea: `0x180017800`
- end: `0x180017869`
- name: `??$CoCreateInstance@VUpdateSessionOrchestrator@@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@0@K@Z`
- size: `105`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bf00`
- `0x180021e90`
- `0x1800236ec`

## callees

- `0x180017800`
- `0x18001c7d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001783c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001783c`

## string_xrefs

- `0x180017857`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

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
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x180017800  mov     rax, rsp
0x180017803  mov     [rax+8], rcx
0x180017807  push    rbx
0x180017808  sub     rsp, 40h
0x18001780c  mov     rbx, rcx
0x18001780f  mov     dword ptr [rax-18h], 0
0x180017816  mov     dword ptr [rax-18h], 2
0x18001781d  mov     qword ptr [rcx], 0
0x180017824  mov     [rax-28h], rcx
0x180017828  lea     r9, _GUID_7aeb09a0_1dbe_4948_b385_116acfb34a2d; riid
0x18001782f  xor     edx, edx; pUnkOuter
0x180017831  lea     r8d, [rdx+4]; dwClsContext
0x180017835  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x18001783c  call    cs:__imp_CoCreateInstance
0x180017842  mov     rcx, [rsp+48h]; this
0x180017847  test    eax, eax
0x180017849  js      short loc_180017854
0x18001784b  mov     rax, rbx
0x18001784e  add     rsp, 40h
0x180017852  pop     rbx
0x180017853  retn
0x180017854  mov     r9d, eax; char *
0x180017857  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001785e  mov     edx, 1CBEh; void *
0x180017863  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
