# Windows::Rtl::InitializeDeltaCompressor(void *)

- ea: `0x18001de30`
- end: `0x18001e073`
- name: `?InitializeDeltaCompressor@Rtl@Windows@@YAJPEAX@Z`
- size: `579`
- prototype: `__int64 __fastcall(Windows::Rtl *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001dae0`

## callees

- `0x180002434`
- `0x1800033e0`
- `0x180003550`
- `0x18001c320`
- `0x18001de30`
- `0x1800293a0`
- `0x18008d248`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x18001deaf`
- `KERNEL32!GetModuleHandleExW` at `0x18001deaf`
- `KERNEL32!GetProcAddress` at `0x18001df92`
- `KERNEL32!GetProcAddress` at `0x18001dfb3`
- `KERNEL32!GetProcAddress` at `0x18001dfd4`
- `KERNEL32!GetProcAddress` at `0x18001dff5`
- `KERNEL32!GetProcAddress` at `0x18001e016`
- `KERNEL32!GetProcAddress` at `0x18001e037`
- `KERNEL32!GetProcAddress` at `0x18001df92`
- `KERNEL32!GetProcAddress` at `0x18001dfb3`
- `KERNEL32!GetProcAddress` at `0x18001dfd4`
- `KERNEL32!GetProcAddress` at `0x18001dff5`
- `KERNEL32!GetProcAddress` at `0x18001e016`
- `KERNEL32!GetProcAddress` at `0x18001e037`
- `KERNEL32!LoadLibraryExW` at `0x18001df1e`
- `KERNEL32!LoadLibraryExW` at `0x18001df52`
- `KERNEL32!LoadLibraryExW` at `0x18001df1e`
- `KERNEL32!LoadLibraryExW` at `0x18001df52`

## string_xrefs

- `0x18001df88`: `CreateDeltaB`
- `0x18001dea6`: `UpdateCompression.dll`
- `0x18001df49`: `UpdateCompression.dll`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::InitializeDeltaCompressor(Windows::Rtl *this, void *a2)
{
  int Win32PathOfSiblingFile; // eax
  unsigned int v3; // ebx
  LPCWSTR v5; // rbx
  HMODULE Library; // rax
  __int64 v7; // r8
  int v8; // eax
  unsigned int v9; // ecx
  __int128 v10; // [rsp+20h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-28h]
  HMODULE phModule; // [rsp+38h] [rbp-20h] BYREF

  if ( !byte_1800D4DF8
    || !hModule
    || !qword_1800D4DE0
    || !qword_1800D4E08
    || !qword_1800D4DF0
    || !qword_1800D4E18
    || !qword_1800D4E00
    || !qword_1800D4DE8 )
  {
    phModule = 0;
    if ( GetModuleHandleExW(0, L"UpdateCompression.dll", &phModule) )
    {
      Library = phModule;
    }
    else
    {
      v10 = 0;
      lpLibFileName = 0;
      Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(this, a2, &v10);
      if ( Win32PathOfSiblingFile < 0 )
      {
        v3 = ConvertHResultToNtStatus((unsigned int)Win32PathOfSiblingFile);
        if ( lpLibFileName )
          RtlFreeLUtf8String(&v10);
        return v3;
      }
      v5 = lpLibFileName;
      Library = LoadLibraryExW(lpLibFileName, 0, 0);
      phModule = Library;
      if ( v5 )
      {
        anonymous_namespace_::OurRtlFreeStringRoutine(v5, a2, v7);
        Library = phModule;
      }
      if ( Library )
        goto LABEL_20;
      Library = LoadLibraryExW(L"UpdateCompression.dll", 0, 0);
      phModule = Library;
    }
    if ( !Library )
    {
      Library = hModule;
      goto LABEL_22;
    }
LABEL_20:
    hModule = Library;
LABEL_22:
    if ( Library )
    {
      qword_1800D4DE0 = (__int64)GetProcAddress(Library, "CreateDeltaB");
      qword_1800D4E08 = (__int64)GetProcAddress(hModule, "ApplyDeltaB");
      qword_1800D4DF0 = (__int64)GetProcAddress(hModule, "ApplyDeltaGetReverseB");
      qword_1800D4E18 = (__int64)GetProcAddress(hModule, "GetDeltaInfoExB");
      qword_1800D4E00 = (__int64)GetProcAddress(hModule, "GetDeltaSignatureB");
      qword_1800D4DE8 = (__int64)GetProcAddress(hModule, "DeltaFree");
    }
    byte_1800D4DF8 = 1;
  }
  v8 = anonymous_namespace_::ValidateDeltaBufferCompressorInitialized(this, a2);
  v9 = 0;
  if ( v8 < 0 )
    return (unsigned int)v8;
  return v9;
}

```

## disassembly

```asm
0x18001de30  push    rbx
0x18001de32  sub     rsp, 50h
0x18001de36  mov     rax, cs:__security_cookie
0x18001de3d  xor     rax, rsp
0x18001de40  mov     [rsp+58h+var_18], rax
0x18001de45  cmp     cs:byte_1800D4DF8, 0
0x18001de4c  jz      short loc_18001DE98
0x18001de4e  cmp     cs:hModule, 0
0x18001de56  jz      short loc_18001DE98
0x18001de58  cmp     cs:qword_1800D4DE0, 0
0x18001de60  jz      short loc_18001DE98
0x18001de62  cmp     cs:qword_1800D4E08, 0
0x18001de6a  jz      short loc_18001DE98
0x18001de6c  cmp     cs:qword_1800D4DF0, 0
0x18001de74  jz      short loc_18001DE98
0x18001de76  cmp     cs:qword_1800D4E18, 0
0x18001de7e  jz      short loc_18001DE98
0x18001de80  cmp     cs:qword_1800D4E00, 0
0x18001de88  jz      short loc_18001DE98
0x18001de8a  cmp     cs:qword_1800D4DE8, 0
0x18001de92  jnz     loc_18001E051
0x18001de98  lea     r8, [rsp+58h+phModule]; phModule
0x18001de9d  mov     [rsp+58h+phModule], 0
0x18001dea6  lea     rdx, g_RGWCH_UpdateCompression_dot_dll; "UpdateCompression.dll"
0x18001dead  xor     ecx, ecx; dwFlags
0x18001deaf  call    cs:__imp_GetModuleHandleExW
0x18001deb6  nop     dword ptr [rax+rax+00h]
0x18001debb  test    eax, eax
0x18001debd  jnz     loc_18001DF65
0x18001dec3  xorps   xmm0, xmm0
0x18001dec6  lea     r8, [rsp+58h+var_38]
0x18001decb  xor     eax, eax
0x18001decd  movups  [rsp+58h+var_38], xmm0
0x18001ded2  mov     [rsp+58h+lpLibFileName], rax
0x18001ded7  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x18001dedc  test    eax, eax
0x18001dede  jns     short loc_18001DF11
0x18001dee0  mov     ecx, eax
0x18001dee2  call    ConvertHResultToNtStatus
0x18001dee7  cmp     [rsp+58h+lpLibFileName], 0
0x18001deed  mov     ebx, eax
0x18001deef  jz      short loc_18001DEFB
0x18001def1  lea     rcx, [rsp+58h+var_38]
0x18001def6  call    RtlFreeLUtf8String
0x18001defb  mov     eax, ebx
0x18001defd  mov     rcx, [rsp+58h+var_18]
0x18001df02  xor     rcx, rsp; StackCookie
0x18001df05  call    __security_check_cookie
0x18001df0a  add     rsp, 50h
0x18001df0e  pop     rbx
0x18001df0f  retn
0x18001df11  mov     rbx, [rsp+58h+lpLibFileName]
0x18001df16  xor     r8d, r8d; dwFlags
0x18001df19  mov     rcx, rbx; lpLibFileName
0x18001df1c  xor     edx, edx; hFile
0x18001df1e  call    cs:__imp_LoadLibraryExW
0x18001df25  nop     dword ptr [rax+rax+00h]
0x18001df2a  mov     [rsp+58h+phModule], rax
0x18001df2f  test    rbx, rbx
0x18001df32  jz      short loc_18001DF41
0x18001df34  mov     rcx, rbx
0x18001df37  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001df3c  mov     rax, [rsp+58h+phModule]
0x18001df41  test    rax, rax
0x18001df44  jnz     short loc_18001DF6F
0x18001df46  xor     r8d, r8d; dwFlags
0x18001df49  lea     rcx, g_RGWCH_UpdateCompression_dot_dll; "UpdateCompression.dll"
0x18001df50  xor     edx, edx; hFile
0x18001df52  call    cs:__imp_LoadLibraryExW
0x18001df59  nop     dword ptr [rax+rax+00h]
0x18001df5e  mov     [rsp+58h+phModule], rax
0x18001df63  jmp     short loc_18001DF6A
0x18001df65  mov     rax, [rsp+58h+phModule]
0x18001df6a  test    rax, rax
0x18001df6d  jz      short loc_18001DF78
0x18001df6f  mov     cs:hModule, rax
0x18001df76  jmp     short loc_18001DF7F
0x18001df78  mov     rax, cs:hModule
0x18001df7f  test    rax, rax
0x18001df82  jz      loc_18001E04A
0x18001df88  lea     rdx, aCreatedeltab; "CreateDeltaB"
0x18001df8f  mov     rcx, rax; hModule
0x18001df92  call    cs:__imp_GetProcAddress
0x18001df99  nop     dword ptr [rax+rax+00h]
0x18001df9e  mov     rcx, cs:hModule; hModule
0x18001dfa5  lea     rdx, aApplydeltab; "ApplyDeltaB"
0x18001dfac  mov     cs:qword_1800D4DE0, rax
0x18001dfb3  call    cs:__imp_GetProcAddress
0x18001dfba  nop     dword ptr [rax+rax+00h]
0x18001dfbf  mov     rcx, cs:hModule; hModule
0x18001dfc6  lea     rdx, aApplydeltagetr; "ApplyDeltaGetReverseB"
0x18001dfcd  mov     cs:qword_1800D4E08, rax
0x18001dfd4  call    cs:__imp_GetProcAddress
0x18001dfdb  nop     dword ptr [rax+rax+00h]
0x18001dfe0  mov     rcx, cs:hModule; hModule
0x18001dfe7  lea     rdx, aGetdeltainfoex; "GetDeltaInfoExB"
0x18001dfee  mov     cs:qword_1800D4DF0, rax
0x18001dff5  call    cs:__imp_GetProcAddress
0x18001dffc  nop     dword ptr [rax+rax+00h]
0x18001e001  mov     rcx, cs:hModule; hModule
0x18001e008  lea     rdx, aGetdeltasignat; "GetDeltaSignatureB"
0x18001e00f  mov     cs:qword_1800D4E18, rax
0x18001e016  call    cs:__imp_GetProcAddress
0x18001e01d  nop     dword ptr [rax+rax+00h]
0x18001e022  mov     rcx, cs:hModule; hModule
0x18001e029  lea     rdx, aDeltafree; "DeltaFree"
0x18001e030  mov     cs:qword_1800D4E00, rax
0x18001e037  call    cs:__imp_GetProcAddress
0x18001e03e  nop     dword ptr [rax+rax+00h]
0x18001e043  mov     cs:qword_1800D4DE8, rax
0x18001e04a  mov     cs:byte_1800D4DF8, 1
0x18001e051  call    _anonymous_namespace___ValidateDeltaBufferCompressorInitialized
0x18001e056  xor     ecx, ecx
0x18001e058  test    eax, eax
0x18001e05a  cmovs   ecx, eax
0x18001e05d  mov     eax, ecx
0x18001e05f  mov     rcx, [rsp+58h+var_18]
0x18001e064  xor     rcx, rsp; StackCookie
0x18001e067  call    __security_check_cookie
0x18001e06c  add     rsp, 50h
0x18001e070  pop     rbx
0x18001e071  retn
```
