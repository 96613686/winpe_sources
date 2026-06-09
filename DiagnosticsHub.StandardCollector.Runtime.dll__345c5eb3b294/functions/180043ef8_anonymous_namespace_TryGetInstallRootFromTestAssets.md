# _anonymous_namespace_::TryGetInstallRootFromTestAssets

- ea: `0x180043ef8`
- end: `0x180044042`
- name: `_anonymous_namespace_::TryGetInstallRootFromTestAssets`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180044044`

## callees

- `0x18000a17c`
- `0x18002f17c`
- `0x180040d8c`
- `0x180041c78`
- `0x180043ef8`
- `0x180049b50`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180043f27`
- `KERNEL32!GetModuleHandleW` at `0x180043f42`
- `KERNEL32!GetModuleHandleW` at `0x180043f58`
- `KERNEL32!GetModuleHandleW` at `0x180043f27`
- `KERNEL32!GetModuleHandleW` at `0x180043f42`
- `KERNEL32!GetModuleHandleW` at `0x180043f58`
- `OLEAUT32!__imp_SysAllocString` at `0x180043fef`
- `OLEAUT32!__imp_SysAllocString` at `0x180043fef`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180043fdf`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180043fdf`

## string_xrefs

- `0x180043f20`: `StandardCollector.dll`
- `0x180043f3b`: `testhost.dll`

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
0x180043ef8  mov     [rsp-8+arg_8], rbx
0x180043efd  mov     [rsp-8+arg_10], rsi
0x180043f02  mov     [rsp-8+arg_18], rdi
0x180043f07  push    rbp
0x180043f08  mov     rbp, rsp
0x180043f0b  sub     rsp, 60h
0x180043f0f  mov     rax, cs:__security_cookie
0x180043f16  xor     rax, rsp
0x180043f19  mov     [rbp+var_10], rax
0x180043f1d  mov     rdi, rcx
0x180043f20  lea     rcx, aStandardcollec_0; "StandardCollector.dll"
0x180043f27  call    cs:__imp_GetModuleHandleW
0x180043f2d  mov     rbx, rax
0x180043f30  xor     esi, esi
0x180043f32  test    rax, rax
0x180043f35  jz      loc_18004401B
0x180043f3b  lea     rcx, aTesthostDll; "testhost.dll"
0x180043f42  call    cs:__imp_GetModuleHandleW
0x180043f48  test    rax, rax
0x180043f4b  jnz     loc_18004401B
0x180043f51  lea     rcx, aTesthostExe; "testhost.exe"
0x180043f58  call    cs:__imp_GetModuleHandleW
0x180043f5e  test    rax, rax
0x180043f61  jnz     loc_18004401B
0x180043f67  xorps   xmm1, xmm1
0x180043f6a  movdqu  xmmword ptr [rbp+var_28], xmm1
0x180043f6f  mov     [rbp+var_18], rsi
0x180043f73  lea     rdx, [rbp+var_28]
0x180043f77  mov     rcx, rbx; hModule
0x180043f7a  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x180043f7f  mov     ebx, eax
0x180043f81  test    eax, eax
0x180043f83  js      loc_18004400E
0x180043f89  xorps   xmm0, xmm0
0x180043f8c  xor     eax, eax
0x180043f8e  movups  xmmword ptr [rbp+pszPath], xmm0
0x180043f92  mov     [rbp+var_30], rax
0x180043f96  mov     rax, [rbp+var_28]
0x180043f9a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180043f9e  inc     rdx
0x180043fa1  cmp     [rax+rdx*2], si
0x180043fa5  jnz     short loc_180043F9E
0x180043fa7  lea     rdx, ds:2[rdx*2]
0x180043faf  lea     rcx, [rbp+pszPath]
0x180043fb3  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180043fb8  nop
0x180043fb9  mov     rcx, [rbp+pszPath]; this
0x180043fbd  mov     rdx, [rbp+pszPath+8]
0x180043fc1  sub     rdx, rcx
0x180043fc4  sar     rdx, 1; unsigned __int16 *
0x180043fc7  mov     r8, [rbp+var_28]; unsigned __int64
0x180043fcb  call    ?PathCchCanonicalize@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJPEAG_KPEBG@Z; Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchCanonicalize(ushort *,unsigned __int64,ushort const *)
0x180043fd0  mov     ebx, eax
0x180043fd2  test    eax, eax
0x180043fd4  js      short loc_180044004
0x180043fd6  mov     ebx, 4
0x180043fdb  mov     rcx, [rbp+pszPath]; pszPath
0x180043fdf  call    cs:__imp_PathRemoveFileSpecW
0x180043fe5  dec     ebx
0x180043fe7  test    ebx, ebx
0x180043fe9  jg      short loc_180043FDB
0x180043feb  mov     rcx, [rbp+pszPath]; psz
0x180043fef  call    cs:__imp_SysAllocString
0x180043ff5  mov     [rdi], rax
0x180043ff8  test    rax, rax
0x180043ffb  mov     ebx, 8007000Eh
0x180044000  jz      short loc_180044004
0x180044002  mov     ebx, esi
0x180044004  lea     rcx, [rbp+pszPath]
0x180044008  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004400d  nop
0x18004400e  lea     rcx, [rbp+var_28]
0x180044012  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180044017  mov     eax, ebx
0x180044019  jmp     short loc_180044020
0x18004401b  mov     eax, 0E111005Bh
0x180044020  mov     rcx, [rbp+var_10]
0x180044024  xor     rcx, rsp; StackCookie
0x180044027  call    __security_check_cookie
0x18004402c  lea     r11, [rsp+60h+var_s0]
0x180044031  mov     rbx, [r11+18h]
0x180044035  mov     rsi, [r11+20h]
0x180044039  mov     rdi, [r11+28h]
0x18004403d  mov     rsp, r11
0x180044040  pop     rbp
0x180044041  retn
```
