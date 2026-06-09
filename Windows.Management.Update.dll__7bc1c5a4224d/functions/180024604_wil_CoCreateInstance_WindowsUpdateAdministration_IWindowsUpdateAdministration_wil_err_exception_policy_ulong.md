# wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)

- ea: `0x180024604`
- end: `0x18002466d`
- name: `??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z`
- size: `105`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012430`
- `0x180014d10`
- `0x180024ca8`
- `0x180024e64`
- `0x1800250cc`
- `0x180025290`

## callees

- `0x18001c7d4`
- `0x180024604`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024640`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024640`

## string_xrefs

- `0x18002465b`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(
        LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_a1365519_3256_41a0_bfd6_9fe9b4b0dc31,
               0,
               4u,
               &GUID_87486abe_0730_4285_abdb_74ba4e8793ed,
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
0x180024604  mov     rax, rsp
0x180024607  mov     [rax+8], rcx
0x18002460b  push    rbx
0x18002460c  sub     rsp, 40h
0x180024610  mov     rbx, rcx
0x180024613  mov     dword ptr [rax-18h], 0
0x18002461a  mov     dword ptr [rax-18h], 2
0x180024621  mov     qword ptr [rcx], 0
0x180024628  mov     [rax-28h], rcx
0x18002462c  lea     r9, _GUID_87486abe_0730_4285_abdb_74ba4e8793ed; riid
0x180024633  xor     edx, edx; pUnkOuter
0x180024635  lea     r8d, [rdx+4]; dwClsContext
0x180024639  lea     rcx, _GUID_a1365519_3256_41a0_bfd6_9fe9b4b0dc31; rclsid
0x180024640  call    cs:__imp_CoCreateInstance
0x180024646  mov     rcx, [rsp+48h]; this
0x18002464b  test    eax, eax
0x18002464d  js      short loc_180024658
0x18002464f  mov     rax, rbx
0x180024652  add     rsp, 40h
0x180024656  pop     rbx
0x180024657  retn
0x180024658  mov     r9d, eax; char *
0x18002465b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024662  mov     edx, 1CBEh; void *
0x180024667  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
