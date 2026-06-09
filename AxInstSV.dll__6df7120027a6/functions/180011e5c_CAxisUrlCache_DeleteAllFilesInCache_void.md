# CAxisUrlCache::DeleteAllFilesInCache(void)

- ea: `0x180011e5c`
- end: `0x180011ed9`
- name: `?DeleteAllFilesInCache@CAxisUrlCache@@QEAAJXZ`
- size: `125`
- prototype: `__int64 __fastcall(CAxisUrlCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180006370`

## callees

- `0x180002c5c`
- `0x180011e5c`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180011e99`
- `OLEAUT32!__imp_SysStringLen` at `0x180011e99`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180011ea6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180011ea6`
- `ntdll!RtlReleaseResource` at `0x180011ec1`
- `ntdll!RtlReleaseResource` at `0x180011ec1`
- `ntdll!RtlAcquireResourceShared` at `0x180011e7a`
- `ntdll!RtlAcquireResourceShared` at `0x180011e7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAxisUrlCache::DeleteAllFilesInCache(CAxisUrlCache *this)
{
  __int64 v2; // rax
  LPCWSTR *v3; // rsi
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 32), 1u);
    v2 = **((_QWORD **)this + 1);
    v5 = v2;
    while ( v2 != *((_QWORD *)this + 1) )
    {
      v3 = *(LPCWSTR **)(v2 + 40);
      if ( SysStringLen((BSTR)*v3) )
        DeleteFileW(*v3);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(&v5);
      v2 = v5;
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 32));
  }
  return 0;
}

```

## disassembly

```asm
0x180011e5c  mov     [rsp+arg_8], rbx
0x180011e61  mov     [rsp+arg_10], rsi
0x180011e66  push    rdi
0x180011e67  sub     rsp, 20h
0x180011e6b  cmp     dword ptr [rcx+18h], 0
0x180011e6f  mov     rdi, rcx
0x180011e72  jz      short loc_180011EC7
0x180011e74  mov     dl, 1; Wait
0x180011e76  add     rcx, 20h ; ' '; Resource
0x180011e7a  call    cs:__imp_RtlAcquireResourceShared
0x180011e80  mov     rax, [rdi+8]
0x180011e84  mov     rax, [rax]
0x180011e87  mov     [rsp+28h+arg_0], rax
0x180011e8c  cmp     rax, [rdi+8]
0x180011e90  jz      short loc_180011EBD
0x180011e92  mov     rsi, [rax+28h]
0x180011e96  mov     rcx, [rsi]; pbstr
0x180011e99  call    cs:__imp_SysStringLen
0x180011e9f  test    eax, eax
0x180011ea1  jz      short loc_180011EAC
0x180011ea3  mov     rcx, [rsi]; lpFileName
0x180011ea6  call    cs:__imp_DeleteFileW
0x180011eac  lea     rcx, [rsp+28h+arg_0]
0x180011eb1  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(void)
0x180011eb6  mov     rax, [rsp+28h+arg_0]
0x180011ebb  jmp     short loc_180011E8C
0x180011ebd  lea     rcx, [rdi+20h]; Resource
0x180011ec1  call    cs:__imp_RtlReleaseResource
0x180011ec7  mov     rbx, [rsp+28h+arg_8]
0x180011ecc  xor     eax, eax
0x180011ece  mov     rsi, [rsp+28h+arg_10]
0x180011ed3  add     rsp, 20h
0x180011ed7  pop     rdi
0x180011ed8  retn
```
