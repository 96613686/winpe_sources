# win_dox::OpcSignatureCustomObjectImpl::GetXml(void)

- ea: `0x180106a4c`
- end: `0x180106b05`
- name: `?GetXml@OpcSignatureCustomObjectImpl@win_dox@@QEAA?AU?$SMART_VECTOR@V?$scope@PEAEU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@2@XZ`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801043f0`

## callees

- `0x1800cd35a`
- `0x1800cd38c`
- `0x1800d5fd8`
- `0x180106a4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180106a8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180106a8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106aa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106aa0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall win_dox::OpcSignatureCustomObjectImpl::GetXml(__int64 a1, __int64 a2)
{
  SIZE_T v4; // rdi
  LPVOID v5; // rax
  void *v6; // rcx
  _QWORD pExceptionObject[5]; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = 0;
  v4 = *(unsigned int *)(a1 + 16);
  v5 = CoTaskMemAlloc(v4);
  v6 = *(void **)a2;
  *(_QWORD *)a2 = v5;
  if ( v6 )
    CoTaskMemFree(v6);
  if ( !*(_QWORD *)a2 )
  {
    exception::exception((exception *)pExceptionObject, (const char *const *)&std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  memcpy_0(*(void **)a2, *(const void **)(a1 + 8), v4);
  *(_DWORD *)(a2 + 8) = v4;
  return a2;
}

```

## disassembly

```asm
0x180106a4c  mov     rax, rsp
0x180106a4f  mov     [rax+10h], rdx
0x180106a53  push    rdi
0x180106a54  sub     rsp, 50h
0x180106a58  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x180106a60  mov     [rax+8], rbx
0x180106a64  mov     [rax+18h], rsi
0x180106a68  mov     rbx, rdx
0x180106a6b  mov     rsi, rcx
0x180106a6e  mov     dword ptr [rax-38h], 0
0x180106a75  mov     qword ptr [rdx], 0
0x180106a7c  mov     dword ptr [rdx+8], 0
0x180106a83  mov     dword ptr [rax-38h], 1
0x180106a8a  mov     edi, [rcx+10h]
0x180106a8d  mov     ecx, edi; cb
0x180106a8f  call    cs:__imp_CoTaskMemAlloc
0x180106a95  mov     rcx, [rbx]; pv
0x180106a98  mov     [rbx], rax
0x180106a9b  test    rcx, rcx
0x180106a9e  jz      short loc_180106AA6
0x180106aa0  call    cs:__imp_CoTaskMemFree
0x180106aa6  mov     rcx, [rbx]; void *
0x180106aa9  test    rcx, rcx
0x180106aac  jz      short loc_180106AD0
0x180106aae  mov     r8, rdi; Size
0x180106ab1  mov     rdx, [rsi+8]; Src
0x180106ab5  call    memcpy_0
0x180106aba  mov     [rbx+8], edi
0x180106abd  mov     rax, rbx
0x180106ac0  mov     rbx, [rsp+58h+arg_0]
0x180106ac5  mov     rsi, [rsp+58h+arg_10]
0x180106aca  add     rsp, 50h
0x180106ace  pop     rdi
0x180106acf  retn
0x180106ad0  mov     r8d, 1; int
0x180106ad6  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char **
0x180106add  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180106ae2  call    ??0exception@@QEAA@AEBQEBDH@Z_0; exception::exception(char const * const &,int)
0x180106ae7  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180106aee  mov     [rsp+58h+pExceptionObject], rax
0x180106af3  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180106afa  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180106aff  call    _CxxThrowException_0
```
