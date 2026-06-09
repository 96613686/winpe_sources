# SecureZeroHString::~SecureZeroHString(void)

- ea: `0x1800225c4`
- end: `0x180022622`
- name: `??1SecureZeroHString@@QEAA@XZ`
- size: `94`
- prototype: `void __fastcall(SecureZeroHString *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180022660`
- `0x180022924`
- `0x180036c55`
- `0x180036c67`

## callees

- `0x1800225c4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022600`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002260f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022600`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002260f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800225e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800225e2`

## pseudocode

```c
void __fastcall SecureZeroHString::~SecureZeroHString(HSTRING *this)
{
  HSTRING v2; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 i; // rcx
  UINT32 length; // [rsp+30h] [rbp+8h] BYREF

  v2 = *this;
  if ( v2 )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v2, &length);
    for ( i = 2LL * length; i; --i )
    {
      *(_BYTE *)StringRawBuffer = 0;
      StringRawBuffer = (PCWSTR)((char *)StringRawBuffer + 1);
    }
  }
  WindowsDeleteString(*this);
  *this = 0;
  WindowsDeleteString(0);
  *this = 0;
}

```

## disassembly

```asm
0x1800225c4  push    rbx
0x1800225c6  sub     rsp, 20h
0x1800225ca  mov     rbx, rcx
0x1800225cd  mov     rcx, [rcx]; string
0x1800225d0  test    rcx, rcx
0x1800225d3  jz      short loc_1800225FD
0x1800225d5  lea     rdx, [rsp+28h+length]; length
0x1800225da  mov     [rsp+28h+length], 0
0x1800225e2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800225e8  mov     ecx, [rsp+28h+length]
0x1800225ec  add     rcx, rcx
0x1800225ef  jz      short loc_1800225FD
0x1800225f1  mov     byte ptr [rax], 0
0x1800225f4  inc     rax
0x1800225f7  sub     rcx, 1
0x1800225fb  jnz     short loc_1800225F1
0x1800225fd  mov     rcx, [rbx]; string
0x180022600  call    cs:__imp_WindowsDeleteString
0x180022606  xor     ecx, ecx; string
0x180022608  mov     qword ptr [rbx], 0
0x18002260f  call    cs:__imp_WindowsDeleteString
0x180022615  mov     qword ptr [rbx], 0
0x18002261c  add     rsp, 20h
0x180022620  pop     rbx
0x180022621  retn
```
