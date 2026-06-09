# DirectUI::KeyboardAccelerator::ConcatVirtualKey(Windows::System::VirtualKey,Windows::Internal::String &)

- ea: `0x180384b00`
- end: `0x180384cd3`
- name: `?ConcatVirtualKey@KeyboardAccelerator@DirectUI@@AEAAJW4VirtualKey@System@Windows@@AEAVString@Internal@5@@Z`
- size: `467`
- prototype: `HRESULT __fastcall(DirectUI::KeyboardAccelerator *this, Windows::System::VirtualKey key, Windows::Internal::String *keyboardAcceleratorString)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1802e0a08`

## callees

- `0x180004bc0`
- `0x1801df610`
- `0x1801e5458`
- `0x1801f1530`
- `0x1803839c0`
- `0x180384b00`
- `0x1803866c4`
- `0x1804d63a8`
- `0x18069f6ac`
- `0x18076e110`
- `0x18076f220`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384b3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384b8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384c1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384c9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384b3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384b8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384c1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180384c9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180384bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180384bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180384bdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180384bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180384bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180384bdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180384b6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180384b6d`

## pseudocode

```c
__int64 __fastcall DirectUI::KeyboardAccelerator::ConcatVirtualKey(
        DirectUI::KeyboardAccelerator *this,
        Windows::System::VirtualKey key,
        Windows::Internal::String *keyboardAcceleratorString)
{
  DirectUI::DXamlCore *Current; // rbx
  unsigned int ResourceStringIdFromVirtualKey; // eax
  HRESULT LocalizedResourceString; // eax
  unsigned int v8; // ebx
  BOOL IsStringEmpty; // eax
  HSTRING__ *hstring; // rbx
  DirectUI::DXamlCore *v11; // rdi
  HRESULT v12; // eax
  unsigned int v13; // esi
  PCWSTR StringRawBuffer; // r14
  PCWSTR v15; // rax
  HSTRING__ *v16; // rdi
  PCWSTR v17; // rsi
  const wchar_t *v18; // rax
  HRESULT v19; // ecx
  Windows::Internal::String keyName; // [rsp+30h] [rbp-D0h] BYREF
  Windows::Internal::String joiningFormatString; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t buffer[256]; // [rsp+40h] [rbp-C0h] BYREF

  Current = DirectUI::DXamlCore::GetCurrent();
  WindowsDeleteString(0);
  keyName._hstring = 0;
  ResourceStringIdFromVirtualKey = GetResourceStringIdFromVirtualKey(key);
  LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(
                              Current,
                              ResourceStringIdFromVirtualKey,
                              &keyName._hstring);
  v8 = LocalizedResourceString;
  if ( LocalizedResourceString < 0 )
  {
    OnFailure_2990_(LocalizedResourceString);
    if ( keyName._hstring )
      WindowsDeleteString(keyName._hstring);
    return v8;
  }
  else
  {
    IsStringEmpty = WindowsIsStringEmpty(keyboardAcceleratorString->_hstring);
    hstring = keyName._hstring;
    if ( IsStringEmpty )
    {
      Windows::Internal::String::Initialize(keyboardAcceleratorString, &keyName._hstring);
    }
    else
    {
      v11 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      joiningFormatString._hstring = 0;
      v12 = DirectUI::DXamlCore::GetLocalizedResourceString(v11, 0x1427u, &joiningFormatString._hstring);
      v13 = v12;
      if ( v12 < 0 )
        goto LABEL_20;
      StringRawBuffer = WindowsGetStringRawBuffer(hstring, 0);
      v15 = WindowsGetStringRawBuffer(keyboardAcceleratorString->_hstring, 0);
      v16 = joiningFormatString._hstring;
      v17 = v15;
      v18 = WindowsGetStringRawBuffer(joiningFormatString._hstring, 0);
      if ( swprintf_s(buffer, 0x100u, v18, v17, StringRawBuffer) < 0 )
      {
        OnNewFailure_2955_(v19);
        if ( v16 )
          WindowsDeleteString(v16);
        if ( hstring )
          WindowsDeleteString(hstring);
        return 2147549183LL;
      }
      v12 = Windows::Internal::String::_InitializeHelper(keyboardAcceleratorString, buffer);
      v13 = v12;
      if ( v12 < 0 )
      {
LABEL_20:
        OnFailure_2990_(v12);
        Windows::Internal::String::~String(&joiningFormatString);
        Windows::Internal::String::~String(&keyName);
        return v13;
      }
      if ( v16 )
        WindowsDeleteString(v16);
    }
    if ( hstring )
      WindowsDeleteString(hstring);
    return 0;
  }
}

```

## disassembly

```asm
0x180384b00  mov     [rsp-8+arg_0], rbx
0x180384b05  push    rbp
0x180384b06  push    rsi
0x180384b07  push    rdi
0x180384b08  push    r14
0x180384b0a  push    r15
0x180384b0c  lea     rbp, [rsp-150h]
0x180384b14  sub     rsp, 250h
0x180384b1b  mov     rax, cs:__security_cookie
0x180384b22  xor     rax, rsp
0x180384b25  mov     [rbp+170h+var_30], rax
0x180384b2c  mov     r15, keyboardAcceleratorString
0x180384b2f  mov     edi, key
0x180384b31  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180384b36  xor     ecx, ecx; string
0x180384b38  mov     rbx, rax
0x180384b3b  call    cs:__imp_WindowsDeleteString
0x180384b41  mov     ecx, edi; key
0x180384b43  mov     [rsp+270h+keyName._hstring], 0
0x180384b4c  call    ?GetResourceStringIdFromVirtualKey@@YAIW4VirtualKey@System@Windows@@@Z; GetResourceStringIdFromVirtualKey(Windows::System::VirtualKey)
0x180384b51  lea     keyboardAcceleratorString, [rsp+270h+keyName]; resourceString
0x180384b56  mov     key, eax; resourceStringID
0x180384b58  mov     rcx, rbx; this
0x180384b5b  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x180384b60  mov     ebx, eax
0x180384b62  test    eax, eax
0x180384b64  js      loc_180384C8D
0x180384b6a  mov     rcx, [r15]; string
0x180384b6d  call    cs:__imp_WindowsIsStringEmpty
0x180384b73  mov     rbx, [rsp+270h+keyName._hstring]
0x180384b78  test    eax, eax
0x180384b7a  jnz     loc_180384C27
0x180384b80  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180384b85  xor     ecx, ecx; string
0x180384b87  mov     rdi, rax
0x180384b8a  call    cs:__imp_WindowsDeleteString
0x180384b90  lea     keyboardAcceleratorString, [rsp+270h+joiningFormatString]; resourceString
0x180384b95  mov     [rsp+270h+joiningFormatString._hstring], 0
0x180384b9e  mov     key, 1427h; resourceStringID
0x180384ba3  mov     rcx, rdi; this
0x180384ba6  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x180384bab  mov     esi, eax
0x180384bad  test    eax, eax
0x180384baf  js      loc_180384CB1
0x180384bb5  xor     key, key; length
0x180384bb7  mov     rcx, rbx; string
0x180384bba  call    cs:__imp_WindowsGetStringRawBuffer
0x180384bc0  mov     rcx, [r15]; string
0x180384bc3  xor     key, key; length
0x180384bc5  mov     r14, rax
0x180384bc8  call    cs:__imp_WindowsGetStringRawBuffer
0x180384bce  mov     rdi, [rsp+270h+joiningFormatString._hstring]
0x180384bd3  xor     key, key; length
0x180384bd5  mov     rcx, rdi; string
0x180384bd8  mov     rsi, rax
0x180384bdb  call    cs:__imp_WindowsGetStringRawBuffer
0x180384be1  mov     r9, rsi
0x180384be4  mov     [rsp+270h+var_250], r14
0x180384be9  mov     keyboardAcceleratorString, rax; _Format
0x180384bec  lea     rcx, [rsp+270h+buffer]; _Buffer
0x180384bf1  mov     key, 100h; _BufferCount
0x180384bf6  call    swprintf_s
0x180384bfb  test    eax, eax
0x180384bfd  jns     short loc_180384C6A
0x180384bff  call    OnNewFailure_2955_
0x180384c04  test    rdi, rdi
0x180384c07  jz      short loc_180384C12
0x180384c09  mov     rcx, rdi; string
0x180384c0c  call    cs:__imp_WindowsDeleteString
0x180384c12  test    rbx, rbx
0x180384c15  jz      short loc_180384C20
0x180384c17  mov     rcx, rbx; string
0x180384c1a  call    cs:__imp_WindowsDeleteString
0x180384c20  mov     eax, 8000FFFFh
0x180384c25  jmp     short loc_180384C44
0x180384c27  lea     rdx, [rsp+270h+keyName]; other
0x180384c2c  mov     rcx, r15; this
0x180384c2f  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180384c34  test    rbx, rbx
0x180384c37  jz      short loc_180384C42
0x180384c39  mov     rcx, rbx; string
0x180384c3c  call    cs:__imp_WindowsDeleteString
0x180384c42  xor     eax, eax
0x180384c44  mov     rcx, [rbp+170h+var_30]
0x180384c4b  xor     rcx, rsp; StackCookie
0x180384c4e  call    __security_check_cookie
0x180384c53  mov     rbx, [rsp+270h+arg_0]
0x180384c5b  add     rsp, 250h
0x180384c62  pop     r15
0x180384c64  pop     r14
0x180384c66  pop     rdi
0x180384c67  pop     rsi
0x180384c68  pop     rbp
0x180384c69  retn
0x180384c6a  lea     rdx, [rsp+270h+buffer]; str
0x180384c6f  mov     rcx, r15; this
0x180384c72  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180384c77  mov     esi, eax
0x180384c79  test    eax, eax
0x180384c7b  js      short loc_180384CA8
0x180384c7d  test    rdi, rdi
0x180384c80  jz      short loc_180384C34
0x180384c82  mov     rcx, rdi; string
0x180384c85  call    cs:__imp_WindowsDeleteString
0x180384c8b  jmp     short loc_180384C34
0x180384c8d  mov     ecx, ebx; failedFrameHR
0x180384c8f  call    OnFailure_2990_
0x180384c94  mov     rcx, [rsp+270h+keyName._hstring]; string
0x180384c99  test    rcx, rcx
0x180384c9c  jz      short loc_180384CA4
0x180384c9e  call    cs:__imp_WindowsDeleteString
0x180384ca4  mov     eax, ebx
0x180384ca6  jmp     short loc_180384C44
0x180384ca8  mov     ecx, eax; failedFrameHR
0x180384caa  call    OnFailure_2990_
0x180384caf  jmp     short loc_180384CB8
0x180384cb1  mov     ecx, eax; failedFrameHR
0x180384cb3  call    OnFailure_2990_
0x180384cb8  lea     rcx, [rsp+270h+joiningFormatString]; this
0x180384cbd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180384cc2  lea     rcx, [rsp+270h+keyName]; this
0x180384cc7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180384ccc  mov     eax, esi
0x180384cce  jmp     loc_180384C44
```
