# Windows::DockedHelpers::GetDockedSystem(void)

- ea: `0x18003a614`
- end: `0x18003a743`
- name: `?GetDockedSystem@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedSystem@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c020`
- `0x18003ef00`

## callees

- `0x180034a30`
- `0x18003a568`
- `0x18003a614`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003a6b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003a6b2`

## string_xrefs

- `0x18003a717`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x18003a731`: `C:\__w\1\s\src\orchestrator\system\windows\common\DockedHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall Windows::DockedHelpers::GetDockedSystem(__int64 *a1)
{
  __int64 (__fastcall *DockedComponentFunc)(GUID *, __int64 *); // rdi
  __int64 v3; // rcx
  int v4; // eax
  HRESULT Instance; // eax
  LPVOID v6; // rax
  LPVOID v7; // rcx
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  LPVOID v12[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v12[1] = a1;
  *a1 = 0;
  DockedComponentFunc = (__int64 (__fastcall *)(GUID *, __int64 *))Windows::DockedHelpers::_anonymous_namespace_::GetDockedComponentFunc();
  if ( DockedComponentFunc )
  {
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    v4 = DockedComponentFunc(&GUID_c663ec6b_2b42_473e_b51d_17a70ce94c50, a1);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\DockedHelpers.cpp",
        (const char *)(unsigned int)v4,
        ppv);
  }
  else
  {
    v12[0] = 0;
    Instance = CoCreateInstance(&CLSID_DockedSystem, 0, 1u, &GUID_c663ec6b_2b42_473e_b51d_17a70ce94c50, v12);
    if ( Instance < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1C96,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)Instance,
        ppva);
    v6 = v12[0];
    v7 = 0;
    v12[0] = 0;
    v8 = *a1;
    *a1 = (__int64)v6;
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v7 = v12[0];
    }
    if ( v7 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18003a614  mov     [rsp+arg_8], rbx
0x18003a619  push    rdi
0x18003a61a  sub     rsp, 50h
0x18003a61e  mov     rbx, rcx
0x18003a621  mov     [rsp+58h+var_18], rcx
0x18003a626  mov     [rsp+58h+var_28], 0
0x18003a62e  xor     eax, eax
0x18003a630  mov     [rcx], rax
0x18003a633  mov     [rsp+58h+var_28], 1
0x18003a63b  call    Windows__DockedHelpers___anonymous_namespace___GetDockedComponentFunc
0x18003a640  mov     rdi, rax
0x18003a643  test    rax, rax
0x18003a646  jz      short loc_18003A683
0x18003a648  mov     rcx, [rbx]
0x18003a64b  mov     qword ptr [rbx], 0
0x18003a652  test    rcx, rcx
0x18003a655  jz      short loc_18003A664
0x18003a657  mov     rax, [rcx]
0x18003a65a  mov     rax, [rax+10h]
0x18003a65e  call    _guard_dispatch_icall
0x18003a663  nop
0x18003a664  mov     rdx, rbx
0x18003a667  lea     rcx, _GUID_c663ec6b_2b42_473e_b51d_17a70ce94c50
0x18003a66e  mov     rax, rdi
0x18003a671  call    _guard_dispatch_icall
0x18003a676  test    eax, eax
0x18003a678  js      loc_18003A729
0x18003a67e  jmp     loc_18003A706
0x18003a683  mov     [rsp+58h+var_28], 3
0x18003a68b  mov     [rsp+58h+var_20], 0
0x18003a694  lea     rax, [rsp+58h+var_20]
0x18003a699  mov     qword ptr [rsp+58h+ppv], rax; int
0x18003a69e  lea     r9, _GUID_c663ec6b_2b42_473e_b51d_17a70ce94c50; riid
0x18003a6a5  xor     edx, edx; pUnkOuter
0x18003a6a7  lea     r8d, [rdx+1]; dwClsContext
0x18003a6ab  lea     rcx, CLSID_DockedSystem; rclsid
0x18003a6b2  call    cs:__imp_CoCreateInstance
0x18003a6b8  mov     rcx, [rsp+58h]; this
0x18003a6bd  test    eax, eax
0x18003a6bf  js      short loc_18003A714
0x18003a6c1  mov     rax, [rsp+58h+var_20]
0x18003a6c6  xor     ecx, ecx
0x18003a6c8  mov     [rsp+58h+var_20], rcx
0x18003a6cd  mov     rdx, [rbx]
0x18003a6d0  mov     [rbx], rax
0x18003a6d3  test    rdx, rdx
0x18003a6d6  jz      short loc_18003A6EC
0x18003a6d8  mov     rax, [rdx]
0x18003a6db  mov     rcx, rdx
0x18003a6de  mov     rax, [rax+10h]
0x18003a6e2  call    _guard_dispatch_icall
0x18003a6e7  mov     rcx, [rsp+58h+var_20]
0x18003a6ec  mov     [rsp+58h+var_28], 1
0x18003a6f4  test    rcx, rcx
0x18003a6f7  jz      short loc_18003A706
0x18003a6f9  mov     rdx, [rcx]
0x18003a6fc  mov     rax, [rdx+10h]
0x18003a700  call    _guard_dispatch_icall
0x18003a705  nop
0x18003a706  mov     rax, rbx
0x18003a709  mov     rbx, [rsp+58h+arg_8]
0x18003a70e  add     rsp, 50h
0x18003a712  pop     rdi
0x18003a713  retn
0x18003a714  mov     r9d, eax; char *
0x18003a717  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18003a71e  mov     edx, 1C96h; void *
0x18003a723  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a729  mov     rcx, [rsp+58h]; this
0x18003a72e  mov     r9d, eax; char *
0x18003a731  lea     r8, aCW1SSrcOrchest_1; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003a738  mov     edx, 38h ; '8'; void *
0x18003a73d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
