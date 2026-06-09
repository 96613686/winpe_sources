# SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)

- ea: `0x18002a594`
- end: `0x18002a5f2`
- name: `?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *__hidden this, const unsigned __int16 *, HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ba90`
- `0x18002d08c`

## callees

- `0x1800171d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a5df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a5df`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::WindowsCreateString(const WCHAR *this, unsigned __int16 *a2, HSTRING *a3)
{
  const WCHAR *v4; // rax
  unsigned int v5; // ebx
  const WCHAR *v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  v4 = &word_180054D68;
  if ( this )
    v4 = this;
  v7 = v4;
  v5 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v8, &v7, a3);
  *(_QWORD *)a2 = v8;
  v8 = 0;
  WindowsDeleteString(0);
  return v5;
}

```

## disassembly

```asm
0x18002a594  mov     r11, rsp
0x18002a597  mov     [r11+18h], rbx
0x18002a59b  push    rdi
0x18002a59c  sub     rsp, 20h
0x18002a5a0  test    rcx, rcx
0x18002a5a3  mov     qword ptr [r11+10h], 0
0x18002a5ab  mov     rdi, rdx
0x18002a5ae  lea     rax, word_180054D68
0x18002a5b5  cmovnz  rax, rcx
0x18002a5b9  lea     rdx, [r11+8]
0x18002a5bd  lea     rcx, [r11+10h]
0x18002a5c1  mov     [r11+8], rax
0x18002a5c5  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002a5ca  mov     rcx, [rsp+28h+arg_8]
0x18002a5cf  mov     ebx, eax
0x18002a5d1  mov     [rdi], rcx
0x18002a5d4  xor     ecx, ecx; string
0x18002a5d6  mov     [rsp+28h+arg_8], 0
0x18002a5df  call    cs:__imp_WindowsDeleteString
0x18002a5e5  mov     eax, ebx
0x18002a5e7  mov     rbx, [rsp+28h+arg_10]
0x18002a5ec  add     rsp, 20h
0x18002a5f0  pop     rdi
0x18002a5f1  retn
```
