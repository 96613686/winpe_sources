# Windows::Rtl::InitializeDeltaCompressor(void *)

- ea: `0x18000ca60`
- end: `0x18000cc85`
- name: `?InitializeDeltaCompressor@Rtl@Windows@@YAJPEAX@Z`
- size: `549`
- prototype: `__int64 __fastcall(Windows::Rtl *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001c300`

## callees

- `0x180004a8c`
- `0x180004f20`
- `0x18000ca60`
- `0x18000cc90`
- `0x18000cff8`
- `0x180021454`
- `0x18002d2b0`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x18000cafb`
- `KERNEL32!GetModuleHandleExW` at `0x18000cafb`
- `KERNEL32!LoadLibraryExW` at `0x18000cb71`
- `KERNEL32!LoadLibraryExW` at `0x18000cba2`
- `KERNEL32!LoadLibraryExW` at `0x18000cb71`
- `KERNEL32!LoadLibraryExW` at `0x18000cba2`
- `KERNEL32!GetProcAddress` at `0x18000cbc8`
- `KERNEL32!GetProcAddress` at `0x18000cbe9`
- `KERNEL32!GetProcAddress` at `0x18000cc0a`
- `KERNEL32!GetProcAddress` at `0x18000cc2b`
- `KERNEL32!GetProcAddress` at `0x18000cc4c`
- `KERNEL32!GetProcAddress` at `0x18000cc6d`
- `KERNEL32!GetProcAddress` at `0x18000cbc8`
- `KERNEL32!GetProcAddress` at `0x18000cbe9`
- `KERNEL32!GetProcAddress` at `0x18000cc0a`
- `KERNEL32!GetProcAddress` at `0x18000cc2b`
- `KERNEL32!GetProcAddress` at `0x18000cc4c`
- `KERNEL32!GetProcAddress` at `0x18000cc6d`

## string_xrefs

- `0x18000caed`: `UpdateCompression.dll`
- `0x18000cb99`: `UpdateCompression.dll`
- `0x18000cbbe`: `CreateDeltaB`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::InitializeDeltaCompressor(Windows::Rtl *this, void *a2)
{
  unsigned int v2; // ebx
  int v3; // eax
  int Win32PathOfSiblingFile; // eax
  HMODULE Library; // rax
  __int128 v7; // [rsp+20h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-28h]
  HMODULE phModule; // [rsp+38h] [rbp-20h] BYREF

  if ( qword_1800D2DF8
    && byte_1800D2E18
    && hModule
    && qword_1800D2E28
    && qword_1800D2DF0
    && qword_1800D2E20
    && qword_1800D2E00
    && qword_1800D2E08 )
  {
    v2 = 0;
LABEL_10:
    v3 = anonymous_namespace_::ValidateDeltaBufferCompressorInitialized(this, a2);
    if ( v3 < 0 )
      return (unsigned int)v3;
    return v2;
  }
  v2 = 0;
  phModule = 0;
  if ( GetModuleHandleExW(0, L"UpdateCompression.dll", &phModule) )
  {
    Library = phModule;
    goto LABEL_18;
  }
  v7 = 0;
  lpLibFileName = 0;
  Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(this, a2, &v7);
  if ( Win32PathOfSiblingFile >= 0 )
  {
    phModule = LoadLibraryExW(lpLibFileName, 0, 0);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v7);
    Library = phModule;
    if ( phModule )
      goto LABEL_25;
    Library = LoadLibraryExW(L"UpdateCompression.dll", 0, 0);
    phModule = Library;
LABEL_18:
    if ( !Library )
    {
      Library = hModule;
LABEL_20:
      if ( Library )
      {
        qword_1800D2DF8 = (__int64)GetProcAddress(Library, "CreateDeltaB");
        qword_1800D2E28 = (__int64)GetProcAddress(hModule, "ApplyDeltaB");
        qword_1800D2DF0 = (__int64)GetProcAddress(hModule, "ApplyDeltaGetReverseB");
        qword_1800D2E20 = (__int64)GetProcAddress(hModule, "GetDeltaInfoExB");
        qword_1800D2E00 = (__int64)GetProcAddress(hModule, "GetDeltaSignatureB");
        qword_1800D2E08 = (__int64)GetProcAddress(hModule, "DeltaFree");
      }
      byte_1800D2E18 = 1;
      goto LABEL_10;
    }
LABEL_25:
    hModule = Library;
    goto LABEL_20;
  }
  v2 = ConvertHResultToNtStatus((unsigned int)Win32PathOfSiblingFile);
  if ( lpLibFileName )
    RtlFreeLUtf8String(&v7);
  return v2;
}

```

## disassembly

```asm
0x18000ca60  push    rbx
0x18000ca62  sub     rsp, 50h
0x18000ca66  mov     rax, cs:__security_cookie
0x18000ca6d  xor     rax, rsp
0x18000ca70  mov     [rsp+58h+var_18], rax
0x18000ca75  cmp     cs:qword_1800D2DF8, 0
0x18000ca7d  jz      short loc_18000CAE6
0x18000ca7f  cmp     cs:byte_1800D2E18, 0
0x18000ca86  jz      short loc_18000CAE6
0x18000ca88  cmp     cs:hModule, 0
0x18000ca90  jz      short loc_18000CAE6
0x18000ca92  cmp     cs:qword_1800D2E28, 0
0x18000ca9a  jz      short loc_18000CAE6
0x18000ca9c  cmp     cs:qword_1800D2DF0, 0
0x18000caa4  jz      short loc_18000CAE6
0x18000caa6  cmp     cs:qword_1800D2E20, 0
0x18000caae  jz      short loc_18000CAE6
0x18000cab0  cmp     cs:qword_1800D2E00, 0
0x18000cab8  jz      short loc_18000CAE6
0x18000caba  cmp     cs:qword_1800D2E08, 0
0x18000cac2  jz      short loc_18000CAE6
0x18000cac4  xor     ebx, ebx
0x18000cac6  call    _anonymous_namespace___ValidateDeltaBufferCompressorInitialized
0x18000cacb  test    eax, eax
0x18000cacd  cmovs   ebx, eax
0x18000cad0  mov     eax, ebx
0x18000cad2  mov     rcx, [rsp+58h+var_18]
0x18000cad7  xor     rcx, rsp; StackCookie
0x18000cada  call    __security_check_cookie
0x18000cadf  add     rsp, 50h
0x18000cae3  pop     rbx
0x18000cae4  retn
0x18000cae6  xor     ebx, ebx
0x18000cae8  lea     r8, [rsp+58h+phModule]; phModule
0x18000caed  lea     rdx, g_RGWCH_UpdateCompression_dot_dll; "UpdateCompression.dll"
0x18000caf4  mov     [rsp+58h+phModule], rbx
0x18000caf9  xor     ecx, ecx; dwFlags
0x18000cafb  call    cs:__imp_GetModuleHandleExW
0x18000cb02  nop     dword ptr [rax+rax+00h]
0x18000cb07  test    eax, eax
0x18000cb09  jnz     short loc_18000CB45
0x18000cb0b  xorps   xmm0, xmm0
0x18000cb0e  lea     r8, [rsp+58h+var_38]
0x18000cb13  xor     eax, eax
0x18000cb15  movups  [rsp+58h+var_38], xmm0
0x18000cb1a  mov     [rsp+58h+lpLibFileName], rax
0x18000cb1f  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x18000cb24  test    eax, eax
0x18000cb26  jns     short loc_18000CB67
0x18000cb28  mov     ecx, eax
0x18000cb2a  call    ConvertHResultToNtStatus
0x18000cb2f  cmp     [rsp+58h+lpLibFileName], 0
0x18000cb35  mov     ebx, eax
0x18000cb37  jz      short loc_18000CAD0
0x18000cb39  lea     rcx, [rsp+58h+var_38]
0x18000cb3e  call    RtlFreeLUtf8String
0x18000cb43  jmp     short loc_18000CAD0
0x18000cb45  mov     rax, [rsp+58h+phModule]
0x18000cb4a  test    rax, rax
0x18000cb4d  jnz     short loc_18000CBB5
0x18000cb4f  mov     rax, cs:hModule
0x18000cb56  test    rax, rax
0x18000cb59  jnz     short loc_18000CBBE
0x18000cb5b  mov     cs:byte_1800D2E18, 1
0x18000cb62  jmp     loc_18000CAC6
0x18000cb67  mov     rcx, [rsp+58h+lpLibFileName]; lpLibFileName
0x18000cb6c  xor     r8d, r8d; dwFlags
0x18000cb6f  xor     edx, edx; hFile
0x18000cb71  call    cs:__imp_LoadLibraryExW
0x18000cb78  nop     dword ptr [rax+rax+00h]
0x18000cb7d  lea     rcx, [rsp+58h+var_38]
0x18000cb82  mov     [rsp+58h+phModule], rax
0x18000cb87  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18000cb8c  mov     rax, [rsp+58h+phModule]
0x18000cb91  test    rax, rax
0x18000cb94  jnz     short loc_18000CBB5
0x18000cb96  xor     r8d, r8d; dwFlags
0x18000cb99  lea     rcx, g_RGWCH_UpdateCompression_dot_dll; "UpdateCompression.dll"
0x18000cba0  xor     edx, edx; hFile
0x18000cba2  call    cs:__imp_LoadLibraryExW
0x18000cba9  nop     dword ptr [rax+rax+00h]
0x18000cbae  mov     [rsp+58h+phModule], rax
0x18000cbb3  jmp     short loc_18000CB4A
0x18000cbb5  mov     cs:hModule, rax
0x18000cbbc  jmp     short loc_18000CB56
0x18000cbbe  lea     rdx, aCreatedeltab; "CreateDeltaB"
0x18000cbc5  mov     rcx, rax; hModule
0x18000cbc8  call    cs:__imp_GetProcAddress
0x18000cbcf  nop     dword ptr [rax+rax+00h]
0x18000cbd4  mov     rcx, cs:hModule; hModule
0x18000cbdb  lea     rdx, aApplydeltab; "ApplyDeltaB"
0x18000cbe2  mov     cs:qword_1800D2DF8, rax
0x18000cbe9  call    cs:__imp_GetProcAddress
0x18000cbf0  nop     dword ptr [rax+rax+00h]
0x18000cbf5  mov     rcx, cs:hModule; hModule
0x18000cbfc  lea     rdx, aApplydeltagetr; "ApplyDeltaGetReverseB"
0x18000cc03  mov     cs:qword_1800D2E28, rax
0x18000cc0a  call    cs:__imp_GetProcAddress
0x18000cc11  nop     dword ptr [rax+rax+00h]
0x18000cc16  mov     rcx, cs:hModule; hModule
0x18000cc1d  lea     rdx, aGetdeltainfoex; "GetDeltaInfoExB"
0x18000cc24  mov     cs:qword_1800D2DF0, rax
0x18000cc2b  call    cs:__imp_GetProcAddress
0x18000cc32  nop     dword ptr [rax+rax+00h]
0x18000cc37  mov     rcx, cs:hModule; hModule
0x18000cc3e  lea     rdx, aGetdeltasignat; "GetDeltaSignatureB"
0x18000cc45  mov     cs:qword_1800D2E20, rax
0x18000cc4c  call    cs:__imp_GetProcAddress
0x18000cc53  nop     dword ptr [rax+rax+00h]
0x18000cc58  mov     rcx, cs:hModule; hModule
0x18000cc5f  lea     rdx, aDeltafree; "DeltaFree"
0x18000cc66  mov     cs:qword_1800D2E00, rax
0x18000cc6d  call    cs:__imp_GetProcAddress
0x18000cc74  nop     dword ptr [rax+rax+00h]
0x18000cc79  mov     cs:qword_1800D2E08, rax
0x18000cc80  jmp     loc_18000CB5B
```
