# wil::CoCreateInstance<IServiceProvider,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x18002e64c`
- end: `0x18002e6b6`
- name: `??$CoCreateInstance@UIServiceProvider@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIServiceProvider@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002e730`

## callees

- `0x18000cf94`
- `0x18002e64c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e688`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e688`

## string_xrefs

- `0x18002e69a`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

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
               &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
               0,
               4u,
               &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x18002e64c  mov     rax, rsp
0x18002e64f  mov     [rax+8], rcx
0x18002e653  push    rbx
0x18002e654  sub     rsp, 40h
0x18002e658  mov     rbx, rcx
0x18002e65b  mov     dword ptr [rax-18h], 0
0x18002e662  mov     dword ptr [rax-18h], 1
0x18002e669  mov     qword ptr [rcx], 0
0x18002e670  mov     [rax-28h], rcx
0x18002e674  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18002e67b  xor     edx, edx; pUnkOuter
0x18002e67d  lea     r8d, [rdx+4]; dwClsContext
0x18002e681  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x18002e688  call    cs:__imp_CoCreateInstance
0x18002e68e  test    eax, eax
0x18002e690  jns     short loc_18002E6AC
0x18002e692  mov     rcx, [rsp+48h]; this
0x18002e697  mov     r9d, eax; char *
0x18002e69a  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002e6a1  mov     edx, 1CBEh; void *
0x18002e6a6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002e6ac  mov     rax, rbx
0x18002e6af  add     rsp, 40h
0x18002e6b3  pop     rbx
0x18002e6b4  retn
```
