# Windows::UI::Composition::AnimationValueData::AnimationValueData(Microsoft::WRL::Wrappers::HStringReference)

- ea: `0x18008c56c`
- end: `0x18008c607`
- name: `??0AnimationValueData@Composition@UI@Windows@@QEAA@VHStringReference@Wrappers@WRL@Microsoft@@@Z`
- size: `155`
- prototype: ``
- caller_count: `24`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800135b0`
- `0x180014580`
- `0x18001626c`
- `0x180016a70`
- `0x180016db8`
- `0x1800317c8`
- `0x180036120`
- `0x180039698`
- `0x180046954`
- `0x180046ed0`
- `0x18004e41c`
- `0x18004e99c`
- `0x18004ecd8`
- `0x18004edfc`
- `0x18004ef2c`
- `0x180071f10`
- `0x18007b314`
- `0x18008c1e4`
- `0x1800a9498`
- `0x1800aece4`
- `0x1800da818`
- `0x180131f64`
- `0x18013a1a8`
- `0x18016c204`

## callees

- `0x1800171b0`
- `0x18008c56c`
- `0x1800f7a80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008c5d2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008c5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008c5bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008c5bc`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::AnimationValueData::AnimationValueData(__int64 a1, __int64 a2)
{
  const WCHAR *StringRawBuffer; // rbx
  UINT32 v5; // eax
  UINT32 v6; // edx
  HRESULT StringReference; // eax
  __int64 result; // rax
  UINT32 length; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)(a1 + 24) = 0;
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 24), &length);
  v5 = Microsoft::WRL::Wrappers::HStringReference::AddOne(length);
  v6 = v5 - 1;
  if ( length < v5 )
    v6 = length;
  StringReference = WindowsCreateStringReference(StringRawBuffer, v6, (HSTRING_HEADER *)a1, (HSTRING *)(a1 + 24));
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  memset_0((void *)(a1 + 32), 0, 0x40u);
  *(_DWORD *)(a1 + 96) = 0;
  result = a1;
  *(_BYTE *)(a1 + 100) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x18008c56c  push    rbx
0x18008c56e  push    rbp
0x18008c56f  push    rsi
0x18008c570  push    rdi
0x18008c571  sub     rsp, 28h
0x18008c575  mov     rbp, rdx
0x18008c578  mov     qword ptr [rcx+18h], 0
0x18008c580  mov     rsi, rcx
0x18008c583  mov     [rsp+48h+length], 0
0x18008c58b  lea     rdx, [rsp+48h+length]; length
0x18008c590  mov     rcx, [rbp+18h]; string
0x18008c594  call    cs:__imp_WindowsGetStringRawBuffer
0x18008c59a  mov     ecx, [rsp+48h+length]; unsigned int
0x18008c59e  mov     rbx, rax
0x18008c5a1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18008c5a6  cmp     [rsp+48h+length], eax
0x18008c5aa  lea     r9, [rsi+18h]; string
0x18008c5ae  mov     r8, rsi; hstringHeader
0x18008c5b1  mov     rcx, rbx; sourceString
0x18008c5b4  lea     edx, [rax-1]
0x18008c5b7  cmovb   edx, [rsp+48h+length]; length
0x18008c5bc  call    cs:__imp_WindowsCreateStringReference
0x18008c5c2  test    eax, eax
0x18008c5c4  jns     short loc_18008C5D9
0x18008c5c6  xor     r9d, r9d; lpArguments
0x18008c5c9  xor     r8d, r8d; nNumberOfArguments
0x18008c5cc  mov     ecx, eax; dwExceptionCode
0x18008c5ce  lea     edx, [r9+1]; dwExceptionFlags
0x18008c5d2  call    cs:__imp_RaiseException
0x18008c5d8  int     3; Trap to Debugger
0x18008c5d9  xor     edx, edx; Val
0x18008c5db  lea     rcx, [rsi+20h]; void *
0x18008c5df  lea     r8d, [rdx+40h]; Size
0x18008c5e3  call    memset_0
0x18008c5e8  mov     dword ptr [rsi+60h], 0
0x18008c5ef  mov     rax, rsi
0x18008c5f2  mov     byte ptr [rsi+64h], 0
0x18008c5f6  mov     qword ptr [rbp+18h], 0
0x18008c5fe  add     rsp, 28h
0x18008c602  pop     rdi
0x18008c603  pop     rsi
0x18008c604  pop     rbp
0x18008c605  pop     rbx
0x18008c606  retn
```
