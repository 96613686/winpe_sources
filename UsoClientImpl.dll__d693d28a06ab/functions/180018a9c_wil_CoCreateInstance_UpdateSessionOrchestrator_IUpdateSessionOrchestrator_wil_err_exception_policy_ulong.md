# wil::CoCreateInstance<UpdateSessionOrchestrator,IUpdateSessionOrchestrator,wil::err_exception_policy>(ulong)

- ea: `0x180018a9c`
- end: `0x180018b05`
- name: `??$CoCreateInstance@VUpdateSessionOrchestrator@@UIUpdateSessionOrchestrator@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_exception_policy@wil@@@0@K@Z`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180018a9c`
- `0x180034a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018ad8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018ad8`

## string_xrefs

- `0x180018af3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<UpdateSessionOrchestrator,IUpdateSessionOrchestrator,wil::err_exception_policy>(
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
               &GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0,
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
0x180018a9c  mov     rax, rsp
0x180018a9f  push    rbx
0x180018aa0  sub     rsp, 40h
0x180018aa4  mov     rbx, rcx
0x180018aa7  mov     [rax-10h], rcx
0x180018aab  mov     dword ptr [rax-18h], 0
0x180018ab2  mov     dword ptr [rax-18h], 2
0x180018ab9  mov     qword ptr [rcx], 0
0x180018ac0  mov     [rax-28h], rcx
0x180018ac4  lea     r9, _GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0; riid
0x180018acb  xor     edx, edx; pUnkOuter
0x180018acd  lea     r8d, [rdx+4]; dwClsContext
0x180018ad1  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x180018ad8  call    cs:__imp_CoCreateInstance
0x180018ade  mov     rcx, [rsp+48h]; this
0x180018ae3  test    eax, eax
0x180018ae5  js      short loc_180018AF0
0x180018ae7  mov     rax, rbx
0x180018aea  add     rsp, 40h
0x180018aee  pop     rbx
0x180018aef  retn
0x180018af0  mov     r9d, eax; char *
0x180018af3  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180018afa  mov     edx, 1C96h; void *
0x180018aff  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
