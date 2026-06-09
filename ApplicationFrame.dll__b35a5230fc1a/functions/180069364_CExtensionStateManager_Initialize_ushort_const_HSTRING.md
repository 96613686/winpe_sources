# CExtensionStateManager::_Initialize(ushort const *,HSTRING__ *)

- ea: `0x180069364`
- end: `0x180069431`
- name: `?_Initialize@CExtensionStateManager@@AEAAJPEBGPEAUHSTRING__@@@Z`
- size: `205`
- prototype: `int(CExtensionStateManager *__hidden this, const unsigned __int16 *, HSTRING)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180063948`

## callees

- `0x18001e260`
- `0x180063758`
- `0x180069364`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800693a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800693a2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069402`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069402`

## pseudocode

```c
__int64 __fastcall CExtensionStateManager::_Initialize(
        CExtensionStateManager *this,
        const unsigned __int16 *a2,
        HSTRING a3)
{
  HKEY *phkResult; // rdi
  signed int v4; // ebx
  PCWSTR StringRawBuffer; // rax
  LSTATUS Key; // eax
  LPCWSTR lpSubKey[5]; // [rsp+50h] [rbp-28h] BYREF

  phkResult = (HKEY *)((char *)this + 16);
  if ( *((_QWORD *)this + 2) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    memset(lpSubKey, 0, 24);
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
           lpSubKey,
           L"%s\\%s",
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AppContract",
           StringRawBuffer);
    if ( v4 >= 0 )
    {
      Key = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      v4 = Key;
      if ( Key > 0 )
        v4 = (unsigned __int16)Key | 0x80070000;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180069364  mov     [rsp+arg_8], rbx
0x180069369  push    rdi
0x18006936a  sub     rsp, 70h
0x18006936e  lea     rdi, [rcx+10h]
0x180069372  cmp     qword ptr [rdi], 0
0x180069376  jz      short loc_180069382
0x180069378  mov     ebx, 8000FFFFh
0x18006937d  jmp     loc_180069421
0x180069382  xor     edx, edx; length
0x180069384  mov     [rsp+78h+lpSubKey], 0
0x18006938d  mov     rcx, r8; string
0x180069390  mov     [rsp+78h+var_20], 0
0x180069399  mov     [rsp+78h+var_18], 0
0x1800693a2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800693a8  mov     r9, rax
0x1800693ab  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800693b2  lea     rdx, aSS; "%s\\%s"
0x1800693b9  lea     rcx, [rsp+78h+lpSubKey]
0x1800693be  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800693c3  mov     ebx, eax
0x1800693c5  test    eax, eax
0x1800693c7  js      short loc_180069417
0x1800693c9  mov     rdx, [rsp+78h+lpSubKey]; lpSubKey
0x1800693ce  xor     r9d, r9d; lpClass
0x1800693d1  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x1800693da  xor     r8d, r8d; Reserved
0x1800693dd  mov     [rsp+78h+phkResult], rdi; phkResult
0x1800693e2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800693e9  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800693f2  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x1800693fa  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180069402  call    cs:__imp_RegCreateKeyExW
0x180069408  mov     ebx, eax
0x18006940a  test    eax, eax
0x18006940c  jle     short loc_180069417
0x18006940e  movzx   ebx, ax
0x180069411  or      ebx, 80070000h
0x180069417  lea     rcx, [rsp+78h+lpSubKey]
0x18006941c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180069421  mov     eax, ebx
0x180069423  mov     rbx, [rsp+78h+arg_8]
0x18006942b  add     rsp, 70h
0x18006942f  pop     rdi
0x180069430  retn
```
