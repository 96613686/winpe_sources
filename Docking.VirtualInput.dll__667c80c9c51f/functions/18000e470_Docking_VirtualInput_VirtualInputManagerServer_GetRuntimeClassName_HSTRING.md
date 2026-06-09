# Docking::VirtualInput::VirtualInputManagerServer::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000e470`
- end: `0x18000e4f1`
- name: `?GetRuntimeClassName@VirtualInputManagerServer@VirtualInput@Docking@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(Docking::VirtualInput::VirtualInputManagerServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e470`
- `0x18000edb8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000e4de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000e4de`

## pseudocode

```c
__int64 __fastcall Docking::VirtualInput::VirtualInputManagerServer::GetRuntimeClassName(
        Docking::VirtualInput::VirtualInputManagerServer *this,
        HSTRING *a2)
{
  unsigned int v3; // [rsp+20h] [rbp-28h]
  __int64 length; // [rsp+28h] [rbp-20h]
  const WCHAR *sourceString; // [rsp+30h] [rbp-18h]

  *a2 = 0;
  v3 = 0;
  sourceString = Docking::VirtualInput::VirtualInputManagerServer::InternalGetRuntimeClassName();
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
0x18000e470  mov     [rsp+string], rdx
0x18000e475  mov     [rsp+arg_0], rcx
0x18000e47a  sub     rsp, 48h
0x18000e47e  mov     rax, [rsp+48h+string]
0x18000e483  mov     qword ptr [rax], 0
0x18000e48a  mov     [rsp+48h+var_28], 0
0x18000e492  call    ?InternalGetRuntimeClassName@VirtualInputManagerServer@VirtualInput@Docking@@SAPEBGXZ; Docking::VirtualInput::VirtualInputManagerServer::InternalGetRuntimeClassName(void)
0x18000e497  mov     [rsp+48h+sourceString], rax
0x18000e49c  cmp     [rsp+48h+sourceString], 0
0x18000e4a2  jz      short loc_18000E4E8
0x18000e4a4  mov     rax, [rsp+48h+sourceString]
0x18000e4a9  mov     [rsp+48h+var_10], rax
0x18000e4ae  mov     qword ptr [rsp+48h+length], 0FFFFFFFFFFFFFFFFh
0x18000e4b7  inc     qword ptr [rsp+48h+length]
0x18000e4bc  mov     rax, [rsp+48h+var_10]
0x18000e4c1  mov     rcx, qword ptr [rsp+48h+length]
0x18000e4c6  cmp     word ptr [rax+rcx*2], 0
0x18000e4cb  jnz     short loc_18000E4B7
0x18000e4cd  mov     rax, qword ptr [rsp+48h+length]
0x18000e4d2  mov     r8, [rsp+48h+string]; string
0x18000e4d7  mov     edx, eax; length
0x18000e4d9  mov     rcx, [rsp+48h+sourceString]; sourceString
0x18000e4de  call    cs:__imp_WindowsCreateString
0x18000e4e4  mov     [rsp+48h+var_28], eax
0x18000e4e8  mov     eax, [rsp+48h+var_28]
0x18000e4ec  add     rsp, 48h
0x18000e4f0  retn
```
