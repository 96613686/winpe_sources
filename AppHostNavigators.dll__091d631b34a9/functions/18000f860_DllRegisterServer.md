# DllRegisterServer

- ea: `0x18000f860`
- end: `0x18000f90a`
- name: `DllRegisterServer`
- size: `170`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000f3cc`
- `0x18000f860`
- `0x1800120ac`
- `0x1800130a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f897`
- `KERNEL32!GetLastError` at `0x18000f897`
- `KERNEL32!GetModuleFileNameW` at `0x18000f88d`
- `KERNEL32!GetModuleFileNameW` at `0x18000f88d`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const unsigned __int16 *v0; // rdx
  HRESULT result; // eax
  const WCHAR *i; // rbx
  HRESULT v3; // eax
  HRESULT v4; // ecx
  WCHAR Filename[512]; // [rsp+20h] [rbp-418h] BYREF

  if ( GetModuleFileNameW(g_hModule, Filename, 0x200u) )
  {
    for ( i = (const WCHAR *)off_18001C1F8; i != (const WCHAR *)&off_18001C1F8; i = *(const WCHAR **)i )
    {
      result = ClassFactory::RegisterCoClass(
                 *((const WCHAR **)i + 1),
                 *((BYTE **)i + 1),
                 (BYTE *)Filename,
                 *((UUID **)i + 2));
      if ( result < 0 )
        return result;
    }
    v3 = ATL::AtlRegisterTypeLib(off_18001C228, v0);
    v4 = 0;
    if ( v3 < 0 )
      return v3;
    return v4;
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
0x18000f860  push    rbx
0x18000f862  sub     rsp, 430h
0x18000f869  mov     rax, cs:__security_cookie
0x18000f870  xor     rax, rsp
0x18000f873  mov     [rsp+438h+var_18], rax
0x18000f87b  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x18000f882  lea     rdx, [rsp+438h+Filename]; lpFilename
0x18000f887  mov     r8d, 200h; nSize
0x18000f88d  call    cs:__imp_GetModuleFileNameW
0x18000f893  test    eax, eax
0x18000f895  jnz     short loc_18000F8AB
0x18000f897  call    cs:__imp_GetLastError
0x18000f89d  test    eax, eax
0x18000f89f  jle     short loc_18000F8F1
0x18000f8a1  movzx   eax, ax
0x18000f8a4  or      eax, 80070000h
0x18000f8a9  jmp     short loc_18000F8F1
0x18000f8ab  mov     rbx, cs:off_18001C1F8
0x18000f8b2  lea     rax, off_18001C1F8
0x18000f8b9  cmp     rbx, rax
0x18000f8bc  jz      short loc_18000F8DC
0x18000f8be  mov     rcx, [rbx+8]; lpData
0x18000f8c2  lea     r8, [rsp+438h+Filename]; BYTE *
0x18000f8c7  mov     r9, [rbx+10h]; Uuid
0x18000f8cb  mov     rdx, rcx; BYTE *
0x18000f8ce  call    ?RegisterCoClass@ClassFactory@@CAJPEBG00PEBU_GUID@@@Z; ClassFactory::RegisterCoClass(ushort const *,ushort const *,ushort const *,_GUID const *)
0x18000f8d3  test    eax, eax
0x18000f8d5  js      short loc_18000F8F1
0x18000f8d7  mov     rbx, [rbx]
0x18000f8da  jmp     short loc_18000F8B2
0x18000f8dc  mov     rcx, cs:off_18001C228; HINSTANCE
0x18000f8e3  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x18000f8e8  xor     ecx, ecx
0x18000f8ea  test    eax, eax
0x18000f8ec  cmovs   ecx, eax
0x18000f8ef  mov     eax, ecx
0x18000f8f1  mov     rcx, [rsp+438h+var_18]
0x18000f8f9  xor     rcx, rsp; StackCookie
0x18000f8fc  call    __security_check_cookie
0x18000f901  add     rsp, 430h
0x18000f908  pop     rbx
0x18000f909  retn
```
