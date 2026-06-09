# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,winrt::Microsoft::Windows::Workloads::ApiInfo>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,winrt::Microsoft::Windows::Workloads::ApiInfo>,void *>>>(void)

- ea: `0x1800297d0`
- end: `0x18002981d`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UApiInfo@Workloads@Windows@Microsoft@winrt@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `77`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003f9d8`

## callees

- `0x1800027d0`
- `0x1800040a0`
- `0x1800297d0`
- `0x18003509c`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  void *v3; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    if ( *(_QWORD *)(v1 + 64) )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 64);
    std::wstring::_Tidy_deallocate(v1 + 32);
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    operator delete(v3, 0x48u);
}

```

## disassembly

```asm
0x1800297d0  mov     [rsp+arg_8], rbx
0x1800297d5  push    rdi
0x1800297d6  sub     rsp, 20h
0x1800297da  mov     rbx, [rcx+8]
0x1800297de  mov     rdi, rcx
0x1800297e1  test    rbx, rbx
0x1800297e4  jz      short loc_1800297FF
0x1800297e6  cmp     qword ptr [rbx+40h], 0
0x1800297eb  lea     rcx, [rbx+40h]
0x1800297ef  jz      short loc_1800297F6
0x1800297f1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800297f6  lea     rcx, [rbx+20h]
0x1800297fa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800297ff  mov     rcx, [rdi+8]; void *
0x180029803  test    rcx, rcx
0x180029806  jz      short loc_180029812
0x180029808  mov     edx, 48h ; 'H'; unsigned __int64
0x18002980d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029812  mov     rbx, [rsp+28h+arg_8]
0x180029817  add     rsp, 20h
0x18002981b  pop     rdi
0x18002981c  retn
```
