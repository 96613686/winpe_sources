# ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)

- ea: `0x18009cd70`
- end: `0x18009cf5d`
- name: `??1ComClassRegistrationEntryProperties@@QEAA@XZ`
- size: `493`
- prototype: `void __fastcall(ComClassRegistrationEntryProperties *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009c650`
- `0x1801b207c`
- `0x1801b8640`
- `0x18020a9f1`
- `0x18020f600`
- `0x18020f820`

## callees

- `0x18000b3bc`
- `0x18003a9c8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cda6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cdc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cdda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cdee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ceba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cd84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cda6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cdc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cdda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cdee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ce9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ceba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cf48`

## pseudocode

```c
void __fastcall ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(HSTRING *this)
{
  WindowsDeleteString(this[67]);
  this[67] = 0;
  SecurityDescriptor::Release((SecurityDescriptor *)(this + 63));
  WindowsDeleteString(this[57]);
  this[57] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 52);
  WindowsDeleteString(this[50]);
  this[50] = 0;
  WindowsDeleteString(this[48]);
  this[48] = 0;
  WindowsDeleteString(this[46]);
  this[46] = 0;
  WindowsDeleteString(this[44]);
  this[44] = 0;
  WindowsDeleteString(this[41]);
  this[41] = 0;
  WindowsDeleteString(this[39]);
  this[39] = 0;
  WindowsDeleteString(this[37]);
  this[37] = 0;
  WindowsDeleteString(this[35]);
  this[35] = 0;
  WindowsDeleteString(this[31]);
  this[31] = 0;
  WindowsDeleteString(this[29]);
  this[29] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 27);
  WindowsDeleteString(this[26]);
  this[26] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 24);
  WindowsDeleteString(this[23]);
  this[23] = 0;
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[19]);
  this[19] = 0;
  WindowsDeleteString(this[17]);
  this[17] = 0;
  WindowsDeleteString(this[15]);
  this[15] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 10);
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
}

```

## disassembly

```asm
0x18009cd70  mov     [rsp+arg_0], rbx
0x18009cd75  push    rdi
0x18009cd76  sub     rsp, 20h
0x18009cd7a  mov     rbx, rcx
0x18009cd7d  mov     rcx, [rcx+218h]; string
0x18009cd84  call    cs:__imp_WindowsDeleteString
0x18009cd8a  xor     edi, edi
0x18009cd8c  lea     rcx, [rbx+1F8h]; this
0x18009cd93  mov     [rbx+218h], rdi
0x18009cd9a  call    ?Release@SecurityDescriptor@@QEAAXXZ; SecurityDescriptor::Release(void)
0x18009cd9f  mov     rcx, [rbx+1C8h]; string
0x18009cda6  call    cs:__imp_WindowsDeleteString
0x18009cdac  lea     rcx, [rbx+1A0h]
0x18009cdb3  mov     [rbx+1C8h], rdi
0x18009cdba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009cdbf  mov     rcx, [rbx+190h]; string
0x18009cdc6  call    cs:__imp_WindowsDeleteString
0x18009cdcc  mov     [rbx+190h], rdi
0x18009cdd3  mov     rcx, [rbx+180h]; string
0x18009cdda  call    cs:__imp_WindowsDeleteString
0x18009cde0  mov     [rbx+180h], rdi
0x18009cde7  mov     rcx, [rbx+170h]; string
0x18009cdee  call    cs:__imp_WindowsDeleteString
0x18009cdf4  mov     [rbx+170h], rdi
0x18009cdfb  mov     rcx, [rbx+160h]; string
0x18009ce02  call    cs:__imp_WindowsDeleteString
0x18009ce08  mov     [rbx+160h], rdi
0x18009ce0f  mov     rcx, [rbx+148h]; string
0x18009ce16  call    cs:__imp_WindowsDeleteString
0x18009ce1c  mov     [rbx+148h], rdi
0x18009ce23  mov     rcx, [rbx+138h]; string
0x18009ce2a  call    cs:__imp_WindowsDeleteString
0x18009ce30  mov     [rbx+138h], rdi
0x18009ce37  mov     rcx, [rbx+128h]; string
0x18009ce3e  call    cs:__imp_WindowsDeleteString
0x18009ce44  mov     [rbx+128h], rdi
0x18009ce4b  mov     rcx, [rbx+118h]; string
0x18009ce52  call    cs:__imp_WindowsDeleteString
0x18009ce58  mov     [rbx+118h], rdi
0x18009ce5f  mov     rcx, [rbx+0F8h]; string
0x18009ce66  call    cs:__imp_WindowsDeleteString
0x18009ce6c  mov     [rbx+0F8h], rdi
0x18009ce73  mov     rcx, [rbx+0E8h]; string
0x18009ce7a  call    cs:__imp_WindowsDeleteString
0x18009ce80  lea     rcx, [rbx+0D8h]
0x18009ce87  mov     [rbx+0E8h], rdi
0x18009ce8e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009ce93  mov     rcx, [rbx+0D0h]; string
0x18009ce9a  call    cs:__imp_WindowsDeleteString
0x18009cea0  lea     rcx, [rbx+0C0h]
0x18009cea7  mov     [rbx+0D0h], rdi
0x18009ceae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009ceb3  mov     rcx, [rbx+0B8h]; string
0x18009ceba  call    cs:__imp_WindowsDeleteString
0x18009cec0  mov     [rbx+0B8h], rdi
0x18009cec7  mov     rcx, [rbx+0A8h]; string
0x18009cece  call    cs:__imp_WindowsDeleteString
0x18009ced4  mov     [rbx+0A8h], rdi
0x18009cedb  mov     rcx, [rbx+98h]; string
0x18009cee2  call    cs:__imp_WindowsDeleteString
0x18009cee8  mov     [rbx+98h], rdi
0x18009ceef  mov     rcx, [rbx+88h]; string
0x18009cef6  call    cs:__imp_WindowsDeleteString
0x18009cefc  mov     [rbx+88h], rdi
0x18009cf03  mov     rcx, [rbx+78h]; string
0x18009cf07  call    cs:__imp_WindowsDeleteString
0x18009cf0d  lea     rcx, [rbx+50h]
0x18009cf11  mov     [rbx+78h], rdi
0x18009cf15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009cf1a  mov     rcx, [rbx+40h]; string
0x18009cf1e  call    cs:__imp_WindowsDeleteString
0x18009cf24  mov     [rbx+40h], rdi
0x18009cf28  mov     rcx, [rbx+30h]; string
0x18009cf2c  call    cs:__imp_WindowsDeleteString
0x18009cf32  mov     [rbx+30h], rdi
0x18009cf36  mov     rcx, [rbx+20h]; string
0x18009cf3a  call    cs:__imp_WindowsDeleteString
0x18009cf40  mov     [rbx+20h], rdi
0x18009cf44  mov     rcx, [rbx+10h]; string
0x18009cf48  call    cs:__imp_WindowsDeleteString
0x18009cf4e  mov     [rbx+10h], rdi
0x18009cf52  mov     rbx, [rsp+28h+arg_0]
0x18009cf57  add     rsp, 20h
0x18009cf5b  pop     rdi
0x18009cf5c  retn
```
