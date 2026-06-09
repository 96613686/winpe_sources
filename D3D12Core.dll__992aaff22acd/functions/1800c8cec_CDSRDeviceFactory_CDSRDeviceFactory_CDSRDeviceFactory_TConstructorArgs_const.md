# CDSRDeviceFactory::CDSRDeviceFactory(CDSRDeviceFactory::TConstructorArgs const &)

- ea: `0x1800c8cec`
- end: `0x1800c8e75`
- name: `??0CDSRDeviceFactory@@QEAA@AEBUTConstructorArgs@0@@Z`
- size: `393`
- prototype: `CDSRDeviceFactory *__fastcall(CDSRDeviceFactory *__hidden this, const struct CDSRDeviceFactory::TConstructorArgs *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800ab82c`

## callees

- `0x1800235dc`
- `0x180029b30`
- `0x1800578c4`
- `0x1800b8c14`
- `0x1800bb480`
- `0x1800c8818`
- `0x1800c8cec`
- `0x180224e94`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c8de0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c8de0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800c8d98`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800c8d98`

## string_xrefs

- `0x1800c8d5f`: `DirectSR.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
CDSRDeviceFactory *__fastcall CDSRDeviceFactory::CDSRDeviceFactory(
        CDSRDeviceFactory *this,
        const struct CDSRDeviceFactory::TConstructorArgs *a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  const WCHAR *v5; // rcx
  HMODULE LibraryW; // rax
  HINSTANCE v7; // rbx
  FARPROC ProcAddress; // rax
  _QWORD v10[3]; // [rsp+20h] [rbp-39h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-21h] BYREF
  const char *v12; // [rsp+40h] [rbp-19h]
  __int64 v13; // [rsp+48h] [rbp-11h]
  LPCWSTR lpLibFileName[4]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v15[32]; // [rsp+78h] [rbp+1Fh] BYREF

  v10[2] = this;
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &CDSRDeviceFactory::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v10[0] = *(&lpMem + 1);
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)*(&lpMem + 1) + v3) );
  v10[1] = v3;
  std::wstring::wstring(v15, v10);
  v4 = std::wstring::wstring(&pExceptionObject, L"DirectSR.dll");
  std::operator+<unsigned short>(lpLibFileName, v15, v4);
  std::wstring::_Tidy_deallocate(&pExceptionObject);
  v5 = (const WCHAR *)lpLibFileName;
  if ( lpLibFileName[3] > (LPCWSTR)7 )
    v5 = lpLibFileName[0];
  LibraryW = LoadLibraryW(v5);
  v7 = LibraryW;
  v10[0] = LibraryW;
  if ( !LibraryW )
  {
    v13 = 0;
    v12 = "bad allocation";
    pExceptionObject = &hlsl::RDAT::CheckedReader::exception::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  ProcAddress = GetProcAddress(LibraryW, (LPCSTR)1);
  *((_QWORD *)this + 3) = ProcAddress;
  if ( !ProcAddress )
  {
    v13 = 0;
    v12 = "bad allocation";
    pExceptionObject = &hlsl::RDAT::CheckedReader::exception::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v10[0] = 0;
  D3DXPlat::unique_module::reset((CDSRDeviceFactory *)((char *)this + 16), v7);
  D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)v10, 0);
  std::wstring::_Tidy_deallocate(lpLibFileName);
  std::wstring::_Tidy_deallocate(v15);
  return this;
}

```

## disassembly

```asm
0x1800c8cec  mov     [rsp-8+arg_8], rbx
0x1800c8cf1  mov     [rsp-8+arg_10], rsi
0x1800c8cf6  push    rbp
0x1800c8cf7  push    rdi
0x1800c8cf8  push    r14
0x1800c8cfa  lea     rbp, [rsp-47h]
0x1800c8cff  sub     rsp, 0A0h
0x1800c8d06  mov     rax, cs:__security_cookie
0x1800c8d0d  xor     rax, rsp
0x1800c8d10  mov     [rbp+57h+var_18], rax
0x1800c8d14  mov     rdi, rcx
0x1800c8d17  mov     [rbp+57h+var_80], rcx
0x1800c8d1b  xor     r14d, r14d
0x1800c8d1e  mov     [rcx+8], r14d
0x1800c8d22  lea     rax, ??_7CDSRDeviceFactory@@6B@; const CDSRDeviceFactory::`vftable'
0x1800c8d29  mov     [rcx], rax
0x1800c8d2c  mov     [rcx+10h], r14
0x1800c8d30  mov     [rcx+18h], r14
0x1800c8d34  mov     rcx, qword ptr cs:lpMem+8
0x1800c8d3b  mov     [rbp+57h+var_90], rcx
0x1800c8d3f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c8d43  inc     rax
0x1800c8d46  cmp     [rcx+rax*2], r14w
0x1800c8d4b  jnz     short loc_1800C8D43
0x1800c8d4d  mov     [rbp+57h+var_88], rax
0x1800c8d51  lea     rdx, [rbp+57h+var_90]
0x1800c8d55  lea     rcx, [rbp+57h+var_38]
0x1800c8d59  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x1800c8d5e  nop
0x1800c8d5f  lea     rdx, aDirectsrDll; "DirectSR.dll"
0x1800c8d66  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c8d6a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c8d6f  nop
0x1800c8d70  mov     r8, rax
0x1800c8d73  lea     rdx, [rbp+57h+var_38]
0x1800c8d77  lea     rcx, [rbp+57h+lpLibFileName]
0x1800c8d7b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x1800c8d80  nop
0x1800c8d81  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c8d85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c8d8a  lea     rcx, [rbp+57h+lpLibFileName]
0x1800c8d8e  cmp     [rbp+57h+var_40], 7
0x1800c8d93  cmova   rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x1800c8d98  call    cs:__imp_LoadLibraryW
0x1800c8d9e  mov     rbx, rax
0x1800c8da1  mov     [rbp+57h+var_90], rax
0x1800c8da5  test    rax, rax
0x1800c8da8  jnz     short loc_1800C8DD8
0x1800c8daa  xorps   xmm0, xmm0
0x1800c8dad  movups  [rbp+57h+var_70], xmm0
0x1800c8db1  lea     rax, aBadAllocation; "bad allocation"
0x1800c8db8  mov     qword ptr [rbp+57h+var_70], rax
0x1800c8dbc  lea     rax, ??_7exception@CheckedReader@RDAT@hlsl@@6B@; const hlsl::RDAT::CheckedReader::exception::`vftable'
0x1800c8dc3  mov     [rbp+57h+pExceptionObject], rax
0x1800c8dc7  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800c8dce  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c8dd2  call    _CxxThrowException_0
0x1800c8dd8  mov     edx, 1; lpProcName
0x1800c8ddd  mov     rcx, rbx; hModule
0x1800c8de0  call    cs:__imp_GetProcAddress
0x1800c8de6  mov     [rdi+18h], rax
0x1800c8dea  test    rax, rax
0x1800c8ded  jnz     short loc_1800C8E1D
0x1800c8def  xorps   xmm0, xmm0
0x1800c8df2  movups  [rbp+57h+var_70], xmm0
0x1800c8df6  lea     rax, aBadAllocation; "bad allocation"
0x1800c8dfd  mov     qword ptr [rbp+57h+var_70], rax
0x1800c8e01  lea     rax, ??_7exception@CheckedReader@RDAT@hlsl@@6B@; const hlsl::RDAT::CheckedReader::exception::`vftable'
0x1800c8e08  mov     [rbp+57h+pExceptionObject], rax
0x1800c8e0c  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800c8e13  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c8e17  call    _CxxThrowException_0
0x1800c8e1d  mov     [rbp+57h+var_90], r14
0x1800c8e21  mov     rdx, rbx; HINSTANCE
0x1800c8e24  lea     rcx, [rdi+10h]; this
0x1800c8e28  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x1800c8e2d  nop
0x1800c8e2e  xor     edx, edx; HINSTANCE
0x1800c8e30  lea     rcx, [rbp+57h+var_90]; this
0x1800c8e34  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x1800c8e39  nop
0x1800c8e3a  lea     rcx, [rbp+57h+lpLibFileName]
0x1800c8e3e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c8e43  nop
0x1800c8e44  lea     rcx, [rbp+57h+var_38]
0x1800c8e48  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c8e4d  nop
0x1800c8e4e  mov     rax, rdi
0x1800c8e51  mov     rcx, [rbp+57h+var_18]
0x1800c8e55  xor     rcx, rsp; StackCookie
0x1800c8e58  call    __security_check_cookie
0x1800c8e5d  lea     r11, [rsp+0B0h+var_10]
0x1800c8e65  mov     rbx, [r11+28h]
0x1800c8e69  mov     rsi, [r11+30h]
0x1800c8e6d  mov     rsp, r11
0x1800c8e70  pop     r14
0x1800c8e72  pop     rdi
0x1800c8e73  pop     rbp
0x1800c8e74  retn
```
