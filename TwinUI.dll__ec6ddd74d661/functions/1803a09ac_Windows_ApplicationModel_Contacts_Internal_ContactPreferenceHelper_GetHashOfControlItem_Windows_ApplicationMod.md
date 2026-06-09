# Windows::ApplicationModel::Contacts::Internal::ContactPreferenceHelper::GetHashOfControlItem(Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem *,unsigned __int64 *)

- ea: `0x1803a09ac`
- end: `0x1803a0ac8`
- name: `?GetHashOfControlItem@ContactPreferenceHelper@Internal@Contacts@ApplicationModel@Windows@@SAJPEAUIContactActionControlItem@2345@PEA_K@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1803a0b40`
- `0x1803a10f0`

## callees

- `0x1803a09ac`
- `0x1803a0cd0`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a09d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a0a17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a0a4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a0a8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a0a9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a0aac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a09d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a0a17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a0a4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a0a8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a0a9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803a0aac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1803a0a6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1803a0a6a`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactPreferenceHelper::GetHashOfControlItem(
        struct Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem *a1,
        unsigned __int64 *a2)
{
  __int64 v3; // rax
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem *, HSTRING *); // rbx
  HRESULT v6; // ebx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(struct Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem *, HSTRING *); // rbx
  HSTRING newString; // [rsp+40h] [rbp+20h] BYREF
  HSTRING string2; // [rsp+48h] [rbp+28h] BYREF
  HSTRING string1; // [rsp+50h] [rbp+30h] BYREF

  *a2 = 0;
  v3 = *(_QWORD *)a1;
  string1 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem *, HSTRING *))(v3 + 64);
  WindowsDeleteString(0);
  string1 = 0;
  v6 = v5(a1, &string1);
  if ( v6 >= 0 )
  {
    v7 = *(_QWORD *)a1;
    string2 = 0;
    v8 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem *, HSTRING *))(v7 + 72);
    WindowsDeleteString(0);
    string2 = 0;
    v6 = v8(a1, &string2);
    if ( v6 >= 0 )
    {
      newString = 0;
      WindowsDeleteString(0);
      newString = 0;
      v6 = WindowsConcatString(string1, string2, &newString);
      if ( v6 >= 0 )
        *a2 = Windows::ApplicationModel::Contacts::Internal::ContactPreferenceHelper::GetStringHash(newString);
      WindowsDeleteString(newString);
    }
    WindowsDeleteString(string2);
  }
  WindowsDeleteString(string1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1803a09ac  mov     [rsp-18h+arg_18], rbx
0x1803a09b1  push    rbp
0x1803a09b2  push    rsi
0x1803a09b3  push    rdi
0x1803a09b4  mov     rbp, rsp
0x1803a09b7  sub     rsp, 20h
0x1803a09bb  mov     qword ptr [rdx], 0
0x1803a09c2  mov     rdi, rcx
0x1803a09c5  mov     rax, [rcx]
0x1803a09c8  mov     rsi, rdx
0x1803a09cb  xor     ecx, ecx; string
0x1803a09cd  mov     [rbp+string1], 0
0x1803a09d5  mov     rbx, [rax+40h]
0x1803a09d9  call    cs:__imp_WindowsDeleteString
0x1803a09e0  nop     dword ptr [rax+rax+00h]
0x1803a09e5  lea     rdx, [rbp+string1]
0x1803a09e9  mov     [rbp+string1], 0
0x1803a09f1  mov     rcx, rdi
0x1803a09f4  mov     rax, rbx
0x1803a09f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a09fc  mov     ebx, eax
0x1803a09fe  test    eax, eax
0x1803a0a00  js      loc_1803A0AA8
0x1803a0a06  mov     rax, [rdi]
0x1803a0a09  xor     ecx, ecx; string
0x1803a0a0b  mov     [rbp+string2], 0
0x1803a0a13  mov     rbx, [rax+48h]
0x1803a0a17  call    cs:__imp_WindowsDeleteString
0x1803a0a1e  nop     dword ptr [rax+rax+00h]
0x1803a0a23  lea     rdx, [rbp+string2]
0x1803a0a27  mov     [rbp+string2], 0
0x1803a0a2f  mov     rcx, rdi
0x1803a0a32  mov     rax, rbx
0x1803a0a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a0a3a  mov     ebx, eax
0x1803a0a3c  test    eax, eax
0x1803a0a3e  js      short loc_1803A0A98
0x1803a0a40  xor     ecx, ecx; string
0x1803a0a42  mov     [rbp+newString], 0
0x1803a0a4a  call    cs:__imp_WindowsDeleteString
0x1803a0a51  nop     dword ptr [rax+rax+00h]
0x1803a0a56  mov     rdx, [rbp+string2]; string2
0x1803a0a5a  lea     r8, [rbp+newString]; newString
0x1803a0a5e  mov     rcx, [rbp+string1]; string1
0x1803a0a62  mov     [rbp+newString], 0
0x1803a0a6a  call    cs:__imp_WindowsConcatString
0x1803a0a71  nop     dword ptr [rax+rax+00h]
0x1803a0a76  mov     ebx, eax
0x1803a0a78  test    eax, eax
0x1803a0a7a  js      short loc_1803A0A88
0x1803a0a7c  mov     rcx, [rbp+newString]; string
0x1803a0a80  call    ?GetStringHash@ContactPreferenceHelper@Internal@Contacts@ApplicationModel@Windows@@SA_KPEAUHSTRING__@@@Z; Windows::ApplicationModel::Contacts::Internal::ContactPreferenceHelper::GetStringHash(HSTRING__ *)
0x1803a0a85  mov     [rsi], rax
0x1803a0a88  mov     rcx, [rbp+newString]; string
0x1803a0a8c  call    cs:__imp_WindowsDeleteString
0x1803a0a93  nop     dword ptr [rax+rax+00h]
0x1803a0a98  mov     rcx, [rbp+string2]; string
0x1803a0a9c  call    cs:__imp_WindowsDeleteString
0x1803a0aa3  nop     dword ptr [rax+rax+00h]
0x1803a0aa8  mov     rcx, [rbp+string1]; string
0x1803a0aac  call    cs:__imp_WindowsDeleteString
0x1803a0ab3  nop     dword ptr [rax+rax+00h]
0x1803a0ab8  mov     eax, ebx
0x1803a0aba  mov     rbx, [rsp+20h+arg_18]
0x1803a0abf  add     rsp, 20h
0x1803a0ac3  pop     rdi
0x1803a0ac4  pop     rsi
0x1803a0ac5  pop     rbp
0x1803a0ac6  retn
```
