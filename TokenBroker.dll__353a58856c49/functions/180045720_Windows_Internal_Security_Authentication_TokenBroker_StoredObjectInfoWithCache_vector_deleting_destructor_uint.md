# Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::`vector deleting destructor'(uint)

- ea: `0x180045720`
- end: `0x1800457d9`
- name: `??_EStoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@UEAAPEAXI@Z`
- size: `185`
- prototype: `void *__fastcall(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180045720`
- `0x18008e6b4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045738`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004576f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004578c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004579b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800457aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045738`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004576f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004578c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004579b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800457aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800457d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800457d1`

## pseudocode

```c
Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache *__fastcall Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::`vector deleting destructor'(
        Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache *this,
        char a2)
{
  HSTRING v4; // rcx
  HSTRING v5; // rcx
  HSTRING v6; // rcx
  HSTRING v7; // rcx
  char *v8; // rcx
  HSTRING v9; // rcx
  HSTRING v10; // rcx
  HSTRING v11; // rcx

  v4 = (HSTRING)*((_QWORD *)this + 14);
  if ( v4 )
    WindowsDeleteString(v4);
  v5 = (HSTRING)*((_QWORD *)this + 13);
  if ( v5 )
    WindowsDeleteString(v5);
  *(_QWORD *)this = &Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::`vftable';
  v6 = (HSTRING)*((_QWORD *)this + 9);
  if ( v6 )
    WindowsDeleteString(v6);
  v7 = (HSTRING)*((_QWORD *)this + 8);
  if ( v7 )
    WindowsDeleteString(v7);
  v8 = (char *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  v9 = (HSTRING)*((_QWORD *)this + 5);
  if ( v9 )
    WindowsDeleteString(v9);
  v10 = (HSTRING)*((_QWORD *)this + 4);
  if ( v10 )
    WindowsDeleteString(v10);
  v11 = (HSTRING)*((_QWORD *)this + 3);
  if ( v11 )
    WindowsDeleteString(v11);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180045720  mov     [rsp+arg_0], rbx
0x180045725  push    rdi
0x180045726  sub     rsp, 20h
0x18004572a  mov     rbx, rcx
0x18004572d  mov     edi, edx
0x18004572f  mov     rcx, [rcx+70h]; string
0x180045733  test    rcx, rcx
0x180045736  jz      short loc_18004573E
0x180045738  call    cs:__imp_WindowsDeleteString
0x18004573e  mov     rcx, [rbx+68h]; string
0x180045742  test    rcx, rcx
0x180045745  jz      short loc_18004574D
0x180045747  call    cs:__imp_WindowsDeleteString
0x18004574d  lea     rax, ??_7StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@6B@; const Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::`vftable'
0x180045754  mov     [rbx], rax
0x180045757  mov     rcx, [rbx+48h]; string
0x18004575b  test    rcx, rcx
0x18004575e  jz      short loc_180045766
0x180045760  call    cs:__imp_WindowsDeleteString
0x180045766  mov     rcx, [rbx+40h]; string
0x18004576a  test    rcx, rcx
0x18004576d  jz      short loc_180045775
0x18004576f  call    cs:__imp_WindowsDeleteString
0x180045775  mov     rcx, [rbx+30h]; hObject
0x180045779  lea     rax, [rcx-1]
0x18004577d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180045781  jbe     short loc_1800457D1
0x180045783  mov     rcx, [rbx+28h]; string
0x180045787  test    rcx, rcx
0x18004578a  jz      short loc_180045792
0x18004578c  call    cs:__imp_WindowsDeleteString
0x180045792  mov     rcx, [rbx+20h]; string
0x180045796  test    rcx, rcx
0x180045799  jz      short loc_1800457A1
0x18004579b  call    cs:__imp_WindowsDeleteString
0x1800457a1  mov     rcx, [rbx+18h]; string
0x1800457a5  test    rcx, rcx
0x1800457a8  jz      short loc_1800457B0
0x1800457aa  call    cs:__imp_WindowsDeleteString
0x1800457b0  test    dil, 1
0x1800457b4  jz      short loc_1800457C3
0x1800457b6  mov     edx, 80h
0x1800457bb  mov     rcx, rbx; Block
0x1800457be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800457c3  mov     rax, rbx
0x1800457c6  mov     rbx, [rsp+28h+arg_0]
0x1800457cb  add     rsp, 20h
0x1800457cf  pop     rdi
0x1800457d0  retn
0x1800457d1  call    cs:__imp_CloseHandle
0x1800457d7  jmp     short loc_180045783
```
