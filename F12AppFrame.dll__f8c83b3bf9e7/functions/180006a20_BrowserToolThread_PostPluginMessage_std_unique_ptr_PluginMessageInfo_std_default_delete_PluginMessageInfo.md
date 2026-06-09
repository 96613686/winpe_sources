# BrowserToolThread::PostPluginMessage(std::unique_ptr<PluginMessageInfo,std::default_delete<PluginMessageInfo>> &&)

- ea: `0x180006a20`
- end: `0x180006abc`
- name: `?PostPluginMessage@BrowserToolThread@@QEBAJ$$QEAV?$unique_ptr@UPluginMessageInfo@@U?$default_delete@UPluginMessageInfo@@@std@@@std@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `23`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001ec50`
- `0x1800227a0`
- `0x180023020`
- `0x180024b9c`
- `0x18002670c`
- `0x1800269a4`
- `0x180028d38`
- `0x18002a070`
- `0x18002a190`
- `0x18002a270`
- `0x18002a350`
- `0x18002a430`
- `0x18002a530`
- `0x18002a710`
- `0x18002a810`
- `0x18002a900`
- `0x18002aad0`
- `0x18002abb0`
- `0x18002ac90`
- `0x18002ad70`
- `0x18002aff0`
- `0x18002b0e0`
- `0x18002b1c0`

## callees

- `0x180005e44`
- `0x180006a20`
- `0x180035010`

## import_xrefs

- `USER32!PostMessageW` at `0x180006a6e`
- `USER32!PostMessageW` at `0x180006a6e`

## pseudocode

```c
__int64 __fastcall BrowserToolThread::PostPluginMessage(__int64 a1, LPARAM *a2)
{
  LPARAM v4; // rsi
  signed int Error; // eax
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  int v7; // ebx

  if ( FrameWindow::s_isDestroying && (*(_DWORD *)(*a2 + 8) & 0xFFFFFFF7) != 0 )
    return 0;
  if ( !*(_QWORD *)(a1 + 24) )
    return 2147947423LL;
  v4 = *a2;
  *a2 = 0;
  if ( PostMessageW(*(HWND *)(a1 + 24), 0x79Bu, 0, v4) )
    return 0;
  Error = ATL::AtlHresultFromLastError();
  v6 = (void (__fastcall ***)(_QWORD, __int64))*a2;
  v7 = Error;
  *a2 = v4;
  if ( v6 )
    (**v6)(v6, 1);
  if ( !v7 )
    return 0;
  if ( v7 >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006a20  mov     [rsp+arg_0], rbx
0x180006a25  mov     [rsp+arg_8], rsi
0x180006a2a  push    rdi
0x180006a2b  sub     rsp, 20h
0x180006a2f  cmp     cs:?s_isDestroying@FrameWindow@@2_NA, 0; bool FrameWindow::s_isDestroying
0x180006a36  mov     rdi, rdx
0x180006a39  jz      short loc_180006A47
0x180006a3b  mov     rax, [rdx]
0x180006a3e  test    dword ptr [rax+8], 0FFFFFFF7h
0x180006a45  jnz     short loc_180006AAA
0x180006a47  cmp     qword ptr [rcx+18h], 0
0x180006a4c  jnz     short loc_180006A55
0x180006a4e  mov     eax, 8007139Fh
0x180006a53  jmp     short loc_180006AAC
0x180006a55  mov     rsi, [rdx]
0x180006a58  xor     r8d, r8d; wParam
0x180006a5b  mov     qword ptr [rdx], 0
0x180006a62  mov     r9, rsi; lParam
0x180006a65  mov     rcx, [rcx+18h]; hWnd
0x180006a69  mov     edx, 79Bh; Msg
0x180006a6e  call    cs:__imp_PostMessageW
0x180006a74  test    eax, eax
0x180006a76  jnz     short loc_180006AAA
0x180006a78  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006a7d  mov     rcx, [rdi]
0x180006a80  mov     ebx, eax
0x180006a82  mov     [rdi], rsi
0x180006a85  test    rcx, rcx
0x180006a88  jz      short loc_180006A9A
0x180006a8a  mov     rdx, [rcx]
0x180006a8d  mov     rax, [rdx]
0x180006a90  mov     edx, 1
0x180006a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9a  test    ebx, ebx
0x180006a9c  jz      short loc_180006AAA
0x180006a9e  mov     eax, 80004005h
0x180006aa3  cmovns  ebx, eax
0x180006aa6  mov     eax, ebx
0x180006aa8  jmp     short loc_180006AAC
0x180006aaa  xor     eax, eax
0x180006aac  mov     rbx, [rsp+28h+arg_0]
0x180006ab1  mov     rsi, [rsp+28h+arg_8]
0x180006ab6  add     rsp, 20h
0x180006aba  pop     rdi
0x180006abb  retn
```
