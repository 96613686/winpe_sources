# GetSystemDirectoryInMString(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001bed0`
- end: `0x18001bf24`
- name: `?GetSystemDirectoryInMString@@YAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001cc8c`
- `0x1800209a8`

## callees

- `0x1800035cc`
- `0x180004198`
- `0x18001bed0`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x18001bef5`
- `SHELL32!SHGetFolderPathW` at `0x18001bef5`

## pseudocode

```c
__int64 __fastcall GetSystemDirectoryInMString(__int64 a1)
{
  HRESULT v2; // edi

  v2 = SHGetFolderPathW(0, 37, 0, 0, *(LPWSTR *)(*(_QWORD *)a1 + 24LL));
  if ( v2 >= 0 )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(a1);
  else
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001bed0  mov     [rsp+arg_0], rbx
0x18001bed5  push    rdi
0x18001bed6  sub     rsp, 30h
0x18001beda  mov     rax, [rcx]
0x18001bedd  xor     r9d, r9d; dwFlags
0x18001bee0  mov     rbx, rcx
0x18001bee3  xor     r8d, r8d; hToken
0x18001bee6  xor     ecx, ecx; hwnd
0x18001bee8  mov     rdx, [rax+18h]
0x18001beec  mov     [rsp+38h+pszPath], rdx; pszPath
0x18001bef1  lea     edx, [r9+25h]; csidl
0x18001bef5  call    cs:__imp_SHGetFolderPathW
0x18001befc  nop     dword ptr [rax+rax+00h]
0x18001bf01  mov     edi, eax
0x18001bf03  mov     rcx, rbx
0x18001bf06  test    eax, eax
0x18001bf08  jns     short loc_18001BF11
0x18001bf0a  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18001bf0f  jmp     short loc_18001BF16
0x18001bf11  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(void)
0x18001bf16  mov     rbx, [rsp+38h+arg_0]
0x18001bf1b  mov     eax, edi
0x18001bf1d  add     rsp, 30h
0x18001bf21  pop     rdi
0x18001bf22  retn
```
