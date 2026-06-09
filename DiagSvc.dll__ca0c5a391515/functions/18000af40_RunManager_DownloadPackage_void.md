# RunManager::DownloadPackage(void)

- ea: `0x18000af40`
- end: `0x18000b028`
- name: `?DownloadPackage@RunManager@@MEAAJXZ`
- size: `232`
- prototype: `__int64 __fastcall(RunManager *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000af40`
- `0x180010c18`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000afac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000afec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000affc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b00e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000afac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000afec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000affc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b00e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b017`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RunManager::DownloadPackage(RunManager *this)
{
  int v2; // ebx
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  HSTRING string; // [rsp+60h] [rbp+28h] BYREF
  HSTRING v7; // [rsp+68h] [rbp+30h] BYREF
  __int64 v8; // [rsp+70h] [rbp+38h]
  __int64 v9; // [rsp+78h] [rbp+40h]

  v7 = 0;
  v8 = 0;
  v9 = 0;
  string = 0;
  v2 = (*(__int64 (__fastcall **)(RunManager *))(*(_QWORD *)this + 112LL))(this);
  if ( v2 >= 0 )
  {
    (*(void (__fastcall **)(RunManager *, __int64))(*(_QWORD *)this + 80LL))(this, 2);
    v3 = *((_QWORD *)this + 9);
    v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v3 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v2 = v4(v3, &string);
    if ( v2 >= 0 )
    {
      v7 = string;
      Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 49, &v7);
    }
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(0);
  WindowsDeleteString(0);
  WindowsDeleteString(0);
  WindowsDeleteString(0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000af40  push    rbp
0x18000af42  push    rbx
0x18000af43  push    rsi
0x18000af44  push    rdi
0x18000af45  mov     rbp, rsp
0x18000af48  sub     rsp, 38h
0x18000af4c  mov     rsi, rcx
0x18000af4f  mov     [rbp+arg_8], 0
0x18000af57  mov     [rbp+arg_10], 0
0x18000af5f  mov     [rbp+arg_18], 0
0x18000af67  mov     [rbp+var_18], 0
0x18000af6f  mov     [rbp+string], 0
0x18000af77  mov     rax, [rcx]
0x18000af7a  mov     rax, [rax+70h]
0x18000af7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af83  mov     ebx, eax
0x18000af85  test    eax, eax
0x18000af87  js      short loc_18000AFE8
0x18000af89  mov     rax, [rsi]
0x18000af8c  mov     edx, 2
0x18000af91  mov     rcx, rsi
0x18000af94  mov     rax, [rax+50h]
0x18000af98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af9d  mov     rdi, [rsi+48h]
0x18000afa1  mov     rax, [rdi]
0x18000afa4  mov     rbx, [rax+38h]
0x18000afa8  mov     rcx, [rbp+string]; string
0x18000afac  call    cs:__imp_WindowsDeleteString
0x18000afb2  mov     [rbp+string], 0
0x18000afba  lea     rdx, [rbp+string]
0x18000afbe  mov     rcx, rdi
0x18000afc1  mov     rax, rbx
0x18000afc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afc9  mov     ebx, eax
0x18000afcb  test    eax, eax
0x18000afcd  js      short loc_18000AFE8
0x18000afcf  mov     rax, [rbp+string]
0x18000afd3  mov     [rbp+arg_8], rax
0x18000afd7  lea     rcx, [rsi+188h]; newString
0x18000afde  lea     rdx, [rbp+arg_8]; HSTRING *
0x18000afe2  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18000afe7  nop
0x18000afe8  mov     rcx, [rbp+string]; string
0x18000afec  call    cs:__imp_WindowsDeleteString
0x18000aff2  mov     [rbp+string], 0
0x18000affa  xor     ecx, ecx; string
0x18000affc  call    cs:__imp_WindowsDeleteString
0x18000b002  nop
0x18000b003  xor     ecx, ecx; string
0x18000b005  call    cs:__imp_WindowsDeleteString
0x18000b00b  nop
0x18000b00c  xor     ecx, ecx; string
0x18000b00e  call    cs:__imp_WindowsDeleteString
0x18000b014  nop
0x18000b015  xor     ecx, ecx; string
0x18000b017  call    cs:__imp_WindowsDeleteString
0x18000b01d  mov     eax, ebx
0x18000b01f  add     rsp, 38h
0x18000b023  pop     rdi
0x18000b024  pop     rsi
0x18000b025  pop     rbx
0x18000b026  pop     rbp
0x18000b027  retn
```
