# Windows::Internal::String::Initialize(HSTRING__ * const &)

- ea: `0x1800134f0`
- end: `0x18001353b`
- name: `?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `75`
- prototype: `HRESULT __fastcall(Windows::Internal::String *this, HSTRING__ *const *other)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180035c28`
- `0x180036abc`

## callees

- `0x1800134f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180013511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180013511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013528`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::String::Initialize(Windows::Internal::String *this, HSTRING *other)
{
  HRESULT result; // eax
  HRESULT v4; // edi
  HSTRING__ *hstring; // rcx
  HSTRING__ *local; // [rsp+30h] [rbp+8h] BYREF

  local = 0;
  result = WindowsDuplicateString(*other, &local);
  v4 = result;
  if ( result >= 0 )
  {
    hstring = this->_hstring;
    this->_hstring = local;
    WindowsDeleteString(hstring);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800134f0  mov     [rsp+arg_8], rbx
0x1800134f5  push    rdi
0x1800134f6  sub     rsp, 20h
0x1800134fa  mov     rax, other
0x1800134fd  mov     [rsp+28h+local], 0
0x180013506  mov     rbx, this
0x180013509  lea     other, [rsp+28h+local]; newString
0x18001350e  mov     this, [rax]; string
0x180013511  call    cs:__imp_WindowsDuplicateString
0x180013517  mov     edi, eax
0x180013519  test    eax, eax
0x18001351b  js      short loc_180013530
0x18001351d  mov     other, [rsp+28h+local]
0x180013522  mov     this, [rbx]; string
0x180013525  mov     [rbx], other
0x180013528  call    cs:__imp_WindowsDeleteString
0x18001352e  mov     eax, edi
0x180013530  mov     rbx, [rsp+28h+arg_8]
0x180013535  add     rsp, 20h
0x180013539  pop     rdi
0x18001353a  retn
```
