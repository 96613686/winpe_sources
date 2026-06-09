# CopyFileToTempDir(char const *,ushort * *)

- ea: `0x407eab`
- end: `0x407fce`
- name: `?CopyFileToTempDir@@YGJPBDPAPAG@Z`
- size: `291`
- prototype: `HRESULT __fastcall(const CHAR *, LPCWSTR *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x40373b`

## callees

- `0x402df9`
- `0x4066c4`
- `0x406d31`
- `0x4074cf`
- `0x407eab`
- `0x408301`
- `0x40ba47`
- `0x40cb60`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x407ef2`
- `KERNEL32!MultiByteToWideChar` at `0x407ef2`
- `KERNEL32!GetFileAttributesW` at `0x407f48`
- `KERNEL32!GetFileAttributesW` at `0x407f48`
- `KERNEL32!CopyFileW` at `0x407f80`
- `KERNEL32!CopyFileW` at `0x407f80`
- `OLEAUT32!__imp__SysAllocString@4` at `0x407fae`
- `OLEAUT32!__imp__SysAllocString@4` at `0x407fae`
- `OLEAUT32!__imp__SysFreeString@4` at `0x407fa1`
- `OLEAUT32!__imp__SysFreeString@4` at `0x407fa1`

## pseudocode

```c
HRESULT __fastcall CopyFileToTempDir(const CHAR *a1, LPCWSTR *a2)
{
  int v4; // esi
  int v6; // eax
  HRESULT v7; // esi
  const unsigned __int16 *v8; // [esp+0h] [ebp-424h]
  WCHAR *v9; // [esp+0h] [ebp-424h]
  const unsigned __int16 *v10; // [esp+0h] [ebp-424h]
  size_t v11; // [esp+4h] [ebp-420h]
  int v12; // [esp+4h] [ebp-420h]
  unsigned __int16 *FileNameFromPath; // [esp+Ch] [ebp-418h]
  WCHAR WideCharStr[260]; // [esp+10h] [ebp-414h] BYREF
  WCHAR FileName[260]; // [esp+218h] [ebp-20Ch] BYREF

  v4 = 1;
  FileNameFromPath = FindFileNameFromPath(v8);
  if ( FileNameFromPath != *a2 )
  {
    if ( !MultiByteToWideChar(0, 8u, a1, -1, WideCharStr, 260) )
      return HRESULTFromLastErrorError();
    while ( v4 <= 500 )
    {
      v6 = v4++;
      if ( StringCchPrintfW(FileName, 0x104u, (wchar_t *)L"%s\\[%d]%s", WideCharStr, v6, FileNameFromPath) < 0
        || GetFileAttributesW(FileName) == -1 )
      {
        v7 = PathCchRemoveExtension(v9, v11);
        if ( v7 >= 0 )
        {
          v7 = AxiPreScanPathW(FileName);
          if ( v7 >= 0 )
          {
            if ( !CopyFileW(*a2, FileName, 1) )
              return HRESULTFromLastErrorError();
            v7 = SetFileIntegrityLevelByNameW(v10, v12);
            if ( v7 >= 0 )
            {
              SysFreeString((BSTR)*a2);
              *a2 = SysAllocString(FileName);
            }
          }
        }
        return v7;
      }
    }
  }
  return -2147467259;
}

```

## disassembly

```asm
0x407eab  mov     edi, edi
0x407ead  push    ebp
0x407eae  mov     ebp, esp
0x407eb0  sub     esp, 418h
0x407eb6  mov     eax, ___security_cookie
0x407ebb  xor     eax, ebp
0x407ebd  mov     [ebp+var_4], eax
0x407ec0  push    ebx
0x407ec1  push    esi; int
0x407ec2  push    edi; unsigned __int16 *
0x407ec3  mov     edi, edx
0x407ec5  mov     ebx, ecx
0x407ec7  xor     esi, esi
0x407ec9  inc     esi
0x407eca  mov     ecx, [edi]
0x407ecc  call    ?FindFileNameFromPath@@YGPAGPBG@Z; FindFileNameFromPath(ushort const *)
0x407ed1  mov     [ebp+var_418], eax
0x407ed7  cmp     eax, [edi]
0x407ed9  jz      loc_407FBA
0x407edf  push    104h; cchWideChar
0x407ee4  lea     eax, [ebp+WideCharStr]
0x407eea  push    eax; lpWideCharStr
0x407eeb  push    0FFFFFFFFh; cbMultiByte
0x407eed  push    ebx; lpMultiByteStr
0x407eee  push    8; dwFlags
0x407ef0  push    0; CodePage
0x407ef2  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x407ef8  test    eax, eax
0x407efa  jnz     short loc_407F06
0x407efc  call    ?HRESULTFromLastErrorError@@YGJXZ; HRESULTFromLastErrorError(void)
0x407f01  jmp     loc_407FBF
0x407f06  mov     ebx, [ebp+var_418]
0x407f0c  cmp     esi, 1F4h
0x407f12  jg      loc_407FBA
0x407f18  push    ebx
0x407f19  mov     eax, esi
0x407f1b  inc     esi
0x407f1c  push    eax
0x407f1d  lea     eax, [ebp+WideCharStr]
0x407f23  push    eax
0x407f24  push    offset aSDS; "%s\\[%d]%s"
0x407f29  lea     eax, [ebp+FileName]
0x407f2f  push    104h; unsigned int
0x407f34  push    eax; Buffer
0x407f35  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x407f3a  add     esp, 18h
0x407f3d  test    eax, eax
0x407f3f  js      short loc_407F53
0x407f41  lea     eax, [ebp+FileName]
0x407f47  push    eax; lpFileName
0x407f48  call    ds:__imp__GetFileAttributesW@4; GetFileAttributesW(x)
0x407f4e  cmp     eax, 0FFFFFFFFh
0x407f51  jnz     short loc_407F0C
0x407f53  lea     ecx, [ebp+FileName]
0x407f59  call    _PathCchRemoveExtension@8; PathCchRemoveExtension(x,x)
0x407f5e  mov     esi, eax
0x407f60  test    esi, esi
0x407f62  js      short loc_407FB6
0x407f64  lea     ecx, [ebp+FileName]
0x407f6a  call    ?AxiPreScanPathW@@YGJPBG@Z; AxiPreScanPathW(ushort const *)
0x407f6f  mov     esi, eax
0x407f71  test    esi, esi
0x407f73  js      short loc_407FB6
0x407f75  push    1; bFailIfExists
0x407f77  lea     eax, [ebp+FileName]
0x407f7d  push    eax; lpNewFileName
0x407f7e  push    dword ptr [edi]; lpExistingFileName
0x407f80  call    ds:__imp__CopyFileW@12; CopyFileW(x,x,x)
0x407f86  test    eax, eax
0x407f88  jz      loc_407EFC
0x407f8e  lea     ecx, [ebp+FileName]
0x407f94  call    ?SetFileIntegrityLevelByNameW@@YGJPBGH@Z; SetFileIntegrityLevelByNameW(ushort const *,int)
0x407f99  mov     esi, eax
0x407f9b  test    esi, esi
0x407f9d  js      short loc_407FB6
0x407f9f  push    dword ptr [edi]; bstrString
0x407fa1  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x407fa7  lea     eax, [ebp+FileName]
0x407fad  push    eax; psz
0x407fae  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x407fb4  mov     [edi], eax
0x407fb6  mov     eax, esi
0x407fb8  jmp     short loc_407FBF
0x407fba  mov     eax, 80004005h
0x407fbf  mov     ecx, [ebp+var_4]
0x407fc2  pop     edi
0x407fc3  pop     esi
0x407fc4  xor     ecx, ebp; StackCookie
0x407fc6  pop     ebx
0x407fc7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x407fcc  leave
0x407fcd  retn
```
