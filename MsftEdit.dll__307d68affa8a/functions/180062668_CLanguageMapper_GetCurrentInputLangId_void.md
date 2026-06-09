# CLanguageMapper::GetCurrentInputLangId(void)

- ea: `0x180062668`
- end: `0x18006270d`
- name: `?GetCurrentInputLangId@CLanguageMapper@@SAGXZ`
- size: `165`
- prototype: `unsigned __int16(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180062498`

## callees

- `0x180062668`
- `0x180062714`
- `0x1800627c4`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800626b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800626b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800626d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800626d2`

## pseudocode

```c
__int64 CLanguageMapper::GetCurrentInputLangId(void)
{
  int v0; // eax
  HSTRING v1; // rcx
  int v2; // edi
  int v3; // eax
  unsigned __int16 v4; // bx
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned __int16 LidForName; // ax
  __int64 v7; // rcx
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  v0 = OSGetLanguageStatics((__int64)&v9);
  v1 = 0;
  v2 = v0;
  string = 0;
  if ( !v0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v9 + 56LL))(v9, &string);
    v1 = string;
    v2 = v3;
  }
  v4 = 0;
  if ( !v2 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v1, 0);
    LidForName = GetLidForName(StringRawBuffer);
    v1 = string;
    v4 = LidForName;
  }
  if ( v1 )
    WindowsDeleteString(v1);
  if ( v2 )
    v4 = 0;
  v7 = v9;
  if ( v9 )
  {
    v9 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return v4;
}

```

## disassembly

```asm
0x180062668  mov     [rsp+arg_10], rbx
0x18006266d  push    rdi
0x18006266e  sub     rsp, 20h
0x180062672  lea     rcx, [rsp+28h+arg_0]
0x180062677  mov     [rsp+28h+arg_0], 0
0x180062680  call    OSGetLanguageStatics
0x180062685  xor     ecx, ecx
0x180062687  mov     edi, eax
0x180062689  mov     [rsp+28h+string], rcx
0x18006268e  test    eax, eax
0x180062690  jnz     short loc_1800626AF
0x180062692  mov     rcx, [rsp+28h+arg_0]
0x180062697  lea     rdx, [rsp+28h+string]
0x18006269c  mov     rax, [rcx]
0x18006269f  mov     rax, [rax+38h]
0x1800626a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626a8  mov     rcx, [rsp+28h+string]; string
0x1800626ad  mov     edi, eax
0x1800626af  xor     ebx, ebx
0x1800626b1  test    edi, edi
0x1800626b3  jnz     short loc_1800626CD
0x1800626b5  xor     edx, edx; length
0x1800626b7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800626bd  mov     rcx, rax; unsigned __int16 *
0x1800626c0  call    ?GetLidForName@@YAGPEBG@Z; GetLidForName(ushort const *)
0x1800626c5  mov     rcx, [rsp+28h+string]; string
0x1800626ca  movzx   ebx, ax
0x1800626cd  test    rcx, rcx
0x1800626d0  jz      short loc_1800626D8
0x1800626d2  call    cs:__imp_WindowsDeleteString
0x1800626d8  xor     ecx, ecx
0x1800626da  test    edi, edi
0x1800626dc  cmovnz  bx, cx
0x1800626e0  mov     rcx, [rsp+28h+arg_0]
0x1800626e5  test    rcx, rcx
0x1800626e8  jz      short loc_1800626FF
0x1800626ea  mov     [rsp+28h+arg_0], 0
0x1800626f3  mov     rax, [rcx]
0x1800626f6  mov     rax, [rax+10h]
0x1800626fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626ff  movzx   eax, bx
0x180062702  mov     rbx, [rsp+28h+arg_10]
0x180062707  add     rsp, 20h
0x18006270b  pop     rdi
0x18006270c  retn
```
