# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,void *>>>(void)

- ea: `0x14000f758`
- end: `0x14000f7c7`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000f2d4`

## callees

- `0x1400088f4`
- `0x14000a840`
- `0x14000f758`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f789`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f789`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  _QWORD *v4; // rbx
  HMODULE v5; // rcx
  void *v6; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = (void *)(v1 + 32);
    v4 = *(_QWORD **)(v1 + 64);
    if ( v4 )
    {
      v5 = (HMODULE)v4[2];
      if ( v5 )
        FreeLibrary(v5);
      operator delete(v4, 0x18u);
    }
    std::wstring::~wstring(v3);
  }
  v6 = *(void **)(a1 + 8);
  if ( v6 )
    operator delete(v6, 0x48u);
}

```

## disassembly

```asm
0x14000f758  mov     [rsp+arg_0], rbx
0x14000f75d  mov     [rsp+arg_8], rsi
0x14000f762  push    rdi
0x14000f763  sub     rsp, 20h
0x14000f767  mov     rax, [rcx+8]
0x14000f76b  mov     rsi, rcx
0x14000f76e  test    rax, rax
0x14000f771  jz      short loc_14000F7A4
0x14000f773  lea     rdi, [rax+20h]
0x14000f777  mov     rbx, [rdi+20h]
0x14000f77b  test    rbx, rbx
0x14000f77e  jz      short loc_14000F79C
0x14000f780  mov     rcx, [rbx+10h]; hLibModule
0x14000f784  test    rcx, rcx
0x14000f787  jz      short loc_14000F78F
0x14000f789  call    cs:__imp_FreeLibrary
0x14000f78f  mov     edx, 18h; unsigned __int64
0x14000f794  mov     rcx, rbx; void *
0x14000f797  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f79c  mov     rcx, rdi; void *
0x14000f79f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f7a4  mov     rcx, [rsi+8]; void *
0x14000f7a8  test    rcx, rcx
0x14000f7ab  jz      short loc_14000F7B7
0x14000f7ad  mov     edx, 48h ; 'H'; unsigned __int64
0x14000f7b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f7b7  mov     rbx, [rsp+28h+arg_0]
0x14000f7bc  mov     rsi, [rsp+28h+arg_8]
0x14000f7c1  add     rsp, 20h
0x14000f7c5  pop     rdi
0x14000f7c6  retn
```
