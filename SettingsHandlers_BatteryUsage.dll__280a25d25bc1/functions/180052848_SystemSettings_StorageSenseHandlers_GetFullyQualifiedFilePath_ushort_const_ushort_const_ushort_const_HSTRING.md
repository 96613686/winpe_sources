# SystemSettings::StorageSenseHandlers::GetFullyQualifiedFilePath(ushort const *,ushort const *,ushort const *,HSTRING__ * *)

- ea: `0x180052848`
- end: `0x18005297a`
- name: `?GetFullyQualifiedFilePath@StorageSenseHandlers@SystemSettings@@YAJPEBG00PEAPEAUHSTRING__@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers *__hidden this, const unsigned __int16 *, const unsigned __int16 *, HSTRING *string, HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800532a0`

## callees

- `0x1800028d0`
- `0x180021504`
- `0x180021534`
- `0x180052848`
- `0x180054340`
- `0x1800543e8`
- `0x1800544b8`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800528fb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800528fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180052947`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180052947`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::GetFullyQualifiedFilePath(
        SystemSettings::StorageSenseHandlers *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        HSTRING *string)
{
  unsigned int v8; // r8d
  HRESULT FilePathNoMRTProtocol; // ebx
  PCNZWCH sourceString; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-C8h]
  __int64 v13; // [rsp+40h] [rbp-C0h]
  unsigned int v14; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  sourceString = 0;
  *(_QWORD *)length = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  *(_QWORD *)length = -1;
  v13 = -1;
  if ( (int)GetMRTFilePath(
              (const unsigned __int16 *)this,
              a2,
              (unsigned __int16 **)&sourceString,
              (enum LS_IMAGE_QUALIFIERS *)&v15,
              &v14) >= 0
    || (FilePathNoMRTProtocol = GetFilePathNoMRTProtocol(a2, pszPath, v8), FilePathNoMRTProtocol >= 0)
    && (!PathIsRelativeW(pszPath)
     || (Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString),
         *(_QWORD *)length = -1,
         v13 = -1,
         FilePathNoMRTProtocol = CombinePaths(a3, pszPath, (unsigned __int16 **)&sourceString),
         FilePathNoMRTProtocol >= 0)) )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
    FilePathNoMRTProtocol = WindowsCreateString(sourceString, length[0], string);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  return (unsigned int)FilePathNoMRTProtocol;
}

```

## disassembly

```asm
0x180052848  push    rbp
0x18005284a  push    rbx
0x18005284b  push    rsi
0x18005284c  push    rdi
0x18005284d  push    r12
0x18005284f  push    r14
0x180052851  lea     rbp, [rsp-178h]
0x180052859  sub     rsp, 278h
0x180052860  mov     rax, cs:__security_cookie
0x180052867  xor     rax, rsp
0x18005286a  mov     [rbp+1A0h+var_40], rax
0x180052871  mov     rsi, r9
0x180052874  mov     r14, r8
0x180052877  mov     rdi, rdx
0x18005287a  mov     rbx, rcx
0x18005287d  mov     [rsp+2A0h+sourceString], 0
0x180052886  mov     qword ptr [rsp+2A0h+length], 0
0x18005288f  mov     [rsp+2A0h+var_260], 0
0x180052898  mov     [rsp+2A0h+var_254], 0
0x1800528a0  mov     [rsp+2A0h+var_258], 0
0x1800528a8  lea     rcx, [rsp+2A0h+sourceString]
0x1800528ad  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800528b2  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800528b6  mov     qword ptr [rsp+2A0h+length], r12
0x1800528bb  mov     [rsp+2A0h+var_260], r12
0x1800528c0  lea     rax, [rsp+2A0h+var_258]
0x1800528c5  mov     [rsp+2A0h+var_280], rax; unsigned int *
0x1800528ca  lea     r9, [rsp+2A0h+var_254]; enum LS_IMAGE_QUALIFIERS *
0x1800528cf  lea     r8, [rsp+2A0h+sourceString]; unsigned __int16 **
0x1800528d4  mov     rdx, rdi; unsigned __int16 *
0x1800528d7  mov     rcx, rbx; unsigned __int16 *
0x1800528da  call    ?GetMRTFilePath@@YAJPEBG0PEAPEAGPEAW4LS_IMAGE_QUALIFIERS@@PEAK@Z; GetMRTFilePath(ushort const *,ushort const *,ushort * *,LS_IMAGE_QUALIFIERS *,ulong *)
0x1800528df  test    eax, eax
0x1800528e1  jns     short loc_180052931
0x1800528e3  lea     rdx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x1800528e8  mov     rcx, rdi; unsigned __int16 *
0x1800528eb  call    ?GetFilePathNoMRTProtocol@@YAJPEBGPEAGI@Z; GetFilePathNoMRTProtocol(ushort const *,ushort *,uint)
0x1800528f0  mov     ebx, eax
0x1800528f2  test    eax, eax
0x1800528f4  js      short loc_18005294F
0x1800528f6  lea     rcx, [rsp+2A0h+pszPath]; pszPath
0x1800528fb  call    cs:__imp_PathIsRelativeW
0x180052901  test    eax, eax
0x180052903  jz      short loc_180052931
0x180052905  lea     rcx, [rsp+2A0h+sourceString]
0x18005290a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005290f  mov     qword ptr [rsp+2A0h+length], r12
0x180052914  mov     [rsp+2A0h+var_260], r12
0x180052919  lea     r8, [rsp+2A0h+sourceString]; unsigned __int16 **
0x18005291e  lea     rdx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x180052923  mov     rcx, r14; unsigned __int16 *
0x180052926  call    ?CombinePaths@@YAJPEBG0PEAPEAG@Z; CombinePaths(ushort const *,ushort const *,ushort * *)
0x18005292b  mov     ebx, eax
0x18005292d  test    eax, eax
0x18005292f  js      short loc_18005294F
0x180052931  lea     rcx, [rsp+2A0h+sourceString]
0x180052936  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18005293b  mov     r8, rsi; string
0x18005293e  mov     edx, [rsp+2A0h+length]; length
0x180052942  mov     rcx, [rsp+2A0h+sourceString]; sourceString
0x180052947  call    cs:__imp_WindowsCreateString
0x18005294d  mov     ebx, eax
0x18005294f  lea     rcx, [rsp+2A0h+sourceString]
0x180052954  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180052959  mov     eax, ebx
0x18005295b  mov     rcx, [rbp+1A0h+var_40]
0x180052962  xor     rcx, rsp; StackCookie
0x180052965  call    __security_check_cookie
0x18005296a  add     rsp, 278h
0x180052971  pop     r14
0x180052973  pop     r12
0x180052975  pop     rdi
0x180052976  pop     rsi
0x180052977  pop     rbx
0x180052978  pop     rbp
0x180052979  retn
```
