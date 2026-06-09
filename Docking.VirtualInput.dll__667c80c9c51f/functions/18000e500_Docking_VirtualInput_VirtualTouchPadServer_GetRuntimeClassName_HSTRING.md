# Docking::VirtualInput::VirtualTouchPadServer::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000e500`
- end: `0x18000e581`
- name: `?GetRuntimeClassName@VirtualTouchPadServer@VirtualInput@Docking@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(Docking::VirtualInput::VirtualTouchPadServer *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e590`

## callees

- `0x18000e500`
- `0x18000edc8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000e56e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000e56e`

## pseudocode

```c
__int64 __fastcall Docking::VirtualInput::VirtualTouchPadServer::GetRuntimeClassName(
        Docking::VirtualInput::VirtualTouchPadServer *this,
        HSTRING *a2)
{
  unsigned int v3; // [rsp+20h] [rbp-28h]
  __int64 length; // [rsp+28h] [rbp-20h]
  const WCHAR *sourceString; // [rsp+30h] [rbp-18h]

  *a2 = 0;
  v3 = 0;
  sourceString = Docking::VirtualInput::VirtualTouchPadServer::InternalGetRuntimeClassName();
  if ( sourceString )
  {
    length = -1;
    do
      ++length;
    while ( sourceString[length] );
    return (unsigned int)WindowsCreateString(sourceString, length, a2);
  }
  return v3;
}

```

## disassembly

```asm
0x18000e500  mov     [rsp+string], rdx
0x18000e505  mov     [rsp+arg_0], rcx
0x18000e50a  sub     rsp, 48h
0x18000e50e  mov     rax, [rsp+48h+string]
0x18000e513  mov     qword ptr [rax], 0
0x18000e51a  mov     [rsp+48h+var_28], 0
0x18000e522  call    ?InternalGetRuntimeClassName@VirtualTouchPadServer@VirtualInput@Docking@@SAPEBGXZ; Docking::VirtualInput::VirtualTouchPadServer::InternalGetRuntimeClassName(void)
0x18000e527  mov     [rsp+48h+sourceString], rax
0x18000e52c  cmp     [rsp+48h+sourceString], 0
0x18000e532  jz      short loc_18000E578
0x18000e534  mov     rax, [rsp+48h+sourceString]
0x18000e539  mov     [rsp+48h+var_10], rax
0x18000e53e  mov     qword ptr [rsp+48h+length], 0FFFFFFFFFFFFFFFFh
0x18000e547  inc     qword ptr [rsp+48h+length]
0x18000e54c  mov     rax, [rsp+48h+var_10]
0x18000e551  mov     rcx, qword ptr [rsp+48h+length]
0x18000e556  cmp     word ptr [rax+rcx*2], 0
0x18000e55b  jnz     short loc_18000E547
0x18000e55d  mov     rax, qword ptr [rsp+48h+length]
0x18000e562  mov     r8, [rsp+48h+string]; string
0x18000e567  mov     edx, eax; length
0x18000e569  mov     rcx, [rsp+48h+sourceString]; sourceString
0x18000e56e  call    cs:__imp_WindowsCreateString
0x18000e574  mov     [rsp+48h+var_28], eax
0x18000e578  mov     eax, [rsp+48h+var_28]
0x18000e57c  add     rsp, 48h
0x18000e580  retn
```
