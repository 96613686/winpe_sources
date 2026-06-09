# CRemoveDeviceContextHandler::GetToolTip(IShellItemArray *,ushort * *)

- ea: `0x180008190`
- end: `0x18000820b`
- name: `?GetToolTip@CRemoveDeviceContextHandler@@UEAAJPEAUIShellItemArray@@PEAPEAG@Z`
- size: `123`
- prototype: `int(CRemoveDeviceContextHandler *__hidden this, struct IShellItemArray *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008190`
- `0x18000c990`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x1800081e0`
- `SHLWAPI!SHStrDupW` at `0x1800081e0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800081ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800081ce`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceContextHandler::GetToolTip(
        CRemoveDeviceContextHandler *this,
        struct IShellItemArray *a2,
        unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  v4 = -2147467259;
  if ( LoadStringW(g_hinst, 0x3EAu, Buffer, 260) )
    return (unsigned int)SHStrDupW(Buffer, a3);
  return v4;
}

```

## disassembly

```asm
0x180008190  mov     [rsp+arg_0], rbx
0x180008195  push    rdi
0x180008196  sub     rsp, 240h
0x18000819d  mov     rax, cs:__security_cookie
0x1800081a4  xor     rax, rsp
0x1800081a7  mov     [rsp+248h+var_18], rax
0x1800081af  mov     rcx, cs:g_hinst; hInstance
0x1800081b6  mov     rdi, r8
0x1800081b9  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x1800081be  mov     r9d, 104h; cchBufferMax
0x1800081c4  mov     edx, 3EAh; uID
0x1800081c9  mov     ebx, 80004005h
0x1800081ce  call    cs:__imp_LoadStringW
0x1800081d4  test    eax, eax
0x1800081d6  jz      short loc_1800081E8
0x1800081d8  mov     rdx, rdi; ppwsz
0x1800081db  lea     rcx, [rsp+248h+Buffer]; psz
0x1800081e0  call    cs:__imp_SHStrDupW
0x1800081e6  mov     ebx, eax
0x1800081e8  mov     eax, ebx
0x1800081ea  mov     rcx, [rsp+248h+var_18]
0x1800081f2  xor     rcx, rsp; StackCookie
0x1800081f5  call    __security_check_cookie
0x1800081fa  mov     rbx, [rsp+248h+arg_0]
0x180008202  add     rsp, 240h
0x180008209  pop     rdi
0x18000820a  retn
```
