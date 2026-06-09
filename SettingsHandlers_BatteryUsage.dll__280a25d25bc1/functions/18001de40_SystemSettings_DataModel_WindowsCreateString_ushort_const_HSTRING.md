# SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)

- ea: `0x18001de40`
- end: `0x18001de9e`
- name: `?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *__hidden this, const unsigned __int16 *, HSTRING *)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019c5c`
- `0x18001b610`
- `0x18001bfb0`
- `0x180020cf0`
- `0x180022840`
- `0x180022860`
- `0x180027030`
- `0x180037c40`
- `0x18004bcb0`
- `0x18004c840`
- `0x18004e2b0`
- `0x18004e7dc`
- `0x18004eba0`

## callees

- `0x180013be0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001de8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001de8b`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::WindowsCreateString(const WCHAR *this, unsigned __int16 *a2, HSTRING *a3)
{
  const WCHAR *v4; // rax
  unsigned int v5; // ebx
  const WCHAR *v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  v4 = &word_180065238;
  if ( this )
    v4 = this;
  v7 = v4;
  v5 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
         (Microsoft::WRL::Wrappers::HString *)&v8,
         (__int64 *)&v7,
         (char)a3);
  *(_QWORD *)a2 = v8;
  v8 = 0;
  WindowsDeleteString(0);
  return v5;
}

```

## disassembly

```asm
0x18001de40  mov     r11, rsp
0x18001de43  mov     [r11+18h], rbx
0x18001de47  push    rdi
0x18001de48  sub     rsp, 20h
0x18001de4c  test    rcx, rcx
0x18001de4f  mov     qword ptr [r11+10h], 0
0x18001de57  mov     rdi, rdx
0x18001de5a  lea     rax, word_180065238
0x18001de61  cmovnz  rax, rcx
0x18001de65  lea     rdx, [r11+8]
0x18001de69  lea     rcx, [r11+10h]
0x18001de6d  mov     [r11+8], rax
0x18001de71  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001de76  mov     rcx, [rsp+28h+arg_8]
0x18001de7b  mov     ebx, eax
0x18001de7d  mov     [rdi], rcx
0x18001de80  xor     ecx, ecx; string
0x18001de82  mov     [rsp+28h+arg_8], 0
0x18001de8b  call    cs:__imp_WindowsDeleteString
0x18001de91  mov     eax, ebx
0x18001de93  mov     rbx, [rsp+28h+arg_10]
0x18001de98  add     rsp, 20h
0x18001de9c  pop     rdi
0x18001de9d  retn
```
