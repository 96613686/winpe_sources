# ProvXmlEnumerator::GetProvxmlPayload(ushort const *,unsigned __int64)

- ea: `0x1800b3120`
- end: `0x1800b3202`
- name: `?GetProvxmlPayload@ProvXmlEnumerator@@AEAAPEAUIStream@@PEBG_K@Z`
- size: `226`
- prototype: `struct IStream *__fastcall(ProvXmlEnumerator *this, const unsigned __int16 *, size_t)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x1800b2dc8`

## callees

- `0x180004d50`
- `0x18000d724`
- `0x1800168d0`
- `0x18003ec00`
- `0x1800b1b28`
- `0x1800b2fb4`
- `0x1800b3120`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b3170`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b3170`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800b3156`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800b3156`

## string_xrefs

- `0x1800b3164`: `.provxml`
- `0x1800b31b7`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`

## pseudocode

```c
struct IStream *__fastcall ProvXmlEnumerator::GetProvxmlPayload(
        ProvXmlEnumerator *this,
        const unsigned __int16 *a2,
        size_t a3)
{
  __int64 v4; // rax
  __int64 v5; // r9
  __int64 v6; // r10
  int v7; // eax
  IStream *MemStreamFromTempFile; // rbx
  int v10; // [rsp+20h] [rbp-48h]
  PCWSTR ppszExt; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v12[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  ppszExt = 0;
  if ( PathCchFindExtension(a2, a3, &ppszExt) < 0 || (unsigned int)_o__wcsicmp(ppszExt, L".provxml") )
    return 0;
  FileUtility::GetFullTempFilePath(v12);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, _QWORD))(v5 + 48))(v6, a2, v4, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      (const char *)(unsigned int)v7,
      v10);
  MemStreamFromTempFile = CreateMemStreamFromTempFile();
  std::wstring::~wstring(v12);
  return MemStreamFromTempFile;
}

```

## disassembly

```asm
0x1800b3120  mov     [rsp+arg_18], rbx
0x1800b3125  push    rdi
0x1800b3126  sub     rsp, 60h
0x1800b312a  mov     rax, cs:__security_cookie
0x1800b3131  xor     rax, rsp
0x1800b3134  mov     [rsp+68h+var_10], rax
0x1800b3139  mov     rax, r8
0x1800b313c  mov     rbx, rdx
0x1800b313f  mov     rdi, rcx
0x1800b3142  mov     [rsp+68h+ppszExt], 0
0x1800b314b  lea     r8, [rsp+68h+ppszExt]; ppszExt
0x1800b3150  mov     rdx, rax; cchPath
0x1800b3153  mov     rcx, rbx; pszPath
0x1800b3156  call    cs:__imp_PathCchFindExtension
0x1800b315c  test    eax, eax
0x1800b315e  js      loc_1800B31E5
0x1800b3164  lea     rdx, ?gc_szProvxmlExtension@@3QBGB; ".provxml"
0x1800b316b  mov     rcx, [rsp+68h+ppszExt]
0x1800b3170  call    cs:__imp__o__wcsicmp
0x1800b3176  test    eax, eax
0x1800b3178  jnz     short loc_1800B31E5
0x1800b317a  lea     rcx, [rsp+68h+var_30]
0x1800b317f  call    ?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; FileUtility::GetFullTempFilePath(void)
0x1800b3184  nop
0x1800b3185  mov     r10, [rdi+10h]
0x1800b3189  mov     r9, [r10]
0x1800b318c  lea     rcx, [rsp+68h+var_30]
0x1800b3191  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b3196  mov     r8, rax
0x1800b3199  mov     rax, [r9+30h]
0x1800b319d  xor     r9d, r9d
0x1800b31a0  mov     rdx, rbx
0x1800b31a3  mov     rcx, r10
0x1800b31a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b31ab  mov     rcx, [rsp+68h]; this
0x1800b31b0  test    eax, eax
0x1800b31b2  jns     short loc_1800B31C9
0x1800b31b4  mov     r9d, eax; char *
0x1800b31b7  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b31be  mov     edx, 63h ; 'c'; void *
0x1800b31c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b31c9  lea     rcx, [rsp+68h+var_30]
0x1800b31ce  call    CreateMemStreamFromTempFile
0x1800b31d3  mov     rbx, rax
0x1800b31d6  lea     rcx, [rsp+68h+var_30]
0x1800b31db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b31e0  mov     rax, rbx
0x1800b31e3  jmp     short loc_1800B31E7
0x1800b31e5  xor     eax, eax
0x1800b31e7  mov     rcx, [rsp+68h+var_10]
0x1800b31ec  xor     rcx, rsp; StackCookie
0x1800b31ef  call    __security_check_cookie
0x1800b31f4  mov     rbx, [rsp+68h+arg_18]
0x1800b31fc  add     rsp, 60h
0x1800b3200  pop     rdi
0x1800b3201  retn
```
