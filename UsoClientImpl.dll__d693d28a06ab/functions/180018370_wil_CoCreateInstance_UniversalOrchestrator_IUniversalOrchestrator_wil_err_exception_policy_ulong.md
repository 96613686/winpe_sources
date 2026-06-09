# wil::CoCreateInstance<UniversalOrchestrator,IUniversalOrchestrator,wil::err_exception_policy>(ulong)

- ea: `0x180018370`
- end: `0x1800183d9`
- name: `??$CoCreateInstance@VUniversalOrchestrator@@UIUniversalOrchestrator@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUniversalOrchestrator@@Uerr_exception_policy@wil@@@0@K@Z`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f104`
- `0x1800150a0`

## callees

- `0x180018370`
- `0x180034a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800183ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800183ac`

## string_xrefs

- `0x1800183c7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall wil::CoCreateInstance<UniversalOrchestrator,IUniversalOrchestrator,wil::err_exception_policy>(
        LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_9c695035_48d2_4229_8b73_4c70e756e519,
               0,
               4u,
               &GUID_c53f3549_0dbf_429a_8297_c812ba00742d,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x180018370  mov     rax, rsp
0x180018373  push    rbx
0x180018374  sub     rsp, 40h
0x180018378  mov     rbx, rcx
0x18001837b  mov     [rax-10h], rcx
0x18001837f  mov     dword ptr [rax-18h], 0
0x180018386  mov     dword ptr [rax-18h], 2
0x18001838d  mov     qword ptr [rcx], 0
0x180018394  mov     [rax-28h], rcx
0x180018398  lea     r9, _GUID_c53f3549_0dbf_429a_8297_c812ba00742d; riid
0x18001839f  xor     edx, edx; pUnkOuter
0x1800183a1  lea     r8d, [rdx+4]; dwClsContext
0x1800183a5  lea     rcx, _GUID_9c695035_48d2_4229_8b73_4c70e756e519; rclsid
0x1800183ac  call    cs:__imp_CoCreateInstance
0x1800183b2  mov     rcx, [rsp+48h]; this
0x1800183b7  test    eax, eax
0x1800183b9  js      short loc_1800183C4
0x1800183bb  mov     rax, rbx
0x1800183be  add     rsp, 40h
0x1800183c2  pop     rbx
0x1800183c3  retn
0x1800183c4  mov     r9d, eax; char *
0x1800183c7  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800183ce  mov     edx, 1C96h; void *
0x1800183d3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
