# ProvisioningFileManager::RetrieveFile(ushort const *)

- ea: `0x180010750`
- end: `0x180010901`
- name: `?RetrieveFile@ProvisioningFileManager@@UEBA?AV?$ComPtr@UIStream@@@WRL@Microsoft@@PEBG@Z`
- size: `433`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e08`
- `0x18000a2e4`
- `0x18000a540`
- `0x180010750`
- `0x180010ae4`
- `0x180010f80`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800108a0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800108b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800108a0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800108b4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180010888`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180010888`

## pseudocode

```c
_QWORD *__fastcall ProvisioningFileManager::RetrieveFile(__int64 a1, _QWORD *a2, __int64 a3)
{
  LPCWSTR *v6; // r8
  int v7; // eax
  LPCWSTR *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  void *v11; // rcx
  _QWORD *v12; // rsi
  HRESULT v13; // eax
  int pstmTemplate; // [rsp+20h] [rbp-60h]
  int pstmTemplatea; // [rsp+20h] [rbp-60h]
  LPCWSTR pszFile[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v18; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  FileUtility::GetFullTempFilePath(pszFile);
  v6 = pszFile;
  if ( v18 >= 8 )
    v6 = (LPCWSTR *)pszFile[0];
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPCWSTR *, __int64))(**(_QWORD **)(a1 + 16) + 48LL))(
         *(_QWORD *)(a1 + 16),
         a3,
         v6,
         1);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provisioningfilemanager.cpp",
      (const char *)(unsigned int)v7,
      pstmTemplate);
  v8 = pszFile;
  if ( v18 >= 8 )
    v8 = (LPCWSTR *)pszFile[0];
  v9 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  v11 = v9;
  v12 = 0;
  if ( v9 )
  {
    *((_DWORD *)v9 + 3) = 1;
    *v9 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v10 = &AutoDeleteFileStream::`vftable';
    v10[5] = 7;
    v10[4] = 0;
    *((_WORD *)v10 + 8) = 0;
    std::wstring::assign(v10 + 2, v8);
    v10[6] = 0;
    v13 = SHCreateStreamOnFileEx((LPCWSTR)v8, 0, 0x80u, 0, 0, (IStream **)v10 + 6);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provisioningfilemanager.cpp",
        (const char *)(unsigned int)v13,
        pstmTemplatea);
    v11 = 0;
    v12 = v10;
  }
  if ( v11 )
    operator delete(v11);
  *a2 = v12;
  if ( v18 >= 8 )
    operator delete((void *)pszFile[0]);
  return a2;
}

```

## disassembly

```asm
0x180010750  push    rbp
0x180010752  push    rbx
0x180010753  push    rsi
0x180010754  push    rdi
0x180010755  push    r14
0x180010757  mov     rbp, rsp
0x18001075a  sub     rsp, 80h
0x180010761  mov     rax, cs:__security_cookie
0x180010768  xor     rax, rsp
0x18001076b  mov     [rbp+var_8], rax
0x18001076f  mov     rdi, r8
0x180010772  mov     r14, rdx
0x180010775  mov     rbx, rcx
0x180010778  mov     [rbp+var_48], rdx
0x18001077c  mov     [rbp+var_50], 0
0x180010783  lea     rcx, [rbp+pszFile]; void *
0x180010787  call    ?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; FileUtility::GetFullTempFilePath(void)
0x18001078c  nop
0x18001078d  mov     rcx, [rbx+10h]
0x180010791  mov     rax, [rcx]
0x180010794  lea     r8, [rbp+pszFile]
0x180010798  cmp     [rbp+var_10], 8
0x18001079d  cmovnb  r8, [rbp+pszFile]
0x1800107a2  mov     r9d, 1
0x1800107a8  mov     rdx, rdi
0x1800107ab  mov     rax, [rax+30h]
0x1800107af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107b4  mov     rcx, [rbp+28h]; this
0x1800107b8  test    eax, eax
0x1800107ba  js      loc_1800108EC
0x1800107c0  lea     rdi, [rbp+pszFile]
0x1800107c4  cmp     [rbp+var_10], 8
0x1800107c9  cmovnb  rdi, [rbp+pszFile]
0x1800107ce  mov     [rbp+var_48], 0
0x1800107d6  mov     [rbp+var_50], 2
0x1800107dd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800107e4  mov     ecx, 38h ; '8'; unsigned __int64
0x1800107e9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800107ee  mov     rbx, rax
0x1800107f1  mov     rcx, rax
0x1800107f4  mov     [rbp+var_40], rax
0x1800107f8  mov     [rbp+var_38], rax
0x1800107fc  xor     esi, esi
0x1800107fe  test    rax, rax
0x180010801  jz      loc_18001089B
0x180010807  mov     [rbp+var_30], rax
0x18001080b  mov     dword ptr [rax+0Ch], 1
0x180010812  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStream@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream>::`vftable'
0x180010819  mov     [rcx], rax
0x18001081c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180010823  test    rcx, rcx
0x180010826  jz      short loc_180010835
0x180010828  mov     rax, [rcx]
0x18001082b  mov     rax, [rax+8]
0x18001082f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010834  nop
0x180010835  lea     rax, ??_7AutoDeleteFileStream@@6B@; const AutoDeleteFileStream::`vftable'
0x18001083c  mov     [rbx], rax
0x18001083f  lea     rcx, [rbx+10h]; void *
0x180010843  mov     qword ptr [rcx+18h], 7
0x18001084b  mov     qword ptr [rcx+10h], 0
0x180010853  xor     eax, eax
0x180010855  mov     [rcx], ax
0x180010858  mov     rdx, rdi; Src
0x18001085b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180010860  nop
0x180010861  lea     rax, [rbx+30h]
0x180010865  mov     qword ptr [rax], 0
0x18001086c  mov     [rsp+80h+ppstm], rax; ppstm
0x180010871  mov     [rsp+80h+pstmTemplate], 0; int
0x18001087a  xor     r9d, r9d; fCreate
0x18001087d  xor     edx, edx; grfMode
0x18001087f  mov     r8d, 80h; dwAttributes
0x180010885  mov     rcx, rdi; pszFile
0x180010888  call    cs:__imp_SHCreateStreamOnFileEx
0x18001088e  mov     rcx, [rbp+28h]; this
0x180010892  test    eax, eax
0x180010894  js      short loc_1800108D7
0x180010896  xor     ecx, ecx
0x180010898  mov     rsi, rbx
0x18001089b  test    rcx, rcx
0x18001089e  jz      short loc_1800108A6
0x1800108a0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800108a6  mov     [r14], rsi
0x1800108a9  cmp     [rbp+var_10], 8
0x1800108ae  jb      short loc_1800108BA
0x1800108b0  mov     rcx, [rbp+pszFile]
0x1800108b4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800108ba  mov     rax, r14
0x1800108bd  mov     rcx, [rbp+var_8]
0x1800108c1  xor     rcx, rsp; StackCookie
0x1800108c4  call    __security_check_cookie
0x1800108c9  add     rsp, 80h
0x1800108d0  pop     r14
0x1800108d2  pop     rdi
0x1800108d3  pop     rsi
0x1800108d4  pop     rbx
0x1800108d5  pop     rbp
0x1800108d6  retn
0x1800108d7  mov     r9d, eax; char *
0x1800108da  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\provision"...
0x1800108e1  mov     edx, 1Bh; void *
0x1800108e6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800108ec  mov     r9d, eax; char *
0x1800108ef  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\provision"...
0x1800108f6  mov     edx, 0BDh; void *
0x1800108fb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
