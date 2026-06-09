# std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>::~pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>(void)

- ea: `0x14000f918`
- end: `0x14000f95c`
- name: `??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(char **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400176e8`

## callees

- `0x1400088f4`
- `0x14000a840`
- `0x14000f918`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f937`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f937`

## pseudocode

```c
void __fastcall std::pair<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>::~pair<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>(
        char **a1)
{
  char *v1; // rbx
  HMODULE v3; // rcx

  v1 = a1[4];
  if ( v1 )
  {
    v3 = (HMODULE)*((_QWORD *)v1 + 2);
    if ( v3 )
      FreeLibrary(v3);
    operator delete(v1, 0x18u);
  }
  std::wstring::~wstring(a1);
}

```

## disassembly

```asm
0x14000f918  mov     [rsp+arg_0], rbx
0x14000f91d  push    rdi
0x14000f91e  sub     rsp, 20h
0x14000f922  mov     rbx, [rcx+20h]
0x14000f926  mov     rdi, rcx
0x14000f929  test    rbx, rbx
0x14000f92c  jz      short loc_14000F94A
0x14000f92e  mov     rcx, [rbx+10h]; hLibModule
0x14000f932  test    rcx, rcx
0x14000f935  jz      short loc_14000F93D
0x14000f937  call    cs:__imp_FreeLibrary
0x14000f93d  mov     edx, 18h; unsigned __int64
0x14000f942  mov     rcx, rbx; void *
0x14000f945  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f94a  mov     rcx, rdi; void *
0x14000f94d  mov     rbx, [rsp+28h+arg_0]
0x14000f952  add     rsp, 20h
0x14000f956  pop     rdi
0x14000f957  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
