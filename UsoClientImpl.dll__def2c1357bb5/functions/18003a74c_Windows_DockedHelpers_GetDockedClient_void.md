# Windows::DockedHelpers::GetDockedClient(void)

- ea: `0x18003a74c`
- end: `0x18003a7d5`
- name: `?GetDockedClient@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedClient2@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `137`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f370`
- `0x18000f580`
- `0x1800137bc`
- `0x1800138b4`
- `0x180013a54`
- `0x180013bf4`
- `0x180013d94`
- `0x180013f34`
- `0x1800150a0`

## callees

- `0x180034a30`
- `0x18003a568`
- `0x18003a74c`
- `0x18005c5e0`

## string_xrefs

- `0x18003a7c3`: `C:\__w\1\s\src\orchestrator\system\windows\common\DockedHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall Windows::DockedHelpers::GetDockedClient(__int64 *a1)
{
  __int64 (__fastcall *DockedComponentFunc)(GUID *, __int64 *); // rdi
  __int64 v3; // rcx
  int v4; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  DockedComponentFunc = (__int64 (__fastcall *)(GUID *, __int64 *))Windows::DockedHelpers::_anonymous_namespace_::GetDockedComponentFunc();
  v3 = *a1;
  *a1 = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = DockedComponentFunc(&GUID_05fe7a70_0229_483d_8bd9_01b03c5743e6, a1);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\DockedHelpers.cpp",
      (const char *)(unsigned int)v4,
      1);
  return a1;
}

```

## disassembly

```asm
0x18003a74c  mov     [rsp+arg_8], rbx
0x18003a751  mov     [rsp+arg_0], rcx
0x18003a756  push    rdi
0x18003a757  sub     rsp, 30h
0x18003a75b  mov     rbx, rcx
0x18003a75e  mov     [rsp+38h+var_18], 0
0x18003a766  xor     eax, eax
0x18003a768  mov     [rcx], rax
0x18003a76b  mov     [rsp+38h+var_18], 1; int
0x18003a773  call    Windows__DockedHelpers___anonymous_namespace___GetDockedComponentFunc
0x18003a778  mov     rdi, rax
0x18003a77b  mov     rcx, [rbx]
0x18003a77e  mov     qword ptr [rbx], 0
0x18003a785  test    rcx, rcx
0x18003a788  jz      short loc_18003A797
0x18003a78a  mov     rax, [rcx]
0x18003a78d  mov     rax, [rax+10h]
0x18003a791  call    _guard_dispatch_icall
0x18003a796  nop
0x18003a797  mov     rdx, rbx
0x18003a79a  lea     rcx, _GUID_05fe7a70_0229_483d_8bd9_01b03c5743e6
0x18003a7a1  mov     rax, rdi
0x18003a7a4  call    _guard_dispatch_icall
0x18003a7a9  test    eax, eax
0x18003a7ab  js      short loc_18003A7BB
0x18003a7ad  mov     rax, rbx
0x18003a7b0  mov     rbx, [rsp+38h+arg_8]
0x18003a7b5  add     rsp, 30h
0x18003a7b9  pop     rdi
0x18003a7ba  retn
0x18003a7bb  mov     rcx, [rsp+38h]; this
0x18003a7c0  mov     r9d, eax; char *
0x18003a7c3  lea     r8, aCW1SSrcOrchest_1; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003a7ca  mov     edx, 63h ; 'c'; void *
0x18003a7cf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
