# wil::CoCreateInstance<UniversalOrchestrator,IUniversalOrchestratorInternal,wil::err_exception_policy>(ulong)

- ea: `0x180018a2c`
- end: `0x180018a95`
- name: `??$CoCreateInstance@VUniversalOrchestrator@@UIUniversalOrchestratorInternal@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUniversalOrchestratorInternal@@Uerr_exception_policy@wil@@@0@K@Z`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180018a2c`
- `0x180034a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018a68`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018a68`

## string_xrefs

- `0x180018a83`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<UniversalOrchestrator,IUniversalOrchestratorInternal,wil::err_exception_policy>(
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
               &GUID_6d207080_eb90_4e16_b5df_780d921023fd,
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
0x180018a2c  mov     rax, rsp
0x180018a2f  push    rbx
0x180018a30  sub     rsp, 40h
0x180018a34  mov     rbx, rcx
0x180018a37  mov     [rax-10h], rcx
0x180018a3b  mov     dword ptr [rax-18h], 0
0x180018a42  mov     dword ptr [rax-18h], 2
0x180018a49  mov     qword ptr [rcx], 0
0x180018a50  mov     [rax-28h], rcx
0x180018a54  lea     r9, _GUID_6d207080_eb90_4e16_b5df_780d921023fd; riid
0x180018a5b  xor     edx, edx; pUnkOuter
0x180018a5d  lea     r8d, [rdx+4]; dwClsContext
0x180018a61  lea     rcx, _GUID_9c695035_48d2_4229_8b73_4c70e756e519; rclsid
0x180018a68  call    cs:__imp_CoCreateInstance
0x180018a6e  mov     rcx, [rsp+48h]; this
0x180018a73  test    eax, eax
0x180018a75  js      short loc_180018A80
0x180018a77  mov     rax, rbx
0x180018a7a  add     rsp, 40h
0x180018a7e  pop     rbx
0x180018a7f  retn
0x180018a80  mov     r9d, eax; char *
0x180018a83  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180018a8a  mov     edx, 1C96h; void *
0x180018a8f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
