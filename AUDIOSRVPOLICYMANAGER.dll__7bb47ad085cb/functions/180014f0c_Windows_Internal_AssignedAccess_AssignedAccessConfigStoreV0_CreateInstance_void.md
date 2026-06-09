# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::CreateInstance(void)

- ea: `0x180014f0c`
- end: `0x180015031`
- name: `?CreateInstance@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@SA?AV?$unique_ptr@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreBase@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@XZ`
- size: `293`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014888`
- `0x180014a80`
- `0x180014ca8`

## callees

- `0x180014f0c`
- `0x180015038`
- `0x180015064`
- `0x1800150c0`
- `0x18001528c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014f30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014f30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014f21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014f21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001500b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001500b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015029`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::CreateInstance(__int64 a1)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v3; // rbx
  char v4; // si
  __int64 v5; // rdi
  void *v6; // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v10[5]; // [rsp+30h] [rbp-28h] BYREF

  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 0, 0x20u);
  if ( !v3 )
  {
    v8 = 0;
LABEL_13:
    wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0>>::reset(&v8);
    goto LABEL_9;
  }
  *v3 = &Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::`vftable';
  v3[1] = 0;
  v3[2] = 0;
  v3[3] = 0;
  v8 = (void (__fastcall ***)(_QWORD, __int64))v3;
  v4 = 0;
  v10[0] = 0;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pv,
    L"SOFTWARE\\Microsoft\\Windows Embedded\\Lockdown",
    -1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    v10,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  v5 = v10[0];
  if ( v10[0] )
  {
    v6 = (void *)v3[1];
    if ( v6 )
      CoTaskMemFree(v6);
    v3[1] = v5;
    v3[3] = -1;
    v3[2] = -1;
    v4 = 1;
  }
  if ( !v4 )
    goto LABEL_13;
LABEL_9:
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(a1, &v8);
  if ( v8 )
    (**v8)(v8, 1);
  return a1;
}

```

## disassembly

```asm
0x180014f0c  mov     [rsp+arg_8], rbx
0x180014f11  mov     [rsp+arg_10], rbp
0x180014f16  push    rsi
0x180014f17  push    rdi
0x180014f18  push    r15
0x180014f1a  sub     rsp, 40h
0x180014f1e  mov     rbp, rcx
0x180014f21  call    cs:__imp_GetProcessHeap
0x180014f27  mov     rcx, rax; hHeap
0x180014f2a  xor     edx, edx; dwFlags
0x180014f2c  lea     r8d, [rdx+20h]; dwBytes
0x180014f30  call    cs:__imp_HeapAlloc
0x180014f36  mov     rbx, rax
0x180014f39  test    rax, rax
0x180014f3c  jz      loc_180015014
0x180014f42  lea     rax, ??_7AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@6B@; const Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::`vftable'
0x180014f49  mov     [rbx], rax
0x180014f4c  mov     qword ptr [rbx+8], 0
0x180014f54  mov     qword ptr [rbx+10h], 0
0x180014f5c  mov     qword ptr [rbx+18h], 0
0x180014f64  mov     [rsp+58h+var_38], rbx
0x180014f69  xor     sil, sil
0x180014f6c  mov     [rsp+58h+var_28], 0
0x180014f75  or      r15, 0FFFFFFFFFFFFFFFFh
0x180014f79  mov     r8, r15
0x180014f7c  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Embedded\\"...
0x180014f83  lea     rcx, [rsp+58h+pv]
0x180014f88  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180014f8d  lea     rdx, [rsp+58h+pv]
0x180014f92  lea     rcx, [rsp+58h+var_28]
0x180014f97  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180014f9c  nop
0x180014f9d  mov     rcx, [rsp+58h+pv]; pv
0x180014fa2  test    rcx, rcx
0x180014fa5  jnz     short loc_18001500B
0x180014fa7  mov     rdi, [rsp+58h+var_28]
0x180014fac  test    rdi, rdi
0x180014faf  jz      short loc_180014FC9
0x180014fb1  mov     rcx, [rbx+8]; pv
0x180014fb5  test    rcx, rcx
0x180014fb8  jnz     short loc_180015029
0x180014fba  mov     [rbx+8], rdi
0x180014fbe  mov     [rbx+18h], r15
0x180014fc2  mov     [rbx+10h], r15
0x180014fc6  mov     sil, 1
0x180014fc9  test    sil, sil
0x180014fcc  jz      short loc_18001501D
0x180014fce  lea     rdx, [rsp+58h+var_38]
0x180014fd3  mov     rcx, rbp
0x180014fd6  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180014fdb  mov     rcx, [rsp+58h+var_38]
0x180014fe0  test    rcx, rcx
0x180014fe3  jz      short loc_180014FF5
0x180014fe5  mov     r8, [rcx]
0x180014fe8  mov     edx, 1
0x180014fed  mov     rax, [r8]
0x180014ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ff5  mov     rax, rbp
0x180014ff8  mov     rbx, [rsp+58h+arg_8]
0x180014ffd  mov     rbp, [rsp+58h+arg_10]
0x180015002  add     rsp, 40h
0x180015006  pop     r15
0x180015008  pop     rdi
0x180015009  pop     rsi
0x18001500a  retn
0x18001500b  call    cs:__imp_CoTaskMemFree
0x180015011  nop
0x180015012  jmp     short loc_180014FA7
0x180015014  mov     [rsp+58h+var_38], 0
0x18001501d  lea     rcx, [rsp+58h+var_38]
0x180015022  call    ?reset@?$unique_ptr@VAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@U?$default_delete@VAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVAssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0>>::reset(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *)
0x180015027  jmp     short loc_180014FCE
0x180015029  call    cs:__imp_CoTaskMemFree
0x18001502f  jmp     short loc_180014FBA
```
