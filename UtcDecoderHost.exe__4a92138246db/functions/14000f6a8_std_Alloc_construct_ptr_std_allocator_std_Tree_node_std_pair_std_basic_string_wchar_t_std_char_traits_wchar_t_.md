# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,void *>>>(void)

- ea: `0x14000f6a8`
- end: `0x14000f6c4`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140017646`

## callees

- `0x1400088f4`
- `0x14000f6a8`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, 0x48u);
}

```

## disassembly

```asm
0x14000f6a8  sub     rsp, 28h
0x14000f6ac  mov     rcx, [rcx+8]; void *
0x14000f6b0  test    rcx, rcx
0x14000f6b3  jz      short loc_14000F6BF
0x14000f6b5  mov     edx, 48h ; 'H'; unsigned __int64
0x14000f6ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f6bf  add     rsp, 28h
0x14000f6c3  retn
```
