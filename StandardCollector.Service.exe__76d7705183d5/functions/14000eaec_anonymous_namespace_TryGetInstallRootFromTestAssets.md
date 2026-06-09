# _anonymous_namespace_::TryGetInstallRootFromTestAssets

- ea: `0x14000eaec`
- end: `0x14000ec36`
- name: `_anonymous_namespace_::TryGetInstallRootFromTestAssets`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000ec38`

## callees

- `0x1400043a0`
- `0x1400095e4`
- `0x14000eaec`
- `0x14000f364`
- `0x1400108a8`
- `0x1400137e0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000eb1b`
- `KERNEL32!GetModuleHandleW` at `0x14000eb36`
- `KERNEL32!GetModuleHandleW` at `0x14000eb4c`
- `KERNEL32!GetModuleHandleW` at `0x14000eb1b`
- `KERNEL32!GetModuleHandleW` at `0x14000eb36`
- `KERNEL32!GetModuleHandleW` at `0x14000eb4c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000ebe3`
- `OLEAUT32!__imp_SysAllocString` at `0x14000ebe3`
- `SHLWAPI!PathRemoveFileSpecW` at `0x14000ebd3`
- `SHLWAPI!PathRemoveFileSpecW` at `0x14000ebd3`

## string_xrefs

- `0x14000eb14`: `StandardCollector.dll`
- `0x14000eb2f`: `testhost.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::TryGetInstallRootFromTestAssets(BSTR *a1)
{
  HMODULE ModuleHandleW; // rbx
  int ModulePath; // ebx
  __int64 v4; // rdx
  const unsigned __int16 *v5; // r9
  int i; // ebx
  BSTR v7; // rax
  LPWSTR pszPath[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v10; // [rsp+30h] [rbp-30h]
  unsigned __int64 v11[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v12; // [rsp+48h] [rbp-18h]

  ModuleHandleW = GetModuleHandleW(L"StandardCollector.dll");
  if ( !ModuleHandleW || GetModuleHandleW(L"testhost.dll") || GetModuleHandleW(L"testhost.exe") )
    return 3775987803LL;
  *(_OWORD *)v11 = 0;
  v12 = 0;
  ModulePath = DiagHubCommon::ModulePath::GetModulePath(ModuleHandleW);
  if ( ModulePath >= 0 )
  {
    *(_OWORD *)pszPath = 0;
    v10 = 0;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(v11[0] + 2 * v4) );
    std::vector<unsigned short>::vector<unsigned short>(pszPath, 2 * v4 + 2);
    ModulePath = Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(
                   (Microsoft::DiagnosticsHub::UnifiedPlatform *)pszPath[0],
                   (unsigned __int16 *)(pszPath[1] - pszPath[0]),
                   v11[0],
                   v5);
    if ( ModulePath >= 0 )
    {
      for ( i = 4; i > 0; --i )
        PathRemoveFileSpecW(pszPath[0]);
      v7 = SysAllocString(pszPath[0]);
      *a1 = v7;
      ModulePath = -2147024882;
      if ( v7 )
        ModulePath = 0;
    }
    std::vector<unsigned short>::~vector<unsigned short>(pszPath);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v11);
  return (unsigned int)ModulePath;
}

```

## disassembly

```asm
0x14000eaec  mov     [rsp-8+arg_8], rbx
0x14000eaf1  mov     [rsp-8+arg_10], rsi
0x14000eaf6  mov     [rsp-8+arg_18], rdi
0x14000eafb  push    rbp
0x14000eafc  mov     rbp, rsp
0x14000eaff  sub     rsp, 60h
0x14000eb03  mov     rax, cs:__security_cookie
0x14000eb0a  xor     rax, rsp
0x14000eb0d  mov     [rbp+var_10], rax
0x14000eb11  mov     rdi, rcx
0x14000eb14  lea     rcx, aStandardcollec; "StandardCollector.dll"
0x14000eb1b  call    cs:__imp_GetModuleHandleW
0x14000eb21  mov     rbx, rax
0x14000eb24  xor     esi, esi
0x14000eb26  test    rax, rax
0x14000eb29  jz      loc_14000EC0F
0x14000eb2f  lea     rcx, aTesthostDll; "testhost.dll"
0x14000eb36  call    cs:__imp_GetModuleHandleW
0x14000eb3c  test    rax, rax
0x14000eb3f  jnz     loc_14000EC0F
0x14000eb45  lea     rcx, aTesthostExe; "testhost.exe"
0x14000eb4c  call    cs:__imp_GetModuleHandleW
0x14000eb52  test    rax, rax
0x14000eb55  jnz     loc_14000EC0F
0x14000eb5b  xorps   xmm1, xmm1
0x14000eb5e  movdqu  xmmword ptr [rbp+var_28], xmm1
0x14000eb63  mov     [rbp+var_18], rsi
0x14000eb67  lea     rdx, [rbp+var_28]
0x14000eb6b  mov     rcx, rbx; hModule
0x14000eb6e  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x14000eb73  mov     ebx, eax
0x14000eb75  test    eax, eax
0x14000eb77  js      loc_14000EC02
0x14000eb7d  xorps   xmm0, xmm0
0x14000eb80  xor     eax, eax
0x14000eb82  movups  xmmword ptr [rbp+pszPath], xmm0
0x14000eb86  mov     [rbp+var_30], rax
0x14000eb8a  mov     rax, [rbp+var_28]
0x14000eb8e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000eb92  inc     rdx
0x14000eb95  cmp     [rax+rdx*2], si
0x14000eb99  jnz     short loc_14000EB92
0x14000eb9b  lea     rdx, ds:2[rdx*2]
0x14000eba3  lea     rcx, [rbp+pszPath]
0x14000eba7  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x14000ebac  nop
0x14000ebad  mov     rcx, [rbp+pszPath]; this
0x14000ebb1  mov     rdx, [rbp+pszPath+8]
0x14000ebb5  sub     rdx, rcx
0x14000ebb8  sar     rdx, 1; unsigned __int16 *
0x14000ebbb  mov     r8, [rbp+var_28]; unsigned __int64
0x14000ebbf  call    ?PathCchCanonicalize@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJPEAG_KPEBG@Z; Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(ushort *,unsigned __int64,ushort const *)
0x14000ebc4  mov     ebx, eax
0x14000ebc6  test    eax, eax
0x14000ebc8  js      short loc_14000EBF8
0x14000ebca  mov     ebx, 4
0x14000ebcf  mov     rcx, [rbp+pszPath]; pszPath
0x14000ebd3  call    cs:__imp_PathRemoveFileSpecW
0x14000ebd9  dec     ebx
0x14000ebdb  test    ebx, ebx
0x14000ebdd  jg      short loc_14000EBCF
0x14000ebdf  mov     rcx, [rbp+pszPath]; psz
0x14000ebe3  call    cs:__imp_SysAllocString
0x14000ebe9  mov     [rdi], rax
0x14000ebec  test    rax, rax
0x14000ebef  mov     ebx, 8007000Eh
0x14000ebf4  jz      short loc_14000EBF8
0x14000ebf6  mov     ebx, esi
0x14000ebf8  lea     rcx, [rbp+pszPath]
0x14000ebfc  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000ec01  nop
0x14000ec02  lea     rcx, [rbp+var_28]
0x14000ec06  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000ec0b  mov     eax, ebx
0x14000ec0d  jmp     short loc_14000EC14
0x14000ec0f  mov     eax, 0E111005Bh
0x14000ec14  mov     rcx, [rbp+var_10]
0x14000ec18  xor     rcx, rsp; StackCookie
0x14000ec1b  call    __security_check_cookie
0x14000ec20  lea     r11, [rsp+60h+var_s0]
0x14000ec25  mov     rbx, [r11+18h]
0x14000ec29  mov     rsi, [r11+20h]
0x14000ec2d  mov     rdi, [r11+28h]
0x14000ec31  mov     rsp, r11
0x14000ec34  pop     rbp
0x14000ec35  retn
```
