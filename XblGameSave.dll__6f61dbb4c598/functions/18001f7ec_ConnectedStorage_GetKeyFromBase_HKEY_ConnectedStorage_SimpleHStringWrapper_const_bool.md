# ConnectedStorage::GetKeyFromBase(HKEY__ *,ConnectedStorage::SimpleHStringWrapper const &,bool)

- ea: `0x18001f7ec`
- end: `0x18001f8d6`
- name: `?GetKeyFromBase@ConnectedStorage@@YA?AVHKey@1@PEAUHKEY__@@AEBVSimpleHStringWrapper@1@_N@Z`
- size: `234`
- prototype: `_QWORD *__fastcall(_QWORD *, HKEY, HSTRING *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001f984`
- `0x18001f9d8`

## callees

- `0x18000ab18`
- `0x18001f7ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f8b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f8b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f85d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f85d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f855`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f855`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f87c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f87c`

## pseudocode

```c
_QWORD *__fastcall ConnectedStorage::GetKeyFromBase(_QWORD *a1, HKEY a2, HSTRING *a3, char a4)
{
  HSTRING v6; // rcx
  const WCHAR *StringRawBuffer; // rax
  LSTATUS Key; // eax
  const unsigned __int16 *v10; // r8
  const WCHAR *v11; // rax
  DWORD v12; // ebx
  unsigned __int64 v13; // rcx
  HKEY phkResult[3]; // [rsp+50h] [rbp-18h] BYREF

  phkResult[0] = 0;
  v6 = *a3;
  if ( a4 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v6, 0);
    Key = RegCreateKeyExW(a2, StringRawBuffer, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  }
  else
  {
    v11 = WindowsGetStringRawBuffer(v6, 0);
    Key = RegOpenKeyExW(a2, v11, 0, 0xF003Fu, phkResult);
  }
  v12 = Key;
  if ( Key )
  {
    if ( a4 )
    {
      if ( Key > 0 )
        v13 = (unsigned __int16)Key | 0x80070000;
      else
        v13 = (unsigned int)Key;
      ConnectedStorage::ReportErrorNoThrow((ConnectedStorage *)v13, (int)L"GetKeyFromBase", v10);
    }
    SetLastError(v12);
    *a1 = 0;
  }
  else
  {
    *a1 = phkResult[0];
  }
  return a1;
}

```

## disassembly

```asm
0x18001f7ec  mov     [rsp+arg_0], rbx
0x18001f7f1  mov     [rsp+arg_8], rsi
0x18001f7f6  push    rdi
0x18001f7f7  sub     rsp, 60h
0x18001f7fb  mov     rbx, rdx
0x18001f7fe  mov     [rsp+68h+var_18], 0
0x18001f807  xor     edx, edx; length
0x18001f809  mov     rdi, rcx
0x18001f80c  mov     rcx, [r8]; string
0x18001f80f  mov     sil, r9b
0x18001f812  test    r9b, r9b
0x18001f815  jz      short loc_18001F85D
0x18001f817  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f81d  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18001f826  lea     rcx, [rsp+68h+var_18]
0x18001f82b  mov     [rsp+68h+phkResult], rcx; phkResult
0x18001f830  xor     r9d, r9d; lpClass
0x18001f833  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001f83c  xor     r8d, r8d; Reserved
0x18001f83f  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x18001f847  mov     rdx, rax; lpSubKey
0x18001f84a  mov     rcx, rbx; hKey
0x18001f84d  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18001f855  call    cs:__imp_RegCreateKeyExW
0x18001f85b  jmp     short loc_18001F882
0x18001f85d  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f863  lea     rcx, [rsp+68h+var_18]
0x18001f868  mov     r9d, 0F003Fh; samDesired
0x18001f86e  mov     qword ptr [rsp+68h+dwOptions], rcx; phkResult
0x18001f873  xor     r8d, r8d; ulOptions
0x18001f876  mov     rcx, rbx; hKey
0x18001f879  mov     rdx, rax; lpSubKey
0x18001f87c  call    cs:__imp_RegOpenKeyExW
0x18001f882  mov     ebx, eax
0x18001f884  test    eax, eax
0x18001f886  jnz     short loc_18001F892
0x18001f888  mov     rax, [rsp+68h+var_18]
0x18001f88d  mov     [rdi], rax
0x18001f890  jmp     short loc_18001F8C3
0x18001f892  test    sil, sil
0x18001f895  jz      short loc_18001F8B4
0x18001f897  test    ebx, ebx
0x18001f899  jg      short loc_18001F89F
0x18001f89b  mov     ecx, ebx
0x18001f89d  jmp     short loc_18001F8A8
0x18001f89f  movzx   ecx, bx
0x18001f8a2  or      ecx, 80070000h; this
0x18001f8a8  lea     rdx, aGetkeyfrombase; "GetKeyFromBase"
0x18001f8af  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x18001f8b4  mov     ecx, ebx; dwErrCode
0x18001f8b6  call    cs:__imp_SetLastError
0x18001f8bc  mov     qword ptr [rdi], 0
0x18001f8c3  mov     rbx, [rsp+68h+arg_0]
0x18001f8c8  mov     rax, rdi
0x18001f8cb  mov     rsi, [rsp+68h+arg_8]
0x18001f8d0  add     rsp, 60h
0x18001f8d4  pop     rdi
0x18001f8d5  retn
```
