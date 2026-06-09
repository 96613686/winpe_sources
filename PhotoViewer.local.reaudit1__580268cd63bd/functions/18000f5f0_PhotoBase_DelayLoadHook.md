# PhotoBase_DelayLoadHook

- ea: `0x18000f5f0`
- end: `0x18000f6b9`
- name: `PhotoBase_DelayLoadHook`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18000f070`

## callees

- `0x18000f5f0`
- `0x18000f780`
- `0x18003f800`
- `0x180040264`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000f669`
- `KERNEL32!GetModuleFileNameW` at `0x18000f669`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000f67f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18000f67f`
- `SHLWAPI!PathAppendW` at `0x18000f691`
- `SHLWAPI!PathAppendW` at `0x18000f691`
- `SHLWAPI!__imp_StrCmpICA` at `0x18000f636`
- `SHLWAPI!__imp_StrCmpICA` at `0x18000f636`

## string_xrefs

- `0x18000f62f`: `PhotoBase.dll`
- `0x18000f685`: `PhotoBase.dll`

## pseudocode

```c
__int64 __fastcall PhotoBase_DelayLoadHook(int a1, __int64 a2)
{
  signed int ModuleFileNameW; // eax
  WCHAR Filename; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v5[526]; // [rsp+22h] [rbp-226h] BYREF

  if ( a1 != 1 )
    return 0;
  if ( StrCmpICA(*(LPCSTR *)(a2 + 24), "PhotoBase.dll") )
    return 0;
  Filename = 0;
  memset_0(v5, 0, 0x206u);
  ModuleFileNameW = GetModuleFileNameW(&_ImageBase, &Filename, 0x104u);
  if ( ModuleFileNameW <= 0 || (unsigned int)ModuleFileNameW >= 0x104 )
    return 0;
  PathRemoveFileSpecW(&Filename);
  PathAppendW(&Filename, L"PhotoBase.dll");
  return IsolationAwareLoadLibraryW(&Filename);
}

```

## disassembly

```asm
0x18000f5f0  sub     rsp, 248h
0x18000f5f7  mov     rax, cs:__security_cookie
0x18000f5fe  xor     rax, rsp
0x18000f601  mov     [rsp+248h+var_18], rax
0x18000f609  mov     rax, rdx
0x18000f60c  cmp     ecx, 1
0x18000f60f  jz      short loc_18000F62B
0x18000f611  xor     eax, eax
0x18000f613  mov     rcx, [rsp+248h+var_18]
0x18000f61b  xor     rcx, rsp; StackCookie
0x18000f61e  call    __security_check_cookie
0x18000f623  add     rsp, 248h
0x18000f62a  retn
0x18000f62b  mov     rcx, [rax+18h]; pszStr1
0x18000f62f  lea     rdx, pszStr2; "PhotoBase.dll"
0x18000f636  call    cs:__imp_StrCmpICA
0x18000f63c  test    eax, eax
0x18000f63e  jnz     short loc_18000F611
0x18000f640  xor     edx, edx; Val
0x18000f642  mov     [rsp+248h+Filename], ax
0x18000f647  mov     r8d, 206h; Size
0x18000f64d  lea     rcx, [rsp+248h+var_226]; void *
0x18000f652  call    memset_0
0x18000f657  mov     r8d, 104h; nSize
0x18000f65d  lea     rdx, [rsp+248h+Filename]; lpFilename
0x18000f662  lea     rcx, __ImageBase; hModule
0x18000f669  call    cs:__imp_GetModuleFileNameW
0x18000f66f  test    eax, eax
0x18000f671  jle     short loc_18000F611
0x18000f673  cmp     eax, 104h
0x18000f678  jnb     short loc_18000F611
0x18000f67a  lea     rcx, [rsp+248h+Filename]; pszPath
0x18000f67f  call    cs:__imp_PathRemoveFileSpecW
0x18000f685  lea     rdx, tstrFilename; "PhotoBase.dll"
0x18000f68c  lea     rcx, [rsp+248h+Filename]; pszPath
0x18000f691  call    cs:__imp_PathAppendW
0x18000f697  lea     rcx, [rsp+248h+Filename]; lpLibFileName
0x18000f69c  call    IsolationAwareLoadLibraryW
0x18000f6a1  mov     rcx, [rsp+248h+var_18]
0x18000f6a9  xor     rcx, rsp; StackCookie
0x18000f6ac  call    __security_check_cookie
0x18000f6b1  add     rsp, 248h
0x18000f6b8  retn
```
