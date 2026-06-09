# CGenerateComment::`scalar deleting destructor'(uint)

- ea: `0x14000b980`
- end: `0x14000b9c0`
- name: `??_GCGenerateComment@@UEAAPEAXI@Z`
- size: `64`
- prototype: `BSTR *__fastcall(BSTR *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b980`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000b9ac`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000b9ac`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b99d`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b99d`

## pseudocode

```c
BSTR *__fastcall CGenerateComment::`scalar deleting destructor'(BSTR *this, char a2)
{
  *this = (BSTR)&CGenerateComment::`vftable';
  SysFreeString(this[1]);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x14000b980  mov     [rsp+arg_0], rbx
0x14000b985  push    rdi
0x14000b986  sub     rsp, 20h
0x14000b98a  mov     ebx, edx
0x14000b98c  mov     rdi, rcx
0x14000b98f  lea     rax, ??_7CGenerateComment@@6B@; const CGenerateComment::`vftable'
0x14000b996  mov     [rcx], rax
0x14000b999  mov     rcx, [rcx+8]; bstrString
0x14000b99d  call    cs:__imp_SysFreeString
0x14000b9a3  nop
0x14000b9a4  test    bl, 1
0x14000b9a7  jz      short loc_14000B9B2
0x14000b9a9  mov     rcx, rdi
0x14000b9ac  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14000b9b2  mov     rax, rdi
0x14000b9b5  mov     rbx, [rsp+28h+arg_0]
0x14000b9ba  add     rsp, 20h
0x14000b9be  pop     rdi
0x14000b9bf  retn
```
