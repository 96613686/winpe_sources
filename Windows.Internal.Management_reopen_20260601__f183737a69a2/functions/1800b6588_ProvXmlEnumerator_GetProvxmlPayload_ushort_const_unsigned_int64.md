# ProvXmlEnumerator::GetProvxmlPayload(ushort const *,unsigned __int64)

- ea: `0x1800b6588`
- end: `0x1800b6677`
- name: `?GetProvxmlPayload@ProvXmlEnumerator@@AEAAPEAUIStream@@PEBG_K@Z`
- size: `239`
- prototype: `struct IStream *(ProvXmlEnumerator *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x1800b6218`

## callees

- `0x180004eb0`
- `0x18000dc18`
- `0x180017024`
- `0x18003e5d4`
- `0x1800b4f28`
- `0x1800b6404`
- `0x1800b6588`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b65de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b65de`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800b65be`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800b65be`

## string_xrefs

- `0x1800b65d2`: `.provxml`
- `0x1800b662b`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  FileUtility::GetFullTempFilePath((__int64)v12);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, _QWORD))(v5 + 48))(v6, a2, v4, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      (const char *)(unsigned int)v7,
      v10);
  MemStreamFromTempFile = CreateMemStreamFromTempFile((__int64)v12);
  std::wstring::~wstring(v12);
  return MemStreamFromTempFile;
}

```

## disassembly

```asm
0x1800b6588  mov     [rsp+arg_18], rbx
0x1800b658d  push    rdi
0x1800b658e  sub     rsp, 60h
0x1800b6592  mov     rax, cs:__security_cookie
0x1800b6599  xor     rax, rsp
0x1800b659c  mov     [rsp+68h+var_10], rax
0x1800b65a1  mov     rax, r8
0x1800b65a4  mov     rbx, rdx
0x1800b65a7  mov     rdi, rcx
0x1800b65aa  mov     [rsp+68h+ppszExt], 0
0x1800b65b3  lea     r8, [rsp+68h+ppszExt]; ppszExt
0x1800b65b8  mov     rdx, rax; cchPath
0x1800b65bb  mov     rcx, rbx; pszPath
0x1800b65be  call    cs:__imp_PathCchFindExtension
0x1800b65c5  nop     dword ptr [rax+rax+00h]
0x1800b65ca  test    eax, eax
0x1800b65cc  js      loc_1800B6659
0x1800b65d2  lea     rdx, ?gc_szProvxmlExtension@@3QBGB; ".provxml"
0x1800b65d9  mov     rcx, [rsp+68h+ppszExt]
0x1800b65de  call    cs:__imp__o__wcsicmp
0x1800b65e5  nop     dword ptr [rax+rax+00h]
0x1800b65ea  test    eax, eax
0x1800b65ec  jnz     short loc_1800B6659
0x1800b65ee  lea     rcx, [rsp+68h+var_30]
0x1800b65f3  call    ?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; FileUtility::GetFullTempFilePath(void)
0x1800b65f8  nop
0x1800b65f9  mov     r10, [rdi+10h]
0x1800b65fd  mov     r9, [r10]
0x1800b6600  lea     rcx, [rsp+68h+var_30]
0x1800b6605  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b660a  mov     r8, rax
0x1800b660d  mov     rax, [r9+30h]
0x1800b6611  xor     r9d, r9d
0x1800b6614  mov     rdx, rbx
0x1800b6617  mov     rcx, r10
0x1800b661a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b661f  mov     rcx, [rsp+68h]; this
0x1800b6624  test    eax, eax
0x1800b6626  jns     short loc_1800B663D
0x1800b6628  mov     r9d, eax; char *
0x1800b662b  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b6632  mov     edx, 63h ; 'c'; void *
0x1800b6637  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b663d  lea     rcx, [rsp+68h+var_30]
0x1800b6642  call    CreateMemStreamFromTempFile
0x1800b6647  mov     rbx, rax
0x1800b664a  lea     rcx, [rsp+68h+var_30]
0x1800b664f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b6654  mov     rax, rbx
0x1800b6657  jmp     short loc_1800B665B
0x1800b6659  xor     eax, eax
0x1800b665b  mov     rcx, [rsp+68h+var_10]
0x1800b6660  xor     rcx, rsp; StackCookie
0x1800b6663  call    __security_check_cookie
0x1800b6668  mov     rbx, [rsp+68h+arg_18]
0x1800b6670  add     rsp, 60h
0x1800b6674  pop     rdi
0x1800b6675  retn
```
