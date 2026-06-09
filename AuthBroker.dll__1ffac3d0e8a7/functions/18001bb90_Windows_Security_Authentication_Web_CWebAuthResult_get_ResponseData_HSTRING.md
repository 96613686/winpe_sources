# Windows::Security::Authentication::Web::CWebAuthResult::get_ResponseData(HSTRING__ * *)

- ea: `0x18001bb90`
- end: `0x18001bc42`
- name: `?get_ResponseData@CWebAuthResult@Web@Authentication@Security@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(Windows::Security::Authentication::Web::CWebAuthResult *this, HSTRING__ **value)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006e5c`
- `0x180012b88`
- `0x18001bb90`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001bbf8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001bbf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bbdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bbdf`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001bc05`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001bc05`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authentication::Web::CWebAuthResult::get_ResponseData(
        Windows::Security::Authentication::Web::CWebAuthResult *this,
        HSTRING__ **value)
{
  int v3; // ebx
  Windows::Internal::String strResult; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-28h] BYREF

  strResult._hstring = 0;
  v3 = Windows::Internal::String::Initialize(&strResult, &this->m_data._hstring);
  if ( v3 >= 0 )
  {
    *value = strResult._hstring;
    strResult._hstring = 0;
  }
  else
  {
    if ( WindowsCreateStringReference(L"Failed to allocate response data", 0x20u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    RoOriginateError((unsigned int)v3, string);
  }
  Windows::Internal::String::~String(&strResult);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001bb90  mov     [rsp+arg_10], rbx
0x18001bb95  push    rdi
0x18001bb96  sub     rsp, 50h
0x18001bb9a  mov     rax, cs:__security_cookie
0x18001bba1  xor     rax, rsp
0x18001bba4  mov     [rsp+58h+var_10], rax
0x18001bba9  mov     rdi, value
0x18001bbac  mov     [rsp+58h+strResult._hstring], 0
0x18001bbb5  lea     value, [this+28h]; other
0x18001bbb9  lea     this, [rsp+58h+strResult]; this
0x18001bbbe  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18001bbc3  mov     ebx, eax
0x18001bbc5  test    eax, eax
0x18001bbc7  jns     short loc_18001BC0D
0x18001bbc9  lea     r9, [rsp+58h+string]; string
0x18001bbce  mov     edx, 20h ; ' '; length
0x18001bbd3  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18001bbd8  lea     this, aFailedToAlloca_0; "Failed to allocate response data"
0x18001bbdf  call    cs:__imp_WindowsCreateStringReference
0x18001bbe5  test    eax, eax
0x18001bbe7  jns     short loc_18001BBFE
0x18001bbe9  xor     r9d, r9d; lpArguments
0x18001bbec  xor     r8d, r8d; nNumberOfArguments
0x18001bbef  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001bbf4  lea     edx, [r9+1]; dwExceptionFlags
0x18001bbf8  call    cs:__imp_RaiseException
0x18001bbfe  mov     value, [rsp+58h+string]
0x18001bc03  mov     ecx, ebx
0x18001bc05  call    cs:__imp_RoOriginateError
0x18001bc0b  jmp     short loc_18001BC1E
0x18001bc0d  mov     rax, [rsp+58h+strResult._hstring]
0x18001bc12  mov     [rdi], rax
0x18001bc15  mov     [rsp+58h+strResult._hstring], 0
0x18001bc1e  lea     this, [rsp+58h+strResult]; this
0x18001bc23  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001bc28  mov     eax, ebx
0x18001bc2a  mov     this, [rsp+58h+var_10]
0x18001bc2f  xor     this, rsp; StackCookie
0x18001bc32  call    __security_check_cookie
0x18001bc37  mov     rbx, [rsp+58h+arg_10]
0x18001bc3c  add     rsp, 50h
0x18001bc40  pop     rdi
0x18001bc41  retn
```
