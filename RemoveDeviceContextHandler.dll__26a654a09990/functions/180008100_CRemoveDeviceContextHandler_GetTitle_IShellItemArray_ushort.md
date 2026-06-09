# CRemoveDeviceContextHandler::GetTitle(IShellItemArray *,ushort * *)

- ea: `0x180008100`
- end: `0x18000817b`
- name: `?GetTitle@CRemoveDeviceContextHandler@@UEAAJPEAUIShellItemArray@@PEAPEAG@Z`
- size: `123`
- prototype: `__int64 __fastcall(CRemoveDeviceContextHandler *this, struct IShellItemArray *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008100`
- `0x18000c990`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180008150`
- `SHLWAPI!SHStrDupW` at `0x180008150`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000813e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000813e`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceContextHandler::GetTitle(
        CRemoveDeviceContextHandler *this,
        struct IShellItemArray *a2,
        unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  v4 = -2147467259;
  if ( LoadStringW(g_hinst, 0x3F0u, Buffer, 260) )
    return (unsigned int)SHStrDupW(Buffer, a3);
  return v4;
}

```

## disassembly

```asm
0x180008100  mov     [rsp+arg_0], rbx
0x180008105  push    rdi
0x180008106  sub     rsp, 240h
0x18000810d  mov     rax, cs:__security_cookie
0x180008114  xor     rax, rsp
0x180008117  mov     [rsp+248h+var_18], rax
0x18000811f  mov     rcx, cs:g_hinst; hInstance
0x180008126  mov     rdi, r8
0x180008129  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x18000812e  mov     r9d, 104h; cchBufferMax
0x180008134  mov     edx, 3F0h; uID
0x180008139  mov     ebx, 80004005h
0x18000813e  call    cs:__imp_LoadStringW
0x180008144  test    eax, eax
0x180008146  jz      short loc_180008158
0x180008148  mov     rdx, rdi; ppwsz
0x18000814b  lea     rcx, [rsp+248h+Buffer]; psz
0x180008150  call    cs:__imp_SHStrDupW
0x180008156  mov     ebx, eax
0x180008158  mov     eax, ebx
0x18000815a  mov     rcx, [rsp+248h+var_18]
0x180008162  xor     rcx, rsp; StackCookie
0x180008165  call    __security_check_cookie
0x18000816a  mov     rbx, [rsp+248h+arg_0]
0x180008172  add     rsp, 240h
0x180008179  pop     rdi
0x18000817a  retn
```
