# DllRegisterServer

- ea: `0x1800031d0`
- end: `0x180003267`
- name: `DllRegisterServer`
- size: `151`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800031d0`
- `0x18001082c`
- `0x180011840`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800031fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800031fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003207`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  const WCHAR *i; // rbx
  WCHAR Filename[512]; // [rsp+20h] [rbp-418h] BYREF

  if ( GetModuleFileNameW(g_hModule, Filename, 0x200u) )
  {
    for ( i = (const WCHAR *)off_1800194E0; i != (const WCHAR *)&off_1800194E0; i = *(const WCHAR **)i )
    {
      result = ClassFactory::RegisterCoClass(
                 *((const WCHAR **)i + 1),
                 *((BYTE **)i + 1),
                 (BYTE *)Filename,
                 *((UUID **)i + 2));
      if ( result < 0 )
        return result;
    }
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800031d0  push    rbx
0x1800031d2  sub     rsp, 430h
0x1800031d9  mov     rax, cs:__security_cookie
0x1800031e0  xor     rax, rsp
0x1800031e3  mov     [rsp+438h+var_18], rax
0x1800031eb  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x1800031f2  lea     rdx, [rsp+438h+Filename]; lpFilename
0x1800031f7  mov     r8d, 200h; nSize
0x1800031fd  call    cs:__imp_GetModuleFileNameW
0x180003203  test    eax, eax
0x180003205  jnz     short loc_18000321B
0x180003207  call    cs:__imp_GetLastError
0x18000320d  test    eax, eax
0x18000320f  jle     short loc_18000324E
0x180003211  movzx   eax, ax
0x180003214  or      eax, 80070000h
0x180003219  jmp     short loc_18000324E
0x18000321b  mov     rbx, cs:off_1800194E0
0x180003222  lea     rax, off_1800194E0
0x180003229  cmp     rbx, rax
0x18000322c  jz      short loc_18000324C
0x18000322e  mov     rcx, [rbx+8]; lpData
0x180003232  lea     r8, [rsp+438h+Filename]; BYTE *
0x180003237  mov     r9, [rbx+10h]; Uuid
0x18000323b  mov     rdx, rcx; BYTE *
0x18000323e  call    ?RegisterCoClass@ClassFactory@@CAJPEBG00PEBU_GUID@@@Z; ClassFactory::RegisterCoClass(ushort const *,ushort const *,ushort const *,_GUID const *)
0x180003243  test    eax, eax
0x180003245  js      short loc_18000324E
0x180003247  mov     rbx, [rbx]
0x18000324a  jmp     short loc_180003222
0x18000324c  xor     eax, eax
0x18000324e  mov     rcx, [rsp+438h+var_18]
0x180003256  xor     rcx, rsp; StackCookie
0x180003259  call    __security_check_cookie
0x18000325e  add     rsp, 430h
0x180003265  pop     rbx
0x180003266  retn
```
