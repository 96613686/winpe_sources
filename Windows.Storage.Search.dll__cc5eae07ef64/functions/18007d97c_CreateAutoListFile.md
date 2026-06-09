# CreateAutoListFile

- ea: `0x18007d97c`
- end: `0x18007daa9`
- name: `CreateAutoListFile`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180078640`
- `0x18007dcf0`

## callees

- `0x180071dc0`
- `0x18007d97c`
- `0x1800c374c`
- `0x1800ea010`

## import_xrefs

- `SHCORE!SHCreateStreamOnFileEx` at `0x18007da2a`
- `SHCORE!SHCreateStreamOnFileEx` at `0x18007da2a`
- `Windows.Storage!SHGetFolderPathEx` at `0x18007d9bd`
- `Windows.Storage!SHGetFolderPathEx` at `0x18007d9bd`
- `Windows.Storage!SHSetLocalizedName` at `0x18007da83`
- `Windows.Storage!SHSetLocalizedName` at `0x18007da83`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18007d9d5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18007d9d5`

## string_xrefs

- `0x18007da77`: `searchfolder.dll`

## pseudocode

```c
__int64 __fastcall CreateAutoListFile(
        unsigned __int16 a1,
        const WCHAR *a2,
        int a3,
        __int64 a4,
        int a5,
        DWORD dwAttributes)
{
  HRESULT v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // r8
  IStream *ppstm; // [rsp+30h] [rbp-258h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-248h] BYREF

  v9 = SHGetFolderPathEx(a4, 0x8000, 0, pszPath, 260);
  if ( v9 >= 0 )
  {
    if ( PathAppendW(pszPath, a2) )
    {
      ppstm = 0;
      v9 = SHCreateStreamOnFileEx(pszPath, a5 != 0 ? 4097 : 1, dwAttributes, 1, 0, &ppstm);
      if ( v9 >= 0 )
      {
        v9 = WriteModuleResourceToStream(v10, a1, v11, ppstm);
        if ( v9 >= 0 )
          (*(void (__fastcall **)(IStream *, __int64))(*(_QWORD *)ppstm + 64LL))(ppstm, 4);
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        if ( v9 >= 0 )
          return (unsigned int)SHSetLocalizedName(pszPath, L"searchfolder.dll", a3);
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007d97c  push    rbx
0x18007d97e  push    rbp
0x18007d97f  push    rsi
0x18007d980  push    rdi
0x18007d981  sub     rsp, 268h
0x18007d988  mov     rax, cs:__security_cookie
0x18007d98f  xor     rax, rsp
0x18007d992  mov     [rsp+288h+var_38], rax
0x18007d99a  mov     rax, r9
0x18007d99d  mov     esi, ecx
0x18007d99f  mov     ebp, r8d
0x18007d9a2  mov     dword ptr [rsp+288h+pstmTemplate], 104h
0x18007d9aa  mov     rdi, rdx
0x18007d9ad  lea     r9, [rsp+288h+pszPath]
0x18007d9b2  mov     rcx, rax
0x18007d9b5  xor     r8d, r8d
0x18007d9b8  mov     edx, 8000h
0x18007d9bd  call    cs:__imp_SHGetFolderPathEx
0x18007d9c3  mov     ebx, eax
0x18007d9c5  test    eax, eax
0x18007d9c7  js      loc_18007DA8B
0x18007d9cd  mov     rdx, rdi; pszMore
0x18007d9d0  lea     rcx, [rsp+288h+pszPath]; pszPath
0x18007d9d5  call    cs:__imp_PathAppendW
0x18007d9db  test    eax, eax
0x18007d9dd  jnz     short loc_18007D9E9
0x18007d9df  mov     ebx, 80004005h
0x18007d9e4  jmp     loc_18007DA8B
0x18007d9e9  neg     [rsp+288h+arg_20]
0x18007d9f0  lea     rax, [rsp+288h+var_258]
0x18007d9f5  mov     r8d, [rsp+288h+dwAttributes]; dwAttributes
0x18007d9fd  lea     rcx, [rsp+288h+pszPath]; pszFile
0x18007da02  sbb     edx, edx
0x18007da04  mov     [rsp+288h+ppstm], rax; ppstm
0x18007da09  and     edx, 1000h
0x18007da0f  mov     [rsp+288h+var_258], 0
0x18007da18  mov     r9d, 1; fCreate
0x18007da1e  mov     [rsp+288h+pstmTemplate], 0; pstmTemplate
0x18007da27  add     edx, r9d; grfMode
0x18007da2a  call    cs:__imp_SHCreateStreamOnFileEx
0x18007da30  mov     ebx, eax
0x18007da32  test    eax, eax
0x18007da34  js      short loc_18007DA8B
0x18007da36  mov     r9, [rsp+288h+var_258]
0x18007da3b  movzx   edx, si
0x18007da3e  call    WriteModuleResourceToStream
0x18007da43  mov     ebx, eax
0x18007da45  test    eax, eax
0x18007da47  js      short loc_18007DA5F
0x18007da49  mov     rcx, [rsp+288h+var_258]
0x18007da4e  mov     edx, 4
0x18007da53  mov     rax, [rcx]
0x18007da56  mov     rax, [rax+40h]
0x18007da5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da5f  mov     rcx, [rsp+288h+var_258]
0x18007da64  mov     rax, [rcx]
0x18007da67  mov     rax, [rax+10h]
0x18007da6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da70  test    ebx, ebx
0x18007da72  js      short loc_18007DA8B
0x18007da74  mov     r8d, ebp; idsRes
0x18007da77  lea     rdx, pszResModule; "searchfolder.dll"
0x18007da7e  lea     rcx, [rsp+288h+pszPath]; pszPath
0x18007da83  call    cs:__imp_SHSetLocalizedName
0x18007da89  mov     ebx, eax
0x18007da8b  mov     eax, ebx
0x18007da8d  mov     rcx, [rsp+288h+var_38]
0x18007da95  xor     rcx, rsp; StackCookie
0x18007da98  call    __security_check_cookie
0x18007da9d  add     rsp, 268h
0x18007daa4  pop     rdi
0x18007daa5  pop     rsi
0x18007daa6  pop     rbp
0x18007daa7  pop     rbx
0x18007daa8  retn
```
