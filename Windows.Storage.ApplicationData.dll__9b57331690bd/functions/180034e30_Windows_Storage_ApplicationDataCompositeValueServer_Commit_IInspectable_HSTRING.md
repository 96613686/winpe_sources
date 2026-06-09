# Windows::Storage::ApplicationDataCompositeValueServer::Commit(IInspectable *,HSTRING__ *)

- ea: `0x180034e30`
- end: `0x180034ed7`
- name: `?Commit@ApplicationDataCompositeValueServer@Storage@Windows@@UEAAJPEAUIInspectable@@PEAUHSTRING__@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(Windows::Storage::ApplicationDataCompositeValueServer *this, IInspectable *containerHandle, HSTRING key)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005ee0`
- `0x180009778`
- `0x180034e30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034e4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034e91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034e4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034e91`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CommitStateAtom` at `0x180034e5d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CommitStateAtom` at `0x180034e5d`

## string_xrefs

- `0x180034e9c`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x180034eab`: `CommitStateAtom %ws`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataCompositeValueServer::Commit(
        Windows::Storage::ApplicationDataCompositeValueServer *this,
        IInspectable *containerHandle,
        HSTRING key)
{
  __int64 v3; // rbx
  PCWSTR StringRawBuffer; // rax
  signed int LastError; // eax
  HRESULT v8; // ebx
  PCWSTR v9; // rax
  void *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *(_QWORD *)&this->gap8;
  StringRawBuffer = WindowsGetStringRawBuffer(key, 0);
  if ( (unsigned int)CommitStateAtom(containerHandle, StringRawBuffer, v3) )
    return 0;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  Windows::Storage::StateABIHelpers::ReportError(v8, 0x14u);
  if ( v8 < 0 )
  {
    v9 = WindowsGetStringRawBuffer(key, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x246u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      v8,
      "CommitStateAtom %ws",
      v9);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180034e30  mov     [rsp+arg_0], rbx
0x180034e35  mov     [rsp+arg_8], rsi
0x180034e3a  push    rdi
0x180034e3b  sub     rsp, 30h
0x180034e3f  mov     rbx, [this+38h]
0x180034e43  mov     rdi, containerHandle
0x180034e46  xor     edx, edx; length
0x180034e48  mov     this, key; string
0x180034e4b  mov     rsi, key
0x180034e4e  call    cs:__imp_WindowsGetStringRawBuffer
0x180034e54  mov     key, rbx
0x180034e57  mov     this, rdi
0x180034e5a  mov     containerHandle, rax
0x180034e5d  call    cs:__imp_CommitStateAtom
0x180034e63  test    eax, eax
0x180034e65  jnz     short loc_180034EC5
0x180034e67  call    cs:__imp_GetLastError
0x180034e6d  mov     ebx, eax
0x180034e6f  test    eax, eax
0x180034e71  jle     short loc_180034E7C
0x180034e73  movzx   ebx, ax
0x180034e76  or      ebx, 80070000h
0x180034e7c  mov     edx, 14h; idsValue
0x180034e81  mov     ecx, ebx; hr
0x180034e83  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180034e88  test    ebx, ebx
0x180034e8a  jns     short loc_180034EC1
0x180034e8c  xor     edx, edx; length
0x180034e8e  mov     this, rsi; string
0x180034e91  call    cs:__imp_WindowsGetStringRawBuffer
0x180034e97  mov     this, [rsp+38h]; callerReturnAddress
0x180034e9c  lea     key, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x180034ea3  mov     [rsp+38h+var_10], rax
0x180034ea8  mov     r9d, ebx; hr
0x180034eab  lea     rax, aCommitstateato_0; "CommitStateAtom %ws"
0x180034eb2  mov     edx, 246h; lineNumber
0x180034eb7  mov     [rsp+38h+formatString], rax; formatString
0x180034ebc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034ec1  mov     eax, ebx
0x180034ec3  jmp     short loc_180034EC7
0x180034ec5  xor     eax, eax
0x180034ec7  mov     rbx, [rsp+38h+arg_0]
0x180034ecc  mov     rsi, [rsp+38h+arg_8]
0x180034ed1  add     rsp, 30h
0x180034ed5  pop     rdi
0x180034ed6  retn
```
