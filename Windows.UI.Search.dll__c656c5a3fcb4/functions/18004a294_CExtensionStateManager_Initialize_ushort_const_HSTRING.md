# CExtensionStateManager::_Initialize(ushort const *,HSTRING__ *)

- ea: `0x18004a294`
- end: `0x18004a361`
- name: `?_Initialize@CExtensionStateManager@@AEAAJPEBGPEAUHSTRING__@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(CExtensionStateManager *this, const unsigned __int16 *, HSTRING)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180044a84`

## callees

- `0x1800120dc`
- `0x180044888`
- `0x18004a294`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a2d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a2d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a332`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a332`

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
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004a294  mov     [rsp+arg_8], rbx
0x18004a299  push    rdi
0x18004a29a  sub     rsp, 70h
0x18004a29e  lea     rdi, [rcx+10h]
0x18004a2a2  cmp     qword ptr [rdi], 0
0x18004a2a6  jz      short loc_18004A2B2
0x18004a2a8  mov     ebx, 8000FFFFh
0x18004a2ad  jmp     loc_18004A351
0x18004a2b2  xor     edx, edx; length
0x18004a2b4  mov     [rsp+78h+lpSubKey], 0
0x18004a2bd  mov     rcx, r8; string
0x18004a2c0  mov     [rsp+78h+var_20], 0
0x18004a2c9  mov     [rsp+78h+var_18], 0
0x18004a2d2  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a2d8  mov     r9, rax
0x18004a2db  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004a2e2  lea     rdx, aSS; "%s\\%s"
0x18004a2e9  lea     rcx, [rsp+78h+lpSubKey]
0x18004a2ee  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18004a2f3  mov     ebx, eax
0x18004a2f5  test    eax, eax
0x18004a2f7  js      short loc_18004A347
0x18004a2f9  mov     rdx, [rsp+78h+lpSubKey]; lpSubKey
0x18004a2fe  xor     r9d, r9d; lpClass
0x18004a301  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18004a30a  xor     r8d, r8d; Reserved
0x18004a30d  mov     [rsp+78h+phkResult], rdi; phkResult
0x18004a312  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18004a319  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004a322  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x18004a32a  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18004a332  call    cs:__imp_RegCreateKeyExW
0x18004a338  mov     ebx, eax
0x18004a33a  test    eax, eax
0x18004a33c  jle     short loc_18004A347
0x18004a33e  movzx   ebx, ax
0x18004a341  or      ebx, 80070000h
0x18004a347  lea     rcx, [rsp+78h+lpSubKey]
0x18004a34c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004a351  mov     eax, ebx
0x18004a353  mov     rbx, [rsp+78h+arg_8]
0x18004a35b  add     rsp, 70h
0x18004a35f  pop     rdi
0x18004a360  retn
```
